---
title: Wprowadzenie do nowego Microsoft Edge
description: Dowiedz się więcej o nowej aplikacji Edge
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, edge, Internet, przeglądarka
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: 8ef73733b9fa4f422335977be860371b9570d549
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036530"
---
# <a name="introducing-the-new-microsoft-edge"></a>Wprowadzenie do nowego Microsoft Edge

![Animacja starszego Microsoft Edge logo nowego Microsoft Edge logo.](images/new-edge.gif)

Nowa aplikacja Microsoft Edge [projekt](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) Chromium open source w celu zapewnienia lepszej zgodności dla klientów i mniejszej fragmentacji sieci Web dla deweloperów sieci Web.

W Windows Holographic w wersji [21H1](hololens-release-notes.md#windows-holographic-version-21h1)nowy Microsoft Edge jest dostępny dla klientów HoloLens 2 po raz pierwszy! Podziel się opinią i błędami z naszym zespołem za pośrednictwem **funkcji** Wyślij opinię w nowej Microsoft Edge lub za [pośrednictwem Centrum opinii.](hololens-feedback.md)

> [!IMPORTANT]
> Ta nowa Microsoft Edge automatycznie zastępuje starsze Microsoft Edge, które nie [są już obsługiwane w](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) nowych wersjach.

![Nowy Microsoft Edge zrzut ekranu.](images/new-edge-ui.png)

## <a name="launching-the-new-microsoft-edge"></a>Uruchamianie nowego Microsoft Edge

Nowa Microsoft Edge ![ikona Microsoft Edge nowej aplikacji.](images/new_edge_logo.png) (reprezentowany przez niebieską i zieloną ikonę zawirowania) jest przypinany do menu Start i automatycznie uruchamia się po aktywowaniu linku internetowego.

> [!NOTE]
> Po pierwszym uruchomieniu nowej aplikacji Microsoft Edge wersji HoloLens 2 ustawienia i dane zostaną zaimportowane ze starszej Microsoft Edge.

## <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>Konfigurowanie ustawień zasad dla nowej Microsoft Edge

Nowa wersja Microsoft Edge administratorom IT znacznie szerszy zestaw zasad przeglądarki na platformie HoloLens 2 niż wcześniej dostępne w starszych wersjach Microsoft Edge.

Oto kilka przydatnych zasobów, które mogą dowiedzieć się więcej na temat zarządzania ustawieniami zasad dla nowej Microsoft Edge:

- [Konfigurowanie Microsoft Edge zasad sieciowych przy użyciu Microsoft Intune](/deployedge/configure-edge-with-intune)
- [Starsza wersja Microsoft Edge do Microsoft Edge mapowania zasad](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Mapowanie zasad Microsoft Edge Google Chrome](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- Pełna [Microsoft Edge Enterprise dokumentacji](/deployedge/)

> [!IMPORTANT]
> Ze względu na ilość zasad przeglądarki obsługiwanych przez nową Microsoft Edge nasz zespół nie może zagwarantować, że wszystkie nowe zasady będą HoloLens 2. Jednak przetestowaliśmy i potwierdziliśmy, że nowe Microsoft Edge równoważne każdej starszej wersji zasad Microsoft Edge obsługiwanych wcześniej na HoloLens 2 działają zgodnie z oczekiwaniami. Zobacz [Starsza wersja Microsoft Edge, Microsoft Edge mapowania](/deployedge/microsoft-edge-policy-map-legacy-to-newedge) zasad, aby znaleźć nowe Microsoft Edge równoważne każdej starszej wersji zasad przeglądarki Microsoft Edge, których używano w programie HoloLens 2.
>
> Istnieją co najmniej dwie nowe zasady Microsoft Edge, które nie *będą* działać z HoloLens 2:
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

## <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>Czego można oczekiwać od nowej Microsoft Edge w HoloLens 2

Ponieważ nowy Microsoft Edge jest natywną aplikacją Win32 z nową warstwą karty platformy uniwersalnej systemu Windows umożliwiającą jej uruchamianie na urządzeniach tylko na platformie uniwersalnej systemu Windows, takich jak HoloLens 2, niektóre funkcje mogą nie być natychmiast dostępne. W najbliższych miesiącach będziemy obsługiwać nowe scenariusze i funkcje, dlatego sprawdź, czy w tym miejscu znajdują się aktualne informacje.

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
- Zapisywanie pliku PDF z menu Drukuj (przy użyciu opcji "Zapisz w formacie PDF")
- Rozszerzenie WebXR i 360 Viewer
- Przywracanie zawartości do poprawnego okna podczas przeglądania w wielu oknach umieszczonych w środowisku

**Scenariusze i funkcje, które nie powinny działać:**
- Dźwięk przestrzenny z wielu okien z równoczesnym strumieniem audio
- "See it, say it" (Zobacz, powiedz)
- Drukowanie

**Najważniejsze znane problemy z przeglądarką:**
- Podgląd lupy na klawiaturze holograficznej został wyłączony dla nowej Microsoft Edge. Mamy nadzieję, że w przyszłej aktualizacji ponownie wejdziemy do tej funkcji, gdy powiększenie będzie działać prawidłowo.
- Dźwięk może być odtwarzany z niewłaściwego okna przeglądarki, jeśli masz otwarte i aktywne inne okno przeglądarki. Ten problem można omiąć, zamykając inne aktywne okno, które nie powinno odtwarzać dźwięku.
- Podczas odtwarzania dźwięku z okna przeglądarki w trybie "Obserwuj mnie" dźwięk będzie odtwarzany, jeśli wyłączysz tryb "Obserwuj mnie". Ten problem można ominić, zatrzymując odtwarzanie dźwięku przed wyłączeniem trybu "Obserwuj mnie" lub zamykając okno za pomocą przycisku X.
- Interakcja z aktywnymi Microsoft Edge może spowodować nieoczekiwane nieaktywne inne okna aplikacji 2D. Te okna można ponownie uaktywnić, ponownie korzystając z nich.

## <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Kanały niejawnych testerów

Zespół Microsoft Edge udostępnia trzy kanały w wersji zapoznawczej społeczności niejawnych testerów edge: Beta, Dev i Canary. Zainstalowanie kanału w wersji zapoznawczej nie spowoduje odinstalowania wydanej wersji programu Microsoft Edge na komputerze HoloLens 2 i można zainstalować więcej niż jedną wersję jednocześnie. 

Odwiedź stronę [główną Microsoft Edge Insider,](https://www.microsoftedgeinsider.com) aby dowiedzieć się więcej na temat społeczności niejawnych testerów przeglądarki Edge. Aby dowiedzieć się więcej na temat różnych kanałów dla niejawnych testerów programu Edge i rozpocząć pracę, odwiedź stronę pobierania dla niejawnych [testerów programu Edge.](https://www.microsoftedgeinsider.com/download)

Istnieje kilka dostępnych metod instalowania kanałów Microsoft Edge insider w HoloLens 2:

**Bezpośrednia instalacja na urządzeniu (obecnie dostępna tylko dla urządzeń niezamaniowych)**
  1. Na komputerze HoloLens 2 odwiedź stronę [pobierania przeglądarki Edge dla niejawnych testerów.](https://www.microsoftedgeinsider.com/download)
  1. Wybierz przycisk **Pobierz dla HoloLens 2** dla kanału niejawnego testera edge, który chcesz zainstalować.
  1. Uruchom pobrany plik msix z kolejki pobierania przeglądarki Edge lub z folderu "Pobrane" urządzenia (przy użyciu Eksplorator plików).
  1. [Zostanie uruchomić instalator](app-deploy-app-installer.md) aplikacji.
  1. Wybierz przycisk **Zainstaluj.**
  1. Po pomyślnej instalacji znajdziesz Microsoft Edge Beta, Dev lub Canary jako oddzielny wpis na **Wszystkie aplikacje** listy menu Start.

**Instalowanie za pośrednictwem komputera Windows Portal urządzeń (wymaga, aby tryb [dewelopera](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) był włączony na HoloLens 2)**
  1. Na komputerze odwiedź stronę pobierania [przeglądarki Edge dla niejawnych testerów.](https://www.microsoftedgeinsider.com/download)
  1. Wybierz przycisk **strzałki listy rozwijanej** obok przycisku "Pobierz dla Windows 10" dla kanału niejawnego testera edge, który chcesz zainstalować.
  1. Wybierz **HoloLens 2** z menu rozwijanego.
  1. Zapisz plik msix w folderze "Pobrane" na komputerze (lub innym folderze, który można łatwo znaleźć).
  1. Użyj [Windows Portal urządzeń](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) na komputerze, aby zainstalować pobrany plik msix na komputerze HoloLens 2.
  1. Po pomyślnej instalacji znajdziesz Microsoft Edge Beta, Dev lub Canary jako oddzielny wpis na **Wszystkie aplikacje** listy menu Start.

## <a name="using-wdac-to-block-new-microsoft-edge"></a>Blokowanie nowych funkcji za pomocą funkcji WDAC Microsoft Edge

W przypadku administratorów IT, którzy chcą zaktualizować swoje zasady [WDAC](windows-defender-application-control-wdac.md) w celu zablokowania nowej Microsoft Edge aplikacji, należy dodać następujące elementy do zasad.

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

## <a name="managing-endpoints-for-the-new-microsoft-edge"></a>Zarządzanie punktami końcowymi dla nowego Microsoft Edge

Niektóre środowiska mogą mieć ograniczenia sieciowe, które należy wziąć pod uwagę. Aby zapewnić bezproblemowe środowisko pracy z nową krawędzią, [włącz te punkty końcowe firmy Microsoft.](/deployedge/microsoft-edge-security-endpoints)

Przeczytaj więcej na temat aktualnie [dostępnych punktów końcowych dla HoloLens](hololens-offline.md).

## <a name="install-web-apps"></a>Instalowanie aplikacji internetowych
 > [!Note]
> Od Windows Holographic w wersji [21H1](hololens-release-notes.md#windows-holographic-version-21h1)aplikacja Office nie będzie już wstępnie zainstalowana. 

Nowej przeglądarki Edge można używać do instalowania aplikacji internetowych Microsoft Store aplikacji. Możesz na przykład zainstalować aplikację internetową Microsoft Office, aby wyświetlać i edytować pliki hostowane SharePoint lub OneDrive. Aby zainstalować Office aplikację internetową, odwiedź i wybierz przycisk App Available (Dostępna aplikacja) https://www.office.com **lub Install Office (Zainstaluj** aplikację) na pasku adresu.  Wybierz **pozycję Zainstaluj,** aby potwierdzić.
> [!IMPORTANT]
> Office aplikacji internetowej jest dostępna tylko wtedy, HoloLens 2 ma aktywne połączenie z Internetem.

## <a name="webxr-and-360-viewer"></a>WebXR i 360 Viewer


Nowa wersja Microsoft Edge obsługę funkcji WebXR, która jest nowym standardem tworzenia immersywnych interfejsów internetowych (zastępując webVR). Wiele immersywnych środowisk internetowych zostało zaprojektowanych z myślą o VR (zastępują one pole widzenia środowiskiem wirtualnym), ale te środowiska są również obsługiwane przez HoloLens 2. Standard WebXR umożliwia również korzystanie z immersywnych środowisk internetowych rzeczywistości rozszerzonej i mieszanej, które korzystają ze środowiska fizycznego. Ponieważ deweloperzy spędzają więcej czasu z webXR, przewidujemy, że nowe immersywne środowiska rzeczywistości rozszerzonej i mieszanej przyjdą do HoloLens 2 klientów!

Rozszerzenie 360 Viewer jest wbudowane w usługę WebXR i jest automatycznie instalowane wraz z nową Microsoft Edge na HoloLens 2. To rozszerzenie internetowe umożliwia zagłębienie się w filmy wideo na poziomie 360 stopni. Serwis YouTube oferuje największy wybór 360 filmów wideo, dlatego zachęcamy do rozpoczęcia w tym miejscu.

### <a name="how-to-use-webxr"></a>Jak używać usługi WebXR

1. Przejdź do witryny internetowej z obsługą usługi WebXR.
1. Wybierz przycisk **Wprowadź VR** w witrynie internetowej. Lokalizacja i wizualna reprezentacja tego przycisku może się różnić w zależności od witryny internetowej, ale może wyglądać podobnie do:

    ![Wprowadź przykład przycisku VR.](images/75px-enter-vr.png)

1. Przy pierwszej próbie uruchomienia środowiska WebXR w określonej domenie przeglądarka poprosi o zgodę na wprowadzenie widoku immersyjnego, a następnie wybierz pozycję **Zezwalaj.**
1. Użyj [HoloLens 2 gestów,](hololens2-basic-usage.md#the-hand-tracking-frame) aby manipulować środowiskom.
1. Jeśli środowisko nie ma przycisku **Wyjdź,** użyj [gestu Uruchom,](hololens2-basic-usage.md#start-gesture) aby powrócić do strony głównej.

**Zalecane przykłady dla usługi WebXR**
- Przeglądarka 360 (zobacz następną sekcję)
- [XR Irytatorzy](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

### <a name="how-to-use-360-viewer"></a>Jak używać przeglądarki 360

1. Przejdź do wideo 360-stopnia w serwisie YouTube.
1. W ramce wideo wybierz przycisk zestawu nagłownego rzeczywistości mieszanej:

    ![Przycisk aktywacji przeglądarki 360.](images/enter-360-viewer.jpg)

1. Przy pierwszej próbie uruchomienia przeglądarki 360 w określonej domenie przeglądarka poprosi o zgodę na wprowadzenie widoku immersyjnego. wybierz pozycję **Zezwalaj**.
1. [Naciśnij w powietrzu,](hololens2-basic-usage.md#select-using-air-tap) aby wyprowadzić kontrolki odtwarzania. Używaj [promieni ręki](hololens2-basic-usage.md#select-using-air-tap) i naciśnięcia w powietrzu, aby odtwarzać/wstrzymywać, pomijać przechodzenie do przodu/do tyłu, włączać/wyłączać napisy lub zatrzymywać środowisko (co zamyka widok immersyjny). Kontrolki odtwarzania znikną po kilku sekundach braku aktywności.

### <a name="top-webxr-and-360-viewer-known-issues"></a>Znane problemy z najlepszymi usługami WebXR i 360 Viewer
- W zależności od złożoności procesu WebXR szybkość klatek może spadać lub być zacinana.
- Obsługa językowej ręki w funkcji WebXR nie jest domyślnie włączona. Deweloperzy mogą włączyć obsługę za pośrednictwem edge://flags, włączając funkcję "WebXR Hand Input".
- 360 filmów wideo z witryn innych niż YouTube może nie działać zgodnie z oczekiwaniami.

### <a name="providing-feedback-on-webxr-and-360-viewer"></a>Przekazywanie opinii na temat usługi WebXR i przeglądarki 360

Podziel się opinią i błędami z naszym zespołem za pośrednictwem funkcji **Wyślij** opinię w nowej Microsoft Edge.
