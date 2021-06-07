---
title: Poprawianie jakości i komfortu wizualizacji
description: Dowiedz się, jak skalibrować odległość między kolumnami (IPD), aby poprawić jakość wizualizacji na urządzeniach HoloLens.
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: jego wygląd, komfort, wizualizacje, jakość, ipd, HoloLens, Windows Mixed Reality, zestawy VR
ms.openlocfilehash: e975e2ccd978d4ec6b5331af0ae566af116711c5
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379683"
---
# <a name="improve-visual-quality-and-comfort"></a>Poprawianie jakości i komfortu wizualizacji

Zarówno urządzenia HoloLens 2, jak i HoloLens (1. generacja) działają lepiej, gdy są skalibrowane do unikatowych oczu.

Oba urządzenia muszą być skalibrowane w celu najlepszego przeglądania hologramów, ale korzystają z różnych technologii i technik.  Przejdź do [urządzenia HoloLens 2 lub](#calibrating-your-hololens-2) [holoLens (1. generacji).](#calibrating-your-hololens-1st-gen)

## <a name="calibrating-your-hololens-2"></a>Skalibrowanie urządzenia HoloLens 2

Urządzenie HoloLens 2 używa technologii śledzenia wzroku, aby ulepszyć środowisko użytkownika i interakcję ze środowiskiem wirtualnym. Skalibrowanie urządzenia HoloLens 2 zapewnia możliwość dokładnego śledzenia oczu (i oczu innych osób, które będą korzystać z urządzenia). Pomaga również zapewnić komfort użytkownika, wyrównanie hologramów i śledzenie rąk. Po nachłoeniu hologramy będą wyświetlane prawidłowo nawet wtedy, gdy przyszła na twoją łbę.

Urządzenie HoloLens 2 monituje użytkownika o skalibrowanie urządzenia w następujących okolicznościach:

- Użytkownik korzysta z urządzenia po raz pierwszy
- Użytkownik wcześniej zrezygnował z procesu procesowego
- Proces odszukania nie powieść się, gdy użytkownik użył urządzenia
- Użytkownik usunął profile profilów profilów profilów profilów
- Urządzenie jest wyłączane i ponownie stosowane, a każda z powyższych sytuacji ma zastosowanie 


![Monit o dostosowanie do oczu.](./images/07-et-adjust-for-your-eyes.png)

W trakcie tego procesu przyjrzymy się zestawowi celów (gemom). Jest w porządku, jeśli migasz podczas ciąży, ale spróbujesz skupić się na gemach, a nie na innych obiektach w pomieszczeniu.  Skupienie się na urządzeniach Gem umożliwia urządzeniem HoloLens poznanie pozycji wzrokowej w celu renderowania świata holograficznego.

![Monit o monitowanie użytkownika o utrzymanie głowy w miejscu i obserwowanie kropek przy oku.](./images/07-et-hold-head-still.png)

![Monit o monit za pomocą przykładu gem.](./images/08-et-gems.png)

![Dostosowywanie monitu o monitowanie.](./images/09-et-adjusting.png)

Jeśli uda się to zrobić, zostanie wyświetlony ekran sukcesu.  Jeśli nie, przeczytaj więcej na [temat diagnozowania błędów awarii.](#troubleshooting-hololens-2-calibration)

![Monit o powodzenie monitu.](./images/10-et-success.png)

### <a name="calibration-when-sharing-a-device-or-session"></a>Podczas udostępniania urządzenia lub sesji

Wielu użytkowników może współużytkować urządzenie HoloLens 2 bez konieczności poszczególnych użytkowników podczas konfigurowania urządzenia. Gdy nowy użytkownik po raz pierwszy przyłoży urządzenie do głowy, urządzenie HoloLens 2 automatycznie monituje użytkownika o skalibrowanie wizualizacji. Gdy użytkownik, który wcześniej skalibrował wizualizacje, umieszcza urządzenie na głowy, ekran jest bezproblemowo dostosowywany pod kątem jakości i wygodnego wyświetlania.  

### <a name="manually-starting-the-calibration-process"></a>Ręczne uruchamianie procesu procesowego

1. Użyj gestu start, aby otworzyć menu [ **Start**](hololens2-basic-usage.md#start-gesture).
1. Jeśli aplikacja Ustawienia nie jest przypięta do menu **Start,** wybierz **pozycję Wszystkie aplikacje.**
1. Wybierz **pozycję Settings**(Ustawienia), a następnie wybierz pozycję **System**  >  **Pogoń** z  >  **okiem Run** eye i wybierz pozycję Run eye w  >  **1996 roku.**

   ![Aplikacja Ustawienia z wyświetloną opcją "Uruchom z okiem"](./images/C-Settings.Calibration.png)

### <a name="auto-eye-position-support"></a>Obsługa automatycznego położenia oka

Na urządzeniach HoloLens 2 położenia oczu umożliwiają dokładne pozycjonowanie hologramów, wygodne środowisko wyświetlania i lepszą jakość wyświetlania. Pozycje oka są obliczane wewnętrznie w ramach obliczeń śledzenia wzroku. Jednak wymaga to, aby każdy użytkownik przechodził przez śledzenie wzroku, nawet wtedy, gdy środowisko może nie wymagać danych wejściowych spojrzenia wzrokowego.

**Funkcja Automatycznego położenia oka (AEP, Auto Eye Position)** umożliwia tym scenariuszom bez interakcji obliczanie pozycji oka dla użytkownika. Automatyczne położenie oka automatycznie rozpoczyna pracę w tle od momentu, gdy użytkownik umieścił urządzenie. Jeśli użytkownik nie ma wcześniejszego śledzenia wzroku, funkcja automatycznego położenia oka zacznie dostarczać informacje o pozycjach oka użytkownika do systemu wyświetlania po czasie przetwarzania 20–30 sekund. Dane użytkownika nie są utrwalane na urządzeniu i ten proces jest powtarzany, jeśli użytkownik wystartuje i ponownie uruchomi urządzenie lub jeśli urządzenie zostanie ponownie uruchomiony lub wznowiony po uśpieniu.

Istnieje kilka zmian zachowania systemu za pomocą funkcji automatycznego rozsyłania okiem, gdy użytkownik nieskalowany umieszcza urządzenie. W tym kontekście użytkownik nieskalibrowany odwołuje się do osoby, która wcześniej nie przechodziła przez proces śledzenia wzroku na urządzeniu.

| Aktywna aplikacja | Wcześniejsze zachowanie | Zachowanie z systemu Windows Holographic, aktualizacja w wersji 20H2 |
|:-------------------|:-----------------|:-----------------------------------|
| Aplikacja bez obsługi spojrzenia lub powłoka Holographic Shell |Zostanie wyświetlone okno dialogowe monitu o śledzenie oczu. | Monit nie jest wyświetlany. |
| Aplikacja z obsługą spojrzenia | Zostanie wyświetlone okno dialogowe monitu o śledzenie oczu. | Monit o śledzenie oczu jest wyświetlany tylko wtedy, gdy aplikacja uzyskuje dostęp do strumienia oczu. |

Jeśli użytkownik przechodzi z aplikacji bez włączonego spojrzenia do aplikacji, która uzyskuje dostęp do danych spojrzenia, zostanie wyświetlony monit o monit. 

Wszystkie inne zachowania systemu będą podobne do zachowania bieżącego użytkownika, który nie ma aktywnego śledzenia wzroku. Na przykład gest One-handed Start nie zostanie włączony. Nie będzie żadnych zmian w zakresie out-of-box-experience na potrzeby konfiguracji początkowej.

W przypadku doświadczeń, które wymagają danych o oku lub precyzyjnego pozycjonowania hologramu, zalecamy użytkownikom nieskalicznym uruchamianie śledzenia oczu. Jest on dostępny z monitu o śledzenie wzroku lub przez uruchomienie aplikacji Ustawienia z menu Start, a następnie wybranie pozycji System > Wymusienie **> Eye w**> Uruchomienie oka .

#### <a name="deferred-calibration-prompt"></a>Monit o odroczone monity o odroczone monity

W przypadku ustawienia pozycji automatycznego oka okno dialogowe monitu o śledzenie oczu jest odroczone do momentu, gdy aplikacja zażąda danych aplikacji Eye Gaze. Dzięki temu użytkownik nie będzie monitować, gdy aktywna aplikacja nie wymaga spojrzenia. Jeśli aplikacja wymaga danych spojrzenia, a bieżący użytkownik nie jest skalibrowany, zostanie wyświetlony monit o monit o monit. To zachowanie może służyć do wyświetlania monitu o śledzenie wzroku w odpowiednim czasie dla tego doświadczenia. Ta metoda jest zalecana z następujących powodów

1.  Okno dialogowe monitu o śledzenie oczu udostępnia użytkownikowi szczegółowe informacje na temat tego, dlaczego jest potrzebne śledzenie oczu.
2.  Przedstawia użytkownikowi sposób odrzucania skalibrowania oczu.

Jeśli użytkownik zdecyduje się na uruchomienie aplikacji Eye Tracking Tracking, fokus powinien zostać zwrócony do oryginalnej aplikacji po zakończeniu śledzenia. 

### <a name="troubleshooting-hololens-2-calibration"></a>Rozwiązywanie problemów z urządzeniem HoloLens 2

Większość osób powinna pracować, ale istnieją przypadki, w których niepowodzeniem.
  
Niektóre potencjalne przyczyny niepowodzenia awarii to:

- Rozpraszanie uwagi i niesłanianie celów docelowych
- Zanieczyszczona lub zadrzewiona osłona urządzenia lub urządzenie nie jest prawidłowo pozycjonowane
- Zanieczyszczone lub porysowane okulary
- Niektóre typy obiektywów i okularów kontaktowych (kolorowe obiektywy kontaktowe, niektóre toryczne obiektywy kontaktowe, okulary blokujące ir IR, niektóre okulary przeciwsłoneczne, okulary przeciwsłoneczne lub podobne)
- Bardziej wymawiane nagie i niektóre rozszerzenia ukośników
- Zarost lub grube ramki okularów, jeśli blokują one wzrok urządzenia
- Niektóre fizjologia, warunki wzrokowe lub operacje oczu, takie jak wąskie oczy, długie ukośniki, amblyopia, nystagmus, niektóre przypadki LASIK lub inne operacje skoków oczu

Jeśli próba nie powiedzie się, spróbuj:

- Czyszczenie aplikacji do czyszczenia urządzenia
- Czyszczenie okularów
- Wypychanie wizjora urządzenia tak blisko oczu, jak to możliwe
- Przenoszenie obiektów w osłodę poza drogę (na przykład zarostu)
- Włączanie światła w pomieszczeniu lub wyprowadzanie bezpośredniego światła

Jeśli wszystkie wytyczne i ustawienia nadal nie są stosowane, można wyłączyć monit monitu w ustawieniach. Daj nam również znać, składając opinię w [Centrum opinii](hololens-feedback.md).

Zobacz również powiązane informacje dotyczące [rozwiązywania problemów z kolorem obrazu lub jasność.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Ustawienie adresu IPD nie ma zastosowania w przypadku urządzenia HoloLens 2, ponieważ pozycje oka są obliczane przez system. 

### <a name="calibration-data-and-security"></a>Dane i zabezpieczenia na przekłoszcie

Informacje o lokalizacji są przechowywane lokalnie na urządzeniu i nie są skojarzone z żadnymi informacjami o koncie. Nie ma danych o tym, kto bez przerwy użył urządzenia. Oznacza to, że nowi użytkownicy otrzymają monit o skalibrowanie wizualizacji podczas korzystania z urządzenia po raz pierwszy, a użytkownicy, którzy zrezygnują z wcześniejszej pracy lub jeśli nie udało się jej odchonić.

Urządzenie może lokalnie przechowywać maksymalnie 50 profilów profilów profilów. Po osiągnięciu tej liczby urządzenie automatycznie usunie najstarszy nieużywany profil.

Informacje o prywatności można zawsze usunąć z urządzenia w **ustawieniach**  >  **Monitor**  >  **prywatności.**  

### <a name="disable-calibration"></a>Wyłączanie ustawienia

Monit o monit monitu o monit można również wyłączyć, wykonać następujące czynności:

1. Wybierz **pozycję Ustawienia**(  >  **Ustawienia) System (Ustawienia) .**  >  
1. Wyłącz tę **w przypadku, gdy nowa osoba korzysta z tego urządzenia HoloLens, automatycznie pytaj o uruchomienie wzroku**.

> [!IMPORTANT]
> To ustawienie może niekorzystnie wpłynąć na jakość i komfort renderowania hologramów.  Po włączeniu tego ustawienia funkcje zależne od śledzenia wzroku (np. przewijania tekstu) nie będą już działać w aplikacjach immersywnych.

### <a name="hololens-2-eye-tracking-technology"></a>Technologia śledzenia wzroku HoloLens 2

Urządzenie używa technologii śledzenia wzroku, aby poprawić jakość wyświetlania i upewnić się, że wszystkie hologramy są prawidłowo i wygodnie wyświetlane w 3D. Ponieważ używa ono oczu jako charakterystycznych elementów krajobrazu, urządzenie może dostosowywać się do każdego użytkownika i dostrajać swoje wizualizacje, gdy zestaw nagłowny zmienia się nieco podczas użytkowania.  Wszystkie korekty są dostrajane na bieżąco bez konieczności ręcznego dostrajania.
> [!NOTE]
> Ustawienie adresu IPD nie ma zastosowania w przypadku urządzenia Hololens 2, ponieważ pozycje oka są obliczane przez system.

Aplikacje dla urządzenia HoloLens śledzą, gdzie patrzysz w czasie rzeczywistym, za pomocą funkcji śledzenia wzroku. Jest to główna funkcja, z których deweloperzy mogą korzystać w celu umożliwienia zupełnie nowego poziomu kontekstu, zrozumienia przez człowieka i interakcji w ramach doświadczenia holograficznego. Deweloperzy nie muszą nic robić, aby korzystać z tej funkcji.

## <a name="calibrating-your-hololens-1st-gen"></a>Skalibrowanie urządzenia HoloLens (1. generacja)

Urządzenie HoloLens (1. generacja) dostosowuje wyświetlanie hologramów zgodnie z odległością między [kolumnami](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD). Jeśli adres IPD nie jest dokładny, hologramy mogą wydawać się niestabilne lub z nieprawidłową odległością. Jakość wizualizacji można poprawić, skalibrując urządzenie do odległości międzyobsychowej (IPD).

Po skonfigurowaniu urządzenia HoloLens (1. generacji) zostanie wyświetlony monit o skalibrowanie wizualizacji po wprowadzeniu się Cortany. Zaleca się ukończenie kroku pełnego w tej fazie konfiguracji. Można go jednak pominąć, czekając na monit Cortany, a następnie mówiąc "Pomiń".

Podczas procesu chłoniaka urządzenie HoloLens prosi o wyrównanie palca do serii sześciu obiektów docelowych na oko. Urządzenie HoloLens używa tego procesu, aby prawidłowo ustawić adres IPD dla oczu.

![Ekran wyrównywania linii papilarnych usługi IPD w drugim kroku](./images/ipd-finger-alignment-300px.jpg)

### <a name="manually-start-the-calibration-process"></a>Ręczne uruchamianie procesu procesów

Jeśli musisz zaktualizować ustawienia lub jeśli nowy użytkownik musi je dostosować, w dowolnym momencie możesz ręcznie uruchomić aplikację Nawę. Domyślnie jest instalowana aplikacja Wymusze. Dostęp do niego można uzyskać za pomocą menu **Start** lub aplikacji Ustawienia.

Aby użyć menu **Start** do uruchomienia aplikacji Wynisz, wykonaj następujące kroki:

1. Użyj [gestu Blooma,](hololens1-basic-usage.md) aby **otworzyć** menu Start.
1. Aby wyświetlić wszystkie aplikacje, wybierz pozycję **+** .
1. Wybierz **pozycję Wymusz**.

![Uzyskiwanie dostępu do aplikacji z powłoką](./images/calibration-shell.png)

![Aplikacja narętowa wyświetlana jako Live Cube po jej zakończeniu](./images/calibration-livecube-200px.png)

Aby uruchomić aplikację Ustawienia, wykonaj następujące kroki:

1. Użyj [gestu Blooma,](hololens1-basic-usage.md) aby **otworzyć** menu Start.
1. Jeśli **ustawienia** nie są przypięte do **menu Start,** wybierz pozycję **+** , aby wyświetlić wszystkie aplikacje.
1. Wybierz pozycję **Ustawienia**.
1. Wybierz **pozycję Narzędzia**  >  **systemowe**  >  **Otwórz i** otwórz .

![Uruchamianie aplikacji narętowej z aplikacji ustawienia](./images/calibration-settings-500px.jpg)

## <a name="immersive-headsets"></a>Immersywne zestawy nagłow

Niektóre immersywne zestawy nagłowne zapewniają możliwość dostosowania ustawienia adresu IPD. Aby zmienić adres IPD zestawu nagłownego, otwórz aplikację Ustawienia i wybierz pozycję **Ekran** zestawu nagłownego rzeczywistości mieszanej,  >  a następnie przesuń kontrolkę suwaka. Zmiany zostaną wprowadzone w czasie rzeczywistym w zestawie nagłownym. Jeśli znasz swój adres IPD, być może podczas wizyty u optometrysta, możesz również wprowadzić go bezpośrednio.

To ustawienie można również dostosować na komputerze, wybierając pozycję Ustawienia **Ekran zestawu**  >  **nagłownego rzeczywistości**  >  **mieszanej**.

Jeśli zestaw nagłowny nie obsługuje dostosowywania adresów IPD, to ustawienie zostanie wyłączone.
