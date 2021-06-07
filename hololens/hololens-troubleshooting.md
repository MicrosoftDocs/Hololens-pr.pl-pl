---
title: Rozwiązywanie problemów
description: Bądź na bieżąco z najpopularniejszymi rozwiązaniami problemów z urządzeniami HoloLens i technikami rozwiązywania problemów.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problemy, usterka, rozwiązywanie problemów, poprawka, pomoc, obsługa techniczna, HoloLens
ms.openlocfilehash: 1039af533b5039eb4eef6599c7cbb480955b0661
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378349"
---
# <a name="troubleshoot-common-issues"></a>Rozwiązywanie typowych problemów

W tym artykule opisano sposób rozwiązywania kilku typowych problemów z urządzeniem HoloLens.

## <a name="my-hololens-is-unresponsive-or-wont-start"></a>My HoloLens is unresponsive or won't start (Mój urządzenie HoloLens nie odpowiada lub nie można uruchomić)

Jeśli nie można uruchomić urządzenia HoloLens:

- Jeśli diody LED obok przycisku zasilania nie zaczną się osłaniać lub tylko jedna dioda LED miga, może być konieczne ładowanie urządzenia [HoloLens.](hololens-recovery.md#charge-the-device)
- Jeśli diody LED są wyświetlane po naciśnięciu przycisku zasilania, ale nie widzisz niczego na ekranach, wstępnie zresetuj [urządzenie.](hololens-recovery.md#hard-reset-procedure)

Jeśli urządzenie HoloLens jest zamrożone lub nie odpowiada:

- Wyłącz urządzenie HoloLens, naciskając przycisk zasilania, aż wszystkie pięć diod LED wyłączy się lub na 15 sekund, jeśli diody LED nie będą odpowiadać. Aby uruchomić urządzenie HoloLens, naciśnij ponownie przycisk zasilania.

Jeśli te kroki nie działają, możesz spróbować odzyskać urządzenie [HoloLens 2](hololens-recovery.md) lub [HoloLens (1. generacja).](hololens1-recovery.md)

## <a name="holograms-dont-look-good"></a>Hologramy nie wyglądają dobrze

Jeśli hologramy są niestabilne, szybko lub nie wyglądają dobrze, spróbuj:

- Czyszczenie osłoni urządzenia i paska czujnika z przodu urządzenia HoloLens.
- Zwiększenie światła w pomieszczeniu.
- Chodzenie po okolicy i przyglądanie się jej, aby urządzenia HoloLens można było je przeskanować w pełni.
- Skalibrowanie urządzenia HoloLens dla oczu. Przejdź do **ustawień**  >  **Narzędzia systemowe**  >  . W **obszarze Podniesieć** wybierz **pozycję Otwórz drukarkę.**
 
### <a name="reporting-issues-where-holograms-are-unstable-or-dont-look-right"></a>Zgłaszanie problemów, w przypadku których hologramy są niestabilne lub nie wyglądają dobrze
 
1. Nagraj [i Przechwytywanie rzeczywistości mieszanej wideo](holographic-photos-and-videos.md#capture-a-mixed-reality-video) o problemie. Ten film wideo można później przekazać za pośrednictwem Centrum opinii jako dołączony plik.  
1. Włączanie pełnej  telemetrii za pośrednictwem aplikacji Ustawienia — > **diagnostyki** prywatności & i w obszarze Opcjonalne dane diagnostyczne upewnij się, że przełącznik jest  ->   ustawiony na **wartość Wł.** 
1. Uzyskaj najnowsze poprawki dotyczące skali i stabilności hologramów, aktualizując system [operacyjny Windows Holographic (20H2 lub wyższy).](hololens-release-notes.md#windows-holographic-version-20h2) Po aktualizacji wykonaj następujące czynności:
    1. Usuń wszystkie hologramy za pomocą ustawienia **app** -> **System**  ->  **Holograms** -> następnie wybierz pozycję Usuń wszystkie **hologramy** i zacznij od nowej mapy.
    1. Utwórz nową mapę swojej przestrzeni, nosząc urządzenia HoloLens i przechodząc po pomieszczeniu i przyglądając się wszystkim obszarom i powierzchniom w przestrzeni. Zrób to przez 2–3 minuty.
    1. Wykonaj czynności z adresu IPD. Przejdź do **ustawień**  >  **Narzędzia systemowe**  >  . W **obszarze Podniesieć** wybierz **pozycję Otwórz drukarkę.**
    1. Ponownie przetestuj scenariusz i sprawdź, czy nadal będzie się powtarzać.
1. Jeśli aktualizacja nie rozwiąże problemu, Centrum opinii [problem](hololens-feedback.md). Po przesłaniu opinii możesz użyć  przycisku Udostępnij, aby utworzyć łatwy do udostępnienia link, który można wysłać podczas kontaktowania się z pomocą techniczną.

## <a name="hololens-doesnt-respond-to-hand-input"></a>Urządzenie HoloLens nie odpowiada na ręczne wprowadzanie danych

Aby mieć pewność, że urządzenie HoloLens będzie widzieć twoje ręce, musisz zachować je w ramce gestu.  Strona Mixed Reality home udostępnia opinię, która informuje o tym, kiedy są śledzone twoje ręce.  Opinie są inne w różnych wersjach urządzenia HoloLens:
- Na urządzeniach HoloLens (1. generacja) kursor spojrzenia zmienia się z kropki na pierścień
- Na urządzeniach HoloLens 2, gdy ręka jest blisko planszy, pojawia się kursor w zasięgu ręki, a gdy plansze znajdują się dalej, pojawia się promienia ręki

Wiele aplikacji immersywnych ma wzorce wejściowe podobne do Mixed Reality Home.  Dowiedz się więcej o używaniu danych wejściowych ręcznie na [urządzeniach HoloLens (1. generacja)](hololens1-basic-usage.md#use-hololens-with-your-hands) i [HoloLens 2.](hololens2-basic-usage.md#the-hand-tracking-frame)

Należy pamiętać, że niektóre typy iniekcj nie działają ze śledzeniem rąk.  Częstym przykładem są czarne gumy, które zwykle absorbują światło podczerwone i nie są odbierane przez kamerę z głębokością.  Jeśli Twoja praca wiąże się z gumką, zalecamy wypróbowanie jaśniejszego koloru, takiego jak niebieski lub szary.  Innym przykładem są duże baggy nagie, które zwykle przesłaniają kształt ręki. Zalecamy używanie tak dopasowanych do formularzy, jak to tylko możliwe, aby uzyskać najlepsze wyniki.

Jeśli twoje urządzenie ma odciski palców lub smekty, użyj mikrofibry czyszczącej urządzenie HoloLens, aby wyczyścić ją.

## <a name="hololens-doesnt-respond-to-my-voice-commands"></a>Urządzenie HoloLens nie odpowiada na polecenia głosowe

Jeśli Cortana nie odpowiada na polecenia głosowe, upewnij się, że Cortana jest włączona. Na liście Wszystkie aplikacje wybierz pozycję **Ustawienia**  >  **notesu menu** Cortany, aby wprowadzić  >    >   zmiany. Aby dowiedzieć się więcej na temat tego, co możesz powiedzieć, zobacz [Używanie głosu na urządzeniach HoloLens.](hololens-cortana.md)

## <a name="i-cant-place-holograms-or-see-holograms-that-i-previously-placed"></a>Nie mogę umieścić hologramów ani zobaczyć hologramów, które zostały wcześniej umieszczone

Jeśli urządzenie HoloLens nie może zamapować ani załadować twojej przestrzeni, przejdzie w tryb ograniczony i nie będzie można umieszczać hologramów ani zobaczyć hologramów, które zostały umieszczone. Oto kilka rozwiązań do wypróbowania:

- Upewnij się, że w Twoim środowisku jest wystarczająca ilość światła, aby urządzenie HoloLens może zobaczyć i zamapować miejsce.
- Upewnij się, że masz połączenie z Wi-Fi siecią. Jeśli nie masz połączenia z siecią Wi-Fi, urządzenie HoloLens nie może zidentyfikować i załadować znanego miejsca.
- Jeśli musisz utworzyć nowe miejsce, połącz się z siecią Wi-Fi, a następnie ponownie uruchom urządzenie HoloLens.
- Aby sprawdzić, czy jest aktywne poprawne miejsce lub aby ręcznie załadować miejsce, przejdź do obszaru **Ustawienia**  >  **Miejsca systemowe**  >  .
- Jeśli załadowane jest odpowiednie miejsce i nadal występują problemy, może to być uszkodzone. Aby rozwiązać ten problem, wybierz miejsce, a następnie wybierz pozycję **Usuń**. Po usunięciu przestrzeni urządzenie HoloLens zacznie mapować twoje otoczenia i tworzyć nowe miejsce.

## <a name="my-hololens-cant-tell-what-space-im-in"></a>Urządzenie HoloLens nie może określić, w jakim miejscu się zajmuję

Jeśli urządzenie HoloLens nie może zidentyfikować i załadować miejsca, w które się znajdujesz, sprawdź następujące czynniki:

- Upewnij się, że masz połączenie z Wi-Fi
- Upewnij się, że w pomieszczeniu jest dużo światła
- Upewnij się, że nie w środowisku nie wszedno żadnych istotnych zmian.

Możesz również ręcznie załadować miejsce lub zarządzać przestrzeniami, przechodząc do obszaru **Ustawienia**  >  **Przestrzenie**  >  **systemowe**.

## <a name="im-getting-a-low-disk-space-error"></a>Występuje błąd "Mała ilość miejsca na dysku"

Konieczne będzie wolne miejsce do magazynowania, wykonując jedną lub więcej z następujących czynności:

- Usuń niektóre nieużywane spacje. Przejdź do **obszaru Ustawienia**  >  **Przestrzenie** systemowe, wybierz miejsce, które nie jest już  >   **potrzebne,** a następnie wybierz pozycję Usuń .
- Usuń niektóre z umieszczonych hologramów.
- Usuń zdjęcia i filmy wideo z aplikacji Zdjęcia.
- Odinstaluj niektóre aplikacje z urządzenia HoloLens. Na liście **Wszystkie aplikacje** naciśnij i przytrzymaj aplikację, którą chcesz odinstalować, a następnie wybierz pozycję **Odinstaluj.**

## <a name="my-hololens-cant-create-a-new-space"></a>My HoloLens can't create a new space (Mój urządzenie HoloLens nie może utworzyć nowego miejsca)

Najbardziej prawdopodobnym problemem jest mała ilość miejsca do magazynowania. Wypróbuj jedną z [poprzednich wskazówek,](#im-getting-a-low-disk-space-error) aby trochę miejsca na dysku.

## <a name="the-hololens-emulator-isnt-working"></a>Emulator urządzenia HoloLens nie działa

Informacje o emulatorze urządzenia HoloLens znajdują się w naszej dokumentacji dla deweloperów.  Przeczytaj więcej na [temat rozwiązywania problemów z emulatorem urządzenia HoloLens.](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)
