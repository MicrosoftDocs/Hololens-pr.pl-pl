---
title: Konfigurowanie urządzenia HoloLens przy użyciu pakietu aprowizowania (HoloLens)
description: Aprowizowanie systemu Windows ułatwia administratorom IT konfigurowanie urządzeń użytkowników końcowych bez przetwarzania obrazów.
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
ms.openlocfilehash: cf2abe249e40e522b4d8993449b9f19033a64744
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378420"
---
# <a name="configure-hololens-by-using-a-provisioning-package"></a>Konfigurowanie urządzenia HoloLens przy użyciu pakietu aprowizowania

[Aprowizowanie](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) systemu Windows ułatwia administratorom IT konfigurowanie urządzeń użytkowników końcowych bez przetwarzania obrazów. Windows Configuration Designer to narzędzie do konfigurowania obrazów i ustawień środowiska uruchomieniowego, które są następnie wbudowane w pakiety aprowizujące.

Oto niektóre konfiguracje urządzenia HoloLens, które można zastosować w pakiecie aprowizowania:

- Uaktualnianie do [Windows Holographic for Business](hololens1-upgrade-enterprise.md)
- Konfigurowanie konta lokalnego
- Konfigurowanie połączenia Wi-Fi sieciowego
- Stosowanie certyfikatów do urządzenia
- Włączanie trybu dewelopera
- Skonfiguruj tryb kiosku, korzystając z naszych [szczegółowych instrukcji.](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

## <a name="provisioning-package-hololens-wizard"></a>Kreator aprowizowania pakietu HoloLens

Kreator urządzenia HoloLens ułatwia skonfigurowanie następujących ustawień w pakiecie aprowizowania:

- Uaktualnianie do wersji Enterprise

    > [!NOTE]
    > Ta funkcja powinna być używana tylko w przypadku urządzeń HoloLens 1. generacji. Ustawienia w pakiecie aprowizowania są stosowane tylko wtedy, gdy pakiet aprowizowania zawiera licencję uaktualnienia wersji do programu Windows Holographic for Business lub jeśli urządzenie zostało już uaktualnione do [wersji Windows Holographic for Business](hololens1-upgrade-enterprise.md).

- Konfigurowanie pierwszego doświadczenia urządzenia HoloLens (OOBE)
- Konfigurowanie sieci Wi-Fi sieci
- Zarejestruj urządzenie w Azure Active Directory lub utwórz konto lokalne
- Dodawanie certyfikatów
- Włączanie trybu dewelopera
- Skonfiguruj tryb kiosku, korzystając ze [szczegółowych instrukcji](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk).

> [!WARNING]
> Należy uruchomić projektanta konfiguracji systemu Windows na Windows 10, aby Azure Active Directory rejestracji przy użyciu dowolnego kreatora.

Pakiety aprowizowania mogą obejmować instrukcje i zasady zarządzania, niestandardowe połączenia sieciowe i zasady i nie tylko.

> [!TIP]
> Użyj kreatora pulpitu, aby utworzyć pakiet z wspólnymi ustawieniami, a następnie przejdź do edytora zaawansowanego, aby dodać inne ustawienia, aplikacje, zasady itp.

## <a name="steps-for-creating-provisioning-packages"></a>Kroki tworzenia pakietów aprowizowania

1. **Opcja 1. Z** [Microsoft Store](https://www.microsoft.com/store/apps/9nblggh4tx22). Obejmuje to możliwości urządzenia HoloLens 2.
2. **Opcja 2. Z** [zestawu Windows Assessment and Deployment Kit (ADK) dla programu Windows 10](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit). Jeśli instalujesz program Windows Configuration Designer z zestawu Windows ADK, wybierz pozycję **Projektant** konfiguracji w oknie dialogowym Wybierz funkcje, **które chcesz** zainstalować. Ta opcja nie obejmuje możliwości urządzenia HoloLens 2.

> [!NOTE]
> Jeśli wiesz, że będziesz używać komputera w trybie offline, który wymaga dostępu do programu Windows Configuration Designer, postępuj zgodnie z instrukcjami [instalowanie aplikacji w trybie offline( instrukcje dotyczące zaawansowanego https://docs.microsoft.com/hololens/hololens-recovery#downloading-arc-without-using-the-app-store) pomocnika odzyskiwania. W projektancie konfiguracji systemu Windows należy dokonać wyboru. 

### <a name="2-create-the-provisioning-package"></a>2. Tworzenie pakietu aprowizowania

Użyj narzędzia Windows Configuration Designer, aby utworzyć pakiet aprowizowania.

1. Otwórz program Windows Configuration Designer (domyślnie %windir%\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe).

2. Wybierz pozycję **Provision HoloLens devices (Aprowizuj urządzenia HoloLens).**

   ![Opcje uruchamiania ICD](images/icd-create-options-1703.png)

3. Nadaj projektowi nazwę i wybierz **pozycję Zakończ.**

4. Przeczytaj instrukcje na stronie **Wprowadzenie** i wybierz pozycję **Dalej.** Na stronach aprowowania aplikacji klasycznych przedstawiono poniższe kroki.
  
> [!IMPORTANT]
> Podczas kompilowania pakietu aprowizowania możesz uwzględnić poufne informacje w plikach projektu i w pliku pakietu aprowizowania (ppkg). Mimo że istnieje możliwość zaszyfrowania pliku ppkg, pliki projektu nie są szyfrowane. Pliki projektu należy przechowywać w bezpiecznej lokalizacji i usuwać je, gdy nie są już potrzebne.

### <a name="configure-settings"></a>Konfigurowanie ustawień

<table>
<tr><td style="width:45%" valign="top"><a id="one"></a><img src="images/one.png" alt="step one"/><img src="images/set-up-device.png" alt="set up device"/></br></br>Przejdź do pliku licencji enterprise i wybierz go, aby uaktualnić wersję urządzenia HoloLens.</br></br>Możesz również przełączyć opcję <strong>Tak</strong> lub <strong>Nie,</strong> aby ukryć części pierwszego doświadczenia.</br></br>Aby skonfigurować urządzenie bez konieczności łączenia się z siecią Wi-Fi, przełącz ustawienie Pomiń Wi-Fi <strong>na</strong> <strong>wartość Wł.</strong>.</br></br>Wybierz region i strefę czasową, w których będzie używane urządzenie. </td><td><img src="images/set-up-device-details.png" alt="Select enterprise licence file and configure OOBE"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="two"></a><img src="images/two.png" alt="step two"/>  <img src="images/set-up-network.png" alt="set up network"/></br></br>W tej sekcji można wprowadzić szczegółowe informacje o sieci Wi-Fi sieci bezprzewodowej, z które urządzenie powinno automatycznie nawiązać połączenie. W tym celu <strong></strong>wybierz pozycję Wł., wprowadź wartość SSID, typ sieci (<strong>Otwórz</strong> lub <strong>WPA2-Personal</strong>) i (jeśli <strong>WPA2-Personal</strong>) hasło sieci bezprzewodowej.</td><td><img src="images/set-up-network-details-desktop.png" alt="Enter network SSID and type"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="three"></a><img src="images/three.png" alt="step three"/>  <img src="images/account-management.png" alt="account management"/></br></br>Możesz zarejestrować urządzenie w Azure Active Directory lub utworzyć konto lokalne na urządzeniu</br></br>Przed skonfigurowaniem zbiorczej rejestracji w usłudze Azure AD za pomocą kreatora projektanta konfiguracji systemu Windows skonfiguruj dołączanie do usługi <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">Azure AD w organizacji.</a> Ustawienie <strong>maksymalnej liczby urządzeń na</strong> użytkownika w dzierżawie usługi Azure AD określa, ile razy można użyć tokenu zbiorczego, który można uzyskać w kreatorze. Aby zarejestrować urządzenie w usłudze Azure AD, wybierz tę opcję i wprowadź przyjazną nazwę tokenu zbiorczego, który otrzymasz za pomocą kreatora. Ustaw datę wygaśnięcia tokenu (maksymalnie 30 dni od daty uzyskania tokenu). Wybierz <strong>pozycję Pobierz token zbiorczy.</strong> W <strong>oknie&#39;możesz</strong> się zalogować wprowadź konto z uprawnieniami do dołączania urządzenia do usługi Azure AD, a następnie hasło. Wybierz <strong>pozycję Zaakceptuj,</strong> aby nadać programowi Windows Configuration Designer niezbędne uprawnienia. </br></br>Aby utworzyć konto lokalne, wybierz tę opcję i wprowadź nazwę użytkownika i hasło. </br></br><strong>Ważne:</strong> <br />(Tylko Windows 10 w wersji 1607) Jeśli tworzysz konto lokalne w pakiecie aprowizowania, musisz zmienić hasło za pomocą aplikacji <strong>Ustawienia</strong> co 42 dni. Jeśli hasło nie zostanie zmienione w tym okresie, konto może zostać zablokowane i nie będzie można się zalogować.  </td><td><img src="images/account-management-details.png" alt="join  Azure AD or create a local  account"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="four"></a><img src="images/four.png" alt="step four"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>Aby aprowizować urządzenie przy użyciu certyfikatu, kliknij <strong>pozycję Dodaj certyfikat.</strong> Wprowadź nazwę certyfikatu, a następnie przejdź do i wybierz certyfikat, który ma być używany.</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><a id="five"></a><img src="images/five.png" alt="step five"/> <img src="images/developer-setup.png" alt="Developer Setup"/></br></br>Przełącz opcję <strong>Tak</strong> lub <strong>Nie,</strong> aby włączyć tryb dewelopera na urządzeniach HoloLens. <a href="https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode" data-raw-source="[Learn more about Developer Mode.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)">Dowiedz się więcej o trybie dewelopera.</a></td><td><img src="images/developer-setup-details.png" alt="Enable Developer Mode"/></td></tr>
<tr><td style="width:45%" valign="top"><a id="six"></a><img src="images/six.png" alt="step six"/> <img src="images/finish.png" alt="finished"/></br></br>Nie należy ustawiać hasła w celu ochrony pakietu aprowizowania. Jeśli pakiet aprowizowania jest chroniony hasłem, aprowizowanie urządzenia HoloLens nie powiedzie się.</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

Gdy wszystko będzie gotowe, wybierz pozycję **Utwórz.** Trwa to tylko kilka sekund. Podczas budowanych pakietów lokalizacja, w której jest przechowywany pakiet, jest wyświetlana jako hiperlink w dolnej części strony.

### <a name="3-create-a-provisioning-package-for-hololens-by-using-advanced-provisioning"></a>3. Tworzenie pakietu aprowizowania dla urządzenia HoloLens przy użyciu aprowizowania zaawansowanego

> [!NOTE]
> Pakiet aprowizowania,  który tworzysz w zaawansowanej aproweniu, nie musi zawierać licencji uaktualnienia wersji, aby Windows Holographic for Business pomyślnie zastosować do urządzenia HoloLens (1. generacja). [Zobacz więcej informacji na Windows Holographic for Business dla urządzenia HoloLens (1. generacja).](hololens1-upgrade-enterprise.md)

1. Na stronie startowej Projektant konfiguracji systemu Windows wybierz pozycję **Aprowizowanie zaawansowane.**
2. W **oknie Enter project details** (Wprowadź szczegóły projektu) określ nazwę projektu i lokalizację projektu. Opcjonalnie wprowadź krótki opis, aby opisać projekt.

3. Wybierz opcję **Dalej**.

4. W **oknie Wybierz ustawienia do wyświetlenia i** skonfigurowania wybierz pozycję Windows 10 Holographic , a następnie wybierz pozycję  **Dalej.**

5. Wybierz pozycję **Zakończ**.

6. Rozwiń **pozycję Ustawienia** środowiska uruchomieniowego i dostosuj pakiet przy użyciu dowolnego z ustawień opisanych [w dalszej części tego artykułu.](#what-you-can-configure)

    > [!IMPORTANT]
    > (Tylko Windows 10 w wersji 1607) Jeśli tworzysz konto lokalne w pakiecie aprowizowania, musisz zmienić hasło za pomocą aplikacji **Ustawienia** co 42 dni. Jeśli hasło nie zostanie zmienione w tym okresie, konto może zostać zablokowane i nie będzie można się zalogować. Jeśli konto użytkownika jest zablokowane, należy wykonać [pełne odzyskiwanie urządzenia.](https://developer.microsoft.com/windows/mixed-reality/reset_or_recover_your_hololens#perform_a_full_device_recovery)

7. Wybierz **pozycję Plik**  >  **Zapisz.**

8. Przeczytaj ostrzeżenie, że pliki projektu mogą zawierać poufne informacje, a następnie wybierz przycisk **OK.**

    > [!IMPORTANT]
    > Podczas kompilowania pakietu aprowizowania możesz uwzględnić poufne informacje w plikach projektu i w pliku pakietu aprowizowania (ppkg). Mimo że istnieje możliwość zaszyfrowania pliku ppkg, pliki projektu nie są szyfrowane. Pliki projektu należy przechowywać w bezpiecznej lokalizacji i usuwać je, gdy nie są już potrzebne.
    
9. Wybierz **pozycję**  >  **Eksportuj pakiet aprowizowania.**

10. Zmień **właściciela na** administratora **IT.** W ten sposób ustawiany jest wyższy priorytet tego pakietu aprowizowania niż pakiety aprowizacyjne stosowane do tego urządzenia z innych źródeł. Wybierz opcję **Dalej**.

11. Ustaw wartość dla wersji **pakietu**.

    > [!TIP]
    > Możesz wprowadzić zmiany w istniejących pakietach i zmienić numer wersji, aby zaktualizować wcześniej zastosowane pakiety.

12. Na stronie Select security details for the provisioning package (Wybierz szczegóły zabezpieczeń **dla pakietu aprowizowania)** wybierz pozycję **Next (Dalej).**

    > [!WARNING]
    > Jeśli zaszyfrujemy pakiet aprowizowania, aprowizowanie urządzenia HoloLens nie powiedzie się.  

13. Wybierz **przycisk** Dalej, aby określić lokalizację wyjściową, do której ma przejść pakiet aprowizowania po jego sbudowaną zawartość. Domyślnie projektant konfiguracji systemu Windows używa folderu projektu jako lokalizacji wyjściowej.

    Opcjonalnie możesz wybrać pozycję **Przeglądaj,** aby zmienić domyślną lokalizację wyjściową.

14. Wybierz opcję **Dalej**.

15. Wybierz **pozycję Kompilacja,** aby rozpocząć kompilowanie pakietu. Informacje o projekcie są wyświetlane na stronie kompilacji, a pasek postępu wskazuje stan kompilacji.

16. Po zakończeniu kompilacji wybierz pozycję **Zakończ.**

<span id="apply" />

## <a name="apply-a-provisioning-package-to-hololens-during-setup"></a>Stosowanie pakietu aprowizowania na urządzeniach HoloLens podczas instalacji

Urządzenia HoloLens 2 w systemie Windows Holographic w wersji 2004 lub kompilacji [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) lub nowszej mogą używać dysku USB w celu zastosowania pakietu aprowizowania. Po prostu skopiuj plik ppkg do katalogu głównego dysku USB. Pakiety aprowizowania będą stosowane tylko wtedy, gdy są w katalogu głównym dysku USB. Wiele pakietów aprowizowania będzie stosowanych sekwencyjnie.

Urządzenia HoloLens 2 w systemie Windows Holographic w wersji [20H2](hololens-release-notes.md#windows-holographic-version-20h2) lub nowszej mają nowsze funkcje ułatwiające usprawnienie i uproszczenie tego procesu, dzięki czemu jest on automatyczny. Zapoznaj się z następującymi sekcjami:

- [Automatyczne uruchamianie aprowizowania z dysku USB](hololens-provisioning.md#auto-launch-provisioning-from-usb)
- [Automatyczne potwierdzanie pakietów aprowizowania w OOBE](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe)
- [Automatyczne aprowizowanie bez użycia interfejsu użytkownika](hololens-provisioning.md#automatic-provisioning-without-using-ui)

1. Użyj kabla USB, aby podłączyć urządzenie do komputera (lub dysku USB dla urządzenia HoloLens 2, jak wspomniano powyżej), a następnie uruchom urządzenie. Nie przechodz po **stronie pierwszego wejdą w interakcję momentu** OOBE.   
    - Na urządzeniach HoloLens (1. generacja) ta strona zawiera niebieskie pole. 
    - Na urządzeniach HoloLens 2 ta strona zawiera łańcingbird.

2. Naciśnij krótko i zwolnij przyciski **Volume Down** i **Power** jednocześnie. 

3. Urządzenie HoloLens jest Eksplorator plików na komputerze.

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
- Zautomatyzowany proces umożliwiający mniejszą interakcję z użytkownikiem, gdy zostanie wyświetlona strona Pakiet aprowizowania, automatycznie zastosuje wszystkie wymienione pakiety.

Gdy pojawi się ekran główny inicjowania obsługi administracyjnej, program OOBE odliczy 10 sekund, zanim automatycznie rozpocznie stosowanie wszystkich pakietów aprowizowania. Użytkownicy mogą nadal potwierdzić lub anulować w ciągu tych 10 sekund po zweryfikowaniu oczekiwanych pakietów.

### <a name="automatic-provisioning-without-using-ui"></a>Automatyczne aprowizowanie bez użycia interfejsu użytkownika
- Połączone procesy automatyczne w celu zmniejszenia interakcji z urządzeniami w celu aprowacji. 

Dzięki połączeniu automatycznego uruchamiania aprowizowania z urządzeń USB i automatycznego potwierdzenia pakietów aprowizowania użytkownik może automatycznie aprowizować urządzenia HoloLens 2 bez korzystania z interfejsu użytkownika urządzenia, a nawet jego nazwy. Możesz nadal używać tego samego dysku USB i pakietu aprowizowania dla wielu urządzeń. Jest to przydatne w przypadku wdrażania wielu urządzeń jednocześnie w tym samym obszarze. 

1. [Utwórz pakiet aprowizowania przy](hololens-provisioning.md) użyciu [programu Windows Configuration Designer.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Skopiuj pakiet na dysk pamięci MASOWEJ USB.
1. [Flashuj urządzenie HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) do [kompilacji 19041.1361 lub nowszej.](https://aka.ms/hololens2previewdownload) 
1. Po [zakończeniu flashowania](https://www.microsoft.com/store/productId/9P74Z35SFRS8) urządzenia przez program Advanced Recovery Companion odłącz kabel USB-C. 
1. Podłącz dysk USB do urządzenia.
1. Po uruchomieniu urządzenia HoloLens 2 w trybie OOBE automatycznie wykryje pakiet aprowizowania na dysku USB i uruchomi stronę aprowizowania.
1. Po 10 sekundach urządzenie automatycznie zastosuje pakiet aprowizowania. 

Urządzenie jest teraz skonfigurowane i będzie na ekranie Aprowowanie powiodło się.

## <a name="applyremove-a-provisioning-package-to-hololens-after-setup"></a>Stosowanie/usuwanie pakietu aprowizowania na urządzeniach HoloLens po zakończeniu konfiguracji

> [!NOTE]
> Te kroki mają zastosowanie do wszystkich urządzeń HoloLens 2 i urządzeń HoloLens (1. generacji) na urządzeniach z systemem Windows Holographic w wersji 1809 lub nowszej.

Na komputerze wykonaj następujące kroki:
1. Utwórz pakiet aprowizowania zgodnie z opisem w [teksie Create a provisioning package for HoloLens using the HoloLens wizard](hololens-provisioning.md)(Tworzenie pakietu aprowizowania dla urządzenia HoloLens przy użyciu kreatora urządzenia HoloLens).
2. Podłącz urządzenie HoloLens do komputera za pomocą kabla USB. Urządzenie HoloLens jest Eksplorator plików na komputerze.
3. Przeciągnij i upuść pakiet aprowizowania do folderu Documents na urządzeniach HoloLens.

Na urządzeniach HoloLens wykonaj następujące kroki:
1. Przejdź kolejno do pozycji **Ustawienia** > **Konta** > **Uzyskaj dostęp do miejsca pracy lub nauki**. 
2. W **ustawieniach pokrewnych** wybierz **pozycję Dodaj lub usuń pakiet aprowizowania.**
3. Na następnej stronie wybierz pozycję **Dodaj pakiet,** aby uruchomić selektor plików, a następnie wybierz pakiet aprowizowania. Jeśli folder jest pusty, upewnij się, że **wybierasz pozycję To urządzenie, a** następnie pozycję **Dokumenty.**

Po zastosowaniu pakietu zostanie on wyświetlona na liście **Zainstalowane pakiety**. Aby wyświetlić szczegóły pakietu lub usunąć pakiet z urządzenia, wybierz wymieniony pakiet.

## <a name="what-you-can-configure"></a>Co można konfigurować

Pakiety aprowizowania korzystają z dostawców usług konfiguracji (CSP). Jeśli nie znasz dostawców CSP, zobacz Wprowadzenie do dostawców usług konfiguracji [(CSP) dla specjalistów IT.](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers)

W projektancie konfiguracji systemu Windows podczas tworzenia pakietu aprowizowania dla systemu Windows Holographic ustawienia w grafie Dostępne dostosowania są oparte na ustawieniach CSP obsługiwanych w systemie [Windows Holographic.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)  W poniższej tabeli opisano ustawienia, które można skonfigurować dla urządzenia HoloLens.

![Typowe ustawienia środowiska uruchomieniowego dla urządzenia HoloLens](images/icd-settings.png)

| Ustawienie | Opis |
| --- | --- |
| **Certyfikaty** | Wdrażanie certyfikatu na urządzeniach HoloLens.  |
| **ConnectivityProfiles** | Wdrażanie profilu Wi-Fi na urządzeniach HoloLens.   |
| **EditionUpgrade** | [Uaktualnij do Windows Holographic for Business.](hololens1-upgrade-enterprise.md)  |
| **Zasady** | Zezwalanie na tryb dewelopera lub uniemożliwianie go na urządzeniach HoloLens. [Zasady obsługiwane przez Windows Holographic for Business](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#hololenspolicies) |

## <a name="app-install-via-provisioning-package"></a>Instalowanie aplikacji za pośrednictwem pakietu aprowizowania

Aplikacje można instalować za pośrednictwem pakietów aprowizowania na urządzeniach HoloLens 2. Umożliwia to łatwe do ponownego użycia pakiet, który może pomóc w dystrybucji aplikacji. Zapoznaj się z pełnymi instrukcjami [dotyczącymi wdrażania aplikacji za pośrednictwem pakietów aprowizowania.](app-deploy-provisioning-package.md)  

> [!NOTE]
> Urządzenie HoloLens (1. generacja) ma ograniczoną obsługę instalowania aplikacji **(UniversalAppInstall**) przy użyciu pakietu aprowizowania. Urządzenia HoloLens (1. generacji) obsługują instalowanie aplikacji za pośrednictwem ppkg tylko podczas instalacji OOBE i tylko w przypadku instalacji w kontekście użytkownika.
