---
title: Korzystanie z domu menu Start rzeczywistości mieszanej
description: Dowiedz się, jak używać menu Start, zarządzać aplikacjami i uzyskać do nich dostęp oraz nawigować po domu rzeczywistości mieszanej na HoloLens urządzeniach.
ms.assetid: 742bc126-7996-4f3a-abb2-cf345dff730c
ms.date: 08/07/2019
keywords: Hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f9a6f1692df05e5fd8faec3da07cc85f7c6a32c7
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036538"
---
# <a name="use-the-start-menu-and-mixed-reality-home"></a>Korzystanie z domu menu Start rzeczywistości mieszanej

Podobnie jak środowisko Windows komputera zaczyna się od pulpitu, Windows Holographic zaczyna się od domu rzeczywistości mieszanej.  Za pomocą menu Start można otwierać i umieszczać okna aplikacji, uruchamianie aplikacji immersywnych oraz zawartość 3D w domu rzeczywistości mieszanej, a ich położenie w przestrzeni fizycznej zostanie zapamiętane.

## <a name="use-the-start-menu"></a>Użyj menu Start

Aplikacja menu Start na HoloLens to miejsce, w którym otwierasz aplikacje, widzisz ważne informacje o stanie i uzyskujesz dostęp do narzędzi, takich jak aparat.

Wszędzie tam, gdzie jesteś w HoloLens, zawsze możesz otworzyć menu Start za pomocą **gestu Start**.  Na HoloLens (1. generacji) gest Uruchamiania to [bloom](https://support.microsoft.com/help/12644/hololens-use-gestures). Na HoloLens 2 gest [Uruchom](hololens2-basic-usage.md#start-gesture) to naciśnięcie ikony Start wyświetlanej na nadgarstku.  Możesz również otworzyć okno menu Start głosem, mówiąc "Przejdź do startu".

> [!TIP]
> Gdy menu Start, użyj gestu Start, aby go zamknąć, lub spójrz na menu Start i powiedz "Zamknij".

W górnej części menu Start są wskaźniki stanu dla sieci Wi-Fi, baterii, głośności i zegara. Na HoloLens 2 znajduje się również wskaźnik nasłuchiwania, który pokazuje, czy urządzenie jest włączone i nasłuchuje poleceń głosowych. W dolnej części znajdują się przyciski **Photo** (Zdjęcie) i **Video (Wideo),** które umożliwiają robić zdjęcia i nagrania wideo.  Istnieje również przycisk **Połączenie,** który umożliwia wyświetlanie danych na innym urządzeniu przy użyciu Miracast.

### <a name="find-apps-on-start-menu"></a>Znajdowanie aplikacji na menu Start

Aplikacja menu Start listę **przypiętych** aplikacji i **Wszystkie aplikacje** listy.

- Lista **Przypięte aplikacje** zawiera przypięte aplikacje. Aplikacje można dodawać i usuwać z listy **Przypięte** aplikacje przy użyciu menu kontekstowego wyświetlanego po wybraniu i **przytrzymaniu** kafelka aplikacji.

- Na **Wszystkie aplikacje** są wszystkie aplikacje zainstalowane na urządzeniu.  Wybierz przycisk **Wszystkie aplikacje** po prawej stronie menu **Start,** aby uzyskać dostęp do listy.

Na obu listach aplikacji użyj przycisków **Page up** (Strona w górę) i **Page down** (Strona w dół) po prawej menu Start, aby przejść do wszystkich aplikacji na liście.  Obie listy aplikacji zostaną automatycznie otwarte na stronie, która została ostatnio użyta podczas sesji urządzenia.

> [!TIP]
> Na HoloLens 2 możesz bezpośrednio przewijać listy aplikacji przy użyciu palca indeksu. Wystarczy dotknięcie listy palcem i przeciągnięcie w górę lub w dół.

### <a name="open-apps-from-start-menu"></a>Otwieranie aplikacji z menu Start

Aby otworzyć aplikację z menu Start, po **prostu wybierz** **kafelek aplikacji**. Możesz również powiedzieć nazwę aplikacji, aby ją otworzyć.

Po otwarciu aplikacji z menu Start, w zależności od sposobu zaprojektowania aplikacji, nastąpi jedna z następujących sytuacji:

- Zostanie **umieszczone okno** aplikacji. Aplikacja zostanie następnie załadowana do okna i będzie można jej używać jak ekranu dotykowego.
- Zostanie **umieszczony ekran uruchamiania aplikacji 3D** dla aplikacji immersyjnej. Następnie należy wybrać **przycisk uruchamiania,** aby otworzyć aplikację immersywną.
- Zostanie umieszczone okno aplikacji, które działa jako **launcher** dla aplikacji immersyjnej. Aplikacja immersywna będzie uruchamiana automatycznie.

Okna aplikacji i uruchamianie aplikacji umieszczone w domu rzeczywistości mieszanej będą się nie czekać, aż zdecydujesz się je usunąć.  Zapewniają one wygodny na świecie skrót do korzystania z tych okien aplikacji lub uruchamiania aplikacji immersywnych bez konieczności ich otwierania ponownie z menu Start. 

> [!NOTE]
>Podobnie jak w przypadku telefonu zasoby systemowe są zarządzane automatycznie na HoloLens.  Na przykład po otwarciu nowej aplikacji immersyjnej wszystkie inne uruchomione aplikacje natychmiast staną się nieaktywne. Nie ma potrzeby usuwania okien aplikacji i okien uruchamiania w domu rzeczywistości mieszanej, aby uwolnić zasoby systemowe. 

## <a name="using-apps-on-hololens"></a>Korzystanie z aplikacji na HoloLens

Aplikacje na HoloLens mogą używać widoku okna aplikacji lub widoku immersyjnego. W widoku okna aplikacji aplikacja po prostu wyświetla swoją zawartość w oknie. Dzięki widokowi immersyjnemu aplikacja odchodzi od mieszanego domu, w którym może wyświetlać swoją zawartość w całym środowisku fizycznym. Aplikacje mogą również używać obu widoków.

### <a name="use-app-windows"></a>Korzystanie z okien aplikacji

Na HoloLens (1. generacji) okna aplikacji są umieszczane i używane w domu rzeczywistości mieszanej, gdzie można [przenosić,](hololens1-basic-usage.md#move-resize-and-rotate-apps) zmieniać rozmiar i obracać je w taki sposób, jak chcesz. Oprócz używania okien aplikacji z spojrzeniem i gestem można ich również używać z Bluetooth myszy i klawiatury.

W HoloLens 2 oprócz korzystania z okien aplikacji w domu rzeczywistości mieszanej można również używać jednego okna aplikacji jednocześnie w aplikacji immersyjnej. Możesz również przejść do  trybu Obserwowanie mnie w oknie aplikacji, w którym pozostanie przed toem podczas śledzenia. Gdy otworzysz okno aplikacji w aplikacji immersyjnej, zostanie ono automatycznie otwarte w **trybie** Obserwuj mnie. Okna aplikacji [można przenosić,](hololens2-basic-usage.md#move-resize-and-rotate-holograms) zmieniać ich rozmiar i obracać bezpośrednio przy użyciu rąk zarówno w domu rzeczywistości mieszanej, jak i wewnątrz aplikacji immersyjnej.

> [!NOTE]
>
> - W domu rzeczywistości mieszanej jednocześnie mogą być aktywne maksymalnie trzy okna aplikacji. Możesz otworzyć więcej, ale tylko trzy pozostaną aktywne.
> - Gdy okno aplikacji nie jest aktywne, będzie ono wyświetlać zawartość, która wygląda na zaciemnianą w porównaniu z aktywnym oknem.  Niektóre po prostu pokażą ikonę aplikacji zamiast jakiejkolwiek zawartości.  Aby aktywować nieaktywne okno, **po prostu wybierz** je.
> - Każda otwarta aplikacja może mieć jedno aktywne okno na raz, z Microsoft Edge, które może mieć maksymalnie trzy.

### <a name="close-apps"></a>Zamykanie aplikacji

Aby zamknąć aplikację, która używa okna aplikacji, po prostu zamknij okno aplikacji za pomocą przycisku **Zamknij** na pasku tytułu.  Możesz również przyjrzeć się oknie i powiedzieć "Zamknij".

Aby zamknąć aplikację, która używa widoku immersyjnego, użyj gestu Start, aby wyświetlić ekran menu Start **,** a następnie wybierz przycisk **Strona główna rzeczywistości mieszanej.**

Jeśli aplikacja immersywna jest w stanie uszkodzonym i musisz ją ponownie uruchomić, możesz upewnić się, że aplikacja została najpierw całkowicie zamknięta, zamykając jej uruchamianie w domu rzeczywistości mieszanej, a następnie uruchamiając ją z menu Start.

### <a name="default-app-picker"></a>Domyślny s wyboru aplikacji

W systemie Windows Holographic w wersji [21H1](hololens-release-notes.md#windows-holographic-version-21h1)po aktywowaniu hiperlinku lub otwarciu typu pliku z więcej niż jedną zainstalowaną aplikacją, która go obsługuje, zostanie otwarte nowe okno z monitem o wybranie zainstalowanej aplikacji, która powinna obsługiwać typ pliku lub linku. W tym oknie możesz również wybrać opcję obsługi pliku przez wybraną aplikację lub typ linku "Raz" lub "Zawsze".

![Okno s wyboru aplikacji.](images/default-app-picker.png)

Jeśli wybierzesz opcję "Zawsze", ale później chcesz zmienić, która aplikacja obsługuje określony typ pliku lub linku, możesz zresetować zapisane wartości domyślne w u **Ustawienia > Apps.** Przewiń w dół strony i  wybierz przycisk Wyczyść w obszarze "Domyślne aplikacje dla typów plików" i/lub "Aplikacje domyślne dla typów linków". W przeciwieństwie do podobnego ustawienia na komputerach stacjonarnych nie można zresetować ustawień domyślnych poszczególnych typów plików.

### <a name="per-app-volume-control"></a>Kontrola głośności dla aplikacji

W Windows Holographic w wersji [21H1](hololens-release-notes.md#windows-holographic-version-21h1)użytkownicy mogą ręcznie dostosować poziom głośności każdej aplikacji. Dzięki temu użytkownicy mogą lepiej skoncentrować się na aplikacjach, których potrzebują, lub lepiej słyszeć w przypadku korzystania z wielu aplikacji. Na przykład konieczność wyłączenia woluminu jednej aplikacji podczas rozmowy z inną osobą w celu uzyskania pomocy zdalnej w innej.

Aby ustawić wolumin poszczególnych aplikacji, przejdź do Ustawienia System Sound i w obszarze **Zaawansowane** opcje dźwięku wybierz pozycję Wolumin  ->    ->  aplikacji **i preferencje urządzenia.**

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

## <a name="related-info"></a>Powiązane informacje

[Znajdowanie, instalowanie i odinstalowywanie aplikacji z Microsoft Store](holographic-store-apps.md)
