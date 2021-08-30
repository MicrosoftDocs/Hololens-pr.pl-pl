---
title: HoloLens wersji 2
description: Bądź na bieżąco ze wszystkimi aktualizacjami w każdej nowej wersji HoloLens 2.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 08/10/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: be2fde329293b89698c0f6dd5d92df1c6260f1be
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190229"
---
# <a name="hololens-2-release-notes"></a>HoloLens wersji 2

Aby zapewnić wydajną pracę z urządzeniami HoloLens, kontynuujemy wydanie funkcji, usterek i aktualizacji zabezpieczeń. Na tej stronie możesz zobaczyć, co nowego w poszczególnych HoloLens miesiącu. Aby uzyskać najnowszą aktualizację HoloLens 2, [](hololens-update-hololens.md#check-for-updates-and-manually-update) możesz sprawdzić aktualizacje i ręcznie zaktualizować lub pobrać aktualizację pełną flash (FFU) w celu flashować urządzenie za pomocą narzędzia [Advanced Recovery Companion.](hololens-recovery.md#clean-reflash-the-device) Pobieranie [jest](https://aka.ms/hololens2download) na bieżąco i zapewnia najnowszą ogólnie dostępną kompilację.

> [!NOTE]
> Najnowsze Windows 11 dotyczyło wersji pc Windows. Niedawno w [](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) maju 2021 r. uruchomiliśmy dużą aktualizację systemu operacyjnego do wersji HoloLens 2. Pracujemy nad nadchodzącym wydaniem na podstawie opinii klientów na temat tej aktualizacji.

> [!IMPORTANT]
> Ze względu na teraz rozwiązany znany problem w kompilacji [21H1,](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)który miał wpływ na użytkowników usługi Remote Assist, tymczasowo wstrzymano ofertę aktualizacji systemu Windows Holographic w wersji 21H1. Zmieniliśmy również domyślną kompilację narzędzia Advanced Recovery Companion (ARC) na wersję Windows Holographic w wersji 20H2 – aktualizacja z czerwca [2021 r.](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update). Kompilacja ARC zostanie teraz wznowiona dla kompilacji 21H1.

## <a name="windows-holographic-version-21h1---august-2021-update"></a>Windows Holographic, wersja 21H1 — aktualizacja z sierpnia 2021 r.

- Kompilacja 20348.1014

Ulepszenia i poprawki w aktualizacji:

- Rozwiązano problem uniemożliwiający działanie kontrolerów Xbox w aplikacjach immersywnych z obsługą kontrolera.
- Ulepszona diagnostyka błędów aktualizacji urządzenia.

## <a name="windows-holographic-version-20h2---august-2021-update"></a>Windows Holographic, wersja 20H2 — aktualizacja z sierpnia 2021 r.

- Kompilacja 19041.1161

Ulepszenia i poprawki w aktualizacji:

- Ta comiesięczna aktualizacja jakości nie zawiera żadnych notowalnych zmian. Zachęcamy do wypróbowania naszej najnowszej kompilacji, Windows Holographic, wersja 21H1.

## <a name="windows-holographic-version-21h1---july-2021-update"></a>Windows Holographic, wersja 21H1 — aktualizacja z lipca 2021 r.

- Kompilacja 20348.1010

Ulepszenia i poprawki w aktualizacji:

- Portal urządzeń ulepszone metody powiadamiania klienta, gdy Eksplorator plików napotka problemy z otwieraniem zablokowanych plików.
- Przekazywanie, pobieranie, zmienianie nazwy i usuwanie plików jest teraz naprawione w przypadku używania protokołu https we wszystkich obsługiwanych przeglądarkach.
- Rozwiązano problem, który Wi-Fi nie można zapisać, gdy interfejs użytkownika właściwości usługi Wi-Fi został uruchomiony z pliku **Ustawienia -> Network & Internet -> Status -> Properties**(Stan usługi > Network &).
- Rozwiązano problem z usuwaniem certyfikatów eSIM w aktualizacjach systemu operacyjnego. Ta poprawka zapewnia, że certyfikaty eSIM i powiązane składniki zostaną usunięte podczas aktualizowania do wersji 21H1.
- Rozwiązano problem wpływający na wstępnie zainstalowane aplikacje podczas resetowania systemu operacyjnego.
- Wydajność ładowania baterii dostosowana do zwiększenia czasu wykonywania podczas ładowania przy zwiększonym ładowaniu procesora CPU. Podczas ładowania HoloLens 2 urządzenia, jeśli urządzenie zostanie wykryte jako uruchomione w cieplej, wewnętrzna bateria będzie ładować się wolniej, aby zmniejszyć ilość ciepła. Dodatnim kompromisem jest mniejsze prawdopodobieństwo zamknięcia urządzenia z powodu problemów cieplnych, co ma wpływ na dłuższe jego wydajność. Jeśli na urządzeniu działa chłodna cena, nie ma to wpływu na stawkę.

## <a name="windows-holographic-version-20h2--july-2021-update"></a>Windows Holographic, wersja 20H2 — aktualizacja z lipca 2021 r.

- Kompilacja 19041.1157

Ulepszenia i poprawki w aktualizacji:

- Portal urządzeń ulepszone metody powiadamiania klienta, gdy Eksplorator plików napotka problemy z otwieraniem zablokowanych plików.
- Przekazywanie, pobieranie, zmienianie nazwy i usuwanie plików jest teraz naprawione w przypadku używania protokołu https we wszystkich obsługiwanych przeglądarkach.

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows Holographic, wersja 21H1 — aktualizacja z czerwca 2021 r.

- Kompilacja 20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive do służbowego rzutu kamery

Dodaliśmy nową funkcję do aplikacji HoloLens 2 Ustawienia, która umożliwia klientom automatyczne przekazywanie zdjęć i wideo rzeczywistości mieszanej z folderu Pictures > Camera Roll urządzenia do odpowiedniego folderu OneDrive for work or school. Ta funkcja rozwiązuje lukę w funkcjach w aplikacji [OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) na platformie HoloLens 2, która obsługuje tylko automatyczne przekazywanie funkcji roll aparatu do osobistego konta konto Microsoft klienta (a nie konta służbowego).

**Jak to działa**

- Odwiedź **stronę Ustawienia > System > Mixed Reality Camera (Aparat > Mixed Reality),** aby włączyć opcję "Przekazywanie aparatu".
- Po ustawieniu tej  funkcji na pozycję Wł. wszystkie zdjęcia rzeczywistości mieszanej lub filmy wideo przechwycone na urządzeniu zostaną automatycznie umieszczone w kolejce do przekazania do folderu Pictures > Camera Roll konta usługi OneDrive for Work lub School.
    >[!NOTE]
    >Zdjęcia i wideo przechwycone  przed włączeniem tej funkcji nie będą kolejkowane do przekazania i nadal będą trzeba je przekazywać ręcznie.
- Komunikat o stanie na stronie Ustawienia wyświetli liczbę plików oczekujących na przekazanie (lub odczyta komunikat "OneDrive jest aktualny", gdy wszystkie oczekujące pliki zostały przekazane).
- Jeśli martwisz się o przepustowość lub chcesz "wstrzymać" przekazywanie z dowolnej **przyczyny,** możesz przełączyć tę funkcję na pozycję Wyłączone. Tymczasowe wyłączenie funkcji gwarantuje, że kolejka przekazywania będzie się zwiększać w przypadku dodawania nowych plików do folderu roll aparatu, ale pliki nie zostaną przesłane do momentu ponownego włączenia tej funkcji.
- Najnowsze pliki zostaną najpierw przesłane (ostatni na węzło, pierwszy na zewnątrz).
- Jeśli twoje OneDrive ma problemy (na przykład po zmianie  hasła), na stronie Ustawienia pojawi się przycisk Napraw teraz.
- Nie ma żadnego maksymalnego rozmiaru pliku, ale pamiętaj, że przekazywanie dużych plików będzie trwać dłużej (zwłaszcza jeśli przepustowość przekazywania jest ograniczona). Jeśli podczas przekazywania dużego pliku zostanie "wstrzymane" lub wyłączone przekazywanie, częściowe przekazywanie zostanie zachowane. Jeśli przekazywanie zostanie ponownie włączone w ciągu kilku godzin od "wstrzymania" lub wyłączenia, przekazywanie będzie kontynuowane od miejsca, w którym zostało przerwane. Jeśli jednak przekazywanie zostanie ponownie włączone po kilku godzinach, przekazywanie dużych plików zostanie uruchomione ponownie od początku.

**Znane problemy i zastrzeżenia**

- To ustawienie nie ma wbudowanego ograniczania przepustowości na podstawie bieżącego użycia przepustowości. Jeśli chcesz zmaksymalizować przepustowość w innym scenariuszu, wyłącz ustawienie ręcznie. Upload zostanie wstrzymana, ale funkcja będzie nadal monitorować nowo dodane pliki do funkcji rzutowania aparatu. Włącz ponownie przekazywanie, gdy wszystko będzie gotowe do kontynuowania.
- Ta funkcja musi być włączona dla każdego konta użytkownika na urządzeniu i może aktywnie przekazywać pliki tylko dla użytkownika, który jest aktualnie zalogowany na urządzeniu.
- Jeśli zdjęcia lub filmy wideo są oglądane w czasie rzeczywistym na stronie Ustawienia, pamiętaj, że liczba oczekujących plików może nie ulec zmianie, dopóki bieżący plik nie zakończy przekazywania.
- Upload wstrzyma się, jeśli urządzenie uśpiono lub zostanie wyłączone. Aby upewnić się, że oczekujące przekazania są ukończone, aktywnie używaj urządzenia do momentu, gdy na stronie usługi Ustawienia zostanie odczytany OneDrive jest aktualny" lub dostosuj ustawienia usługi **Power & uśpienia.**

### <a name="added-support-for-some-telemetry-policies"></a>Dodano obsługę niektórych zasad telemetrii

Następujące zasady telemetrii są teraz obsługiwane na HoloLens 2:

- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

Zarówno system\AllowTelemetry, jak i system\ConfigureTelemetryOptInSettingsUx powinny być używane razem, aby mieć pełną kontrolę nad telemetrią i zachowaniem Ustawienia aplikacji.

Ulepszenia i poprawki w aktualizacji:

- Naprawia poważne uszkodzenie wideo za pomocą kolorowania.
- Rozwiązano problem, który mógł spowodować obcięcie tekstu w menu power.power.
- Włącza obsługę zasad RequirePrivateStoreOnly.

## <a name="windows-holographic-version-20h2--june-2021-update"></a>Windows Holographic, wersja 20H2 — aktualizacja z czerwca 2021 r.

- Kompilacja 19041.1154

### <a name="added-support-for-some-telemetry-policies"></a>Dodano obsługę niektórych zasad telemetrii

Następujące zasady telemetrii są teraz obsługiwane na HoloLens 2:

- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

Zarówno system\AllowTelemetry, jak i system\ConfigureTelemetryOptInSettingsUx powinny być używane razem, aby mieć pełną kontrolę nad telemetrią i zachowaniem Ustawienia aplikacji.

Zachęcamy do wypróbowania naszej najnowszej kompilacji, Windows Holographic, wersja 21H1.

## <a name="windows-holographic-version-1903---june-2021-update"></a>Windows Holographic, wersja 1903 — aktualizacja z czerwca 2021 r.

- Kompilacja 18362.1116

Ulepszenia i poprawki w aktualizacji:

- Ta comiesięczna aktualizacja jakości nie zawiera żadnych notowalnych zmian. Zachęcamy do wypróbowania naszej najnowszej kompilacji, Windows Holographic, wersja 21H1.

>[!IMPORTANT]
> Ta kompilacja nie będzie już serwisowana.

## <a name="windows-holographic-version-21h1"></a>Windows Holographic, wersja 21H1
- Kompilacja 20346.1002

Ta aktualizacja zawiera funkcje dla dwóch docelowych odbiorców. funkcje, które mogą być używane przez każdego na urządzeniu przez użytkownika końcowego, oraz nowe opcje zarządzania urządzeniami, które mogą być konfigurowane przez administratorów IT. W poniższej tabeli określono funkcje, które są istotne dla poszczególnych odbiorców. Jeśli jesteś administratorem IT, zapoznaj się z naszą listą kontrolną [dla administratorów IT — aktualizacja.](#it-admin---update-checklist)
>[!IMPORTANT]
>Aby można było wykonać aktualizację do tej kompilacji, HoloLens 2 urządzenia muszą być aktualnie uruchomione z aktualizacją z lutego 2021 r. (kompilacja 19041.1136) lub nowszą. Jeśli ta aktualizacja funkcji nie jest dostępna, zaktualizuj najpierw urządzenie i spróbuj ponownie.

>[!NOTE]
>Obecnie program Microsoft HoloLens 2 obsługuje comiesięczne aktualizacje obsługi (poprawki usterek i zabezpieczeń) dla następujących wersji:
>- Windows Holographic, wersja 20H2 (kompilacja 19041.1128+)
>- Windows Holographic, wersja 2004 (kompilacja 19041.1103+)
>- Windows Holographic, wersja 1903 (kompilacja 18362+)
>
> Wraz z wprowadzeniem systemu Windows Holographic w wersji 21H1 zaprzestajemy comiesięcznych aktualizacji obsługi dla systemu Windows Holographic w wersji **1903.** Dzięki temu możemy skupić się na najnowszych wersjach i nadal dostarczać cenne ulepszenia.


| Nazwa funkcji                                              | Krótki opis                                                                      | Docelowej | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Nowe Microsoft Edge](#introducing-the-new-microsoft-edge)  | Nowa, Chromium oparta na Microsoft Edge jest teraz dostępna dla HoloLens 2. | Użytkownik końcowy | 
[WebXR i 360 Viewer](#webxr-and-360-viewer) | Wypróbuj immersywne środowiska internetowe i odtwarzanie 360 wideo. | Użytkownik końcowy | 
[Nowa Ustawienia aplikacji](#new-settings-app) | Starsza Ustawienia aplikacji jest zastępowana przez zaktualizowaną wersję nowymi funkcjami i ustawieniami. | Użytkownik końcowy |
[Wyświetlanie kolorowania](#display-color-calibration) | Wybierz alternatywny profil kolorów dla ekranu HoloLens 2. | Użytkownik końcowy |
[Domyślny s wyboru aplikacji](#default-app-picker) | Wybierz aplikację, która ma być uruchamiana dla każdego typu pliku lub linku. | Użytkownik końcowy |
[Kontrola głośności dla aplikacji](#per-app-volume-control) | Kontroluj wolumin na poziomie aplikacji niezależnie od woluminu systemowego. | Użytkownik końcowy |
[Instalowanie aplikacji internetowych](#install-web-apps) | Zainstaluj aplikacje internetowe na HoloLens 2, na przykład Microsoft Office, przy użyciu nowej Microsoft Edge przeglądarki. | Użytkownik końcowy |
[Szybkie przesunięcie w celu wpisania](#swipe-to-type) | Użyj wierzchołka palca, aby "szybko przesunąć" wyrazy na klawiaturze holograficznej. | Użytkownik końcowy |
[Menu Zasilania z menu Start](#power-menu-from-start) | W menu Start uruchom ponownie i zamknij HoloLens urządzeniu. | Użytkownik końcowy |
[Wielu użytkowników na liście na ekranie Logowania](#multiple-users-listed-on-sign-in-screen) | Wyświetlanie wielu kont użytkowników na ekranie Logowanie. | Użytkownik końcowy |
[Obsługa mikrofonu zewnętrznego USB-C](#usb-c-external-microphone-support) | Używaj mikrofonów USB-C dla aplikacji i/lub funkcji Remote Assist. | Użytkownik końcowy |
[Automatyczne logowanie gościa dla kiosków](#visitor-auto-logon-for-kiosks) | Umożliwia automatyczne logowanie na kontach gości, które mają być używane w trybach kiosku. | Administrator IT |
[Nowe identyfikatory AUMID dla nowych aplikacji w trybie kiosku](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | Identyfikatory AUMID dla nowych Ustawienia i aplikacji brzegowych. | Administrator IT |
[Ulepszono sposób awarii trybu kiosku](#kiosk-mode-behavior-changes-for-handling-of-failures) | Tryb kiosku wyszukuje dostęp przypisany globalnie przed pustym menu Start. | Administrator IT |
[Nowe ustawieniaUruchomienie dla widoczności Ustawienia strony](#new-settings-uris-for-page-settings-visibility) | Ponad 20 nowych ustawieńUruchomień dla Ustawienia/PageVisibilityList. | Administrator IT |
[Konfigurowanie diagnostyki rezerwowej](#configuring-fallback-diagnostics-via-settings-app) | Ustawianie zachowania diagnostyki rezerwowej w Ustawienia aplikacji. | Administrator IT |
[Udostępnianie rzeczy pobliskim urządzeniem](#share-things-with-nearby-devices) | Udostępnianie plików lub adresów URL z HoloLens komputera. | Wszystko |
[Nowe ślady diagnostyczne systemu operacyjnego](#new-os-diagnostic-traces) | Nowe narzędzie do rozwiązywania problemów Ustawienia aktualizacji systemu operacyjnego. | Administrator IT |
[Optymalizacja dostarczania zapoznawcza](#delivery-optimization-preview) | Zmniejsz zużycie przepustowości w przypadku pobierania z HoloLens urządzeń. | Administrator IT |

Zapoznaj się z powiązanymi informacjami o wersji:

- [Odwiedź archiwum HoloLens Emulator archiwum](/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Wprowadzenie do nowej Microsoft Edge

![Animacja starszego Microsoft Edge logo nowego Microsoft Edge logo.](images/new-edge.gif)

Nowa aplikacja Microsoft Edge [projekt](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) Chromium open source w celu zapewnienia lepszej zgodności dla klientów i mniejszej fragmentacji sieci Web dla deweloperów sieci Web.

> [!IMPORTANT]
> Ta nowa Microsoft Edge automatycznie zastępuje starsze Microsoft Edge, które nie [są już obsługiwane w](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) nowych wersjach.

![Nowy Microsoft Edge zrzut ekranu.](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Uruchamianie nowego Microsoft Edge

Nowa Microsoft Edge ![ikona Microsoft Edge nowej aplikacji.](images/new_edge_logo.png) (reprezentowany przez niebieską i zieloną ikonę wirowania) jest przypinany do menu Start i będzie automatycznie uruchamiany po aktywowaniu linku internetowego.

> [!NOTE]
> Po pierwszym uruchomieniu nowej aplikacji Microsoft Edge wersji HoloLens 2 ustawienia i dane zostaną zaimportowane ze starszych wersji Microsoft Edge. Jeśli po uruchomieniu nowego Microsoft Edge nadal używasz starszej Microsoft Edge, nowe dane nie będą synchronizowane ze starszej wersji Microsoft Edge do nowej Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Konfigurowanie ustawień zasad dla nowego Microsoft Edge

Nowa wersja Microsoft Edge administratorom IT znacznie szerszy zestaw zasad przeglądarki na platformie HoloLens 2 niż były wcześniej dostępne w starszych wersjach Microsoft Edge.

Oto kilka przydatnych zasobów, które mogą dowiedzieć się więcej na temat zarządzania ustawieniami zasad dla nowej Microsoft Edge:

- [Konfigurowanie Microsoft Edge ustawień zasad sieciowych przy użyciu Microsoft Intune](/deployedge/configure-edge-with-intune)
- [Starsza wersja Microsoft Edge do Microsoft Edge mapowania zasad](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Mapowanie zasad Microsoft Edge Google Chrome](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Pełna [Microsoft Edge Enterprise dokumentacji](/deployedge/)

> [!IMPORTANT]
> Ze względu na ilość zasad przeglądarki obsługiwanych przez nową Microsoft Edge nasz zespół nie może zagwarantować, że wszystkie nowe zasady będą HoloLens 2. Jednak przetestowaliśmy i potwierdziliśmy, że nowe Microsoft Edge równoważne każdej starszej wersji zasad Microsoft Edge obsługiwanych wcześniej w HoloLens 2 działają zgodnie z oczekiwaniami. Zobacz [Starsza wersja Microsoft Edge, Microsoft Edge mapowania](/deployedge/microsoft-edge-policy-map-legacy-to-newedge) zasad, aby znaleźć nowe Microsoft Edge równoważne każdej starszej wersji zasad przeglądarki Microsoft Edge, których używano w programie HoloLens 2.
>
> Istnieją co najmniej dwie nowe zasady Microsoft Edge, które nie *będą działać* z HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Czego można oczekiwać od nowej Microsoft Edge w HoloLens 2

Ponieważ nowy Microsoft Edge to natywna aplikacja Win32 z nową warstwą adaptera platformy uniwersalnej systemu Windows umożliwiającą jej uruchamianie na urządzeniach tylko na platformie uniwersalnej systemu Windows, takich jak HoloLens 2, niektóre funkcje mogą nie być natychmiast dostępne. W najbliższych miesiącach będziemy obsługiwać nowe scenariusze i funkcje, dlatego sprawdź, czy w tym miejscu znajdują się aktualne informacje.

**Scenariusze i funkcje, które powinny działać:**
- Środowisko pierwszego uruchomienia, logowanie do profilu i synchronizacja
- Witryny internetowe powinny być renderowane i zachowywać się zgodnie z oczekiwaniami
- Większość funkcji przeglądarki (Ulubione, Historia itp.) powinna działać zgodnie z oczekiwaniami
- Tryb ciemny
- Instalowanie aplikacji internetowych na urządzeniu
- Instalowanie rozszerzeń (daj nam znać, jeśli używasz jakichkolwiek rozszerzeń, które nie działają prawidłowo na HoloLens 2)
- Wyświetlanie i oznaczanie pliku PDF
- Dźwięk przestrzenny z pojedynczego okna przeglądarki
- Automatyczne i ręczne aktualizowanie przeglądarki
- Zapisywanie pliku PDF z menu Drukuj (przy użyciu opcji "Zapisz do pliku PDF")
- Rozszerzenie WebXR i 360 Viewer
- Przywracanie zawartości w prawidłowym oknie podczas przeglądania wielu okien umieszczonych w środowisku

**Scenariusze i funkcje, które nie powinny działać:**
- Dźwięk przestrzenny z wielu okien z równoczesnym strumieniem audio
- "See it, say it" (Zobacz, powiedz to)
- Drukowanie

**Najważniejsze znane problemy z przeglądarką:**

- Podgląd lupy na klawiaturze holograficznej został wyłączony dla nowej Microsoft Edge. Mamy nadzieję, że w przyszłej aktualizacji ponownie wdniemy się w tę funkcję, gdy powiększanie będzie działać prawidłowo.
- Dźwięk może być odtwarzany z niewłaściwego okna przeglądarki, jeśli masz otwarte i aktywne inne okno przeglądarki. Ten problem można omiń, zamykając inne aktywne okno, które nie powinno odtwarzać dźwięku.
- Podczas odtwarzania dźwięku z okna przeglądarki w trybie ["Obserwuj mnie"](hololens2-basic-usage.md#follow-me-stop-following)dźwięk będzie odtwarzany, jeśli wyłączysz tryb "Obserwuj mnie". Ten problem można ominić, zatrzymując odtwarzanie audio przed wyłączeniem trybu "Obserwuj mnie" lub zamykając okno za pomocą **przycisku X.**
- Interakcja z aktywnymi Microsoft Edge windows może spowodować nieoczekiwane nieaktywne inne okna aplikacji 2D. Te okna można ponownie uaktywnić, ponownie korzystając z nich.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Kanały niejawnych testerów

Zespół Microsoft Edge udostępnia trzy kanały w wersji zapoznawczej dla niejawnych testerów edge: Beta, Dev i Canary. Zainstalowanie kanału w wersji zapoznawczej nie spowoduje odinstalowania wydanej wersji programu Microsoft Edge na komputerze HoloLens 2 i można zainstalować więcej niż jedną wersję jednocześnie. 

Odwiedź stronę [główną Microsoft Edge Insider,](https://www.microsoftedgeinsider.com) aby dowiedzieć się więcej na temat społeczności niejawnych testerów przeglądarki Edge. Aby dowiedzieć się więcej na temat różnych kanałów dla niejawnych testerów w programie Edge i rozpocząć pracę, odwiedź stronę [pobierania dla niejawnego testera programu Edge.](https://www.microsoftedgeinsider.com/download)

Istnieje kilka dostępnych metod instalowania kanałów Microsoft Edge insider w HoloLens 2:

**Bezpośrednia instalacja na urządzeniu (obecnie dostępna tylko dla urządzeń nieza pomocą oprogramowania)**
  1. Na stronie HoloLens 2 odwiedź stronę pobierania [dla niejawnego testera przeglądarki Edge.](https://www.microsoftedgeinsider.com/download)
  1. Wybierz przycisk **Pobierz dla HoloLens 2** dla kanału niejawnego testera edge, który chcesz zainstalować.
  1. Uruchom pobrany plik msix z kolejki pobierania przeglądarki Edge lub z folderu "Pobrane" urządzenia (przy użyciu Eksplorator plików).
  1. [Zostanie uruchomić instalator](app-deploy-app-installer.md) aplikacji.
  1. Wybierz przycisk **Zainstaluj.**
  1. Po pomyślnej instalacji znajdziesz Microsoft Edge Beta, Dev lub Canary jako oddzielny **wpis** na Wszystkie aplikacje listy menu Start.

**Instalowanie za pośrednictwem komputera Windows Portal urządzeń (wymaga, aby tryb [dewelopera](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) był włączony na HoloLens 2)**
  1. Na komputerze odwiedź stronę pobierania przeglądarki [Edge dla niejawnych testerów.](https://www.microsoftedgeinsider.com/download)
  1. Wybierz przycisk **strzałki listy rozwijanej** obok przycisku "Pobierz dla Windows 10" dla kanału niejawnego testera edge, który chcesz zainstalować.
  1. Wybierz **HoloLens 2** z menu rozwijanego.
  1. Zapisz plik msix w folderze "Pobrane" na komputerze (lub innym folderze, który można łatwo znaleźć).
  1. Użyj [Windows Portal urządzeń](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) na komputerze, aby zainstalować pobrany plik msix na komputerze HoloLens 2.
  1. Po pomyślnej instalacji znajdziesz Microsoft Edge Beta, Dev lub Canary jako oddzielny **wpis** na Wszystkie aplikacje listy menu Start.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Używanie funkcji WDAC do blokowania nowych Microsoft Edge

W przypadku administratorów IT, którzy chcą zaktualizować swoje zasady [WDAC](windows-defender-application-control-wdac.md) w celu zablokowania nowej Microsoft Edge aplikacji, należy dodać następujące elementy do zasad.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Zarządzanie punktami końcowymi dla nowego Microsoft Edge

Niektóre środowiska mogą mieć ograniczenia sieciowe, które należy wziąć pod uwagę. Aby zapewnić bezproblemowe działanie nowej krawędzi, włącz [te punkty końcowe firmy Microsoft.](/deployedge/microsoft-edge-security-endpoints)

Przeczytaj więcej na temat aktualnie [dostępnych punktów końcowych dla HoloLens](hololens-offline.md).

### <a name="install-web-apps"></a>Instalowanie aplikacji internetowych
 > [!Note]
>Od [Windows Holographic w wersji 21H1](hololens-release-notes.md#windows-holographic-version-21h1)Office nie będzie już wstępnie zainstalowana.

Nowej przeglądarki Edge można używać do instalowania aplikacji internetowych Microsoft Store aplikacji. Na przykład możesz zainstalować aplikację internetową Microsoft Office, aby wyświetlać i edytować pliki hostowane na SharePoint lub OneDrive. Aby zainstalować Office internetową, odwiedź i wybierz przycisk App Available (Dostępna aplikacja) lub https://www.office.com **Office** (Zainstaluj aplikację) na  pasku adresu. Wybierz **pozycję Zainstaluj,** aby potwierdzić.

> [!IMPORTANT]
> Office aplikacji internetowej jest dostępna tylko wtedy, HoloLens 2 ma aktywne połączenie z Internetem.

### <a name="webxr-and-360-viewer"></a>WebXR i przeglądarka 360

Nowa wersja Microsoft Edge obsługę funkcji WebXR, która jest nowym standardem tworzenia immersywnych interfejsów internetowych (zastępowanie serwera WebVR). Wiele immersywnych środowisk internetowych zostało zaprojektowanych z myślą o VR (zastępują one pole widzenia środowiskiem wirtualnym), ale te środowiska są również obsługiwane przez HoloLens 2. Standard WebXR umożliwia również immersywne środowiska internetowe rzeczywistości rozszerzonej i mieszanej, które korzystają ze środowiska fizycznego. Ponieważ deweloperzy spędzają więcej czasu z webxr, przewidujemy, że nowe immersywne środowiska rzeczywistości rozszerzonej i mieszanej będą przychodzić do HoloLens 2 klientów!

Rozszerzenie 360 Viewer jest wbudowane w usługę WebXR i jest automatycznie instalowane wraz z nową Microsoft Edge na HoloLens 2. To rozszerzenie internetowe umożliwia poszerzenie możliwości korzystania z filmów wideo na poziomie 360 stopni. Serwis YouTube oferuje największy wybór 360 filmów wideo, dlatego zachęcamy do rozpoczęcia w tym miejscu.

#### <a name="how-to-use-webxr"></a>Jak używać usługi WebXR

1. Przejdź do witryny internetowej z obsługą webxr.
1. Wybierz przycisk **Wprowadź VR** w witrynie internetowej. Lokalizacja i wizualna reprezentacja tego przycisku może się różnić w zależności od witryny internetowej, ale może wyglądać podobnie do:

    ![Wprowadź przykład przycisku VR.](images/75px-enter-vr.png)

1. Przy pierwszej próbie uruchomienia środowiska WebXR w określonej domenie przeglądarka poprosi o zgodę na wprowadzenie widoku immersyjnego i wybierz pozycję **Zezwalaj.**
1. [Manipuluj HoloLens 2 gestami.](hololens2-basic-usage.md#the-hand-tracking-frame)
1. Jeśli środowisko nie ma przycisku **Wyjdź,** użyj [gestu Start,](hololens2-basic-usage.md#start-gesture) aby powrócić do strony głównej.

**Zalecane przykłady dla usługi WebXR**
- Przeglądarka 360 (zobacz następną sekcję)
- [XR Irysy](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>Jak używać przeglądarki 360

1. Przejdź do wideo na 360 stopni w serwisie YouTube.
1. W ramce wideo wybierz przycisk zestawu nagłownego rzeczywistości mieszanej:

    ![Przycisk aktywacji przeglądarki 360.](images/enter-360-viewer.jpg)

1. Przy pierwszej próbie uruchomienia przeglądarki 360 w określonej domenie przeglądarka poprosi o zgodę na wprowadzenie widoku immersyjnego. wybierz pozycję **Zezwalaj**.
1. [Naciśnij w powietrzu,](hololens2-basic-usage.md#select-using-air-tap) aby wyprowadzić kontrolki odtwarzania. Używaj [promieni dłoni i](hololens2-basic-usage.md#select-using-air-tap) naciśnięcia w powietrzu, aby odtwarzać/wstrzymywać, pomijać przechodzenie do przodu/do tyłu, włączać/wyłączać napisy lub zatrzymywać środowisko (co zamyka widok immersyjny). Kontrolki odtwarzania znikną po kilku sekundach braku aktywności.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Znane problemy związane z najlepszymi usługami WebXR i 360 Viewer
- W zależności od złożoności procesu WebXR szybkość klatek może ulec spadkowi lub zaciemnieniom.
- Obsługa językowego ręki w funkcji WebXR nie jest domyślnie włączona. Deweloperzy mogą włączyć obsługę `edge://flags` za pośrednictwem usługi , włączając funkcję "WebXR Hand Input".
- 360 filmów wideo z witryn innych niż YouTube może nie działać zgodnie z oczekiwaniami.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Przekazywanie opinii na temat webXR i przeglądarki 360

Podziel się opinią i błędami z naszym zespołem za pośrednictwem funkcji **Wyślij opinię** w nowej Microsoft Edge.

### <a name="new-settings-app"></a>Nowa Ustawienia aplikacji

W tej wersji wprowadzamy nową wersję aplikacji Ustawienia aplikacji. Nowa aplikacja Ustawienia zawiera nowe funkcje i rozszerzone ustawienia dla usługi HoloLens 2 w następujących obszarach: Dźwięk, Uśpienie usługi Power &, Sieć & Internet, Aplikacje, Konta, Ułatwienia dostępu i inne.

> [!NOTE]
> Ponieważ nowa aplikacja Ustawienia różni się od starszej aplikacji Ustawienia, wszystkie okna Ustawienia wcześniej umieszczone wokół środowiska zostaną usunięte po aktualizacji.

![Nowa Ustawienia strony głównej aplikacji.](images/new-settings-app.png)

**Nowe funkcje i ustawienia**
- Ustawienia wyszukiwania: wyszukaj ustawienia ze strony Ustawienia głównej przy użyciu słów kluczowych lub nazwy ustawienia.
- Dźwięk > systemu:
  - Wejściowe i wyjściowe urządzenia audio: niezależne wybieranie wejściowych i wyjściowych urządzeń audio (na przykład nasłuchiwać dźwięku za pośrednictwem mikrofonu Bluetooth lub używać mikrofonu USB-C do wprowadzania audio).
    > [!NOTE]
    > Bluetooth nie są obsługiwane przez HoloLens 2.
  - Wolumin aplikacji: niezależnie dostosuj wolumin każdej aplikacji. Zobacz [per app volume control (Kontrola woluminu aplikacji).](#per-app-volume-control)
- System > power & uśpienia: wybierz, kiedy urządzenie ma przejść w stan uśpienia po okresie braku aktywności.
- System > Baterii: ręcznie włączyć tryb oszczędzanie baterii lub ustawić próg baterii, w którym punkt oszczędzanie baterii automatycznie włączyć tryb.
- Urządzenia > USB: można domyślnie wyłączyć połączenia USB.
- Sieć & Internet:
  - Karty Ethernet USB-C będą teraz wyświetlane w sieci & Internet.
  - Ustawienia karty Ethernet USB-C są teraz dostępne, łącznie z jej adresem IP.
  - Teraz można włączyć tryb samolotowy na HoloLens 2.
- Aplikacje: możesz zresetować domyślne aplikacje używane dla typów plików i linków. Aby uzyskać więcej informacji, zobacz [S wyboru domyślnej aplikacji.](#default-app-picker)
- Konta > innych użytkowników: właściciele urządzeń mogą dodawać użytkowników, uaktualniać użytkowników standardowych do właścicieli urządzeń, obniżać właścicieli urządzeń do standardowych użytkowników i usuwać użytkowników.
- Ułatwienia dostępu: zmiana rozmiaru tekstu i niektórych efektów wizualnych.

**Znane problemy**
- Wcześniej umieszczone Ustawienia zostaną usunięte (patrz uwaga powyżej).
- Nie można już zmienić nazwy urządzenia na Ustawienia aplikację. Administratorzy IT mogą zmieniać nazwy urządzeń za pomocą szablonu nazwy urządzenia rozwiązania [Windows Autopilot for HoloLens 2](hololens2-autopilot.md) lub węzła MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.
- Na stronie Ethernet przez cały czas jest przedstawiane wirtualne urządzenie Ethernet ("UsbNcm").
- Użycie baterii dla nowej Microsoft Edge może być niedokładne, ze względu na charakter aplikacji klasycznej Win32 obsługiwanej przez warstwę adaptera platformy uniwersalnej systemu Windows (nie przewiduje się wkrótce żadnej poprawki).

#### <a name="display-color-calibration"></a>Wyświetlanie kolorów



To nowe ustawienie umożliwia wybranie alternatywnego profilu koloru dla wyświetlanego HoloLens 2. Może to ułatwić wyświetlanie kolorów bardziej precyzyjnych, szczególnie na niższych poziomach jasność ekranu. Kolorowanie wyświetlania można znaleźć w Ustawienia aplikacji na stronie > Firmy.

> [!NOTE]
> Ponieważ to ustawienie zapisuje nowy profil kolorów w oprogramowaniu układowym wyświetlania, jest to ustawienie dla poszczególnych urządzeń (i nie jest unikatowe dla każdego konta użytkownika).

##### <a name="how-to-use-display-color-calibration"></a>Jak używać kolorów wyświetlania

1. Uruchom aplikację **Ustawienia** i przejdź do > **System .**
1. W **obszarze Wyświetl kolor kolor** wybierz przycisk Run display color **(Uruchom wyświetlanie koloru).**
1. Zostanie uruchomić środowisko kolorowania wyświetlania i zachęcamy do upewninia się, że twoja przyszła pozycja jest poprawna.
1. Po zakończeniu pracy z oknami dialogowymi instrukcji ekran zostanie automatycznie wygaszony do 30%.
    > [!TIP]
    > Jeśli masz problemy z wyświetlaniem wygaszanej sceny w środowisku, możesz ręcznie dostosować poziom jasność HoloLens 2 za pomocą przycisków jasność po lewej stronie urządzenia.
1. Wybierz przyciski od 1 do 6, aby natychmiast wypróbować każdy profil kolorów i znaleźć taki, który wygląda najlepiej dla Twoich oczu (zazwyczaj oznacza to, że profil, który pomaga scenie wyglądać najbardziej neutralnie, z wzorcem skali szarości i wyglądem w kolorze zgodnie z oczekiwaniami).

    ![Wyświetl scenę z natłokami kolorów.](images/color-cal-ui.png)
    
1. Jeśli wybrany profil ci się przyjmuje, wybierz przycisk **Save & Exit (Zapisz** & zakończ).
1. Jeśli nie chcesz wprowadzać zmian, wybierz przycisk Anuluj & **zakończ,** a zmiany zostaną przywrócone

> [!TIP]
> Poniżej podano kilka przydatnych wskazówek, które należy mieć na uwadze podczas korzystania z ustawienia koloru wyświetlania:
> - Zawsze, gdy chcesz, możesz ponownie Ustawienia kolorów wyświetlania
> - Jeśli każda osoba na urządzeniu wcześniej użyła tego ustawienia do zmiany profilów kolorów, data/godzina ostatniej zmiany zostanie odzwierciedlona na stronie Ustawienia kolorów
> - Po uruchomieniu ponownie ustawienia kolorów wyświetlania profil kolorów, który został wcześniej zapisany, zostanie wyróżniony, a profil 0 nie będzie wyświetlany (ponieważ profil 0 reprezentuje oryginalny profil koloru ekranu)
> - Jeśli chcesz przywrócić oryginalny profil koloru ekranu, możesz to zrobić na stronie Ustawienia (zobacz, jak [zresetować profil kolorów](#how-to-reset-color-profile))

##### <a name="how-to-reset-color-profile"></a>Jak zresetować profil kolorów 

Jeśli niestandardowy profil kolorów zapisany na urządzeniu HoloLens 2 jest niezadowolony, możesz przywrócić oryginalny profil kolorów urządzenia:
1. Uruchom aplikację **Ustawienia** i przejdź do > **System .**
1. W **obszarze Wyświetl kolor kolor** wybierz przycisk **Przywróć domyślny profil** kolorów.
1. Gdy zostanie otwarte okno dialogowe, wybierz **pozycję** Uruchom ponownie, jeśli wszystko jest gotowe do ponownego HoloLens 2 i zastosowania zmian.

#### <a name="top-display-color-calibration-known-issues"></a>Znane problemy dotyczące najniebędszego kolorowania kolorów

- Na stronie Ustawienia ciąg stanu, który informuje o tym, kiedy profil kolorów został ostatnio zmieniony, będzie aktualny do momentu ponownego załadowania tej strony Ustawienia.
    - Obejście: Wybierz inną Ustawienia, a następnie ponownie wybierz stronę Wynisz.

#### <a name="default-app-picker"></a>Domyślny s wyboru aplikacji

Po aktywowaniu hiperlinku lub otwarciu typu pliku zawierającego więcej niż jedną zainstalowaną aplikację, która go obsługuje, zostanie otwarte nowe okno z monitem o wybranie zainstalowanej aplikacji, która powinna obsługiwać typ pliku lub linku. W tym oknie możesz również zdecydować, aby wybrana aplikacja obsługiła plik lub link o typie "Raz" lub "Zawsze".

Jeśli wybierzesz opcję "Zawsze", ale później chcesz zmienić aplikację, która obsługuje określony typ pliku lub linku, możesz zresetować zapisane wartości domyślne w u **Ustawienia > Apps.** Przewiń w dół strony i wybierz przycisk **Wyczyść** w obszarze "Domyślne aplikacje dla typów plików" i/lub "Aplikacje domyślne dla typów linków". W przeciwieństwie do podobnego ustawienia na komputerach stacjonarnych nie można resetować ustawień domyślnych poszczególnych typów plików.

#### <a name="per-app-volume-control"></a>Kontrola głośności dla aplikacji

Teraz w Windows kompilacji użytkownicy mogą ręcznie dostosować poziom woluminu każdej aplikacji. Dzięki temu użytkownicy mogą lepiej skupić się na aplikacjach, których potrzebują, lub lepiej słyszeć podczas korzystania z wielu aplikacji. Może to na przykład wymagać wyłączenia woluminu jednej aplikacji podczas rozmowy z inną osobą w celu uzyskania pomocy zdalnej w innej.

Aby ustawić wolumin poszczególnych aplikacji, przejdź do Ustawienia System Sound i w obszarze **Zaawansowane** opcje dźwięku wybierz pozycję Wolumin  ->    ->  aplikacji **i preferencje urządzenia.**<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Szybkie przesunięcie w celu wpisania

Niektórzy klienci szybciej "wpisują" na klawiaturze wirtualnej, szybko przesuwając kształt wyrazu, który zamierza wpisać, i wyświetlamy podgląd tej funkcji dla klawiatury holograficznej. Możesz szybko przesuwać po jednym wyrazie na raz, przekazując wierzchołek palca przez płaszczyznę klawiatury holograficznej, szybko przesuwając kształt wyrazu, a następnie odsłaniając wierzchołek palca od płaszczyzny klawiatury. Możesz szybko przesunąć kolejne wyrazy bez konieczności naciskania spacji, usuwając palcem z klawiatury między wyrazami. Funkcja będzie działać, jeśli po przesunięciu palca na klawiaturze zostanie wyświetlony ślad przesunięcia.

Pamiętaj, że korzystanie z tej funkcji i opanowanie jej może być trudne ze względu na charakter klawiatury holograficznej, w przypadku której nie masz odporność na palca (w przeciwieństwie do ekranu telefonu komórkowego). 

### <a name="power-menu-from-start"></a>Menu Zasilania z menu Start

Nowe menu, które umożliwia użytkownikowi wylogowanie się, zamknięcie i ponowne uruchomienie urządzenia. Wskaźnik w HoloLens ekran startowy, który pokazuje, kiedy jest dostępna aktualizacja systemu.

#### <a name="how-to-use"></a>Sposób użycia

1. Otwórz okno HoloLens ekran startowy użyciu [gestu Start](hololens2-basic-usage.md#start-gesture) lub powiedzenie "Przejdź do startu".

2. Zwróć uwagę na ikonę wielokropka (...) obok obrazu profilu użytkownika:<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Wybierz obraz profilu użytkownika przy użyciu rąk lub polecenia głosowego "Power".

4. Zostanie wyświetlone menu z opcjami Wyloguj, Uruchom ponownie lub Zamknij urządzenie:<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Wybierz opcje menu, aby wylogować się, ponownie uruchomić lub zamknąć HoloLens. Opcja Wyloguj może być dostępna, jeśli urządzenie jest ustawione dla pojedynczego konta [Microsoft (MSA) lub konta lokalnego.](hololens-identity.md)

6. Odrzuć menu, dotykając dowolnego miejsca lub zamykając menu Start gestem Start.

#### <a name="update-indicator"></a>Wskaźnik aktualizacji

Gdy aktualizacja jest dostępna, ikona wielokropka pojawi się, aby wskazać, że ponowne uruchomienie zainstaluje aktualizację Opcje menu również zmienią się, aby odzwierciedlić obecność aktualizacji.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Wielu użytkowników na ekranie logowania

Wcześniej na ekranie Logowanie był pokazywany tylko ostatnio zalogowany użytkownik, a także punkt wejścia "Inny użytkownik". Otrzymaliśmy opinie klientów, że nie jest to wystarczające, jeśli wielu użytkowników zalogowało się na urządzeniu. Nadal wymagane było ponowne wpisze nazwę użytkownika itp.

Wprowadzone w tej Windows kompilacji  po wybraniu pozycji Inny użytkownik, która znajduje się po prawej stronie pola wprowadzania numeru PIN, na ekranie Logowanie będzie wyświetlanych wielu użytkowników, którzy wcześniej zalogowali się na urządzeniu. Dzięki temu użytkownicy mogą wybrać swój profil użytkownika, a następnie zalogować się przy użyciu Windows Hello poświadczeń. Nowego użytkownika można również dodać do urządzenia z tej strony Inni użytkownicy za pośrednictwem **przycisku Dodaj** konto.

W menu Inni użytkownicy na przycisku Inni użytkownicy zostanie wyświetlany ostatni użytkownik zalogowany na urządzeniu. Wybierz ten przycisk, aby powrócić do ekranu Logowania dla tego użytkownika.

![Domyślny ekran logowania.](./images/multiusers1.jpg)

<br>

![Ekran logowania innych użytkowników.](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Obsługa zewnętrznego mikrofonu USB-C

> [!IMPORTANT]
> Podłączanie **mikrofonu USB nie ustawi go** automatycznie jako urządzenia wejściowego . Podczas podłączania zestawu słuchawki USB-C użytkownicy zauważą, że dźwięk telefonu komórkowego zostanie automatycznie przekierowany do słuchawki, ale system operacyjny HoloLens określa priorytet wewnętrznej macierzy mikrofonów nad innymi urządzeniami wejściowymi. **Aby użyć mikrofonu USB-C, wykonaj poniższe kroki.**

Użytkownicy mogą wybierać zewnętrzne mikrofony podłączone do dysku USB C przy użyciu **panelu Ustawień** dźwięku. Mikrofony USB-C mogą służyć do wywoływania, nagrywania itp.

Otwórz aplikację **Ustawienia** wybierz **pozycję Dźwięk**  >  **systemowy.**

![Dźwięk Ustawienia.](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Aby używać mikrofonów zewnętrznych z **usługą Remote Assist,** użytkownicy będą musieli kliknąć hiperlink "Zarządzanie urządzeniami dźwiękowymi".
>
> Następnie użyj listy rozwijanej, aby ustawić zewnętrzny mikrofon jako **Domyślny lub** Domyślny **dla komunikacji.** Wybranie **opcji Domyślne** oznacza, że zewnętrzny mikrofon będzie używany wszędzie.
>
> Wybranie **opcji Domyślna** komunikacja oznacza, że zewnętrzny mikrofon będzie używany w uciece zdalnej pomocy i innych aplikacjach komunikacyjnych, ale HoloLens macierz mikrofonu może być nadal używana do innych zadań.

![Zarządzanie urządzeniami dźwiękowymi.](images/usbc-mic-2.png)

<br>

![Ustaw wartość domyślną mikrofonu.](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Co z obsługą Bluetooth mikrofonu?

Niestety, Bluetooth mikrofony nie są obecnie obsługiwane na HoloLens 2.

#### <a name="troubleshooting-usb-c-microphones"></a>Rozwiązywanie problemów z mikrofonami USB-C

Należy pamiętać, że niektóre mikrofony USB-C nieprawidłowo zgłaszają się jako mikrofon *i prelegent.* Jest to problem z mikrofonem, a nie z HoloLens. Podczas podłączania jednego z tych mikrofonów do HoloLens może zostać utracony dźwięk. Na szczęście istnieje prosta poprawka.  

W **Ustawienia** System Sound jawnie ustaw wbudowane osoby mówiące (sterownik audio funkcji  ->    ->   **analogicznej)** jako **domyślne urządzenie**. HoloLens zapamiętać to ustawienie, nawet jeśli mikrofon zostanie później usunięty i ponownie nawiązyny połączenie.

![Rozwiązywanie problemów z mikrofonami USB-C.](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Automatyczne logowanie gościa dla kiosków

Ta nowa funkcja umożliwia automatyczne logowanie na kontach gościa w trybach kiosku.

W przypadku konfiguracji spoza usługi AAD, aby skonfigurować urządzenie do automatycznego logowania gościa:

1. Utwórz pakiet aprowizowania, który:
    1. Konfiguruje **ustawienia środowiska uruchomieniowego/AssignedAccess,** aby zezwalać na konta gości.
    1. Opcjonalnie rejestruje urządzenie w układzie MDM (ustawienia środowiska **uruchomieniowego/miejsce pracy/rejestracje),** aby można było nim zarządzać później.
    1. Nie twórz konta lokalnego
1. [Zastosuj pakiet aprowizowania](hololens-provisioning.md).

W przypadku konfiguracji usługi AAD użytkownicy mogą dzisiaj osiągnąć coś podobnego bez tej zmiany. Urządzenia przyłączone do usługi AAD skonfigurowane do trybu kiosku mogą zalogować się do konta gościa jednym naciśnięciem przycisku na ekranie logowania. Po zalogowaniu się do konta gościa urządzenie nie wyświetli monitu o ponowne zalogowanie, dopóki gość nie zostanie jawnie wylogowany z menu Start lub urządzenie zostanie uruchomione ponownie.

Automatyczne logowanie gościa można zarządzać za pomocą [niestandardowych zasad OMA-URI:](/mem/intune/configuration/custom-settings-windows-10)

- Wartość URI: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Zasady  | Opis   | Konfiguracje  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Umożliwia odwiedzającemu automatyczne logowanie do kiosku   | 1 (Tak), 0 (Nie, wartość domyślna).  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Korzystanie z nowych aplikacji Ustawienia Edge w trybach kiosku

W przypadku do uwzględnienia aplikacji [w kioskach](hololens-kiosk.md)administrator IT często dodaje aplikację do kiosku, ale używając jej identyfikatora modelu użytkownika aplikacji (AUMID). Ponieważ zarówno aplikacja Ustawienia, jak i aplikacja Microsoft Edge są traktowane jako nowe aplikacje i inne niż starsze aplikacje Kioski, które używają identyfikatorów AUMID dla tych aplikacji, należy zaktualizować w celu użycia nowego AUMID.

W przypadku modyfikowania kiosku w celu dodawania nowych aplikacji zalecamy dodanie nowego aumidu do nowego, a także pozostawienie starego. Spowoduje to łatwe przejście, gdy użytkownicy zaktualizują system operacyjny i nie będą musieli otrzymywać nowych zasad, aby nadal korzystać z kiosku w zamierzony sposób.

| Aplikacja                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Stara Ustawienia aplikacji       | HolographicSystemSettings_cw5n1h2txyewy! App            |
| Nowa Ustawienia aplikacji       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
| Stara Microsoft Edge aplikacji | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| Nowa Microsoft Edge aplikacji | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Zmiany zachowania trybu kiosku w celu obsługi awarii

W starszych kompilacjach, jeśli urządzenie miało konfigurację kiosku, która jest kombinacją przypisanego dostępu globalnego i przypisanego do członka grupy usługi AAD, w przypadku określenia, że członkostwo w grupie usługi AAD nie powiodło się, użytkownik zobaczy "nic nie jest wyświetlane w menu[Start".](hololens-kiosk.md#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode)

Począwszy od Windows wersji, środowisko kiosku po awarii w globalnej konfiguracji kiosku (jeśli występuje) w przypadku awarii w trybie kiosku grupy usługi AAD.

### <a name="new-settings-uris-for-page-settings-visibility"></a>Nowe Ustawienia URI dla widoczności Ustawienia stron

Na Windows Holographic w wersji [20H2](hololens-release-notes.md#windows-holographic-version-20h2) dodaliśmy zasady [Ustawienia/PageVisibilityList,](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) aby ograniczyć strony widoczne w Ustawienia aplikacji. PageVisibilityList to zasady, które umożliwiają administratorom IT uniemożliwić widoczność lub dostępność określonych stron w aplikacji System Ustawienia lub na ich użycie dla wszystkich stron z wyjątkiem określonych.

Jeśli odwiedzisz stronę [Ustawienia Widoczność,](settings-uri-list.md)możesz znaleźć instrukcje dotyczące korzystania z tego CSP oraz listę URI dostępnych w poprzednich wersjach.

Rozszerzamy listę dostępnych interfejsów URI, którymi administratorzy IT mogą zarządzać Ustawienia. Niektóre z tych URI są dla nowo dostępnych obszarów w nowej Ustawienia aplikacji. Jeśli używasz zasad Ustawienia/PageVisibilityList, przejrzyj następującą listę i dostosuj dozwolone lub zablokowane strony zgodnie z potrzebami.

> [!NOTE]
> **Przestarzałe: ms-settings:network-proxy**
>
> Jedna strona ustawień jest przestarzała w tych nowszej kompilacji. Stara strona **serwera proxy & sieciowego** nie jest już dostępna jako ustawienie  >   globalne. Nowe ustawienia serwera proxy dla połączenia można znaleźć w obszarze Właściwości sieci **& Sieci**  >  **Wi-Fi** lub Właściwości sieci &  >   **Internet**  >    >  **Ethernet.**

<br>

| Strona Ustawienia                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Funkcje > Apps & Apps                               | `ms-settings:appsfeatures`                         |
| Funkcje > Apps & > zaawansowane          | `ms-settings:appsfeatures-app`                     |
| Mapy > offline                                  | `ms-settings:maps`                                 |
| Mapy > offline > pobieranie map                  | `ms-settings:maps-downloadmaps`                    |
| Urządzenie > myszy                                      | `ms-settings:mouse`                                |
| Urządzenia > USB                                        | `ms-settings:usb`                                  |
| Sieć & Internet > tryb samolotowy                   | `ms-settings:network-airplanemode`                 |
| Zasady ochrony > ogólne                                    | `ms-settings:privacy-general`                      |
| Prywatność > pisma odręcznego & wpisywania personalizacji             | `ms-settings:privacy-speechtyping`                 |
| Ochrona > ruchu                                     | `ms-settings:privacy-motion`                       |
| Granice zrzutów > prywatności                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Zrzuty > i aplikacje dotyczące prywatności                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| System > Battery                                     | `ms-settings:batterysaver`                         |
| System > Battery                                     | `ms-settings:batterysaver-settings`                |
| Dźwięk > systemowego                                       | `ms-settings:sound`                                |
| System > Sound > app volume and device preferences (Wolumin aplikacji i preferencje urządzenia) | `ms-settings:apps-volume`                          |
| System > Sound > Zarządzanie urządzeniami dźwiękowymi              | `ms-settings:sound-devices`                        |
| Konfigurowanie usługi > Storage > Storage Sense         | `ms-settings:storagepolicies`                      |
| Data & > data & czasowa                        | `ms-settings:dateandtime`                          |
| Time & Language > Keyboard                           | `ms-settings:keyboard`                             |
| Time & Language > Language                           | `ms-settings:language`                             |
| Time & Language > Language                           | `ms-settings:regionlanguage-languageoptions`       |
| Aktualizowanie & zabezpieczeń > resetowania & odzyskiwania               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>Zaktualizowane interfejsy URI

Wcześniej następujące dwa identyfikatory URI nie przyjmowałyby użytkownika bezpośrednio do wskazanych stron, ale blokowały tylko główną stronę aktualizacji. Zaktualizowano następujące elementy tak, aby kierowały je do ich stron:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Konfigurowanie diagnostyki powrotu za pomocą Ustawienia aplikacji

Teraz w Ustawienia App użytkownik może skonfigurować zachowanie diagnostyki [rezerwowej](hololens-diagnostic-logs.md). W aplikacji Ustawienia przejdź do strony **Rozwiązywanie** problemów z  ->  **prywatnością,** aby skonfigurować to ustawienie.

> [!NOTE]
> Jeśli dla urządzenia skonfigurowano zasady zarządzania urządzeniami przenośnymi, użytkownik nie będzie mógł przesłonić tego zachowania.  

### <a name="share-things-with-nearby-devices"></a>Udostępnianie rzeczy pobliskim urządzeniem

Udostępniaj rzeczy w pobliżu Windows 10, w tym komputerach i innych urządzeniach HoloLens 2. Możesz ją wypróbować w **użytce Ustawienia** systemowych, aby udostępniać pliki lub adresy URL z HoloLens  ->    ->   na komputerze. Aby uzyskać więcej informacji, przeczytaj więcej na temat sposobu udostępniania rzeczy [pobliskim urządzeniem](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)w Windows 10 .

Tą funkcją można zarządzać za [pośrednictwem opcji Connectivity/AllowConnectedDevices.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)

### <a name="new-os-diagnostic-traces"></a>Nowe ślady diagnostyczne systemu operacyjnego

Oprócz poprzednich funkcji rozwiązywania problemów w aplikacji Ustawienia dodano nowe narzędzie do rozwiązywania problemów wraz z dodaniem nowej aplikacji Ustawienia aktualizacji systemu operacyjnego. Przejdź do **Ustawienia**  ->  **Rozwiązywanie problemów z &amp; zabezpieczeniami aktualizacji**  >  **Windows**  >  **aktualizacji i** wybierz pozycję **Uruchom.** Dzięki temu można zbierać ślady podczas odtwarzania problemu z aktualizacjami systemu operacyjnego, aby pomóc w lepszym rozwiązywaniu problemów z chmurze lub pomocą techniczną.

### <a name="delivery-optimization-preview"></a>Optymalizacja dostarczania zapoznawcza

Dzięki tej HoloLens można Windows Holographic for Business optymalizacji dostarczania w celu zmniejszenia zużycia przepustowości w przypadku pobierania z HoloLens urządzeń. Pełny opis tej funkcji wraz z zalecaną konfiguracją sieci jest dostępny tutaj: Optymalizacja dostarczania [do Windows 10 aktualizacji.](/windows/deployment/update/waas-delivery-optimization)

Następujące ustawienia są włączone w ramach powierzchni zarządzania i [można je skonfigurować z usługi Intune:](/mem/intune/configuration/delivery-optimization-settings)

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Kilka zastrzeżenia dotyczących tej oferty w wersji zapoznawczej:

- HoloLens jest ograniczona w tej wersji zapoznawczej tylko do aktualizacji systemu operacyjnego.
- Windows Holographic for Business obsługuje tylko tryby pobierania HTTP i pobieranie z punktu [końcowego usługi Microsoft Connected Cache ;](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) Tryby pobierania równorzędne i przypisania grup nie są obecnie obsługiwane HoloLens równorzędnych.
- HoloLens nie obsługuje optymalizacji wdrażania ani dostarczania dla Windows Server Update Services końcowych.
- Rozwiązywanie problemów będzie wymagało diagnostyki na serwerze Connected Cache lub zebrania śladu na serwerze HoloLens na HoloLens za pośrednictwem usługi **Ustawienia**  >  **Update & Security**  >   **Troubleshooting** Windows  >   **Update.**

### <a name="it-admin---update-checklist"></a>Administrator IT — lista kontrolna aktualizacji

Ta lista kontrolna pomoże Ci poznać nowe elementy, które są dodawane w tej aktualizacji funkcji, które mogą mieć wpływ na bieżące konfiguracje zarządzania urządzeniami, lub nowe funkcje, których możesz użyć.

#### <a name="updates-to-kiosk-mode"></a>Aktualizacje trybu kiosku

✔️ [**nowe identyfikatory AUMID dla nowych aplikacji w trybie kiosku:**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Jeśli wcześniej używano aplikacji Ustawienia lub Microsoft Edge w kiosku, zastąpiliśmy te aplikacje nowymi aplikacjami, które używają innego identyfikatora aplikacji. Zdecydowanie zachęcamy do przeczytania artykułu [New AUMIDs for new apps in Kiosk mode (Nowe identyfikatory AUMID dla](#use-the-new-settings-and-edge-apps-in-kiosk-modes) nowych aplikacji w trybie kiosku) poniżej. Dzięki temu będziesz nadal mieć aplikację Ustawienia kiosku lub dołączysz nową Microsoft Edge aplikację. Te zmiany można teraz wprowadzać i wdrażać na wszystkich urządzeniach, co pozwala na płynniejsze przechodzenie po aktualizacji.

✔️ automatyczne [**logowanie gościa dla kiosków:**](#visitor-auto-logon-for-kiosks) 

Odwiedzający mogą być teraz automatycznie logni do kiosku. To zachowanie jest domyślnie włączone, ale może być zarządzane i wyłączone.

✔️ błąd [**trybu kiosku:**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Jeśli członkostwo w grupie usługi AAD zalogowanego użytkownika usługi AAD nie zostanie pomyślnie określone, globalna konfiguracja kiosku będzie używana w menu Start (jeśli istnieje). W przeciwnym razie użytkownik będzie prezentowany z pustym menu Start. Puste menu Start nie jest konfiguracją, którą można bezpośrednio ustawić, ale ta nowa obsługa może być czymś, o czym powinien poinformować dział pomocy technicznej, jeśli używasz kiosków, ponieważ może to dotyczyć Twoich konfiguracji lub możesz chcieć wprowadzić nowe korekty w przypisanych konfiguracjach dostępu.

#### <a name="updates-to-page-settings-visibility"></a>Aktualizacje widoczności Ustawienia strony

✔️ nowe [**Ustawienia URI dla widoczności Ustawienia stron**](#new-settings-uris-for-page-settings-visibility)

Jeśli obecnie używasz funkcji [Widoczność Ustawienia](settings-uri-list.md) strony, możesz wprowadzić zmiany istniejących adresów UR, które zostały dozwolone lub zablokowane.

#### <a name="updates-for-your-wdac-policy"></a>Aktualizacje zasad funkcji WDAC
✔️ Jeśli wcześniej blokowano Microsoft Edge za pośrednictwem usługi WDAC, należy zaktualizować zasady WDAC. Przejrzyj poniższe informacje i użyj podanego przykładowego kodu.
#### <a name="enable-new-endpoints-for-edge"></a>Włączanie nowych punktów końcowych dla usługi Edge
✔️ Jeśli masz infrastrukturę, która obejmuje konfigurowanie punktów końcowych sieci, takich jak serwer proxy lub zapora, włącz te nowe punkty końcowe dla nowej Microsoft Edge sieci.

#### <a name="newly-configurable-items"></a>Nowo konfigurowalne elementy

✔️ [diagnostyki rezerwowej:](#configuring-fallback-diagnostics-via-settings-app)można skonfigurować, czy i kto może zbierać dane diagnostyki rezerwowej.

✔️[Udostępnij rzeczy pobliskim urządzeniem:](#share-things-with-nearby-devices)możesz wyłączyć nową funkcję udostępniania w pobliżu.

✔️ [Konfigurowanie ustawień zasad dla nowej Microsoft Edge:](#configuring-policy-settings-for-the-new-microsoft-edge)Przejrzyj nowo dostępne konfiguracje dla Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Nowe narzędzie diagnostyczne

✔️[ślady diagnostyczne nowego](#new-os-diagnostic-traces)systemu operacyjnego: zbieranie dzienników związanych z aktualizacjami systemu operacyjnego.

### <a name="improvements-and-fixes-in-the-update"></a>Ulepszenia i poprawki w aktualizacji:

- [Diagnostyka w](hololens-diagnostic-logs.md#offline-diagnostics) trybie offline będzie również zawierać dodatkowe informacje o urządzeniu dla numeru seryjnego i wersji systemu operacyjnego.
- Rozwiązuje problem dotyczący wdrażania aplikacji biznesowych za pośrednictwem pakietów aprowizowania środowiska uruchomieniowego.
- Rozwiązuje problem z raportowaniem stanu instalacji aplikacji biznesowych.
- Rozwiązano problem z trwałością nowych pakietów aplikacji podczas resetowania urządzenia.
- Rozwiązano problem, który mógł prowadzić do wpisywania nieprawidłowych symboli w programie Edge dla japońskich klientów.
- Zwiększa odporność aktualizacji systemu operacyjnego wokół wstępnie zainstalowanych aplikacji, takich jak Edge. 
- Rozwiązuje problem z niezawodnością aktualizacji, która ma wpływ na instalację Microsoft Edge. 


## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holographic, wersja 20H2 — aktualizacja z maja 2021 r.
- Kompilacja 19041.1146

Ulepszenia i poprawki w aktualizacji:
- Ta comiesięczna aktualizacja jakości nie zawiera żadnych notowalnych zmian. Zachęcamy do wypróbowania naszej najnowszej kompilacji, Windows Holographic, wersja 21H1.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holographic, wersja 1903 — aktualizacja z maja 2021 r.
- Kompilacja 18362.1110

Ulepszenia i poprawki w aktualizacji:
- Ta miesięczna aktualizacja jakości nie zawiera żadnych notowalnych zmian. **Ta kompilacja nie będzie już otrzymywać comiesięcznych aktualizacji usługi.** Zachęcamy do wypróbowania naszej najnowszej kompilacji, Windows Holographic, wersja 21H1.



## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographic, wersja 20H2 — aktualizacja z kwietnia 2021 r.
- Kompilacja 19041.1144

Ulepszenia i poprawki w aktualizacji:

- Rozwiązuje problem z raportowaniem stanu instalacji aplikacji biznesowych.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographic, wersja 1903 — aktualizacja z kwietnia 2021 r.
- Kompilacja 18362.1108

Ulepszenia i poprawki w aktualizacji:

- Rozwiązano problem, który Ustawienia awarii aplikacji podczas próby zmiany hasła dla konta lokalnego.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic, wersja 20H2 — aktualizacja z marca 2021 r.
- Kompilacja 19041.1140

Ulepszenia i poprawki w aktualizacji:

- Klienci korzystający z funkcji AdvancedPhotoCapture lub LowLagPhotoCapture do przechwytywania zdjęć za pomocą urządzenia HoloLens 2 mogą teraz pobierać kamerę w ciągu maksymalnie 3 sekund po przechwyceniu zdjęcia.
- Poprawka przecieku pamięci w usłudze Portal urządzeń Service, który powodował zwiększone użycie pamięci przez usługę, co powodowało niepowodzenie przydzielania pamięci przez inne aplikacje.
- Rozwiązano problem, który oznaczał, że użytkownicy zarejestrowani w etapowym wywłaszczania nie mogli zalogować się na urządzeniu.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, wersja 1903 — aktualizacja z marca 2021 r.
- Kompilacja 18362.1102

Ulepszenia i poprawki w aktualizacji:

- Poprawka przecieku pamięci w usłudze Portal urządzeń Service, który powodował zwiększone użycie pamięci przez usługę, co powodowało niepowodzenie przydzielania pamięci przez inne aplikacje.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, wersja 20H2 — aktualizacja z lutego 2021 r.
- Kompilacja 19041.1136

Ulepszenia i poprawki w aktualizacji:

- Rozwiązuje problem z początkową konfiguracją urządzenia i przechowywaniem aktualizacji aplikacji.
- Rozwiązuje problem z uaktualnieniami i lotami dla HoloLens wersji.
- Usunięto nieużywane wstępnie zainstalowane certyfikaty z głównego magazynu eSIM z HoloLens urządzeń.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, wersja 1903 — aktualizacja z lutego 2021 r.
- Kompilacja 18362.1098

Ta comiesięczna aktualizacja jakości nie zawiera żadnych notowalnych zmian. Zachęcamy do wypróbowania naszych najnowszych kompilacji dla systemu Windows Holographic w wersji 2004.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, wersja 20H2 — aktualizacja ze stycznia 2021 r.
- Kompilacja 19041.1134

Ulepszenia i poprawki w aktualizacji:

- Zwiększona wydajność podczas uruchamiania, wznawiania i przełączania użytkowników, gdy na urządzeniu jest wielu użytkowników.
- Dodano obsługę arm32 dla [trybu badania](/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode).

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, wersja 1903 — aktualizacja ze stycznia 2021 r.
- Kompilacja 18362.1091

Ta comiesięczna aktualizacja jakości nie zawiera żadnych notowalnych zmian. Zachęcamy do wypróbowania naszych najnowszych kompilacji dla systemu Windows Holographic w wersji 2004.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic, wersja 20H2 — aktualizacja z grudnia 2020 r.
- Kompilacja 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Instalowanie aplikacji na HoloLens 2 za pośrednictwem Instalator aplikacji

Dodajemy **nową funkcję (Instalator aplikacji),** aby umożliwić bezproblemowe instalowanie aplikacji na urządzeniach z HoloLens 2. Ta funkcja będzie domyślnie **włączona dla urządzeń nieza pomocą programu**. Aby zapobiec zakłóceniom pracy przedsiębiorstw, instalator aplikacji nie **będzie w** tej chwili dostępny dla zarządzanych urządzeń.  

Urządzenie jest uznawane za "zarządzane", **jeśli** spełnione są dowolne z następujących czynności:
- Zarejestrowane w usłudze ZARZĄDZANIA [urządzeniami przenośnymi](hololens-enroll-mdm.md)
- Skonfigurowano przy użyciu [pakietu aprowizowania](hololens-provisioning.md)
- Tożsamość [użytkownika to](hololens-identity.md) usługa Azure AD

Teraz możesz instalować aplikacje bez konieczności włączania trybu dewelopera ani korzystania z Portal urządzeń.  Po prostu pobierz (za pośrednictwem portu USB lub za pośrednictwem przeglądarki Edge) pakiet Appx na urządzenie i przejdź do pakietu Appx w Eksplorator plików, aby zostać poproszony o rozpoczynanie instalacji.  Alternatywnie [zainicjuj instalację ze strony internetowej](/windows/msix/app-installer/installing-windows10-apps-web).  Podobnie jak aplikacje, które instalujesz z usługi Microsoft Store lub ładować bezpośrednio przy użyciu funkcji wdrażania aplikacji [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) LOB [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) rozwiązania MDM, aplikacje muszą być podpisane cyfrowo przy użyciu narzędzia podpisywania, a certyfikat używany do podpisywania musi być zaufany przez urządzenie HoloLens, zanim będzie można wdrożyć aplikację.

**Instrukcje dotyczące instalacji aplikacji.**

1.  Upewnij się, że urządzenie nie jest uznawane za zarządzane
1.  Upewnij się, HoloLens urządzenie z systemem Windows 2 jest włączone i podłączone do komputera
1.  Upewnij się, że zalogowano się do HoloLens 2
1.  Na komputerze przejdź do aplikacji niestandardowej i skopiuj plik yourapp.appxbundle do katalogu yourdevicename\Internal Storage\Downloads.   Po zakończeniu kopiowania pliku możesz rozłączyć urządzenie
1.  Na urządzeniu HoloLens 2 Otwórz menu Start, wybierz pozycję Wszystkie aplikacje i uruchom Eksplorator plików aplikację.
1.  Przejdź do folderu Pobrane. W lewym panelu aplikacji może być konieczne wybranie najpierw opcji To urządzenie, a następnie przejście do sekcji Pliki do pobrania.
1.  Wybierz plik yourapp.appxbundle.
1.  Zostanie Instalator aplikacji. Wybierz przycisk Zainstaluj, aby zainstalować aplikację.
Zainstalowana aplikacja zostanie automatycznie uruchamiana po zakończeniu instalacji.

Przykładowe aplikacje można znaleźć na [stronie Windows universal samples GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) to test this flow (Przykłady uniwersalne), aby przetestować ten przepływ.

Przeczytaj o pełnym procesie instalowania aplikacji na [HoloLens 2 za pomocą Instalator aplikacji.](app-deploy-app-installer.md)  

![Instalowanie przykładów mrTK za pośrednictwem Instalator aplikacji.](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Ulepszenia i poprawki w aktualizacji:

- Śledzenie rąk obsługuje teraz śledzenie w wielu nowych przypadkach, w których wcześniej zostałaby utracona ręka.  W niektórych z tych nowych przypadków tylko położenie pępka jest nadal aktualizowane na podstawie rzeczywistej ręki użytkownika, podczas gdy drugi jest wywnioskować na podstawie poprzedniej pozycji.  Ta zmiana pomaga zwiększyć spójność śledzenia w ruchach, takich jak slapping, throwing, singing i clapping.  Pomaga również w przypadkach, gdy ręka znajduje się blisko powierzchni lub trzymający obiekt.  W przypadku wywłasznia [](/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) ręki wartość dokładności na maksymalną będzie ustawiona na wartość "Przybliżona", a nie "Wysoka".
- Rozwiązano problem, który pokazywał błąd "Wystąpił problem podczas resetowania numeru PIN dla kont usługi Azure AD.
- Użytkownicy powinni widzieć znacznie mniej awarii OOBE po rozruchu podczas uruchamiania et, irysy z ustawienia aplikacji, nowego użytkownika lub powiadomienia wyskakującego.
- Użytkownicy powinni mieć poprawną strefę czasową wychodzącą z OOBE.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, wersja 1903 — aktualizacja z grudnia 2020 r.
- Kompilacja 18362.1088

Ta comiesięczna aktualizacja jakości nie zawiera żadnych owalnych zmian. Zachęcamy do wypróbowania naszej najnowszej wersji systemu Windows Holographic w wersji 20H2 – aktualizacja z grudnia 2020 r. i nowej funkcji Instalator aplikacji dodanej w kompilacji.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic, wersja 20H2
- Kompilacja 19041.1128

Windows System Holographic w wersji 20H2 jest teraz dostępny i oferuje doskonały zestaw nowych funkcji dla HoloLens 2 użytkowników i specjalistów IT. Od automatycznego pozycjonowania oka, przez Menedżera certyfikatów w Ustawienia, po ulepszone funkcje trybu kiosku i nowe możliwości konfiguracji rozwiązania Autopilot. Ta nowa aktualizacja umożliwia zespołom IT bardziej szczegółową kontrolę nad konfigurowaniem urządzeń HoloLens i zarządzaniem nimi, a także oferuje użytkownikom jeszcze bardziej bezproblemowe środowisko holograficzne. 

Ta najnowsza wersja to comiesięczne aktualizacje do wersji 2004, ale tym razem są dostępne nowe funkcje. Główny numer kompilacji pozostanie taki sam, a Windows Update będzie wskazywać comiesięczne wydanie do wersji 2004 (kompilacja 19041). Możesz sprawdzić numer kompilacji na ekranie informacje Ustawienia >, aby potwierdzić, że używasz najnowszej dostępnej kompilacji 19041.1128+. Aby zaktualizować program do najnowszej wersji, otwórz aplikację Ustawienia, przejdź do & Aktualizacji i naciśnij pozycję Sprawdź aktualizacje. Aby uzyskać więcej informacji na temat zarządzania aktualizacjami HoloLens, odwiedź stronę Manage HoloLens updates (Zarządzanie [HoloLens aktualizacjami).](hololens-updates.md)

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Co nowego w wersji Windows Holographic, wersja 20H2  

| Cecha                                              | Opis                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Obsługa automatycznego położenia oka](hololens-release-notes.md#auto-eye-position-support) | Aktywnie oblicza pozycje oka bez użytkowników przechodzących przez śledzenie oczu.   |
| [Menedżer certyfikatów](hololens-release-notes.md#certificate-manager)   | Umożliwia nowe prostsze metody instalowania i usuwania certyfikatów z Ustawienia aplikacji.     |
| [Automatyczne uruchamianie aprowizowania z dysku USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | Aprowizowanie pakietów na dyskach USB automatycznie wyświetla monit o stronę aprowingu w trybie OOBE.                                                         |
| [Automatyczne potwierdzanie pakietów aprowizowania w OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Pakiety aprowizowania są automatycznie stosowane podczas OOBE ze strony aprowowania.                                                         |
| [Automatyczne aprowizowanie bez użycia interfejsu użytkownika](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Jak połączyć automatyczne uruchamianie aprowizowania i automatyczne potwierdzanie razem. |
| [Używanie rozwiązania Autopilot z Wi-Fi połączenia](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Używaj rozwiązania Autopilot z poziomu Wi-Fi bez konieczności używania karty Ethernet. |
| [Tenantlockdown CSP and Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Po zarejestrowaniu dzierżawy i zastosowaniu zasad urządzenie może zostać zarejestrowane w tej dzierżawie tylko za każdym razem, gdy urządzenie zostanie zresetowane lub ponownie flashowane. |
| [Dostęp przypisany globalnie](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Nowa metoda konfiguracji dla trybu kiosku z wieloma aplikacjami, która stosuje kiosk na poziomie systemu, dzięki czemu ma zastosowanie do wszystkich.                  |
| [Automatyczne uruchamianie aplikacji w kiosku z wieloma aplikacjami](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Ustawia automatyczne uruchamianie aplikacji podczas logowania się w trybie kiosku z wieloma aplikacjami.                                                        |
| [Zmiany zachowania trybu kiosku w celu obsługi błędów](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Awaria trybu kiosku ma teraz restrykcyjny tryb rezerwowy.                                                                                                |
| [HoloLens Zasady działalności](hololens-release-notes.md#hololens-policies)                                    | Nowe zasady dla HoloLens.     |
| [Buforowanie członkostwa w grupie usługi Azure AD dla kiosku w trybie offline](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | Nowe zasady umożliwiają użytkownikom używanie pamięci podręcznej członkostwa w grupach do korzystania z trybu kiosku w trybie offline przez ustawioną liczbę dni.                                        |
| [Nowe zasady ograniczeń urządzeń dla HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Zasady zarządzania urządzeniami włączono nowo włączone dla HoloLens 2.                                                                                |
| [Nowe zasady zasilania dla HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Nowo obsługiwane zasady ustawień limitu czasu zasilania.  |
| [Aktualizowanie zasad](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Nowo włączone zasady umożliwiające kontrolę nad aktualizacjami.           |
| [Włączono Ustawienia strony dla HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Zasady służące do wyboru stron widocznych w Ustawienia aplikacji.             |
| [Tryb badań](hololens-release-notes.md#research-mode) | Korzystanie z trybu badania w HoloLens 2. |
| [Zwiększona długość rejestrowania](hololens-release-notes.md#recording-length-increased) | Nagrania MRC nie są już ograniczone do 5 minut. |
| [Ulepszenia i poprawki w aktualizacji](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Dodatkowe poprawki w aktualizacji.   |

### <a name="auto-eye-position-support"></a>Obsługa automatycznego położenia oka

W HoloLens 2 położenia oczu umożliwiają dokładne pozycjonowanie hologramów, wygodne środowisko wyświetlania i lepszą jakość wyświetlania. Pozycje oka są obliczane wewnętrznie w ramach obliczeń śledzenia wzroku. Jednak wymaga to, aby każdy użytkownik przechodził przez śledzenie wzroku, nawet wtedy, gdy środowisko może nie wymagać danych wejściowych spojrzenia oczu.

**Funkcja Auto Eye Position (AEP)** umożliwia tym scenariuszom bez interakcji obliczanie pozycji oczu dla użytkownika. Funkcja Auto Eye Position automatycznie zacznie działać w tle od momentu, w którym użytkownik umieści urządzenie. Jeśli użytkownik nie ma wcześniejszego śledzenia wzroku, funkcja Auto Eye Position zacznie dostarczać użytkownikowi pozycje oczu do systemu wyświetlania po czasie przetwarzania 20–30 sekund. Dane użytkownika nie są utrwalane na urządzeniu, dlatego ten proces jest powtarzany, jeśli użytkownik wystartuje i ponownie uruchomi urządzenie lub jeśli urządzenie zostanie ponownie uruchomiony lub wznowiony po uśpieniu.

Istnieje kilka zmian zachowania systemu za pomocą funkcji automatycznego położenia oka, gdy na urządzeniu jest umieszczany nieskalibrowany użytkownik. W tym kontekście użytkownik nieskalowany odnosi się do kogoś, kto wcześniej nie przeszedł przez proces śledzenia wzroku na urządzeniu.

| Aktywna aplikacja | Wcześniejsze zachowanie | Zachowanie z Windows Holographic, aktualizacja w wersji 20H2 |
|:-------------------|:-----------------|:-----------------------------------|
| Aplikacja bez obsługi spojrzenia lub powłoka Holographic Shell |Zostanie wyświetlone okno dialogowe monitu o śledzenie wzroku. | Monit nie jest wyświetlany. |
| Aplikacja z obsługą spojrzenia | Zostanie wyświetlone okno dialogowe monitu o śledzenie wzroku. | Monit o śledzenie wzroku jest wyświetlany tylko wtedy, gdy aplikacja uzyskuje dostęp do strumienia oczu. |

Jeśli użytkownik przechodzi z aplikacji z włączoną obsługą spojrzenia do aplikacji, która uzyskuje dostęp do danych spojrzenia, zostanie wyświetlony monit o podanie monitu. 

Wszystkie inne zachowania systemu będą podobne do zachowania bieżącego użytkownika, który nie ma aktywnej kontroli wzroku. Na przykład gest Uruchamiania jednym ręki nie zostanie włączony. Nie będzie żadnych zmian w out-of-box-experience dla konfiguracji początkowej.

W przypadku doświadczeń wymagających danych o spojrzeniu lub bardzo precyzyjnego pozycjonowania hologramu zalecamy użytkownikom nieskalicznym uruchamianie śledzenia wzroku. Jest on dostępny z monitu o śledzenie wzroku lub przez uruchomienie aplikacji Ustawienia z menu Start, a następnie wybranie pozycji **System > Wyniszcz wzrokowy >** i > oczu.

Te informacje można znaleźć później z innymi [informacjami o incydowaniu.](hololens-calibration.md#auto-eye-position-support) 

### <a name="certificate-manager"></a>Menedżer certyfikatów

- Ulepszono narzędzia do inspekcji, diagnostyki i weryfikacji zabezpieczeń i zgodności urządzeń za pośrednictwem nowego Menedżera certyfikatów. Ta funkcja umożliwi wdrażanie, rozwiązywanie problemów i weryfikowanie certyfikatów na dużą skalę w środowiskach komercyjnych.

W Windows Holographic w wersji 20H2 dodajemy Menedżera certyfikatów w aplikacji HoloLens 2 Ustawienia aplikacji. Przejdź do **Ustawienia > Update & Security > Certificates**. Ta funkcja zapewnia prosty i przyjazny dla użytkownika sposób wyświetlania, instalowania i usuwania certyfikatów na urządzeniu. Dzięki nowej funkcji Menedżer certyfikatów administratorzy i użytkownicy mają teraz ulepszone narzędzia inspekcji, diagnostyki i walidacji, aby zapewnić, że urządzenia pozostaną bezpieczne i zgodne. 

-   **Inspekcja:** Możliwość zweryfikowania, czy certyfikat został wdrożony poprawnie, lub potwierdzenia, że został on odpowiednio usunięty. 
-   **Diagnostyka:** W przypadku problemów podczas sprawdzania, czy na urządzeniu istnieją odpowiednie certyfikaty, oszczędzasz czas i pomagasz w rozwiązywaniu problemów. 
-   **Walidacja:** Sprawdzenie, czy certyfikat służy zamierzony cel i jest funkcjonalny, może zaoszczędzić dużo czasu, szczególnie w środowiskach komercyjnych przed wdrożeniem certyfikatów na większą skalę.

Aby szybko znaleźć określony certyfikat na liście, dostępne są opcje sortowania według nazwy, magazynu lub daty wygaśnięcia. Użytkownicy mogą również bezpośrednio wyszukiwać certyfikat. Aby wyświetlić właściwości poszczególnych certyfikatów, wybierz certyfikat i kliknij pozycję **Informacje.** 

Instalacja certyfikatu obsługuje obecnie pliki cer i crt. Właściciele urządzeń mogą instalować certyfikaty na komputerze lokalnym i bieżącym użytkowniku;  Wszyscy inni użytkownicy mogą instalować tylko w programie Current User. Użytkownicy mogą usuwać tylko certyfikaty zainstalowane bezpośrednio z interfejsu Ustawienia użytkownika. Jeśli certyfikat został zainstalowany za pośrednictwem innych środków, należy go również usunąć za pomocą tego samego mechanizmu.

#### <a name="to-install-a-certificate"></a>Aby zainstalować certyfikat: 

1.  Połączenie komputer HoloLens 2.
1.  Umieść plik certyfikatu, który chcesz zainstalować, w lokalizacji na komputerze HoloLens 2.
1.  Przejdź do **Ustawienia App > Update & Security > Certificates**(Zaktualizuj certyfikaty > Security >) i wybierz pozycję Install a certificate (Zainstaluj certyfikat).
1.  Kliknij **pozycję Importuj** plik i przejdź do lokalizacji, w którym zapisano certyfikat.
1.  Wybierz **pozycję Store Location (Lokalizacja sklepu).**
1.  Wybierz **pozycję Magazyn certyfikatów.**
1.  Kliknij przycisk **Zainstaluj**.

Certyfikat powinien być teraz zainstalowany na urządzeniu.

#### <a name="to-remove-a-certificate"></a>Aby usunąć certyfikat: 
1. Przejdź do **Ustawienia App > Update i Security > Certificates**.
1. Wyszukaj certyfikat według nazwy w polu wyszukiwania.
1. Wybierz certyfikat.
1. Kliknij pozycję **Usuń.**
1. Po **wyświetleniu** monitu o potwierdzenie wybierz pozycję Tak.

![Przeglądarka certyfikatów w Ustawienia aplikacji.](images/certificate-viewer-device.jpg)

![Obraz przedstawiający sposób instalowania certyfikatu przy użyciu interfejsu użytkownika certyfikatu.](images/certificate-device-install.jpg)

Te informacje można znaleźć później [na nowej stronie Menedżera certyfikatów.](certificate-manager.md)

### <a name="auto-launch-provisioning-from-usb"></a>Automatyczne uruchamianie aprowizowania z dysku USB

- Zautomatyzowane procesy, które pozwalają na mniejszą interakcję z użytkownikiem, gdy dyski USB z pakietami aprowizowania są używane podczas OOBE.

Przed wydaniem użytkownicy musieli ręcznie uruchomić ekran aprowizowania podczas OOBE, aby aprowizować przy użyciu kombinacji przycisków. Teraz użytkownicy mogą pominąć kombinację przycisków przy użyciu pakietu aprowizowania na dysku pamięci USB. 

1. Podłącz dysk USB za pomocą pakietu aprowizowania podczas pierwszej interakcji ZOBE
1. Gdy urządzenie będzie gotowe do aprowizowania, automatycznie otworzy monit ze stroną aprowizowania. 

Uwaga: Jeśli dysk USB jest podłączony do zasilania podczas rozruchu urządzenia, system OOBE wylicza istniejące urządzenie magazynujące USB, a także będzie obserwować dodatkowe podłączone urządzenia.

Aby uzyskać więcej informacji na temat stosowania pakietów aprowizowania podczas OOBE, odwiedź dokumentację [HoloLens aprowizowania.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Dodatkowe informacje na [temat aprowizowania automatycznego](hololens-provisioning.md#auto-launch-provisioning-from-usb) uruchamiania z dysku USB można znaleźć w dokumentacji HoloLens aprowizowania.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Automatyczne potwierdzanie pakietów aprowizowania w OOBE
- Zautomatyzowany proces umożliwiający mniejszą interakcję z użytkownikiem, gdy zostanie wyświetlona strona Pakiet aprowizowania, automatycznie zastosuje wszystkie wymienione pakiety.

Gdy pojawi się ekran główny aprowizowania, OOBE odliczy 10 sekund przed automatyczne rozpoczęcie stosowania wszystkich pakietów aprowizowania. Użytkownicy mogą nadal [potwierdzić lub anulować](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) w ciągu tych 10 sekund po zweryfikowaniu oczekiwanych pakietów.

### <a name="automatic-provisioning-without-using-ui"></a>Automatyczna aprownia bez użycia interfejsu użytkownika
- Połączone procesy automatyczne w celu zmniejszenia interakcji z urządzeniami w celu aprowacji. 

Łącząc automatyczne uruchamianie aprowizowania z urządzeń USB i automatyczne potwierdzanie pakietów aprowizowania, użytkownik może automatycznie aprowizować urządzenia z systemem HoloLens 2 bez użycia interfejsu użytkownika urządzenia, a nawet jego nazwy. Możesz nadal używać tego samego dysku USB i pakietu aprowizowania dla wielu urządzeń. Jest to przydatne w przypadku wdrażania wielu urządzeń jednocześnie w tym samym obszarze. 

1. [Utwórz pakiet aprowizowania przy](hololens-provisioning.md) [użyciu Windows Configuration Designer.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Skopiuj pakiet na dysk pamięci MASOWEJ USB.
1. [Flash your HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) to [19041.1361 or newer build ( Flash your HoloLens 2 to 19041.1361 or newer build ( Flash your HoloLens 2 do 19041.1361 lub nowszej kompilacji).](https://aka.ms/hololens2previewdownload) 
1. Po [zakończeniu flashowania](https://www.microsoft.com/store/productId/9P74Z35SFRS8) urządzenia przez program Advanced Recovery Companion odłącz kabel USB-C. 
1. Podłącz dysk USB do urządzenia.
1. Po uruchomieniu HoloLens 2 urządzenia OOBE automatycznie wykryje pakiet aprowizowania na dysku USB i uruchomi stronę aprowizowania.
1. Po upływie 10 sekund urządzenie automatycznie zastosuje pakiet aprowizowania. 

Urządzenie jest teraz skonfigurowane i zostanie na tym [ekranie wyświetlany ekran Provisioning Successful (Aprowizowanie powiodło się).](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### <a name="using-autopilot-with-wi-fi-connection"></a>Używanie rozwiązania Autopilot z Wi-Fi połączenia
- Usunięto potrzebę adapterów USB-C w celu zmniejszenia potrzeb sprzętowych przez włączenie rozwiązania Autopilot do Wi-Fi połączonych urządzeń.

Teraz podczas OOBE po nawiązać HoloLens 2 z siecią Wi-Fi, OOBE będzie sprawdzać profil rozwiązania Autopilot dla urządzenia. Jeśli zostanie znaleziony, zostanie on użyty do ukończenia pozostałej części przepływu dołączania do i rejestracji w UAD. Innymi słowy, używanie sieci Ethernet do portu USB-C lub Wi-Fi adaptera USB-C nie jest już wymagane, jednak nadal działają, jeśli zostały podane na początku OOBE. Dowiedz się więcej na [temat rozwiązania Autopilot dla HoloLens 2.](hololens2-autopilot.md)

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP and Autopilot
- Utrzymuje urządzenia w dzierżawie organizacji, blokując je do dzierżawy nawet za pomocą resetowania urządzenia lub reflash. Z dalszymi zabezpieczeniami przez odmówienie tworzenia konta w programie za pośrednictwem aprowizowania. 

HoloLens 2 obsługują teraz usługę TenantLockdown CSP od [Windows Holographic w wersji 20H2.](hololens-release-notes.md#windows-holographic-version-20h2) 

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) Zasady CSP umożliwiają HoloLens 2 z rejestracją MDM tylko przy użyciu rozwiązania Autopilot. Gdy w węźle RequireNetworkInOOBE w programie TenantLockdown dla węzła RequireNetworkInOOBE zostanie ustawiona wartość true lub false (początkowo ustawiona) na HoloLens 2, ta wartość pozostanie na urządzeniu pomimo ponownego flashowania, aktualizacji systemu operacyjnego itp. 

Gdy węzeł RequireNetworkInOOBE dostawcy CSP TenantLockdown zostanie ustawiony na wartość true w wersji HoloLens 2, obiekt OOBE czeka przez czas nieokreślony na pomyślne pobranie i zastosowanie profilu rozwiązania Autopilot po napięciu łączności sieciowej. 

Gdy dla węzła RequireNetworkInOOBE dla węzła RequireNetworkInOOBE dla węzła TenantLockdown zostanie ustawiona wartość true HoloLens 2, następujące operacje są niedozwolone w OOBE: 
- Tworzenie użytkownika lokalnego przy użyciu aprowizowania środowiska uruchomieniowego 
- Wykonywanie operacji dołączania do usługi Azure AD za pośrednictwem aprowizowania środowiska uruchomieniowego 
- Wybieranie, kto jest właścicielem urządzenia w środowisko OOBE 

#### <a name="how-to-set-this-using-intune"></a>Jak to ustawić przy użyciu usługi Intune? 
1. Utwórz niestandardowy profil konfiguracji urządzenia OMA URI i określ wartość true dla węzła RequireNetworkInOOBE, jak pokazano poniżej.
Wartość OMA-URI powinna mieć wartość ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Ustawianie blokady czasowej za pośrednictwem OMA-URI.](images/hololens-tenant-lockdown.png)

1. Utwórz grupę i przypisz profil konfiguracji urządzenia do tej grupy urządzeń. 

1. Dokonaj synchronizacji HoloLens 2 urządzenia w grupie utworzonej w poprzednim kroku.  

Sprawdź w portalu usługi Intune, czy konfiguracja urządzenia została pomyślnie zastosowana. Po pomyślnym zastosowaniem tej konfiguracji urządzenia HoloLens 2 efekty ustawienia TenantLockdown będą aktywne.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Jak w usłudze Intune w HoloLens 2 wyebrać usługę RequireNetworkInOOBE HoloLens TenantLockdown? 
1. Usuń HoloLens 2 z grupy urządzeń, do której wcześniej przypisano konfigurację urządzenia utworzoną powyżej. 

1. Utwórz niestandardowy profil konfiguracji urządzenia oparty na adresie URI OMA i określ wartość false dla wartości RequireNetworkInOOBE, jak pokazano poniżej. Wartość OMA-URI powinna mieć wartość ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Zrzut ekranu przedstawiający ustawianie wartości false dla ustawienia RequireNetworkInOOBE za pośrednictwem adresu URI OMA w usłudze Intune.](images/hololens-tenant-lockdown-false.png)

1. Utwórz grupę i przypisz profil konfiguracji urządzenia do tej grupy urządzeń.

1. Dokonaj synchronizacji HoloLens 2 urządzenia w grupie utworzonej w poprzednim kroku.

Sprawdź w portalu usługi Intune, czy konfiguracja urządzenia została pomyślnie zastosowana. Po pomyślnym zastosowaniem tej konfiguracji urządzenia na HoloLens 2 skutki ustawienia TenantLockdown będą nieaktywne.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Co się stanie podczas OOBE, jeśli profil rozwiązania Autopilot zostanie nieprzypisany na HoloLens gdy ustawienie TenantLockdown zostanie ustawione na wartość true? 
Funkcja OOBE będzie przez czas nieokreślona czekać na pobranie profilu rozwiązania Autopilot. Zostanie wyświetlone następujące okno dialogowe. Aby usunąć skutki blokady dzierżawy, urządzenie musi zostać najpierw zarejestrowane w pierwotnej dzierżawie przy użyciu rozwiązania Autopilot, a opcja RequireNetworkInOOBE musi zostać nieskonkcedyowana zgodnie z opisem w poprzednim kroku przed usunięciem ograniczeń wprowadzonych przez usługę TenantLockdown CSP.

![Widok w urządzeniu dla sytuacji, gdy zasady są wymuszane na urządzeniu.](images/hololens-autopilot-lockdown.png)

Te informacje można teraz znaleźć obok pozostałej części rozwiązania Autopilot w obszarze [Tenantlockdown CSP and Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)(Dzierżawablokuje CSP i Autopilot).

### <a name="global-assigned-access--kiosk-mode"></a>Dostęp przypisany globalnie — tryb kiosku
- Zredukowano zarządzanie tożsamościami dla kiosku, włączając nową metodę kiosku, która stosuje tryb kiosku na poziomie systemu.

Ta nowa funkcja umożliwia administratorowi IT skonfigurowanie urządzenia z systemem HoloLens 2 dla wielu trybów kiosku aplikacji, które ma zastosowanie na poziomie systemu, nie ma koligacji z żadną tożsamością w systemie i ma zastosowanie do wszystkich użytkowników, którzy się na nim inserują. Przeczytaj szczegółowo o tej nowej funkcji w [trybie HoloLens kiosku.](hololens-kiosk.md)

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Automatyczne uruchamianie aplikacji w trybie kiosku z wieloma aplikacjami 
- Ukierunkowane doświadczenie z automatycznym uruchamianiem aplikacji, co dodatkowo zwiększa wybór interfejsu użytkownika i aplikacji wybranych dla trybu kiosku.

Dotyczy tylko trybu kiosku z wieloma aplikacjami i tylko 1 aplikacja może zostać wyznaczona do automatycznego uruchamiania przy użyciu wyróżnienia atrybutu poniżej w konfiguracji przypisanego dostępu.

Aplikacja jest uruchamiana automatycznie po sięgniecie użytkownika.

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Zmiany zachowania trybu kiosku w celu obsługi awarii
- Bezpieczniejszy tryb kiosku dzięki wyeliminowaniu dostępnych aplikacji w przypadku awarii trybu kiosku. 

Wcześniej w przypadku napotkania błędów podczas stosowania trybu kiosku HoloLens do pokazywania wszystkich aplikacji w menu Start. Teraz w Windows Holographic w wersji 20H2 w przypadku awarii żadne aplikacje nie będą wyświetlane w menu Start, jak pokazano poniżej:

![Obraz trybu kiosku wygląda teraz w przypadku awarii.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens Zasady działalności

- Opcje zarządzania urządzeniami przeznaczone specjalnie HoloLens do zarządzania urządzeniem. 

Utworzono nowe zasady rzeczywistości mieszanej dla urządzeń HoloLens 2 na Windows Holographic w wersji 20H2. Nowe ustawienia z możliwością kontrolowania obejmują: ustawianie jasność, ustawianie głośności, wyłączanie rejestrowania dźwięku w przechwytywaniu rzeczywistości mieszanej, ustawianie czasu zbierania danych diagnostycznych oraz pamięć podręczną członkostwa w grupach usługi AAD.  

| Nowe HoloLens zasad                                | Opis                                                                               | Uwagi                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Umożliwia wyłączone przyciski jasność, więc naciśnięcie jej nie zmienia jasność.       | 1 Tak, 0 Nie (ustawienie domyślne)                                                |
| MixedReality\VolumeButtonDisabled                  | Umożliwia wyłączone przyciski regulacji głośności, więc naciśnięcie jej nie zmienia głośności.               | 1 Tak, 0 Nie (ustawienie domyślne)                                                |
| MixedReality\MicrophoneDisabled                    | Wyłącza mikrofon, aby nie było możliwe nagrywanie dźwięku HoloLens 2.                      | 1 Tak, 0 Nie (ustawienie domyślne)                                                |
| MixedReality\FallbackDiagnostics                   | Steruje zachowaniem funkcji zbierania dzienników diagnostycznych.                               | 0 Wyłączone, 1 włączone dla właścicieli urządzeń, 2 włączone dla wszystkich (ustawienie domyślne) |
| MixedReality\HeadTrackingMode                      | Zarezerwowane do użytku w przyszłości.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Określa, ile dni pamięci podręcznej członkostwa grupy usługi Azure AD jest używana w przypadku grup usługi Azure AD przeznaczonych dla kiosku. | Sprawdź poniżej.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Buforowanie członkostwa w grupie usługi Azure AD dla kiosku w trybie offline
- Włączono kioski offline do użytku z grupami usługi AAD przez maksymalnie 60 dni.

Ta zasada określa, ile dni może być używana pamięć podręczna członkostwa grupy usługi Azure AD w konfiguracjach przypisanego dostępu przeznaczonych dla grup usługi Azure AD dla zalogowanych użytkowników. Gdy ta wartość zasad jest ustawiona na wartość większą niż 0, pamięć podręczna jest używana w przeciwnym razie.  

Nazwa: Wartość URI AADGroupMembershipCacheValidityInDays: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min. – 0 dni  
Maks. — 60 dni 

Kroki poprawnego używania tych zasad: 
1. Utwórz profil konfiguracji urządzenia dla grup usługi Azure AD przeznaczony dla kiosku i przypisz go do HoloLens urządzeń. 
1. Utwórz niestandardową konfigurację urządzenia opartą na URI OMA, która ustawia tę wartość zasad na żądaną liczbę dni (> 0) i przypisz ją do HoloLens urządzeń. 
    1. Wartość URI powinna zostać wprowadzona w polu tekstowym OMA-URI jako ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. Dozwolona wartość może być minimalna/maksymalna.
1. Zarejestruj HoloLens urządzeń i sprawdź, czy obie konfiguracje są stosowane do urządzenia. 
1. Pozwól użytkownikowi usługi Azure AD 1 zalogować się, gdy internet jest dostępny, po pomyślnym zalogowaniu użytkownika i pomyślnym potwierdzeniu członkostwa w grupie usługi Azure AD zostanie utworzona pamięć podręczna. 
1. Teraz użytkownik 1 usługi Azure AD może prze HoloLens trybu offline i używać go w trybie kiosku, o ile wartość zasad zezwala na X liczbę dni. 
1. Kroki 4 i 5 można powtórzyć dla każdego innego użytkownika usługi Azure AD N. Kluczową punktem tutaj jest to, że każdy użytkownik usługi Azure AD musi zalogować się do urządzenia przy użyciu Internetu, aby co najmniej raz ustalić, że jest on członkiem grupy usługi Azure AD, do której jest ukierunkowana konfiguracja kiosku. 
 
> [!NOTE]
> Dopóki krok 4 nie zostanie wykonany dla użytkownika usługi Azure AD, wystąpi awaria wymieniona w środowiskach "odłączonych". 

### <a name="new-device-restriction-policies-for-hololens-2"></a>Nowe zasady ograniczeń urządzeń dla HoloLens 2
- Umożliwia użytkownikom zarządzanie określonymi zasadami zarządzania urządzeniami, takimi jak blokowanie dodawania lub usuwania pakietów aprowizowania.

Nowo włączone zasady, które umożliwiają więcej opcji zarządzania HoloLens 2 urządzeń. 
- [AllowAddProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [Konfigurowanie strefy czasowej](/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](/windows/client-management/mdm/remotelock-csp)

Te dwie nowe zasady dla pakietów AllowAddProvisioningPackage i AllowRemoveProvisioningPackage są dodawane do naszych typowych [ograniczeń dotyczących urządzeń.](hololens-common-device-restrictions.md)

> [!NOTE]
> W odniesieniu do [funkcji RemoteLock](/windows/client-management/mdm/remotelock-csp)HoloLens tylko konfigurację ./Vendor/MSFT/RemoteLock/Lock. Konfiguracje związane z kodem PIN, takie jak resetowanie i odzyskiwanie, nie są obsługiwane.

### <a name="new-power-policies-for-hololens-2"></a>Nowe zasady zasilania dla HoloLens 2
- Więcej opcji dla sytuacji, HoloLens uśpienia lub blokady za pośrednictwem zasad zasilania. 

Te nowo dodane zasady umożliwiają administratorom kontrolowanie stanów zasilania, takich jak limit czasu bezczynności. Aby dowiedzieć się więcej na temat poszczególnych zasad, kliknij link dla tych zasad.

|     Link do dokumentacji zasad                |     Uwagi                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Przykładowa wartość do użycia w Windows Configuration Designer, tj.`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Przykładowa wartość do użycia w Windows Configuration Designer, tj.`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Przykładowa wartość do użycia w Windows Configuration Designer, tj. 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Przykładowa wartość do użycia w Windows Configuration Designer, tj. 100                                                                          |
|     [StandbyTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Przykładowa wartość do użycia w Windows Configuration Designer, tj.`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Przykładowa wartość do użycia w Windows Configuration Designer, tj.`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Te dwie nowe zasady dla usług DisplayOffTimeoutOnBattery i DisplayOffTimeoutPluggedIn są dodawane do naszych typowych [ograniczeń dotyczących urządzeń.](hololens-common-device-restrictions.md)

> [!NOTE]
> Aby zapewnić spójne środowisko w HoloLens 2, upewnij się, że wartości dla właściwości DisplayOffTimeoutOnBattery i StandbyTimeoutOnBattery są ustawione jako taką samą wartość. To samo dotyczy funkcji DisplayOffTimeoutPluggedIn i StandbyTimeoutPluggedIn. Aby uzyskać więcej informacji na temat [nowoczesnego wstrzymania,](/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) zobacz Wyświetlanie, uśpienie i hibernacja czasomierzy bezczynnych.

### <a name="newly-enabled-update-policies-for-hololens"></a>Nowo włączone zasady aktualizacji dla HoloLens
- Więcej opcji instalacji aktualizacji lub wyłączenia przycisku Wstrzymaj aktualizacje w celu zapewnienia aktualizacji.

Te zasady aktualizacji są teraz włączone na HoloLens 2:
-   [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Szczegółowe informacje na temat tych zasad aktualizacji i sposobu ich używania dla urządzeń HoloLens można znaleźć tutaj w te HoloLens [aktualizacji.](hololens-updates.md)

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>Włączono Ustawienia strony dla HoloLens 2
- Zwiększona kontrola interfejsu użytkownika w Ustawienia, co może być mylone z wyświetlaniem ograniczonego wyboru stron.

Włączyliśmy zasady, które umożliwiają administratorom IT uniemożliwić widoczność lub dostępność określonych stron w aplikacji System Ustawienia lub na ich użycie dla wszystkich stron z wyjątkiem określonych. Aby dowiedzieć się, jak w pełni dostosować tę funkcję, kliknij poniższy link.

- [PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Aby dowiedzieć się, które ustawienia strony można dostosować w HoloLens 2, odwiedź naszą Ustawienia [URI.](settings-uri-list.md) 
 
![Zrzut ekranu przedstawiający modyfikację godzin aktywnego Ustawienia aplikacji.](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Tryb badań
W trybie badań komputer HoloLens 2 staje się narzędziem do badania obrazów. W porównaniu z poprzednimi wersjami tryb badania dla HoloLens 2 ma następujące zalety:
-   Oprócz czujników dostępnych w trybie badań HoloLens (1. generacji), teraz zapewniamy dostęp do czujników IMU, w tym przyspieszeniomierza, gyroscope i akcelerometru.
-   HoloLens 2 udostępnia nowe możliwości, których można używać razem z trybem badania. W szczególności dostęp do określonych interfejsów API do śledzenia rąk i śledzenia oczu, które mogą dostarczać bogatszy zestaw eksperymentów.

Badacze mają teraz możliwość włączenia trybu badań na urządzeniach HoloLens, aby uzyskać dostęp do wszystkich tych strumieni zewnętrznych czujników nieprzetworzonych obrazów. Tryb badań dla HoloLens 2 zapewnia również dostęp do akcelerometru, żyrometru i odczytów akcelerometrów. Aby chronić prywatność użytkowników, nieprzetworzone obrazy kamer śledzące wzrok nie są dostępne za pośrednictwem trybu badania, ale kierunek spojrzenia jest dostępny za pośrednictwem istniejących interfejsów API.

Zapoznaj się z [dokumentacją trybu badań,](/windows/mixed-reality/research-mode) aby uzyskać więcej informacji technicznych.

### <a name="recording-length-increased"></a>Długość rejestrowania zwiększona
Dzięki opiniom klientów zwiększyliśmy długość rejestrowania przechwytywania [rzeczywistości mieszanej.](holographic-photos-and-videos.md) Przechwytywanie rzeczywistości mieszanej nie będzie domyślnie ograniczone do 5 minut, ale zamiast tego obliczy maksymalną długość rejestrowania na podstawie dostępnego miejsca na dysku. Urządzenie oszacowa maksymalny czas trwania nagrywania wideo na podstawie dostępnego miejsca na dysku do 80% całkowitego miejsca na dysku.

> [!NOTE]
> W HoloLens będzie używać domyślnej długości rejestrowania wideo (5 minut), jeśli wystąpi jedna z następujących sytuacji:
> - Szacowany maksymalny czas trwania rejestrowania jest mniejszy niż domyślne 5 minut.
> - Dostępne miejsce na dysku jest mniejsza niż 20% całkowitego miejsca na dysku.

Pełne wymagania można znaleźć w naszej dokumentacji [dotyczącej zdjęć i filmów wideo](holographic-photos-and-videos.md#maximum-recording-length) na urządzeniach holograficznych. 

### <a name="improvements-and-fixes-in-the-update"></a>Ulepszenia i poprawki w aktualizacji:
- Więcej ekranów w trybie OOBE jest teraz w trybie ciemnym.
- Więcej informacji powinno wskazać najnowsze zasady zachowania poufności informacji w trybie online.
- Rozwiązano problem, który nie pozwalał użytkownikom aprowizować profilów sieci VPN za pośrednictwem pakietów aprowizowania.
- Rozwiązano problem z konfiguracją serwera proxy dla połączenia sieci VPN.
- Zaktualizowano zasady, aby wyłączyć wyliczanie funkcji USB za pośrednictwem funkcji MDM dla NCM dla AllowUsbConnection.
- Rozwiązano problem, który uniemożliwiał wyświetlanie urządzenia HoloLens w uciece Eksplorator plików za pośrednictwem protokołu MTP (Media Transfer Protocol), gdy urządzenie jest ustawione jako kiosk z jedną [aplikacją.](hololens-kiosk.md) Należy pamiętać, że usługę MTP (i ogólnie połączenie USB) można wyłączyć przy użyciu [zasad AllowUSBConnection.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
- Rozwiązano problem, który pozwalał na poprawne skalowanie ikon menu Start w trybie kiosku.
- Rozwiązano problem z buforowaniem HTTP zakłócanym przez tryb kiosku skierowany do grup usługi Azure AD.
- Rozwiązano problem, który mógł dotyczyć użytkowników, którzy nie mogli używać przycisku Parowanie po włączeniu trybu dewelopera z pakietami aprowizowania, chyba że wyłączyli i ponownie włączyli tryb dewelopera.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic, wersja 1903 — aktualizacja z listopada 2020 r.
- Kompilacja 18362.1085

Ta comiesięczna aktualizacja jakości nie zawiera żadnych notowalnych zmian. Zachęcamy do wypróbowania najnowszej kompilacji wydania funkcji na Windows Holographic w wersji 20H2.

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows Holographic, wersja 2004 — aktualizacja z października 2020 r.
- Kompilacja 19041.1124
 
Ulepszenia i poprawki w aktualizacji:

- Usunięto niepotrzebne sprawdzanie, które powodowało błąd systemu środowiska uruchomieniowego.

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows Holographic, wersja 1903 — aktualizacja z października 2020 r.
- Kompilacja 18362.1081

Ta comiesięczna aktualizacja jakości nie zawiera żadnych notowalnych zmian. Zachęcamy do wypróbowania naszych najnowszych kompilacji dla systemu Windows Holographic w wersji 2004.

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows Holographic, wersja 2004 — aktualizacja z września 2020 r.
- Kompilacja 19041.1117

Ulepszenia i poprawki w aktualizacji:

- Rozwiązuje problem, który uniemożliwiał Visual Studio debugowania aplikacji, gdy element SupportsMultipleInstances="true" występuje w pliku appxmanifest.
- Ta wersja zawiera poprawkę wykrywania serwera proxy NCSI w celu rozwiązania problemu z niepowodzeniem wykrywania Internetu za pośrednictwem serwera proxy sieci. Usługa NCSI może używać serwera proxy maszyny i serwera proxy dla profilu do wykrywania łączności z Internetem. W przyszłej wersji serwer proxy dla 1 użytkownika będzie obsługiwany przez interfejs NCSI.
- Na większości Windows Mixed Reality wektor kierunku do przodu jest równoległy do ziemi, gdy głowy użytkownika jest w pozycji neutralnej w przód. Jednak wcześniejsze wersje HoloLens 2 wyrównały wektor do paneli wyświetlania, które są pochylony w dół o kilka stopni w stosunku do idealnej orientacji. W nowszej wersji HoloLens 2 rozwiązano ten problem, aby zapewnić spójność semantyczną między kształtami.
- Ulepszona niezawodność śledzenia rąk, która spowoduje mniejszą liczbę strat śledzenia w określonych scenariuszach.
- Ta wersja zawiera poprawkę poprawiającą jakość znaczników czasu dźwięku, która może mieć wpływ na problemy z przechwytywaniem wideo.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, wersja 1903 — aktualizacja z września 2020 r.
- Kompilacja 18362.1079

Ulepszenia i poprawki w aktualizacji:

- Na większości Windows Mixed Reality wektor kierunku do przodu jest równoległy do ziemi, gdy głowy użytkownika jest w pozycji neutralnej w przód. Jednak wcześniejsze wersje HoloLens 2 wyrównały wektor do paneli wyświetlania, które są pochylony w dół o kilka stopni w stosunku do idealnej orientacji. W nowszej wersji HoloLens 2 rozwiązano ten problem, aby zapewnić spójność semantyczną między kształtami.
- Ulepszona niezawodność śledzenia rąk, która spowoduje mniejszą liczbę strat śledzenia w określonych scenariuszach.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, wersja 2004 — aktualizacja z sierpnia 2020 r.
- Kompilacja 19041.1113

Ulepszenia i poprawki w aktualizacji:

- Ustawienia nie będzie już śledzić użytkownika w doświadczeniach z rejestracją irysów ani śledzeniem oczu.
- Usunięto usterkę, która oznaczała, że zastosowanie pakietu aprowizowania podczas OOBE, który zmienia nazwę urządzenia i wykonuje inne akcje (takie jak łączenie się z siecią), nie może wykonać innych akcji po ponownym uruchomieniu urządzenia z powodu zmiany nazwy.
- Zmodyfikowano schemat kolorów początkowych przepływów konfiguracji urządzenia, aby poprawić jakość wizualizacji.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic, wersja 1903 — aktualizacja z sierpnia 2020 r.
- Kompilacja 18362.1074

Ta comiesięczna aktualizacja jakości nie zawiera żadnych notowalnych zmian. Zachęcamy do wypróbowania naszych najnowszych kompilacji dla systemu Windows Holographic w wersji 2004.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic, wersja 2004 — aktualizacja z lipca 2020 r.
- Kompilacja 19041.1109

Ulepszenia i poprawki w aktualizacji:

- Deweloperzy mogą teraz wybierać między włączaniem i wyłączaniem Portal urządzeń wymagać bezpiecznego połączenia.
- Poprawiono niezawodność uruchamiania aplikacji po aktualizacjach systemu operacyjnego.
- Zmieniono domyślną jasność skrzynki odbiorczej na 100 procent.
- Rozwiązano problem z przekazywaniem HTTPS dla Windows Portal urządzeń na HoloLens 2.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic, wersja 1903 — aktualizacja z lipca 2020 r.
- Kompilacja 18362.1071

Ulepszenia i poprawki w aktualizacji:

- Rozwiązano problem, który mógł powodować zniknięcie hologramów w aplikacjach unity podczas utraty lub odzyskania śledzenia.
- Rozwiązano problem, który powodował, że aplikacje HoloLens ulegały awarii z powrotem do powłoki podczas używania HoloLens Emulator z przyspieszania sprzętowego na niektórych urządzeniach.
- Rozwiązano problem dotyczący przekazywania HTTPS dla Windows Portal urządzeń na HoloLens 2.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic, wersja 2004 — aktualizacja z czerwca 2020 r.
- Kompilacja 19041.1106

Ulepszenia i poprawki w aktualizacji:

- Niestandardowe rejestratory MRC mają teraz nowe wartości domyślne dla niektórych właściwości, jeśli nie zostały określone.
  - W przypadku *efektu wideo MRC:*
    - PreferredOgramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (immersyjny zestaw nagłowny))
  - W przypadku *efektu dźwięku MRC:*
    - LoopbackGain (bieżąca wartość "Zysk dźwięku aplikacji" na stronie Przechwytywanie rzeczywistości mieszanej w Windows Portal urządzeń)
    - MicrophoneGain (bieżąca wartość "Zysk dźwięku mikrofonu" na stronie Przechwytywanie rzeczywistości mieszanej w Windows Portal urządzeń)
- Usunięto usterkę w celu poprawy jakości dźwięku w scenariuszach przechwytywania rzeczywistości mieszanej. W szczególności ta poprawka powinna wyeliminować błędy audio podczas rejestrowania podczas **wyświetlania** menu Start.
- Ulepszona stabilność hologramów w zarejestrowanych filmach wideo.
- Rozwiązano problem, który mógł dotyczyć sytuacji, w której przechwytywanie rzeczywistości mieszanej nie mogło nagrać wideo po tym, jak urządzenie było w stanie wstrzymania przez wiele dni.
- Interfejs API HolographicSpace.UserPresence jest zwykle wyłączony dla aplikacji unity. Takie zachowanie pozwala uniknąć problemu, który powodował, że niektóre aplikacje były wstrzymywane po przerzuceniu funkcji odszybłej, nawet jeśli ustawienie "uruchom w tle" zostało włączone. Interfejs API jest teraz włączony dla aparatu Unity w wersji 2018.4.18 i nowszych oraz 2019.3.4 i nowszych.
- Gdy uzyskujesz dostęp Portal urządzeń za pośrednictwem Wi-Fi, przeglądarka internetowa może uniemożliwić dostęp z powodu nieprawidłowego certyfikatu. Przeglądarka może zgłosić błąd, taki jak "ERR_SSL_PROTOCOL_ERROR", nawet jeśli certyfikat urządzenia był wcześniej zaufany. W takim przypadku nie można przejść do Portal urządzeń, ponieważ nie ma opcji ignorowania ostrzeżeń zabezpieczeń. Ta aktualizacja rozwiązała problem. Jeśli certyfikat urządzenia został wcześniej pobrany i zaufany na komputerze w celu usunięcia ostrzeżeń o zabezpieczeniach przeglądarki, a wystąpi błąd protokołu SSL, nowy certyfikat musi zostać pobrany i zaufany, aby rozwiązać problem z ostrzeżeniami o zabezpieczeniach przeglądarki.
- Włączono możliwość tworzenia pakietu aprowizowania środowiska uruchomieniowego, który może instalować aplikację przy użyciu pakietów MSIX.
- Dodano ustawienie w **Ustawienia**  >  **System** Hologramy, które umożliwia użytkownikom automatyczne usuwanie wszystkich hologramów Mixed Reality domu po  >   zamknięciu urządzenia.
- Rozwiązano problem, który powodował, HoloLens, które zmieniają format pikseli na czarny w HoloLens emulatorze.
- Usunięto usterkę, która powodowała awarię podczas logowania irysów.
- Rozwiązano problem z wielokrotnym pobieraniem ze sklepu dla już bieżących aplikacji.
- Usunięto usterkę uniemożliwiającą wielokrotne otwieranie aplikacji Microsoft Edge immersyjnej.
- Rozwiązano problem z uruchamianiem aplikacji Zdjęcia podczas początkowych uruchomień po aktualizacji z wersji 1903.
- Zwiększona wydajność i niezawodność.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic, wersja 1903 — aktualizacja z czerwca 2020 r.
- Kompilacja 18362.1064

Ulepszenia i poprawki w aktualizacji:

- Niestandardowe rejestratory MRC mają nowe wartości domyślne dla niektórych właściwości, jeśli nie zostały określone.
  - W przypadku *efektu wideo MRC:*
    - PreferredOgramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (immersyjny zestaw nagłowny))
  - W przypadku *efektu dźwięku MRC:*
    - LoopbackGain (bieżąca wartość "Zysk dźwięku aplikacji" na stronie Przechwytywanie rzeczywistości mieszanej w Windows Portal urządzeń)
    - MicrophoneGain (bieżąca wartość "Zysk dźwięku mikrofonu" na stronie Przechwytywanie rzeczywistości mieszanej w Windows Portal urządzeń)
- Interfejs API HolographicSpace.UserPresence jest zwykle wyłączony dla aplikacji unity. Takie zachowanie pozwala uniknąć problemu, który powoduje, że niektóre aplikacje są wstrzymywane po przerzuceniu funkcji odszybłej, nawet jeśli ustawienie do uruchomienia w tle jest włączone. Interfejs API jest teraz włączony dla aparatu Unity w wersji 2018.4.18 i nowszych oraz 2019.3.4 i nowszych.
- Rozwiązano problem, który powodował, HoloLens, które zmieniły format pikseli na czarny w HoloLens Emulator.
- Rozwiązano problem z uruchamianiem aplikacji Zdjęcia podczas początkowych uruchomień po aktualizacji z wersji 1903.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, wersja 2004  
- Kompilacja — 19041.1103

Główna aktualizacja oprogramowania dla systemu HoloLens 2, Windows Holographic w wersji *2004* z maja 2020 r. obejmuje wiele nowych, interesujących funkcji, takich jak obsługa rozwiązania Windows Autopilot, tryb ciemny aplikacji, obsługa interfejsu USB Ethernet dla hotspotów 5G/LTE i wiele innych. Aby zaktualizować program do najnowszej wersji, otwórz aplikację **Ustawienia,** przejdź do opcji Update & Security i wybierz przycisk Sprawdź    **** **aktualizacje.**   

|             Cecha                              |          Opis                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Wstępne konfigurowanie i bezproblemowe konfigurowanie nowych urządzeń do produkcji przy użyciu rozwiązania Windows AutoPilot                 |
|       Obsługa fido 2                             |          Obsługa kluczy zabezpieczeń FIDO2 w celu umożliwienia szybkiego i bezpiecznego uwierzytelniania dla urządzeń udostępnionych            |
|       Ulepszono aprowizowanie                      |          Bezproblemowe stosowanie pakietu aprowizowania z dysku USB do urządzenia HoloLens                              |
|       Stan instalacji aplikacji                 |          Sprawdzanie stanu instalacji w aplikacji Ustawienia dla aplikacji zostało wypchniętą do usługi HoloLens 2 za pośrednictwem rozwiązania MDM               |
|       Dostawcy usług konfiguracji (CSP)   |          Dodano nowych dostawców usług konfiguracji w celu zwiększenia możliwości kontroli administracyjnej                 |
|       Obsługa usb 5G/LTE                       |          Rozszerzona funkcja ethernetu USB umożliwia obsługę sieci 5G/LTE                                    |
|       Tryb ciemnej aplikacji                              |          Tryb ciemny aplikacji dostępny dla aplikacji, które obsługują tryb ciemny i jasny, co poprawia środowisko wyświetlania        |
|       Polecenia głosowe                             |          Obsługa dodatkowych systemowych poleceń głosowych do sterowania HoloLens bez rąk                           |
|       Ulepszenia śledzenia rąk                 |          Ulepszenia śledzenia rąk sprawiają, że przyciski i interakcje z planszą 2D są dokładniejsze                        |
|       Ulepszenia i poprawki dotyczące jakości                 |          Różne ulepszenia wydajności i niezawodności systemu na platformie                            |

### <a name="support-for-windows-autopilot"></a>Obsługa rozwiązania Windows Autopilot

Windows Funkcja Autopilot HoloLens 2 umożliwia wstępne zarejestrowanie kanału sprzedaży urządzenia HoloLens dzierżawie usługi Intune. Po przybyciu urządzenia są gotowe do samodzielnego wdrożenia jako urządzenia udostępnione w ramach dzierżawy. Aby skorzystać z funkcji samodzielnego wdrażania, urządzenie musi połączyć się z siecią podczas pierwszego ekranu w konfiguracji przy użyciu połączenia USB-C-to-Ethernet.

Gdy użytkownik rozpocznie proces samodzielnego wdrażania rozwiązania Autopilot, proces ten kończy następujące kroki:

1. Dołącz urządzenie do usługi Azure Active Directory (Azure AD).
1. Użyj usługi Azure AD, aby zarejestrować urządzenie w Microsoft Intune (lub innej usłudze MDM).
1. Pobierz zasady, certyfikaty i profile sieciowe dla urządzeń docelowych.
1. Aprowizuj urządzenie.
1. Przedstawianie użytkownikowi ekranu logowania.

Dowiedz się więcej z [przewodnika Windows autopilot dla programu HoloLens 2.](hololens2-autopilot.md)

*Skontaktuj się z menedżerem ds. konta, aby teraz dołączyć do wersji zapoznawczej rozwiązania AutoPilot. Wkrótce rozpocznie się wysyłanie urządzeń gotowych do rozwiązania Autopilot.*

### <a name="fido2-security-key-support"></a>Obsługa klucza zabezpieczeń FIDO2

Niektórzy użytkownicy współdzielą urządzenie HoloLens z innymi w środowisku służbowym. Dlatego ważne jest, aby użytkownicy z łatwością wpisywali długie nazwy użytkowników i hasła. Usługa Fast Identity Online (FIDO) umożliwia wszystkim osobom w organizacji (dzierżawie usługi Azure AD) bezproblemowe logowanie do usługi HoloLens bez wprowadzania nazwy użytkownika lub hasła.

Klucze zabezpieczeń FIDO2 to metoda uwierzytelniania bez hasła oparta na standardach "unphishable", która może mieć dowolną formę. FIDO to otwarty standard uwierzytelniania bez hasła. Dzięki temu użytkownicy i organizacje mogą logować się do swoich zasobów bez nazwy użytkownika ani hasła. Zamiast tego używają zewnętrznego klucza zabezpieczeń lub klucza platformy wbudowanego w urządzenie.

Aby rozpocząć pracę, zobacz Włączanie logowania za pomocą klucza [zabezpieczeń bez hasła.](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Ulepszona rejestracja mdm za pośrednictwem pakietu aprowizowania

Pakiety aprowizowania umożliwiają HoloLens konfiguracji za pośrednictwem pliku konfiguracji, a nie HoloLens za pośrednictwem dostępnego w tym celu programu . Wcześniej pakiety aprowizowania były kopiowane do HoloLens pamięci wewnętrznej. Teraz mogą one być na dysku USB, dzięki czemu można łatwiej używać ich ponownie na wielu urządzeniach HoloLens i można aprowizować urządzenia równolegle. Pakiety aprowizowania obsługują teraz również pole do rejestrowania w zarządzaniu urządzeniami, dzięki czemu nie ma ręcznej konfiguracji po aprowiwizowania.

Aby wypróbować ten sposób:

1. Pobierz najnowszą wersję programu Windows Configuration Designer ze sklepu Windows na komputer.
1. Wybierz **pozycję Provision HoloLens Devices Provision** HoloLens 2 devices (Aprowizuj urządzenia HoloLens  >  **2 urządzeniach).**
2. Skompilowanie profilu konfiguracji. Następnie skopiuj wszystkie utworzone pliki na urządzenie magazynujące USB-C.
3. Podłącz urządzenie USB-C do dowolnego nowo flashowanych HoloLens. Następnie naciśnij przyciski **zasilania regulacji**  +  **głośności,** aby zastosować pakiet aprowizowania.

### <a name="line-of-business-application-install-status"></a>Stan instalacji aplikacji biznesowych

Wdrażanie aplikacji MDM i zarządzanie nimi w aplikacjach biznesowych ma kluczowe znaczenie dla HoloLens. Administratorzy i użytkownicy muszą wyświetlić stan instalacji aplikacji na potrzeby inspekcji i diagnostyki. W tej wersji dodaliśmy więcej szczegółów w te Ustawienia Dostęp do konta służbowego  >    >    >  **Kliknij pozycję Informacje o** swoim  >  **koncie.**

### <a name="additional-csps-and-policies"></a>Dodatkowi CSP i zasady

Dostawca [usług konfiguracji (CSP)](/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) to interfejs do odczytywania, konfigurowania, modyfikowania lub usuwania ustawień konfiguracji na urządzeniu. W tej wersji dodajemy obsługę większej liczby zasad w celu zwiększenia kontroli nad wdrożoną kontrolą HoloLens urządzeń. Aby uzyskać listę CSP obsługiwanych przez HoloLens, zobacz [NetworkQoSPolicy CSP (NetworkQoSPolicy CSP).](/windows/client-management/mdm/networkqospolicy-csp)

Nowość w tej wersji:

**Dostawca CSP zasad** 

Dostawca usługi konfiguracji zasad umożliwia przedsiębiorstwu konfigurowanie zasad na Windows urządzeniach. W tej wersji dodaliśmy nowe zasady dla HoloLens, które są wymienione tutaj. Aby dowiedzieć się więcej, zobacz Policy CSPs supported by HoloLens 2 (Zasady [CSP obsługiwane przez HoloLens 2).](/windows/client-management/mdm/policies-supported-by-hololens2)  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps 
- LetAppsAccessGazeInput 
- LetAppsAccessGazeInput_ForceAllowTheseApps 
- LetAppsAccessGazeInput_ForceDenyTheseApps 
- LetAppsAccessGazeInput_UserInControlOfTheseApps 
- LetAppsAccessMicrophone_ForceAllowTheseApps 
- LetAppsAccessMicrophone_ForceDenyTheseApps 
- LetAppsAccessMicrophone_UserInControlOfTheseApps 
- AllowWiFi 

**NetworkQoSPolicy CSP**

Dostawca usługi konfiguracji NetworkQoSPolicy tworzy zasady jakości usług (QoS) sieci. Zasady QoS wykonuje zestaw akcji dla ruchu sieciowego na podstawie zestawu pasujących warunków. Aby dowiedzieć się więcej, zobacz [NetworkQoSPolicy CSP (NetworkQoSPolicy CSP).](/windows/client-management/mdm/networkqospolicy-csp)

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>Rozszerzona obsługa ethernetu USB dla urządzeń z połączeniami 5G/LTE

Dodano obsługę włączania niektórych mobilnych urządzeń bezprzewodowych, takich jak telefony 5G/LTE i hotspoty Wi-Fi, gdy są one podłączone do sieci HoloLens 2 za pośrednictwem portu USB. Te urządzenia są teraz wyświetlane w **ustawieniach sieciowych jako** inne połączenie Ethernet. (Mobilne urządzenia komórkowe, które wymagają sterownika zewnętrznego, nie są obsługiwane). Ta funkcja umożliwia połączenia o wysokiej przepustowości, Wi-Fi nie jest dostępna, Wi-Fi tethering nie jest wystarczająco performantny. Aby dowiedzieć się więcej o obsługiwanych urządzeniach USB, zobacz Połączenie do Bluetooth [i USB-C.](hololens-connect-devices.md)  

### <a name="hand-tracking-improvements"></a>Ulepszenia śledzenia rąk

Ta wersja zawiera kilka ulepszeń śledzenia rąk:

- **Punktowanie stabilności pozycji:** System opiera się teraz palcem wskazującym, gdy zostanie przycięty przez rąbek. Ta zmiana zwiększa dokładność przycisków wypychania, wpisywania, przewijania zawartości i nie tylko. 
- **Mniejsze przypadkowe naciśnięcia w powietrzu:** Ulepszyliśmy wykrywanie gestu naciśnięcia w powietrzu. Teraz istnieje mniej przypadkowych aktywacji w kilku typowych scenariuszach, takich jak po upuszczenie rąk na boki.
- **Niezawodność przełącznika użytkownika:** System jest teraz szybszy i bardziej niezawodny podczas aktualizowania rozmiaru ręki podczas udostępniania urządzenia.
- **Ograniczona liczba kradzieży rąk:** Ulepszyliśmy obsługę przypadków, w których czujniki mają więcej niż dwie dłonie. Jeśli wiele osób pracuje blisko siebie, istnieje teraz znacznie mniejsze prawdopodobieństwo, że śledzona ręka "przeskoczy" z użytkownika do ręki kogoś innego w scenie.
- **Niezawodność systemu:** Rozwiązano problem, który powodował, że śledzenie rąk przestało działać, gdy urządzenie jest pod dużym obciążeniem.

### <a name="dark-mode"></a>Tryb ciemny

Wiele Windows obsługuje teraz tryb ciemny i jasny. HoloLens 2 użytkownicy mogą wybrać tryb domyślny dla aplikacji, które obsługują oba te ustawienia. Po aktualizacji domyślny tryb aplikacji jest "ciemny", ale można łatwo zmienić to ustawienie: Przejdź do Ustawienia kolorów systemowych Wybierz  >    >    >  **domyślny tryb aplikacji.** 

Te "w skrzynki" aplikacje obsługują tryb ciemny: 

- Ustawienia 
- Sklepie Microsoft 
- Mail 
- Kalendarz 
- Eksplorator plików 
- Centrum opinii 
- OneDrive 
- Zdjęcia 
- Przeglądarka 3D 
- Filmy & TV 

![Okna trybu ciemnego kafelkowane.](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Systemowe polecenia głosowe

Teraz możesz używać poleceń głosowych z dowolną aplikacją na urządzeniu. Aby uzyskać więcej informacji, zobacz [Używanie głosu do obsługi HoloLens](hololens-cortana.md). Zobacz również [obsługiwane języki dla HoloLens 2.](hololens2-language-support.md)  

### <a name="cortana-updates"></a>Cortana aktualizacji

Zaktualizowana aplikacja integruje się z Microsoft 365, aby ułatwić ci pracę na różnych urządzeniach (obecnie tylko US-English). W HoloLens 2 Cortana już nie obsługuje niektórych poleceń specyficznych dla urządzenia, takich jak dostosowywanie głośności lub ponowne uruchamianie. Te opcje są teraz obsługiwane przez nowe systemowe polecenia głosowe. Dowiedz się więcej o nowej Cortana aplikacji w naszym [blogu.](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)

### <a name="quality-improvements-and-fixes"></a>Ulepszenia i poprawki dotyczące jakości

Ulepszenia i poprawki również w aktualizacji:  
- Wprowadzono aktywny system natłoków wyświetlania. Ta funkcja poprawia stabilność i wyrównanie hologramów. Teraz pozostają one na miejscu, gdy przenosisz łb z boku na bok.
- Usunięto usterkę, która Wi-Fi przesyłania strumieniowego do HoloLens okresowo zakłócana. Jeśli aplikacja wskazuje, że wymaga przesyłania strumieniowego z małym opóźnieniem, zaimplikuj poprawkę, wywołując funkcję [SetSocketMediaStreamingMode](/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Rozwiązano problem z zawieszaniem się urządzenia, które wystąpiło podczas przesyłania strumieniowego w trybie badania.
- Usunięto usterkę, która w niektórych przypadkach pokazywała, że właściwy użytkownik nie był wyświetlany na ekranie logowania podczas wznawiania sesji.
- Rozwiązano problem, który umożliwiał użytkownikom eksportowanie dzienników zarządzania urządzeniami przenośnymi za **pośrednictwem Ustawienia**.
- Rozwiązano problem, który miał miejsce, gdy dokładność śledzenia oczu natychmiast po instalacji out-of-box mogła być niższa niż oczekiwano.
- Rozwiązano problem, który dotyczył sytuacji, w której podsystem śledzenia oczu nie zainicjował lub nie przeszedł operacji orzeł w określonych warunkach.
- Rozwiązano problem, który oznaczał, że monitowany był monit o już skalibrowany użytkownik.
- Rozwiązano problem, który miał miejsce, gdy sterownik ulegał awarii podczas awarii wzroku.
- Rozwiązano problem, który mógł powodować powtarzające się naciśnięcia przycisku zasilania, co mogło spowodować 60-sekundowy limit czasu systemu i awarię powłoki.
- Zwiększona stabilność buforów głębokości.
- Dodano **przycisk Udostępnij** w Centrum opinii, aby użytkownicy mogą łatwiej udostępniać opinie.
- Usunięto usterkę, przez która program RoboRaid nie był poprawnie instalowany.

### <a name="known-issues"></a>Znane problemy

- Problem z językiem systemowym zh-CN uniemożliwia poleceń głosowych przechwytywanie rzeczywistości mieszanej lub wyświetlanie adresu IP urządzenia.
- Problem wymaga uruchomienia aplikacji Cortana po uruchomieniu urządzenia w celu używania aktywacji głosowej "Hej Cortana". Jeśli kompilacja została zaktualizowana z kompilacji 18362, może być również wyświetlony drugi kafelek aplikacji dla poprzedniej wersji aplikacji Cortana, która nie działa już w **startie**.

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, wersja 1903 — aktualizacja z maja 2020 r. 
- Kompilacja 18362.1061

Ta comiesięczna aktualizacja jakości nie zawiera żadnych notowalnych zmian, ponieważ zespół pracował nad aktualizacją systemu Windows Holographic w wersji 2004 May Update, zgodnie z wcześniejszym opisem.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, wersja 1903 — aktualizacja z kwietnia 2020 r.
- Kompilacja 18362.1059

**Tryb ciemny dla obsługiwanych aplikacji** 

Wiele Windows obsługuje tryb ciemny i jasny. HoloLens 2 klienci mogą teraz wybrać tryb domyślny dla aplikacji, które obsługują oba schematy kolorów. Na podstawie opinii klientów ustawiamy domyślny tryb aplikacji na "ciemny", ale możesz łatwo zmienić to ustawienie w dowolnym momencie: Przejdź do opcji **Ustawienia > System > Colors** (Wybierz domyślny tryb **aplikacji).**

Te "w box" aplikacje obsługują tryb ciemny:
- Ustawienia
- Sklepie Microsoft
- Mail
- Kalendarz
- Eksplorator plików
- Centrum opinii
- OneDrive
- Zdjęcia
- Przeglądarka 3D
- Filmy & TV

**Ulepszenia i poprawki także w aktualizacji:** 
- Upewniliśmy się, że nakładki powłoki są uwzględniane w przechwytywaniach rzeczywistości mieszanej.
- Deweloperzy unreal mogą teraz używać strony widoku 3D w Portal urządzeń do testowania i debugowania swoich aplikacji.
- Poprawiono stabilność hologramów w przechwytywaniu rzeczywistości mieszanej w przypadku korzystania z algorytmu *HolographicDepthReprojectionMethod DepthReprojection.*
- Naprawiono błąd "Klasa interfejsu API WinRT IStreamSocketListener nie jest zarejestrowana" w 32-bitowych aplikacjach ARM.

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows Holographic, wersja 1903 — aktualizacja z marca 2020 r. 
- Kompilacja 18362.1056

Ulepszenia i poprawki w aktualizacji:

- Ulepszona stabilność hologramów w przechwytywaniu rzeczywistości mieszanej w przypadku korzystania z *algorytmu HolographicDepthReprojectionMethod AutoPlanar.*
- Upewniliśmy się, że układ współrzędnych dołączony do próbki mf głębokości jest zgodny z publiczną dokumentacją.
- Zwiększona produktywność deweloperów dzięki umożliwieniu klientom wklejania dużych ilości tekstu za pośrednictwem portalu urządzenia.

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows Holographic, wersja 1903 — aktualizacja z lutego 2020 r. 
- Kompilacja 18362.1053

Ulepszenia i poprawki w aktualizacji:

- Tymczasowo wyłączono interfejs API HolographicSpace.UserPresence dla aplikacji unity. Ta zmiana pozwala uniknąć problemu, który powodował, że niektóre aplikacje były wstrzymywane po przerzuceniu funkcji odszybłej, nawet jeśli ustawienie "uruchom w tle" zostało włączone.
- Usunięto losową awarię HUP spowodowaną przez śledzenie rąk, w której użytkownik zauważył zablokowanie interfejsu użytkownika, a następnie powrót do powłoki po kilku sekundach.
- Ulepszono śledzenie rąk, dzięki czemu podczas przesuwania palcem wskazującym górna część tego palca jest mniej prawdopodobne nieoczekiwanego zwinięcia.
- Zwiększona niezawodność śledzenia głowy, mapowania przestrzennego i innych środowisk uruchomieniowych.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic, wersja 1903 — aktualizacja ze stycznia 2020 r. 
- Kompilacja 18362.1043
 
Ulepszenia i poprawki w aktualizacji:

- Ulepszona stabilność dla aplikacji wyłącznych podczas pracy z HoloLens 2.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic, wersja 1903 — aktualizacja z grudnia 2019 r. 
- Kompilacja 18362.1042

Ulepszenia i poprawki w aktualizacji:

- Wprowadzono poprawki dotyczące odtwarzania ostatniego etapu (LSR). Ulepszone renderowanie wizualizacji hologramów, aby wydawać się bardziej stabilne i bardziej szczegółowe, dzięki dokładniejszemu ewidencjonowania ich głębokości. Ten objaw będzie bardziej zauważalny po tej aktualizacji, jeśli aplikacje nie ustawią poprawnie głębokości hologramów.
- Poprawiono stabilność aplikacji wyłącznych i nawigację między aplikacjami wyłączności.
- Rozwiązano problem, który mógł dotyczyć sytuacji, w której przechwytywanie rzeczywistości mieszanej nie mogło nagrać wideo, gdy urządzenie było w stanie wstrzymania przez kilka dni.
- Ulepszona stabilność hologramów.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic, wersja 1903 — aktualizacja z listopada 2019 r. 
- Kompilacja 18362.1039

Ulepszenia i poprawki w aktualizacji:

- Naprawiono funkcjonalność poleceń **Select** voice podczas początkowej konfiguracji dla en-CA i en-AU.
- Ulepszona jakość wizualna obiektów umieszczonych daleko w najnowszych wersjach aparatu Unity Mixed Reality Toolkit (MRTK).
- Rozwiązano problemy z blokowaniem aplikacji holograficznych w stanie wstrzymania podczas uruchamiania do momentu menu Start, a następnie zamknięcia.
- Poprawki i ulepszenia zgodności środowiska uruchomieniowego OpenXR dla HoloLens 2 i emulatora.
