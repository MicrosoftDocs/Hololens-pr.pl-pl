---
title: HoloLens uwagi dotyczące środowiska
description: Uzyskiwanie najlepszego możliwego środowiska podczas HoloLens optymalizacji urządzenia pod kątem wzroku i środowiska.
author: dorreneb
ms.author: dobrown
manager: jarrettr
ms.date: 8/29/2019
ms.prod: hololens
ms.topic: article
audience: ITPro
ms.localizationpriority: high
keywords: holograficzna ramka, pole widzenia, fov, spaces, environment, how-to, HoloLens, mixed reality, zestawy nagłowne rzeczywistości mieszanej
ms.openlocfilehash: 6976527d759e768fa5da72f96395a8b7b390cefd
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427844"
---
# <a name="hololens-environment-considerations"></a>HoloLens uwagi dotyczące środowiska

HoloLens zmiękczy holograficzne ze światem "rzeczywistym", umieszczając hologramy w twoim środowisku. Okno aplikacji holograficznej "zawiesza się" na ścianie, na tablecie kręci się ballerina, a na ścianie nieświadomego znajomego znajduje się chłoń. W przypadku korzystania z gry lub aplikacji immersyjnej świat holograficzny zostanie rozrzuty, aby wypełnić twoje środowiska, ale nadal możesz zobaczyć i poruszać się po przestrzeni.

Hologramy, które umieścisz, zostaną tam, gdzie je umieścisz, nawet jeśli wyłączysz urządzenie.

## <a name="setting-up-an-environment"></a>Konfigurowanie środowiska

HoloLens urządzenia wiedzą, jak umieszczać stabilne i  dokładne hologramy, śledząc użytkowników w przestrzeni. Bez odpowiedniego śledzenia urządzenie nie rozumie środowiska ani użytkownika w nim. Hologramy się w niewłaściwych miejscach, nie pojawiać się w tym samym miejscu za każdym razem lub w ogóle nie pojawiać się. Dane używane do śledzenia użytkowników są reprezentowane na *mapie przestrzennej*.  

Na wydajność śledzenia ma duży wpływ środowisko, w którym znajduje się użytkownik, a dostrajanie środowiska w celu zapewnienia stabilnego i spójnego śledzenia jest sztuką, a nie nauką. Wiele różnych czynników środowiskowych jest ze sobą połączone w celu umożliwienia śledzenia, ale jako deweloper Mixed Reality istnieje kilka czynników, które można mieć na uwadze, aby dostroić miejsce w celu lepszego śledzenia.

### <a name="lighting"></a>Oświetlenie

Windows Mixed Reality używa wizualnego światła do śledzenia lokalizacji użytkownika. Gdy środowisko jest zbyt jasne, kamery mogą się nasycić i nic nie jest widoczne. Jeśli środowisko jest zbyt ciemne, kamery nie mogą uzyskać wystarczającej ilości informacji i nic nie jest widoczne. Oświetlenie powinno być równomierne i wystarczająco jasne, aby człowiek widział je bez wysiłku, ale nie tak jasne, że światło jest dostrzegące.  

Obszary, w których w ogólnym przyciemnionym obszarze znajdują się punkty jasnego światła, również są problematyczne, ponieważ aparat musi się dostosowywać podczas przechodzenia do i z jasnych obszarów. Może to spowodować "zagubione" urządzenie i sądzi, że zmiana światła odpowiada zmianie lokalizacji. Stabilne poziomy światła w obszarze prowadzą do lepszego śledzenia.  

Każde oświetlenie na zewnątrz może również powodować niestabilność trackera, ponieważ z czasem światło słoneczne może się znacznie zmieniać. Na przykład śledzenie w tej samej przestrzeni w okresie letnim i w czasie rzeczywistym może przynieść znacząco różne wyniki, ponieważ światło z drugiej ręki na zewnątrz może być wyższe o różne godziny w roku.  

Jeśli masz mikrometryk, dobrym miejscem do rozpoczęcia jest stały 500–1000 dolarów.  

#### <a name="types-of-lighting"></a>Typy oświetlenia

Różne typy światła w przestrzeni mogą również mieć wpływ na śledzenie. Żarówki pulsuje prądem zmiennym — jeśli częstotliwość prądu zmiennego wynosi 50 Hz, światło pulsuje przy częstotliwości 50 Hz. Dla człowieka to pulsowanie nie jest zauważalne. Jednak 30-cyfrowy aparat HoloLens widzi te zmiany — niektóre ramki będą dobrze oświetlone, niektóre będą źle oświetlone, a inne będą zbyt widoczne, gdy aparat spróbuje skompensować pulsy światła.  

W Stanach Zjednoczonych standard częstotliwości energii elektrycznej wynosi 60 Hz, więc pulsy żarówki są nasycane szybkość klatek HoloLens — pulsy 60 Hz są wyrównane do 30 ramek HOLOLENS' 30 FRAME. Jednak wiele krajów ma standard częstotliwości prądu zmiennego 50 Hz, co oznacza, że niektóre HoloLens będą podejmowane w trakcie pulsów, a inne nie. W szczególności wiadomo, że oświetlenie w Europie powoduje problemy.  

Istnieje kilka rzeczy, które można spróbować rozwiązać problemy z migotaniami. Temperatury, wiek żarówki i cykle rozgrzewki to typowe przyczyny migotowania i wymiany żarówek. Pomocne może być również zaostrzenie żarówek i upewnienie się, że bieżące rysy są stałe.  

### <a name="items-in-a-space"></a>Elementy w przestrzeni

HoloLens używa unikatowych elementów krajobrazu, znanych także jako *cechy*, aby zlokalizować się w przestrzeni.  

Urządzenie prawie nigdy nie może śledzić w obszarze z niską jakością funkcji, ponieważ nie wie, gdzie znajduje się w przestrzeni. Dodawanie funkcji do ścian przestrzeni jest zwykle dobrym sposobem na usprawnienie śledzenia. Pomocne są plakaty, symbole przyklejone do ściany, rośliny, unikatowe obiekty lub inne podobne elementy. Nieuchowe biurko to dobry przykład środowiska, które prowadzi do dobrego śledzenia — w jednym obszarze istnieje wiele różnych funkcji.  

Ponadto należy używać unikatowych funkcji w tym samym miejscu. Na przykład ten sam plakat powtórzony wielokrotnie na ścianie spowoduje dezorientację urządzenia, ponieważ HoloLens nie będzie wiedzieć, którego z powtarzających się plakatów się przygląda. Jednym z typowych sposobów dodawania unikatowych cech jest użycie linii taśm maskowania w celu utworzenia unikatowych, nie powtarzających się wzorców wzdłuż ścian i podłogi w przestrzeni.  

Dobrym pytaniem, które warto sobie zadać, jest: jeśli widzieliśsz tylko niewielką ilość sceny, czy możesz jednoznacznie zlokalizować siebie w przestrzeni? Jeśli nie, prawdopodobnie urządzenie również będzie mieć problemy ze śledzeniem.

#### <a name="wormholes"></a>Wormholes (wormholes)

Jeśli masz dwa obszary lub regiony, które wyglądają tak samo, monitor może uważać, że są takie same. Powoduje to, że urządzenie oszuka się, że jest w innym miejscu. Nazywamy je powtarzalnymi *obszarami.*  

Aby zapobiec zrębowi, staraj się zapobiegać identycznym obszarom w tym samym obszarze. Identyczne obszary mogą czasami obejmować stacje fabryczne, okna w budynku, stojaki serwerowe lub stacje robocze. Etykietowanie obszarów lub dodawanie unikatowych cech do każdego podobnego obszaru może pomóc w zminimalizowaniu problemów.

### <a name="movement-in-a-space"></a>Ruch w przestrzeni

Jeśli środowisko ciągle się przesuwa i zmienia, urządzenie nie ma stabilnych funkcji do zlokalizowania.  

Im więcej obiektów, które znajdują się w przestrzeni, w tym ludzi, tym łatwiej jest utracić śledzenie. Wiadomo, że przenoszenie przenośników taśmowych, elementów w różnych stanach konstrukcji i wielu ludzi w przestrzeni powoduje problemy ze śledzeniem.

Ten HoloLens szybko dostosować się do tych zmian, ale tylko wtedy, gdy ten obszar jest wyraźnie widoczny dla urządzenia. Obszary, które nie są często spotykane, mogą być opóźniana w związku z rzeczywistością, co może powodować błędy na mapie przestrzennej. Na przykład użytkownik skanuje znajomego, a następnie zawraca się, gdy znajomy opuszcza pomieszczenie. W danych mapowania przestrzennego będzie zachowywana reprezentacja "oduchomień" znajomego, dopóki użytkownik nie przeskanuje ponownie pustego miejsca.

### <a name="proximity-of-the-user-to-items-in-the-space"></a>Bliskość użytkownika z elementami w przestrzeni

Podobnie jak ludzie nie mogą dobrze skupić się na obiektach znajdujących się blisko oczu, HoloLens ma trudności, gdy obiekty znajdują się blisko swoich aparatów. Jeśli obiekt jest zbyt blisko widoczny z obu aparatów lub jeśli obiekt blokuje jeden aparat, urządzenie będzie mieć znacznie więcej problemów ze śledzeniem obiektu.  

Kamery nie widzą więcej niż 15 cm od obiektu.

### <a name="surfaces-in-a-space"></a>Powierzchnie w przestrzeni

Silnie odbicia powierzchni prawdopodobnie będą wyglądać inaczej w zależności od kąta, który ma wpływ na śledzenie. Pomyśl o zupełnie nowym aucie — gdy poruszasz się po nim, światło jest odzwierciedlane, a na powierzchni widać różne obiekty podczas poruszania się. W przypadku trackera różne obiekty odzwierciedlone na powierzchni reprezentują zmieniające się środowisko, a urządzenie traci śledzenie.

Łatwiej jest śledzić mniej świetlionych obiektów.

### <a name="wi-fi-fingerprint-considerations"></a>Wi-Fi odcisków palców

Tak długo, Wi-Fi jest włączona, dane mapy będą skorelowane z odciskiem palca Wi-Fi nawet wtedy, gdy nie są połączone z rzeczywistą siecią/routerem Wi-Fi. Bez Wi-Fi informacji przestrzeń i hologramy mogą być nieco wolniejsze do rozpoznania. Jeśli sygnały Wi-Fi znacznie się zmienią, urządzenie może pomyśleć, że znajduje się w innej przestrzeni.

Identyfikacja sieci (na przykład identyfikator SSID lub adres MAC) nie jest wysyłana do firmy Microsoft, a wszystkie odwołania Wi-Fi są przechowywane lokalnie na HoloLens.

## <a name="mapping-new-spaces"></a>Mapowanie nowych przestrzeni

Po wprowadzeniu nowej przestrzeni (lub załadowaniu istniejącej) zobaczysz siatkę rozkładaną się na przestrzeń. Oznacza to, że urządzenie mapuje twoje otoczenia. Podczas gdy HoloLens uczy się przestrzeni w czasie, istnieją porady i wskazówki dotyczące mapowania przestrzeni.

## <a name="environment-management"></a>Zarządzanie środowiskiem

Istnieją dwa ustawienia, które umożliwiają użytkownikom "czyszczenie" hologramów i HoloLens "zapomnienie" miejsca. Istnieją one **w Hologramy i środowiskach** w aplikacji Ustawienia, a  drugie ustawienie jest również wyświetlane w obszarze Prywatność w aplikacji Ustawienia.  

1. **Usuń pobliskie hologramy**. Po wybraniu tego ustawienia HoloLens wszystkie zakotwiczone hologramów i wszystkie przechowywane dane mapy dla "bieżącej przestrzeni", w której znajduje się urządzenie. Nowa sekcja mapy zostanie utworzona i zapisana w bazie danych dla tej lokalizacji, gdy hologramy zostaną ponownie umieszczone w tym samym miejscu.

1. **Usuń wszystkie hologramy**. Wybranie tego ustawienia spowoduje usunięcie HoloLens wszystkich danych mapy i zakotwiczonych hologramów z całych baz danych spacji. Nie zostaną ponownie odnalezione żadne hologramy i wszelkie hologramy muszą zostać nowo umieszczone w celu ponownego przechowywania sekcji map w bazie danych.

## <a name="hologram-quality"></a>Jakość hologramu

Hologramy można je umieścić w całym środowisku — wysokim, niskim i wokół — [](/windows/mixed-reality/holographic-frame) ale zobaczysz je za pośrednictwem ramki holograficznej, która znajduje się przed twoimi wzrokami. Aby uzyskać najlepszy widok, upewnij się, że urządzenie zostało dostosowane tak, aby widzieć całą ramkę. Nie chciej też eksplorować swojego środowiska.

Aby [hologramy](/windows/mixed-reality/hologram) wyglądały na jasne i stabilne, HoloLens muszą być skalibrowane tylko dla Ciebie. Po pierwszym skonfigurowaniu konta HoloLens zostaniesz pokierować tym procesem. Później, jeśli hologramy nie wyglądają dobrze lub widzisz wiele błędów, możesz wprowadzić korekty.

Jeśli masz problemy z mapowaniem przestrzeni, spróbuj usunąć pobliskie hologramy i ponownie zamapować miejsce.

### <a name="calibration"></a>Kalibracja

Jeśli hologramy wyglądają na potrząsanie lub potrząsanie albo jeśli masz problemy z umieszczaniem hologramów, pierwszą rzeczą, którą należy wypróbować, jest aplikacja [Doceń.](hololens-calibration.md) Ta aplikacja może również pomóc, jeśli podczas korzystania z aplikacji występują jakiekolwiek problemy HoloLens.

Aby uzyskać dostęp do aplikacji Dosyć, przejdź do **Ustawienia**  >  **System**  >  **Utilities**. Wybierz **pozycję Open i** postępuj zgodnie z instrukcjami.

Jeśli ktoś inny będzie używać Twojego HoloLens, powinien najpierw uruchomić aplikację w celu poprawnego skonfigurowania dla nich urządzenia.

## <a name="temperature-and-regulatory-information"></a>Informacje dotyczące temperatury i przepisów prawnych

[HoloLens prawne:](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information)obejmują informacje dotyczące zakresu temperatur, usuwania, interferencji radiowej i tv i nie tylko.

Zobacz szczegóły dotyczące "HoloLens" w artykule [Materiały i](https://www.microsoft.com/legal/compliance/materials-substances) > REACH Article 33 Disclosure on Environmental Compliance (PDF).

Poniżej podano kilka wskazówek, które należy wykonać podczas korzystania z urządzenia:

1. Przechowuj urządzenie w środowisku w zakresie temperatury (w stanie wstrzymania lub wyłączonym) przez godzinę przed użyciem urządzenia.
1. Używaj urządzenia w środowisku w zakresie temperatur.
1. Korzystanie z pomieszczeń urządzenia.
1. Używanie urządzenia w cieniu; nawet w pomieszczeniu unikaj bezpośredniej instalacji przy oknach lub skylightach.
1. Jeśli postępuj zgodnie z powyższymi wytycznymi, ale wystąpią nieoczekiwane problemy, wykonaj poniższe kroki, aby przesłać [opinię.](hololens-feedback.md) 
    1. Upewnij **się,** że **na** urządzeniu jest włączona pełna lub opcjonalna telemetria. Jeśli tak nie jest, włącz ją. 
    >[!CAUTION]
    > Telemetria nie jest wsteczna dla zdarzeń cieplnych — musi być włączona podczas przetwarzania lub wymagane dane nie zostaną przechwycone.
    
    2. Odtąd odtąd problem z grzewczym.
    3. Uwzględnij datę i czas, o których wystąpiło chłonienie.
    4. Prześlij [opinię.](hololens-feedback.md)

## <a name="see-also"></a>Zobacz też

- [Projekt mapowania przestrzennego](/windows/mixed-reality/spatial-mapping)
- [Hologramy](/windows/mixed-reality/hologram)
