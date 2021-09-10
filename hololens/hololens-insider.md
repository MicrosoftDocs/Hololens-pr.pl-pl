---
title: Insider Preview for Microsoft HoloLens
description: Dowiedz się, jak rozpocząć pracę z kompilacjami niejawnych testerów i przekazać cenną opinię na temat naszej następnej ważnej aktualizacji systemu operacyjnego na HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 08/16/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: cabf35d44cdd144151e048d7a6e14e391629d00a
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428781"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview for Microsoft HoloLens

Witamy w najnowszych kompilacjach insider preview dla HoloLens! Łatwo jest rozpocząć pracę [i przekazać](hololens-insider.md#start-receiving-insider-builds) cenną opinię na temat naszej następnej ważnej aktualizacji systemu operacyjnego na HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Informacje o wersji dla niejawnych testerów

Z przyjemnością rozpoczynamy lotami po nowych funkcjach, aby Windows niejawni testerzy. Nowe kompilacje będą dostępne w kanałach Dev i Beta, aby uzyskać najnowsze aktualizacje. Będziemy nadal aktualizować tę stronę w przypadku dodawania kolejnych funkcji i aktualizacji do naszych Windows niejawnych testerów. Przygotuj się do pomieszania tych aktualizacji ze swoją rzeczywistością.

Dotyczy to ulepszonych raportów dotyczących rozwiązywania problemów i urządzeń, niektórych naprawień usterek w trybie kiosku i przeglądarki certyfikatów, rozszerzonej powierzchni możliwości zarządzania oraz zwiększonej niezawodności aktualizacji. Nową, nową funkcją tej aktualizacji funkcji, która zostanie HoloLens jest tryb przenoszenia platformy. Zapoznaj się ze wszystkimi nowymi doskonałymi funkcjami dla HoloLens 2!

| Cecha                 | Opis                | Użytkownik lub scenariusz | Wprowadzono kompilację |
|-------------------------|----------------------------|--------------|------------------|
| [Przenoszenie trybu platformy](#moving-platform-mode) | Wprowadzono tryb przenoszenia platformy w wersji beta, który po skonfigurowaniu umożliwia korzystanie z wersji HoloLens 2 w dużych dyskach z ruchami o niskiej dynamice. | Wszystko | 20348.1411 |
| [Obsługa plików PFX dla Menedżera certyfikatów](#pfx-file-support-for-certificate-manager) | Dodawanie certyfikatów PFX za pomocą interfejsu Ustawienia użytkownika | Użytkownik końcowy | 20348.1405 |
| [Wyświetlanie zaawansowanego raportu diagnostycznego w Ustawienia na HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Wyświetlanie dzienników diagnostycznych mdm na urządzeniu | Rozwiązywanie problemów | 20348.1405 |
| [Powiadomienia diagnostyki w trybie offline](#offline-diagnostics-notifications) | Opinie dotyczące zbierania dzienników | Rozwiązywanie problemów | 20348.1405 |
| [Ulepszenia zbierania dzienników magazynu o niskiej wydajności](#low-storage-log-collection-improvements) | Ulepszenia scenariuszy zbierania dzienników w sytuacjach niskiego poziomu magazynowania. | Rozwiązywanie problemów | 20348.1412 |
| [Zmiany WSP dotyczące raportowania HoloLens szczegóły](#csp-changes-for-reporting-hololens-details) | Nowi CSP dla programu do wykonywania zapytań o dane | Administratorzy IT    | 20348.1403                 |
| [Zasady automatycznego logowania kontrolowane przez CSP](#auto-login-policy-controlled-by-csp) | Służy do automatycznego logowania się do konta | Administratorzy IT | 20348.1405 |
| [Ulepszone wykrywanie ponownego uruchamiania aktualizacji i powiadomienia](#improved-update-restart-detection-and-notifications) | Nowe włączone zasady i interfejs użytkownika dla aktualizacji. | Administratorzy IT | 20348.1405 |
| [Inteligentne ponawianie próby aktualizacji aplikacji](#smart-retry-for-app-updates) | Umożliwia administratorom IT zaplanowanie ponownych prób aktualizacji aplikacji. | Administratorzy IT | 20348.1405 |
| [Używaj tylko aplikacji ze sklepu prywatnego tylko dla Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Konfigurowanie aplikacji ze sklepu w celu pokazywania tylko aplikacji z organizacji | Administrator IT | 20348.1408 |
| [Korzystanie z aplikacji WDAC i LOB](#use-wdac-and-lob-apps) | Umożliwia administratorom IT korzystanie z własnych aplikacji i blokowanie innych aplikacji za pomocą funkcji WDAC. | Administratorzy IT | 20348.1405 |
| [Poprawki i ulepszenia](#fixes-and-improvements) | Poprawki i ulepszenia dotyczące HoloLens. | Wszystko | 20348.1411 |

### <a name="it-admin-insider-feature-checklist"></a>Lista kontrolna funkcji dla niejawnych testerów IT

✔️ Jeśli chcesz ustawić pojedyncze konto usługi Azure AD do automatycznego logowania, skonfiguruj [tego nowego programu CSP.](#auto-login-policy-controlled-by-csp) <br>
✔️ Jeśli chcesz skonfigurować aplikacje tak, aby automatycznie podejmiły próbę aktualizacji po nieudanych aktualizacjach, ustaw tego nowego programu CSP na inteligentne [ponawianie próby.](#smart-retry-for-app-updates) <br>
✔️ Jeśli chcesz mieć większą kontrolę nad aktualizacjami systemu operacyjnego, zapoznaj się z tymi nowo włączonymi [zasadami aktualizacji.](#improved-update-restart-detection-and-notifications) <br>
✔️ Jeśli musisz udostępnić aplikacje organizacji w sklepie firmowym za pośrednictwem usługi Microsoft Store, ale chcesz zezwolić na dostęp tylko do aplikacji organizacji, a nie do pełnego sklepu, ustaw te [zasady.](#use-only-private-store-apps-for-microsoft-store) <br>
✔️ Jeśli chcesz poznać wolne miejsce do magazynowania, SSID lub BSSID urządzeń z systemem HoloLens, zapoznaj się z tymi raportami dla [CSP.](#csp-changes-for-reporting-hololens-details) <br>
✔️ Jeśli chcesz użyć funkcji WDAC do blokowania uruchamiania aplikacji lub procesów, ale musisz również użyć własnej linii aplikacji do pracy, możesz teraz zezwolić na uruchamianie aplikacji biznesowych w zasadach [funkcji WDAC.](#use-wdac-and-lob-apps)

### <a name="moving-platform-mode"></a>Przenoszenie trybu platformy

W wersji **Insider Build 20348.1411** dodaliśmy obsługę wersji beta śledzenia na platformach ruchu o niskiej dynamice na platformach w wersji HoloLens 2. Po zainstalowaniu kompilacji i włączeniu trybu przenoszenia platformy będzie można używać urządzenia HoloLens 2 w wcześniej niedostępnych środowiskach, takich jak duże statku i duże statku. Obecnie funkcja jest ukierunkowana na włączanie tylko tych konkretnych ruchomych platform. Chociaż nic nie uniemożliwia próby użycia tej funkcji w innych środowiskach, ta funkcja koncentruje się najpierw na dodawaniu obsługi tych środowisk.

Aby dowiedzieć się więcej o tym, co jest obsługiwane i jak włączyć tę nową funkcję, [odwiedź stronę przenoszenia platformy.](hololens2-moving-platform.md)

### <a name="pfx-file-support-for-certificate-manager"></a>Obsługa plików PFX dla Menedżera certyfikatów

Wprowadzono w kompilacji Windows Insider 20348.1405. Dodaliśmy obsługę Menedżera [](certificate-manager.md) certyfikatów, aby teraz używać certyfikatów pfx. Gdy użytkownicy **przejdą** do Ustawienia  >  **zaktualizują &,** a następnie wybierzą pozycję Zainstaluj certyfikat, interfejs użytkownika obsługuje teraz  >  plik certyfikatu pfx. 
Użytkownicy mogą importować certyfikat PFX z kluczem prywatnym do magazynu użytkowników lub magazynu maszynowego.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Wyświetlanie zaawansowanego raportu diagnostycznego w Ustawienia na HoloLens

W przypadku urządzeń zarządzanych podczas rozwiązywania problemów z zachowaniem ważnym krokiem jest potwierdzenie zastosowania oczekiwanej konfiguracji zasad. Wcześniej w przypadku tej nowej funkcji wyświetlanie tych informacji musiało odbywać się za pośrednictwem rozwiązania MDM lub w pobliżu urządzenia po wyeksportowaniu dzienników diagnostycznych MDM zebranych za pośrednictwem konta usługi Ustawienia Dostęp do miejsca pracy lub nauki, **a** następnie wybranie opcji Eksportuj dzienniki zarządzania i wyświetlane na pobliskim  ->    >  komputerze. 

Teraz diagnostykę MDM można wyświetlić na urządzeniu przy użyciu przeglądarki Edge. Aby łatwiej wyświetlić raport diagnostyczny MDM, przejdź do strony Dostęp do konta służbowego i wybierz pozycję **Wyświetl zaawansowany raport diagnostyczny.** Spowoduje to wygenerowanie i otwarcie raportu w nowym oknie przeglądarki Edge.

![Wyświetlanie zaawansowanego raportu diagnostycznego w Ustawienia aplikacji.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Powiadomienia diagnostyki w trybie offline

Jest to aktualizacja istniejącej funkcji o nazwie [Diagnostyka w trybie offline.](hololens-diagnostic-logs.md#offline-diagnostics) Wcześniej nie było wyraźnego wskaźnika dla użytkowników, że wyzwolono kolekcję diagnostyczną lub została ona zakończona.
Teraz dodane w kompilacjach Windows Insider istnieją dwie formy wymiany opinii na temat diagnostyki w trybie offline. Pierwsze z nich to wyskakujące powiadomienia wyświetlane zarówno podczas uruchamiania, jak i zakończenia zbierania. Będą one wyświetlane, gdy użytkownik jest zalogowany i ma wizualizacje.

![Wyskakujące powiadomienia dotyczące zbierania dzienników.](./images/logcollection1.jpg)

![Wyskakujące wyskakujące powiadomienia po zakończeniu zbierania dzienników.](./images/logcollection2.jpg)

Ponieważ użytkownicy często używają diagnostyki offline jako mechanizmu rezerwowego zbierania dzienników, gdy nie mają dostępu do ekranu, nie mogą się zalogować lub nadal znajdują się w trybie OOBE, podczas zbierania dzienników będzie również odtwarzany sygnał dźwiękowy. Ten dźwięk będzie odtwarzany oprócz powiadomienia wyskakującego.

Ta nowa funkcja zostanie włączona podczas aktualizacji urządzenia i nie trzeba jej włączać ani zarządzać. W przypadku, gdy nie będzie można wyświetlić ani wysłuchać nowej opinii, diagnostyka w trybie offline będzie nadal generowana.

Mamy nadzieję, że dzięki temu nowszej dodatku opinii będzie łatwiej zbierać dane diagnostyczne i szybciej rozwiązywać problemy.

### <a name="low-storage-log-collection-improvements"></a>Ulepszenia zbierania dzienników magazynu o niskiej wydajności

W scenariuszach, w których ilość miejsca na dysku urządzenia wydaje się mała podczas zbierania dzienników diagnostycznych, zostanie utworzony dodatkowy raportStorageDiagnostics.zip **o** nazwie . Próg małej pojemności magazynu jest określany automatycznie przez Windows [magazynu.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

### <a name="csp-changes-for-reporting-hololens-details"></a>Zmiany WSP dotyczące raportowania HoloLens szczegóły

- Wprowadzono w kompilacji Windows Insider, 20348.1403

Następujący CSP zostały zaktualizowane o nowe sposoby zgłaszania informacji z HoloLens urządzeń.

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP — bezpłatne Storage

DevDetail CSP now now also reports free storage space on HoloLens device. Powinno to być w przybliżeniu zgodne z wartością wyświetlaną na Ustawienia aplikacji Storage aplikacji. Poniżej znajduje się konkretny węzeł zawierający te informacje.

- ./DevDetail/Ext/Microsoft/FreeStorage (tylko operacja GET)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP — SSID i BSSID

DeviceStatus CSP now also reports SSID and BSSID of Wi-Fi network which HoloLens is actively connected. Poniżej przedstawiono konkretne węzły zawierające te informacje.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*adres mac* karty Wi-Fi /SSID
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*adres mac* karty Wi-Fi /BSSID

Przykład obiektu blob syncml (dla dostawców mdm) do wykonywania zapytań o identyfikatory sieci

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a>Zasady automatycznego logowania kontrolowane przez CSP

Te nowe zasady AutoLogonUser kontroluje, czy użytkownik będzie automatycznie zalogowany. Niektórzy klienci chcą skonfigurować urządzenia, które są powiązane z tożsamością, ale nie chcą mieć żadnego logowania. Imagine urządzenie i natychmiast korzystać z pomocy zdalnej. Możesz też skorzystać z możliwości szybkiej dystrybucji urządzeń HoloLens i umożliwienia użytkownikom końcowych przyspieszenia logowania.

Jeśli zasady są ustawione na niepustą wartość, określają adres e-mail użytkownika logowania automatycznego. Określony użytkownik musi logować się na urządzeniu co najmniej raz, aby włączyć automatyczne logowanie.

OMA-URI nowej wartości `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` ciągu zasad

- Użytkownik z tym samym adresem e-mail będzie miał włączone automatyczne logowanie.

Na urządzeniu, na którym te zasady są skonfigurowane, użytkownik określony w zasadach musi się logować co najmniej raz. Podczas kolejnych ponownych uruchomień urządzenia po pierwszym zalogowaniu określony użytkownik będzie automatycznie zalogowany. Obsługiwany jest tylko jeden użytkownik z automatycznym logowaniem. Po włączeniu automatycznie zalogowanego użytkownika nie będzie można wylogować się ręcznie. Aby logować się jako inny użytkownik, należy najpierw wyłączyć zasady.

> [!NOTE]
>
> - Niektóre zdarzenia, takie jak główne aktualizacje systemu operacyjnego, mogą wymagać od określonego użytkownika ponownego zalogowania się na urządzeniu w celu wznowienia działania automatycznego logowania.
> - Logowanie automatyczne jest obsługiwane tylko w przypadku użytkowników msa i usługi AAD.

### <a name="improved-update-restart-detection-and-notifications"></a>Ulepszone wykrywanie ponownego uruchamiania aktualizacji i powiadomienia

Między godzinami aktywnego użytkowania a zasadami czasu instalacji można uniknąć ponownego uruchamiania HoloLens, gdy są one w użyciu. Jednak takie rozwiązanie opóźniłoby również wdrożenie aktualizacji, jeśli ponowne uruchomienie nie zostanie ukończone w celu ukończenia instalacji wymaganej aktualizacji. Dodaliśmy zasady, które umożliwiają itom wymuszanie terminów ostatecznych i wymaganych ponownych uruchomień oraz zapewniają terminowe ukończenie instalacji aktualizacji. Użytkownicy mogą zostać powiadomieni przed zainicjowaniem ponownego rozruchu i mogą opóźnić ponowne uruchomienie zgodnie z zasadami IT.

Dodano następujące zasady aktualizacji:

- [Update/AutoRestartNotificationSchedule](/windows/client-management/mdm/policy-csp-update#update-autorestartnotificationschedule)
- [Update/AutoRestartRequiredNotificationDismissal](/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
- [Update/ConfigureDeadlineForFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)
- [Update/ConfigureDeadlineForQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)
- [Update/ConfigureDeadlineGracePeriod](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)
- [Update/ConfigureDeadlineNoAutoReboot](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)
- [Update/ScheduleImminentRestartWarning](/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)
- [Update/ScheduleRestartWarning](/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)
- [Update/UpdateNotificationLevel](/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

### <a name="smart-retry-for-app-updates"></a>Inteligentne ponawianie próby aktualizacji aplikacji

Teraz włączone dla usługi HoloLens to nowe zasady, które umożliwiają administratorom IT ustawianie cyklicznych lub jednorazowych dat w celu ponownego uruchomienia aplikacji, których aktualizacja nie powiodła się z powodu używania aplikacji, co umożliwia zastosowanie aktualizacji. Można je ustawić na podstawie kilku różnych wyzwalaczy, takich jak zaplanowany czas lub logowanie. Aby dowiedzieć się więcej na temat sposobu używania tego widoku zasad [ApplicationManagement/ScheduleForceRestartForUpdateFailures.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Używaj tylko aplikacji ze sklepu prywatnego dla Microsoft Store

Zasady RequirePrivateStoreOnly zostały włączone dla HoloLens. Te zasady umożliwiają skonfigurowanie Microsoft Store tak, aby wyświetlała tylko magazyn prywatny skonfigurowany dla twojej organizacji. Ograniczenie dostępu tylko do aplikacji, które zostały udostępnione.

Dowiedz się więcej o [applicationmanagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="use-wdac-and-lob-apps"></a>Korzystanie z aplikacji WDAC i LOB

Teraz możesz używać funkcji WDAC, aby blokować uruchamianie aplikacji lub procesów i nadal korzystać z własnej linii aplikacji do pracy. Można teraz zezwolić na nie w zasadach WDAC. Użycie tych zasad obejmuje uruchomienie dodatkowego wiersza kodu w programie PowerShell podczas tworzenia zasad funkcji WDAC. [Zapoznaj się z krokami tutaj.](/mem/intune/configuration/custom-profile-hololens)

### <a name="fixes-and-improvements"></a>Poprawki i ulepszenia

- Rozwiązano znany problem z Portal urządzeń w którym nie było [monitu o pobranie zablokowanych plików.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Rozwiązano [znany problem z Portal urządzeń podczas przekazywania i pobierania plików.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- Rozwiązuje problemy związane z raportowaniem właściwości zgodności z HoloLens urządzeń; Do wyzwolenia poprawnego raportowania w kompilacjach niejawnych testerów może być wymagany ponowny rozruch.  
- Włączono [interfejs API przypisanego dostępu,](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348&preserve-view=true) aby aplikacje mogą teraz określić, HoloLens działa w trybie kiosku dla użytkownika zalogowanego do HoloLens.
- Zaktualizowano wersję w polu usługi Remote Assist, która jest instalowana na nowych urządzeniach flash.
- Przetwarzanie gier dla aplikacji 2D zostało wyłączone w kompilacjach niejawnych testerów. Po jego usunięciu aplikacje mogą teraz bezpośrednio korzystać z interfejsów API gamepad i mieć dostęp do całego zestawu kontrolek oraz robić to, co chcą. Deweloperzy powinni używać interfejsów API gamepad do korzystania z danych wejściowych gamepad. Oto przykład dla klasy [Gamepad (Windows. Gaming.Input) — Windows aplikacji platformy UWP](/uwp/api/windows.gaming.input.gamepad?view=winrt-20348&preserve-view=true)

## <a name="start-receiving-insider-builds"></a>Rozpoczynanie odbierania kompilacji niejawnych testerów

> [!NOTE]
> Jeśli ostatnio nie była aktualizowana, uruchom ponownie urządzenie, aby zaktualizować stan i pobrać najnowszą kompilację.
>
> - Polecenie głosowe "Reboot device" (Uruchom ponownie urządzenie) działa dobrze.
> - Możesz również wybrać przycisk ponownego uruchamiania w Ustawienia/Windows niejawny program testów.
>
> Wystąpiła usterka w załocie, która może cię napotkać, co pozwoli ci wrócić do śledzenia.

Na urządzeniu HoloLens 2 przejdź do usługi **Ustawienia**  >  **Update & Security**  >  **Windows niejawny program testów** wybierz pozycję **Wprowadzenie.** Połącz konto, które było używane do zarejestrowania się jako Windows Insider.

Windows niejawny program testów jest teraz przenoszący się do kanałów. Szybki **pierścień** stanie się kanałem **dewelopera,** pierścień Wolny stanie  się **kanał beta,** a pierścień wersji zapoznawczej zostanie  **kanałem wersji zapoznawczej.** Oto jak wygląda to mapowanie:

![Windows Wyjaśnienie kanałów niejawnych testerów.](images/WindowsInsiderChannels.png)

Aby uzyskać więcej informacji, zobacz Introducing Windows Insider Channels (Wprowadzenie do [kanałów niejawnych testerów)](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) Windows Blogi.
Następnie wybierz pozycję Active **development of Windows**, wybierz, czy chcesz otrzymywać kanał **dewelopera,** czy kanał beta **kompilacje,** i przejrzyj warunki programu.
Wybierz **pozycję > uruchom ponownie teraz,** aby zakończyć. Po ponownym uruchomieniu urządzenia przejdź do usługi **Ustawienia > Update & Security > Sprawdź** aktualizacje, aby pobrać najnowszą kompilację.

### <a name="update-error-0x80070490-work-around"></a>Aktualizowanie błędu 0x80070490 pracy

Jeśli wystąpi błąd aktualizacji 0x80070490 podczas aktualizowania w kanale dewelopera lub wersji beta, spróbuj wykonać poniższe krótkoterminowe czynności. Obejmuje to przeniesienie kanału niejawnego testera, pobranie aktualizacji, a następnie przeniesienie kanału niejawnego testera z powrotem.

#### <a name="stage-one---release-preview"></a>Etap pierwszy — wersja zapoznawcza

1. Ustawienia, Zaktualizuj zabezpieczenia &, Windows niejawny program testów wybierz pozycję **Kanał wersji zapoznawczej.**

2. Ustawienia, Update & Security, Windows Update, **Check for updates**. Po aktualizacji przejdź do etapu 2.

#### <a name="stage-two---dev-channel"></a>Etap drugi — kanał dewelopera

1. Ustawienia, Zaktualizuj zabezpieczenia &, Windows niejawny program testów wybierz pozycję **Kanał deweloperów.**

2. Ustawienia, Update & Security, Windows Update, **Check for updates**.

## <a name="ffu-download-and-flash-directions"></a>Wskazówki dotyczące pobierania i flasha ffu

Aby przetestować przy użyciu ffu z podpisem lotu, musisz najpierw odblokować urządzenie podczas lotu przed flashowanie locie podpisanego ffu.

1. Na komputerze:
    1. Pobierz ffu na komputer ze strony [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .

    1. Zainstaluj program ARC (pomocnik odzyskiwania zaawansowanego) z Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. Na HoloLens — Flight Unlock: **otwórz** Ustawienia Update & Security Windows niejawny program testów następnie zarejestruj  >    >   się i uruchom ponownie urządzenie.

1. Flash FFU — teraz możesz flashć ffu z podpisem lotu przy użyciu usługi ARC.

### <a name="provide-feedback-and-report-issues"></a>Opinie i zgłaszanie problemów

Użyj aplikacji [Centrum opinii aplikacji na](hololens-feedback.md) swoim HoloLens, aby przekazać opinię i zgłosić problemy. Użycie Centrum opinii zapewnia, że wszystkie niezbędne informacje diagnostyczne są uwzględniane, aby ułatwić naszym inżynierom szybkie debugowanie i rozwiązywanie problemu.  Problemy z chińskim i japońskim wersją HoloLens powinny być zgłaszane w ten sam sposób.

> [!NOTE]
> Pamiętaj, aby zaakceptować monit z pytaniem, czy chcesz Centrum opinii dostępu  do folderu Dokumenty (po wyświetleniu monitu wybierz pozycję Tak).

## <a name="note-for-developers"></a>Uwaga dla deweloperów

Zachęcamy i zachęcamy do wypróbowania tworzenia aplikacji przy użyciu kompilacji niejawnych testerów HoloLens.  Zapoznaj się z [HoloLens dla deweloperów,](https://developer.microsoft.com/windows/mixed-reality/development) aby rozpocząć pracę. Te same instrukcje działają z kompilacjami niejawnych testerów HoloLens.  Możesz użyć tych samych kompilacji aparatu Unity i Visual Studio, których już używasz do HoloLens kompilowania.

## <a name="stop-receiving-insider-builds"></a>Zatrzymywanie otrzymywania kompilacji niejawnych testerów

Jeśli nie chcesz już otrzymywać kompilacji systemu Windows Holographic dla niejawnych testerów, możesz zrezygnować z uruchamiania [](hololens-recovery.md) kompilacji produkcyjnej na platformie HoloLens lub odzyskać urządzenie przy użyciu zaawansowanego pomocnika odzyskiwania, aby odzyskać urządzenie do wersji systemu Windows Holographic, która nie jest niejawnym testerem.

> [!CAUTION]
> Istnieje znany problem, w którym użytkownicy, którzy nie zarejestrują się w kompilacjach insider preview po ręcznej ponownej instalacji nowej kompilacji w wersji zapoznawczej, będą mieli niebieski ekran. Następnie muszą ręcznie odzyskać urządzenie. Aby uzyskać szczegółowe informacje na temat tego problemu, zobacz więcej informacji na temat tego [znanego problemu.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Aby sprawdzić, czy HoloLens jest uruchomiona kompilacja produkcyjna:

1. Przejdź do **Ustawienia > System > informacje** i znajdź numer kompilacji.

1. [Zobacz informacje o wersji dla numerów kompilacji produkcyjnych.](hololens-release-notes.md)

Aby zrezygnować z kompilacji niejawnych testerów:

1. Na stronie HoloLens kompilacji produkcyjnej przejdź do usługi **Ustawienia > Update & Security > Windows niejawny program testów** i wybierz pozycję Zatrzymaj kompilacje **niejawnych testerów.**

1. Postępuj zgodnie z instrukcjami, aby zrezygnować z urządzenia.
