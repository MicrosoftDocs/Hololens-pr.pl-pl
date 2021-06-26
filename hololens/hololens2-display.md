---
title: Rozwiązywanie problemów z wyświetlaniem urządzenia HoloLens 2
description: Zostaną wyświetlone oczekiwania dotyczące urządzenia HoloLens 2. Wskazówki dotyczące konfigurowania ekranów w celu zapewnienia najlepszej jakości obrazu.
author: BrandonBray
ms.author: branbray
ms.date: 8/13/2020
ms.topic: article
keywords: display, wymuszenie, komfort, wizualizacje, jakość, ipd
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 96bacd79d559bc0adcd42665c4a8b4af856b58b0
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923622"
---
# <a name="hololens-2-display-troubleshooting"></a>Rozwiązywanie problemów z wyświetlaniem urządzenia HoloLens 2

## <a name="overview"></a>Omówienie
Ekran HoloLens 2 jest kombinacją falowodnych projektorów i projektorów światła. Podczas noszenia zestawu nagłownego użytkownicy zaglądaj przez falowody — obiektywy wewnątrz środka nagłownego. Żarówki znajdują się wewnątrz obudowy nad browem. Urządzenie HoloLens 2 używa światła laserowego do ująć ekran.

## <a name="troubleshooting"></a>Rozwiązywanie problemów

Aby zapewnić najwyższą jakość wizualną hologramów prezentowanych na ekranach, należy wykonać następujące czynności:

* **Zwiększ jasność ekranu.** Hologramy wyglądają najlepiej, gdy ekran jest na najjaśniejszym poziomie. W przypadku noszenia urządzenia HoloLens przyciski jasność znajdują się po lewej stronie funkcji odszyblniania w pobliżu twojego sklepu.
* **Przybliż wzrok przybliż jej wzrok.** Rozsuń wizjer w dół do najbliższej pozycji oczu.
* **Przesuwaj w dół.** Spróbuj przesunąć ekran do góry na dół, co spowoduje, że oszławica przybliża nos.
* **[Wybiegaj wzrok.](hololens-calibration.md#calibrating-your-hololens-2)** Ekran wykorzystuje odległość międzypoczelniową (IPD) i spojrzenie na oko, aby zoptymalizować obrazy na ekranie. Jeśli nie przejedzesz na oko, jakość obrazu może się pogorszyć. Aby uruchomić wzrok, przejdź do strony **Ustawienia**  >  **System**  >  **IoT**  >  **Run eye i**.
* **Uruchom kolor wyświetlania .** Na  [platformie Windows Holographic w wersji 21H1](hololens-release-notes.md#windows-holographic-version-21h1) lub dalszej można wybrać alternatywny profil kolorów dla ekranu HoloLens 2. Może to ułatwić wyświetlanie kolorów bardziej precyzyjnych, szczególnie na niższych poziomach jasność ekranu. Kolor wyświetlania można znaleźć w aplikacji **Ustawienia** na stronie System **> Temat kolorów.**

    > [!NOTE]
    > Ponieważ to ustawienie zapisuje nowy profil kolorów w oprogramowaniu układowym wyświetlania, jest to ustawienie dla poszczególnych urządzeń (i nie jest unikatowe dla każdego konta użytkownika).

### <a name="how-to-use-display-color-calibration"></a>Jak używać kolorów wyświetlania
1. Uruchom aplikację **Ustawienia** i przejdź do witryny **System > IoT .**
1. W **obszarze Wyświetl kolor zgodnie** z kolorami wybierz przycisk Uruchom wyświetlanie **koloru.**
1. Zostanie uruchomić środowisko kolorowania wyświetlania, które będzie zachęcało do upewninia się, że twoja przyszła pozycja jest poprawna.
1. Po zakończeniu pracy z oknami dialogowymi instrukcji ekran zostanie automatycznie wygaszony do 30%.
    > [!TIP]
    > Jeśli masz problemy z wyświetlaniem wygaszanej sceny w środowisku, możesz ręcznie dostosować poziom jasność urządzenia HoloLens 2 przy użyciu przycisków jasność po lewej stronie urządzenia.
1. Wybierz przyciski od 1 do 6, aby natychmiast wypróbować każdy profil kolorów i znaleźć taki, który wygląda najlepiej dla Twoich oczu (zazwyczaj oznacza to, że profil, który pomaga scenie wyglądać na najbardziej neutralną, z wzorcem skali szarości i kolorem wyglądającym zgodnie z oczekiwaniami).

    ![Wyświetlanie sceny z natłokami kolorów](images/color-cal-ui.png)
    
6. Jeśli wybrany profil ci się przyjmuje, wybierz przycisk **Save & Exit (Zapisz** & zakończ).
1. Jeśli nie chcesz wprowadzać zmian, wybierz przycisk Anuluj & **zakończ,** a zmiany zostaną przywrócone

> [!TIP]
> Poniżej podano kilka przydatnych wskazówek, które należy mieć na uwadze podczas korzystania z ustawienia koloru wyświetlania:
> - Zawsze, gdy chcesz, możesz ponownie uruchomić ustawienia kolorów wyświetlania w ustawieniach
> - Jeśli ktoś na urządzeniu wcześniej użył tego ustawienia do zmiany profilów kolorów, data/godzina ostatniej zmiany zostanie odzwierciedlona na stronie Ustawienia
> - Po uruchomieniu ponownie kolorowania wyświetlania profil kolorów, który został wcześniej zapisany, zostanie wyróżniony, a profil 0 nie będzie wyświetlany (ponieważ profil 0 reprezentuje oryginalny profil koloru ekranu)
> - Jeśli chcesz przywrócić oryginalny profil koloru ekranu, możesz to zrobić na stronie Ustawienia (zobacz, [jak zresetować profil kolorów](#how-to-reset-color-profile))

### <a name="how-to-reset-color-profile"></a>Jak zresetować profil kolorów

Jeśli niestandardowy profil kolorów zapisany na urządzeniu HoloLens 2 jest niezadowolony, możesz przywrócić oryginalny profil kolorów urządzenia:
1. Uruchom aplikację **Ustawienia** i przejdź do witryny **System > IoT .**
1. W **obszarze Wyświetl kolor kolor** wybierz przycisk **Przywróć domyślny profil** kolorów.
1. Gdy zostanie otwarte okno dialogowe, wybierz **pozycję** Uruchom ponownie, jeśli wszystko jest gotowe do ponownego uruchomienia urządzenia HoloLens 2 i zastosowania zmian.

### <a name="top-display-color-calibration-known-issues"></a>Znane problemy dotyczące najniebędszego kolorowania kolorów

- Na stronie Ustawienia ciąg stanu, który informuje o tym, kiedy profil kolorów został ostatnio zmieniony, będzie aktualny do momentu ponownego załadowania tej strony ustawień 
    - **Obejście:** Wybierz inną stronę Ustawienia, a następnie ponownie wybierz stronę Wynisz.
- Jeśli urządzenie HoloLens 2 przejdzie w stan uśpienia podczas wyświetlania koloru, zostanie później wznowione do domu rzeczywistości mieszanej, a poziom jasność ekranu nadal będzie wygaszony.
- Może być konieczne kilkukrotnie naciśnięcie przycisków jasność po lewej stronie urządzenia w górę/w dół, zanim będą one działać zgodnie z oczekiwaniami.
- Lokalizacja nie jest kompletna dla wszystkich rynków

## <a name="faq"></a>Często zadawane pytania

### <a name="what-are-the-patterns-that-occasionally-flash-in-the-bottom-corners-of-the-display"></a>Jakie wzorce od czasu do czasu migają w dolnych narożnikach ekranu?

Czasami urządzenie HoloLens 2 będzie wyświetlać różne wzorce w lewym dolnym i prawym rogu ekranu. Poniżej przedstawiono przykłady (animowane obrazy GIF). Ten wzorzec jest częścią normalnego działania urządzenia HoloLens 2 w celu skalibrowania ekranu w celu uzyskania optymalnego doświadczenia.

![Wzorzec dwufazowy](./images/DAT-Biphase-Fiducial.gif) ![Wzorzec GEO](./images/DAT-GEO-Fiducial.gif)

### <a name="why-am-i-unable-to-take-an-accurate-photograph-of-my-hololens-2-display"></a>Dlaczego nie mogę zrobić dokładnego zdjęcia urządzenia HoloLens 2?

Ekran Urządzenia HoloLens 2 został zaprojektowany z myślą o widoku ludzkiego oka. Urządzenie ma aktywny system korekcji kolorów, który dostosowuje się do oczu użytkownika. W porównaniu do ludzkiego oka, kamery widzą środowiska inaczej i poniżej przedstawiono pewne czynniki, które mogą mieć wpływ na niespójność między tym, co kamery przechwyci, a tym, co widzi użytkownik.

* **Położenie oka.** Ekran HoloLens 2 został zaprojektowany specjalnie z myślą o położeniu oka użytkownika. Urządzenie HoloLens 2 wykorzystuje technologię śledzenia wzroku, aby dostosować się do położenia wzroku użytkownika. Aparat, który jest nieprawidłowo pozycjonowany o kilka milimetrów, może prowadzić do zniekształcenia obrazu. Dokładne pozycjonowanie za pomocą aparatu jest trudne i musi być zgodne z dokładną lokalizacją i odciążenia wzroku, dla którego urządzenie wykonuje korektę kolorów.
* **Ruch oczu.** Ekran dostosowuje się do ruchu oka użytkownika w celu dostosowania kolorów. To, co jest wyświetlane na ekranie, może się różnić w zależności od tego, czy użytkownik patrzy na środek, krawędź, czy róg ekranu. Przechwytywanie pojedynczego obrazu może w najlepszym przypadku pokazać tylko wygląd ekranu dla osi, która pasuje do kierunku spojrzenia oczu.
* **Wyświetlanie binokularne.** Ekran urządzenia HoloLens 2 zaprojektowano pod kątem wyświetlania obu oczu. Mózg dostosowuje się do dwóch obrazów i łączy je ze sobą. Obrazy tylko jednego z nich ignorują informacje z drugiego ekranu.
* **Czas narażenia aparatu.** Czas narażenia aparatu musi być dokładną wielokrotnością 1/120 sekundy. Częstotliwość wyświetlania ramki urządzenia HoloLens wynosi 120 Hz. Ze względu na sposób, w jaki urządzenie HoloLens 2 rysuje obrazy, przechwytywanie pojedynczej ramki również nie wystarczy, aby dopasować je do wizualnego doświadczenia człowieka. W tym samym czasie, jeśli urządzenie zostanie w ogóle przemieszczane — nawet mikroukładzie — system ponownie wyprojektuje obraz na ekranie, aby ustabilizować hologramy. Przechwytywanie wielu ramek przy jednoczesnym zachowaniu przed przenoszeniem urządzenia HoloLens zwykle wymaga konfiguracji laboratoryjnej.
* **Rozmiar aparatu fotograficznego.** Rozmiar aparatu musi być co najmniej 3 mm, aby można było przechwycić dokładny obraz. Kamery do telefonów komórkowych z małymi węzłami integrują światło z mniejszego obszaru niż ludzkie oko. Urządzenie stosuje korektę kolorów dla wzorców obserwowanych przez większe rozmiary. W przypadku małych łysek wzorce jednolitych są ostrzejsze i pozostają widoczne pomimo poprawek kolorów stosowanych przez system.
* **Kamery na zdjęciach.** W celu przechwycenia dokładnego obrazu źrenicę aparatu powinna mieć co najmniej 3 mm szerokości. W przeciwnym razie aparat przechwyci niektóre wzorce wysokiej częstotliwości, które nie są widoczne dla oka. Położenie źrenicy na wejściu musi być przed kamerą i umieszczone w odległości odciążenia oka, aby uniknąć wprowadzenia aberracji i innych odmian przechwyconego obrazu.
* **Położenie kamery.** Kamery, które spełniają wymagania dotyczące wyświetlania ekranu HoloLens 2, są większe i trudno jest ustawić aparat wystarczająco blisko ekranu HoloLens 2, aby zaobserwować poprawiony kolor obrazu. Jeśli aparat znajduje się w niewłaściwym miejscu, korekta kolorów może negatywnie wpłynąć na przechwytywanie ekranu HoloLens 2.
* **Korekta obrazu.** Typowe aparaty cyfrowe i smartfony stosują krzywą reprodukcyjną (TRC), która zwiększa kontrast i kolor, aby zapewnić lepsze wyniki. Po zastosowaniu na ekranie urządzenia HoloLens 2 ta krzywa tonu wzmacnia nieujemności.

Wszystkie te informacje są jednak nadal możliwe w przypadku wyspecjalizowanych aparatów przemysłowych, które przechwytują reprezentatywne obrazy z ekranu HoloLens 2. Niestety smartfony, kamery dla konsumentów i profesjonalistów nie przechwytują obrazów, które pasują do tego, co użytkownik widzi na urządzeniach HoloLens 2.

### <a name="what-does-eye-calibration-do-to-display-image-quality"></a>Co robi wzrok, aby wyświetlić jakość obrazu?

Ekran urządzenia HoloLens 2 aktywnie koloruje obrazy na podstawie położenia oczu użytkownika. [Pomiar wzroku](hololens-calibration.md) zapewnia dwa ważne dane wejściowe: (1) odległość międzywęzową użytkownika (IPD) i (2) kierunek, w jakim patrzy każde oko. Bez układu wzrokowego system domyślnie ma nominalną pozycję oka bez ruchu oczu. Różnica między aktywną korektą kolorów a żadną korektą zależy od fizjologii użytkownika. Na przykład użytkownicy, którzy mają ten sam adres IPD co domyślna wartość systemowa, zobaczą mniej ulepszeń korekty kolorów. Użytkownicy, którzy mają znacznie węższy lub szerszy adres IPD niż domyślny system, zobaczą więcej zmian w obrazie wyświetlanym.

Pamiętaj, że nowa funkcja w systemie Windows Holographic w wersji [20H2](hololens-release-notes.md#windows-holographic-version-20h2) rozpocznie [automatyczne wykrywanie pozycji oka.](hololens-calibration.md#auto-eye-position-support) 

### <a name="what-are-the-display-differences-between-hololens-1st-gen-and-hololens-2"></a>Jakie są różnice między wyświetlaniem urządzenia HoloLens (1. generacji) i urządzenia HoloLens 2?

Wśród żądań, które klienci podali firmie Microsoft po napotkaniu urządzenia HoloLens 1, było (1) zwiększenie pola widzenia i (2) zwiększenie jasność. Rozwój technologii umożliwił firmie Microsoft tworzenie falowodów, które podwajały obszar pola widzenia i tworzyć projektory światła z ekranem, który jest maksymalnie trzy razy jaśniejszy. Sprzęt ustawia punkt odniesienia dla kilku kompromisów w zakresie jakości obrazu wyświetlanego: (1) pola widzenia, (2) jasność i (3) jednolity kolor. Dalszy postęp technologiczny umożliwia ulepszenia we wszystkich obszarach bez poświęcania innego obszaru. W międzyczasie istniejąca technologia określa limity dostępne dla tych kompromisów.

### <a name="what-improvements-are-coming-that-will-improve-hololens-2-image-quality"></a>Jakie ulepszenia zostaną wprowadzone, aby poprawić jakość obrazu urządzenia HoloLens 2?

Mamy wiele badań w toku w celu poprawy jakości obrazu, jednak w nadchodzących aktualizacjach powinny pojawić się następujące obszary:

* **Automatyczne położenie oka.** Ta funkcja umożliwi w tle procedury odcłaniania oczu. Użytkownicy nie będą już musieli uruchamiać korekcji oczu, aby aktywna korekta kolorów działała. Zamiast tego będzie działać.
* **Ulepszenia kolorów kolorów.** Ta aktualizacja koncentruje się na wartościach kolorów ciemniejszych (na przykład ciemnoszarych). W tej chwili kolory wygaszacza odbierają czerwony ton. Ten problem występuje również wtedy, gdy cały ekran jest wygaszony — cały ekran przejmuje czerwone kolory. Ten problem jest wynikiem zbyt dużej aktywności w kanale koloru czerwonego dla tych ciemniejszych kolorów. Scharakteryzowaliśmy krzywe nachylne promienia promieniowego w tych bardziej wygaszanych kolorach i pracujemy nad zaoferacją procedury ujednania użytkownika. Wynikiem będzie większa dokładność kolorów w całym spektrum jasność. Nie zmieni to wyglądu białych tła przy pełnej jasności. Nadal zalecamy używanie wzorców projektowych w trybie ciemnym w aplikacjach.
* **Tryb odczytu.** Deweloperzy aplikacji mogą realizować kompromis między polem widzenia wyświetlania, aby uzyskać wyższą rozdzielczość kątową. Deweloperzy aplikacji mogą przesłonić macierz projekcji, aby zawartość została wyrenderowana w rozdzielczości rysowania ekranu. Ta funkcja powoduje zmniejszenie pola widzenia o 30% i odpowiednie zwiększenie rozdzielczości kątowej. Trwają prace nad wprowadzeniem tej możliwości do zestawu [narzędzi Mixed Reality Toolkit.](https://github.com/Microsoft/MixedRealityToolkit-Unity) Jeśli jest dostępny, tryb odczytu będzie działać w dowolnym z systemu operacyjnego HoloLens 2 — nie jest zależny od aktualizacji systemu operacyjnego.

Aktualizacje systemu operacyjnego są dostarczane automatycznie. Możesz również przetestować wczesne wersje ulepszeń oprogramowania za pośrednictwem programu insider preview.

### <a name="what-guidance-is-available-for-developers-to-apply-dark-mode-design-principles"></a>Jakie wskazówki są dostępne dla deweloperów dotyczące stosowania zasad projektowania w trybie ciemnym?

Użytkownicy będą mieli najlepsze środowisko w przypadku unikania białych tła. Tryb ciemny to zasada projektowania używana przez aplikacje do używania czarnego lub ciemnego tła. Ustawienia systemu są domyślnie ustawiane na tryb ciemny i można je dostosować, przechodząc do ustawienia  >  **Kolor**  >  **systemu**.

Deweloperom zaleca się, aby postępowali zgodnie ze wskazówkami projektowania w trybie ciemnym:

* [Developer design guidelines for HoloLens displays (Wytyczne dotyczące projektowania dla deweloperów dla wyświetlaczy HoloLens)](https://docs.microsoft.com/windows/mixed-reality/designing-content-for-holographic-display#design-guidelines)
* [Zalecane rozmiary czcionek](https://docs.microsoft.com/windows/mixed-reality/typography#recommended-font-size)

Jeśli hologram wymaga białego tła, rozmiar hologramu musi być mniejszy niż pełne pole widoku wyświetlanego. Ten rozmiar umożliwia użytkownikom ustawienie hologramu w środku ekranu.

### <a name="how-do-you-clean-a-hololens-2-display"></a>Jak wyczyścić ekran HoloLens 2?

Użyj mikrofibry, aby wyczyścić osłonę. Aby odczyścić osłodę, użyj 70% izopropylu do lekkiego nawilżenia szmaty, a następnie wyczyść osłodę. Przeczytaj pełne wskazówki w artykule [HoloLens 2 cleaning FAQ (Czyszczenie urządzenia HoloLens 2 — często zadawane pytania).](hololens2-maintenance.md)
