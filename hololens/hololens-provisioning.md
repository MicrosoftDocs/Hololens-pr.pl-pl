---
title: Konfigurowanie HoloLens przy użyciu pakietu aprowizowania (HoloLens)
description: Windows aprowizowanie ułatwia administratorom IT konfigurowanie urządzeń użytkowników końcowych bez przetwarzania obrazów.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.custom:
- CI 115190
- CSSTroubleshooting
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: Teresa-Motiv
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: d9a0901a916ec33c076eeae33b680406a45f7feefe82442da1f346e78bc9b383
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663667"
---
# <a name="configure-hololens-by-using-a-provisioning-package"></a>Konfigurowanie HoloLens przy użyciu pakietu aprowizowania

[Windows aprowizowanie](/windows/configuration/provisioning-packages/provisioning-packages) ułatwia administratorom IT konfigurowanie urządzeń użytkowników końcowych bez przetwarzania obrazów. Windows Configuration Designer to narzędzie do konfigurowania obrazów i ustawień środowiska uruchomieniowego, które są następnie wbudowane w pakiety aprowingu.

Oto niektóre HoloLens konfiguracji, które można zastosować w pakiecie aprowizowania:

- Uaktualnianie do [Windows Holographic for Business](hololens1-upgrade-enterprise.md)
- Konfigurowanie konta lokalnego
- Konfigurowanie połączenia Wi-Fi sieciowego
- Stosowanie certyfikatów do urządzenia
- Włączanie trybu dewelopera
- Skonfiguruj tryb kiosku, korzystając z naszych [szczegółowych instrukcji.](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

## <a name="provisioning-package-hololens-wizard"></a>Kreator inicjowania obsługi HoloLens pakietu

Kreator HoloLens pomaga skonfigurować następujące ustawienia w pakiecie aprowizowania:

- Uaktualnianie do wersji Enterprise

    > [!NOTE]
    > Należy jej używać tylko w przypadku HoloLens pierwszej generacji. Ustawienia pakietu aprowizowania są stosowane tylko wtedy, gdy pakiet aprowizowania zawiera licencję uaktualnienia wersji do programu Windows Holographic for Business lub jeśli urządzenie zostało już uaktualnione do [wersji Windows Holographic for Business.](hololens1-upgrade-enterprise.md)

- Konfigurowanie pierwszego HoloLens (OOBE)
- Konfigurowanie sieci Wi-Fi sieci
- Zarejestruj urządzenie w Azure Active Directory lub utwórz konto lokalne
- Dodawanie certyfikatów
- Włączanie trybu dewelopera
- Skonfiguruj tryb kiosku, korzystając ze [szczegółowych instrukcji](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk).

> [!WARNING]
> Należy uruchomić program Windows Configuration Designer na Windows 10, aby skonfigurować Azure Active Directory rejestracji przy użyciu dowolnego kreatora.

Pakiety aprowizowania mogą obejmować instrukcje i zasady zarządzania, niestandardowe połączenia sieciowe i zasady i nie tylko.

> [!TIP]
> Użyj kreatora pulpitu, aby utworzyć pakiet z wspólnymi ustawieniami, a następnie przejdź do edytora zaawansowanego, aby dodać inne ustawienia, aplikacje, zasady itp.

## <a name="steps-for-creating-provisioning-packages"></a>Kroki tworzenia pakietów aprowizowania

1. **Opcja 1.** [Z Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22). Obejmuje to HoloLens 2.
2. **Opcja 2.** [Z zestawu Windows Assessment and Deployment Kit (ADK) dla](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit)programu Windows 10 . Jeśli zainstalujesz program Windows Configuration Designer z zestawu Windows  ADK, wybierz pozycję Projektant konfiguracji w oknie dialogowym Wybierz funkcje, które **chcesz** zainstalować. Ta opcja nie obejmuje możliwości HoloLens 2.

> [!NOTE]
> Jeśli wiesz, że będziesz używać komputera w trybie offline, który wymaga dostępu do projektanta konfiguracji usługi Windows, postępuj zgodnie z instrukcjami [offline app install(hololens-recovery.md#downloading-arc-without-using-the-app-store) dotyczącymi zaawansowanego pomocnika odzyskiwania. Zaznacz Windows Projektanta konfiguracji. 

### <a name="2-create-the-provisioning-package"></a>2. Tworzenie pakietu aprowizowania

Użyj narzędzia Windows Configuration Designer, aby utworzyć pakiet aprowizowania.

1. Otwórz Windows Configuration Designer (domyślnie %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe).

2. Wybierz **pozycję Aprowizuj HoloLens urządzeń.**

   ![Opcje uruchamiania ICD](images/icd-create-options-1703.png)

3. Nadaj projektowi nazwę i wybierz **pozycję Zakończ.**

4. Przeczytaj instrukcje na stronie **Wprowadzenie** i wybierz pozycję **Dalej.** Na stronach aprowizowania pulpitu przedstawiono poniższe kroki.
  
> [!IMPORTANT]
> Podczas kompilowania pakietu aprowizowania możesz uwzględnić poufne informacje w plikach projektu i w pliku pakietu aprowizowania (ppkg). Mimo że istnieje możliwość zaszyfrowania pliku ppkg, pliki projektu nie są szyfrowane. Pliki projektu należy przechowywać w bezpiecznej lokalizacji i usuwać je, gdy nie są już potrzebne.

### <a name="configure-settings"></a>Konfigurowanie ustawień

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>Przejdź do pliku licencji enterprise i wybierz go, aby uaktualnić HoloLens wersji.</br></br>Możesz również przełączyć opcję <strong>Tak</strong> lub <strong>Nie,</strong> aby ukryć części pierwszego doświadczenia.</br></br>Aby skonfigurować urządzenie bez konieczności łączenia się z siecią Wi-Fi, przełącz przełącznik Pomiń Wi-Fi <strong>konfiguracji</strong> na <strong>wartość Wł.</strong>.</br></br>Wybierz region i strefę czasową, w których będzie używane urządzenie. </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>W tej sekcji można wprowadzić szczegóły sieci Wi-Fi sieci bezprzewodowej, z które urządzenie powinno automatycznie nawiązać połączenie. W tym celu <strong></strong>wybierz pozycję Wł., wprowadź wartość SSID, typ sieci (<strong>Otwórz</strong> lub <strong>WPA2-Personal</strong>) i (jeśli <strong>WPA2-Personal</strong>) hasło sieci bezprzewodowej.</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>Możesz zarejestrować urządzenie w Azure Active Directory lub utworzyć konto lokalne na urządzeniu</br></br>Przed skonfigurowaniem rejestracji zbiorczej w usłudze Azure AD za pomocą kreatora Windows Configuration Designer skonfiguruj dołączanie do usługi <a href="/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](/azure/active-directory/active-directory-azureadjoin-setup)">Azure AD w organizacji.</a> Maksymalna <strong>liczba urządzeń na użytkownika</strong> w dzierżawie usługi Azure AD określa, ile razy można użyć tokenu zbiorczego, który można uzyskać w kreatorze. Aby zarejestrować urządzenie w usłudze Azure AD, wybierz tę opcję i wprowadź przyjazną nazwę tokenu zbiorczego, który otrzymasz za pomocą kreatora. Ustaw datę wygaśnięcia tokenu (maksymalnie 30 dni od daty uzyskania tokenu). Wybierz <strong>pozycję Pobierz token zbiorczy.</strong> W <strong>oknie&#39;możesz</strong> się zalogować wprowadź konto z uprawnieniami do dołączania urządzenia do usługi Azure AD, a następnie hasło. Wybierz <strong>pozycję Zaakceptuj,</strong> aby Windows Configuration Designer wymagane uprawnienia. </br></br>Aby utworzyć konto lokalne, wybierz tę opcję i wprowadź nazwę użytkownika i hasło. </br></br><strong>Ważne:</strong> <br />(Tylko Windows 10 wersji 1607) Jeśli tworzysz konto lokalne w pakiecie aprowizowania, musisz zmienić hasło przy użyciu <strong>aplikacji Ustawienia</strong> co 42 dni. Jeśli hasło nie zostanie zmienione w tym okresie, konto może zostać zablokowane i nie będzie można się zalogować.  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>Aby aprowizować urządzenie przy użyciu certyfikatu, kliknij <strong>pozycję Dodaj certyfikat.</strong> Wprowadź nazwę certyfikatu, a następnie przejdź do i wybierz certyfikat, który ma być używany.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>Przełącz opcję <strong>Tak</strong> lub <strong>Nie,</strong> aby włączyć tryb dewelopera na HoloLens. <a href="/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">Dowiedz się więcej o trybie dewelopera.</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br>Nie należy ustawiać hasła w celu ochrony pakietu aprowizowania. Jeśli pakiet aprowizowania jest chroniony hasłem, aprowizowanie HoloLens nie powiedzie się.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

Po zakończeniu wybierz pozycję **Utwórz**. Trwa to tylko kilka sekund. Po s zbudowaniu pakietu lokalizacja, w której pakiet jest przechowywany, jest wyświetlana jako hiperlink w dolnej części strony.

### <a name="3-create-a-provisioning-package-for-hololens-by-using-advanced-provisioning"></a>3. Tworzenie pakietu aprowizowania dla HoloLens przy użyciu zaawansowanej aprowrowi

> [!NOTE]
> Pakiet aprowizowania,  który tworzysz w zaawansowanej aprowiwizowania, nie musi zawierać licencji uaktualnienia wersji, aby Windows Holographic for Business pomyślnie zastosować do aplikacji HoloLens (1. generacji). [Zobacz więcej informacji na Windows Holographic for Business for HoloLens (1. generacja).](hololens1-upgrade-enterprise.md)

1. Na stronie Windows Configuration Designer wybierz pozycję **Aprowizowanie zaawansowane.**
2. W **oknie Enter project details** (Wprowadź szczegóły projektu) określ nazwę projektu i lokalizację projektu. Opcjonalnie wprowadź krótki opis, aby opisać projekt.

3. Wybierz opcję **Dalej**.

4. W **oknie Wybierz ustawienia do wyświetlenia i** skonfigurowania wybierz pozycję Windows 10 Holographic , **a** następnie wybierz pozycję **Dalej.**

5. Wybierz pozycję **Zakończ**.

6. Rozwiń **pozycję Ustawienia** środowiska uruchomieniowego i dostosuj pakiet przy użyciu dowolnego z ustawień opisanych [w dalszej części tego artykułu.](#what-you-can-configure)

    > [!IMPORTANT]
    > (Tylko Windows 10 wersji 1607) Jeśli tworzysz konto lokalne w pakiecie aprowizowania, musisz zmienić hasło przy użyciu **aplikacji Ustawienia** co 42 dni. Jeśli hasło nie zostanie zmienione w tym okresie, konto może zostać zablokowane i nie będzie można się zalogować. Jeśli konto użytkownika jest zablokowane, należy [wykonać pełne odzyskiwanie urządzenia.](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery)

7. Wybierz **pozycję Zapisz**  >  **plik.**

8. Przeczytaj ostrzeżenie, że pliki projektu mogą zawierać poufne informacje, a następnie wybierz przycisk **OK**.

    > [!IMPORTANT]
    > Podczas kompilowania pakietu aprowizowania możesz uwzględnić poufne informacje w plikach projektu i w pliku pakietu aprowizowania (ppkg). Mimo że istnieje możliwość zaszyfrowania pliku ppkg, pliki projektu nie są szyfrowane. Pliki projektu należy przechowywać w bezpiecznej lokalizacji i usuwać je, gdy nie są już potrzebne.
    
9. Wybierz **pozycję**  >  **Eksportuj pakiet aprowizowania.**

10. Zmień **właściciela na** administratora **IT.** W ten sposób ustawiany jest wyższy priorytet tego pakietu aprowizowania niż pakiety aprowizacyjne stosowane do tego urządzenia z innych źródeł. Wybierz opcję **Dalej**.

11. Ustaw wartość dla wersji **pakietu**.

    > [!TIP]
    > Możesz wprowadzić zmiany w istniejących pakietach i zmienić numer wersji, aby zaktualizować wcześniej zastosowane pakiety.

12. Na stronie Select security details for the provisioning package (Wybieranie szczegółów zabezpieczeń **dla pakietu aprowizowania)** wybierz pozycję **Next (Dalej).**

    > [!WARNING]
    > Jeśli zaszyfrujemy pakiet aprowizowania, aprowizowanie HoloLens nie powiedzie się.  

13. Wybierz **przycisk** Dalej, aby określić lokalizację wyjściową, w której ma zostać sbudowaną zawartość pakietu aprowizowania. Domyślnie program Windows Configuration Designer używa folderu projektu jako lokalizacji wyjściowej.

    Opcjonalnie możesz wybrać pozycję **Przeglądaj,** aby zmienić domyślną lokalizację wyjściową.

14. Wybierz opcję **Dalej**.

15. Wybierz **pozycję Kompilacja,** aby rozpocząć kompilowanie pakietu. Informacje o projekcie są wyświetlane na stronie kompilacji, a pasek postępu wskazuje stan kompilacji.

16. Po zakończeniu kompilacji wybierz pozycję **Zakończ.**

<span id="apply" />

## <a name="apply-a-provisioning-package-to-hololens-during-setup"></a>Stosowanie pakietu aprowizowania do pakietu HoloLens podczas instalacji

HoloLens urządzenia z systemem Windows Holographic w wersji 2004 lub kompilacji [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) lub nowszej mogą używać dysku USB w celu zastosowania pakietu aprowizowania. Po prostu skopiuj plik ppkg do katalogu głównego dysku USB. Pakiety aprowizowania będą stosowane tylko wtedy, gdy są w katalogu głównym dysku USB. Wiele pakietów aprowizowania będzie stosowanych sekwencyjnie.

HoloLens urządzenia z systemem [Windows Holographic w wersji 20H2](hololens-release-notes.md#windows-holographic-version-20h2) lub nowszej mają nowsze funkcje ułatwiające usprawnienie i uproszczenie tego procesu, dzięki czemu jest on automatyczny. Zapoznaj się z następującymi sekcjami:

- [Automatyczne uruchamianie aprowizowania z dysku USB](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [Automatyczne potwierdzanie pakietów aprowizowania w OOBE](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [Automatyczne aprowizowanie bez użycia interfejsu użytkownika](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. Użyj kabla USB, aby podłączyć urządzenie do komputera (lub dysku USB HoloLens 2, jak wspomniano powyżej), a następnie uruchom urządzenie. Nie przechodz po **stronie pierwszego wejdą w interakcję momentu** OOBE.   
    - Na HoloLens (1. generacji) ta strona zawiera niebieskie pole. 
    - Na HoloLens 2 ta strona zawiera łańcingbird.

2. Naciśnij krótko i zwolnij przyciski **Volume Down** i **Power** jednocześnie. 

3. HoloLens urządzenie jest Eksplorator plików na komputerze.

4. W Eksplorator plików przeciągnij i upuść pakiet aprowizowania (ppkg) do magazynu urządzenia.

5. Na krótko naciśnij i zwolnij przyciski **Volume Down** i **Power** jednocześnie na stronie **Pierwszy** moment interakcji Wobe.

6. Urządzenie zapyta, czy pakiet jest zaufany i czy chcesz go zastosować. Upewnij się, że pakiet jest zaufany.

7. Zobaczysz, czy pakiet został zastosowany pomyślnie. Jeśli to się nie powiedzie, możesz naprawić pakiet i spróbować ponownie. Jeśli to się powiodło, przejdź do OOBE.

> [!NOTE]
> Jeśli urządzenie zostało zakupione przed sierpniem 2016 r., musisz zalogować się na nim przy użyciu usługi konto Microsoft, pobrać najnowszą aktualizację systemu operacyjnego, a następnie zresetować system operacyjny, aby zastosować pakiet aprowizowania.

### <a name="auto-launch-provisioning-from-usb"></a>Automatyczne uruchamianie aprowizowania z dysku USB

- Zautomatyzowane procesy, które pozwalają na mniejszą interakcję z użytkownikiem, gdy dyski USB z pakietami aprowizowania są używane podczas OOBE.

Przed wydaniem użytkownicy musieli ręcznie uruchomić ekran aprowizowania podczas OOBE, aby aprowizować przy użyciu kombinacji przycisków. Teraz użytkownicy mogą pominąć kombinację przycisków przy użyciu pakietu aprowizowania na dysku pamięci MASOWEJ USB. 

1. Podłącz dysk USB za pomocą pakietu aprowizowania podczas pierwszej interakcji ZOBE
1. Gdy urządzenie będzie gotowe do aprowizowania, automatycznie otworzy monit ze stroną aprowizowania. 

Uwaga: Jeśli dysk USB jest podłączony do zasilania podczas rozruchu urządzenia, system OOBE wyliczy istniejące urządzenie magazynujące USB, a także będzie obserwować dodatkowe podłączone urządzenia.

Przeczytaj informacje na [temat stosowania pakietów aprowingu podczas OOBE.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Automatyczne potwierdzanie pakietów aprowizowania w OOBE
- Zautomatyzowany proces umożliwiający mniejszą interakcję z użytkownikiem. Gdy zostanie wyświetlona strona Pakiet aprowizowania, automatycznie zastosuje wszystkie wymienione pakiety.

Gdy pojawi się ekran główny aprowizowania, program OOBE odliczy 10 sekund, zanim automatycznie rozpocznie stosowanie wszystkich pakietów aprowiwizowania. Użytkownicy mogą nadal potwierdzić lub anulować w ciągu tych 10 sekund po zweryfikowaniu oczekiwanych pakietów.

### <a name="automatic-provisioning-without-using-ui"></a>Automatyczne aprowizowanie bez użycia interfejsu użytkownika
- Połączone procesy automatyczne w celu zmniejszenia interakcji z urządzeniami w celu aprowacji. 

Dzięki połączeniu automatycznego uruchamiania aprowizowania z urządzeń USB i automatycznego potwierdzenia pakietów aprowizowania użytkownik może automatycznie aprowizować urządzenia HoloLens 2 bez użycia interfejsu użytkownika urządzenia, a nawet jego nazwy. Możesz nadal używać tego samego dysku USB i pakietu aprowizowania dla wielu urządzeń. Jest to przydatne w przypadku wdrażania wielu urządzeń jednocześnie w tym samym obszarze. 

1. [Utwórz pakiet aprowizowania przy](hololens-provisioning.md) [użyciu Windows Configuration Designer.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Skopiuj pakiet na dysk pamięci MASOWEJ USB.
1. [Flashuj HoloLens od 2](hololens-insider.md#ffu-download-and-flash-directions) do [19041.1361 lub nowszej kompilacji](https://aka.ms/hololens2previewdownload). 
1. Po [zakończeniu flashowania](https://www.microsoft.com/store/productId/9P74Z35SFRS8) urządzenia przez program Advanced Recovery Companion odłącz kabel USB-C. 
1. Podłącz dysk USB do urządzenia.
1. Gdy urządzenie HoloLens 2 zostanie ponownie w trybie OOBE, automatycznie wykryje pakiet aprowizowania na dysku USB i uruchomi stronę aprowizowania.
1. Po 10 sekundach urządzenie automatycznie zastosuje pakiet aprowizowania. 

Urządzenie jest teraz skonfigurowane i będzie na ekranie Aprowowanie powiodło się.

## <a name="applyremove-a-provisioning-package-to-hololens-after-setup"></a>Stosowanie/usuwanie pakietu aprowizowania do usługi HoloLens po instalacji

> [!NOTE]
> Te kroki mają zastosowanie do wszystkich HoloLens 2 i urządzeń HoloLens (1. generacji) na Windows Holographic w wersji 1809 lub nowszej.

Na komputerze wykonaj następujące kroki:
1. Utwórz pakiet aprowizowania zgodnie z opisem w tece Create a provisioning package for HoloLens using the HoloLens wizard (Tworzenie pakietu [aprowizowania](hololens-provisioning.md)dla usługi HoloLens użyciu kreatora HoloLens administracyjnego).
2. Połączenie HoloLens podłącz urządzenie do komputera za pomocą kabla USB. HoloLens urządzenie jest Eksplorator plików na komputerze.
3. Przeciągnij i upuść pakiet aprowizowania do folderu Documents na HoloLens.

Na HoloLens wykonaj następujące kroki:
1. Przejdź kolejno do pozycji **Ustawienia** > **Konta** > **Uzyskaj dostęp do miejsca pracy lub nauki**. 
2. W **Ustawienia** wybierz pozycję **Dodaj lub usuń pakiet aprowizowania.**
3. Na następnej stronie wybierz pozycję **Dodaj pakiet,** aby uruchomić selektor plików, a następnie wybierz pakiet aprowizowania. Jeśli folder jest pusty, upewnij się, że **wybierasz pozycję To urządzenie, a** następnie pozycję **Dokumenty.**

Po zastosowaniu pakietu zostanie on wyświetlona na liście **Zainstalowane pakiety**. Aby wyświetlić szczegóły pakietu lub usunąć pakiet z urządzenia, wybierz wymieniony pakiet.

## <a name="what-you-can-configure"></a>Co można konfigurować

Pakiety aprowizowania korzystają z dostawców usług konfiguracji (CSP). Jeśli nie znasz dostawców CSP, zobacz Wprowadzenie do dostawców usług konfiguracji [(CSP) dla specjalistów IT.](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)

W programie Windows Configuration Designer podczas tworzenia pakietu aprowizowania dla systemu  Windows Holographic ustawienia dostępnego dostosowania są oparte na ustawieniach CSP obsługiwanych na platformie [Windows Holographic.](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) W poniższej tabeli opisano ustawienia, które można skonfigurować dla HoloLens.

![Typowe ustawienia środowiska uruchomieniowego dla HoloLens](images/icd-settings.png)

| Ustawienie | Opis |
| --- | --- |
| **Certyfikaty** | Wd wdrażaj certyfikat w HoloLens.  |
| **ConnectivityProfiles** | Wdrożenie profilu Wi-Fi w HoloLens.   |
| **EditionUpgrade** | [Uaktualnij do Windows Holographic for Business.](hololens1-upgrade-enterprise.md)  |
| **Zasady** | Zezwalaj na tryb dewelopera na HoloLens. [Zasady obsługiwane przez Windows Holographic for Business](/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## <a name="app-install-via-provisioning-package"></a>Instalowanie aplikacji za pośrednictwem pakietu aprowizowania

Aplikacje można instalować za pośrednictwem pakietów aprowizowania na HoloLens 2. Umożliwia to łatwe ponowne użycie pakietu, który może pomóc w dystrybucji aplikacji. Zapoznaj się z pełnymi instrukcjami [dotyczącymi wdrażania aplikacji za pośrednictwem pakietów aprowizowania.](app-deploy-provisioning-package.md)  

> [!NOTE]
> HoloLens (1. generacji) ma ograniczoną obsługę instalowania aplikacji **(UniversalAppInstall**) przy użyciu pakietu aprowizowania. HoloLens (1. generacji) obsługują instalowanie aplikacji tylko za pośrednictwem ppkg tylko podczas instalacji OOBE i tylko w kontekście użytkownika.
