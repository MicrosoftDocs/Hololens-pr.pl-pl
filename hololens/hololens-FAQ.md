---
title: Często zadawane pytania dotyczące urządzeń HoloLens i hologramów
description: Czy masz szybkie pytanie dotyczące HoloLens lub interakcji z hologramami?  Ten artykuł zawiera szybką odpowiedź i dodatkowe zasoby.
keywords: hololens, często zadawane pytania, znany problem, pomoc
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 02/27/2020
ms.reviewer: ''
ms.custom:
- CI 114606
- CSSTroubleshooting
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ae44ae1d9a2e088a1ef746f4e929e8fae73880bf
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428382"
---
# <a name="holograms-and-interactions-troubleshooting"></a>Hologramy i interakcje dotyczące rozwiązywania problemów

Ten artykuł dotyczy rozwiązywania problemów z umieszczaniem hologramów, pracą ze spacjami i raportowaniem problemów z hologramami.

Zawsze, gdy masz problemy, upewnij się, że:
- Spróbuj [uruchomić go ponownie,](hololens-restart-recover.md) aby sprawdzić, czy to rozwiąże problem.
- Przed rozpoczęciem rozwiązywania problemów upewnij się, HoloLens zostanie [naliczona](hololens2-charging.md) opłata (opłata za co najmniej godzinę). 


Użyj aplikacji Opinia, aby wysłać nam informacje o problemie. Aplikację Opinia znajdziesz w menu [ **Start.**](holographic-home.md) 

Aby uzyskać porady dotyczące sposobu noszenia HoloLens, zobacz [Dostosowywanie dopasowania](hololens2-setup.md#adjust-fit).

<a id="list"></a>
- [Nie można utworzyć nowych spacji](#new-spaces-cant-be-created)
- [Nie można zidentyfikować ani załadować spacji](#spaces-cant-be-identified-or-loaded)
- [Jak mogę usunąć wszystkie spacje?](#how-do-i-delete-all-spaces)
- [Hologramy nie wygląda dobrze lub są poruszane](#holograms-dont-look-right-or-are-moving-around)
- [Komunikat "Znajdowanie miejsca"](#finding-your-space-message)
- [Oczekiwane hologramy nie są wyświetlane w moim miejscu](#expected-holograms-arent-showing-in-my-space)
- [Nie można umieszczać hologramów ani zobaczyć wcześniej umieszczonych hologramów](#cant-place-holograms-or-see-previously-placed-holograms)
- [Hologramy znika lub są zamknięte w innych hologramach lub obiektach](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [Hologramy są wyświetlane po drugiej stronie ściany](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [Po umieszczeniu hologramu na ścianie wydaje się on zmiennoprzecinkowy](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [Aplikacje są wyświetlane zbyt blisko po przeniesieniu](#apps-appear-too-close-after-moving-them)
- [Zgłaszanie problemów z niestabilnymi lub nieakcyjnie hologramami](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a>Nie można utworzyć nowych spacji

Najbardziej prawdopodobnym problemem jest mała ilość miejsca do magazynowania. [Wolne miejsce na dysku, a](hololens-troubleshooting.md#low-disk-space-error) następnie ponów próbę.

[Powrót do listy](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a>Nie można zidentyfikować ani załadować spacji

Jeśli twoja HoloLens nie może zidentyfikować i załadować miejsca, w których się znajdujesz, sprawdź następujące czynniki:

- Upewnij się, że masz połączenie z Wi-Fi
- Upewnij się, że w pomieszczeniu jest dużo światła
- Upewnij się, że nie w środowisku nie wszedno żadnych istotnych zmian.

Możesz również ręcznie załadować miejsce lub zarządzać przestrzeniami, przechodząc do obszaru **Ustawienia**  >  **System**  >  **Spaces.**

[Powrót do listy](#list)

## <a name="how-do-i-delete-all-spaces"></a>Jak mogę usunąć wszystkie spacje?

*Już wkrótce*

[Powrót do listy](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a>Hologramy nie wyglądają dobrze lub są poruszane

Jeśli Twoje hologramy nie wyglądają dobrze (na przykład są nieświeżące lub potrząsają albo na ich górze widać czarne poprawki), wypróbuj jedną z tych poprawek:

- [Wyczyść urządzenie i upewnij](hololens1-hardware.md#care-and-cleaning) się, że nic nie blokuje czujników.
- Upewnij się, że znajdujesz się w dobrze oświetlonym pomieszczeniu, które nie ma dużo bezpośredniego światła.
- Spróbuj chodzenia po okolicy i zaglądać w jej okolicy, aby HoloLens można było je przeskanować w pełni.
- Jeśli umieścisz wiele hologramów, spróbuj je usunąć.

Jeśli nadal występują problemy, spróbuj ponownie uruchamiać aplikację w 2018 roku. Ta aplikacja umożliwia skalibrowanie HoloLens tylko dla Ciebie, aby ułatwić zachowanie najlepszego wygląd hologramów. W tym celu przejdź do **tematu Ustawienia**  >  **System**  >  **Utilities**. W **obszarze Podniesieć** wybierz **pozycję Otwórz drukarkę.**

[Powrót do listy](#list)

## <a name="finding-your-space-message"></a>Komunikat "Znajdowanie miejsca"

Gdy HoloLens się lub ładuje miejsce, może zostać wyświetlony krótki komunikat "Znajdowanie miejsca". Jeśli ten komunikat będzie wyświetlany przez więcej niż kilka sekund, pod ekranem zostanie wyświetlony inny komunikat menu Start "Nadal szukasz miejsca".

Te komunikaty oznaczają, HoloLens ma problemy z mapowaniem przestrzeni. W takim przypadku możesz otwierać aplikacje, ale nie możesz umieszczać hologramów w swoim środowisku.

Jeśli te komunikaty są często wyświetlane, wypróbuj co najmniej jedną z następujących poprawek:

- Upewnij się, że znajdujesz się w dobrze oświetlonym pomieszczeniu, które nie ma dużo bezpośredniego światła.
- Upewnij się, że urządzenie jest czyste. [Dowiedz się, jak wyczyścić swoją wizjer.](hololens1-hardware.md#care-and-cleaning)
- Upewnij się, że masz silny sygnał Wi-Fi danych. Jeśli wprowadzasz nowe środowisko, które nie ma Wi-Fi ani słabego sygnału Wi-Fi, HoloLens nie będzie można znaleźć miejsca. Sprawdź swoje Wi-Fi, przechodząc **do** Ustawienia Network  >  **&amp; Internet**  >  **Wi-Fi.**
- Spróbuj poruszać się wolniej.

[Powrót do listy](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a>Oczekiwane hologramy nie są wyświetlane w moim miejscu

Jeśli nie widzisz umieszczonych hologramów lub jeśli widzisz, których nie oczekujesz, wypróbuj co najmniej jedną z następujących poprawek:

- Włącz kilka światła. HoloLens działa najlepiej w dobrze oświetlonej przestrzeni.
- Usuń holoogramy, które nie są potrzebne, przechodząc do Ustawienia  >  **System**  >  **Hologramy**  >  **Usuń hologramy w pobliżu.** Lub, w razie potrzeby, wybierz **pozycję Usuń wszystkie hologramy**.

  > [!NOTE]
  > Jeśli układ lub oświetlenie w przestrzeni znacznie się zmieni, urządzenie może mieć problemy ze zidentyfikowaniem Twojej przestrzeni i pokazaniem hologramów.

[Powrót do listy](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a>Nie można umieszczać hologramów ani zobaczyć wcześniej umieszczonych hologramów

Jeśli HoloLens nie można zamapować ani załadować miejsca, zostanie ona w trybie ograniczonym i nie będzie można umieszczać hologramów ani zobaczyć hologramów, które zostały umieszczone. Oto kilka rozwiązań do wypróbowania:

- Upewnij się, że w Twoim środowisku jest wystarczająco dużo światła, aby HoloLens można było zobaczyć i zamapować miejsce.
- Umieść w odległości od jednego do trzech metrów od miejsca, w którym próbujesz umieścić hologram.
- Nie umieszczaj hologramów na czarnych powierzchniach ani na powierzchniach z odbicia.
- Upewnij się, że masz połączenie z Wi-Fi siecią. Jeśli nie masz połączenia z siecią Wi-Fi, HoloLens nie będzie w stanie zidentyfikować ani załadować znanego miejsca.
- Aby można było ponownie HoloLens obszarów, warto poekskanować pomieszczenia. Aby zobaczyć, co zostało już zeskanowane, naciśnij w powietrzu, aby wyświetlić grafikę siatki mapowania.
- Jeśli musisz utworzyć nowe miejsce, połącz się z siecią Wi-Fi, a następnie uruchom ponownie HoloLens.
- Aby sprawdzić, czy jest aktywne poprawne miejsce lub aby ręcznie załadować miejsce, przejdź do tematu **Ustawienia**  >  **System**  >  **Spaces**.
- Jeśli załadowane jest odpowiednie miejsce i nadal występują problemy, może to być uszkodzone. Aby rozwiązać ten problem, wybierz miejsce, a następnie wybierz pozycję **Usuń**. Po usunięciu przestrzeni HoloLens mapować otaczający obszar i utworzyć nową przestrzeń.

[Powrót do listy](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>Hologramy znika lub są zamknięte w innych hologramach lub obiektach

Jeśli za bardzo zbliżysz się do hologramu, tymczasowo zniknie, aby przywrócić hologram, po prostu &mdash; odchodzisz od niego. Ponadto, jeśli kilka hologramów zostanie umieszczonych blisko siebie, niektóre mogą zniknąć. Spróbuj usunąć kilka.

Hologramy mogą być również blokowane lub zamknięte innymi hologramami lub obiektami, takimi jak ściany. W takim przypadku wypróbuj jedną z następujących poprawek:

- Jeśli hologram jest ocypowany na innym hologramie, przenieś go do innej lokalizacji. W tym celu wybierz pozycję **Dostosuj**, a następnie naciśnij i przytrzymaj, aby ją umieścić.
- Jeśli hologram jest zawijany na ścianie, wybierz pozycję **Dostosuj**, a następnie przechodz w kierunku tablicy, aż pojawi się hologram. Naciśnij i przytrzymaj, a następnie ściągnij hologram do przodu i z ściany.
- Jeśli nie możesz przenieść hologramu za pomocą gestów, użyj głosu, aby go usunąć. Spojrz na hologram, a następnie powiedz "Remove" (Usuń). Następnie otwórz ponownie hologram i umieść go w nowej lokalizacji.

[Powrót do listy](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a>Hologramy są wyświetlane po drugiej stronie ściany

Jeśli jesteś bardzo blisko ściany lub jeśli HoloLens nie zeskanowała jeszcze ściany, możesz zobaczyć hologramy, które znajdują się w następnym pomieszczeniu. Aby przeskanować tablicę, odstaj od jednego do trzech metrów od ściany i spojrz na nie.

Czarny lub odbicia obiekt (na przykład czarną sofę lub chłodziarkę z chłodziarkami z chłodziarkami z chłodziarki) w pobliżu ściany może spowodować problemy, HoloLens spróbuje przeskanować ściany. Jeśli istnieje taki obiekt, przeskanuj drugą stronę ściany.

[Powrót do listy](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a>Po umieszczeniu hologramu na ścianie wydaje się on zmiennoprzecinkowy

Hologram, który umieszczasz na ścianie, zazwyczaj wygląda jak cal lub tak daleko od ściany. Jeśli wydaje się, że znajduje się ona dalej, wypróbuj co najmniej jedną z następujących poprawek:

- Gdy umieszczasz hologram na ścianie, odstaj od jednego do trzech metrów od ściany i odstaj na prostą ściany.
- Naciśnij w powietrzu ściany, aby ujawnić grafikę siatki mapowania. Upewnij się, że siatka jest wyrównana z ścianą. Jeśli tak się nie stanie, usuń hologram, ponownie przeskanuj ściany, a następnie spróbuj ponownie.
- Jeśli problem będzie się powtarzać, uruchom aplikację Wyliczy. Znajdziesz go w programie **Ustawienia**  >  **System**  >  **Utilities**.

[Powrót do listy](#list)

## <a name="apps-appear-too-close-after-moving-them"></a>Aplikacje są wyświetlane zbyt blisko po przeniesieniu

Spróbuj pomiązyć i zaglądać do obszaru, w którym umieszczasz aplikację, tak aby HoloLens przeskanować obszar pod różnymi kątami. [Pomocne może być również wyczyszczenie](hololens1-hardware.md#care-and-cleaning) urządzenia.

[Powrót do listy](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a>Zgłaszanie problemów z niestabilnymi lub nieakcyjnie hologramami
 
1. Nagraj [i Przechwytywanie rzeczywistości mieszanej wideo](holographic-photos-and-videos.md#capture-a-mixed-reality-video) o problemie. Ten film wideo można później przekazać za pośrednictwem Centrum opinii jako dołączony plik.  
1. Włącz pełną telemetrię za **pośrednictwem aplikacji Ustawienia** - > **Privacy** Diagnostics & i w obszarze Opcjonalne dane diagnostyczne upewnij się, że przełącznik jest  ->   **wł.** 
1. Uzyskaj najnowsze poprawki dotyczące skali i stabilności hologramów, aktualizując system [operacyjny Windows Holographic (20H2 lub wyższy).](hololens-release-notes.md#windows-holographic-version-20h2) Po aktualizacji wykonaj następujące czynności:
    1. Usuń wszystkie Hologramy za pomocą **Ustawienia** app -> **System** Hologramy -> następnie wybierz pozycję Usuń wszystkie  ->   **hologramy** i zacznij od nowej mapy.
    1. Utwórz nową mapę przestrzeni, nosząc HoloLens i przechodząc po pomieszczeniu oraz patrząc na wszystkie obszary i powierzchnie w przestrzeni. Zrób to przez 2–3 minuty.
    1. Wykonaj czynności z adresu IPD. Przejdź do **Ustawienia**  >  **Narzędzia**  >  **systemowe**. W **obszarze Podniesieć** wybierz **pozycję Otwórz drukarkę.**
    1. Ponownie przetestuj scenariusz i sprawdź, czy nadal będzie się powtarzać.
1. Jeśli aktualizacja nie rozwiąże problemu, Centrum opinii [problem](hololens-feedback.md). Po przesłaniu opinii możesz użyć  przycisku Udostępnij, aby utworzyć łatwy do udostępnienia link, który można wysłać podczas kontaktowania się z pomocą techniczną.

[Powrót do listy](#list)