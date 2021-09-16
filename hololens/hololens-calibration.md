---
title: Poprawianie jakości i komfortu wizualizacji
description: Dowiedz się, jak skalibrować odległość międzypobiegową (IPD) w celu poprawy jakości wizualizacji na HoloLens urządzeniach.
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
ms.openlocfilehash: cdeef216cbf6d1fb165737ae194071c60b31146a
ms.sourcegitcommit: 20ea1ed37772655504ccb11a7e185ed19d85f336
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2021
ms.locfileid: "127833560"
---
# <a name="improve-visual-quality-and-comfort"></a>Poprawianie jakości i komfortu wizualizacji

HoloLens 2 i HoloLens (1. generacja) działają lepiej, gdy są skalibrowane do unikatowych oczu.

Oba urządzenia muszą być skalibrowane w celu najlepszego przeglądania hologramów, ale korzystają z różnych technologii i technik.  Przejdź do [HoloLens 2 lub](#calibrating-your-hololens-2) [HoloLens (1. generacji).](#calibrating-your-hololens-1st-gen)

## <a name="calibrating-your-hololens-2"></a>Skalibrowanie HoloLens 2

HoloLens 2 używa technologii śledzenia wzroku, aby ulepszyć środowisko użytkownika i interakcję ze środowiskiem wirtualnym. Skalibrowanie HoloLens 2 zapewnia możliwość dokładnego śledzenia oczu (i oczu innych osób, które będą korzystać z urządzenia). Pomaga również zapewnić komfort użytkownika, wyrównanie hologramów i śledzenie rąk. Po nachłoeniu hologramy będą wyświetlane prawidłowo nawet wtedy, gdy przyczomienie przesuwa się w kierunku głowy.

HoloLens 2 monituje użytkownika o skalibrowanie urządzenia w następujących okolicznościach:

- Użytkownik korzysta z urządzenia po raz pierwszy
- Użytkownik wcześniej zrezygnował z procesu procesowego
- Proces odszukania nie powieść się, gdy użytkownik użył urządzenia
- Użytkownik usunął swoje profile profilów profilów profilów profilów
- Urządzenie jest wyłączane i ponownie stosowane, a każda z powyższych okoliczności ma zastosowanie 

![Monit o dostosowanie do oczu.](./images/07-et-adjust-for-your-eyes.png)

W trakcie tego procesu przyjrzymy się zestawowi celów (gemom). Jest w porządku, jeśli migasz podczas ciąży, ale spróbujesz skupić się na gemach, a nie na innych obiektach w pomieszczeniu.  Skupienie się na tych HoloLens pozwala HoloLens o pozycji wzrokowej w celu renderowania świata holograficznego.

![Monit o monitowanie użytkownika o utrzymanie głowy w miejscu i obserwowanie kropek przy oku.](./images/07-et-hold-head-still.png)

![Monit o monit za pomocą przykładu gem.](./images/08-et-gems.png)

![Dostosowywanie monitu o monitowanie.](./images/09-et-adjusting.png)

Jeśli uda się to zrobić, zostanie wyświetlony ekran sukcesu.  Jeśli nie, przeczytaj więcej na [temat diagnozowania błędów awarii.](hololens2-display.md#troubleshooting)

![Monit o powodzenie monitu.](./images/10-et-success.png)

### <a name="calibration-when-sharing-a-device-or-session"></a>Podczas udostępniania urządzenia lub sesji

Wielu użytkowników może współużytkować urządzenie HoloLens 2, bez potrzeby, aby każda osoba przechodziła przez konfigurację urządzenia. Gdy nowy użytkownik po raz pierwszy przyłoży urządzenie do głowy, HoloLens 2 automatycznie monituje użytkownika o skalibrowanie wizualizacji. Gdy użytkownik, który wcześniej skalibrował wizualizacje, umieszcza urządzenie na głowy, ekran jest bezproblemowo dostosowywany pod kątem jakości i wygodnego wyświetlania.  

### <a name="manually-starting-the-calibration-process"></a>Ręczne uruchamianie procesu procesowego

1. Użyj gestu uruchamiania, aby [**otworzyć menu Start**](hololens2-basic-usage.md#start-gesture).
1. Jeśli aplikacja Ustawienia nie jest przypięta do opcji **Uruchom,** wybierz **pozycję Wszystkie aplikacje.**
1. Wybierz **Ustawienia** pozycję , a następnie wybierz **pozycję System**  >  **Wybieg** z  >    >  **okiem.**

   ![Aplikacja Ustawienia z wyświetloną opcją "Run eye odszukaj".](./images/C-Settings.Calibration.png)

### <a name="auto-eye-position-support"></a>Obsługa automatycznego położenia oka

W HoloLens 2 położenia oczu umożliwiają dokładne pozycjonowanie hologramów, wygodne środowisko wyświetlania i lepszą jakość wyświetlania. Pozycje oka są obliczane wewnętrznie w ramach obliczeń śledzenia wzroku. Jednak wymaga to, aby każdy użytkownik przechodził przez śledzenie wzroku, nawet wtedy, gdy środowisko może nie wymagać danych wejściowych spojrzenia oczu.

**Funkcja Automatycznego położenia oka (AEP)** umożliwia tym scenariuszom bez interakcji obliczanie pozycji oka dla użytkownika. Automatyczne położenie oka automatycznie rozpoczyna pracę w tle od momentu, gdy użytkownik umieścił urządzenie. Jeśli użytkownik nie ma wcześniejszego śledzenia wzroku, funkcja automatycznego położenia oka zacznie dostarczać informacje o pozycjach oka użytkownika do systemu wyświetlania po czasie przetwarzania 20–30 sekund. Dane użytkownika nie są utrwalane na urządzeniu i ten proces jest powtarzany, jeśli użytkownik wystartuje i ponownie uruchomi urządzenie lub jeśli urządzenie zostanie ponownie uruchomiony lub wznowiony po uśpieniu.

Istnieje kilka zmian zachowania systemu za pomocą funkcji automatycznego rozsyłania okiem, gdy użytkownik nieskalowany umieszcza urządzenie. W tym kontekście użytkownik nieskalibrowany odwołuje się do osoby, która wcześniej nie przechodziła przez proces śledzenia oczu na urządzeniu.

| Aktywna aplikacja | Wcześniejsze zachowanie | Zachowanie z Windows Holographic, aktualizacja w wersji 20H2 |
|:-------------------|:-----------------|:-----------------------------------|
| Aplikacja bez obsługi spojrzenia lub powłoka Holographic Shell |Zostanie wyświetlone okno dialogowe monitu o śledzenie oczu. | Monit nie jest wyświetlany. |
| Aplikacja z obsługą spojrzenia | Zostanie wyświetlone okno dialogowe monitu o śledzenie oczu. | Monit o śledzenie oczu jest wyświetlany tylko wtedy, gdy aplikacja uzyskuje dostęp do strumienia oczu. |

Jeśli użytkownik przechodzi z aplikacji bez włączonego spojrzenia do aplikacji, która uzyskuje dostęp do danych spojrzenia, zostanie wyświetlony monit o monit. 

Wszystkie inne zachowania systemu będą podobne do zachowania bieżącego użytkownika, który nie ma aktywnego śledzenia wzroku. Na przykład gest One-handed Start nie zostanie włączony. Nie będzie żadnych zmian w zakresie out-of-box-experience na potrzeby konfiguracji początkowej.

W przypadku doświadczeń, które wymagają danych o oku lub precyzyjnego pozycjonowania hologramu, zalecamy użytkownikom nieskalicznym uruchamianie śledzenia oczu. Jest on dostępny z monitu o śledzenie wzroku lub przez uruchomienie aplikacji Ustawienia z menu Start, a następnie wybranie pozycji **System > Namysłowy > Eye W > ystartuj** z okiem.

#### <a name="deferred-calibration-prompt"></a>Monit o odroczone monity o odroczone monity

W przypadku ustawienia pozycji automatycznego oka okno dialogowe monitu o śledzenie wzroku jest odroczone do momentu, gdy aplikacja zażąda danych aplikacji Eye Gaze. Dzięki temu użytkownik nie będzie monitować, gdy aktywna aplikacja nie wymaga spojrzenia. Jeśli aplikacja wymaga danych spojrzenia, a bieżący użytkownik nie jest skalibrowany, zostanie wyświetlony monit o monit o monit. To zachowanie może służyć do wyświetlania monitu o śledzenie wzroku w odpowiednim czasie dla tego doświadczenia. Ta metoda jest zalecana z następujących powodów:

1.  Okno dialogowe monitu o śledzenie oczu udostępnia użytkownikowi szczegółowe informacje na temat tego, dlaczego śledzenie oczu jest potrzebne.
2.  Przedstawia użytkownikowi sposób odrzucania skalibrowania oczu.

Jeśli użytkownik zdecyduje się na uruchomienie aplikacji Eye Tracking Tracking, fokus powinien zostać zwrócony do oryginalnej aplikacji po zakończeniu śledzenia. 

### <a name="calibration-data-and-security"></a>Dane i zabezpieczenia na przekłoszcie

Informacje o lokalizacji są przechowywane lokalnie na urządzeniu i nie są skojarzone z żadnymi informacjami o koncie. Nie ma danych o tym, kto bez przerwy użył urządzenia. Oznacza to, że nowi użytkownicy otrzymają monit o skalibrowanie wizualizacji podczas korzystania z urządzenia po raz pierwszy, a użytkownicy, którzy zrezygnują z wcześniejszej pracy lub jeśli nie udało się jej odchonić.

Urządzenie może lokalnie przechowywać maksymalnie 50 profilów profilów profilów profilów profilów. Po osiągnięciu tej liczby urządzenie automatycznie usunie najstarszy nieużywany profil.

Informacje o prywatności można zawsze usunąć z urządzenia w Ustawienia  >  **Privacy**  >  **Eye Tracker.**  

### <a name="disable-calibration"></a>Wyłączanie ustawienia

#### <a name="eye-calibration-behavior-on-hololens-2-builds-20h2-and-newer"></a>Zachowanie wzroku na HoloLens 2 kompilacjach 20H2 i nowsze

Od wersji 20H2 systemu Windows Holographic jest już dostępna obsługa funkcji Auto [Eye Position.](hololens-release-notes.md#auto-eye-position-support) Monit o monit monitu jest wyświetlany automatycznie tylko wtedy, gdy używasz aplikacji z włączoną obsługą funkcji Eye Tracking.

#### <a name="disabling-eye-calibration-on-hololens-2-older-builds"></a>Wyłączanie funkcji eye w HoloLens 2 starszych kompilacji

Można przerzucić przełącznik Ustawienia na zestawie nagłownym, aby wyłączyć odcięcie, ale jego stan może nie być łatwy do określenia. Została ona usunięta i zastąpiona przez funkcję [Auto Eye Position Support](hololens-release-notes.md#auto-eye-position-support), która odmówi ustawienia nachylić podczas zapewniania korekty kolorów i ustawienia hologramów.

#### <a name="disabling-eye-calibration-on-hololens-1st-gen"></a>Wyłączanie oku na HoloLens (1. generacja)

W [HoloLens (1. generacji)](#calibrating-your-hololens-1st-gen)można wyłączyć monit o wzrok, wykonać następujące czynności:

1. Wybierz **Ustawienia**  >    >  **systemowego**.
1. Wyłącz , **gdy nowa osoba używa tego HoloLens, automatycznie pytaj** o uruchomienie wzroku .

   > [!IMPORTANT]
   > To ustawienie może niekorzystnie wpłynąć na jakość i komfort renderowania hologramów.  Po włączeniu tego ustawienia funkcje zależne od śledzenia wzroku (np. przewijania tekstu) nie będą już działać w aplikacjach immersywnych.

### <a name="hololens-2-eye-tracking-technology"></a>HoloLens 2 technologii śledzenia wzroku

Urządzenie używa technologii śledzenia wzroku, aby poprawić jakość wyświetlania i upewnić się, że wszystkie hologramy są prawidłowo i wygodnie wyświetlane w 3D. Ponieważ używa ono oczu jako charakterystycznych elementów krajobrazu, urządzenie może dostosowywać się do każdego użytkownika i dostrajać swoje wizualizacje, gdy zestaw nagłowny zmienia się nieco podczas użytkowania.  Wszystkie korekty są dostrajane na bieżąco bez konieczności ręcznego dostrajania.
> [!NOTE]
> Ustawienie adresu IPD nie ma zastosowania w przypadku urządzenia Hololens 2, ponieważ pozycje oka są obliczane przez system.

HoloLens śledząc miejsce w czasie rzeczywistym, aplikacje śledzące wzrok. Jest to główna funkcja, z których deweloperzy mogą korzystać, aby umożliwić zupełnie nowy poziom kontekstu, zrozumienia przez człowieka i interakcji w ramach doświadczenia holograficznego. Deweloperzy nie muszą nic robić, aby korzystać z tej funkcji.

## <a name="calibrating-your-hololens-1st-gen"></a>Skalibrowanie HoloLens (1. generacja)

HoloLens (1. generacja) dostosowuje wyświetlanie hologramów zgodnie z [odległością międzypołędową](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD). Jeśli adres IPD nie jest dokładny, hologramy mogą wydawać się niestabilne lub z nieprawidłową odległością. Jakość wizualizacji można poprawić, skalibrując urządzenie do odległości międzyobsychowej (IPD).

Po skonfigurowaniu urządzenia HoloLens (1. generacji) zostanie wyświetlony monit o skalibrowanie wizualizacji po Cortana się. Zaleca się ukończenie kroku pełnego w tej fazie konfiguracji. Można go jednak pominąć, czekając Cortana monitu, a następnie mówiąc "Pomiń".

Podczas procesu chłoniaka HoloLens, aby wyrównać palec do serii sześciu celów na okiem. HoloLens używa tego procesu, aby prawidłowo ustawić adres IPD dla twoich oczu.

![Ekran wyrównywania linii papilarnych IPD w drugim kroku.](./images/ipd-finger-alignment-300px.jpg)

### <a name="manually-start-the-calibration-process"></a>Ręczne uruchamianie procesu procesów

Jeśli musisz zaktualizować ten certyfikat lub jeśli nowy użytkownik musi go dostosować, możesz ręcznie uruchomić aplikację W dowolnym momencie. Domyślnie jest instalowana aplikacja Wymusze. Dostęp do niego można uzyskać za pomocą menu **Start** lub Ustawienia aplikacji.

Aby użyć menu **Start** do uruchomienia aplikacji Wynisz, wykonaj następujące kroki:

1. Użyj [gestu Blooma,](hololens1-basic-usage.md) aby otworzyć menu **Start.**
1. Aby wyświetlić wszystkie aplikacje, wybierz pozycję **+** .
1. Wybierz **pozycję Wymusz**.

   ![Uzyskiwanie dostępu do aplikacji z powłoką.](./images/calibration-shell.png)

   ![Aplikacja wytchnieniowa wyświetlana jako Live Cube po jej zakończeniu.](./images/calibration-livecube-200px.png)

Aby użyć aplikacji Ustawienia do uruchomienia aplikacji w 2018 r., wykonaj następujące kroki:

1. Użyj [gestu Blooma,](hololens1-basic-usage.md) aby otworzyć menu **Start.**
1. Jeśli **Ustawienia** nie jest przypięty do opcji **Start,** wybierz pozycję , **+** aby wyświetlić wszystkie aplikacje.
1. Wybierz pozycję **Ustawienia**.
1. Wybierz **pozycję Narzędzia**  >  **systemowe**  >  **Otwórz i** otwórz .

   ![Uruchamianie aplikacji z ustawieniami.](./images/calibration-settings-500px.jpg)

## <a name="immersive-headsets"></a>Immersywne zestawy nagłow

Niektóre immersywne zestawy nagłowne zapewniają możliwość dostosowania ustawienia adresu IPD. Aby zmienić adres IPD zestawu nagłownego, otwórz aplikację Ustawienia i wybierz pozycję Ekran zestawu nagłownego rzeczywistości mieszanej, a następnie przesuń  >  kontrolkę suwaka. Zmiany zostaną wprowadzone w czasie rzeczywistym w zestawie nagłownym. Jeśli znasz swój adres IPD, być może podczas wizyty u optometrysta, możesz również wprowadzić go bezpośrednio.

To ustawienie można również dostosować na komputerze, wybierając pozycję **Ustawienia** zestawu nagłownego rzeczywistości  >    >  **mieszanej.**

Jeśli zestaw nagłowny nie obsługuje dostosowywania adresów IPD, to ustawienie zostanie wyłączone.
