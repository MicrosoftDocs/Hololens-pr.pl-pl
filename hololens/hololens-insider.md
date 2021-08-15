---
title: Insider Preview for Microsoft HoloLens
description: Dowiedz się, jak rozpocząć pracę z kompilacjami niejawnych testerów i przekazać cenne opinie na temat naszej następnej ważnej aktualizacji systemu operacyjnego na HoloLens.
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
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: df0cb555c8445ef4d8f8165996a33e0f8c1a38653b45514594f893e3c761f65a
ms.sourcegitcommit: 9615ed824bdf3f1747ec346da6136704d8eed015
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/11/2021
ms.locfileid: "120364289"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview for Microsoft HoloLens

Witamy w najnowszych kompilacjach insider preview dla HoloLens! Łatwo jest rozpocząć pracę [i przekazać](hololens-insider.md#start-receiving-insider-builds) cenną opinię na temat naszej następnej ważnej aktualizacji systemu operacyjnego na HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Informacje o wersji dla niejawnych testerów

Z przyjemnością rozpoczynamy lotami po nowych funkcjach, aby ponownie Windows niejawnych testerów. Nowe kompilacje będą dostępne w kanałach Dev i Beta, aby uzyskać najnowsze aktualizacje. Będziemy nadal aktualizować tę stronę w przypadku dodawania kolejnych funkcji i aktualizacji do naszych Windows niejawnych testerów. Przygotuj się do pomieszania tych aktualizacji ze swoją rzeczywistością.

| Cecha                 | Opis                | Użytkownik lub scenariusz | Wprowadzono kompilację |
|-------------------------|----------------------------|--------------|------------------|
| [Zmiany WSP dotyczące raportowania HoloLens szczegóły](#csp-changes-for-reporting-hololens-details) | Nowi CSP dla programu do wykonywania zapytań o dane | Administratorzy IT    | 20348.1403                 |
| [Zasady automatycznego logowania kontrolowane przez CSP](#auto-login-policy-controlled-by-csp) | Służy do automatycznego logowania się do konta | Administratorzy IT | 20348.1405 |
| [Obsługa plików PFX dla Menedżera certyfikatów](#pfx-file-support-for-certificate-manager) | Dodawanie certyfikatów PFX za pomocą interfejsu Ustawienia użytkownika | Użytkownik końcowy | 20348.1405 |
| [Wyświetlanie zaawansowanego raportu diagnostycznego w Ustawienia na HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Wyświetlanie dzienników diagnostycznych rozwiązania MDM na urządzeniu | Rozwiązywanie problemów | 20348.1405 |
| [Powiadomienia diagnostyki w trybie offline](#offline-diagnostics-notifications) | Opinie dotyczące zbierania dzienników | Rozwiązywanie problemów | 20348.1405 |
| [Używaj tylko aplikacji ze sklepu prywatnego tylko dla Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Konfigurowanie aplikacji ze sklepu w celu pokazywania tylko aplikacji z organizacji | Administrator IT | 20348.1408 |
| [Ulepszenia zbierania dzienników magazynu o niskiej wydajności](#low-storage-log-collection-improvements) | Ulepszenia scenariuszy zbierania dzienników w sytuacjach niskiego poziomu magazynowania. | Administrator IT | 20348.1412 |
| [Przenoszenie trybu platformy](#moving-platform-mode) | Wprowadzono tryb przenoszenia platformy w wersji beta, który po skonfigurowaniu umożliwia korzystanie z wersji HoloLens 2 w dużych dyskach z ruchami o niskiej dynamice. | Wszystko | 20348.1411 |
| [Poprawki i ulepszenia](#fixes-and-improvements) | Poprawki i ulepszenia dotyczące HoloLens. | Wszystko | 20348.1411 |

### <a name="csp-changes-for-reporting-hololens-details"></a>Zmiany WSP dotyczące raportowania HoloLens szczegóły

- Wprowadzono w kompilacji Windows Insider, 20348.1403

Następujący CSP zostały zaktualizowane o nowe sposoby zgłaszania informacji z HoloLens urządzeń.

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP — bezpłatne Storage

DevDetail CSP now also reports free storage space on HoloLens device. Powinno to być w przybliżeniu zgodne z wartością wyświetlaną Ustawienia stronie aplikacji Storage aplikacji. Poniżej znajduje się konkretny węzeł zawierający te informacje.

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

Ta nowa zasada AutoLogonUser określa, czy użytkownik będzie automatycznie zalogowany. Niektórzy klienci chcą skonfigurować urządzenia, które są powiązane z tożsamością, ale nie chcą mieć żadnego logowania. Imagine urządzenie i natychmiast korzystać z pomocy zdalnej. Możesz też skorzystać z możliwości szybkiej dystrybucji urządzeń HoloLens i umożliwienia użytkownikom końcowych przyspieszenia logowania.

Jeśli zasady są ustawione na niepustą wartość, określają adres e-mail użytkownika logowania automatycznego. Określony użytkownik musi logować się na urządzeniu co najmniej raz, aby włączyć automatyczne logowanie.

OMA-URI wartości ciągu `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` nowych zasad

- Użytkownik z tym samym adresem e-mail będzie mieć włączone automatyczne logowanie.

Na urządzeniu, na którym te zasady są skonfigurowane, użytkownik określony w zasadach musi się logować co najmniej raz. Podczas kolejnych ponownych uruchomień urządzenia po pierwszym zalogowaniu określony użytkownik zostanie automatycznie zalogowany. Obsługiwany jest tylko jeden użytkownik z automatycznym logowaniem. Po włączeniu automatycznie zalogowany użytkownik nie będzie mógł wylogować się ręcznie. Aby logować się jako inny użytkownik, należy najpierw wyłączyć zasady.

> [!NOTE]
> - Niektóre zdarzenia, takie jak główne aktualizacje systemu operacyjnego, mogą wymagać od określonego użytkownika ponownego zalogowania się na urządzeniu w celu wznowienia działania automatycznego logowania. 
> - Logowanie automatyczne jest obsługiwane tylko w przypadku użytkowników msa i usługi AAD.

### <a name="pfx-file-support-for-certificate-manager"></a>Obsługa plików PFX dla Menedżera certyfikatów

Wprowadzono w kompilacji Windows Insider 20348.1405. Dodaliśmy obsługę Menedżera [](certificate-manager.md) certyfikatów, aby teraz używać certyfikatów pfx. Gdy użytkownicy **przejdą** do Ustawienia zaktualizują &, a następnie wybierzą pozycję Zainstaluj certyfikat, interfejs użytkownika obsługuje teraz  >    >  plik certyfikatu  pfx.
Użytkownicy mogą importować certyfikat PFX z kluczem prywatnym do magazynu użytkowników lub magazynu maszynowego.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>Wyświetlanie zaawansowanego raportu diagnostycznego w Ustawienia na HoloLens

W przypadku urządzeń zarządzanych podczas rozwiązywania problemów z zachowaniem ważnym krokiem jest potwierdzenie zastosowania oczekiwanej konfiguracji zasad. Wcześniej ta nowa funkcja musiała zostać wyłączona za pośrednictwem rozwiązania MDM lub w pobliżu urządzenia po wyeksportowaniu dzienników diagnostycznych MDM zebranych za pośrednictwem konta usługi Ustawienia Dostęp do miejsca pracy lub nauki, **a** następnie wybranie opcji Eksportuj dzienniki zarządzania i przeglądane na pobliskim  ->    >  komputerze. 

Teraz diagnostykę MDM można wyświetlić na urządzeniu przy użyciu przeglądarki Edge. Aby łatwiej wyświetlić raport diagnostyczny MDM, przejdź do strony Dostęp do konta służbowego i wybierz pozycję **Wyświetl zaawansowany raport diagnostyczny.** Spowoduje to wygenerowanie i otwarcie raportu w nowym oknie przeglądarki Edge.

![Wyświetlanie zaawansowanego raportu diagnostycznego w Ustawienia aplikacji.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Powiadomienia diagnostyki w trybie offline

Jest to aktualizacja istniejącej funkcji o nazwie [Diagnostyka w trybie offline.](hololens-diagnostic-logs.md#offline-diagnostics) Wcześniej nie było jasnego wskaźnika dla użytkowników, że wyzwolono kolekcję diagnostyczną lub została ona zakończona.
Teraz dodane w kompilacjach Windows Insider istnieją dwie formy poufnych opinii na temat diagnostyki w trybie offline. Pierwsze z nich to wyskakujące powiadomienia wyświetlane zarówno podczas uruchamiania, jak i zakończenia zbierania. Będą one wyświetlane, gdy użytkownik jest zalogowany i ma wizualizacje.

![Wyskakujące powiadomienia dotyczące zbierania dzienników.](./images/logcollection1.jpg)

![Wyskakujące powiadomienia po zakończeniu zbierania dzienników.](./images/logcollection2.jpg)
 
Ponieważ użytkownicy często używają diagnostyki w trybie offline jako mechanizmu rezerwowego zbierania dzienników, gdy nie mają dostępu do ekranu, nie mogą się zalogować lub nadal znajdują się w trybie OOBE, podczas zbierania dzienników będzie również odtwarzany sygnał dźwiękowy. Ten dźwięk będzie odtwarzany oprócz powiadomienia wyskakującego.

Ta nowa funkcja zostanie włączona podczas aktualizacji urządzenia i nie trzeba jej włączać ani zarządzać. Jeśli ta nowa opinia nie zostanie wyświetlona lub nie zostanie wyświetlona, diagnostyka w trybie offline będzie nadal generowana.

Mamy nadzieję, że dzięki temu nowszej dodatku opinii zwrotnej łatwiej jest zbierać dane diagnostyczne i szybciej rozwiązywać problemy.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Używaj tylko aplikacji ze sklepu prywatnego dla Microsoft Store

Zasady RequirePrivateStoreOnly zostały włączone dla HoloLens. Te zasady umożliwiają skonfigurowanie Microsoft Store tak, aby wyświetlała tylko sklep prywatny skonfigurowany dla organizacji. Ograniczenie dostępu tylko do aplikacji, które zostały udostępnione.

Dowiedz się więcej o [applicationmanagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="low-storage-log-collection-improvements"></a>Ulepszenia zbierania dzienników o niskim poziomie magazynu

W scenariuszach, w których wydaje się, że ilość miejsca na dysku na urządzeniu podczas zbierania dzienników diagnostycznych jest niska, zostanie utworzony dodatkowy raport o **nazwieStorageDiagnostics.zip.** Próg niskiego poziomu magazynu jest określany automatycznie przez Windows [magazynu.](https://support.microsoft.com/office/use-onedrive-and-storage-sense-in-windows-10-to-manage-disk-space-de5faa9a-6108-4be1-87a6-d90688d08a48)

### <a name="moving-platform-mode"></a>Przenoszenie trybu platformy

W wersji **Insider Build 20348.1411** dodaliśmy obsługę wersji beta śledzenia na platformach ruchu o niskiej dynamice na platformach HoloLens 2. Po zainstalowaniu kompilacji i włączeniu trybu przenoszenia platformy będzie można używać urządzenia HoloLens 2 w wcześniej niedostępnych środowiskach, takich jak duże jednostki i duże statku. Obecnie ta funkcja jest ukierunkowana na włączanie tylko tych konkretnych ruchomych platform. Chociaż nic nie uniemożliwia próby użycia tej funkcji w innych środowiskach, ta funkcja koncentruje się najpierw na dodawaniu obsługi tych środowisk.

Aby dowiedzieć się więcej o tym, co jest obsługiwane i jak włączyć tę nową funkcję, [odwiedź stronę przenoszenia platformy.](hololens2-moving-platform.md)

### <a name="fixes-and-improvements"></a>Poprawki i ulepszenia

- Rozwiązano znany problem z Portal urządzeń, który nie wyświetlał monitu o [pobranie zablokowanych plików.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Rozwiązano [znany problem z Portal urządzeń podczas przekazywania i pobierania.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- Rozwiązuje problemy związane z raportowaniem właściwości zgodności z HoloLens urządzeń; Ponowne uruchomienie może być wymagane, aby poprawne raportowanie było wyzwalane w kompilacjach niejawnych testerów.  
- Włączono [interfejs API przypisanego](/uwp/api/windows.system.userprofile.assignedaccesssettings?view=winrt-20348) dostępu, dzięki czemu aplikacje mogą teraz określić, HoloLens jest uruchomiona w trybie kiosku dla użytkownika zalogowanego do HoloLens.
- Zaktualizowano wersję w polu usługi Remote Assist zainstalowaną na nowych urządzeniach flash.

## <a name="start-receiving-insider-builds"></a>Rozpoczynanie otrzymywania kompilacji niejawnych testerów

> [!NOTE]
> Jeśli ostatnio nie zaktualizowano, uruchom ponownie urządzenie, aby zaktualizować stan i pobrać najnowszą kompilację.
> - Polecenie głosowe "Reboot device" (Uruchom ponownie urządzenie) działa dobrze. 
> - Możesz również wybrać przycisk ponownego uruchamiania w Ustawienia/Windows niejawny program testów.
>
> Na zadurze wystąpiła usterka, która może spowodować powrót na tory.

Na urządzeniu HoloLens 2 przejdź do Ustawienia  >  **Update & Security**  >  **Windows niejawny program testów** i wybierz **pozycję Wprowadzenie.** Połącz konto użyte do zarejestrowania się jako Windows Insider.

Windows niejawny tester jest teraz przenoszący się do kanałów. Szybki **pierścień** stanie się kanałem **dewelopera,** powolny pierścień  stanie się kanał beta, **a** pierścień wersji zapoznawczej stanie się kanałem wersji **zapoznawczej.**  Oto jak wygląda to mapowanie:

![Windows Wyjaśnienie kanałów niejawnych testerów](images/WindowsInsiderChannels.png)

Aby uzyskać więcej informacji, zobacz Introducing Windows Insider Channels (Wprowadzenie [do kanałów niejawnych testerów)](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) Windows Blogi.
Następnie wybierz pozycję **Aktywne opracowywanie** Windows, wybierz, czy chcesz otrzymywać  kanał **dewelopera,** czy kanał beta kompilacje, i przejrzyj warunki programu.
Wybierz **pozycję > uruchom ponownie teraz,** aby zakończyć. Po ponownym uruchomieniu urządzenia przejdź do Ustawienia > **Update & Security > Sprawdź** aktualizacje w celu uzyskania najnowszej kompilacji.

### <a name="update-error-0x80070490-work-around"></a>Błąd aktualizacji 0x80070490 omięcie

Jeśli wystąpi błąd aktualizacji 0x80070490 podczas aktualizowania w kanale dewelopera lub wersji beta, spróbuj wykonać następujące krótkoterminowe czynności. Obejmuje to przeniesienie kanału dla niejawnych testerów, pobranie aktualizacji, a następnie przeniesienie kanału niejawnego testera z powrotem.

#### <a name="stage-one---release-preview"></a>Etap pierwszy — wersja zapoznawcza

1.  Ustawienia, Zaktualizuj zabezpieczenia &, Windows niejawny program testów wybierz pozycję Kanał **wersji zapoznawczej.**

2.  Ustawienia, Update & Security, Windows Update, **Check for updates**. Po aktualizacji przejdź do etapu 2.

#### <a name="stage-two---dev-channel"></a>Etap drugi — kanał dewelopera

1. Ustawienia, Zaktualizuj & Security, Windows niejawny program testów pozycję **Kanał deweloperów.**

2. Ustawienia, Update & Security, Windows Update, **Check for updates**.

## <a name="ffu-download-and-flash-directions"></a>Wskazówki dotyczące pobierania i flasha ffu

Aby przetestować przy użyciu ffu z podpisem lotu, musisz najpierw odblokować urządzenie podczas lotu przed flashowanie locie podpisanego ffu.

1. Na komputerze:
    1. Pobierz ffu na komputer ze strony [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Zainstaluj program ARC (Advanced Recovery Companion) z Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. Na HoloLens — Flight Unlock: **otwórz** Ustawienia  >  **Update & Security**  >  **Windows niejawny program testów** następnie zarejestruj się i uruchom ponownie urządzenie.

1. Flash FFU — teraz możesz flashowane ffu z podpisem lotu przy użyciu usługi ARC.

### <a name="provide-feedback-and-report-issues"></a>Opinie i zgłaszanie problemów

Użyj aplikacji [Centrum opinii aplikacji na](hololens-feedback.md) swoim HoloLens, aby przekazać opinię i zgłosić problemy. Użycie Centrum opinii zapewnia, że wszystkie niezbędne informacje diagnostyczne są uwzględniane, aby ułatwić naszym inżynierom szybkie debugowanie i rozwiązywanie problemu.  Problemy z wersją języka chińskiego i japońskiego HoloLens powinny być zgłaszane w ten sam sposób.

> [!NOTE]
> Pamiętaj, aby zaakceptować monit z pytaniem, Centrum opinii chcesz uzyskać dostęp  do folderu Dokumenty (po wyświetleniu monitu wybierz pozycję Tak).

## <a name="note-for-developers"></a>Uwaga dla deweloperów

Zachęcamy i zachęcamy do wypróbowania tworzenia aplikacji przy użyciu kompilacji niejawnych testerów HoloLens.  Zapoznaj się z HoloLens [dla deweloperów,](https://developer.microsoft.com/windows/mixed-reality/development) aby rozpocząć pracę. Te same instrukcje działają z kompilacjami niejawnych testerów HoloLens.  Możesz użyć tych samych kompilacji aparatu Unity i Visual Studio, których już używasz do HoloLens kompilowania.

## <a name="stop-receiving-insider-builds"></a>Zatrzymywanie otrzymywania kompilacji niejawnych testerów

Jeśli nie chcesz już otrzymywać kompilacji systemu Windows Holographic dla niejawnych testerów, możesz zrezygnować z [](hololens-recovery.md) uruchamiania kompilacji produkcyjnej na platformie HoloLens lub odzyskać urządzenie przy użyciu narzędzia Advanced Recovery Companion, aby odzyskać urządzenie do wersji systemu Windows Holographic innego niż niejawny program.

> [!CAUTION]
> Istnieje znany problem, w którym użytkownicy, którzy nie zarejestrują się w kompilacjach insider preview po ręcznej ponownej instalacji nowej kompilacji w wersji zapoznawczej, będą mieli niebieski ekran. Następnie muszą ręcznie odzyskać urządzenie. Aby uzyskać szczegółowe informacje na temat tego problemu, zobacz więcej informacji na temat tego [znanego problemu.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Aby sprawdzić, czy HoloLens jest uruchomiona kompilacja produkcyjna:

1. Przejdź do **Ustawienia > System > informacje** i znajdź numer kompilacji.

1. [Zobacz informacje o wersji dla numerów kompilacji produkcyjnych.](hololens-release-notes.md)

Aby zrezygnować z kompilacji niejawnych testerów:

1. Na stronie HoloLens kompilacji produkcyjnej przejdź do usługi **Ustawienia > Update & Security > Windows niejawny program testów** i wybierz pozycję Zatrzymaj kompilacje niejawnych **testerów.**

1. Postępuj zgodnie z instrukcjami, aby zrezygnować z urządzenia.
