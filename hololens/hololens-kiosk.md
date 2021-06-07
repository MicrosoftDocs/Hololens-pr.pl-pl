---
title: Konfigurowanie urządzenia HoloLens jako kiosku
description: Dowiedz się, jak skonfigurować konfigurację kiosku i używać jej do blokowania aplikacji na urządzeniach HoloLens.
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
ms.openlocfilehash: 347501c3ac8f1b115b0d537332a17938a99d3257
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378362"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Konfigurowanie urządzenia HoloLens jako kiosku

Urządzenie HoloLens można skonfigurować tak, aby działało jako urządzenie o stałym przeznaniu, nazywane *również kioskiem,* przez skonfigurowanie urządzenia do uruchamiania w trybie kiosku. Tryb kiosku ogranicza aplikacje (lub użytkowników), które są dostępne na urządzeniu. Tryb kiosku to wygodna funkcja, za pomocą których można dedykować urządzenie HoloLens do aplikacji biznesowych lub użyć urządzenia HoloLens w pokazie aplikacji.

Ten artykuł zawiera informacje dotyczące aspektów konfiguracji kiosku specyficznych dla urządzeń HoloLens. Aby uzyskać ogólne informacje na temat różnych typów kiosków z systemem Windows i sposobu ich konfigurowania, zobacz Configure [kiosks and digital signs on Windows desktop editions](https://docs.microsoft.com/windows/configuration/kiosk-methods)(Konfigurowanie kiosków i podpisów cyfrowych w wersjach klasycznych systemu Windows).  

> [!IMPORTANT]  
> Tryb kiosku określa, które aplikacje są dostępne, gdy użytkownik się na urządzeniu. Jednak tryb kiosku nie jest metodą zabezpieczeń. Nie zatrzymuje to otwierania przez aplikację "dozwoloną" innej aplikacji, która nie jest dozwolona. Aby zablokować otwieranie aplikacji lub procesów, należy użyć Windows Defender CSP kontroli aplikacji [(WDAC)](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) w celu utworzenia odpowiednich zasad.
>
> Dowiedz się więcej o usługi firmy Microsoft zapewnianiu użytkownikom zaawansowanego poziomu zabezpieczeń, z których korzysta urządzenie HoloLens 2, przeczytaj więcej na temat separacji i izolacji stanu — [zabezpieczenia usługi Defender.](security-state-separation-isolation.md#defender-protections) Możesz też dowiedzieć się, jak używać funkcji WDAC i Windows PowerShell do zezwalania na aplikacje lub blokowania ich na [urządzeniach HoloLens 2 z Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).

Trybu kiosku można używać w konfiguracji pojedynczej aplikacji lub wielu aplikacji, a do konfigurowania i wdrażania konfiguracji kiosku można użyć jednego z trzech procesów.

> [!IMPORTANT]  
> Usunięcie konfiguracji wielu aplikacji powoduje usunięcie profilów blokady użytkownika utworzonych przez przypisaną funkcję dostępu. Nie przywraca jednak wszystkich zmian zasad. Aby przywrócić te zasady, należy zresetować urządzenie do ustawień fabrycznych.

## <a name="plan-the-kiosk-deployment"></a>Planowanie wdrożenia kiosku

Podczas planowania kiosku musisz mieć możliwość odpowiedzi na następujące pytania. Poniżej znajdują się pewne decyzje, które należy wziąć pod uwagę podczas czytania tej strony, oraz zagadnienia dotyczące tych pytań.
1. **Kto będzie używać kiosku [](hololens-identity.md) i jakiego typu konta będą używać?** Jest to decyzja, która prawdopodobnie została już podjęta i nie powinna zostać dostosowana do potrzeb kiosku, ale będzie mieć wpływ na sposób przypisania kiosku później.
1. **Czy musisz mieć różne kioski na użytkownika/grupę lub kiosk nie jest włączony dla niektórych?** Jeśli tak, należy utworzyć kiosk za pośrednictwem kodu XML. 
1. **Ile aplikacji będzie w kiosku?** Jeśli masz więcej niż 1 aplikację, będziesz potrzebować kiosku z wieloma aplikacjami. 
1. **Które aplikacje będą dostępne w kiosku?** Skorzystaj z poniższej listy identyfikatorów AUMID, aby dodać In-Box aplikacji oprócz własnych.
1. **Jak planujesz wdrożenie kiosku?** Jeśli rejestrujesz urządzenie w funkcji MDM, zalecamy wdrożenie kiosku przy użyciu rozwiązania MDM. Jeśli nie używasz rozwiązania MDM, wdrożenie z pakietem aprowizowania jest dostępne.  

### <a name="kiosk-mode-requirements"></a>Wymagania dotyczące trybu kiosku

Do korzystania z trybu kiosku można skonfigurować dowolne urządzenie HoloLens 2.

> [!IMPORTANT]
> Tryb kiosku jest dostępny tylko wtedy, gdy urządzenie Windows Holographic for Business. Wszystkie urządzenia HoloLens 2 są Windows Holographic for Business i nie ma żadnych innych wersji. Na każdym urządzeniu HoloLens 2 można uruchomić tryb kiosku.
>
> Urządzenia HoloLens (1. generacji) należy uaktualnić zarówno pod względem kompilacji systemu operacyjnego, jak i wersji systemu operacyjnego. Poniżej znajduje się więcej informacji na temat aktualizowania urządzenia HoloLens (1. generacji) [do Windows Holographic for Business](hololens1-upgrade-enterprise.md) wersji. Aby zaktualizować urządzenie HoloLens (1. generacji) w celu używania trybu kiosku, należy najpierw upewnić się, że na urządzeniu działa Windows 10, wersja 1803 lub nowsza. Jeśli do odzyskania urządzenia HoloLens (1. generacji) do kompilacji domyślnej zostało użyte narzędzie do odzyskiwania urządzeń z systemem Windows lub zainstalowano najnowsze aktualizacje, urządzenie jest gotowe do skonfigurowania.

> [!IMPORTANT]  
> Aby ułatwić ochronę urządzeń uruchamianych w trybie kiosku, rozważ dodanie zasad zarządzania urządzeniami, które wyłączają funkcje, takie jak łączność USB. Ponadto sprawdź ustawienia pierścienia aktualizacji, aby upewnić się, że aktualizacje automatyczne nie występują w godzinach pracy.

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>Decydowanie o kiosku z jedną aplikacją lub kiosku z wieloma aplikacjami

Kiosk z jedną aplikacją uruchamia określoną aplikację, gdy użytkownik się na urządzeniu. Ta menu Start jest wyłączona, tak jak Cortana. Urządzenie HoloLens 2 nie odpowiada na gest [Start.](hololens2-basic-usage.md#start-gesture) Urządzenie HoloLens (1. generacji) nie odpowiada na gest [Blooma.](hololens1-basic-usage.md) Ponieważ można uruchomić tylko jedną aplikację, użytkownik nie może umieścić innych aplikacji.

Kiosk z wieloma aplikacjami wyświetla menu Start, gdy użytkownik się na urządzeniu. Konfiguracja kiosku określa, które aplikacje są dostępne na menu Start. Możesz użyć kiosku z wieloma aplikacjami, aby zapewnić użytkownikom łatwe do zrozumienia środowisko, prezentując im tylko te rzeczy, których potrzebują, i usuwając rzeczy, których nie potrzebują.

W poniższej tabeli wymieniono możliwości funkcji w różnych trybach kiosku.

| &nbsp; |Menu Start |Menu Szybkie akcje |Aparat i wideo |Miracast |Cortana |Wbudowane polecenia głosowe |
| --- | --- | --- | --- | --- | --- | --- | 
|Kiosk z jedną aplikacją |Disabled |Disabled |Disabled |Disabled   |Disabled |Włączone<sup>1</sup> |
|Kiosk z wieloma aplikacjami |Enabled (Włączony) |Włączone<sup>2</sup> |Dostępne<sup>2</sup> |Dostępne<sup>2</sup> |Dostępne<sup>2, 3</sup>  |Włączone<sup>1</sup> |

> <sup>1 Polecenia</sup> głosowe powiązane z wyłączonymi funkcjami nie działają.  
> <sup>2</sup> Aby uzyskać więcej informacji na temat konfigurowania tych funkcji, zobacz [Wybieranie aplikacji kiosku.](#plan-kiosk-apps)  
> <sup>3</sup> Nawet jeśli Cortana jest wyłączona, wbudowane polecenia głosowe są włączone.

W poniższej tabeli wymieniono funkcje obsługi użytkowników w różnych trybach kiosku.

| &nbsp; |Obsługiwane typy użytkowników | Automatyczne logowanie | Wiele poziomów dostępu |
| --- | --- | --- | --- |
|Kiosk z jedną aplikacją |Zarządzane konto usługi (MSA) na Azure Active Directory (Azure AD) lub na koncie lokalnym |Tak |Nie |
|Kiosk z wieloma aplikacjami |Konto usługi Azure AD |Nie |Tak |

Przykłady użycia tych możliwości można znaleźć w poniższej tabeli.

|Użyj kiosku z jedną aplikacją, aby: |Użyj kiosku z wieloma aplikacjami, aby: |
| --- | --- |
|Urządzenie z uruchomionym tylko przewodnikiem usługi Dynamics 365 dla nowych pracowników. |Urządzenie, na których działa zarówno przewodnik, jak i pomoc zdalna dla wielu pracowników. |
|Urządzenie, na których działa tylko aplikacja niestandardowa. |Urządzenie, które działa jako kiosk dla większości użytkowników (z uruchamianą tylko aplikacją niestandardową), ale działa jako urządzenie standardowe dla określonej grupy użytkowników. |

### <a name="plan-kiosk-apps"></a>Planowanie aplikacji kiosku

Aby uzyskać ogólne informacje na temat wybierania aplikacji kiosku, zobacz Wytyczne dotyczące wybierania aplikacji do przypisanego dostępu [(tryb kiosku).](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)

Jeśli używasz Portal urządzeń z systemem Windows do konfigurowania kiosku z jedną aplikacją, wybierz aplikację podczas procesu konfiguracji.  

Jeśli używasz systemu mobile Zarządzanie urządzeniami (MDM) lub pakietu aprowizowania do konfigurowania trybu kiosku, użyj dostawcy usług konfiguracji [AssignedAccess (CSP)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) do określenia aplikacji. Program CSP używa [identyfikatorów modelu użytkownika aplikacji (AUMID)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) do identyfikowania aplikacji. W poniższej tabeli wymieniono identyfikatory AUMID niektórych aplikacji, których można używać w kiosku z wieloma aplikacjami.

> [!IMPORTANT]
> Tryb kiosku określa, które aplikacje są dostępne, gdy użytkownik się na urządzeniu. Tryb kiosku nie jest jednak metodą zabezpieczeń. Nie zatrzymuje to otwierania przez aplikację "dozwoloną" innej aplikacji, która nie jest dozwolona. Ponieważ nie ograniczamy tego zachowania, aplikacje nadal mogą być uruchomione z przeglądarki Edge, Eksploratora plików i Microsoft Store aplikacji. Jeśli istnieją określone aplikacje, które nie mają być uruchomione z kiosku, utwórz odpowiednie zasady za pomocą Windows Defender CSP kontroli aplikacji [(WDAC).](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) 
> 
> Ponadto nie można Mixed Reality strony głównej jako aplikacji kiosku.

<a id="aumids"></a>

|Nazwa aplikacji |AUMID |
| --- | --- |
|Przeglądarka 3D |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|Kalendarz |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
|Aparat<sup>fotograficzny 1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! App |
|S wyboru urządzeń na urządzeniu HoloLens (1. generacja) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|S wyboru urządzenia na urządzeniu HoloLens 2 |Microsoft.Windows.DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft.Windows.DevicesFlowHost |
|Dynamics 365 Guides |Microsoft.Dynamics365.Guides \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft.RemoteAssist |
|Centrum &nbsp; opinii |Aplikacja Microsoft.WindowsFeedbackHub \_ 8wekyb3d8bbwe \! |
|Eksplorator plików |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy! App |
|Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Stare Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge |
|Nowe Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Sklepie Microsoft |Microsoft.WindowsStore_8wekyb3d8bbwe! App |
|Miracast<sup>4</sup> |&nbsp; |
|Filmy & TV |Microsoft.ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive \_ 8wekyb3d8bbwe \! App |
|Zdjęcia |Aplikacja Microsoft.Windows.Photos \_ 8wekyb3d8bbwe \! |
|Stare ustawienia |HolographicSystemSettings_cw5n1h2txyewy! App |
|Nowe ustawienia |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
|Porady |Microsoft.HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> Aby włączyć funkcję przechwytywania zdjęć lub wideo, należy włączyć aplikację Aparat jako aplikację kiosku.  
> <sup>2</sup> Po włączeniu aplikacji Aparat należy pamiętać o następujących warunkach:
> - Menu Szybkie akcje zawiera przyciski Zdjęcie i Wideo.  
> - Należy również włączyć aplikację (taką jak Zdjęcia, Poczta lub OneDrive), która może wchodzić w interakcje z obrazami lub je pobierać.  
>  
> <sup>3</sup> Nawet jeśli Cortana nie zostanie włączona jako aplikacja kiosku, wbudowane polecenia głosowe są włączone. Jednak polecenia związane z wyłączonymi funkcjami nie mają żadnego efektu.  
> <sup>4</sup> Nie można włączyć funkcji Miracast bezpośrednio. Aby włączyć miracast jako aplikację kiosku, włącz aplikację Aparat i aplikację S wyboru urządzenia.

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>Planowanie profilów kiosku dla użytkowników lub grup

Podczas tworzenia pliku XML lub używania interfejsu użytkownika usługi Intune do skonfigurowania kiosku należy rozważyć, kto będzie użytkownikiem kiosku. Konfiguracja kiosku może być ograniczona do pojedynczego konta lub grup usługi Azure AD. 

Zazwyczaj kioski są włączone dla użytkownika lub grupy użytkowników. Jeśli jednak planujesz pisanie własnego kiosku XML, warto rozważyć dostęp przypisany globalnie, w którym kiosk jest stosowany na poziomie urządzenia niezależnie od tożsamości. Jeśli jest to atrakcyjne dla Ciebie, przeczytaj więcej na temat kiosków z [dostępem przypisanym globalnie.](hololens-global-assigned-access-kiosk.md)

#### <a name="if-you-are-creating-an-xml-file"></a>Jeśli tworzysz plik XML:
-   Wiele z nich tworzy wiele profilów kiosku i przypisuje je do różnych użytkowników/grup. Na przykład kiosk dla grupy usługi Azure AD, która zawiera wiele aplikacji, oraz kiosk z wieloma aplikacjami z pojedynczą aplikacją.
-   Konfiguracja kiosku będzie nazywana **identyfikatorem profilu i** identyfikatorem GUID.
-   Przypiszesz ten profil w sekcji konfiguracji, określając typ użytkownika i używając tego samego identyfikatora GUID dla **identyfikatora DefaultProfile.**
- Plik XML można utworzyć, ale nadal stosować do urządzenia za pośrednictwem rozwiązania MDM, tworząc niestandardowy profil konfiguracji urządzenia OMA URI i stosując go do grupy urządzeń HoloLens przy użyciu wartości URI:./Device/Vendor/MSFT/AssignedAccess/Configuration

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>Jeśli tworzysz kiosk w usłudze Intune.
-   Każde urządzenie może otrzymać tylko jeden profil kiosku. W przeciwnym razie spowoduje konflikt i w ogóle nie otrzyma konfiguracji kiosku. 
    -   Inne rodzaje profilów i zasad, takie jak ograniczenia dotyczące urządzeń, które nie są związane z profilem konfiguracji kiosku, nie kolidują z profilem konfiguracji kiosku.
-   Kiosk zostanie włączony dla wszystkich użytkowników, którzy są częścią typu logowania Użytkownik. Zostanie on ustawiony za pomocą użytkownika lub grupy usługi Azure AD. 
-   Po skonfigurowaniu konfiguracji kiosku i wybraniu typu Logowanie użytkownika **(użytkownicy,** którzy mogą logować się do kiosku) i Aplikacje, konfiguracja urządzenia nadal musi być przypisana do grupy. Grupy Przypisane określają, które urządzenia odbierają konfigurację urządzenia kiosku, ale nie wchodzą w interakcje, jeśli kiosk jest włączony lub nie. 
    - Aby uzyskać pełne omówienie skutków przypisywania profilów konfiguracji w usłudze Intune, zobacz [Przypisywanie profilów](https://docs.microsoft.com/intune/configuration/device-profile-assign)użytkowników i urządzeń w usłudze Microsoft Intune .

### <a name="select-a-deployment-method"></a>Wybieranie metody wdrażania

Możesz wybrać jedną z następujących metod wdrażania konfiguracji kiosku:

- [Microsoft Intune lub inną usługę zarządzania urządzeniami przenośnymi (MDM)](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Pakiet aprowizowania](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Portal urządzeń z systemem Windows](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Ponieważ ta metoda wymaga włączonego trybu dewelopera na urządzeniu, zalecamy używanie go tylko na pokazach.

W poniższej tabeli wymieniono możliwości i zalety każdej z metod wdrażania.

| &nbsp; |Wdrażanie przy użyciu Portal urządzeń z systemem Windows |Wdrażanie przy użyciu pakietu aprowizowania |Wdrażanie przy użyciu rozwiązania MDM |
| --------------------------- | ------------- | -------------------- | ---- |
|Wdrażanie kiosków z jedną aplikacją   | Tak           | Tak                  | Tak  |
|Wdrażanie kiosków z wieloma aplikacjami    | Nie            | Tak                  | Tak  |
|Wdrażanie tylko na urządzeniach lokalnych | Tak           | Tak                  | Nie   |
|Wdrażanie przy użyciu trybu dewelopera |Wymagane       | Niewymagane            | Niewymagane   |
|Wdrażanie przy użyciu Azure Active Directory (Azure AD)  | Niewymagane            | Niewymagane                   | Wymagane  |
|Automatyczne wdrażanie      | Nie            | Nie                   | Tak  |
|Szybkość wdrażania            | Duża       | Duża                 | Mała |
|Wdrażanie w dużej skali | Niezalecane    | Zalecane        | Zalecane |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>Konfigurowanie kiosku z pojedynczą aplikacją lub kioskiem z wieloma Microsoft Intune urządzeniami przenośnymi za pomocą usługi Microsoft Intune lub innego rozwiązania MDM

Aby skonfigurować tryb kiosku przy użyciu Microsoft Intune lub innego systemu MDM, wykonaj następujące kroki.

1. [Przygotuj się do zarejestrowania urządzeń.](#mdmenroll)
1. [Utwórz profil konfiguracji kiosku.](#mdmprofile)
1. Konfigurowanie kiosku.
   - [Skonfiguruj ustawienia kiosku z jedną aplikacją.](#mdmconfigsingle)
   - [Skonfiguruj ustawienia kiosku z wieloma aplikacjami.](#mdmconfigmulti)
1. [Przypisz profil konfiguracji kiosku do grupy.](#mdmassign)
1. Wdrażanie urządzeń.
   - [Wdrażanie kiosku z jedną aplikacją.](#mdmsingledeploy)
   - [Wdrażanie kiosku z wieloma aplikacjami.](#mdmmultideploy)

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a>MDM, krok 1 &ndash; Przygotowanie do zarejestrowania urządzeń

Możesz skonfigurować system MDM do automatycznego rejestrowania urządzeń HoloLens, gdy użytkownik po raz pierwszy się zarejestruje, lub aby użytkownicy rejestrują urządzenia ręcznie. Urządzenia muszą być również przyłączone do twojej domeny usługi Azure AD i przypisane do odpowiednich grup.

Aby uzyskać więcej informacji na temat rejestrowania urządzeń, zobacz Rejestrowanie urządzenia [HoloLens](hololens-enroll-mdm.md) w usłudze MDM i Metody rejestracji urządzeń z [systemem Windows w usłudze Intune.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM, krok 2 &ndash; Tworzenie profilu konfiguracji kiosku

1. Otwórz [witrynę Azure](https://portal.azure.com/) Portal i zaloguj się do konta administratora usługi Intune.
1. Wybierz **Microsoft Intune**  >  **Konfiguracja urządzenia — Profile** Utwórz  >  **profil.**
1. Wprowadź nazwę profilu.
1. Wybierz **pozycję Ustawienia** Windows 10 i  >  **nowsze,** a następnie wybierz pozycję Typ **profilu** Ograniczenia  > **dotyczące urządzeń.**
1. Wybierz **pozycję**  >  **Skonfiguruj kiosk,** a następnie wybierz jedną z następujących opcji:
   - Aby utworzyć kiosk z jedną aplikacją, wybierz **pozycję Kiosk w trybie pojedynczej**  >  **aplikacji.**
   - Aby utworzyć kiosk z wieloma aplikacjami, wybierz **pozycję Kiosk w trybie** wielu  >  **aplikacji.**
1. Aby rozpocząć konfigurowanie kiosku, wybierz pozycję **Dodaj.**

Następne kroki różnią się w zależności od wybranego typu kiosku. Aby uzyskać więcej informacji, wybierz jedną z następujących opcji:  

- [Kiosk z jedną aplikacją](#mdmconfigsingle)
- [Kiosk z wieloma aplikacjami](#mdmconfigmulti)

Aby uzyskać więcej informacji na temat tworzenia profilu konfiguracji kiosku, zobacz Windows 10 i Windows Holographic for Business urządzenia do uruchamiania jako dedykowany kiosk przy [użyciu usługi Intune.](https://docs.microsoft.com/intune/configuration/kiosk-settings)

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM, krok 3 (pojedyncza aplikacja) &ndash;  Konfigurowanie ustawień kiosku z jedną aplikacją

Ta sekcja zawiera podsumowanie ustawień wymaganych przez kiosk z jedną aplikacją. Aby uzyskać więcej informacji, zobacz następujące artykuły:

- Aby uzyskać informacje na temat konfigurowania profilu konfiguracji kiosku w usłudze Intune, zobacz [Jak skonfigurować tryb kiosku](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)przy użyciu Microsoft Intune .
- Aby uzyskać więcej informacji na temat dostępnych ustawień kiosków z jedną aplikacją w usłudze Intune, zobacz Kioski z pojedynczą aplikacją [w trybie pełnoekranowym](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- W przypadku innych usług MDM zapoznaj się z dokumentacją dostawcy, aby uzyskać instrukcje. Jeśli musisz użyć niestandardowej konfiguracji XML do skonfigurowania kiosku w usłudze MDM, utwórz plik XML, który [definiuje konfigurację kiosku.](#ppkioskconfig)

1. Wybierz pozycję Logowanie **użytkownika** wpisz Konto użytkownika lokalnego, a następnie wprowadź nazwę użytkownika konta lokalnego (urządzenia) lub konta Microsoft  >  (MSA), które może zalogować się do kiosku.
   > [!NOTE]  
   > Konta użytkowników typu **Logowanie automatyczne** nie są obsługiwane na platformie Windows Holographic for Business.
1. Wybierz **pozycję Typ** aplikacji Aplikacja ze  >  **sklepu,** a następnie wybierz aplikację z listy.

Następnym krokiem jest [przypisanie](#mdmassign) profilu do grupy.

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM, krok 3 (wiele aplikacji) &ndash; Konfigurowanie ustawień kiosku z wieloma aplikacjami

Ta sekcja zawiera podsumowanie ustawień wymaganych przez kiosk z wieloma aplikacjami. Aby uzyskać bardziej szczegółowe informacje, zobacz następujące artykuły:

- Aby uzyskać informacje na temat konfigurowania profilu konfiguracji kiosku w usłudze Intune, zobacz [Jak skonfigurować tryb kiosku](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)przy użyciu Microsoft Intune .
- Aby uzyskać więcej informacji na temat dostępnych ustawień kiosków z wieloma aplikacjami w usłudze Intune, zobacz [Kioski z wieloma aplikacjami](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- W przypadku innych usług MDM zapoznaj się z dokumentacją dostawcy, aby uzyskać instrukcje. Jeśli musisz użyć niestandardowej konfiguracji XML do skonfigurowania kiosku w usłudze MDM, utwórz plik XML definiujący [konfigurację kiosku.](#ppkioskconfig) Jeśli używasz pliku XML, pamiętaj, aby uwzględnić układ [Start](#start-layout-for-hololens).  
- Opcjonalnie możesz użyć niestandardowego układu startowego z usługą Intune lub innymi usługami MDM. Aby uzyskać więcej informacji, zobacz [Start layout file for MDM (Intune and others) (Uruchamianie](#start-layout-file-for-mdm-intune-and-others)pliku układu dla rozwiązania MDM (usługi Intune i innych).

1. Wybierz **pozycję Target Windows 10 in S mode devices** No (Nie dla urządzeń  >  **docelowych).**  
>[!NOTE]  
> Tryb S nie jest obsługiwany na platformie Windows Holographic for Business.

1. Wybierz **pozycję User logon type**(Typ logowania użytkownika) user or group (Użytkownik lub grupa) usługi Azure AD lub User  >   **logon type** HoloLens visitor (Typ logowania użytkownika dla gościa urządzenia  >  **HoloLens),** a następnie dodaj co najmniej jedną grupę lub konto użytkownika.  

   Tylko użytkownicy, którzy należą do grup lub kont, które określisz w **typie** logowania użytkownika, mogą używać kiosku.

1. Wybierz co najmniej jedną aplikacje przy użyciu następujących opcji:
   - Aby dodać przesłaną aplikację biznesową, wybierz pozycję **Dodaj** aplikację ze sklepu, a następnie wybierz aplikację, której chcesz użyć.
   - Aby dodać aplikację, określając jej wartość AUMID, wybierz pozycję Dodaj według **AUMID,** a następnie wprowadź wartość AUMID aplikacji. [Zobacz listę dostępnych identyfikatorów AUMID](#aumids)

Następnym krokiem jest [przypisanie](#mdmassign) profilu do grupy.

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM, krok &ndash; 4. Przypisywanie profilu konfiguracji kiosku do grupy

Użyj strony **Przypisania profilu** konfiguracji kiosku, aby określić miejsce wdrożenia konfiguracji kiosku. W najprostszym przypadku przypiszesz profil konfiguracji kiosku do grupy, która będzie zawierać urządzenie HoloLens podczas rejestracji urządzenia w funkcji MDM.

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM, krok 5 (pojedyncza aplikacja) &ndash; Wdrażanie kiosku z jedną aplikacją

W przypadku korzystania z systemu MDM można zarejestrować urządzenie w układzie MDM podczas OOBE. Po zakończeniu OOBE logowanie na urządzeniu jest łatwe.

Podczas OOBE wykonaj następujące kroki:

1. Zaloguj się przy użyciu konta określonego w profilu konfiguracji kiosku.
1. Zarejestruj urządzenie. Upewnij się, że urządzenie zostało dodane do grupy, do których przypisano profil konfiguracji kiosku.
1. Poczekaj na zakończenie działania środowiska OOBE, pobranie i zainstalowanie aplikacji ze sklepu oraz zastosowanie zasad. Następnie uruchom ponownie urządzenie.

Po następnym zalogowaniu się do urządzenia aplikacja kiosku powinna zostać automatycznie uruchamiana.

Jeśli na tym etapie nie widzisz konfiguracji kiosku, [sprawdź stan przypisania](https://docs.microsoft.com/intune/configuration/device-profile-monitor).

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM, krok 5 (wiele aplikacji) &ndash; Wdrażanie kiosku z wieloma aplikacjami

Korzystając z systemu MDM, możesz dołączyć urządzenie do dzierżawy usługi Azure AD i zarejestrować je w usłudze MDM podczas OOBE. W razie potrzeby podaj informacje o rejestracji użytkownikom, aby udostępnili je podczas procesu OOBE.

> [!NOTE]  
> Jeśli profil konfiguracji kiosku został przypisany do grupy zawierającej użytkowników, upewnij się, że jedno z tych kont użytkowników jest pierwszym kontem do zalogowania się na urządzeniu.

Podczas OOBE wykonaj następujące kroki:

1. Zaloguj się przy użyciu konta należącego do **grupy typów logowania** użytkownika.
1. Zarejestruj urządzenie.
1. Poczekaj na pobranie i zainstalowanie wszystkich aplikacji, które są częścią profilu konfiguracji kiosku. Zaczekaj również na zastosowanie zasad.  
1. Po zakończeniu działania OOBE możesz zainstalować dodatkowe aplikacje ze sklepu Microsoft Store lub przez ładowanie bezpośrednio. [Wymagane aplikacje](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) dla grupy, do której należy urządzenie, aby zainstalować je automatycznie.
1. Po zakończeniu instalacji uruchom ponownie urządzenie.

Przy następnym zalogowaniu się na urządzeniu przy użyciu konta należącego do typu logowania Użytkownik **aplikacja** kiosku powinna zostać automatycznie uruchamiana.

Jeśli na tym etapie nie widzisz konfiguracji kiosku, [sprawdź stan przypisania](https://docs.microsoft.com/intune/configuration/device-profile-monitor).

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>Konfigurowanie kiosku z pojedynczą aplikacją lub wieloma aplikacjami przy użyciu pakietu aprowizowania

Aby skonfigurować tryb kiosku przy użyciu pakietu aprowizowania, wykonaj następujące kroki.

1. [Utwórz plik XML definiujący konfigurację kiosku.](#ppkioskconfig), w tym układ [Start.](#start-layout-for-hololens)
2. [Dodaj plik XML do pakietu aprowizowania.](#ppconfigadd)
3. [Zastosuj pakiet aprowizowania na urządzeniach HoloLens.](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>Pakiet aprowizowania, krok &ndash; 1. Tworzenie pliku XML konfiguracji kiosku

Postępuj [zgodnie z ogólnymi instrukcjami, aby utworzyć plik XML](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)konfiguracji kiosku dla komputerów z systemem Windows, z wyjątkiem następujących:

- Nie uwzględniaj klasycznych aplikacji systemu Windows (Win32). Urządzenie HoloLens nie obsługuje tych aplikacji.
- Użyj [symbolu zastępczego Xml układu startowego](#start-layout-for-hololens) dla urządzenia HoloLens.
- Opcjonalnie: Dodawanie dostępu gościa do konfiguracji kiosku

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>Opcjonalnie: Dodawanie dostępu gościa do konfiguracji kiosku

W [ **sekcji Konfiguracje** pliku XML](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)można skonfigurować specjalną grupę o nazwie **Odwiedzający,** aby umożliwić gościom korzystanie z kiosku. Po skonfigurowaniu kiosku do obsługi grupy specjalnej **Odwiedzający** do strony logowania zostanie dodana opcja"Gość". Konto **gościa** nie wymaga hasła, a wszystkie dane skojarzone z tym kontem są usuwane po wye m.in.

Aby włączyć konto **gościa,** dodaj następujący fragment kodu do pliku XML konfiguracji kiosku:

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```
#### <a name="enable-visitor-autologon"></a>Włączanie automatycznegologowania gości

W kompilacjach [systemu Windows Holographic w wersji 21H1](hololens-release-notes.md#windows-holographic-version-21h1) i jego wersjach:
- Konfiguracje usługi AAD i inne niż ADD obsługują automatyczne logowanie dla kont gości włączonych dla trybów kiosku.

##### <a name="non-aad-configuration"></a>Konfiguracja bez usługi AAD

1. Utwórz pakiet aprowizowania, który:
    1. Konfiguruje ustawienia środowiska uruchomieniowego/AssignedAccess, aby zezwalać na konta gości.
    1. Opcjonalnie rejestruje urządzenie w układzie MDM (ustawienia środowiska uruchomieniowego/miejsce pracy/rejestracje), aby można było nim zarządzać później.
    1. Nie twórz konta lokalnego
2. [Zastosuj pakiet aprowizowania](https://docs.microsoft.com/hololens/hololens-provisioning).

##### <a name="aad-configuration"></a>Konfiguracja usługi AAD

Urządzenia przyłączone do usługi AAD skonfigurowane do trybu kiosku mogą zalogować się do konta gościa jednym naciśnięciem przycisku na ekranie logowania. Po zalogowaniu się do konta gościa urządzenie nie wyświetli monitu o ponowne zalogowanie, dopóki gość nie zostanie jawnie wylogowany z menu Start lub urządzenie zostanie uruchomione ponownie.

Automatyczne logowanie gościa można zarządzać za pomocą niestandardowych zasad [OMA-URI:](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)

- Wartość URI: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon


| Zasady |Opis |Konfiguracje 
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | Umożliwia odwiedzającemu automatyczne logowanie do kiosku. | 1 (Tak), 0 (Nie, wartość domyślna). |

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>Układ symbolu zastępczego startu dla urządzenia HoloLens

Jeśli używasz pakietu [aprowizacyjnego do](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) skonfigurowania kiosku z wieloma aplikacjami, procedura wymaga układu Start. Dostosowywanie układu uruchamiania nie jest obsługiwane w Windows Holographic for Business. W związku z tym należy użyć układu symbolu zastępczego Start.

> [!NOTE]  
> Ponieważ kiosk z jedną aplikacją uruchamia aplikację kiosku, gdy użytkownik się do niego insyguje, nie używa ona menu Start i nie musi mieć układu Start.

> [!NOTE]  
> Jeśli używasz rozwiązania [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) do skonfigurowania kiosku z wieloma aplikacjami, opcjonalnie możesz użyć układu Start. Aby uzyskać więcej informacji, zobacz [Placeholder Start layout file for MDM (Intune and others) (Plik](#start-layout-file-for-mdm-intune-and-others)układu symbolu zastępczego startu dla rozwiązania MDM (usługi Intune i innych).

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

Zapisz poniższy przykład jako plik XML. Tego pliku można użyć podczas konfigurowania kiosku z wieloma Microsoft Intune (lub w innej usłudze MDM, która udostępnia profil kiosku).

> [!NOTE]
> Jeśli musisz użyć ustawienia niestandardowego i pełnej konfiguracji XML w celu skonfigurowania kiosku w usłudze MDM, skorzystaj z instrukcji układu Start dla pakietu [aprowizowania.](#start-layout-for-hololens)

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

1. Otwórz [program Windows Configuration Designer.](https://www.microsoft.com/store/apps/9nblggh4tx22)
1. Wybierz **pozycję Aprowizowanie zaawansowane,** wprowadź nazwę projektu, a następnie wybierz pozycję **Dalej.**
1. Wybierz **Windows 10 Holographic**, a następnie wybierz pozycję **Dalej.**
1. Wybierz pozycję **Zakończ**. Zostanie otwarty obszar roboczy pakietu.
1. Wybierz **pozycję Ustawienia środowiska**  >  **uruchomieniowego AssignedAccess**  >  **MultiAppAssignedAccessSettings.**
1. W środkowym okienku wybierz pozycję **Przeglądaj,** aby zlokalizować i wybrać utworzony plik XML konfiguracji kiosku.

   ![Zrzut ekranu przedstawiający pole MultiAppAssignedAccessSettings w programie Windows Configuration Designer](./images/multiappassignedaccesssettings.png)

1. **Opcjonalny element**. (Jeśli chcesz zastosować pakiet aprowizowania po początkowej konfiguracji urządzenia, a na urządzeniu kiosku jest już dostępny administrator, pomiń ten krok). Wybierz **pozycję Ustawienia środowiska** &gt;  &gt; **uruchomieniowego Konta Użytkownicy,** a następnie utwórz konto użytkownika. Podaj nazwę użytkownika i hasło, a następnie wybierz pozycję **Administratorzy grupy**  >  **użytkowników.**  
  
     Korzystając z tego konta, można wyświetlić stan aprowowania i dzienniki.  
1. **Opcjonalny element**. (Jeśli masz już konto inne niż konto administratora na urządzeniu kiosku, pomiń ten krok). Wybierz **pozycję Ustawienia środowiska** &gt;  &gt; **uruchomieniowego Konta Użytkownicy,** a następnie utwórz konto użytkownika lokalnego. Upewnij się, że nazwa użytkownika jest taka sama jak w przypadku konta, które określono w pliku XML konfiguracji. Wybierz **pozycję Użytkownicy**  >  **standardowi grupy użytkowników.**
1. Wybierz **pozycję Zapisz**  >  **plik.**
1. Wybierz **pozycję**  >  **Eksportuj pakiet aprowizowania,** a następnie **wybierz pozycję Właściciel** administrator  >  **IT.** W ten sposób ustawiany jest wyższy priorytet tego pakietu aprowizowania niż pakiety aprowizujące, które są stosowane do tego urządzenia z innych źródeł.
1. Wybierz opcję **Dalej**.
1. Na stronie **Zabezpieczenia pakietu aprowizowania** wybierz opcję zabezpieczeń.
   > [!IMPORTANT]  
   > W przypadku wybrania **opcji Włącz podpisywanie pakietu** należy również wybrać prawidłowy certyfikat, który ma być umożliwiający podpisywanie pakietu. W tym celu wybierz **pozycję Przeglądaj** i wybierz certyfikat, którego chcesz użyć do podpisania pakietu.
   
   > [!CAUTION]  
   > Nie wybieraj opcji **Włącz szyfrowanie pakietów.** Na urządzeniach HoloLens to ustawienie powoduje niepowodzenie aprowizowania.
1. Wybierz opcję **Dalej**.
1. Określ lokalizację wyjściową, do której ma przejść pakiet aprowizowania podczas jego budowania. Domyślnie projektant konfiguracji systemu Windows używa folderu projektu jako lokalizacji wyjściowej. Jeśli chcesz zmienić lokalizację wyjściową, wybierz pozycję **Przeglądaj**. Po zakończeniu wybierz pozycję **Dalej.**
1. Wybierz **pozycję Kompilacja,** aby rozpocząć tworzenie pakietu. Tworzenie pakietu aprowizowania nie trwa długo. Na stronie kompilacji są wyświetlane informacje o projekcie, a pasek postępu wskazuje stan kompilacji.

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>Pakiet aprowizowania, krok 3. Stosowanie pakietu &ndash; aprowizowania na urządzeniach HoloLens

Artykuł "Konfigurowanie urządzenia HoloLens przy użyciu pakietu aprowizowania" zawiera szczegółowe instrukcje dotyczące stosowania pakietu aprowizowania w następujących okolicznościach:

- Pakiet aprowizowania [można początkowo zastosować do urządzenia HoloLens podczas instalacji](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

- Po zakończeniu konfiguracji możesz również zastosować pakiet aprowizowania [do urządzenia HoloLens.](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>Konfigurowanie kiosku z jedną aplikacją przy użyciu Portal urządzeń z systemem Windows aplikacji

Aby skonfigurować tryb kiosku przy użyciu Portal urządzeń z systemem Windows, wykonaj następujące kroki.

1. [Skonfiguruj urządzenie HoloLens do korzystania z Portal urządzeń z systemem Windows](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal). Serwer Portal urządzeń to serwer internetowy na urządzeniach HoloLens, z którym można nawiązać połączenie z przeglądarki internetowej na komputerze.

    > [!CAUTION]
    > Po skonfigurowaniu urządzenia HoloLens do korzystania z Portal urządzeń należy włączyć tryb dewelopera na urządzeniu. Tryb dewelopera na urządzeniu, na Windows Holographic for Business umożliwia ładowanie aplikacji side-load. Jednak to ustawienie tworzy ryzyko, że użytkownik może instalować aplikacje, które nie zostały certyfikowane przez Microsoft Store. Administratorzy mogą zablokować możliwość włączania trybu dewelopera przy użyciu ustawienia **ApplicationManagement/AllowDeveloper Unlock** w [programie Policy CSP.](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider) [Dowiedz się więcej o trybie dewelopera.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. Na komputerze połącz się z urządzeniem HoloLens przy użyciu [sieci Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) lub [USB.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)

1. Wykonaj jedną z następujących czynności:
   - Jeśli łączysz się z Portal urządzeń z systemem Windows po raz pierwszy, [utwórz nazwę użytkownika i hasło](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - Wprowadź nazwę użytkownika i hasło, które zostały wcześniej ustawione.

    > [!TIP]
    > Jeśli w przeglądarce zostanie wyświetlony błąd certyfikatu, wykonaj [następujące kroki rozwiązywania problemów.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)

1. W Portal urządzeń z systemem Windows wybierz pozycję **Tryb kiosku.**

1. Wybierz **pozycję Włącz tryb kiosku,** wybierz aplikację do uruchomienia po uruchomieniu urządzenia, a następnie wybierz pozycję **Zapisz.**

    ![Tryb kiosku](images/kiosk.png)
1. Uruchom ponownie urządzenie HoloLens. Jeśli nadal masz otwartą Portal urządzeń, możesz wybrać  pozycję Uruchom ponownie w górnej części strony.

> [!NOTE]
> Tryb kiosku można ustawić za pośrednictwem interfejsu API REST usługi Portal urządzeń, wykonując wpis POST na wartość /api/holographic/kioskmode/settings z jednym wymaganym parametrem ciągu zapytania ("kioskModeEnabled&quot; o wartości &quot;true&quot; lub &quot;false") i jednym opcjonalnym parametrem ("startupApp" z wartością nazwy pakietu). Należy pamiętać, że Portal urządzeń jest przeznaczona tylko dla deweloperów i nie powinna być włączona na urządzeniach niezamówionych przez deweloperów. Interfejs API REST może ulec zmianie w przyszłych aktualizacjach/wydaniach.

## <a name="more-information"></a>Więcej informacji

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>Zobacz, jak skonfigurować kiosk przy użyciu pakietu aprowizowania.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>Dostęp przypisany globalnie — tryb kiosku
- Zmniejszenie zarządzania tożsamościami w przypadku kiosku przez włączenie nowej metody kiosku, która stosuje tryb kiosku na poziomie systemu.

Ta nowa funkcja umożliwia administratorowi IT skonfigurowanie urządzenia HoloLens 2 pod kątem trybu kiosku z wieloma aplikacjami, który ma zastosowanie na poziomie systemu, nie ma koligacji z żadną tożsamością w systemie i ma zastosowanie do wszystkich osób, które się do niego wyślą. Zobacz dokumentację dotyczącą kiosku z dostępem przypisanym globalnie do urządzenia [HoloLens,](hololens-global-assigned-access-kiosk.md) aby uzyskać więcej informacji na temat tej nowej funkcji.

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Automatyczne uruchamianie aplikacji w trybie kiosku z wieloma aplikacjami 
- Ukierunkowane środowisko z automatycznym uruchamianiem aplikacji, co dodatkowo zwiększa wybór interfejsu użytkownika i aplikacji wybranych dla trybu kiosku.

Dotyczy tylko trybu kiosku z wieloma aplikacjami i tylko 1 aplikacja może zostać wyznaczona do automatycznego uruchamiania przy użyciu wyróżnienia atrybutu poniżej w konfiguracji przypisanego dostępu. 

Aplikacja jest uruchamiana automatycznie po dojściu użytkownika. 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Zmiany zachowania trybu kiosku w celu obsługi awarii
Po napotkaniu błędów podczas stosowania trybu kiosku zostanie wyświetlone następujące zachowanie:

- Przed systemem Windows Holographic w wersji 20H2 — HoloLens będą wyświetlane wszystkie aplikacje w menu Start.
- Windows Holographic, wersja 20H2 — jeśli urządzenie ma konfigurację kiosku, która jest kombinacją przypisanego dostępu globalnego i dostępu przypisanego do członka grupy usługi AAD, jeśli określenie członkostwa w grupie usługi AAD nie powiedzie się, użytkownik zobaczy menu "Nic nie jest wyświetlane w menu Start".

![Obraz tego, jak wygląda teraz tryb kiosku w przypadku jego awarii.](images/hololens-kiosk-failure-behavior.png )


- Począwszy od [systemu Windows Holographic w wersji 21H1,](hololens-release-notes.md#windows-holographic-version-21h1)tryb kiosku wyszukuje dostęp przypisany globalnie przed pokazaniem pustego menu Start. W przypadku awarii w trybie kiosku grupy usługi AAD środowisko kiosku zostanie wywłaszczane do globalnej konfiguracji kiosku (jeśli występuje).

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Buforowanie członkostwa w grupie usługi Azure AD dla kiosku w trybie offline

- Bezpieczniejszy tryb kiosku dzięki wyeliminowaniu dostępnych aplikacji w przypadku awarii trybu kiosku.
- Włączono kioski offline do użytku z grupami usługi Azure AD przez maksymalnie 60 dni.

Te zasady służą do określania, ile dni może być używana pamięć podręczna członkostwa grupy usługi Azure AD w konfiguracjach przypisanego dostępu przeznaczonych dla grup usługi Azure AD dla zalogowaowego użytkownika. Gdy ta wartość zasad jest ustawiona na wartość większą niż 0, tylko pamięć podręczna jest używana w przeciwnym razie.  

Nazwa: Wartość URI AADGroupMembershipCacheValidityInDays: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min. – 0 dni  
Maks. — 60 dni 

Kroki poprawnego używania tych zasad: 
1. Utwórz profil konfiguracji urządzenia dla grup usługi Azure AD przeznaczony dla kiosku i przypisz go do urządzeń HoloLens. 
1. Utwórz niestandardową konfigurację urządzenia opartą na interfejsie OMA URI, która ustawia tę wartość zasad na żądaną liczbę dni (> 0) i przypisz ją do urządzeń HoloLens. 
    1. Wartość URI powinna zostać wprowadzona w polu tekstowym OMA-URI jako ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. Ta wartość może być między dozwolonymi wartościami minimalnej/maksymalnej.
1. Zarejestruj urządzenia HoloLens i sprawdź, czy obie konfiguracje są stosowane do urządzenia. 
1. Po pomyślnym zalogowaniu się użytkownika usługi Azure AD i pomyślnym potwierdzeniu członkostwa w grupie usługi Azure AD zostanie utworzona pamięć podręczna. 
1. Teraz użytkownik 1 usługi Azure AD może przeczekać urządzenie HoloLens w tryb offline i używać go w trybie kiosku, o ile wartość zasad zezwala na X liczbę dni. 
1. Kroki 4 i 5 można powtórzyć dla każdego innego użytkownika usługi Azure AD N. Kluczową punktu w tym miejscu jest to, że każdy użytkownik usługi Azure AD musi zalogować się do urządzenia przy użyciu Internetu, aby co najmniej raz ustalić, że należy on do grupy usługi Azure AD, której celem jest konfiguracja kiosku. 
 
> [!NOTE]
> Do momentu wykonania kroku 4 dla użytkownika usługi Azure AD występuje błąd w środowiskach "odłączonych". 


## <a name="xml-kiosk-code-samples-for-hololens"></a>Przykłady kodu kiosku XML dla urządzenia HoloLens

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>Tryb kiosku z wieloma aplikacjami przeznaczony dla grupy usługi Azure AD. 
Ten kiosk wdraża kiosk, który dla użytkowników w grupie usługi Azure AD będzie miał włączony kiosk, który obejmuje 3 aplikacje: Ustawienia, Pomoc zdalna i Centrum opinii. Aby zmodyfikować ten przykład, aby był używany natychmiast, zmień identyfikator GUID wyróżniony poniżej, aby dopasować go do własnej grupy usługi Azure AD. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>Tryb kiosku z wieloma aplikacjami przeznaczony dla konta usługi Azure AD.
Ten kiosk wdraża kiosk dla jednego użytkownika. Ma on włączoną obsługę kiosku, która obejmuje 3 aplikacje: Ustawienia, Pomoc zdalna i Centrum opinii. Aby zmodyfikować ten przykład, aby był używany natychmiast, zmień konto wyróżnione poniżej, aby dopasować je do własnego konta usługi Azure AD. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

