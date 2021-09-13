---
title: Znajdowanie, instalowanie i odinstalowywanie aplikacji
description: Ta Microsoft Store źródło aplikacji i gier, które działają z HoloLens.  Dowiedz się więcej na temat znajdowania, instalowania i odinstalowywania aplikacji holograficznych.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 9/7/2021
manager: jarrettr
keywords: hololens, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 3442da500e7554d7f97db2178cbaceeecad143ac
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036065"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a>Znajdowanie, instalowanie i odinstalowywanie aplikacji z Microsoft Store

Ten Microsoft Store to źródło dla aplikacji i gier, które działają z HoloLens. Po przejdź do sklepu na HoloLens zostaną uruchomione na nim wszystkie aplikacje, które tam zobaczysz.

Aplikacje w HoloLens używają widoku 2D lub widoku holograficznego. Aplikacje, które używają widoku 2D, wyglądają jak okna i mogą być rozmieszone wokół Ciebie. Aplikacje, które korzystają z widoku holograficznego, otaczają Cię i stają się jedyną zobaczysz.

HoloLens obsługuje wiele istniejących aplikacji z Microsoft Store, a nowe aplikacje opracowane specjalnie dla HoloLens.  Ten artykuł koncentruje się na aplikacjach holograficznych z Microsoft Store.

Aby dowiedzieć się więcej na temat instalowania i uruchamiania aplikacji niestandardowych, przeczytaj [niestandardowe aplikacje holograficzne.](holographic-custom-apps.md)

## <a name="find-apps"></a>Znajdź aplikacje

Otwórz Microsoft Store z menu **Start.** Następnie wyszukaj aplikacje i gry. Możesz wyszukiwać [przy](hololens-cortana.md) użyciu poleceń głosowych, mówiąc "Wyszukaj", gdy zostanie otwarte okno wyszukiwania, powiedz "Rozpocznij dyktowanie", a następnie po wyświetleniu monitu zaczniesz wypowiadać terminy wyszukiwania.

> [!NOTE]
> Wymagania systemowe dla HoloLens są oparte na architekturze kompilacji aplikacji. Jeśli kompilacja aplikacji dla usługi HoloLens (1. generacji) nie została zaktualizowana do nowszej platformy UWP w sklepie w celu dołączyć pakiet architektury ARM, nie będzie ona dostępna dla urządzeń z systemem HoloLens 2. Podobnie jeśli aplikacja HoloLens 2 nie zawiera pakietu architektury x86, nie będzie dostępna dla urządzeń HoloLens (1. generacji). HoloLens architektury urządzeń:
>
> - x86 = HoloLens (1. generacja)
> - ARM = HoloLens 2

> [!NOTE]
> 12 stycznia 2021 r. następujące aplikacje zakończą wsparcie techniczne na HoloLens urządzeń. Zachęcamy do korzystania z internetowej wersji aplikacji na urządzeniu za pomocą następującego linku.

| Aplikacja        | Link                                          |
|------------|-----------------------------------------------|
| Excel mobilne      | [https://office.live.com/start/Excel.aspx](https://office.live.com/start/Excel.aspx)      |
| Word Mobile       | [https://office.live.com/start/Word.aspx](https://office.live.com/start/Word.aspx)       |
| PowerPoint mobilne | [https://office.live.com/start/PowerPoint.aspx](https://office.live.com/start/PowerPoint.aspx) |

> [!NOTE]
> Aplikacja OneDrive nie jest obecnie obsługiwana w przypadku kont usługi Azure AD na HoloLens. Zalecamy pobranie aplikacji Microsoft OneDrive PWA aplikacji. [Wykonaj następujące kroki, aby pobrać aplikację.]

## <a name="install-apps"></a>Instalowanie aplikacji

Aby pobrać aplikacje, musisz zalogować się przy użyciu konto Microsoft. Niektóre aplikacje są bezpłatne i można je pobrać od razu. W przypadku aplikacji, które wymagają zakupu, musisz zalogować się do Sklepu przy użyciu konta konto Microsoft i mieć prawidłową formę płatności.

> [!NOTE]
> Konto, za pomocą Microsoft Store nie musi być takie samo jak konto, za pomocą których się zalogowano. Jeśli używasz konta służbowego na koncie usługi HoloLens może być konieczne zalogowanie się przy użyciu konta osobistego w aplikacji ze sklepu, aby dokonać zakupu.

> [!TIP]
> Aby skonfigurować formę płatności, przejdź do usługi  [account.microsoft.com](https://account.microsoft.com/) i wybierz pozycję Rozliczenia & Opcje płatności  >    >  **Dodaj opcję płatności.**

1. Aby otworzyć menu [ **Start,**](holographic-home.md)wykonaj gest [Start](/hololens/hololens2-basic-usage#start-gesture) lub gest [Blooma](hololens1-basic-usage.md) HoloLens (1. generacja).

1. Wybierz Microsoft Store aplikację. Po otworeniu aplikacji ze Sklepu:
   1. Użyj paska wyszukiwania, aby wyszukać aplikacje.
   1. Wybierz podstawowe aplikacje lub aplikacje przeznaczone specjalnie HoloLens z jednej z wybranych kategorii.
   1. W prawym górnym rogu aplikacji ze Sklepu wybierz  przycisk **"...",** a następnie wybierz pozycję Moja biblioteka, aby wyświetlić wszystkie wcześniej zakupione aplikacje.

1. Wybierz **pozycję** **Pobierz lub Zainstaluj** na stronie aplikacji (może być wymagany zakup).

### <a name="install-microsoft-onedrive-pwa-app"></a>Instalowanie Microsoft OneDrive PWA aplikacji

Wymagania wstępne: Użytkownik dołączył już urządzenie HoloLens 2 do swojej dzierżawy służbowej.

1. Otwórz menu Start i uruchom przeglądarkę Edge.

    ![Menu Start](images/office-pwa-1.jpg)

1. Na stronie HoloLens i [https://onedrive.live.com/about/signin](https://onedrive.live.com/about/signin) wprowadź poświadczenia konta służbowego

    ![Logowanie służbowe](images/office-pwa-2.jpg)

1. Po pomyślnym zalogowaniu się do portalu OneDrive zaczekaj od 30 do 60 sekund na PWA pobierania

    ![PWA przycisk instalacji](images/office-pwa-3.jpg)

1. Wybierz przycisk PWA pobierz i zainstaluj aplikację

    ![Monit o zainstalowanie](images/office-pwa-4.jpg)

1. Zamknij przeglądarkę Edge i na menu Start wybierz przycisk **Wszystkie** aplikacje i uruchom aplikację OneDrive PWA z etykietą **Microsoft OneDrive**

    ![Wszystkie aplikacje obie aplikacje.](images/office-pwa-5.jpg)

> [!NOTE]
> "Microsoft OneDrive" jest aplikacją PWA której jako "OneDrive" jest starsza wersja platformy uniwersalnej systemu Windows.

1. Następnie będzie można wyświetlić pliki OneDrive plików.

    ![OneDrive PWA](images/office-pwa-6.jpg)

Zobacz też: [Włączanie automatycznego przekazywania do OneDrive dla firm](hololens-release-notes.md#onedrive-for-work-or-school-camera-roll-upload)

## <a name="update-apps"></a>Aktualizowanie aplikacji

Aby zaktualizować aplikację zainstalowaną z Microsoft Store, możesz ją zaktualizować z Microsoft Store aplikacji. W przypadku aplikacji zainstalowanych Microsoft Store dla Firm można również aktualizować te aplikacje z Microsoft Store dla Firm.

1. Aby otworzyć menu [ **Start,**](holographic-home.md)wykonaj gest [Start](/hololens/hololens2-basic-usage#start-gesture) lub gest [Blooma](hololens1-basic-usage.md) HoloLens (1. generacja).

1. Wybierz aplikację ze Sklepu.

1. Spójrz w prawym górnym rogu aplikacji ze Sklepu.

1. Wybierz przycisk **"..."** lub "Zobacz więcej".

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store zrzut ekranu aplikacji.](images/store-update-1.png)

1. Wybierz **pozycję Pliki do pobrania i aktualizacje.**
    1. Jeśli urządzenie wcześniej zidentyfikował aktualizacje, może to być strzałka w dół i liczba reprezentująca oczekujące aktualizacje.

1. Wybierz **pozycję Pobierz aktualizacje.** Urządzenie będzie teraz wyszukiwać aktualizacje i ustawiać je na pobieranie i instalowanie.

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store aplikacji zrzut ekranu przedstawiający pobieranie aktualizacji.](images/store-update-2.png.jpg)

> [!NOTE]
> Jeśli aplikacje na urządzeniu zostały dystrybuowane przez organizację, można je zaktualizować za pomocą tych samych metod zarządzania aplikacjami komercyjnymi. Jeśli dotyczy to Twojej sytuacji, przeczytaj więcej za pośrednictwem [naszego o omówienie wdrażania aplikacji komercyjnych.](app-deploy-overview.md)
>
> Jeśli chcesz zaktualizować aplikację niestandardową, która została załadowana lub wdrożona w sposób sideload, musisz użyć tej samej metody ze zaktualizowaną wersją aplikacji. Aby dowiedzieć się więcej na temat instalowania i uruchamiania aplikacji niestandardowych, przeczytaj [temat Niestandardowe aplikacje holograficzne.](holographic-custom-apps.md)

## <a name="uninstall-apps"></a>Odinstaluj aplikacje

Istnieją trzy sposoby odinstalowywania aplikacji. Aplikacje można odinstalować za pośrednictwem Microsoft Store, menu Start lub z Ustawienia.

> [!WARNING]
> Nie można odinstalować aplikacji systemowej ani samej Microsoft Store aplikacji.

> [!IMPORTANT]
> Jeśli twoja HoloLens 2 ma wielu użytkowników, musisz być zalogowany jako użytkownik, który zainstalował aplikację, aby ją odinstalować.

### <a name="uninstall-from-the-microsoft-store"></a>Odinstalowywanie z Microsoft Store

Otwórz Microsoft Store menu **Start,** a następnie wyszukaj aplikację, którą chcesz odinstalować.  Na stronie Sklep każda zainstalowana aplikacja ma przycisk **Odinstaluj.**

### <a name="uninstall-from-the-start-menu"></a>Odinstalowywanie z menu Start

W menu **Start** lub na **Wszystkie aplikacje** przejdź do aplikacji. Wybieraj i przytrzymaj do momentu, aż pojawi się menu, a następnie wybierz pozycję **Odinstaluj**.

### <a name="uninstall-from-settings"></a>Odinstalowywanie z Ustawienia

W menu **Start** wybierz pozycję **Ustawienia > Aplikacje.** Znajdź aplikację na liście, wybierz ją, a następnie kliknij pozycję **Odinstaluj.**

Jeśli nie możesz odinstalować aplikacji, [](/hololens/hololens-feedback) prosimy o opinię przy użyciu Centrum opinii.
