---
title: Poprawianie jakości i komfortu wizualizacji
description: Dowiedz się, jak skalibrować odległość międzypołudniową (IPD), aby poprawić jakość wizualizacji na HoloLens urządzeniach.
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
keywords: nagłowne, komfort, wizualizacje, jakość, ipd, HoloLens, Windows Mixed Reality, zestawy VR
ms.openlocfilehash: b3d917c71ac7441aeaf8dcbc25748ee07b9fbfa3
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427068"
---
# <a name="improve-visual-quality-and-comfort"></a>Poprawianie jakości i komfortu wizualizacji

HoloLens 2 i HoloLens (1. generacja) działają lepiej, gdy są skalibrowane do unikatowych oczu.

Oba urządzenia muszą być skalibrowane w celu najlepszego przeglądania hologramów, jednak używają różnych technologii i technik na potrzeby odsłowu.  Przejdź do [HoloLens 2](#calibrating-your-hololens-2) lub [HoloLens (1. generacji).](#calibrating-your-hololens-1st-gen)

## <a name="calibrating-your-hololens-2"></a>Skalibrowanie HoloLens 2

HoloLens 2 używa technologii śledzenia wzroku, aby ulepszyć środowisko użytkownika i interakcję ze środowiskiem wirtualnym. Skalibrowanie HoloLens 2 zapewnia możliwość dokładnego śledzenia oczu (i oczu innych osób, które będą korzystać z urządzenia). Pomaga również w zapewnianiu komfortu użytkownika, wyrównaniu hologramu i śledzeniu rąk. Po połyceniu hologramy będą wyświetlane prawidłowo nawet wtedy, gdy wizjer przesuwa się w łb.

HoloLens 2 monituje użytkownika o skalibrowanie urządzenia w następujących okolicznościach:

- Użytkownik korzysta z urządzenia po raz pierwszy
- Użytkownik wcześniej zrezygnował z procesu odc.
- Proces odtąd zakończył się powodzeniem, gdy użytkownik użył urządzenia
- Użytkownik usunął profile profilów profilów profilów
- Urządzenie jest wyłączane i ponownie wsadowe, a każda z powyższych okoliczności ma zastosowanie 


![Monit o dostosowanie wzroku.](./images/07-et-adjust-for-your-eyes.png)

W trakcie tego procesu przyjrzymy się zestawowi celów (gemom). Jest w porządku, jeśli migasz podczas pominięcia, ale spróbujesz skupić się na gemach, a nie na innych obiektach w pomieszczeniu.  Skupienie się na gemach HoloLens dowiedzieć się więcej o pozycji oka w celu renderowania świata holograficznego.

![Monit o monit o monitowanie użytkownika, aby nie chwycił głowy i podążał kropkami przy oku.](./images/07-et-hold-head-still.png)

![Monit o monit o monit z przykładem gem.](./images/08-et-gems.png)

![Dostosowywanie monitu o monitowanie.](./images/09-et-adjusting.png)

Jeśli uda się odszukać, zostanie wyświetlony ekran powodzenia.  Jeśli nie, przeczytaj więcej na [temat diagnozowania błędów awarii.](hololens2-display.md#troubleshooting)

![Powodzenie monitu o monitowanie o monitowanie.](./images/10-et-success.png)

### <a name="calibration-when-sharing-a-device-or-session"></a>Nieudzielenie pamięci podczas udostępniania urządzenia lub sesji

Wielu użytkowników może współużytkować HoloLens 2 urządzenia bez konieczności poszczególnych osób do poszczególnych przejść przez konfigurację urządzenia. Gdy nowy użytkownik po raz pierwszy umieszcza urządzenie na głowy, HoloLens 2 automatycznie monituje użytkownika o skalibrowanie wizualizacji. Gdy użytkownik, który wcześniej skalibrował wizualizacje, umieszcza urządzenie na głowy, ekran jest bezproblemowo dostosowywany do jakości i wygodnego wyświetlania.  

### <a name="manually-starting-the-calibration-process"></a>Ręczne rozpoczynanie procesu inkasowania

1. Użyj gestu uruchamiania, aby [**otworzyć menu Start**](hololens2-basic-usage.md#start-gesture).
1. Jeśli aplikacja Ustawienia nie została przypięta do opcji **Uruchom,** wybierz **pozycję Wszystkie aplikacje.**
1. Wybierz **Ustawienia**, a następnie wybierz **pozycję System**  >  **Wybłysek**  >  **wybiegowy.**  >  

   ![Aplikacja Ustawienia z wyświetloną opcją "Uruchom okiem".](./images/C-Settings.Calibration.png)

### <a name="auto-eye-position-support"></a>Obsługa automatycznego położenia oka

W HoloLens 2 położenia oczu umożliwiają dokładne pozycjonowanie hologramów, wygodne środowisko wyświetlania i lepszą jakość wyświetlania. Pozycje oczu są obliczane wewnętrznie w ramach obliczeń śledzenia wzroku. Jednak wymaga to, aby każdy użytkownik przechodził przez śledzenie wzroku, nawet wtedy, gdy środowisko może nie wymagać danych wejściowych spojrzenia oczu.

**Funkcja Auto Eye Position (AEP)** umożliwia tym scenariuszom bez interakcji obliczanie pozycji oczu dla użytkownika. Funkcja Auto Eye Position automatycznie zacznie działać w tle od momentu, w którym użytkownik umieści urządzenie. Jeśli użytkownik nie ma wcześniejszego śledzenia wzroku, funkcja Auto Eye Position zacznie dostarczać użytkownikowi pozycje oczu do systemu wyświetlania po czasie przetwarzania 20–30 sekund. Dane użytkownika nie są utrwalane na urządzeniu i ten proces jest powtarzany, jeśli użytkownik wyłączy i ponownie uruchomi urządzenie lub jeśli urządzenie zostanie ponownie uruchomiony lub wznowiony po uśpieniu.

Istnieje kilka zmian zachowania systemu za pomocą funkcji automatycznego położenia oka, gdy na urządzeniu jest umieszczany nieskalibrowany użytkownik. W tym kontekście użytkownik nieskalibrowany odnosi się do kogoś, kto wcześniej nie przeszedł przez proces śledzenia wzroku na urządzeniu.

| Aktywna aplikacja | Wcześniejsze zachowanie | Zachowanie z Windows Holographic, aktualizacja w wersji 20H2 |
|:-------------------|:-----------------|:-----------------------------------|
| Aplikacja bez obsługi spojrzenia lub powłoka Holographic Shell |Zostanie wyświetlone okno dialogowe monitu o śledzenie wzroku. | Monit nie jest wyświetlany. |
| Aplikacja z obsługą spojrzenia | Zostanie wyświetlone okno dialogowe monitu o śledzenie wzroku. | Monit o śledzenie wzroku jest wyświetlany tylko wtedy, gdy aplikacja uzyskuje dostęp do strumienia oczu. |

Jeśli użytkownik przechodzi z aplikacji bez włączonego spojrzenia do aplikacji, która uzyskuje dostęp do danych spojrzenia, zostanie wyświetlony monit o podanie monitu. 

Wszystkie inne zachowania systemu będą podobne do zachowania bieżącego użytkownika, który nie ma aktywnej kontroli wzroku. Na przykład gest "One-handed Start" nie będzie włączony. Nie będzie żadnych zmian w out-of-box-experience na potrzeby konfiguracji początkowej.

W przypadku doświadczeń wymagających danych o spojrzeniu lub precyzyjnego pozycjonowania hologramu zalecamy użytkownikom nieskalowania uruchamianie śledzenia oczu. Jest on dostępny z monitu o śledzenie wzroku lub przez uruchomienie aplikacji Ustawienia z menu Start, a następnie wybranie pozycji System > > Wyniszcz wzrokowy > IOT. 

#### <a name="deferred-calibration-prompt"></a>Monit o odroczone monitowanie o odroczenie

W przypadku ustawienia pozycji automatycznego oka okno dialogowe monitu o śledzenie oczu jest odroczone do momentu, gdy aplikacja zażąda danych funkcji Eye Gaze. Dzięki temu nie będzie wyświetlany monit do użytkownika, gdy aktywna aplikacja nie wymaga spojrzenia. Jeśli aplikacja wymaga danych spojrzenia, a bieżący użytkownik nie jest skalibrowany, zostanie wyświetlony monit o poumianie. To zachowanie może służyć do wyświetlania monitu o śledzenie wzroku w odpowiednim czasie dla tego doświadczenia. Ta metoda jest zalecana z następujących powodów

1.  Okno dialogowe monitu o śledzenie wzroku udostępnia użytkownikowi szczegółowe informacje o tym, dlaczego jest potrzebne śledzenie oczu.
2.  Przedstawia użytkownikowi sposób odrzucania skalibrowania oczu.

Jeśli użytkownik zdecyduje się na uruchomienie aplikacji Eye Tracking Tracking, fokus powinien zostać zwrócony do oryginalnej aplikacji po zakończeniu zabiegu. 

### <a name="calibration-data-and-security"></a>Dane pośrednie i zabezpieczenia

Informacje o opadach są przechowywane lokalnie na urządzeniu i nie są skojarzone z żadnymi informacjami o koncie. Nie ma żadnych rekordów osób, które użyły urządzenia bez żadnego wyjątku. Oznacza to, że nowi użytkownicy otrzymają monit o skalibrowanie wizualizacji podczas korzystania z urządzenia po raz pierwszy, a użytkownicy, którzy wybrali wcześniej orzeł o rezygnacji z indygnowania, lub jeśli próba nie powiodła się.

Urządzenie może lokalnie przechowywać maksymalnie 50 profilów profilów profilów. Po osiągnięciu tej liczby urządzenie automatycznie usunie najstarszy nieużywany profil.

Informacje o odwzorowaniach można zawsze usunąć z urządzenia w **programie Ustawienia**  >  **Privacy**  >  **Eye Tracker.**  

### <a name="disable-calibration"></a>Wyłącz iniekcja

Monit o monit o monit można również wyłączyć, wykonać następujące czynności:

1. Wybierz **Ustawienia**  >    >  **systemowego**.
1. Wyłącz , **gdy nowa osoba korzysta z tego HoloLens, automatycznie poproś o uruchomienie wzroku.**

   > [!IMPORTANT]
   > To ustawienie może niekorzystnie wpłynąć na jakość i komfort renderowania hologramów.  Po włączeniu tego ustawienia funkcje zależne od śledzenia wzroku (takie jak przewijanie tekstu) nie będą już działać w aplikacjach immersywnych.

> [!NOTE]
> Przełącznik Ustawienia został usunięty od wersji Windows Holographic w wersji 20H2 z odjęciem obsługi automatycznego [położenia oka.](hololens-release-notes.md#auto-eye-position-support) Monit o monit o monit monitu będzie wyświetlany automatycznie tylko wtedy, gdy użytkownik nieskalowany korzysta z aplikacji z obsługą funkcji Eye Tracking.

### <a name="hololens-2-eye-tracking-technology"></a>HoloLens 2 technologia śledzenia wzroku

Urządzenie używa technologii śledzenia wzroku, aby poprawić jakość wyświetlania i zapewnić, że wszystkie hologramy są prawidłowo i wygodnie wyświetlane w 3D. Ponieważ używa ono oczu jako charakterystycznych elementów krajobrazu, urządzenie może dostosowywać się do każdego użytkownika i dostrajać swoje wizualizacje, gdy zestaw nagłowny zmienia się nieco w całym użyciu.  Wszystkie korekty są na bieżąco bez konieczności ręcznego dostrajania.
> [!NOTE]
> Ustawienie adresu IPD nie ma zastosowania w przypadku urządzenia Hololens 2, ponieważ pozycje oka są obliczane przez system.

HoloLens śledząc miejsce w czasie rzeczywistym, można śledzić za pomocą funkcji śledzenia wzroku. Jest to główna funkcja, z poziomu których deweloperzy mogą korzystać, aby umożliwić zupełnie nowy poziom kontekstu, zrozumienia przez człowieka i interakcji w ramach doświadczenia holograficznego. Deweloperzy nie muszą nic robić, aby korzystać z tej funkcji.

## <a name="calibrating-your-hololens-1st-gen"></a>Skalibrowanie HoloLens (1. generacja)

HoloLens (1. generacja) dostosowuje wyświetlanie hologramów zgodnie z odległością [międzypołudową](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD). Jeśli adres IPD nie jest dokładny, hologramy mogą wydawać się niestabilne lub z nieprawidłową odległością. Jakość wizualizacji można poprawić, skalibrując urządzenie do odległości międzyobsuwowej (IPD).

Po skonfigurowaniu urządzenia HoloLens (1. generacji) wyświetlany jest monit o skalibrowanie wizualizacji po Cortana się. Zaleca się ukończenie kroku inkasywu podczas tej fazy konfiguracji. Można go jednak pominąć, czekając Cortana monitu, a następnie mówiąc "Pomiń".

Podczas procesu chłoniaka HoloLens o wyrównanie palca serią sześciu obiektów docelowych na oko. HoloLens ten proces pozwala prawidłowo ustawić adres IPD dla twoich oczu.

![Ekran wyrównywania linii papilarnych IPD w drugim kroku.](./images/ipd-finger-alignment-300px.jpg)

### <a name="manually-start-the-calibration-process"></a>Ręczne uruchamianie procesu procesów

Jeśli musisz zaktualizować ten certyfikat lub jeśli nowy użytkownik musi go dostosować, możesz ręcznie uruchomić aplikację W dowolnym momencie. Domyślnie jest instalowana aplikacja Wymusze. Dostęp do niego można uzyskać za pomocą menu **Start** lub Ustawienia aplikacji.

Aby użyć menu **Start** do uruchomienia aplikacji Wynisz, wykonaj następujące kroki:

1. Użyj [gestu Blooma,](hololens1-basic-usage.md) aby otworzyć menu **Start.**
1. Aby wyświetlić wszystkie aplikacje, wybierz pozycję **+** .
1. Wybierz **pozycję Wymusz**.

   ![Uzyskiwanie dostępu do aplikacji z powłoką.](./images/calibration-shell.png)

   ![Aplikacja wytchnieniowa wyświetlana jako Live Cube po jej zakończeniu.](./images/calibration-livecube-200px.png)

Aby uruchomić aplikację Ustawienia, wykonaj następujące kroki:

1. Użyj [gestu Blooma,](hololens1-basic-usage.md) aby otworzyć menu **Start.**
1. Jeśli **Ustawienia** nie jest przypięty do opcji **Start,** wybierz pozycję , **+** aby wyświetlić wszystkie aplikacje.
1. Wybierz pozycję **Ustawienia**.
1. Wybierz **pozycję Narzędzia**  >  **systemowe**  >  **Otwórz i** otwórz .

   ![Uruchamianie aplikacji z ustawieniami.](./images/calibration-settings-500px.jpg)

## <a name="immersive-headsets"></a>Immersywne zestawy nagłow

Niektóre immersywne zestawy nagłowne zapewniają możliwość dostosowania ustawienia adresu IPD. Aby zmienić adres IPD zestawu nagłownego, otwórz aplikację Ustawienia i wybierz pozycję Ekran zestawu nagłownego rzeczywistości mieszanej, a następnie przesuń  >  kontrolkę suwaka. Zmiany zostaną wprowadzone w czasie rzeczywistym w zestawie nagłownym. Jeśli znasz swój adres IPD, być może podczas wizyty u optometrysta, możesz również wprowadzić go bezpośrednio.

To ustawienie można również dostosować na komputerze, wybierając pozycję Ustawienia  >  **zestawu nagłownego** rzeczywistości  >  **mieszanej.**

Jeśli zestaw nagłowny nie obsługuje dostosowywania adresów IPD, to ustawienie zostanie wyłączone.
