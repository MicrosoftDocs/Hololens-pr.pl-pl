---
title: HoloLens rozwiązywania problemów z wyświetlaniem w trybie 2
description: Zostaną wyświetlone oczekiwania dotyczące HoloLens 2. Wskazówki dotyczące konfigurowania ekranów w celu zapewnienia najlepszej jakości obrazu.
author: BrandonBray
ms.author: branbray
ms.date: 8/13/2020
ms.topic: article
keywords: display, cyt, komfort, wizualizacje, jakość, ipd
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 38bab16d2d0d4ace5879f00c133d66b9974e4b2a
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036442"
---
# <a name="hololens-2-display-troubleshooting"></a>HoloLens rozwiązywania problemów z wyświetlaniem w trybie 2

## <a name="overview"></a>Omówienie
Ekran HoloLens 2 jest kombinacją falowodów i projektorów jasnych. Użytkownicy patrzą na falowody — obiektywy wewnątrz wizjeru — podczas noszenia zestawu nagłownego. Żarówki znajdują się wewnątrz obudowy nad browem. HoloLens 2 używa światła laserowego do osłaniania ekranu.

## <a name="troubleshooting"></a>Rozwiązywanie problemów

Aby zapewnić najwyższą jakość wizualną hologramów prezentowanych na ekranach, należy wykonać następujące czynności:

* **Zwiększ jasność ekranu.** Hologramy wygląda najlepiej, gdy ekran jest na najjaśniejszym poziomie. W przypadku HoloLens przycisków jasność znajdują się po lewej stronie oszołomyka w pobliżu twojej daszki.
* **Przybliż wzrok wzrokowi.** Rozsuń daszek w dół do pozycji znajdującej się najbliżej Twoich oczu.
* **Przesuwaj w dół.** Spróbuj przesunąć w dół nakładkę do browek, co spowoduje, że oszławik będzie zbliżać się do nosów.
* **[Wybiegaj wzrok.](hololens-calibration.md#calibrating-your-hololens-2)** Ekran używa odległości międzypołudowej (IPD) i spojrzenia okiem, aby zoptymalizować obrazy na ekranie. Jeśli nie uruchamiasz kontroli wzroku, jakość obrazu może się pogorszyć. Aby uruchomić ćwęzienie oczu, przejdź **do Ustawienia**  >    >  **systemowej.**  >  
* **Uruchamianie kolorowania wyświetlania**. Na Windows Holographic w wersji [21H1](hololens-release-notes.md#windows-holographic-version-21h1) i od  tego momentu możesz wybrać alternatywny profil kolorów dla ekranu HoloLens 2. Może to pomóc w dokładniejszej wyświetlaniu kolorów, szczególnie na niższych poziomach jasność ekranu. Kolorowanie wyświetlania można znaleźć w **Ustawienia** aplikacji na stronie **> tematu.**

    > [!NOTE]
    > Ponieważ to ustawienie zapisuje nowy profil kolorów w oprogramowaniu układowym wyświetlania, jest to ustawienie dla poszczególnych urządzeń (i nie jest unikatowe dla każdego konta użytkownika).

### <a name="how-to-use-display-color-calibration"></a>Jak używać kolorowania wyświetlania
1. Uruchom aplikację **Ustawienia** i przejdź do > **System.**
1. W **obszarze Wyświetl kolorowanie** wybierz przycisk **Uruchom wyświetlanie kolorowania.**
1. Rozpocznie się środowisko kolorowania wyświetlania, które będzie zachęcało do upewninia się, że twoja wizja znajduje się we właściwej pozycji.
1. Po zakończeniu pracy z oknami dialogowymi instrukcji ekran zostanie automatycznie wygaszony do 30% jasność.
    > [!TIP]
    > Jeśli masz problemy z wyświetlaniem wygaszanej sceny w środowisku, możesz ręcznie dostosować poziom jasność HoloLens 2 przy użyciu przycisków jasność po lewej stronie urządzenia.
1. Wybierz przyciski od 1 do 6, aby natychmiast wypróbować każdy profil kolorów i znaleźć taki, który wygląda najlepiej dla Twoich oczu (zwykle oznacza to, że profil, który pomaga scenie wyglądać na najbardziej neutralną, ze wzorcem skali szarości i wyglądem oczu zgodnie z oczekiwaniami).

    ![Wyświetlanie sceny natłokania kolorów.](images/color-cal-ui.png)
    
6. Jeśli wybrany profil jest zadowolone, wybierz przycisk **Save & Exit (Zapisz** & zakończ).
1. Jeśli nie chcesz wprowadzać zmian, wybierz przycisk Anuluj & **zakończ,** aby zmiany zostały przywrócone

> [!TIP]
> Poniżej podano kilka przydatnych wskazówek, które należy mieć na uwadze podczas korzystania z ustawienia wyznaczania koloru wyświetlania:
> - Zawsze, gdy chcesz, możesz ponownie Ustawienia wyświetlania kolorów
> - Jeśli każda osoba na urządzeniu wcześniej użyła tego ustawienia do zmiany profilów kolorów, data/godzina ostatniej zmiany zostanie odzwierciedlona na Ustawienia kolorów
> - Po uruchomieniu ponownego kolorowania wyświetlania profil kolorów, który został wcześniej zapisany, zostanie wyróżniony, a profil 0 nie będzie wyświetlany (ponieważ profil 0 reprezentuje oryginalny profil koloru wyświetlania)
> - Jeśli chcesz przywrócić oryginalny profil kolorów ekranu, możesz to zrobić na stronie Ustawienia (zobacz jak [zresetować profil kolorów](#how-to-reset-color-profile))

### <a name="how-to-reset-color-profile"></a>Jak zresetować profil kolorów

Jeśli nie masz niezadowolenia z niestandardowego profilu kolorów zapisanego na urządzeniu HoloLens 2, możesz przywrócić oryginalny profil kolorów urządzenia:
1. Uruchom aplikację **Ustawienia** i przejdź do > **System.**
1. W **obszarze Wyświetlanie kolorowania** wybierz przycisk **Przywróć domyślny profil** kolorów.
1. Gdy zostanie otwarte okno dialogowe, wybierz **pozycję** Uruchom ponownie, jeśli wszystko jest gotowe do ponownego HoloLens 2 i zastosowania zmian.

### <a name="top-display-color-calibration-known-issues"></a>Znane problemy związane z kolorami w górnej części ekranu

- Na stronie Ustawienia ciąg stanu, który informuje o tym, kiedy ostatnio zmieniono profil kolorów, będzie aktualny do momentu ponownego załadowania tej strony Ustawienia 
    - **Obejście:** Wybierz inną Ustawienia, a następnie ponownie wybierz stronę Wylicja.
- Jeśli urządzenie HoloLens 2 przejdzie w stan uśpienia podczas korzystania z kolorowania na ekranie, zostanie później wznowione do domu rzeczywistości mieszanej, a poziom jasność ekranu będzie nadal wygaszony.
- Może być konieczne kilkukrotnie naciśnięcie przycisków jasność po lewej stronie urządzenia w górę/w dół, zanim będą działać zgodnie z oczekiwaniami.
- Lokalizacja nie jest ukończona dla wszystkich rynków

## <a name="faq"></a>Często zadawane pytania

### <a name="what-are-the-patterns-that-occasionally-flash-in-the-bottom-corners-of-the-display"></a>Jakie wzorce czasami migają w dolnych narożnikach ekranu?

Czasami w HoloLens 2 będą wyświetlane różne wzorce w lewym dolnym i prawym rogu ekranu. Poniżej przedstawiono przykłady (animowane obrazy GIF). Ten wzorzec jest częścią normalnego działania urządzenia HoloLens 2 w celu skalibrowania ekranu w celu uzyskania optymalnego doświadczenia.

![Wzorzec dwufazowy.](./images/DAT-Biphase-Fiducial.gif) ![Wzorzec GEO](./images/DAT-GEO-Fiducial.gif)

### <a name="why-am-i-unable-to-take-an-accurate-photograph-of-my-hololens-2-display"></a>Dlaczego nie mogę zrobić dokładnego zdjęcia mojego HoloLens 2?

Ekran HoloLens 2 jest przeznaczony do wyświetlania przez ludzkie oko. Urządzenie ma aktywny system korekcji kolorów, który dostosowuje się do oczu użytkownika. W porównaniu do ludzkiego oka, aparaty widzą środowiska inaczej i poniżej to pewne czynniki, które mogą mieć wpływ na niespójność między tym, co przechwycił aparat, a tym, co widzi użytkownik.

* **Położenie oka.** Ekran HoloLens 2 został zaprojektowany specjalnie z myślą o położeniu oka użytkownika. System HoloLens 2 wykorzystuje technologię śledzenia wzroku, aby dostosować się do pozycji oka użytkownika. Aparat, który jest nieprawidłowo pozycjonowany o kilka milimetrów, może prowadzić do zniekształcenia obrazu. Dokładne pozycjonowanie za pomocą aparatu jest trudne i musi odpowiadać dokładnej lokalizacji i odciążenia oka, dla którego urządzenie wykonuje korektę kolorów.
* **Ruch oczu.** Ekran dostosowuje się do ruchu oka użytkownika w celu dostosowania kolorów. To, co jest wyświetlane na ekranie, może się różnić w zależności od tego, czy użytkownik patrzy na środek, krawędź lub róg ekranu. W najlepszym przypadku przechwytywanie pojedynczego obrazu może pokazywać tylko wygląd ekranu dla osi, która pasuje do kierunku spojrzenia oczu.
* **Wyświetlanie binokularne.** Ekran HoloLens 2 jest przeznaczony do wyświetlania przy użyciu obu oczu. Mózg dostosowuje się do dwóch obrazów i łączy je ze sobą. Obrazy tylko jednego ekranu ignorują informacje z drugiego ekranu.
* **Czas naświetlania aparatu.** Czas narażenia aparatu musi być dokładną wielokrotnością 1/120 sekundy. Szybkość HoloLens ekranu wynosi 120 Hz. Ze względu na sposób, w jaki HoloLens 2 rysuje obrazy, przechwytywanie pojedynczej ramki również nie wystarczy, aby dopasować je do wizualnego doświadczenia człowieka. W tym samym czasie, jeśli urządzenie w ogóle się przemieszcza — nawet mikroukładzie — system reprojects obrazu na ekranie w celu ustabilizowania hologramów. Przechwytywanie wielu ramek przy zachowaniu HoloLens przed przenoszeniem zwykle wymaga konfiguracji laboratorium.
* **Rozmiar aparatu fotograficznego.** Rozmiar aparatu musi być co najmniej 3 mm, aby można było przechwycić dokładny obraz. Kamery do telefonów komórkowych z małymi węzłami integrują światło z mniejszego obszaru niż ludzkie oko. Urządzenie stosuje korektę kolorów dla wzorców obserwowanych przez większe pierścienie. W przypadku małych łydek wzorce równomierności są ostrzejsze i pozostają widoczne pomimo korekt kolorów stosowanych przez system.
* **Kamery na wejściu.** Źrenicy węzła kamery powinny mieć co najmniej 3 mm w celu przechwycenia dokładnego obrazu. W przeciwnym razie aparat przechwyci pewne wzorce wysokiej częstotliwości, które nie są widoczne dla oka. Położenie źrenicy wejściowej musi być przed kamerą i umieszczone w odległości odciążenia oka, aby uniknąć wprowadzenia aberracji i innych wariacji do przechwyconego obrazu.
* **Położenie kamery.** Kamery spełniające wymagania dotyczące wyświetlania ekranu HoloLens 2 są większe i trudno jest ustawić aparat wystarczająco blisko ekranu HoloLens 2, aby zaobserwować poprawiony kolor obrazu. Jeśli aparat znajduje się w niewłaściwym miejscu, korekta koloru może negatywnie wpłynąć na przechwytywanie HoloLens 2.
* **Korekta obrazu.** Typowe cyfrowe aparaty fotograficzne i smartfony stosują krzywą reprodukcyjną (TRC), która zwiększa kontrast i kolor, aby zapewnić lepsze wyniki. Po zastosowaniu do HoloLens 2 ta krzywa tonu wzmacnia nieujedności.

Jak już ująliśmy, wyspecjalizowane kamery przemysłowe mogą przechwytywać reprezentatywne obrazy z ekranu HoloLens 2. Niestety smartfony, smartfony, konsument i profesjonalne aparaty fotograficzne nie będą przechwytywać obrazów, które są zgodne z tym, co użytkownik widzi na ekranie HoloLens 2.

### <a name="what-does-eye-calibration-do-to-display-image-quality"></a>Co robi wzrok, aby wyświetlić jakość obrazu?

Ekran HoloLens 2 aktywnie koloruje obrazy na podstawie położenia oczu użytkownika. [Wzrok zapewnia](hololens-calibration.md) dwa ważne dane wejściowe: (1) odległość międzypobiegową użytkownika (IPD) i (2) kierunek, w jakim patrzy każde okiem. Bez wzroku system domyślnie ma nominalną pozycję okiem bez ruchu oczu. Różnica między aktywną korektą kolorów a żadną korektą zależy od fizjologii użytkownika. Na przykład użytkownicy, którzy mają ten sam adres IPD co domyślna wartość systemowa, zobaczą mniejszą liczbę ulepszeń korekty kolorów. Użytkownicy, którzy mają znacznie węższy lub szerszy adres IPD niż domyślna wartość systemowa, zobaczą więcej zmian w obrazie wyświetlanym.

Pamiętaj, że nowa funkcja w Windows Holographic w wersji [20H2](hololens-release-notes.md#windows-holographic-version-20h2) rozpocznie automatyczne [wykrywanie pozycji oka.](hololens-calibration.md#auto-eye-position-support) 

### <a name="what-are-the-display-differences-between-hololens-1st-gen-and-hololens-2"></a>Jakie są różnice między wyświetlaniem HoloLens (1. generacja) i HoloLens 2?

Wśród najślidszych żądań, które klient udzielił firmie Microsoft po HoloLens 1, było (1) zwiększenie pola widzenia i (2) zwiększenie jasność. Rozwój technologii umożliwił firmie Microsoft tworzenie falowodów, które podwoiły obszar widoku, i wyświetlenie projektorów jasnych z ekranem, który jest maksymalnie trzy razy jaśniejszy. Sprzęt ustawia punkt odniesienia dla kompromisów dla jakości obrazu wyświetlanego: (1) pola widzenia, (2) jasność i (3) jednolity kolor. Dalszy postęp technologiczny umożliwia ulepszenia we wszystkich obszarach bez poświęcania innego obszaru. W międzyczasie istniejąca technologia określa limity dostępne dla tych kompromisów.

### <a name="what-improvements-are-coming-that-will-improve-hololens-2-image-quality"></a>Jakie ulepszenia zostaną wprowadzone, które poprawią HoloLens 2 obrazów?

Mamy wiele badań w toku w celu poprawy jakości obrazu, jednak oczekuje się, że w nadchodzących aktualizacjach pojawią się następujące obszary:

* **Automatyczne położenie oka.** Ta funkcja umożliwi w tle obsługę procedur odwłoceń oczu. Użytkownicy nie będą już musieli uruchamiać korekt oczu, aby aktywna korekta kolorów działała. Zamiast tego po prostu będzie działać.
* **Ulepszenia kolorów i kolorów.** Ta aktualizacja koncentruje się na wartościach kolorów ciemniejszych (na przykład ciemnoszarych). W tej chwili kolory wygaszacza zbierają czerwony ton. Ten problem występuje również wtedy, gdy cały ekran jest wygaszony — cały ekran przejmuje czerwone kolory. Ten problem jest wynikiem zbyt dużej aktywności w czerwonym kanale kolorów dla tych ciemniejszych kolorów. Scharakteryzowaliśmy krzywą promieniową w tych wygaszanych kolorach i pracujemy nad zaoferacją procedury odszumiania użytkowników. Wynikiem będzie większa dokładność kolorów w całym spektrum jasność. Nie zmieni to wyglądu białych tła przy pełnej jasność. Nadal zalecamy używanie wzorców projektowych w trybie ciemnym w aplikacjach.
* **Tryb odczytu.** Deweloperzy aplikacji mogą dorównować widokowi wyświetlania, aby uzyskać wyższą rozdzielczość kątową. Deweloperzy aplikacji mogą przesłonić macierz projekcji, aby zawartość została wyrenderowana w rozdzielczości rysowania na ekranie. Ta funkcja powoduje 30- procentowy spadek pola widzenia i odpowiedni wzrost rozdzielczości kątowej. Trwa praca nad wprowadzeniem tej możliwości do [zestawu narzędzi Mixed Reality Toolkit.](https://github.com/Microsoft/MixedRealityToolkit-Unity) Jeśli jest dostępny, tryb odczytu będzie działać w HoloLens systemu operacyjnego 2 — nie jest on zależny od aktualizacji systemu operacyjnego.

Aktualizacje systemu operacyjnego są dostarczane automatycznie. Możesz również przetestować wczesne wersje ulepszeń oprogramowania za pośrednictwem programu insider preview.

### <a name="what-guidance-is-available-for-developers-to-apply-dark-mode-design-principles"></a>Jakie wskazówki są dostępne dla deweloperów dotyczące stosowania zasad projektowania w trybie ciemnym?

Użytkownicy będą mieli najlepsze środowisko w przypadku unikania białych tła. Tryb ciemny to zasada projektowania używana przez aplikacje do używania czarnych lub ciemnych tła. Ustawienia systemu są domyślnie ustawiane na tryb ciemny i można je dostosować, przechodząc **do Ustawienia**  >  **System**  >  **Color**.

Deweloperom zaleca się, aby postępowali zgodnie ze wskazówkami projektowania w trybie ciemnym:

* [Wytyczne dotyczące projektowania aplikacji dla HoloLens ekranów](/windows/mixed-reality/designing-content-for-holographic-display#design-guidelines)
* [Zalecane rozmiary czcionek](/windows/mixed-reality/typography#recommended-font-size)

Jeśli holoogram wymaga białego tła, zachowaj rozmiar hologramów mniejszy niż pełne pole widoku na ekranie. Ten rozmiar umożliwia użytkownikom umieszczanie hologramu w środku ekranu.

### <a name="how-do-you-clean-a-hololens-2-display"></a>Jak wyczyścić ekran HoloLens 2?

Użyj mikrofibry, aby wyczyścić osłonę. Aby odczyszczyć osłodę, użyj 70% 70% składników izopropylowych, aby jasno naizolować go, a następnie wyczyścić go. Pełne wskazówki można znaleźć w [często zadawanych pytaniach dotyczących czyszczenia HoloLens 2.](hololens2-maintenance.md)
