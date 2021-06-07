---
title: Informacje o wersji urządzenia HoloLens 2
description: Bądź na bieżąco ze wszystkimi aktualizacjami w każdej nowej wersji urządzenia HoloLens 2.
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 02/16/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 554dc796ee793a3f7e81108c6eb614a9555f10d7
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378409"
---
# <a name="hololens-2-release-notes"></a>Informacje o wersji urządzenia HoloLens 2

Aby zapewnić wydajną pracę z urządzeniami HoloLens, kontynuujemy wydanie funkcji, usterek i aktualizacji zabezpieczeń. Na tej stronie możesz zobaczyć, co nowego dla urządzenia HoloLens w każdym miesiącu. Aby uzyskać najnowszą aktualizację urządzenia HoloLens 2, możesz sprawdzić aktualizacje i ręcznie zaktualizować lub pobrać pełną aktualizację flash (FFU), aby flashować urządzenie za pomocą narzędzia [Advanced Recovery Companion.](hololens-recovery.md#clean-reflash-the-device) [](hololens-update-hololens.md#check-for-updates-and-manually-update) Pobieranie [jest](https://aka.ms/hololens2download) aktualne i udostępnia najnowszą ogólnie dostępną kompilację.

## <a name="windows-holographic-version-21h1"></a>Windows Holographic, wersja 21H1
- Kompilacja 20346.1002

Ta aktualizacja zawiera funkcje dla dwóch docelowych odbiorców. funkcje, z których każdy może korzystać na urządzeniu przez użytkownika końcowego, oraz nowe opcje zarządzania urządzeniami, które mogą być konfigurowane przez administratorów IT. W poniższej tabeli przedstawiono funkcje, które są istotne dla poszczególnych odbiorców. Jeśli jesteś administratorem IT, zapoznaj się z naszą listą kontrolną [administratorów IT — aktualizacja.](#it-admin---update-checklist)
>[!IMPORTANT]
>Aby można było zaktualizować tę kompilację, urządzenia HoloLens 2 muszą być aktualnie uruchomione z aktualizacją z lutego 2021 r. (kompilacja 19041.1136) lub nowszą. Jeśli ta aktualizacja funkcji nie jest dostępna, zaktualizuj najpierw urządzenie i spróbuj ponownie.

>[!NOTE]
>Obecnie program Microsoft HoloLens 2 obsługuje comiesięczne aktualizacje obsługi (poprawki usterek i zabezpieczeń) dla następujących wersji:
>- Windows Holographic, wersja 20H2 (kompilacja 19041.1128+)
>- Windows Holographic, wersja 2004 (kompilacja 19041.1103+)
>- Windows Holographic, wersja 1903 (kompilacja 18362+) 
>
> Wraz z wprowadzeniem systemu Windows Holographic w wersji 21H1 zaprzestajemy comiesięcznych aktualizacji obsługi systemu Windows Holographic w wersji **1903.** Dzięki temu możemy skupić się na najnowszych wersjach i nadal dostarczać cenne ulepszenia. 


| Nazwa funkcji                                              | Krótki opis                                                                      | Docelowej | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [Nowe Microsoft Edge](#introducing-the-new-microsoft-edge)  | Nowa wersja oparta na Microsoft Edge Chromium jest teraz dostępna dla urządzenia HoloLens 2. | Użytkownik końcowy | 
[WebXR i 360 Viewer](#webxr-and-360-viewer) | Wypróbuj immersywne środowiska internetowe i odtwarzanie 360 wideo. | Użytkownik końcowy | 
[Nowa aplikacja Ustawienia](#new-settings-app) | Starsza aplikacja Ustawienia jest zastępowana przez zaktualizowaną wersję nowymi funkcjami i ustawieniami. | Użytkownik końcowy |
[Wyświetlanie kolorowania](#display-color-calibration) | Wybierz alternatywny profil kolorów dla ekranu urządzenia HoloLens 2. | Użytkownik końcowy |
[Domyślny s wyboru aplikacji](#default-app-picker) | Wybierz aplikację, która ma być uruchamiana dla każdego typu pliku lub linku. | Użytkownik końcowy |
[Kontrola głośności dla aplikacji](#per-app-volume-control) | Kontroluj wolumin na poziomie aplikacji niezależnie od woluminu systemowego. | Użytkownik końcowy |
[Instalowanie aplikacji internetowych](#install-web-apps) | Zainstaluj aplikacje internetowe na urządzeniach HoloLens 2, takich jak Microsoft Office, przy użyciu nowej Microsoft Edge przeglądarki. | Użytkownik końcowy |
[Szybkie przesunięcie do typu](#swipe-to-type) | Użyj wierzchołka palca, aby "szybko przesunąć" wyrazy na klawiaturze holograficznej. | Użytkownik końcowy |
[Menu Zasilania z menu Start](#power-menu-from-start) | W menu Start uruchom ponownie i zamknij urządzenie HoloLens. | Użytkownik końcowy |
[Wielu użytkowników na liście na ekranie Logowania](#multiple-users-listed-on-sign-in-screen) | Wyświetlanie wielu kont użytkowników na ekranie Logowanie. | Użytkownik końcowy |
[Obsługa mikrofonu zewnętrznego USB-C](#usb-c-external-microphone-support) | Używaj mikrofonów USB-C dla aplikacji i/lub funkcji Remote Assist. | Użytkownik końcowy |
[Automatyczne logowanie gościa dla kiosków](#visitor-auto-logon-for-kiosks) | Umożliwia automatyczne logowanie na kontach gości, które mają być używane w trybach kiosku. | Administrator IT |
[Nowe identyfikatory AUMID dla nowych aplikacji w trybie kiosku](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | Identyfikatory AUMID dla nowych ustawień i aplikacji brzegowych. | Administrator IT |
[Ulepszono sposób awarii trybu kiosku](#kiosk-mode-behavior-changes-for-handling-of-failures) | Tryb kiosku wyszukuje dostęp przypisany globalnie przed pustym menu Start. | Administrator IT |
[Nowe ustawieniaUruchomienie widoczności ustawień strony](#new-settings-uris-for-page-settings-visibility) | Ponad 20 nowych ustawieńUruchomienie dla zasad Settings/PageVisibilityList. | Administrator IT |
[Konfigurowanie diagnostyki rezerwowej](#configuring-fallback-diagnostics-via-settings-app) | Ustawianie zachowania diagnostyki rezerwowej w aplikacji Ustawienia. | Administrator IT |
[Udostępnianie rzeczy pobliskim urządzeniem](#share-things-with-nearby-devices) | Udostępnianie plików lub adresów URL z urządzenia HoloLens na komputerze. | Wszystko |
[Nowe ślady diagnostyczne systemu operacyjnego](#new-os-diagnostic-traces) | Nowe narzędzie do rozwiązywania problemów w ustawieniach aktualizacji systemu operacyjnego. | Administrator IT |
[Optymalizacja dostarczania zapoznawcza](#delivery-optimization-preview) | Zmniejsz zużycie przepustowości w przypadku pobierania z wielu urządzeń HoloLens. | Administrator IT |

Zapoznaj się z powiązanymi informacjami o wersji:

- [Odwiedź archiwum emulatora urządzenia HoloLens](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>Wprowadzenie do nowej Microsoft Edge

![Animacja starszego Microsoft Edge logo do nowego Microsoft Edge logo](images/new-edge.gif)

Nowa aplikacja Microsoft Edge [projekt Chromium open source](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) w celu zapewnienia lepszej zgodności dla klientów i mniejszej fragmentacji sieci Web dla deweloperów sieci Web.

> [!IMPORTANT]
> Ta nowa Microsoft Edge automatycznie zastępuje starsze wersje Microsoft Edge, które nie [są już obsługiwane w](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) nowych wersjach.

![Nowy Microsoft Edge zrzut ekranu](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>Uruchamianie nowego Microsoft Edge

Nowa Microsoft Edge ![ikona Microsoft Edge nowej aplikacji](images/new_edge_logo.png) (reprezentowany przez niebieską i zieloną ikonę wirowania) jest przypinany do menu Start i będzie automatycznie uruchamiany po aktywowaniu linku internetowego.

> [!NOTE]
> Po pierwszym uruchomieniu nowej aplikacji na Microsoft Edge HoloLens 2 ustawienia i dane zostaną zaimportowane ze starszej wersji Microsoft Edge. Jeśli będziesz nadal używać starszej wersji Microsoft Edge po uruchomieniu nowego Microsoft Edge, nowe dane nie będą synchronizowane ze starszych wersji Microsoft Edge do nowych Microsoft Edge.

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Konfigurowanie ustawień zasad dla nowej Microsoft Edge

Nowa wersja Microsoft Edge administratorom IT znacznie szerszy zestaw zasad przeglądarki na urządzeniach HoloLens 2 niż wcześniej dostępne w starszych wersjach Microsoft Edge.

Oto kilka przydatnych zasobów, które mogą dowiedzieć się więcej na temat zarządzania ustawieniami zasad dla nowej Microsoft Edge:

- [Konfigurowanie Microsoft Edge ustawień zasad sieciowych przy użyciu Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Starsza wersja Microsoft Edge do Microsoft Edge mapowania zasad](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Mapowanie zasad Microsoft Edge Google Chrome](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Pełna [dokumentacja Microsoft Edge Enterprise](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> Ze względu na ilość zasad przeglądarki obsługiwanych przez nową Microsoft Edge nasz zespół nie może zagwarantować, że każda nowa zasada będzie działać na urządzeniach HoloLens 2. Jednak przetestowaliśmy i potwierdziliśmy, że nowe Microsoft Edge odpowiedniki poszczególnych starszych zasad Microsoft Edge obsługiwanych wcześniej na urządzeniach HoloLens 2 działają zgodnie z oczekiwaniami. Zobacz [Starsza wersja Microsoft Edge, Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) mapowania zasad, aby znaleźć nowe Microsoft Edge równoważne każdej starszej wersji zasad przeglądarki Microsoft Edge, których używano z urządzeniem HoloLens 2.
>
> Istnieją co najmniej dwie nowe zasady Microsoft Edge, które nie *będą działać* z urządzeniem HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Czego można oczekiwać od nowej Microsoft Edge holoLens 2

Ponieważ nowy Microsoft Edge to natywna aplikacja Win32 z nową warstwą adaptera platformy UWP umożliwiającą jej uruchamianie na urządzeniach tylko na platformie uniwersalnej systemu Windows, takich jak HoloLens 2, niektóre funkcje mogą nie być natychmiast dostępne. W najbliższych miesiącach będziemy obsługiwać nowe scenariusze i funkcje, dlatego sprawdź, czy w tym miejscu znajdują się aktualne informacje.

**Scenariusze i funkcje, które powinny działać:**
- Środowisko pierwszego uruchomienia, logowanie do profilu i synchronizacja
- Witryny internetowe powinny być renderowane i zachowywać się zgodnie z oczekiwaniami
- Większość funkcji przeglądarki (Ulubione, Historia itp.) powinna działać zgodnie z oczekiwaniami
- Tryb ciemny
- Instalowanie aplikacji internetowych na urządzeniu
- Instalowanie rozszerzeń (daj nam znać, jeśli używasz jakichkolwiek rozszerzeń, które nie działają prawidłowo na urządzeniach HoloLens 2)
- Wyświetlanie i oznaczanie pliku PDF
- Dźwięk przestrzenny z pojedynczego okna przeglądarki
- Automatyczne i ręczne aktualizowanie przeglądarki
- Zapisywanie pliku PDF z menu Drukuj (przy użyciu opcji "Zapisz w formacie PDF")
- Rozszerzenie WebXR i 360 Viewer
- Przywracanie zawartości do poprawnego okna podczas przeglądania w wielu oknach umieszczonych w środowisku

**Scenariusze i funkcje, które nie powinny działać:**
- Dźwięk przestrzenny z wielu okien z równoczesnym strumieniem audio
- "See it, say it" (Zobacz, powiedz)
- Drukowanie

**Najważniejsze znane problemy z przeglądarką:**

- Podgląd lupy na klawiaturze holograficznej został wyłączony dla nowej Microsoft Edge. Mamy nadzieję, że w przyszłej aktualizacji ponownie wdniemy się w tę funkcję, gdy powiększenie będzie działać prawidłowo.
- Dźwięk może być odtwarzany z niewłaściwego okna przeglądarki, jeśli masz otwarte i aktywne inne okno przeglądarki. Ten problem można omiąć, zamykając inne aktywne okno, które nie powinno odtwarzać dźwięku.
- Podczas odtwarzania dźwięku z okna przeglądarki w trybie ["Obserwuj mnie"](hololens2-basic-usage.md#follow-me-stop-following)dźwięk będzie odtwarzany, jeśli wyłączysz tryb "Obserwuj mnie". Ten problem można ominić, zatrzymując odtwarzanie dźwięku przed wyłączeniem trybu "Obserwuj mnie" lub zamykając okno za pomocą **przycisku X.**
- Interakcja z aktywnymi Microsoft Edge windows może spowodować nieoczekiwane nieaktywne inne okna aplikacji 2D. Te okna można ponownie uaktywnić, ponownie korzystając z nich.

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge kanałów niejawnych testerów

Zespół Microsoft Edge udostępnia trzy kanały w wersji zapoznawczej społeczności niejawnych testerów edge: Beta, Dev i Canary. Zainstalowanie kanału w wersji zapoznawczej nie spowoduje odinstalowania wydanej wersji urządzenia Microsoft Edge na urządzeniach HoloLens 2 i można zainstalować więcej niż jedną wersję jednocześnie. 

Odwiedź stronę [główną Microsoft Edge Insider,](https://www.microsoftedgeinsider.com) aby dowiedzieć się więcej o społeczności niejawnych testerów przeglądarki Edge. Aby dowiedzieć się więcej na temat różnych kanałów dla niejawnych testerów programu Edge i rozpocząć pracę, odwiedź stronę pobierania dla niejawnych [testerów programu Edge.](https://www.microsoftedgeinsider.com/download)

Istnieje kilka dostępnych metod instalowania kanałów Microsoft Edge insider na urządzeniach HoloLens 2:

**Bezpośrednia instalacja na urządzeniu (obecnie dostępna tylko dla urządzeń niezamaniowych)**
  1. Na urządzeniach HoloLens 2 odwiedź stronę [pobierania przeglądarki Edge dla niejawnych testerów.](https://www.microsoftedgeinsider.com/download)
  1. Wybierz przycisk **Pobierz dla urządzenia HoloLens 2** dla kanału niejawnego testera edge, który chcesz zainstalować.
  1. Uruchom pobrany plik msix z kolejki pobierania przeglądarki Edge lub z folderu "Pobrane" urządzenia (przy użyciu Eksplorator plików).
  1. [Zostanie uruchomić instalator](app-deploy-app-installer.md) aplikacji.
  1. Wybierz przycisk **Zainstaluj.**
  1. Po pomyślnej instalacji znajdziesz Microsoft Edge Beta, Dev lub Canary jako oddzielny wpis na **Wszystkie aplikacje** listy menu Start.

**Instalowanie na komputerze przy użyciu Portal urządzeń z systemem Windows [(wymaga](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) włączonego trybu dewelopera na urządzeniach HoloLens 2)**
  1. Na komputerze odwiedź stronę pobierania przeglądarki [Edge dla niejawnych testerów.](https://www.microsoftedgeinsider.com/download)
  1. Wybierz przycisk **strzałki listy rozwijanej** obok przycisku "Pobierz dla Windows 10" dla kanału niejawnego testera edge, który chcesz zainstalować.
  1. Wybierz **pozycję HoloLens 2** z menu rozwijanego.
  1. Zapisz plik msix w folderze "Pobrane" na komputerze (lub innym folderze, który można łatwo znaleźć).
  1. Użyj [Portal urządzeń z systemem Windows](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) na komputerze, aby zainstalować pobrany plik msix na urządzenie HoloLens 2.
  1. Po pomyślnej instalacji znajdziesz Microsoft Edge Beta, Dev lub Canary jako oddzielny wpis na **Wszystkie aplikacje** listy menu Start.

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>Używanie funkcji WDAC do blokowania nowych Microsoft Edge

W przypadku administratorów IT, którzy chcą zaktualizować zasady [usługi WDAC](windows-defender-application-control-wdac.md) w celu zablokowania nowej Microsoft Edge aplikacji, należy dodać następujące elementy do zasad.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Zarządzanie punktami końcowymi dla nowego Microsoft Edge

Niektóre środowiska mogą mieć ograniczenia sieciowe, które należy wziąć pod uwagę. Aby zapewnić bezproblemowe środowisko pracy z nową krawędzią, [włącz te punkty końcowe firmy Microsoft.](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

Przeczytaj więcej na temat aktualnie dostępnych [punktów końcowych dla urządzenia HoloLens.](hololens-offline.md)

### <a name="install-web-apps"></a>Instalowanie aplikacji internetowych
 > [!Note]
>W systemie [Windows Holographic w wersji 21H1](hololens-release-notes.md#windows-holographic-version-21h1)aplikacja internetowa pakietu Office nie będzie już wstępnie instalowana.

Nowej przeglądarki Edge można używać do instalowania aplikacji internetowych Microsoft Store aplikacji. Możesz na przykład zainstalować aplikację internetową Microsoft Office, aby wyświetlać i edytować pliki hostowane w programie SharePoint lub OneDrive. Aby zainstalować aplikację internetową pakietu Office, odwiedź i wybierz przycisk https://www.office.com **Aplikacja dostępna** lub Zainstaluj pakiet **Office** na pasku adresu. Wybierz **pozycję Zainstaluj,** aby potwierdzić.

> [!IMPORTANT]
> Funkcja aplikacji internetowej pakietu Office jest dostępna tylko wtedy, gdy urządzenie HoloLens 2 ma aktywne połączenie z Internetem.

### <a name="webxr-and-360-viewer"></a>WebXR i 360 Viewer

Nowa wersja Microsoft Edge obsługę funkcji WebXR, która jest nowym standardem tworzenia immersywnych interfejsów internetowych (zastępując webVR). Wiele immersywnych środowisk internetowych zaprojektowano z myślą o vr (zastępują one pole widzenia środowiskiem wirtualnym), ale te środowiska są również obsługiwane przez urządzenie HoloLens 2. Standard WebXR umożliwia również korzystanie z immersywnych środowisk internetowych rzeczywistości rozszerzonej i mieszanej, które korzystają ze środowiska fizycznego. Ponieważ deweloperzy spędzają więcej czasu z webxr, przewidujemy, że do klientów korzystających z urządzenia HoloLens 2 dotrą nowe immersywne środowiska rzeczywistości rozszerzonej i mieszanej.

Rozszerzenie 360 Viewer jest wbudowane w usługę WebXR i jest automatycznie instalowane wraz z nową Microsoft Edge na urządzeniach HoloLens 2. To rozszerzenie internetowe umożliwia zagłębienie się w filmy wideo na poziomie 360 stopni. Serwis YouTube oferuje największy wybór 360 filmów wideo, dlatego zachęcamy do rozpoczęcia w tym miejscu.

#### <a name="how-to-use-webxr"></a>Jak używać usługi WebXR

1. Przejdź do witryny internetowej z obsługą usługi WebXR.
1. Wybierz przycisk **Wprowadź VR** w witrynie internetowej. Lokalizacja i wizualna reprezentacja tego przycisku może się różnić w zależności od witryny internetowej, ale może wyglądać podobnie do:

    ![Przykład przycisku VR](images/75px-enter-vr.png)

1. Przy pierwszej próbie uruchomienia środowiska WebXR w określonej domenie przeglądarka poprosi o zgodę na wprowadzenie widoku immersyjnego, a następnie wybierz pozycję **Zezwalaj.**
1. Użyj [gestów urządzenia HoloLens 2,](hololens2-basic-usage.md#the-hand-tracking-frame) aby manipulować tym doświadczeniem.
1. Jeśli środowisko nie ma przycisku **Wyjdź,** użyj [gestu Uruchom,](hololens2-basic-usage.md#start-gesture) aby powrócić do strony głównej.

**Zalecane przykłady dla usługi WebXR**
- Przeglądarka 360 (zobacz następną sekcję)
- [XR Irytatorzy](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>Jak używać przeglądarki 360

1. Przejdź do wideo 360-stopnia w serwisie YouTube.
1. W ramce wideo wybierz przycisk zestawu nagłownego rzeczywistości mieszanej:

    ![Przycisk aktywacji przeglądarki 360](images/enter-360-viewer.jpg)

1. Przy pierwszej próbie uruchomienia przeglądarki 360 w określonej domenie przeglądarka poprosi o zgodę na wprowadzenie widoku immersyjnego. wybierz pozycję **Zezwalaj**.
1. [Naciśnij w powietrzu,](hololens2-basic-usage.md#select-using-air-tap) aby wyprowadzić kontrolki odtwarzania. Używaj [promieni ręki](hololens2-basic-usage.md#select-using-air-tap) i naciśnięcia w powietrzu, aby odtwarzać/wstrzymywać, pomijać przechodzenie do przodu/do tyłu, włączać/wyłączać napisy lub zatrzymywać środowisko (co zamyka widok immersyjny). Kontrolki odtwarzania znikną po kilku sekundach braku aktywności.

#### <a name="top-webxr-and-360-viewer-known-issues"></a>Znane problemy z najlepszymi usługami WebXR i 360 Viewer
- W zależności od złożoności procesu WebXR szybkość klatek może spadać lub być zacinana.
- Obsługa językowej ręki w funkcji WebXR nie jest domyślnie włączona. Deweloperzy mogą włączyć obsługę `edge://flags` za pośrednictwem funkcji , włączając funkcję "WebXR Hand Input".
- 360 filmów wideo z witryn innych niż YouTube może nie działać zgodnie z oczekiwaniami.

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Przekazywanie opinii na temat usługi WebXR i przeglądarki 360

Podziel się opinią i błędami z naszym zespołem za pośrednictwem funkcji **Wyślij** opinię w nowej Microsoft Edge.

### <a name="new-settings-app"></a>Nowa aplikacja Ustawienia

W tej wersji wprowadzamy nową wersję aplikacji Ustawienia. Nowa aplikacja Ustawienia zawiera nowe funkcje i rozszerzone ustawienia urządzenia HoloLens 2 w następujących obszarach: Dźwięk, Power & uśpienia, Sieć & Internet, Aplikacje, Konta, Ułatwienia dostępu i inne.

> [!NOTE]
> Ponieważ nowa aplikacja Ustawienia różni się od starszej aplikacji Ustawienia, wszystkie okna ustawień umieszczone wcześniej w środowisku zostaną usunięte po aktualizacji.

![Strona główna nowej aplikacji Ustawienia](images/new-settings-app.png)

**Nowe funkcje i ustawienia**
- Wyszukiwanie ustawień: wyszukaj ustawienia na stronie głównej Ustawienia przy użyciu słów kluczowych lub nazwy ustawienia.
- Dźwięk > systemowego:
  - Wejściowe i wyjściowe urządzenia audio: niezależne wybieranie wejściowych i wyjściowych urządzeń audio (na przykład nasłuchiwać dźwięku za pośrednictwem mikrofonu Bluetooth lub używać mikrofonu USB-C do wprowadzania audio).
    > [!NOTE]
    > Mikrofony Bluetooth nie są obsługiwane przez urządzenie HoloLens 2.
  - Wolumin aplikacji: niezależnie dostosuj wolumin każdej aplikacji. Zobacz [sterowanie głośnością aplikacji.](#per-app-volume-control)
- System > Power & uśpienia: wybierz, kiedy urządzenie ma przejść w stan uśpienia po okresie braku aktywności.
- System > Battery: ręcznie włącz tryb oszczędzanie baterii lub ustaw próg naładowania baterii, w którym oszczędzanie baterii jest automatycznie włączany.
- Urządzenia > USB: można domyślnie wyłączyć połączenia USB.
- Sieć & Internet:
  - Karty Ethernet USB-C będą teraz wyświetlane w sieci & Internet.
  - Dostępne są teraz ustawienia karty Ethernet USB-C, w tym jej adres IP.
  - Teraz można włączyć tryb samolotowy na urządzeniach HoloLens 2.
- Aplikacje: możesz zresetować domyślne aplikacje używane dla typów plików i linków. Aby uzyskać więcej informacji, zobacz [S wyboru domyślnej aplikacji.](#default-app-picker)
- Konta > innych użytkowników: właściciele urządzeń mogą dodawać użytkowników, uaktualniać użytkowników standardowych do właścicieli urządzeń, obniżanie poziomu właścicieli urządzeń do użytkowników standardowych i usuwanie użytkowników.
- Ułatwienia dostępu: zmiana rozmiaru tekstu i niektórych efektów wizualnych.

**Znane problemy**
- Wcześniej umieszczone okna Ustawienia zostaną usunięte (patrz uwaga powyżej).
- Nie można już zmienić nazwy urządzenia za pomocą aplikacji Ustawienia. Administratorzy IT mogą zmieniać nazwy urządzeń za pomocą szablonu nazwy urządzenia Windows Autopilot dla urządzenia [HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) lub węzła MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.
- Na stronie Ethernet przez cały czas jest wyświetlane wirtualne urządzenie Ethernet ("UsbNcm").
- Użycie baterii dla nowej Microsoft Edge może być niedokładne ze względu na charakter aplikacji klasycznej Win32 obsługiwanej przez warstwę karty platformy uniwersalnej systemu Windows (nie przewiduje się wkrótce żadnej poprawki).

#### <a name="display-color-calibration"></a>Wyświetlanie kolorowania



To nowe ustawienie umożliwia wybranie alternatywnego profilu kolorów dla urządzenia HoloLens 2. Może to pomóc w dokładniejszej wyświetlaniu kolorów, szczególnie na niższych poziomach jasność ekranu. Kolorowanie wyświetlania można znaleźć w aplikacji Ustawienia na stronie > tematu.

> [!NOTE]
> Ponieważ to ustawienie zapisuje nowy profil kolorów w oprogramowaniu układowym wyświetlania, jest to ustawienie dla poszczególnych urządzeń (i nie jest unikatowe dla każdego konta użytkownika).

##### <a name="how-to-use-display-color-calibration"></a>Jak używać kolorowania wyświetlania

1. Uruchom aplikację **Ustawienia** i przejdź do strony **System > Nawigowanie.**
1. W **obszarze Wyświetl kolorowanie** wybierz przycisk **Uruchom wyświetlanie kolorowania.**
1. Rozpocznie się środowisko kolorowania wyświetlania, które będzie zachęcało do upewninia się, że twoja wizja znajduje się we właściwej pozycji.
1. Po zakończeniu pracy z oknami dialogowymi instrukcji ekran zostanie automatycznie wygaszony do 30% jasność.
    > [!TIP]
    > Jeśli masz problemy z wyświetlaniem wygaszanej sceny w środowisku, możesz ręcznie dostosować poziom jasność urządzenia HoloLens 2 przy użyciu przycisków jasność po lewej stronie urządzenia.
1. Wybierz przyciski od 1 do 6, aby natychmiast wypróbować każdy profil kolorów i znaleźć taki, który wygląda najlepiej dla Twoich oczu (zwykle oznacza to, że profil, który pomaga scenie wyglądać najbardziej neutralnie, ze wzorcem skali szarości i wyglądem oczu zgodnie z oczekiwaniami).

    ![Wyświetlanie sceny odwzorowania kolorów](images/color-cal-ui.png)
    
1. Jeśli wybrany profil jest zadowolone, wybierz przycisk Save & Exit (Zapisz & **zakończ).**
1. Jeśli nie chcesz wprowadzać zmian, wybierz przycisk Anuluj & **zakończ,** a zmiany zostaną przywrócone

> [!TIP]
> Poniżej podano kilka przydatnych wskazówek, które należy mieć na uwadze podczas korzystania z ustawienia wyznaczania koloru wyświetlania:
> - Zawsze, gdy chcesz, możesz ponownie uruchomić kolor wyświetlania w ustawieniach
> - Jeśli ktoś na urządzeniu wcześniej użył ustawienia do zmiany profilów kolorów, data/godzina ostatniej zmiany zostanie odzwierciedlona na stronie Ustawienia
> - Po uruchomieniu ponownego kolorowania wyświetlania profil kolorów, który został wcześniej zapisany, zostanie wyróżniony, a profil 0 nie będzie wyświetlany (ponieważ profil 0 reprezentuje oryginalny profil koloru wyświetlania)
> - Jeśli chcesz przywrócić oryginalny profil kolorów ekranu, możesz to zrobić na stronie Ustawienia [(zobacz, jak zresetować profil kolorów](#how-to-reset-color-profile))

##### <a name="how-to-reset-color-profile"></a>Jak zresetować profil kolorów 

Jeśli nie masz niezadowolenia z niestandardowego profilu kolorów zapisanego na urządzeniu HoloLens 2, możesz przywrócić oryginalny profil kolorów urządzenia:
1. Uruchom aplikację **Ustawienia** i przejdź do strony **System > Nawigowanie.**
1. W **obszarze Wyświetlanie kolorowania** wybierz przycisk **Przywróć domyślny profil** kolorów.
1. Gdy zostanie otwarte okno dialogowe, wybierz pozycję **Uruchom** ponownie, jeśli wszystko jest gotowe do ponownego uruchomienia urządzenia HoloLens 2 i zastosowania zmian.

#### <a name="top-display-color-calibration-known-issues"></a>Znane problemy związane z kolorami w górnej części ekranu

- Na stronie Ustawienia ciąg stanu, który informuje o tym, kiedy profil kolorów został ostatnio zmieniony, będzie aktualny do momentu ponownego załadowania tej strony ustawień.
    - Obejście: Wybierz inną stronę Ustawienia, a następnie ponownie wybierz stronę Wynisz.

#### <a name="default-app-picker"></a>Domyślny s wyboru aplikacji

Po aktywowaniu hiperlinku lub otwarciu typu pliku z więcej niż jedną zainstalowaną aplikacją, która go obsługuje, zostanie otwarte nowe okno z monitem o wybranie zainstalowanej aplikacji, która powinna obsługiwać typ pliku lub linku. W tym oknie możesz również wybrać opcję obsługi pliku przez wybraną aplikację lub typ linku "Raz" lub "Zawsze".

Jeśli wybierzesz opcję "Zawsze", ale później chcesz zmienić, która aplikacja obsługuje określony typ pliku lub linku, możesz zresetować zapisane ustawienia domyślne w ustawieniach **> Apps.** Przewiń w dół strony i  wybierz przycisk Wyczyść w obszarze "Domyślne aplikacje dla typów plików" i/lub "Aplikacje domyślne dla typów linków". W przeciwieństwie do podobnego ustawienia na komputerach stacjonarnych nie można zresetować ustawień domyślnych poszczególnych typów plików.

#### <a name="per-app-volume-control"></a>Kontrola głośności dla aplikacji

Teraz w tej kompilacji systemu Windows użytkownicy mogą ręcznie dostosować poziom woluminu każdej aplikacji. Dzięki temu użytkownicy mogą lepiej skoncentrować się na aplikacjach, których potrzebują, lub lepiej słyszeć w przypadku korzystania z wielu aplikacji. Na przykład konieczność wyłączenia woluminu jednej aplikacji podczas rozmowy z inną osobą w celu uzyskania pomocy zdalnej w innej.

Aby ustawić wolumin poszczególnych aplikacji, przejdź do opcji Ustawienia Dźwięk systemowy i w obszarze Zaawansowane opcje dźwięku wybierz pozycję Wolumin aplikacji i  ->    ->   **preferencje urządzenia.**

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>Szybkie przesunięcie do typu

Niektórzy klienci szybciej "wpisują" na klawiaturach wirtualnych, szybko przesuwając kształt wyrazu, który zamierza wpisać, i wyświetlamy podgląd tej funkcji dla klawiatury holograficznej. Możesz szybko przesunąć po jednym wyrazie, przekazując wierzchołek palca przez płaszczyznę klawiatury holograficznej, szybko przesuwając kształt wyrazu, a następnie przesuwając wierzchołek palca od płaszczyzny klawiatury. Możesz szybko przesuwać kolejne wyrazy bez konieczności naciskania spacji, usuwając palec z klawiatury między wyrazami. Funkcja będzie działać, jeśli zobaczysz ślad przesunięcia po przesunięciu palca na klawiaturze.

Pamiętaj, że korzystanie z tej funkcji i jej opanowanie może być trudne ze względu na charakter klawiatury holograficznej, w której nie poczujesz się opór względem palca (w przeciwieństwie do ekranu telefonu komórkowego). 

### <a name="power-menu-from-start"></a>Menu Zasilania z menu Start

Nowe menu, które umożliwia użytkownikowi wylogowanie się, zamknięcie i ponowne uruchomienie urządzenia. Wskaźnik w wyświetlaczu HoloLens ekran startowy, który pokazuje, kiedy jest dostępna aktualizacja systemu.

#### <a name="how-to-use"></a>Sposób użycia

1. Otwórz urządzenie HoloLens ekran startowy [gestem Start](hololens2-basic-usage.md#start-gesture) lub powiedzenie "Przejdź do startu".

2. Zwróć uwagę na ikonę wielokropka (...) obok obrazu profilu użytkownika:

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. Wybierz obraz profilu użytkownika przy użyciu rąk lub polecenia głosowego "Power".

4. Zostanie wyświetlone menu z opcjami Wyloguj się, Uruchom ponownie lub Zamknij urządzenie:

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. Wybierz opcje menu, aby wylogować się, ponownie uruchomić lub zamknąć urządzenie HoloLens. Opcja Wyloguj może być dostępna, jeśli urządzenie jest ustawione dla pojedynczego konta [Microsoft (MSA) lub konta lokalnego.](hololens-identity.md)

6. Odrzuć menu, dotykając w innym miejscu lub zamykając menu Start gestem Start.

#### <a name="update-indicator"></a>Wskaźnik aktualizacji

Gdy aktualizacja jest dostępna, ikona wielokropka zostanie wyzjemniła, aby wskazać, że ponowne uruchomienie zainstaluje aktualizację Opcje menu również zmieniają się w celu odzwierciedlenia obecności aktualizacji.<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>Wielu użytkowników na liście na ekranie Logowania

Wcześniej na ekranie Logowanie był pokazywany tylko ostatnio zalogowany użytkownik, a także punkt wejścia "Inny użytkownik". Otrzymaliśmy opinie klientów, że nie jest to wystarczające, jeśli wielu użytkowników zalogowało się na urządzeniu. Nadal wymagane było ponowne wpisze swoją nazwę użytkownika itp.

Wprowadzone w tej kompilacji  systemu Windows po wybraniu pozycji Inny użytkownik znajdującej się po prawej stronie pola wprowadzania numeru PIN na ekranie Logowanie będzie wyświetlanych wielu użytkowników, którzy wcześniej zalogowali się na urządzeniu. Dzięki temu użytkownicy mogą wybrać swój profil użytkownika, a następnie zalogować się przy użyciu Windows Hello poświadczeń. Nowego użytkownika można również dodać do urządzenia z tej strony Inni użytkownicy za pośrednictwem **przycisku Dodaj** konto.

W menu Inni użytkownicy na przycisku Inni użytkownicy zostanie wyświetlany ostatni użytkownik zalogowany na urządzeniu. Wybierz ten przycisk, aby powrócić do ekranu Logowania dla tego użytkownika.

![Domyślny ekran logowania](./images/multiusers1.jpg)

<br>

![Ekran logowania innych użytkowników](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>Obsługa zewnętrznego mikrofonu USB-C

> [!IMPORTANT]
> Podłączanie **mikrofonu USB nie ustawi go** automatycznie jako urządzenia wejściowego . Podczas podłączania zestawu słuchawki USB-C użytkownicy zauważą, że dźwięk telefonu komórkowego zostanie automatycznie przekierowany do słuchawki, ale system operacyjny HoloLens określa priorytet wewnętrznej macierzy mikrofonów nad każdym innym urządzeniem wejściowym. **Aby użyć mikrofonu USB-C, wykonaj poniższe kroki.**

Użytkownicy mogą wybierać zewnętrzne mikrofony podłączone do dysku USB C przy użyciu **panelu Ustawień** dźwięku. Mikrofony USB-C mogą służyć do wywoływania, nagrywania itp.

Otwórz aplikację **Ustawienia** i wybierz **pozycję Dźwięk**  >  **systemowy.**

![Ustawienia dźwięku](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Aby używać mikrofonów zewnętrznych z **usługą Remote Assist,** użytkownicy będą musieli kliknąć hiperlink "Zarządzanie urządzeniami dźwiękowymi".
>
> Następnie użyj listy rozwijanej, aby ustawić zewnętrzny mikrofon jako **domyślny lub** domyślny **dla komunikacji.** Wybranie **opcji** Domyślne oznacza, że zewnętrzny mikrofon będzie używany wszędzie.
>
> Wybranie **opcji Domyślna** komunikacja oznacza, że zewnętrzny mikrofon będzie używany w uchęce Remote Assist i innych aplikacjach komunikacyjnych, ale macierz mikrofonu HoloLens może być nadal używana do innych zadań.

![Zarządzanie urządzeniami dźwiękowymi](images/usbc-mic-2.png)

<br>

![Ustawianie domyślnego mikrofonu](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>A co z obsługą mikrofonu Bluetooth?

Niestety mikrofony Bluetooth nadal nie są obecnie obsługiwane na urządzeniu HoloLens 2.

#### <a name="troubleshooting-usb-c-microphones"></a>Rozwiązywanie problemów z mikrofonami USB-C

Należy pamiętać, że niektóre mikrofony USB-C nieprawidłowo zgłaszają się jako mikrofon i *prelegent.* Jest to problem z mikrofonem, a nie z urządzeniem HoloLens. Podczas podłączania jednego z tych mikrofonów do urządzenia HoloLens dźwięk może zostać utracony. Na szczęście istnieje prosta poprawka.  

W   ->  **ustawieniach Dźwięk** systemowy jawnie ustaw wbudowane osoby mówiące (sterownik audio funkcji analogicznej) jako domyślne  ->   **urządzenie**.  Urządzenie HoloLens powinno zapamiętać to ustawienie, nawet jeśli mikrofon zostanie później usunięty i ponownie podłączony.

![Rozwiązywanie problemów z mikrofonami USB-C](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>Automatyczne logowanie gościa dla kiosków

Ta nowa funkcja umożliwia automatyczne logowanie na kontach gościa w trybach kiosku.

W przypadku konfiguracji spoza usługi AAD, aby skonfigurować urządzenie do automatycznego logowania gościa:

1. Utwórz pakiet aprowizowania, który:
    1. Konfiguruje **ustawienia środowiska uruchomieniowego/AssignedAccess,** aby umożliwić kontom odwiedzającym.
    1. Opcjonalnie rejestruje urządzenie w układzie MDM (ustawienia środowiska **uruchomieniowego/miejsce pracy/rejestracje),** aby można było nim zarządzać później.
    1. Nie twórz konta lokalnego
1. [Zastosuj pakiet aprowizowania](hololens-provisioning.md).

W przypadku konfiguracji usługi AAD użytkownicy mogą dzisiaj osiągnąć coś podobnego bez tej zmiany. Urządzenia przyłączone do usługi AAD skonfigurowane do pracy w trybie kiosku mogą zalogować się do konta gościa jednym naciśnięciem przycisku na ekranie logowania. Po zalogowaniu się do konta gościa urządzenie nie będzie monitować o ponowne zalogowanie, dopóki gość nie zostanie jawnie wylogowany z menu Start lub urządzenie zostanie uruchomione ponownie.

Automatyczne logowanie gościa można zarządzać za pomocą niestandardowych zasad [OMA-URI:](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)

- Wartość URI: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Zasady  | Opis   | Konfiguracje  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | Umożliwia odwiedzającemu automatyczne logowanie do kiosku   | 1 (Tak), 0 (Nie, wartość domyślna).  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>Używanie nowych ustawień i aplikacji Edge w trybach kiosku

W przypadku do uwzględnienia aplikacji [w kioskach](hololens-kiosk.md)administrator IT często dodaje aplikację do kiosku, ale przy użyciu identyfikatora modelu użytkownika aplikacji (AUMID). Ponieważ zarówno aplikacja Ustawienia, jak i aplikacja Microsoft Edge są traktowane jako nowe aplikacje i inne niż starsze kioski aplikacji, które używają identyfikatorów AUMID dla tych aplikacji, należy zaktualizować tak, aby używać nowego identyfikatorów AUMID.

W przypadku modyfikowania kiosku w celu dodawania nowych aplikacji zalecamy dodanie nowego aumidu do nowego, a także pozostawienie starego. Spowoduje to łatwe przejście, gdy użytkownicy zaktualizują system operacyjny i nie będą musieli otrzymywać nowych zasad, aby nadal korzystać z kiosku zgodnie z przeznaczeniem.

| Aplikacja                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| Stara aplikacja ustawienia       | HolographicSystemSettings_cw5n1h2txyewy! App            |
| Nowa aplikacja ustawienia       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
| Stara Microsoft Edge aplikacji | Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge    |
| Nowa Microsoft Edge aplikacji | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Zmiany zachowania trybu kiosku w celu obsługi awarii

W starszych kompilacjach, jeśli urządzenie miało konfigurację kiosku, która jest kombinacją dostępu przypisanego globalnie i przypisanego do członka grupy usługi AAD, w przypadku określenia, że członkostwo w grupie usługi AAD nie powiodło się, użytkownik zobaczy "nic nie jest wyświetlane w menu[Start".](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)

Począwszy od tej wersji systemu Windows, środowisko kiosku będzie w razie awarii w trybie kiosku grupy usługi AAD w razie awarii w globalnej konfiguracji kiosku.

### <a name="new-settings-uris-for-page-settings-visibility"></a>Nowe adresy URI ustawień dla widoczności ustawień strony

W [systemie Windows Holographic w wersji 20H2](hololens-release-notes.md#windows-holographic-version-20h2) dodaliśmy zasady [Settings/PageVisibilityList,](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) aby ograniczyć strony widoczne w aplikacji Ustawienia. PageVisibilityList to zasady, które umożliwiają administratorom IT uniemożliwić widoczność lub dostępność określonych stron w aplikacji Ustawienia systemowe lub zrobić to dla wszystkich stron z wyjątkiem określonych.

Jeśli odwiedzisz stronę Widoczność ustawień [strony,](settings-uri-list.md)możesz znaleźć instrukcje korzystania z tego programu CSP oraz listę URI dostępnych w poprzednich wersjach.

Rozszerzamy listę dostępnych URI ustawień, którymi administratorzy IT mogą zarządzać. Niektóre z tych URI są dla nowo dostępnych obszarów w nowej aplikacji Ustawienia. Jeśli używasz zasad Settings/PageVisibilityList, przejrzyj następującą listę i dostosuj dozwolone lub zablokowane strony zgodnie z potrzebami.

> [!NOTE]
> **Przestarzałe: ms-settings:network-proxy**
>
> Jedna strona ustawień jest przestarzała w tych nowszej kompilacji. Stara strona **serwera & proxy**  >  **sieci** nie jest już dostępna jako ustawienie globalne. Nowe ustawienia serwera proxy dla połączenia można znaleźć w obszarze Właściwości sieci **& Internet**  >  **Wi-Fi** lub Właściwości  >   sieci & **Internet**  >    >  **Ethernet.**

<br>

| Strona Ustawienia                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| Funkcje > Apps & Apps                               | `ms-settings:appsfeatures`                         |
| Funkcje > Apps & > opcje zaawansowane          | `ms-settings:appsfeatures-app`                     |
| Mapy > offline                                  | `ms-settings:maps`                                 |
| Mapy > w trybie offline > pobieranie map                  | `ms-settings:maps-downloadmaps`                    |
| Mysz > urządzenia                                      | `ms-settings:mouse`                                |
| Urządzenia > USB                                        | `ms-settings:usb`                                  |
| Sieć & Internet > tryb samolotowy                   | `ms-settings:network-airplanemode`                 |
| Zasady ochrony > ogólne                                    | `ms-settings:privacy-general`                      |
| Privacy > Ink & typing personalizacja             | `ms-settings:privacy-speechtyping`                 |
| Ochrona > prywatności i ruchu                                     | `ms-settings:privacy-motion`                       |
| Ochrona prywatności > obramowania zrzutów ekranu                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| Zrzuty > i aplikacje dotyczące prywatności                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| System > baterii                                     | `ms-settings:batterysaver`                         |
| System > baterii                                     | `ms-settings:batterysaver-settings`                |
| Dźwięk > systemowego                                       | `ms-settings:sound`                                |
| System > Sound > App volume and device preferences (Wolumin aplikacji i preferencje urządzenia) | `ms-settings:apps-volume`                          |
| System > Sound > Zarządzanie urządzeniami dźwiękowymi              | `ms-settings:sound-devices`                        |
| Konfigurowanie > magazynu > Czujnik pamięci         | `ms-settings:storagepolicies`                      |
| Data & > data & czas                        | `ms-settings:dateandtime`                          |
| Time & Language > Klawiatura                           | `ms-settings:keyboard`                             |
| Time & Language > Language                           | `ms-settings:language`                             |
| Time & Language > Language                           | `ms-settings:regionlanguage-languageoptions`       |
| Aktualizowanie & zabezpieczeń > resetowania & odzyskiwania               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>Zaktualizowane dane URI

Wcześniej następujące dwa identyfikatory URI nie przyjmowałyby użytkownika bezpośrednio do wskazanych stron, ale blokowały tylko główną stronę aktualizacji. Zaktualizowano następujące elementy tak, aby kierowały się do ich stron:

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>Konfigurowanie diagnostyki powrotu za pośrednictwem aplikacji Ustawienia

Teraz w aplikacji Ustawienia użytkownik może skonfigurować zachowanie diagnostyki [rezerwowej](hololens-diagnostic-logs.md). W aplikacji Ustawienia przejdź do strony **Rozwiązywanie**  ->  **problemów z prywatnością,** aby skonfigurować to ustawienie.

> [!NOTE]
> Jeśli dla urządzenia skonfigurowano zasady zarządzania urządzeniami przenośnymi, użytkownik nie będzie mógł przesłonić tego zachowania.  

### <a name="share-things-with-nearby-devices"></a>Udostępnianie rzeczy pobliskim urządzeniem

Udostępniaj urządzenia w pobliżu urządzeń Windows 10, w tym komputerów i innych urządzeń HoloLens 2. Aby udostępnić pliki lub adresy URL z urządzenia HoloLens na komputerze, możesz ją wypróbować w dzielonych przez system  ->    ->   ustawieniach środowiskoch udostępnionych. Aby uzyskać więcej informacji, przeczytaj więcej na temat sposobu udostępniania rzeczy [pobliskim urządzeniem w Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

Tą funkcją można zarządzać za [pośrednictwem elementu Connectivity/AllowConnectedDevices.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)

### <a name="new-os-diagnostic-traces"></a>Nowe ślady diagnostyczne systemu operacyjnego

Oprócz poprzednich funkcji rozwiązywania problemów w aplikacji Ustawienia dodano nowe narzędzie do rozwiązywania problemów z dodaniem nowej aplikacji Ustawienia aktualizacji systemu operacyjnego. Przejdź do **tematu Rozwiązywanie problemów**  ->  **z &amp; aktualizacjami**  >    >  **Windows Update** ustawienia i wybierz pozycję **Uruchom.** Dzięki temu można zbierać ślady podczas odtwarzania problemu z aktualizacjami systemu operacyjnego, aby lepiej pomóc w rozwiązywaniu problemów z pomocą techniczną lub IT.

### <a name="delivery-optimization-preview"></a>Optymalizacja dostarczania zapoznawcza

Dzięki tej aktualizacji urządzenia HoloLens Windows Holographic for Business ustawienia optymalizacji dostarczania w celu zmniejszenia zużycia przepustowości w przypadku pobierania z wielu urządzeń HoloLens. Pełniejsze opisy tej funkcji wraz z zalecaną konfiguracją sieci są dostępne tutaj: Optymalizacja dostarczania [do Windows 10 aktualizacji.](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)

Następujące ustawienia są włączane w ramach powierzchni zarządzania i [można je skonfigurować z usługi Intune:](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings)

- [DOCacheHost](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Kilka zastrzeżenia dotyczących tej oferty w wersji zapoznawczej:

- Obsługa urządzenia HoloLens w tej wersji zapoznawczej jest ograniczona tylko do aktualizacji systemu operacyjnego.
- Windows Holographic for Business obsługuje tylko tryby pobierania i pobierania http z punktu [końcowego usługi Microsoft Connected Cache ;](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) Tryby pobierania elementów równorzędnych i przypisania grup nie są obecnie obsługiwane w przypadku urządzeń HoloLens.
- Urządzenie HoloLens nie obsługuje optymalizacji wdrażania ani dostarczania dla Windows Server Update Services końcowych.
- Rozwiązywanie problemów będzie wymagało diagnostyki na serwerze Connected Cache lub zebrania śladu na urządzeniach HoloLens na urządzeniach HoloLens za pośrednictwem narzędzia Do rozwiązywania problemów z zabezpieczeniami usługi & Update  >    >     >   **Windows Update**.

### <a name="it-admin---update-checklist"></a>Administrator IT — lista kontrolna aktualizacji

Ta lista kontrolna pomoże Ci poznać nowe elementy, które są dodawane w tej aktualizacji funkcji, które mogą mieć wpływ na bieżące konfiguracje zarządzania urządzeniami, lub nowe funkcje, których możesz użyć.

#### <a name="updates-to-kiosk-mode"></a>Aktualizacje trybu kiosku

✔️ nowe [**identyfikatory AUMID dla nowych aplikacji w trybie kiosku:**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

Jeśli wcześniej używano aplikacji Ustawienia lub aplikacji Microsoft Edge kiosku, zastąpiliśmy te aplikacje nowymi aplikacjami, które używają innego identyfikatora aplikacji. Zdecydowanie zachęcamy do przeczytania poniższego [artykułu New AUMIDs for new apps in Kiosk mode (Nowe identyfikatory AUMID](#use-the-new-settings-and-edge-apps-in-kiosk-modes) dla nowych aplikacji w trybie kiosku). Dzięki temu będziesz nadal mieć aplikację Ustawienia w kiosku lub dołączysz nową Microsoft Edge aplikację. Te zmiany można teraz wprowadzić i wdrożyć na wszystkich urządzeniach, aby umożliwić płynniejsze przejście po aktualizacji.

✔️ automatyczne [**logowanie gościa dla kiosków:**](#visitor-auto-logon-for-kiosks) 

Odwiedzający mogą być teraz automatycznie logni do kiosku. To zachowanie jest domyślnie włączone, ale może być zarządzane i wyłączone.

✔️ [**awarii trybu kiosku:**](#kiosk-mode-behavior-changes-for-handling-of-failures)

Jeśli członkostwo w grupie usługi AAD zalogowaowego użytkownika usługi AAD nie zostanie pomyślnie określone, globalna konfiguracja kiosku będzie używana dla menu Start (jeśli istnieje). W przeciwnym razie użytkownikom zostanie przedstawione puste menu Start. Puste menu Start nie jest konfiguracją, którą można ustawić bezpośrednio, jednak ta nowa obsługa może być czymś, o czym dział pomocy technicznej informuje, jeśli używasz kiosków, ponieważ może to dotyczyć Twoich konfiguracji lub możesz chcieć wprowadzić nowe korekty w przypisanych konfiguracjach dostępu.

#### <a name="updates-to-page-settings-visibility"></a>Aktualizacje widoczności ustawień strony

✔️ nowe [**ustawienia dla widoczności ustawień strony**](#new-settings-uris-for-page-settings-visibility)

Jeśli obecnie używasz [widoczności](settings-uri-list.md) ustawień strony, możesz chcieć wprowadzić zmiany istniejących URI, które zostały dozwolone lub zablokowane.

#### <a name="updates-for-your-wdac-policy"></a>Aktualizacje zasad funkcji WDAC
✔️ jeśli wcześniej blokowano Microsoft Edge za pośrednictwem usługi WDAC, należy zaktualizować zasady WDAC. Zapoznaj się z poniższymi tematami i użyj podanego przykładowego kodu.
#### <a name="enable-new-endpoints-for-edge"></a>Włączanie nowych punktów końcowych dla usługi Edge
✔️ jeśli masz infrastrukturę, która obejmuje konfigurowanie punktów końcowych sieci, takich jak serwer proxy lub zapora, włącz te nowe punkty końcowe dla nowej Microsoft Edge wirtualnej.

#### <a name="newly-configurable-items"></a>Nowo konfigurowalne elementy

✔️ [diagnostyki rezerwowej:](#configuring-fallback-diagnostics-via-settings-app)można skonfigurować, czy i kto może zbierać dane diagnostyki rezerwowej.

✔️[Udostępnij rzeczy pobliskim urządzeniem:](#share-things-with-nearby-devices)możesz wyłączyć nową funkcję udostępniania w pobliżu.

✔️ Konfigurowanie [ustawień zasad dla nowej](#configuring-policy-settings-for-the-new-microsoft-edge)Microsoft Edge: Przejrzyj nowo dostępne konfiguracje dla Microsoft Edge.

#### <a name="new-diagnostic-tool"></a>Nowe narzędzie diagnostyczne

✔️[danych śledzenia diagnostycznego systemu operacyjnego:](#new-os-diagnostic-traces)zbieranie dzienników związanych z aktualizacjami systemu operacyjnego.

### <a name="improvements-and-fixes-in-the-update"></a>Ulepszenia i poprawki w aktualizacji:

- [Diagnostyka w](hololens-diagnostic-logs.md#offline-diagnostics) trybie offline będzie również zawierać dodatkowe informacje o urządzeniu dla numeru seryjnego i wersji systemu operacyjnego.
- Rozwiązuje problem dotyczący wdrażania aplikacji biznesowych za pośrednictwem pakietów aprowizowania środowiska uruchomieniowego.
- Rozwiązuje problem z raportowaniem stanu instalacji aplikacji biznesowych.
- Rozwiązuje problem z trwałością nowych pakietów aplikacji podczas resetowania urządzenia.
- Rozwiązano problem, który mógł prowadzić do wpisywania nieprawidłowych symboli w programie Edge dla japońskich klientów.
- Zwiększa odporność aktualizacji systemu operacyjnego wokół wstępnie zainstalowanych aplikacji, takich jak Microsoft Edge. 
- Rozwiązuje problem z niezawodnością aktualizacji, która ma wpływ na instalację Microsoft Edge. 


## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holographic, wersja 20H2 — aktualizacja z maja 2021 r.
- Kompilacja 19041.1146

Ulepszenia i poprawki w aktualizacji:
- Ta comiesięczna aktualizacja jakości nie zawiera żadnych notowalnych zmian. Zachęcamy do wypróbowania naszej najnowszej kompilacji, Windows Holographic, wersja 21H1.

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holographic, wersja 1903 — aktualizacja z maja 2021 r.
- Kompilacja 18362.1110

Ulepszenia i poprawki w aktualizacji:
- Ta miesięczna aktualizacja jakości nie zawiera żadnych notowalnych zmian. **Ta kompilacja nie będzie już otrzymywać comiesięcznych aktualizacji usługi.** Zachęcamy do wypróbowania najnowszej kompilacji systemu Windows Holographic w wersji 21H1.



## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographic, wersja 20H2 — aktualizacja z kwietnia 2021 r.
- Kompilacja 19041.1144

Ulepszenia i poprawki w aktualizacji:

- Rozwiązuje problem z raportowaniem stanu instalacji aplikacji biznesowych.

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographic, wersja 1903 — aktualizacja z kwietnia 2021 r.
- Kompilacja 18362.1108

Ulepszenia i poprawki w aktualizacji:

- Rozwiązuje problem, który występuje, gdy aplikacja Ustawienia ulega awarii podczas próby zmiany hasła dla konta lokalnego.


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows Holographic, wersja 20H2 — aktualizacja z marca 2021 r.
- Kompilacja 19041.1140

Ulepszenia i poprawki w aktualizacji:

- Klienci korzystający z funkcji AdvancedPhotoCapture lub LowLagPhotoCapture do przechwytywania zdjęć za pomocą urządzenia HoloLens 2 mogą teraz pobierać kamerę po maksymalnie 3 sekundach od przechwycenia zdjęcia.
- Poprawka rozmytego przecieku pamięci w usłudze Portal urządzeń Service, która powodowała zwiększone użycie pamięci przez usługę, która powodowała niepowodzenie przydzielania pamięci przez inne aplikacje.
- Rozwiązano problem, który mógł oznaczać, że użytkownicy zarejestrowani w etapowym wywłaszczania nie mogli zalogować się na urządzeniu.

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows Holographic, wersja 1903 — aktualizacja z marca 2021 r.
- Kompilacja 18362.1102

Ulepszenia i poprawki w aktualizacji:

- Poprawka rozmytego przecieku pamięci w usłudze Portal urządzeń Service, która powodowała zwiększone użycie pamięci przez usługę, która powodowała niepowodzenie przydzielania pamięci przez inne aplikacje.

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows Holographic, wersja 20H2 — aktualizacja z lutego 2021 r.
- Kompilacja 19041.1136

Ulepszenia i poprawki w aktualizacji:

- Rozwiązuje problem z początkową konfiguracją urządzenia i przechowywaniem aktualizacji aplikacji.
- Rozwiązuje problem z uaktualnieniami i lotami dla nowszych wersji urządzenia HoloLens.
- Usunięto nieużywane wstępnie zainstalowane certyfikaty z głównego magazynu eSIM z urządzeń HoloLens.

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows Holographic, wersja 1903 — aktualizacja z lutego 2021 r.
- Kompilacja 18362.1098

Ta comiesięczna aktualizacja jakości nie zawiera żadnych owalnych zmian. Zachęcamy do wypróbowania naszych najnowszych kompilacji dla systemu Windows Holographic w wersji 2004.

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic, wersja 20H2 — aktualizacja ze stycznia 2021 r.
- Kompilacja 19041.1134

Ulepszenia i poprawki w aktualizacji:

- Zwiększona wydajność podczas uruchamiania, wznawiania i przełączania użytkowników w przypadku wielu użytkowników na urządzeniu.
- Dodano obsługę arm32 dla [trybu badania](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode).

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic, wersja 1903 — aktualizacja ze stycznia 2021 r.
- Kompilacja 18362.1091

Ta comiesięczna aktualizacja jakości nie zawiera żadnych owalnych zmian. Zachęcamy do wypróbowania naszych najnowszych kompilacji dla systemu Windows Holographic w wersji 2004.

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic, wersja 20H2 — aktualizacja z grudnia 2020 r.
- Kompilacja 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>Instalowanie aplikacji na urządzeniach HoloLens 2 za pośrednictwem Instalator aplikacji

Dodajemy **nową funkcję (Instalator aplikacji),** aby umożliwić bezproblemowe instalowanie aplikacji na urządzeniach HoloLens 2. Ta funkcja będzie domyślnie **włączona dla urządzeń nieza pomocą programu**. Aby zapobiec zakłóceniom pracy przedsiębiorstw, instalator aplikacji nie **będzie w** tej chwili dostępny dla zarządzanych urządzeń.  

Urządzenie jest uznawane za "zarządzane", **jeśli** spełnione są dowolne z następujących czynności:
- Zarejestrowane w usłudze ZARZĄDZANIA [urządzeniami przenośnymi](hololens-enroll-mdm.md)
- Skonfigurowano przy użyciu [pakietu aprowizowania](hololens-provisioning.md)
- Tożsamość [użytkownika to](hololens-identity.md) usługa Azure AD

Teraz możesz instalować aplikacje bez konieczności włączania trybu dewelopera ani korzystania z Portal urządzeń.  Po prostu pobierz (za pośrednictwem portu USB lub za pośrednictwem przeglądarki Edge) pakiet Appx na urządzenie i przejdź do pakietu Appx Eksplorator plików w celu monitowania o rozpoczynanie instalacji.  Alternatywnie [zainicjuj instalację ze strony internetowej](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  Podobnie jak aplikacje, które instalujesz z usługi Microsoft Store lub ładować bezpośrednio przy użyciu funkcji wdrażania [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) aplikacji LOB [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) mdM, aplikacje muszą być podpisane cyfrowo przy użyciu narzędzia podpisywania, a certyfikat używany do podpisywania musi być zaufany przez urządzenie HoloLens, zanim będzie można wdrożyć aplikację.

**Instrukcje dotyczące instalacji aplikacji.**

1.  Upewnij się, że urządzenie nie jest uznawane za zarządzane
1.  Upewnij się, że urządzenie HoloLens 2 jest włączone i połączone z komputerem
1.  Upewnij się, że zalogowano się na urządzeniu HoloLens 2
1.  Na komputerze przejdź do aplikacji niestandardowej i skopiuj yourapp.appxbundle do katalogu yourdevicename\Internal Storage\Downloads.   Po zakończeniu kopiowania pliku możesz rozłączyć urządzenie
1.  Na urządzeniu HoloLens 2 Otwórz menu Start, wybierz pozycję Wszystkie aplikacje i uruchom Eksplorator plików aplikację.
1.  Przejdź do folderu Pobrane. W lewym panelu aplikacji może być konieczne wybranie najpierw opcji To urządzenie, a następnie przejście do sekcji Pliki do pobrania.
1.  Wybierz plik yourapp.appxbundle.
1.  Zostanie Instalator aplikacji. Wybierz przycisk Zainstaluj, aby zainstalować aplikację.
Zainstalowana aplikacja zostanie automatycznie uruchamiana po zakończeniu instalacji.

Przykładowe aplikacje można znaleźć w witrynie [GitHub z uniwersalnymi przykładami](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) systemu Windows, aby przetestować ten przepływ.

Przeczytaj o pełnym procesie instalowania [aplikacji na urządzeniach HoloLens 2 za pomocą Instalator aplikacji](app-deploy-app-installer.md).  

![Instalowanie przykładów mrTK za pośrednictwem Instalator aplikacji](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>Ulepszenia i poprawki w aktualizacji:

- Śledzenie rąk obsługuje teraz śledzenie w wielu nowych przypadkach, w których wcześniej zostałaby utracona ręka.  W niektórych z tych nowych przypadków tylko położenie pępka jest nadal aktualizowane na podstawie rzeczywistej ręki użytkownika, podczas gdy drugi jest wywnioskować na podstawie poprzedniej pozycji.  Ta zmiana pomaga zwiększyć spójność śledzenia w ruchach, takich jak slapping, throwing, singing i clapping.  Pomaga to również w przypadkach, gdy ręka znajduje się blisko powierzchni lub trzymający obiekt.  W przypadku wywłasznia [](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) ręki wartość dokładności na maksymalną zostanie ustawiona na wartość "Przybliżona", a nie "Wysoka".
- Rozwiązano problem, który pokazywał błąd "Wystąpił problem podczas resetowania numeru PIN dla kont usługi Azure AD.
- Użytkownicy powinni widzieć znacznie mniej awarii OOBE po rozruchu podczas uruchamiania et, irys z ustawienia aplikacji, nowego użytkownika lub powiadomienia wyskakującego.
- Użytkownicy powinni mieć poprawną strefę czasową wychodzącą z OOBE.

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic, wersja 1903 — aktualizacja z grudnia 2020 r.
- Kompilacja 18362.1088

Ta comiesięczna aktualizacja jakości nie zawiera żadnych notowalnych zmian. Zachęcamy do wypróbowania najnowszej wersji systemu Windows Holographic w wersji 20H2 — aktualizacja z grudnia 2020 r. i nowej funkcji Instalator aplikacji dodanej w kompilacji.


## <a name="windows-holographic-version-20h2"></a>Windows Holographic, wersja 20H2
- Kompilacja 19041.1128

System Windows Holographic w wersji 20H2 jest teraz dostępny i oferuje doskonały zestaw nowych funkcji dla użytkowników urządzenia HoloLens 2 i informatyków. Od automatycznego pozycjonowania oka, przez Menedżera certyfikatów w ustawieniach po ulepszone funkcje trybu kiosku i nowe możliwości konfiguracji rozwiązania Autopilot. Ta nowa aktualizacja umożliwia zespołom IT bardziej szczegółową kontrolę nad konfigurowaniem urządzeń HoloLens i zarządzaniem nimi, a także oferuje użytkownikom jeszcze bardziej bezproblemowe środowisko holograficzne. 

Ta najnowsza wersja to comiesięczne aktualizacje do wersji 2004, ale tym razem są dostępne nowe funkcje. Główny numer kompilacji pozostanie taki sam, Windows Update będzie wskazywać comiesięczne wydanie do wersji 2004 (kompilacja 19041). Możesz sprawdzić numer kompilacji na ekranie Ustawienia > informacje, aby potwierdzić, że używasz najnowszej dostępnej kompilacji 19041.1128+. Aby zaktualizować program do najnowszej wersji, otwórz aplikację Ustawienia, przejdź do witryny Update & Security i naciśnij pozycję Sprawdź aktualizacje. Aby uzyskać więcej informacji na temat zarządzania aktualizacjami urządzenia HoloLens, odwiedź [tę stronę](https://docs.microsoft.com/hololens/hololens-updates).

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Co nowego w systemie Windows Holographic w wersji 20H2  

| Cecha                                              | Opis                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [Obsługa automatycznego położenia oka](hololens-release-notes.md#auto-eye-position-support) | Aktywnie oblicza położenie oka bez użytkowników przechodzących przez śledzenie oczu.   |
| [Menedżer certyfikatów](hololens-release-notes.md#certificate-manager)   | Umożliwia nowe prostsze metody instalowania i usuwania certyfikatów z aplikacji Ustawienia.     |
| [Automatyczne uruchamianie aprowizowania z dysku USB](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | Aprowizowanie pakietów na dyskach USB automatycznie wyświetla monit o stronę aprowingu w trybie OOBE.                                                         |
| [Automatyczne potwierdzanie pakietów aprowizowania w OOBE](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | Pakiety aprowizowania są automatycznie stosowane podczas OOBE ze strony aprowowania.                                                         |
| [Automatyczne aprowizowanie bez użycia interfejsu użytkownika](hololens-release-notes.md#automatic-provisioning-without-using-ui) | Jak połączyć automatyczne uruchamianie aprowizowania i automatyczne potwierdzanie razem. |
| [Używanie rozwiązania Autopilot z Wi-Fi połączenia](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | Używaj rozwiązania Autopilot z poziomu Wi-Fi bez konieczności używania karty Ethernet. |
| [Tenantlockdown CSP and Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | Po zarejestrowaniu dzierżawy i zastosowaniu zasad urządzenie może zostać zarejestrowane w tej dzierżawie tylko za każdym razem, gdy urządzenie zostanie zresetowane lub ponownie flashowane. |
| [Dostęp przypisany globalnie](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | Nowa metoda konfiguracji dla trybu kiosku z wieloma aplikacjami, która stosuje kiosk na poziomie systemu, dzięki czemu ma zastosowanie do wszystkich.                  |
| [Automatyczne uruchamianie aplikacji w kiosku z wieloma aplikacjami](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | Ustawia aplikację do automatycznego uruchamiania podczas logowania się w trybie kiosku z wieloma aplikacjami.                                                        |
| [Zmiany zachowania trybu kiosku w celu obsługi awarii](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | Awaria trybu kiosku ma teraz restrykcyjny tryb rezerwowy.                                                                                                |
| [Zasady dotyczące urządzenia HoloLens](hololens-release-notes.md#hololens-policies)                                    | Nowe zasady dla urządzenia HoloLens.     |
| [Buforowanie członkostwa w grupie usługi Azure AD dla kiosku w trybie offline](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | Nowe zasady umożliwiają użytkownikom używanie pamięci podręcznej członkostwa w grupach do korzystania z trybu kiosku w trybie offline przez ustawioną liczbę dni.                                        |
| [Nowe zasady ograniczeń urządzeń HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | Włączono nowo włączone zasady zarządzania urządzeniami dla urządzenia HoloLens 2.                                                                                |
| [Nowe zasady zasilania dla urządzenia HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | Nowo obsługiwane zasady ustawień limitu czasu zasilania.  |
| [Aktualizowanie zasad](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | Nowo włączone zasady umożliwiające kontrolę nad aktualizacjami.           |
| [Widoczność strony Włączone ustawienia dla urządzenia HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | Zasady służące do wyboru stron widocznych w aplikacji Ustawienia.             |
| [Tryb badań](hololens-release-notes.md#research-mode) | Korzystanie z trybu badań na urządzeniach HoloLens 2. |
| [Długość rejestrowania zwiększona](hololens-release-notes.md#recording-length-increased) | Nagrania MRC nie są już ograniczone do 5 minut. |
| [Ulepszenia i poprawki w aktualizacji](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | Dodatkowe poprawki w aktualizacji.   |

### <a name="auto-eye-position-support"></a>Obsługa automatycznego położenia oka

Na urządzeniach HoloLens 2 położenia oczu umożliwiają dokładne pozycjonowanie hologramów, wygodne środowisko wyświetlania i lepszą jakość wyświetlania. Pozycje oczu są obliczane wewnętrznie w ramach obliczeń śledzenia wzroku. Jednak wymaga to, aby każdy użytkownik przechodził przez śledzenie wzroku, nawet wtedy, gdy środowisko może nie wymagać danych wejściowych spojrzenia oczu.

**Funkcja Auto Eye Position (AEP)** umożliwia tym scenariuszom bez interakcji obliczanie pozycji oczu dla użytkownika. Funkcja Auto Eye Position automatycznie zacznie działać w tle od momentu, w którym użytkownik umieści urządzenie. Jeśli użytkownik nie ma wcześniejszego śledzenia wzroku, funkcja Auto Eye Position zacznie dostarczać użytkownikowi pozycje oczu do systemu wyświetlania po czasie przetwarzania 20–30 sekund. Dane użytkownika nie są utrwalane na urządzeniu, dlatego ten proces jest powtarzany, jeśli użytkownik wystartuje i ponownie uruchomi urządzenie lub jeśli urządzenie zostanie ponownie uruchomiony lub wznowiony po uśpieniu.

Istnieje kilka zmian zachowania systemu za pomocą funkcji automatycznego położenia oka, gdy na urządzeniu zostanie umieszczony nieskalibrowany użytkownik. W tym kontekście użytkownik nieskalibrowany odnosi się do kogoś, kto wcześniej nie przeszedł przez proces śledzenia wzroku na urządzeniu.

| Aktywna aplikacja | Wcześniejsze zachowanie | Zachowanie z systemu Windows Holographic, aktualizacja w wersji 20H2 |
|:-------------------|:-----------------|:-----------------------------------|
| Aplikacja bez obsługi spojrzenia lub powłoka Holographic Shell |Zostanie wyświetlone okno dialogowe monitu o śledzenie wzroku. | Monit nie jest wyświetlany. |
| Aplikacja z obsługą spojrzenia | Zostanie wyświetlone okno dialogowe monitu o śledzenie wzroku. | Monit o śledzenie wzroku jest wyświetlany tylko wtedy, gdy aplikacja uzyskuje dostęp do strumienia oczu. |

Jeśli użytkownik przechodzi z aplikacji z włączoną obsługą spojrzenia do aplikacji, która uzyskuje dostęp do danych spojrzenia, zostanie wyświetlony monit o podanie monitu. 

Wszystkie inne zachowania systemu będą podobne do zachowania bieżącego użytkownika, który nie ma aktywnej kontroli wzroku. Na przykład gest Uruchamiania jednym ręki nie zostanie włączony. Nie będzie żadnych zmian w out-of-box-experience dla konfiguracji początkowej.

W przypadku doświadczeń wymagających danych dotyczących spojrzenia oczu lub bardzo precyzyjnego pozycjonowania hologramu zalecamy użytkownikom nieskalicznym uruchamianie śledzenia wzroku. Jest on dostępny z monitu o śledzenie wzroku lub przez uruchomienie aplikacji Ustawienia z menu Start, a następnie wybranie pozycji System > Pochylinie **>** Pochłoń okiem > podniebna.

Te informacje można znaleźć później z innymi [informacjami o incydowaniu.](hololens-calibration.md#auto-eye-position-support) 

### <a name="certificate-manager"></a>Menedżer certyfikatów

- Ulepszono narzędzia do inspekcji, diagnostyki i weryfikacji zabezpieczeń i zgodności urządzeń za pośrednictwem nowego Menedżera certyfikatów. Ta funkcja umożliwi wdrażanie, rozwiązywanie problemów i weryfikowanie certyfikatów na dużą skalę w środowiskach komercyjnych.

W systemie Windows Holographic w wersji 20H2 dodajemy Menedżera certyfikatów w aplikacji Ustawienia urządzenia HoloLens 2. Przejdź do **ustawień > Update & Security > Certificates**. Ta funkcja zapewnia prosty i przyjazny dla użytkownika sposób wyświetlania, instalowania i usuwania certyfikatów na urządzeniu. Dzięki nowej funkcji Menedżer certyfikatów administratorzy i użytkownicy mają teraz ulepszone narzędzia inspekcji, diagnostyki i walidacji, aby zapewnić, że urządzenia pozostaną bezpieczne i zgodne. 

-   **Inspekcja:** Możliwość zweryfikowania, czy certyfikat został wdrożony poprawnie, lub potwierdzenia, że został on odpowiednio usunięty. 
-   **Diagnostyka:** W przypadku problemów podczas sprawdzania, czy na urządzeniu istnieją odpowiednie certyfikaty, oszczędzasz czas i pomagasz w rozwiązywaniu problemów. 
-   **Walidacja:** Sprawdzenie, czy certyfikat służy zamierzony cel i jest funkcjonalny, może zaoszczędzić dużo czasu, szczególnie w środowiskach komercyjnych przed wdrożeniem certyfikatów na większą skalę.

Aby szybko znaleźć określony certyfikat na liście, dostępne są opcje sortowania według nazwy, magazynu lub daty wygaśnięcia. Użytkownicy mogą również bezpośrednio wyszukiwać certyfikat. Aby wyświetlić właściwości poszczególnych certyfikatów, wybierz certyfikat i kliknij pozycję **Informacje.** 

Instalacja certyfikatu obsługuje obecnie pliki cer i crt. Właściciele urządzeń mogą instalować certyfikaty na komputerze lokalnym i w bieżącym użytkowniku;  Wszyscy inni użytkownicy mogą instalować tylko w programie Current User. Użytkownicy mogą usuwać tylko certyfikaty zainstalowane bezpośrednio z interfejsu użytkownika ustawień. Jeśli certyfikat został zainstalowany za pośrednictwem innych środków, należy go również usunąć za pomocą tego samego mechanizmu.

#### <a name="to-install-a-certificate"></a>Aby zainstalować certyfikat: 

1.  Podłącz urządzenie HoloLens 2 do komputera.
1.  Umieść plik certyfikatu, który chcesz zainstalować, w lokalizacji na urządzeniach HoloLens 2.
1.  Przejdź do **ustawień App > Update & Security > Certificates**, a następnie wybierz pozycję Zainstaluj certyfikat.
1.  Kliknij **pozycję Importuj** plik i przejdź do lokalizacji, w którym zapisano certyfikat.
1.  Wybierz **pozycję Store Location (Lokalizacja sklepu).**
1.  Wybierz **pozycję Magazyn certyfikatów.**
1.  Kliknij przycisk **Zainstaluj**.

Certyfikat powinien być teraz zainstalowany na urządzeniu.

#### <a name="to-remove-a-certificate"></a>Aby usunąć certyfikat: 
1. Przejdź do **ustawień App > Update and Security > Certificates**(Aktualizacje i > zabezpieczeń).
1. Wyszukaj certyfikat według nazwy w polu wyszukiwania.
1. Wybierz certyfikat.
1. Kliknij pozycję **Usuń.**
1. Po **wyświetleniu** monitu o potwierdzenie wybierz pozycję Tak.

![Przeglądarka certyfikatów w aplikacji Ustawienia](images/certificate-viewer-device.jpg)

![Obraz przedstawiający sposób instalowania certyfikatu przy użyciu interfejsu użytkownika certyfikatu](images/certificate-device-install.jpg)

Te informacje można znaleźć później [na nowej stronie Menedżera certyfikatów.](certificate-manager.md)

### <a name="auto-launch-provisioning-from-usb"></a>Automatyczne uruchamianie aprowizowania z dysku USB

- Zautomatyzowane procesy umożliwiające mniejszą interakcję z użytkownikiem, gdy dyski USB z pakietami aprowizowania są używane podczas OOBE.

Przed wydaniem użytkownicy musieli ręcznie uruchomić ekran aprowizowania podczas OOBE, aby aprowizować przy użyciu kombinacji przycisków. Teraz użytkownicy mogą pominąć kombinację przycisków przy użyciu pakietu aprowizowania na dysku pamięci USB. 

1. Podłącz dysk USB za pomocą pakietu aprowizowania podczas pierwszej interakcji ZOBE
1. Gdy urządzenie będzie gotowe do aprowizowania, automatycznie otworzy monit ze stroną aprowizowania. 

Uwaga: Jeśli dysk USB jest podłączony do zasilania podczas rozruchu urządzenia, system OOBE wylicza istniejące urządzenie magazynujące USB, a także będzie obserwować dodatkowe podłączone urządzenia.

Aby uzyskać więcej informacji na temat stosowania pakietów aprowizowania podczas OOBE, odwiedź dokumentację [aprowizowania urządzenia HoloLens.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

Dodatkowe informacje na [temat aprowizowania automatycznego](hololens-provisioning.md#auto-launch-provisioning-from-usb) uruchamiania z dysku USB można znaleźć w dokumentacji aprowowania urządzenia HoloLens.

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>Automatyczne potwierdzanie pakietów aprowizowania w OOBE
- Zautomatyzowany proces umożliwiający mniejszą interakcję z użytkownikiem, gdy zostanie wyświetlona strona Pakiet aprowizowania, automatycznie zastosuje wszystkie wymienione pakiety.

Gdy pojawi się ekran główny aprowizowania, OOBE odliczy 10 sekund przed automatyczne rozpoczęcie stosowania wszystkich pakietów aprowizowania. Użytkownicy mogą nadal [potwierdzić lub anulować](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) w ciągu tych 10 sekund po zweryfikowaniu oczekiwanych pakietów.

### <a name="automatic-provisioning-without-using-ui"></a>Automatyczna aprownia bez użycia interfejsu użytkownika
- Połączone procesy automatyczne w celu zmniejszenia interakcji z urządzeniami w celu aprowacji. 

Łącząc automatyczne uruchamianie aprowizowania z urządzeń USB i automatyczne potwierdzanie pakietów aprowizowania, użytkownik może automatycznie aprowizować urządzenia HoloLens 2 bez korzystania z interfejsu użytkownika urządzenia, a nawet jego noszenia. Możesz nadal używać tego samego dysku USB i pakietu aprowizowania dla wielu urządzeń. Jest to przydatne w przypadku wdrażania wielu urządzeń jednocześnie w tym samym obszarze. 

1. [Utwórz pakiet aprowizowania przy](hololens-provisioning.md) użyciu [programu Windows Configuration Designer.](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 
1. Skopiuj pakiet na dysk pamięci MASOWEJ USB.
1. [Flash your HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions) to 19041.1361 or newer build (Flash your HoloLens 2 to [19041.1361 lub nowsza kompilacja).](https://aka.ms/hololens2previewdownload) 
1. Po [zakończeniu flashowania](https://www.microsoft.com/store/productId/9P74Z35SFRS8) urządzenia przez program Advanced Recovery Companion odłącz kabel USB-C. 
1. Podłącz dysk USB do urządzenia.
1. Po uruchomieniu urządzenia HoloLens 2 w trybie OOBE automatycznie wykryje pakiet aprowizowania na dysku USB i uruchomi stronę aprowizowania.
1. Po upływie 10 sekund urządzenie automatycznie zastosuje pakiet aprowizowania. 

Urządzenie jest teraz skonfigurowane i zostanie na tym ekranie wyświetlany [ekran Inicjowanie obsługi administracyjnej powiodło się.](hololens-provisioning.md#automatic-provisioning-without-using-ui)

### <a name="using-autopilot-with-wi-fi-connection"></a>Używanie rozwiązania Autopilot z Wi-Fi połączenia
- Usunięto potrzebę adapterów USB-C w celu zmniejszenia potrzeb sprzętowych przez włączenie rozwiązania Autopilot do działania Wi-Fi połączonych urządzeń.

Teraz podczas OOBE po połączeniu urządzenia HoloLens 2 z siecią Wi-Fi system OOBE sprawdzi profil rozwiązania Autopilot dla urządzenia. Jeśli zostanie znaleziony, zostanie on użyty do ukończenia pozostałej części przepływu dołączania do i rejestracji w UAD. Innymi słowy, używanie sieci Ethernet do portu USB-C lub Wi-Fi z adapterem USB-C nie jest już wymagane, jednak będą one nadal działać, jeśli zostały podane na początku OOBE. Dowiedz się więcej na [temat rozwiązania Autopilot dla urządzeń HoloLens 2.](hololens2-autopilot.md)

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP and Autopilot
- Urządzenia w dzierżawie organizacji są blokowane dla dzierżawy nawet za pośrednictwem resetowania urządzenia lub reflashu. Z dalszymi zabezpieczeniami przez nie zezwalanie na tworzenie kont w programie za pośrednictwem aprowizowania. 

Urządzenia HoloLens 2 obsługują teraz usługę TenantLockdown CSP od systemu [Windows Holographic w wersji 20H2.](hololens-release-notes.md#windows-holographic-version-20h2) 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) Zasady CSP umożliwiają wiązanie urządzenia HoloLens 2 z rejestracją MDM tylko przy użyciu rozwiązania Autopilot. Gdy węzeł RequireNetworkInOOBE w programie TenantLockdown CSP zostanie ustawiony na wartość true lub false (początkowo ustawioną) na urządzeniu HoloLens 2, ta wartość pozostanie na urządzeniu pomimo ponownego flashowania, aktualizacji systemu operacyjnego itp. 

Gdy węzeł RequireNetworkInOOBE dostawcy CSP TenantLockdown zostanie ustawiony na wartość true na urządzeniach HoloLens 2, system OOBE czeka przez czas nieokreślony na pomyślne pobranie i zastosowanie profilu rozwiązania Autopilot po napięciu sieciowym. 

Gdy węzeł RequireNetworkInOOBE dla dzierżawcy TenantLockdown zostanie ustawiony na wartość true na urządzeniach HoloLens 2, następujące operacje są niedozwolone w OOBE: 
- Tworzenie użytkownika lokalnego przy użyciu aprowizowania środowiska uruchomieniowego 
- Wykonywanie operacji dołączania do usługi Azure AD za pośrednictwem aprowizowania środowiska uruchomieniowego 
- Wybieranie, kto jest właścicielem urządzenia w środowisko OOBE 

#### <a name="how-to-set-this-using-intune"></a>Jak ustawić tę wartość przy użyciu usługi Intune? 
1. Utwórz niestandardowy profil konfiguracji urządzenia OMA URI i określ wartość true dla węzła RequireNetworkInOOBE, jak pokazano poniżej.
Wartość OMA-URI powinna być ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Ustawianie blokady czasowej za pośrednictwem OMA-URI](images/hololens-tenant-lockdown.png)

1. Utwórz grupę i przypisz profil konfiguracji urządzenia do tej grupy urządzeń. 

1. Dokonaj synchronizacji urządzenia HoloLens 2 w grupie utworzonej w poprzednim kroku i wyzwolij synchronizację.  

Sprawdź w portalu usługi Intune, czy konfiguracja urządzenia została pomyślnie zastosowana. Po pomyślnym zastosowaniem tej konfiguracji urządzenia na urządzeniu HoloLens 2 efekty ustawienia TenantLockdown będą aktywne.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Jak zdezsetować usługę TenantLockdown z usługi RequireNetworkInOOBE na urządzeniach HoloLens 2 przy użyciu usługi Intune? 
1. Usuń urządzenie HoloLens 2 z grupy urządzeń, do której wcześniej przypisano utworzoną wcześniej konfigurację urządzenia. 

1. Utwórz niestandardowy profil konfiguracji urządzenia oparty na interfejsie OMA URI i określ wartość false dla wartości RequireNetworkInOOBE, jak pokazano poniżej. Wartość OMA-URI powinna być ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Zrzut ekranu przedstawiający ustawianie wartości false dla ustawienia RequireNetworkInOOBE za pośrednictwem adresu URI OMA w usłudze Intune](images/hololens-tenant-lockdown-false.png)

1. Utwórz grupę i przypisz profil konfiguracji urządzenia do tej grupy urządzeń. 

1. Dokonaj synchronizacji urządzenia HoloLens 2 w grupie utworzonej w poprzednim kroku i wyzwolij synchronizację.

Sprawdź w portalu usługi Intune, czy konfiguracja urządzenia została pomyślnie zastosowana. Po pomyślnym zastosowaniem tej konfiguracji urządzenia na urządzeniu HoloLens 2 efekty ustawienia TenantLockdown będą nieaktywne. 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Co się stanie podczas OOBE, jeśli profil rozwiązania Autopilot zostanie nieprzypisane na urządzeniach HoloLens po tym, jak ustawienie TenantLockdown miało wartość true? 
OOBE będzie czekać przez czas nieokreślony na pobranie profilu rozwiązania Autopilot i zostanie wyświetlone następujące okno dialogowe. Aby usunąć skutki ustawienia TenantLockdown, urządzenie musi najpierw zostać zarejestrowane w pierwotnej dzierżawie przy użyciu rozwiązania Autopilot, a opcja RequireNetworkInOOBE musi zostać cofnięciem ustawienia zgodnie z opisem w poprzednim kroku przed usunięciem ograniczeń wprowadzonych przez usługę TenantLockdown CSP. 

![Widok na urządzeniu dla sytuacji, gdy zasady są wymuszane na urządzeniu.](images/hololens-autopilot-lockdown.png)

Te informacje można teraz znaleźć obok pozostałej części rozwiązania Autopilot w obszarze [Tenantlockdown CSP (Dzierżawa)CSP (CSP) i Autopilot (Autopilot).](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)

### <a name="global-assigned-access--kiosk-mode"></a>Dostęp przypisany globalnie — tryb kiosku
- Zmniejszenie zarządzania tożsamościami w przypadku kiosku przez włączenie nowej metody kiosku, która stosuje tryb kiosku na poziomie systemu.

Ta nowa funkcja umożliwia administratorowi IT skonfigurowanie urządzenia HoloLens 2 pod kątem trybu kiosku z wieloma aplikacjami, który ma zastosowanie na poziomie systemu, nie ma koligacji z żadną tożsamością w systemie i ma zastosowanie do wszystkich osób, które się do niego wyślą. Przeczytaj szczegółowo o tej nowej funkcji w kiosku z dostępem przypisanym globalnie [do urządzenia HoloLens.](hololens-global-assigned-access-kiosk.md)

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Automatyczne uruchamianie aplikacji w trybie kiosku z wieloma aplikacjami 
- Ukierunkowane środowisko z automatycznym uruchamianiem aplikacji, co dodatkowo zwiększa wybór interfejsu użytkownika i aplikacji wybranych dla trybu kiosku.

Dotyczy tylko trybu kiosku z wieloma aplikacjami i tylko 1 aplikacja może zostać wyznaczona do automatycznego uruchamiania przy użyciu wyróżnienia atrybutu poniżej w konfiguracji przypisanego dostępu. 

Aplikacja jest uruchamiana automatycznie po dojściu użytkownika. 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Zmiany zachowania trybu kiosku w celu obsługi awarii
- Bezpieczniejszy tryb kiosku dzięki wyeliminowaniu dostępnych aplikacji w przypadku awarii trybu kiosku. 

Wcześniej po napotkaniu błędów podczas stosowania trybu kiosku urządzenie HoloLens wyświetlało wszystkie aplikacje w menu Start. Teraz w systemie Windows Holographic w wersji 20H2 w przypadku awarii żadne aplikacje nie będą wyświetlane w menu Start, jak pokazano poniżej: 

![Obraz tego, jak wygląda teraz tryb kiosku w przypadku jego awarii.](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>Zasady dotyczące urządzenia HoloLens
- Opcje zarządzania urządzeniami przeznaczone specjalnie dla urządzeń HoloLens utworzonych do zarządzania urządzeniem. 

Utworzono nowe zasady rzeczywistości mieszanej dla urządzeń HoloLens 2 na platformie Windows Holographic w wersji 20H2. Nowe ustawienia z możliwością kontrolowania obejmują: ustawienie jasność, ustawienie głośności, wyłączenie rejestrowania dźwięku w przechwytywaniach rzeczywistości mieszanej, ustawienie czasu zbierania danych diagnostycznych i pamięć podręczną członkostwa w grupie usługi AAD.  

| Nowe zasady dotyczące urządzenia HoloLens                                | Opis                                                                               | Uwagi                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | Umożliwia wyłączone przyciski jasność, więc naciśnięcie jej nie zmienia jasność.       | 1 Tak, 0 Nie (ustawienie domyślne)                                                |
| MixedReality\VolumeButtonDisabled                  | Umożliwia wyłączone przyciski regulacji głośności, tak aby ich naciśnięcie nie zmieniało głośności.               | 1 Tak, 0 Nie (ustawienie domyślne)                                                |
| MixedReality\MicrophoneDisabled                    | Wyłącza mikrofon, aby na urządzeniach HoloLens 2 nie było możliwe nagrywanie dźwięku.                      | 1 Tak, 0 Nie (ustawienie domyślne)                                                |
| MixedReality\FallbackDiagnostics                   | Steruje zachowaniem funkcji zbierania dzienników diagnostycznych.                               | 0 Wyłączone, 1 włączone dla właścicieli urządzeń, 2 włączone dla wszystkich (ustawienie domyślne) |
| MixedReality\HeadTrackingMode                      | Zarezerwowane do użytku w przyszłości.                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | Określa, ile dni pamięci podręcznej członkostwa w grupie usługi Azure AD jest używane w przypadku grup usługi Azure AD przeznaczonych dla kiosku. | Sprawdź poniżej.                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Buforowanie członkostwa w grupie usługi Azure AD dla kiosku w trybie offline
- Włączono kioski offline do użytku z grupami usługi AAD przez maksymalnie 60 dni.

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

### <a name="new-device-restriction-policies-for-hololens-2"></a>Nowe zasady ograniczeń urządzeń HoloLens 2
- Umożliwia użytkownikom zarządzanie określonymi zasadami zarządzania urządzeniami, takimi jak blokowanie dodawania lub usuwania pakietów aprowizowania.

Nowo włączone zasady, które umożliwiają obsługę większej liczby opcji zarządzania urządzeniami HoloLens 2. 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [Konfigurowanie strefy czasowej](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

Te dwie nowe zasady dla pakietów AllowAddProvisioningPackage i AllowRemoveProvisioningPackage są dodawane do naszych typowych [ograniczeń dotyczących urządzeń.](hololens-common-device-restrictions.md)

> [!NOTE]
> W odniesieniu do [funkcji RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)urządzenie HoloLens będzie obsługiwać tylko konfigurację ./Vendor/MSFT/RemoteLock/Lock. Konfiguracje związane z kodem PIN, takie jak resetowanie i odzyskiwanie, nie są obsługiwane.

### <a name="new-power-policies-for-hololens-2"></a>Nowe zasady zasilania dla urządzenia HoloLens 2
- Więcej opcji, które można uzyskać, gdy urządzenie HoloLens jest w trybie uśpienia lub blokuje się za pośrednictwem zasad zasilania. 

Te nowo dodane zasady umożliwiają administratorom kontrolowanie stanów zasilania, takich jak limit czasu bezczynności. Aby dowiedzieć się więcej na temat poszczególnych zasad, kliknij link dla tych zasad.

|     Link do dokumentacji zasad                |     Uwagi                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     Przykładowa wartość do użycia w programie Windows Configuration Designer, tj.  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     Przykładowa wartość do użycia w programie Windows Configuration Designer, tj.  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  Przykładowa wartość do użycia w programie Windows Configuration Designer, tj. 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     Przykładowa wartość do użycia w programie Windows Configuration Designer, tj. 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     Przykładowa wartość do użycia w programie Windows Configuration Designer, tj.   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     Przykładowa wartość do użycia w programie Windows Configuration Designer, tj.  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

Te dwie nowe zasady dla usług DisplayOffTimeoutOnBattery i DisplayOffTimeoutPluggedIn są dodawane do naszych typowych [ograniczeń dotyczących urządzeń.](hololens-common-device-restrictions.md)

> [!NOTE]
> Aby zapewnić spójne środowisko pracy na urządzeniach HoloLens 2, upewnij się, że wartości dla obu właściwości DisplayOffTimeoutOnBattery i StandbyTimeoutOnBattery są ustawione jako taka sama wartość. To samo dotyczy funkcji DisplayOffTimeoutPluggedIn i StandbyTimeoutPluggedIn. Aby uzyskać więcej informacji na temat [nowoczesnego wstrzymania,](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) zobacz Wyświetlanie, uśpienie i hibernacja czasomierzy bezczynnych.

### <a name="newly-enabled-update-policies-for-hololens"></a>Nowo włączone zasady aktualizacji dla urządzenia HoloLens
- Więcej opcji instalacji aktualizacji lub wyłączenia przycisku Wstrzymaj aktualizacje w celu zapewnienia aktualizacji.

Te zasady aktualizacji są teraz włączone na urządzeniach HoloLens 2:
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

Szczegółowe informacje na temat tych zasad aktualizacji i sposobu ich używania na urządzeniach HoloLens można znaleźć tutaj: Manage HoloLens updates (Zarządzanie [aktualizacjami urządzenia HoloLens).](hololens-updates.md)

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>Widoczność strony Włączone ustawienia dla urządzenia HoloLens 2
- Zwiększona kontrola interfejsu użytkownika w aplikacji Ustawienia, co może być mylone z wyświetlaniem ograniczonego wyboru stron.

Teraz włączyliśmy zasady, które umożliwiają administratorom IT uniemożliwić widoczność lub dostępność określonych stron w aplikacji Ustawienia systemowe lub na ich użycie dla wszystkich stron z wyjątkiem określonych. Aby dowiedzieć się, jak w pełni dostosować tę funkcję, kliknij poniższy link.

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

Aby dowiedzieć się, które ustawienia strony można dostosować na urządzeniach HoloLens 2, odwiedź naszą [stronę Ustawienia URI](settings-uri-list.md). 
 
![Zrzut ekranu przedstawiający modyfikację godzin aktywnego działania w aplikacji Ustawienia](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>Tryb badań
W trybie badań urządzenie HoloLens 2 staje się narzędziem do badania obrazów. W porównaniu z poprzednimi wersjami tryb badań dla urządzenia HoloLens 2 ma następujące zalety:
-   Oprócz czujników dostępnych w trybie badania urządzenia HoloLens (1. generacji) zapewniamy teraz dostęp do czujników IMU, w tym przyspieszeniomierza, żyrogramu i plombometru.
-   Urządzenie HoloLens 2 udostępnia nowe możliwości, których można używać razem z trybem badań. W szczególności dostęp do określonych interfejsów API do śledzenia rąk i śledzenia oczu, które mogą dostarczać bogatszy zestaw eksperymentów.

Badacze mają teraz możliwość włączenia trybu badań na urządzeniach HoloLens w celu uzyskania dostępu do wszystkich tych strumieni zewnętrznych czujników nieprzetworzonych obrazów. Tryb badań dla urządzenia HoloLens 2 zapewnia również dostęp do odczytów przyspieszeniomierza, gyroscope i krokomierza. Aby chronić prywatność użytkowników, nieprzetworzone obrazy kamer śledzące wzrok nie są dostępne za pośrednictwem trybu badania, ale kierunek spojrzenia jest dostępny za pośrednictwem istniejących interfejsów API.

Zapoznaj się z [dokumentacją trybu badań,](https://docs.microsoft.com/windows/mixed-reality/research-mode) aby uzyskać więcej informacji technicznych.

### <a name="recording-length-increased"></a>Długość rejestrowania zwiększona
Dzięki opiniom klientów zwiększyliśmy długość rejestrowania przechwytywania [rzeczywistości mieszanej.](holographic-photos-and-videos.md) Przechwytywanie rzeczywistości mieszanej nie będzie domyślnie ograniczone do 5 minut, ale zamiast tego obliczy maksymalną długość rejestrowania na podstawie dostępnego miejsca na dysku. Urządzenie oszacowa maksymalny czas trwania nagrywania wideo na podstawie dostępnego miejsca na dysku do 80% całkowitego miejsca na dysku.

> [!NOTE]
> Urządzenie HoloLens użyje domyślnej długości nagrania wideo (5 minut), jeśli wystąpi jedna z następujących sytuacji:
> - Szacowany maksymalny czas trwania rejestrowania jest mniejszy niż domyślne 5 minut.
> - Dostępne miejsce na dysku jest mniejsza niż 20% całkowitego miejsca na dysku.

Pełne wymagania można znaleźć w naszej dokumentacji [dotyczącej zdjęć i filmów wideo](holographic-photos-and-videos.md#maximum-recording-length) na urządzeniach holograficznych. 

### <a name="improvements-and-fixes-in-the-update"></a>Ulepszenia i poprawki w aktualizacji:
- Więcej ekranów w trybie OOBE jest teraz w trybie ciemnym.
- Więcej informacji powinno wskazać najnowsze zasady zachowania poufności informacji w trybie online.
- Rozwiązano problem, który nie pozwalał użytkownikom aprowizować profilów sieci VPN za pośrednictwem pakietów aprowizowania.
- Rozwiązano problem z konfiguracją serwera proxy dla połączenia sieci VPN.
- Zaktualizowano zasady, aby wyłączyć wyliczanie funkcji USB za pośrednictwem funkcji MDM dla NCM dla AllowUsbConnection.
- Rozwiązano problem, który uniemożliwiał wyświetlanie urządzenia HoloLens w u użytkownikach Eksplorator plików za pośrednictwem protokołu MTP (Media Transfer Protocol), gdy urządzenie zostało ustawione jako kiosk z jedną [aplikacją.](hololens-kiosk.md) Należy pamiętać, że usługę MTP (i ogólnie połączenie USB) można wyłączyć przy użyciu [zasad AllowUSBConnection.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
- Rozwiązano problem, który pozwalał na poprawne skalowanie ikon menu Start w trybie kiosku.
- Rozwiązano problem z buforowaniem HTTP zakłócanym przez tryb kiosku skierowany do grup usługi Azure AD.
- Rozwiązano problem, który mógł dotyczyć użytkowników, którzy nie mogli używać przycisku Parowanie po włączeniu trybu dewelopera z pakietami aprowizowania, chyba że wyłączyli i ponownie włączyli tryb dewelopera.

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows Holographic, wersja 1903 — aktualizacja z listopada 2020 r.
- Kompilacja 18362.1085

Ta comiesięczna aktualizacja jakości nie zawiera żadnych notowalnych zmian. Zachęcamy do wypróbowania najnowszej kompilacji wersji funkcji Systemu Windows Holographic w wersji 20H2.

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
- Ta wersja zawiera poprawkę wykrywania serwera proxy NCSI w celu rozwiązania problemu z niepowodzeniem wykrywania Internetu za pośrednictwem serwera proxy sieci. Usługa NCSI może używać serwera proxy komputera i serwera proxy dla profilu do wykrywania łączności z Internetem. W przyszłej wersji serwer proxy dla 1 użytkownika będzie obsługiwany przez interfejs NCSI.
- Na większości Windows Mixed Reality wektor kierunku do przodu jest równoległy do ziemi, gdy głowy użytkownika znajduje się w pozycji neutralnej do przodu. Jednak wcześniejsze wersje urządzenia HoloLens 2 wyrównały wektor do paneli wyświetlania, który jest pochylony o kilka stopni w dół w stosunku do idealnej orientacji. W nowszej wersji urządzenia HoloLens 2 rozwiązano ten problem, aby zapewnić spójność semantyczną między kształtami.
- Zwiększona niezawodność śledzenia rąk, która spowoduje mniejszą liczbę strat śledzenia w określonych scenariuszach.
- Ta wersja zawiera poprawkę poprawiającą jakość znaczników czasu dźwięku, która może mieć wpływ na problemy z przechwytywaniem wideo.

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic, wersja 1903 — aktualizacja z września 2020 r.
- Kompilacja 18362.1079

Ulepszenia i poprawki w aktualizacji:

- Na większości Windows Mixed Reality wektor kierunku do przodu jest równoległy do ziemi, gdy głowy użytkownika znajduje się w pozycji neutralnej do przodu. Jednak wcześniejsze wersje urządzenia HoloLens 2 wyrównały wektor do paneli wyświetlania, który jest pochylony o kilka stopni w dół w stosunku do idealnej orientacji. W nowszej wersji urządzenia HoloLens 2 rozwiązano ten problem, aby zapewnić spójność semantyczną między kształtami.
- Zwiększona niezawodność śledzenia rąk, która spowoduje mniejszą liczbę strat śledzenia w określonych scenariuszach.

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic, wersja 2004 — aktualizacja z sierpnia 2020 r.
- Kompilacja 19041.1113

Ulepszenia i poprawki w aktualizacji:

- Aplikacja Ustawienia nie będzie już śledzić użytkownika w doświadczeniach dotyczących rejestracji irysów ani śledzenia oczu.
- Usunięto usterkę, która oznaczała, że zastosowanie pakietu aprowizowania podczas OOBE, który zmienia nazwę urządzenia i wykonuje inne akcje (takie jak łączenie się z siecią), nie może wykonać innych akcji po ponownym uruchomieniu urządzenia z powodu zmiany nazwy.
- Zmodyfikowano schemat kolorów początkowych przepływów konfiguracji urządzenia, aby poprawić jakość wizualizacji.

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows Holographic, wersja 1903 — aktualizacja z sierpnia 2020 r.
- Kompilacja 18362.1074

Ta comiesięczna aktualizacja jakości nie zawiera żadnych notowalnych zmian. Zachęcamy do wypróbowania naszych najnowszych kompilacji dla systemu Windows Holographic w wersji 2004.

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows Holographic, wersja 2004 — aktualizacja z lipca 2020 r.
- Kompilacja 19041.1109

Ulepszenia i poprawki w aktualizacji:

- Deweloperzy mogą teraz wybierać między włączeniem lub wyłączeniem Portal urządzeń wymagać bezpiecznego połączenia.
- Poprawiono niezawodność uruchamiania aplikacji po aktualizacjach systemu operacyjnego.
- Zmieniono domyślną jasność skrzynki odbiorczej na 100 procent.
- Rozwiązano problem z przekazywaniem HTTPS dla urządzenia Portal urządzeń z systemem Windows holoLens 2.

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows Holographic, wersja 1903 — aktualizacja z lipca 2020 r.
- Kompilacja 18362.1071

Ulepszenia i poprawki w aktualizacji:

- Rozwiązano problem, który mógł powodować zniknięcie hologramów w aplikacjach unity podczas utraty lub odzyskania śledzenia.
- Rozwiązano problem, który powodował, że wyłączne aplikacje urządzenia HoloLens ulegały awarii z powrotem do powłoki podczas korzystania z emulatora urządzenia HoloLens z przyspieszeniem sprzętowym na niektórych urządzeniach.
- Rozwiązano problem dotyczący przekazywania HTTPS dla Portal urządzeń z systemem Windows na urządzeniach HoloLens 2.

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic, wersja 2004 — aktualizacja z czerwca 2020 r.
- Kompilacja 19041.1106

Ulepszenia i poprawki w aktualizacji:

- Niestandardowe rejestratory MRC mają teraz nowe wartości domyślne dla niektórych właściwości, jeśli nie zostały określone.
  - W przypadku *efektu wideo MRC:*
    - PreferredOgramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (immersyjny zestaw nagłowny))
  - W przypadku *efektu dźwięku MRC:*
    - LoopbackGain (bieżąca wartość "App Audio Gain" na stronie Przechwytywanie rzeczywistości mieszanej w Portal urządzeń z systemem Windows)
    - MicrophoneGain (bieżąca wartość "Zysk dźwięku mikrofonu" na stronie Przechwytywanie rzeczywistości mieszanej w Portal urządzeń z systemem Windows)
- Usunięto usterkę w celu poprawy jakości dźwięku w scenariuszach przechwytywania rzeczywistości mieszanej. W szczególności ta poprawka powinna wyeliminować błędy audio podczas rejestrowania podczas wyświetlania **menu** Start.
- Poprawiono stabilność hologramów w zarejestrowanych filmach wideo.
- Rozwiązano problem, który miał miejsce, gdy przechwytywanie rzeczywistości mieszanej nie mogło nagrać wideo po tym, jak urządzenie było w stanie wstrzymania przez wiele dni.
- Interfejs API HolographicSpace.UserPresence jest zwykle wyłączony dla aplikacji unity. Takie zachowanie pozwala uniknąć problemu, który powodował wstrzymanie niektórych aplikacji po przerzuceniu funkcji odszybłej, nawet jeśli ustawienie "uruchom w tle" zostało włączone. Interfejs API jest teraz włączony dla aparatu Unity w wersji 2018.4.18 i nowszych oraz 2019.3.4 i nowszych.
- Gdy uzyskujesz dostęp Portal urządzeń za pośrednictwem Wi-Fi sieci Web, przeglądarka internetowa może uniemożliwić dostęp z powodu nieprawidłowego certyfikatu. Przeglądarka może zgłosić błąd, taki jak "ERR_SSL_PROTOCOL_ERROR", nawet jeśli certyfikat urządzenia był wcześniej zaufany. W takim przypadku nie można przejść do Portal urządzeń, ponieważ nie ma możliwości ignorowania ostrzeżeń zabezpieczeń. Ta aktualizacja rozwiązała problem. Jeśli certyfikat urządzenia został wcześniej pobrany i zaufany na komputerze w celu usunięcia ostrzeżeń o zabezpieczeniach przeglądarki i wystąpi błąd protokołu SSL, nowy certyfikat musi zostać pobrany i zaufany, aby rozwiązać problem z ostrzeżeniami o zabezpieczeniach przeglądarki.
- Włączono możliwość tworzenia pakietu aprowizowania środowiska uruchomieniowego, który umożliwia zainstalowanie aplikacji przy użyciu pakietów MSIX.
- Dodano ustawienie **w**  >    >  **hologramach systemu ustawień,** które umożliwia użytkownikom automatyczne usuwanie wszystkich hologramów Mixed Reality domu po zamknięciu urządzenia.
- Rozwiązano problem, który powodował, że aplikacje urządzenia HoloLens, które zmieniają format pikseli, renderują kolor czarny w emulatorze urządzenia HoloLens.
- Usunięto usterkę, która powodowała awarię podczas logowania irysów.
- Rozwiązano problem z wielokrotnym pobieraniem ze sklepu dla już bieżących aplikacji.
- Usunięto usterkę uniemożliwiającą wielokrotne otwieranie aplikacji Microsoft Edge immersywnych.
- Rozwiązano problem z uruchamianiem aplikacji Photos podczas początkowych uruchomień po aktualizacji z wersji 1903.
- Zwiększona wydajność i niezawodność.

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows Holographic, wersja 1903 — aktualizacja z czerwca 2020 r.
- Kompilacja 18362.1064

Ulepszenia i poprawki w aktualizacji:

- Niestandardowe rejestratory MRC mają nowe wartości domyślne dla niektórych właściwości, jeśli nie zostały określone.
  - W przypadku *efektu wideo MRC:*
    - PreferredOgramPerspective (1 PhotoVideoCamera)
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (immersyjny zestaw nagłowny))
  - W przypadku *efektu dźwięku MRC:*
    - LoopbackGain (bieżąca wartość "App Audio Gain" na stronie Przechwytywanie rzeczywistości mieszanej w Portal urządzeń z systemem Windows)
    - MicrophoneGain (bieżąca wartość "Zysk dźwięku mikrofonu" na stronie Przechwytywanie rzeczywistości mieszanej w Portal urządzeń z systemem Windows)
- Interfejs API HolographicSpace.UserPresence jest zwykle wyłączony dla aplikacji unity. Takie zachowanie pozwala uniknąć problemu, który powoduje wstrzymanie niektórych aplikacji po przerzuceniu funkcji odszybłej, nawet jeśli ustawienie do uruchomienia w tle jest włączone. Interfejs API jest teraz włączony dla aparatu Unity w wersji 2018.4.18 i nowszych oraz 2019.3.4 i nowszych.
- Rozwiązano problem, który powodował, że aplikacje urządzenia HoloLens, które zmieniają format pikseli na czarny, w emulatorze urządzenia HoloLens.
- Rozwiązano problem z uruchamianiem aplikacji Photos podczas początkowych uruchomień po aktualizacji z wersji 1903.

## <a name="windows-holographic-version-2004"></a>Windows Holographic, wersja 2004  
- Kompilacja — 19041.1103

Główna aktualizacja oprogramowania dla urządzenia HoloLens 2, Windows Holographic w wersji *2004* z maja 2020 r. zawiera wiele nowych, interesujących możliwości, takich jak obsługa technologii Windows Autopilot, tryb ciemny aplikacji, obsługa interfejsu USB Ethernet dla hotspotów 5G/LTE i wiele innych. Aby zaktualizować program do najnowszej wersji, otwórz aplikację Ustawienia, przejdź do witryny Update & Security i wybierz przycisk   Sprawdź **** **aktualizacje.**   

|             Cecha                              |          Opis                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          Wstępne konfigurowanie i bezproblemowe konfigurowanie nowych urządzeń do produkcji przy użyciu rozwiązania Windows AutoPilot                 |
|       Obsługa fido 2                             |          Obsługa kluczy zabezpieczeń FIDO2 w celu umożliwienia szybkiego i bezpiecznego uwierzytelniania dla urządzeń udostępnionych            |
|       Ulepszono aprowizowanie                      |          Bezproblemowe stosowanie pakietu aprowizowania z dysku USB do urządzenia HoloLens                              |
|       Stan instalacji aplikacji                 |          Sprawdzanie stanu instalacji w aplikacji Ustawienia dla aplikacji zostało wypchnięte na urządzenie HoloLens 2 za pośrednictwem rozwiązania MDM               |
|       Dostawcy usług konfiguracji (CSP)   |          Dodano nowych dostawców usług konfiguracji w celu zwiększenia możliwości kontroli administracyjnej                 |
|       Obsługa standardu USB 5G/LTE                       |          Rozszerzona funkcja ethernetu USB umożliwia obsługę sieci 5G/LTE                                    |
|       Tryb ciemnej aplikacji                              |          Tryb ciemny aplikacji dostępny dla aplikacji, które obsługują tryb ciemny i jasny, co poprawia środowisko wyświetlania        |
|       Polecenia głosowe                             |          Obsługa dodatkowych poleceń głosowych systemu do sterowania urządzeniem HoloLens bez rąk                           |
|       Ulepszenia śledzenia rąk                 |          Ulepszenia śledzenia rąk sprawiają, że przyciski i interakcje z planszą 2D są dokładniejsze                        |
|       Ulepszenia i poprawki dotyczące jakości                 |          Różne ulepszenia wydajności i niezawodności systemu na platformie                            |

### <a name="support-for-windows-autopilot"></a>Obsługa Windows Autopilot

Windows Autopilot urządzenia HoloLens 2 umożliwia kanałowi sprzedaży urządzeń wstępne zarejestrowanie urządzenia HoloLens w dzierżawie usługi Intune. Po przybyciu urządzenia są one gotowe do samodzielnego wdrożenia jako urządzenia udostępnione w ramach dzierżawy. Aby skorzystać z samodzielnego wdrażania, urządzenie musi połączyć się z siecią podczas pierwszego ekranu w konfiguracji przy użyciu połączenia USB-C-to-Ethernet.

Gdy użytkownik rozpocznie proces samodzielnego wdrażania rozwiązania Autopilot, proces ten kończy się następującymi krokami:

1. Dołącz urządzenie do usługi Azure Active Directory (Azure AD).
1. Użyj usługi Azure AD, aby zarejestrować urządzenie w Microsoft Intune (lub innej usłudze MDM).
1. Pobierz zasady, certyfikaty i profile sieciowe dla urządzeń docelowych.
1. Aprowizuj urządzenie.
1. Prezentuj użytkownikowi ekran logowania.

Dowiedz się więcej z [przewodnika Windows Autopilot dla urządzenia HoloLens 2 .](https://docs.microsoft.com/hololens/hololens2-autopilot)

*Skontaktuj się z menedżerem ds. konta, aby teraz dołączyć do wersji zapoznawczej rozwiązania AutoPilot. Wkrótce rozpocznie się wysyłka urządzeń gotowych do rozwiązania Autopilot.*

### <a name="fido2-security-key-support"></a>Obsługa kluczy zabezpieczeń FIDO2

Niektórzy użytkownicy współdzielą urządzenie HoloLens z innymi w środowisku służbowym. Dlatego ważne jest, aby użytkownicy z łatwością wpisywali długie nazwy użytkowników i hasła. Usługa Fast Identity Online (FIDO) umożliwia wszystkim osobom w organizacji (dzierżawie usługi Azure AD) bezproblemowe logowanie się do urządzenia HoloLens bez wprowadzania nazwy użytkownika lub hasła.

Klucze zabezpieczeń FIDO2 to metoda uwierzytelniania bez hasła oparta na standardach "unphishable", która może mieć dowolną formę. FIDO to otwarty standard uwierzytelniania bez hasła. Dzięki temu użytkownicy i organizacje mogą logować się do swoich zasobów bez nazwy użytkownika ani hasła. Zamiast tego używają zewnętrznego klucza zabezpieczeń lub klucza platformy wbudowanego w urządzenie.

Aby rozpocząć pracę, zobacz Włączanie logowania za pomocą klucza [zabezpieczeń bez hasła.](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>Ulepszona rejestracja mdm za pośrednictwem pakietu aprowizowania

Pakiety aprowizowania umożliwiają ustawianie konfiguracji urządzenia HoloLens za pomocą pliku konfiguracji, a nie za pośrednictwem out-of-box experience urządzenia HoloLens. Wcześniej pakiety aprowizowania trzeba było skopiować do pamięci wewnętrznej urządzenia HoloLens. Teraz można je znaleźć na dysku USB, aby łatwiej było ich użyć ponownie na wielu urządzeniach HoloLens i można aprowizować urządzenia równolegle. Pakiety aprowizowania obsługują teraz również pole do rejestrowania w zarządzaniu urządzeniami, dzięki czemu po aprowizeniu nie ma żadnej ręcznej konfiguracji.

Aby ją wypróbować:

1. Pobierz najnowszą wersję programu Windows Configuration Designer ze Sklepu Windows na komputer.
1. Wybierz pozycję **Aprowizuj urządzenia**  >  **HoloLens Aprowizuj urządzenia HoloLens 2.**
2. Skompilowanie profilu konfiguracji. Następnie skopiuj wszystkie pliki, które zostały utworzone na urządzenie magazynujące USB-C.
3. Podłącz urządzenie USB-C do dowolnego nowo flashowanych urządzeń HoloLens. Następnie naciśnij przyciski **zasilania regulacji głośności,**  +   aby zastosować pakiet aprowizowania.

### <a name="line-of-business-application-install-status"></a>Stan instalacji aplikacji biznesowych

Wdrażanie aplikacji MDM i zarządzanie nimi dla aplikacji biznesowych ma kluczowe znaczenie dla urządzenia HoloLens. Administratorzy i użytkownicy muszą wyświetlić stan instalacji aplikacji na potrzeby inspekcji i diagnostyki. W tej wersji dodaliśmy więcej szczegółów w ustawieniach Konta Dostęp do  >    >  **pracy lub nauki** Kliknij informacje  >  **o**  >  **koncie**.

### <a name="additional-csps-and-policies"></a>Dodatkowi CSP i zasady

Dostawca [usług konfiguracji (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) to interfejs do odczytywania, konfigurowania, modyfikowania lub usuwania ustawień konfiguracji na urządzeniu. W tej wersji dodajemy obsługę większej liczby zasad w celu zwiększenia administratorów kontroli nad wdrożonych urządzeń HoloLens. Aby uzyskać listę CSP obsługiwanych przez urządzenie HoloLens, zobacz [NetworkQoSPolicy CSP (NetworkQoSPolicy CSP).](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)

Nowość w tej wersji:

**Dostawca CSP zasad** 

Dostawca usługi konfiguracji zasad umożliwia przedsiębiorstwu konfigurowanie zasad na urządzeniach z systemem Windows. W tej wersji dodaliśmy nowe zasady dla urządzenia HoloLens, które są wymienione tutaj. Aby dowiedzieć się więcej, zobacz [Policy CSPs supported by HoloLens 2 (Zasady CSP obsługiwane przez urządzenie HoloLens 2).](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)  

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

Dostawca usługi konfiguracji NetworkQoSPolicy tworzy zasady jakości usług (QoS) sieci. Zasady QoS tworzą zestaw akcji dla ruchu sieciowego na podstawie zestawu pasujących warunków. Aby dowiedzieć się więcej, [zobacz NetworkQoSPolicy CSP (NetworkQoSPolicy CSP).](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>Rozszerzona obsługa ethernetu USB dla urządzeń z tethered 5G/LTE

Dodano obsługę włączania niektórych mobilnych urządzeń bezprzewodowych, takich jak telefony 5G/LTE i hotspoty Wi-Fi, gdy są one podłączane do urządzenia HoloLens 2 za pośrednictwem portu USB. Te urządzenia są teraz wyświetlane w **ustawieniach sieciowych jako** inne połączenie Ethernet. (Mobilne urządzenia komórkowe, które wymagają sterownika zewnętrznego, nie są obsługiwane). Ta funkcja umożliwia połączenia o wysokiej przepustowości, Wi-Fi nie są dostępne, Wi-Fi tethering nie jest wystarczająco performantny. Aby dowiedzieć się więcej o obsługiwanych urządzeniach USB, zobacz Łączenie z urządzeniami Bluetooth i [USB-C.](https://docs.microsoft.com/hololens/hololens-connect-devices)  

### <a name="hand-tracking-improvements"></a>Ulepszenia śledzenia rąk

Ta wersja zawiera kilka ulepszeń śledzenia ręcznego:

- **Stabilność punktu odniesienia:** System opiera się teraz na kącie palca indeksu, gdy zostanie przycięty przez gałę. Ta zmiana zwiększa dokładność wypychania przycisków, typów, przewijania zawartości i nie tylko. 
- **Zmniejszenie przypadkowych nacięć w powietrzu:** Ulepszyliśmy wykrywanie gestu naciśnięcia w powietrzu. Teraz istnieje mniej przypadkowych aktywacji w kilku typowych scenariuszach, na przykład po pochylić ręce po stronach.
- **Niezawodność przełącznika użytkownika:** System jest teraz szybszy i bardziej niezawodny podczas aktualizowania rozmiaru rąk podczas udostępniania urządzenia.
- **Ograniczona liczba kradzieży rąk:** Ulepszyliśmy obsługę przypadków, w których czujniki mają więcej niż dwie dłonie. Jeśli wiele osób pracuje blisko siebie, istnieje teraz znacznie mniejsze prawdopodobieństwo, że śledzona ręka "przeskoczy" od użytkownika do ręki kogoś innego w scenie.
- **Niezawodność systemu:** Rozwiązano problem, który powodował, że śledzenie rąk przestało działać, gdy urządzenie jest pod dużym obciążeniem.

### <a name="dark-mode"></a>Tryb ciemny

Wiele aplikacji systemu Windows obsługuje teraz tryb ciemny i jasny. Użytkownicy urządzenia HoloLens 2 mogą wybrać tryb domyślny dla aplikacji, które obsługują oba te urządzenia. Po aktualizacji domyślny tryb aplikacji to "ciemny", ale możesz łatwo zmienić to ustawienie: Przejdź do ustawień Kolory systemowe Wybierz  >    >    >  **domyślny tryb aplikacji.** 

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

![Okna trybu ciemnego kafelkowane](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>Systemowe polecenia głosowe

Teraz można używać poleceń głosowych z dowolną aplikacją na urządzeniu. Aby uzyskać więcej informacji, zobacz [Używanie głosu do obsługi urządzenia HoloLens.](https://docs.microsoft.com/hololens/hololens-cortana) Zobacz też [obsługiwane języki dla urządzenia HoloLens 2.](https://docs.microsoft.com/hololens/hololens2-language-support)  

### <a name="cortana-updates"></a>Aktualizacje Cortany

Zaktualizowana aplikacja integruje się z Microsoft 365, aby ułatwić ci pracę na różnych urządzeniach (obecnie tylko US-English). Na urządzeniu HoloLens 2 Cortana nie obsługuje już niektórych poleceń specyficznych dla urządzenia, takich jak dostosowywanie głośności lub ponowne uruchamianie. Te opcje są teraz obsługiwane przez nowe systemowe polecenia głosowe. Dowiedz się więcej o nowej aplikacji Cortany z naszego [bloga](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).

### <a name="quality-improvements-and-fixes"></a>Ulepszenia i poprawki dotyczące jakości

Ulepszenia i poprawki także w aktualizacji:  
- Wprowadzono aktywny system natłoków wyświetlania. Ta funkcja poprawia stabilność i wyrównanie hologramów. Teraz pozostają one na miejscu podczas przesuwania głowy z boku na bok.
- Usunięto usterkę, która Wi-Fi przesyłania strumieniowego na urządzenie HoloLens okresowo zakłócała działanie. Jeśli aplikacja wskazuje, że wymaga przesyłania strumieniowego z małym opóźnieniem, zaim implementuj poprawkę, wywołując [funkcję SetSocketMediaStreamingMode](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).
- Rozwiązano problem z zawieszaniem się urządzenia, które wystąpiło podczas przesyłania strumieniowego w trybie badań.
- Usunięto usterkę, która w niektórych przypadkach pokazywała, że właściwy użytkownik nie był wyświetlany na ekranie logowania podczas wznawiania sesji.
- Rozwiązano problem, który mógł dotyczyć sytuacji, w której użytkownicy nie mogli eksportować dzienników mdm za pomocą **ustawień**.
- Rozwiązaliśmy problem, który miał miejsce, gdy dokładność śledzenia oka natychmiast po instalacji out-of-box mogła być niższa niż oczekiwano.
- Rozwiązano problem, który dotyczył sytuacji, w której podsystem śledzenia oczu nie może zainicjować lub wykonać operacji śledzenia w określonych warunkach.
- Rozwiązano problem, który oznaczał, że w przypadku już skalibrowanego użytkownika był wyświetlany monit o wzrok.
- Rozwiązano problem, który miał miejsce, gdy sterownik ulegał awarii podczas awarii oczu.
- Rozwiązaliśmy problem, który mógł powodować 60-sekundowe naciśnięcie przycisku zasilania i awarię powłoki.
- Ulepszona stabilność buforów głębokości.
- Dodano **przycisk Udostępnij** w Centrum opinii, aby użytkownicy mogą łatwiej udostępniać opinie.
- Usunięto usterkę, przez która program RoboRaid nie był poprawnie instalowany.

### <a name="known-issues"></a>Znane problemy

- Problem z językiem systemu zh-CN uniemożliwia poleceń głosowych przechwytywanie rzeczywistości mieszanej lub wyświetlanie adresu IP urządzenia.
- Problem wymaga uruchomienia aplikacji Cortany po uruchomieniu urządzenia w celu używania aktywacji głosowej "Hej Cortana". Jeśli zaktualizowano z kompilacji 18362, możesz również zobaczyć drugi kafelek aplikacji dla poprzedniej wersji aplikacji Cortany, który nie działa już w sekcji **Uruchamianie.**

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic, wersja 1903 — aktualizacja z maja 2020 r. 
- Kompilacja 18362.1061

Ta comiesięczna aktualizacja jakości nie zawiera żadnych notowalnych zmian, ponieważ zespół pracował nad aktualizacją systemu Windows Holographic w wersji 2004 May Update, zgodnie z wcześniejszym opisem.

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic, wersja 1903 — aktualizacja z kwietnia 2020 r.
- Kompilacja 18362.1059

**Tryb ciemny dla obsługiwanych aplikacji** 

Wiele aplikacji systemu Windows obsługuje tryb ciemny i jasny. Klienci urządzenia HoloLens 2 mogą teraz wybrać tryb domyślny dla aplikacji, które obsługują oba schematy kolorów. Na podstawie opinii klientów ustawiamy domyślny tryb aplikacji na "ciemny", ale możesz łatwo zmienić to ustawienie w dowolnym momencie: Przejdź do opcji Ustawienia **> System > Colors** i znajdź pozycję "Wybierz domyślny tryb **aplikacji".**

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

- Tymczasowo wyłączono interfejs API HolographicSpace.UserPresence dla aplikacji aparatu Unity. Ta zmiana pozwala uniknąć problemu, który powodował, że niektóre aplikacje były wstrzymywane po przerzuceniu funkcji odszybłej, nawet jeśli ustawienie "uruchom w tle" zostało włączone.
- Usunięto losową awarię HUP spowodowaną przez śledzenie rąk, w której użytkownik zauważył zablokowanie interfejsu użytkownika, a następnie powrót do powłoki po kilku sekundach.
- Ulepszono śledzenie rąk, dzięki czemu podczas przesuwania palcem wskazującym górna część tego palca jest mniej prawdopodobne nieoczekiwanego zwinięcia.
- Zwiększona niezawodność śledzenia głowy, mapowania przestrzennego i innych środowisk uruchomieniowych.

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic, wersja 1903 — aktualizacja ze stycznia 2020 r. 
- Kompilacja 18362.1043
 
Ulepszenia i poprawki w aktualizacji:

- Ulepszona stabilność aplikacji wyłącznych podczas pracy z emulatorem urządzenia HoloLens 2.

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic, wersja 1903 — aktualizacja z grudnia 2019 r. 
- Kompilacja 18362.1042

Ulepszenia i poprawki w aktualizacji:

- Wprowadzono poprawki dotyczące odtwarzania ostatniego etapu (LSR). Ulepszone renderowanie wizualizacji hologramów, aby bardziej stabilne i bardziej chylić się, dzięki dokładniejszemu ewidencjonowania ich głębokości. Ten objaw będzie bardziej zauważalny po tej aktualizacji, jeśli aplikacje nie ustawią prawidłowo głębokości hologramów.
- Poprawiono stabilność wyłącznych aplikacji i nawigację między aplikacjami wyłączności.
- Rozwiązano problem, który mógł dotyczyć sytuacji, w której przechwytywanie rzeczywistości mieszanej nie mogło nagrać wideo, gdy urządzenie było w stanie wstrzymania przez kilka dni.
- Ulepszona stabilność hologramów.

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic, wersja 1903 — aktualizacja z listopada 2019 r. 
- Kompilacja 18362.1039

Ulepszenia i poprawki w aktualizacji:

- Naprawiono funkcjonalność poleceń **Select** voice podczas początkowej konfiguracji dla en-CA i en-AU.
- Ulepszona jakość wizualna obiektów umieszczonych daleko w najnowszych wersjach aparatu Unity Mixed Reality Toolkit (MRTK).
- Rozwiązano problemy z blokowaniem aplikacji holograficznych w stanie wstrzymania podczas uruchamiania do momentu menu Start, a następnie zamknięcia.
- Poprawki i ulepszenia zgodności środowiska uruchomieniowego OpenXR dla urządzenia HoloLens 2 i emulatora.
