---
title: Konfigurowanie HoloLens jako kiosku
description: Dowiedz się, jak skonfigurować konfigurację kiosku i używać jej do blokowania aplikacji na HoloLens urządzeniach.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/27/2020
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e7f1efa99cc16b1003bd7063817451013ed2ec2661dbdf02edcd89c7984d0980
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664002"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Konfigurowanie HoloLens jako kiosku

Można skonfigurować urządzenie HoloLens, aby działało jako urządzenie o stałym przeznaniu, nazywane *również kioskiem,* przez skonfigurowanie urządzenia do uruchamiania w trybie kiosku. Tryb kiosku ogranicza aplikacje (lub użytkowników), które są dostępne na urządzeniu. Tryb kiosku to wygodna funkcja, za pomocą HoloLens można przeznaczyć urządzenie biznesowe lub użyć urządzenia HoloLens w pokazie aplikacji.

Ten artykuł zawiera informacje dotyczące aspektów konfiguracji kiosku, które są specyficzne dla HoloLens urządzeń. Aby uzyskać ogólne informacje na temat różnych typów kiosków opartych na Windows i sposobu ich konfigurowania, zobacz Configure [kiosks and digital signs on Windows desktop editions](/windows/configuration/kiosk-methods)(Konfigurowanie kiosków i podpisów cyfrowych w Windows klasycznych).  

> [!IMPORTANT]  
> Tryb kiosku określa, które aplikacje są dostępne, gdy użytkownik się na urządzeniu. Tryb kiosku nie jest jednak metodą zabezpieczeń. Nie zatrzymuje to otwierania przez aplikację "dozwoloną" innej aplikacji, która nie jest dozwolona. Aby zablokować otwieranie aplikacji lub procesów, należy użyć Windows Defender CSP kontroli aplikacji [(WDAC)](/windows/client-management/mdm/applicationcontrol-csp) w celu utworzenia odpowiednich zasad.
>
> Dowiedz się więcej o usługi firmy Microsoft, aby zapewnić użytkownikom zaawansowany poziom zabezpieczeń, z których korzysta program HoloLens 2, przeczytaj więcej na temat oddzielania i izolacji stanu — [ochrona usługi Defender.](security-state-separation-isolation.md#defender-protections) Możesz też dowiedzieć się, jak [używać funkcji WDAC i Windows PowerShell](/mem/intune/configuration/custom-profile-hololens)do zezwalania na aplikacje lub blokowania ich na HoloLens 2 z Microsoft Intune .

Trybu kiosku można używać w konfiguracji pojedynczej aplikacji lub wielu aplikacji, a do konfigurowania i wdrażania konfiguracji kiosku można użyć jednego z trzech procesów.

> [!IMPORTANT]  
> Usunięcie konfiguracji wielu aplikacji powoduje usunięcie profilów blokady użytkownika utworzonych przez przypisaną funkcję dostępu. Nie przywraca jednak wszystkich zmian zasad. Aby przywrócić te zasady, należy zresetować urządzenie do ustawień fabrycznych.

## <a name="plan-the-kiosk-deployment"></a>Planowanie wdrożenia kiosku

Podczas planowania kiosku musisz mieć możliwość odpowiedzi na następujące pytania. Poniżej znajdują się pewne decyzje, które należy wziąć pod uwagę podczas czytania tej strony, oraz kilka kwestii, które należy wziąć pod uwagę w przypadku tych pytań.
1. **KtoTo będą używać kiosku i jakiego [](hololens-identity.md) typu kont będą używać?** Jest to decyzja, która prawdopodobnie została już podjęta i nie powinna być dostosowywana w celu zapewnienia kiosku, ale będzie mieć wpływ na sposób przypisania kiosku później.
1. **Czy musisz mieć różne kioski na użytkownika/grupę lub kiosk nie jest włączony dla niektórych?** Jeśli tak, należy utworzyć kiosk za pośrednictwem kodu XML. 
1. **Ile aplikacji będzie w kiosku?** Jeśli masz więcej niż 1 aplikację, będziesz potrzebować kiosku z wieloma aplikacjami. 
1. **Które aplikacje będą dostępne w kiosku?** Skorzystaj z poniższej listy identyfikatorów AUMID, aby dodać In-Box aplikacji oprócz własnych.
1. **Jak planujesz wdrożenie kiosku?** Jeśli rejestrujesz urządzenie w funkcji MDM, zalecamy użycie rozwiązania MDM do wdrożenia kiosku. Jeśli nie używasz rozwiązania MDM, jest dostępne wdrożenie z pakietem aprowizowania.  

### <a name="kiosk-mode-requirements"></a>Wymagania dotyczące trybu kiosku

Możesz skonfigurować dowolne urządzenie HoloLens 2 do korzystania z trybu kiosku.

> [!IMPORTANT]
> Tryb kiosku jest dostępny tylko wtedy, gdy urządzenie Windows Holographic for Business. Wszystkie HoloLens 2 są Windows Holographic for Business i nie ma żadnych innych wersji. Co HoloLens 2 urządzenia mogą uruchamiać tryb kiosku.
>
> HoloLens (1. generacji) należy uaktualnić zarówno pod względem kompilacji systemu operacyjnego, jak i wersji systemu operacyjnego. Poniżej znajduje się więcej informacji na temat aktualizowania HoloLens (1. generacji) do [Windows Holographic for Business](hololens1-upgrade-enterprise.md) wersji. Aby zaktualizować urządzenie HoloLens (1. generacji) w celu używania trybu kiosku, należy najpierw upewnić się, że na urządzeniu działa Windows 10, wersja 1803 lub nowsza. Jeśli do odzyskania urządzenia z systemem HoloLens (pierwszej generacji) do kompilacji domyślnej zostało użyte narzędzie Windows Device Recovery Tool, lub jeśli zainstalowano najnowsze aktualizacje, urządzenie jest gotowe do skonfigurowania.

> [!IMPORTANT]  
> Aby ułatwić ochronę urządzeń uruchamianych w trybie kiosku, rozważ dodanie zasad zarządzania urządzeniami, które wyłączają funkcje, takie jak łączność USB. Ponadto sprawdź ustawienia pierścienia aktualizacji, aby upewnić się, że aktualizacje automatyczne nie występują w godzinach pracy.

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>Decydowanie o kiosku z jedną aplikacją lub kiosku z wieloma aplikacjami

Kiosk z jedną aplikacją uruchamia określoną aplikację, gdy użytkownik się na urządzeniu. Menu Start jest wyłączona, tak jak Cortana. Urządzenie HoloLens 2 nie odpowiada na gest [Start.](hololens2-basic-usage.md#start-gesture) Urządzenie HoloLens (1. generacji) nie odpowiada na gest [blooma.](hololens1-basic-usage.md) Ponieważ można uruchomić tylko jedną aplikację, użytkownik nie może umieścić innych aplikacji.

Kiosk z wieloma aplikacjami wyświetla menu Start, gdy użytkownik się na urządzeniu. Konfiguracja kiosku określa, które aplikacje są dostępne na menu Start. Możesz użyć kiosku z wieloma aplikacjami, aby zapewnić użytkownikom łatwe do zrozumienia środowisko, prezentując im tylko te rzeczy, których potrzebują, i usuwając rzeczy, których nie muszą używać.

W poniższej tabeli wymieniono możliwości funkcji w różnych trybach kiosku.

| &nbsp; |Menu Start |Menu Szybkie akcje |Aparat i wideo |Miracast |Cortana |Wbudowane polecenia głosowe |
| --- | --- | --- | --- | --- | --- | --- | 
|Kiosk z jedną aplikacją |Disabled |Disabled |Disabled |Disabled   |Disabled |Włączone<sup>1</sup> |
|Kiosk z wieloma aplikacjami |Enabled (Włączony) |Włączone<sup>2</sup> |Dostępne<sup>2</sup> |Dostępne<sup>2</sup> |Dostępne<sup>2, 3</sup>  |Włączone<sup>1</sup> |

> <sup>1 Polecenia</sup> głosowe, które odnoszą się do wyłączonych funkcji, nie działają.  
> <sup>2</sup> Aby uzyskać więcej informacji na temat konfigurowania tych funkcji, zobacz [Wybieranie aplikacji kiosku.](#plan-kiosk-apps)  
> <sup>3</sup> Nawet jeśli Cortana, wbudowane polecenia głosowe są włączone.

W poniższej tabeli wymieniono funkcje obsługi użytkowników w różnych trybach kiosku.

| &nbsp; |Obsługiwane typy użytkowników | Automatyczne logowanie | Wiele poziomów dostępu |
| --- | --- | --- | --- |
|Kiosk z jedną aplikacją | Konto Microsoft (MSA) na koncie Azure Active Directory (Azure AD) lub koncie lokalnym |Tak |Nie |
|Kiosk z wieloma aplikacjami |Konto usługi Azure AD |Nie |Tak |

Przykłady użycia tych możliwości można znaleźć w poniższej tabeli.

|Użyj kiosku z jedną aplikacją, aby: |Użyj kiosku z wieloma aplikacjami, aby: |
| --- | --- |
|Urządzenie z uruchomionym tylko przewodnikiem usługi Dynamics 365 dla nowych pracowników. |Urządzenie, na których działa zarówno przewodnik, jak i pomoc zdalna dla wielu pracowników. |
|Urządzenie, na których działa tylko aplikacja niestandardowa. |Urządzenie, które działa jako kiosk dla większości użytkowników (uruchamia tylko aplikację niestandardową), ale działa jako urządzenie standardowe dla określonej grupy użytkowników. |

### <a name="plan-kiosk-apps"></a>Planowanie aplikacji kiosku

Aby uzyskać ogólne informacje na temat wybierania aplikacji kiosku, zobacz Wytyczne dotyczące wybierania aplikacji na przypisany dostęp [(tryb kiosku).](/windows/configuration/guidelines-for-assigned-access-app)

Jeśli używasz tej Windows Portal urządzeń do konfigurowania kiosku z jedną aplikacją, wybierz aplikację podczas procesu instalacji.  

Jeśli używasz systemu mobile Zarządzanie urządzeniami (MDM) lub pakietu aprowizowania do konfigurowania trybu kiosku, do określania aplikacji używasz dostawcy usługi konfiguracji [AssignedAccess (CSP).](/windows/client-management/mdm/assignedaccess-csp) Program CSP używa identyfikatorów modelu użytkownika [aplikacji (AUMID)](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) do identyfikowania aplikacji. W poniższej tabeli wymieniono identyfikatory AUMID niektórych aplikacji, których można używać w kiosku z wieloma aplikacjami.

> [!IMPORTANT]
> Tryb kiosku określa, które aplikacje są dostępne, gdy użytkownik się na urządzeniu. Jednak tryb kiosku nie jest metodą zabezpieczeń. Nie zatrzymuje to otwierania przez aplikację "dozwoloną" innej aplikacji, która nie jest dozwolona. Ponieważ nie ograniczamy tego zachowania, aplikacje nadal mogą być uruchomione z przeglądarki Edge, Eksploratora plików i Microsoft Store aplikacji. Jeśli istnieją określone aplikacje, których nie chcesz uruchomiać z kiosku, użyj programu Windows Defender CSP kontroli aplikacji [(WDAC)](/windows/client-management/mdm/applicationcontrol-csp) w celu utworzenia odpowiednich zasad. 
> 
> Ponadto ustawienia Mixed Reality Home nie można ustawić jako aplikacji kiosku.

<a id="aumids"></a>

|Nazwa aplikacji |AUMID |
| --- | --- |
|Przeglądarka 3D |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|Kalendarz |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
|Aparat<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! App |
|S wyboru urządzenia na HoloLens (1. generacja) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|S wyboru urządzenia w HoloLens 2 |Microsoft. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft.Windows. DevicesFlowHost |
|Przewodniki dotyczące usługi Dynamics 365 |Microsoft.Dynamics365.Guides \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft.RemoteAssist |
|Centrum &nbsp; opinii |Microsoft.WindowsFeedbackHub \_ 8wekyb3d8bbwe \! App |
|Eksplorator plików |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy! App |
|Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Stary Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge |
|Nowe Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Sklepie Microsoft |Microsoft.WindowsStore_8wekyb3d8bbwe! App |
|Miracast<sup>4</sup> |&nbsp; |
|Filmy & TV |Microsoft.ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive \_ 8wekyb3d8bbwe \! App |
|Zdjęcia |Microsoft. Windows. Zdjęcia \_ 8wekyb3d8bbwe \! App |
|Stary Ustawienia |HolographicSystemSettings_cw5n1h2txyewy! App |
|Nowe Ustawienia |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
|Porady |Microsoft.HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> Aby włączyć funkcję przechwytywania zdjęć lub wideo, należy włączyć aplikację Aparat jako aplikację kiosku.  
> <sup>2</sup> Po włączeniu aplikacji Aparat należy pamiętać o następujących warunkach:
> - Menu Szybkie akcje zawiera przyciski Zdjęcie i Wideo.  
> - Należy również włączyć aplikację (taką jak Zdjęcia, Poczta lub OneDrive), która może wchodzić w interakcje z obrazami lub je pobierać.  
>  
> <sup>3</sup> Nawet jeśli nie włączysz Cortana jako aplikacji kiosku, wbudowane polecenia głosowe są włączone. Jednak polecenia związane z wyłączonymi funkcjami nie mają żadnego efektu.  
> <sup>4</sup> Nie można włączyć Miracast bezpośrednio. Aby włączyć Miracast jako aplikację kiosku, włącz aplikacje Aparat i S wyboru urządzenia.

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>Planowanie profilów kiosku dla użytkowników lub grup

Podczas tworzenia pliku XML lub używania interfejsu użytkownika usługi Intune do skonfigurowania kiosku należy rozważyć, kto będzie użytkownikiem kiosku. Konfiguracja kiosku może być ograniczona do pojedynczego konta lub grup usługi Azure AD. 

Zazwyczaj kioski są włączone dla użytkownika lub grupy użytkowników. Jeśli jednak planujesz pisanie własnego kiosku XML, warto rozważyć dostęp przypisany globalnie, w którym kiosk jest stosowany na poziomie urządzenia niezależnie od tożsamości. Jeśli jest to atrakcyjne dla Ciebie, przeczytaj więcej na temat kiosków z [dostępem przypisanym globalnie.](hololens-global-assigned-access-kiosk.md)

#### <a name="if-you-are-creating-an-xml-file"></a>Jeśli tworzysz plik XML:
-   Wiele z nich tworzy wiele profilów kiosku i przypisuje je do różnych użytkowników/grup. Na przykład kiosk dla grupy usługi Azure AD, która zawiera wiele aplikacji, oraz kiosk z wieloma aplikacjami z pojedynczą aplikacją.
-   Konfiguracja kiosku będzie nazywana **identyfikatorem profilu i** identyfikatorem GUID.
-   Przypiszesz ten profil w sekcji konfiguracji, określając typ użytkownika i używając tego samego identyfikatora GUID dla **identyfikatora DefaultProfile .**
- Plik XML można utworzyć, ale nadal stosować do urządzenia za pośrednictwem rozwiązania MDM, tworząc niestandardowy profil konfiguracji urządzenia OMA URI i stosując go do grupy urządzeń usługi HoloLens przy użyciu wartości URI:./Device/Vendor/MSFT/AssignedAccess/Configuration

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>Jeśli tworzysz kiosk w usłudze Intune.
-   Każde urządzenie może otrzymać tylko jeden profil kiosku. W przeciwnym razie spowoduje konflikt i w ogóle nie otrzyma konfiguracji kiosku. 
    -   Inne rodzaje profilów i zasad, takie jak ograniczenia dotyczące urządzeń, które nie są powiązane z profilem konfiguracji kiosku, nie kolidują z profilem konfiguracji kiosku.
-   Kiosk zostanie włączony dla wszystkich użytkowników, którzy są częścią typu logowania Użytkownik. Zostanie on ustawiony z użytkownikiem lub grupą usługi Azure AD. 
-   Po wybraniu opcji Konfiguracja  kiosku i typ logowania użytkownika (użytkownicy, którzy mogą logować się do kiosku) i Aplikacje są zaznaczone, konfiguracja urządzenia nadal musi być przypisana do grupy. Grupy Przypisane określają, które urządzenia odbierają konfigurację urządzenia kiosku, ale nie wchodzą w interakcje, jeśli kiosk jest włączony lub nie. 
    - Aby uzyskać pełne omówienie skutków przypisywania profilów konfiguracji w usłudze Intune, zobacz [Przypisywanie profilów](/intune/configuration/device-profile-assign)użytkowników i urządzeń w usłudze Microsoft Intune .

### <a name="select-a-deployment-method"></a>Wybieranie metody wdrażania

Możesz wybrać jedną z następujących metod wdrażania konfiguracji kiosku:

- [Microsoft Intune lub innej usługi zarządzania urządzeniami przenośnymi (MDM)](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Pakiet aprowizowania](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Portal urządzeń](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Ponieważ ta metoda wymaga, aby tryb dewelopera był włączony na urządzeniu, zalecamy używanie go tylko na pokazach.

W poniższej tabeli wymieniono możliwości i zalety każdej z metod wdrażania.

| &nbsp; |Wdrażanie przy użyciu Windows Portal urządzeń |Wdrażanie przy użyciu pakietu aprowizowania |Wdrażanie przy użyciu rozwiązania MDM |
| --------------------------- | ------------- | -------------------- | ---- |
|Wdrażanie kiosków z jedną aplikacją   | Tak           | Tak                  | Tak  |
|Wdrażanie kiosków z wieloma aplikacjami    | Nie            | Tak                  | Tak  |
|Wdrażanie tylko na urządzeniach lokalnych | Tak           | Tak                  | Nie   |
|Wdrażanie przy użyciu trybu dewelopera |Wymagane       | Niewymagane            | Niewymagane   |
|Wdrażanie przy użyciu usługi Azure Active Directory (Azure AD)  | Niewymagane            | Niewymagane                   | Wymagane  |
|Automatyczne wdrażanie      | Nie            | Nie                   | Tak  |
|Szybkość wdrażania            | Duża       | Duża                 | Mała |
|Wdrażanie w dużej skali | Niezalecane    | Zalecane        | Zalecane |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>Konfigurowanie kiosku z jedną aplikacją lub wieloma aplikacjami przy użyciu Microsoft Intune lub innego rozwiązania MDM

Aby skonfigurować tryb kiosku przy użyciu Microsoft Intune lub innego systemu MDM, wykonaj następujące kroki.

1. [Przygotuj się do zarejestrowania urządzeń.](#mdmenroll)
1. [Utwórz profil konfiguracji kiosku.](#mdmprofile)
1. Konfigurowanie kiosku.
   - [Skonfiguruj ustawienia kiosku z jedną aplikacją.](#mdmconfigsingle)
   - [Skonfiguruj ustawienia kiosku z wieloma aplikacjami.](#mdmconfigmulti)
1. [Przypisz profil konfiguracji kiosku do grupy](#mdmassign).
1. Wdrażanie urządzeń.
   - [Wdrażanie kiosku z jedną aplikacją.](#mdmsingledeploy)
   - [Wdrażanie kiosku z wieloma aplikacjami.](#mdmmultideploy)

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a>MDM, krok 1 &ndash; Przygotowanie do zarejestrowania urządzeń

Możesz skonfigurować system MDM do automatycznego rejestrowania HoloLens urządzeń podczas pierwszego rejestrowania się użytkownika lub ręcznego rejestrowania urządzeń przez użytkowników. Urządzenia muszą być również przyłączone do domeny usługi Azure AD i przypisane do odpowiednich grup.

Aby uzyskać więcej informacji na temat sposobu rejestrowania urządzeń, zobacz Rejestrowanie urządzeń HoloLens w metodach rejestracji w usłudze [MDM](hololens-enroll-mdm.md) i [Intune dla Windows urządzeń.](/mem/intune/enrollment/windows-enrollment-methods)

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM, krok &ndash; 2. Tworzenie profilu konfiguracji kiosku

1. Otwórz [witrynę Azure](https://portal.azure.com/) Portal i zaloguj się do konta administratora usługi Intune.
1. Wybierz **Microsoft Intune**  >  **Konfiguracja urządzenia — Profile** Utwórz  >  **profil.**
1. Wprowadź nazwę profilu.
1. Wybierz **pozycję Windows 10** i  >  **nowsze,** a następnie wybierz pozycję Typ **profilu**  > **Ograniczenia urządzenia.**
1. Wybierz **pozycję Konfiguruj**  >  **kiosk,** a następnie wybierz jedną z następujących opcji:
   - Aby utworzyć kiosk z jedną aplikacją, wybierz **pozycję Kiosk w trybie pojedynczej**  >  **aplikacji.**
   - Aby utworzyć kiosk z wieloma aplikacjami, wybierz **pozycję Kiosk w trybie** wielu  >  **aplikacji.**
1. Aby rozpocząć konfigurowanie kiosku, wybierz pozycję **Dodaj.**

Następne kroki różnią się w zależności od wybranego typu kiosku. Aby uzyskać więcej informacji, wybierz jedną z następujących opcji:  

- [Kiosk z jedną aplikacją](#mdmconfigsingle)
- [Kiosk z wieloma aplikacjami](#mdmconfigmulti)

Aby uzyskać więcej informacji na temat tworzenia profilu konfiguracji kiosku, zobacz Windows 10 i Windows Holographic for Business urządzenia do uruchamiania jako dedykowany kiosk przy użyciu [usługi Intune.](/intune/configuration/kiosk-settings)

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM, krok 3 (pojedyncza aplikacja) &ndash;  Konfigurowanie ustawień kiosku z jedną aplikacją

Ta sekcja zawiera podsumowanie ustawień wymaganych przez kiosk z jedną aplikacją. Aby uzyskać więcej informacji, zobacz następujące artykuły:

- Aby uzyskać informacje na temat konfigurowania profilu konfiguracji kiosku w usłudze Intune, zobacz [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Aby uzyskać więcej informacji o dostępnych ustawieniach kiosków z pojedynczą aplikacją w usłudze Intune, zobacz Kioski z pojedynczą [aplikacją pełnoekranową](/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- W przypadku innych usług MDM zapoznaj się z dokumentacją dostawcy, aby uzyskać instrukcje. Jeśli musisz użyć niestandardowej konfiguracji XML do skonfigurowania kiosku w usłudze MDM, utwórz plik XML, który [definiuje konfigurację kiosku.](#ppkioskconfig)

1. Wybierz pozycję Logowanie **użytkownika** wpisz Konto użytkownika lokalnego, a następnie wprowadź nazwę użytkownika konta lokalnego (urządzenia) lub konta Microsoft  >  (MSA), które może zalogować się do kiosku.
   > [!NOTE]  
   > Konta użytkowników typu **Logowanie automatyczne** nie są obsługiwane na platformie Windows Holographic for Business.
1. Wybierz **pozycję Typ aplikacji** Aplikacja ze  >  **sklepu,** a następnie wybierz aplikację z listy.

Następnym krokiem jest [przypisanie](#mdmassign) profilu do grupy.

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM, krok 3 (wiele aplikacji) &ndash; Konfigurowanie ustawień kiosku z wieloma aplikacjami

Ta sekcja zawiera podsumowanie ustawień wymaganych przez kiosk z wieloma aplikacjami. Aby uzyskać bardziej szczegółowe informacje, zobacz następujące artykuły:

- Aby uzyskać informacje na temat konfigurowania profilu konfiguracji kiosku w usłudze Intune, zobacz [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Aby uzyskać więcej informacji na temat dostępnych ustawień kiosków z wieloma aplikacjami w usłudze Intune, zobacz [Kioski z wieloma aplikacjami](/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- W przypadku innych usług MDM zapoznaj się z dokumentacją dostawcy, aby uzyskać instrukcje. Jeśli musisz użyć niestandardowej konfiguracji XML do skonfigurowania kiosku w usłudze MDM, utwórz plik XML, który [definiuje konfigurację kiosku.](#ppkioskconfig) Jeśli używasz pliku XML, pamiętaj, aby dołączyć układ [Start](#start-layout-for-hololens).  
- Opcjonalnie możesz użyć niestandardowego układu Start z usługą Intune lub innymi usługami MDM. Aby uzyskać więcej informacji, zobacz [Start layout file for MDM (Intune and others) (Uruchamianie](#start-layout-file-for-mdm-intune-and-others)pliku układu dla rozwiązania MDM (usługi Intune i innych).

1. Wybierz **pozycję Windows 10 na S mode**  >  **urządzeniach nie.**  
>[!NOTE]  
> Tryb S nie jest obsługiwany na platformie Windows Holographic for Business.

1. Wybierz **pozycję User logon type** Azure AD user or group (Typ logowania użytkownika) lub User  >   **logon type**(Typ logowania użytkownika HoloLens użytkownik odwiedzający), a następnie dodaj co najmniej jedną grupę lub konta  >  użytkowników.  

   Tylko użytkownicy, którzy należą do grup lub kont, które określisz w typie logowania **użytkownika,** mogą używać funkcji kiosku.

1. Wybierz co najmniej jedną aplikacje, korzystając z następujących opcji:
   - Aby dodać przesłaną aplikację biznesową, wybierz pozycję **Dodaj** aplikację ze sklepu, a następnie wybierz aplikację, której chcesz użyć.
   - Aby dodać aplikację, określając jej wartość AUMID, wybierz pozycję Dodaj według **wartości AUMID, a** następnie wprowadź wartość AUMID aplikacji. [Zobacz listę dostępnych identyfikatorów AUMID](#aumids)

Następnym krokiem jest [przypisanie](#mdmassign) profilu do grupy.

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM, krok 4 &ndash; Przypisywanie profilu konfiguracji kiosku do grupy

Użyj strony **Przypisania profilu** konfiguracji kiosku, aby ustawić miejsce wdrożenia konfiguracji kiosku. W najprostszym przypadku przypiszesz profil konfiguracji kiosku do grupy, która będzie zawierać urządzenie HoloLens podczas rejestrowania urządzenia w funkcji MDM.

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM, krok 5 (pojedyncza aplikacja) &ndash; Wdrażanie kiosku z jedną aplikacją

W przypadku korzystania z systemu MDM można zarejestrować urządzenie w układzie MDM podczas OOBE. Po zakończeniu OOBE logowanie do urządzenia jest łatwe.

Podczas OOBE wykonaj następujące kroki:

1. Zaloguj się przy użyciu konta określonego w profilu konfiguracji kiosku.
1. Zarejestruj urządzenie. Upewnij się, że urządzenie zostało dodane do grupy, do których przypisano profil konfiguracji kiosku.
1. Poczekaj na zakończenie działania środowiska OOBE, pobranie i zainstalowanie aplikacji ze sklepu oraz zastosowanie zasad. Następnie uruchom ponownie urządzenie.

Przy następnym zalogowaniu się na urządzeniu aplikacja kiosku powinna zostać automatycznie uruchamiana.

Jeśli na tym etapie nie widzisz konfiguracji kiosku, [sprawdź stan przypisania](/intune/configuration/device-profile-monitor).

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM, krok 5 (wiele aplikacji) &ndash; Wdrażanie kiosku z wieloma aplikacjami

Korzystając z systemu MDM, możesz dołączyć urządzenie do dzierżawy usługi Azure AD i zarejestrować je w usłudze MDM podczas OOBE. W razie potrzeby podaj użytkownikom informacje o rejestracji, aby były one dostępne podczas procesu OOBE.

> [!NOTE]  
> Jeśli profil konfiguracji kiosku został przypisany do grupy zawierającej użytkowników, upewnij się, że jedno z tych kont użytkowników jest pierwszym kontem do zalogowania się na urządzeniu.

Podczas OOBE wykonaj następujące kroki:

1. Zaloguj się przy użyciu konta należącego do grupy **Typów logowania** użytkownika.
1. Zarejestruj urządzenie.
1. Poczekaj na pobranie i zainstalowanie wszystkich aplikacji, które są częścią profilu konfiguracji kiosku. Ponadto zaczekaj na zastosowanie zasad.  
1. Po zakończeniu działania programu OOBE możesz zainstalować dodatkowe aplikacje ze sklepu Microsoft Store lub przez ładowanie bezpośrednio. [Wymagane aplikacje](/mem/intune/apps/apps-deploy#assign-an-app) dla grupy, do której należy urządzenie, aby zainstalować je automatycznie.
1. Po zakończeniu instalacji uruchom ponownie urządzenie.

Przy następnym zalogowaniu się do urządzenia przy użyciu konta należącego do typu logowania Użytkownik **aplikacja** kiosku powinna zostać automatycznie uruchamiana.

Jeśli na tym etapie nie widzisz konfiguracji kiosku, [sprawdź stan przypisania](/intune/configuration/device-profile-monitor).

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>Konfigurowanie kiosku z pojedynczą aplikacją lub z wieloma aplikacjami przy użyciu pakietu aprowizowania

Aby skonfigurować tryb kiosku przy użyciu pakietu aprowizowania, wykonaj następujące kroki.

1. [Utwórz plik XML definiujący konfigurację kiosku.](#ppkioskconfig), w tym układ [Start](#start-layout-for-hololens).
2. [Dodaj plik XML do pakietu aprowizowania.](#ppconfigadd)
3. [Zastosuj pakiet aprowizowania do HoloLens.](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>Pakiet aprowizowania, krok &ndash; 1. Tworzenie pliku XML konfiguracji kiosku

Postępuj [zgodnie z ogólnymi instrukcjami, aby](/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)utworzyć plik XML konfiguracji kiosku dla Windows, z wyjątkiem następujących:

- Nie dołączaj aplikacji klasycznych Windows (Win32). HoloLens nie obsługuje tych aplikacji.
- Użyj [symbolu zastępczego XML układu HoloLens.](#start-layout-for-hololens)
- Opcjonalnie: Dodaj dostęp gościa do konfiguracji kiosku

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>Opcjonalnie: Dodaj dostęp gościa do konfiguracji kiosku

W [ **sekcji Konfiguracje** pliku XML](/windows/configuration/lock-down-windows-10-to-specific-apps#configs)można skonfigurować specjalną grupę o nazwie **Odwiedzający,** aby umożliwić gościom korzystanie z kiosku. Gdy kiosk jest skonfigurowany do obsługi grupy specjalnej **Odwiedzający,** opcja **"Gość"** jest dodawana do strony logowania. Konto **gościa** nie wymaga hasła, a wszystkie dane skojarzone z tym kontem są usuwane po wy wychodzącym koncie.

Aby włączyć konto **gościa,** dodaj następujący fragment kodu do pliku XML konfiguracji kiosku:

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```
#### <a name="enable-visitor-autologon"></a>Włączanie automatycznegologowania dla gości

W kompilacjach [Windows Holographic, wersja 21H1](hololens-release-notes.md#windows-holographic-version-21h1) lub nowsza:
- Konfiguracje usługi AAD i inne niż ADD obsługują automatyczne logowanie dla kont gości włączonych dla trybów kiosku.

##### <a name="non-aad-configuration"></a>Konfiguracja bez usługi AAD

1. Utwórz pakiet aprowizowania, który:
    1. Konfiguruje ustawienia środowiska uruchomieniowego/AssignedAccess, aby umożliwić kontom odwiedzającym.
    1. Opcjonalnie rejestruje urządzenie w układzie MDM (ustawienia środowiska uruchomieniowego/miejsce pracy/rejestracje), aby można było nim zarządzać później.
    1. Nie twórz konta lokalnego
2. [Zastosuj pakiet aprowizowania](hololens-provisioning.md).

##### <a name="aad-configuration"></a>Konfiguracja usługi AAD

Urządzenia przyłączone do usługi AAD skonfigurowane do pracy w trybie kiosku mogą zalogować się do konta gościa jednym naciśnięciem przycisku na ekranie logowania. Po zalogowaniu się do konta gościa urządzenie nie będzie monitować o ponowne zalogowanie, dopóki gość nie zostanie jawnie wylogowany z menu Start lub urządzenie zostanie uruchomione ponownie.

Automatyczne logowanie gościa można zarządzać za pomocą niestandardowych zasad [OMA-URI:](/mem/intune/configuration/custom-settings-windows-10)

- Wartość URI: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon


| Zasady |Opis |Konfiguracje 
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | Umożliwia odwiedzającemu automatyczne logowanie do kiosku. | 1 (Tak), 0 (Nie, wartość domyślna). |

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>Układ symbolu zastępczego startowego dla HoloLens

Jeśli używasz pakietu [aprowizacyjnego do](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) skonfigurowania kiosku z wieloma aplikacjami, procedura wymaga układu startowego. Dostosowywanie układu uruchamiania nie jest obsługiwane w Windows Holographic for Business. W związku z tym należy użyć zastępczego układu Start.

> [!NOTE]  
> Ponieważ kiosk z jedną aplikacją uruchamia aplikację kiosku, gdy użytkownik się do niego insyguje, nie używa ona menu Start i nie musi mieć układu Start.

> [!NOTE]  
> Jeśli używasz rozwiązania [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) do skonfigurowania kiosku z wieloma aplikacjami, możesz opcjonalnie użyć układu Start. Aby uzyskać więcej informacji, zobacz [Plik zastępczego układu startowego dla rozwiązania MDM (usługi Intune i innych).](#start-layout-file-for-mdm-intune-and-others)

W przypadku układu Start dodaj następującą **sekcję StartLayout** do pliku XML aprowowania kiosku:

```xml
<!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
            <StartLayout>
                <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
                      <LayoutOptions StartTileGroupCellWidth="6" />
                      <DefaultLayoutOverride>
                        <StartLayoutCollection>
                          <defaultlayout:StartLayout GroupCellWidth="6">
                            <start:Group Name="">
                              <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
                            </start:Group>
                          </defaultlayout:StartLayout>
                        </StartLayoutCollection>
                      </DefaultLayoutOverride>
                    </LayoutModificationTemplate>
                ]]>
            </StartLayout>
            <!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
```

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a>Zastępczy plik układu startowego dla rozwiązania MDM (usługa Intune i inne)

Zapisz poniższy przykład jako plik XML. Tego pliku można użyć podczas konfigurowania kiosku z wieloma aplikacjami w usłudze Microsoft Intune (lub w innej usłudze MDM, która udostępnia profil kiosku).

> [!NOTE]
> Jeśli musisz użyć ustawienia niestandardowego i pełnej konfiguracji XML w celu skonfigurowania kiosku w usłudze MDM, skorzystaj z instrukcji startowych dotyczących pakietu [aprowizowania.](#start-layout-for-hololens)

```xml
<LayoutModificationTemplate
    xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"
    xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout"
    xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout"
    Version="1">
  <RequiredStartGroupsCollection>
    <RequiredStartGroups>
      <AppendGroup Name="">
        <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
      </AppendGroup>
    </RequiredStartGroups>
  </RequiredStartGroupsCollection>
 </LayoutModificationTemplate>
```

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>Prov. pakiet, krok 2. Dodawanie pliku XML konfiguracji &ndash; kiosku do pakietu aprowizowania

1. Otwórz [Windows Configuration Designer.](https://www.microsoft.com/store/apps/9nblggh4tx22)
1. Wybierz **pozycję Aprowizowanie zaawansowane,** wprowadź nazwę projektu, a następnie wybierz pozycję **Dalej.**
1. Wybierz **Windows 10 Holographic**, a następnie wybierz pozycję **Dalej.**
1. Wybierz pozycję **Zakończ**. Zostanie otwarty obszar roboczy pakietu.
1. Wybierz **pozycję Ustawienia środowiska**  >  **uruchomieniowego AssignedAccess**  >  **MultiAppAssignedAccessSettings.**
1. W środkowym okienku wybierz pozycję **Przeglądaj,** aby zlokalizować i wybrać utworzony plik XML konfiguracji kiosku.

   ![Zrzut ekranu przedstawiający pole MultiAppAssignedAccessSettings w Windows Configuration Designer](./images/multiappassignedaccesssettings.png)

1. **Opcjonalny element**. (Jeśli chcesz zastosować pakiet aprowizowania po początkowej konfiguracji urządzenia, a na urządzeniu kiosku jest już dostępny administrator, pomiń ten krok). Wybierz **pozycję Ustawienia środowiska** &gt; **uruchomieniowego** &gt; **Użytkownicy,** a następnie utwórz konto użytkownika. Podaj nazwę użytkownika i hasło, a następnie wybierz pozycję **Administratorzy grupy**  >  **użytkowników.**  
  
     Za pomocą tego konta można wyświetlić stan i dzienniki aprowingu.  
1. **Opcjonalny element**. (Jeśli masz już konto inne niż administrator na urządzeniu kiosku, pomiń ten krok). Wybierz **pozycję Ustawienia środowiska** &gt; **uruchomieniowego** &gt; **Użytkownicy,** a następnie utwórz konto użytkownika lokalnego. Upewnij się, że nazwa użytkownika jest taka sama jak dla konta, które jest określone w konfiguracji XML. Wybierz **pozycję Użytkownicy**  >  **standardowi grupy użytkowników .**
1. Wybierz **pozycję Plik**  >  **Zapisz.**
1. Wybierz **pozycję**  >  **Eksportuj pakiet aprowizowania,** a następnie **wybierz pozycję Właściciel** administrator  >  **IT.** W ten sposób ustawiany jest wyższy priorytet tego pakietu aprowizowania niż pakiety aprowizujące, które są stosowane do tego urządzenia z innych źródeł.
1. Wybierz opcję **Dalej**.
1. Na stronie **Zabezpieczenia pakietu aprowizowania** wybierz opcję zabezpieczeń.
   > [!IMPORTANT]  
   > W przypadku wybrania **opcji Włącz podpisywanie** pakietu należy również wybrać prawidłowy certyfikat do użycia podczas podpisywania pakietu. W tym celu wybierz **pozycję Przeglądaj** i wybierz certyfikat, którego chcesz użyć do podpisania pakietu.
   
   > [!CAUTION]  
   > Nie wybieraj **opcji Włącz szyfrowanie pakietów.** Na HoloLens to ustawienie powoduje niepowodzenie aprowizowania.
1. Wybierz opcję **Dalej**.
1. Określ lokalizację wyjściową, do której ma przejść pakiet aprowizowania podczas jego budowania. Domyślnie program Windows Configuration Designer używa folderu projektu jako lokalizacji wyjściowej. Jeśli chcesz zmienić lokalizację wyjściową, wybierz pozycję **Przeglądaj**. Po zakończeniu wybierz pozycję **Dalej.**
1. Wybierz **pozycję Kompilacja,** aby rozpocząć kompilowanie pakietu. Tworzenie pakietu aprowizowania nie trwa długo. Na stronie kompilacji są wyświetlane informacje o projekcie, a pasek postępu wskazuje stan kompilacji.

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>Pakiet aprowizowania, krok &ndash; 3. Stosowanie pakietu aprowizowania do HoloLens

Artykuł "Konfigurowanie HoloLens za pomocą pakietu aprowizowania" zawiera szczegółowe instrukcje stosowania pakietu aprowizowania w następujących okolicznościach:

- Możesz początkowo zastosować [pakiet aprowizowania do usługi HoloLens podczas instalacji.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

- Możesz również zastosować [pakiet aprowizowania do usługi HoloLens po zakończeniu instalacji.](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>Konfigurowanie kiosku z jedną aplikacją za pomocą Windows Portal urządzeń aplikacji

Aby skonfigurować tryb kiosku przy użyciu Windows Portal urządzeń, wykonaj następujące kroki.

1. [Skonfiguruj urządzenie HoloLens do korzystania z Windows Portal urządzeń](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal). Serwer Portal urządzeń to serwer internetowy na komputerze HoloLens z którym można nawiązać połączenie z przeglądarki internetowej na komputerze.

    > [!CAUTION]
    > Po skonfigurowaniu HoloLens korzystania z Portal urządzeń należy włączyć tryb dewelopera na urządzeniu. Tryb dewelopera na urządzeniu, które Windows Holographic for Business umożliwia ładowanie aplikacji side-load. Jednak to ustawienie powoduje ryzyko, że użytkownik będzie może instalować aplikacje, które nie zostały certyfikowane przez Microsoft Store. Administratorzy mogą zablokować możliwość włączania trybu dewelopera przy użyciu ustawienia **ApplicationManagement/AllowDeveloper Unlock** w [programie Policy CSP.](/windows/client-management/mdm/policy-configuration-service-provider) [Dowiedz się więcej o trybie dewelopera.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. Na komputerze połącz się z siecią HoloLens za pomocą [sieci Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) lub [USB.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)

1. Wykonaj jedną z następujących czynności:
   - Jeśli łączysz się z Windows Portal urządzeń po raz pierwszy, [utwórz nazwę użytkownika i hasło](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - Wprowadź nazwę użytkownika i hasło, które zostały wcześniej ustawione.

    > [!TIP]
    > Jeśli w przeglądarce zostanie wyświetlony błąd certyfikatu, wykonaj [następujące kroki rozwiązywania problemów.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)

1. W Windows Portal urządzeń wybierz pozycję **Tryb kiosku.**

1. Wybierz **pozycję Włącz tryb kiosku,** wybierz aplikację do uruchomienia po uruchomieniu urządzenia, a następnie wybierz pozycję **Zapisz.**

    ![Tryb kiosku](images/kiosk.png)
1. Uruchom ponownie HoloLens. Jeśli nadal masz otwartą Portal urządzeń, możesz wybrać  pozycję Uruchom ponownie w górnej części strony.

> [!NOTE]
> Tryb kiosku można ustawić za pośrednictwem interfejsu API REST usługi Portal urządzeń, wykonując wpis POST na wartość /api/holographic/kioskmode/settings z jednym wymaganym parametrem ciągu zapytania ("kioskModeEnabled&quot; o wartości &quot;true&quot; lub &quot;false") i jednym opcjonalnym parametrem ("startupApp" z wartością nazwy pakietu). Należy pamiętać, że Portal urządzeń jest przeznaczona tylko dla deweloperów i nie powinna być włączona na urządzeniach niezamówionych przez deweloperów. Interfejs API REST może ulec zmianie w przyszłych aktualizacjach/wydaniach.

## <a name="more-information"></a>Więcej informacji

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>Zobacz, jak skonfigurować kiosk przy użyciu pakietu aprowizowania.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>Dostęp przypisany globalnie — tryb kiosku
- Zmniejszenie zarządzania tożsamościami w przypadku kiosku przez włączenie nowej metody kiosku, która stosuje tryb kiosku na poziomie systemu.

Ta nowa funkcja umożliwia administratorowi IT skonfigurowanie urządzenia z systemem HoloLens 2 pod kątem trybu kiosku z wieloma aplikacjami, który ma zastosowanie na poziomie systemu, nie ma koligacji z żadną tożsamością w systemie i ma zastosowanie do wszystkich osób, które się na nim pojawiają. Zobacz [dokumentację HoloLens kiosku z dostępem](hololens-global-assigned-access-kiosk.md) globalnym, aby uzyskać więcej informacji na temat tej nowej funkcji.

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Automatyczne uruchamianie aplikacji w trybie kiosku z wieloma aplikacjami 
- Ukierunkowane środowisko z automatycznym uruchamianiem aplikacji, co dodatkowo zwiększa wybór interfejsu użytkownika i aplikacji wybranych dla trybu kiosku.

Dotyczy tylko trybu kiosku z wieloma aplikacjami i tylko 1 aplikacja może zostać wyznaczona do automatycznego uruchamiania przy użyciu wyróżnienia atrybutu poniżej w konfiguracji przypisanego dostępu. 

Aplikacja jest uruchamiana automatycznie po dojściu użytkownika. 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Zmiany zachowania trybu kiosku w celu obsługi błędów
Po napotkaniu błędów podczas stosowania trybu kiosku zostanie wyświetlone następujące zachowanie:

- Przed Windows Holographic w wersji 20H2 — HoloLens będą wyświetlane wszystkie aplikacje w menu Start.
- Windows Holographic, wersja 20H2 — jeśli urządzenie ma konfigurację kiosku, która jest kombinacją przypisanego dostępu globalnego i przypisanego do członka grupy usługi AAD, w przypadku określenia niepowodzenia członkostwa w grupie usługi AAD użytkownik zobaczy menu "nic nie jest wyświetlane w menu Start".

![Obraz tego, jak wygląda teraz tryb kiosku w przypadku jego awarii.](images/hololens-kiosk-failure-behavior.png )


- Począwszy od Windows Holographic w wersji [21H1,](hololens-release-notes.md#windows-holographic-version-21h1)tryb kiosku wyszukuje dostęp przypisany globalnie, zanim zostanie wyświetlane puste menu Start. W przypadku awarii w trybie kiosku grupy usługi AAD środowisko kiosku zostanie wywłaszczane do globalnej konfiguracji kiosku (jeśli występuje).

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Buforowanie członkostwa w grupie usługi Azure AD dla kiosku w trybie offline

- Bezpieczniejszy tryb kiosku dzięki wyeliminowaniu dostępnych aplikacji w przypadku awarii trybu kiosku.
- Włączono kioski offline do użytku z grupami usługi Azure AD przez maksymalnie 60 dni.

Te zasady służą do określania, ile dni może być używana pamięć podręczna członkostwa grupy usługi Azure AD w konfiguracjach przypisanego dostępu przeznaczonych dla grup usługi Azure AD dla zalogowaowego użytkownika. Gdy ta wartość zasad jest ustawiona na wartość większą niż 0, tylko pamięć podręczna jest używana w przeciwnym razie.  

Nazwa: Wartość URI AADGroupMembershipCacheValidityInDays: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min. – 0 dni  
Maks. — 60 dni 

Kroki poprawnego używania tych zasad: 
1. Utwórz profil konfiguracji urządzenia dla grup usługi Azure AD przeznaczonych dla kiosku i przypisz go do HoloLens urządzeń. 
1. Utwórz niestandardową konfigurację urządzenia opartą na interfejsie OMA URI, która ustawia tę wartość zasad na żądaną liczbę dni (> 0) i przypisz ją do HoloLens urządzeń. 
    1. Wartość URI powinna zostać wprowadzona w polu tekstowym OMA-URI jako ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. Ta wartość może być między dozwolonymi wartościami minimalnej/maksymalnej.
1. Zarejestruj HoloLens i sprawdź, czy obie konfiguracje są stosowane do urządzenia. 
1. Po pomyślnym zalogowaniu się użytkownika usługi Azure AD i pomyślnym potwierdzeniu członkostwa w grupie usługi Azure AD zostanie utworzona pamięć podręczna. 
1. Teraz użytkownik 1 usługi Azure AD może prze HoloLens w tryb offline i używać go w trybie kiosku, o ile wartość zasad zezwala na X liczbę dni. 
1. Kroki 4 i 5 można powtórzyć dla każdego innego użytkownika usługi Azure AD N. Kluczową punktu w tym miejscu jest to, że każdy użytkownik usługi Azure AD musi zalogować się do urządzenia przy użyciu Internetu, aby co najmniej raz ustalić, że należy on do grupy usługi Azure AD, której celem jest konfiguracja kiosku. 
 
> [!NOTE]
> Do momentu wykonania kroku 4 dla użytkownika usługi Azure AD występuje błąd w środowiskach "odłączonych". 


## <a name="xml-kiosk-code-samples-for-hololens"></a>Przykłady kodu kiosku XML dla HoloLens

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>Tryb kiosku z wieloma aplikacjami przeznaczony dla grupy usługi Azure AD. 
Ten kiosk wdraża kiosk, który dla użytkowników w grupie usługi Azure AD będzie miał włączony kiosk, który obejmuje 3 aplikacje: Ustawienia, Remote Assist i Centrum opinii. Aby zmodyfikować ten przykład, aby był używany natychmiast, zmień identyfikator GUID wyróżniony poniżej, aby dopasować go do własnej grupy usługi Azure AD. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>Tryb kiosku z wieloma aplikacjami przeznaczony dla konta usługi Azure AD.
Ten kiosk wdraża kiosk dla jednego użytkownika. Ma on włączoną obsługę kiosku, która obejmuje 3 aplikacje: Ustawienia, Remote Assist i Centrum opinii. Aby zmodyfikować ten przykład, aby był używany natychmiast, zmień konto wyróżnione poniżej, aby dopasować je do własnego konta usługi Azure AD. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

