---
title: Mapowanie przestrzeni fizycznych za pomocą urządzenia HoloLens
description: Urządzenie HoloLens dowiesz się, jak wygląda przestrzeń w czasie. Użytkownicy mogą ułatwić ten proces, przenosząc urządzenia HoloLens w określony sposób przez przestrzeń.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens, Windows Mixed Reality, projektowanie, mapowanie przestrzenne, HoloLens, odtworzeń powierzchni, siatki, śledzenia głowy, mapowanie
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: 7cedf2af90744477c33736087c85a43168167707
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379739"
---
# <a name="map-physical-spaces-with-hololens"></a>Mapowanie przestrzeni fizycznych za pomocą urządzenia HoloLens

Urządzenie HoloLens łączy hologramy ze światem fizycznym. Aby to zrobić, urządzenie HoloLens musi poznać świat fizyczny wokół Ciebie i zapamiętać, gdzie umieszczasz hologramy w tej przestrzeni.

Z czasem urządzenie HoloLens tworzy mapę *przestrzenną* środowiska, które widział.  Urządzenie HoloLens aktualizuje mapę w przypadku zmiany środowiska. Tak długo, jak użytkownik jest zalogowany i urządzenie jest włączone, urządzenie HoloLens tworzy i aktualizuje mapy przestrzenne. Jeśli urządzenie jest wstrzymywane lub zużywane przy użyciu kamer wskazywanych w przestrzeni, urządzenie HoloLens próbuje zamapować obszar. Chociaż urządzenie HoloLens uczy się kosmosu w naturalny sposób, istnieją sposoby, dzięki którym można szybciej i wydajniej mapować przestrzeń na urządzenia HoloLens.  

> [!NOTE]
> Jeśli urządzenie HoloLens nie może zamapować twojej przestrzeni lub jest poza jej powierzchnią, urządzenie HoloLens może przejść do trybu ograniczonego. W trybie ograniczonym nie będzie można umieszczać hologramów w okolicy.

W tym artykule wyjaśniono, jak urządzenie HoloLens mapuje miejsca, jak ulepszyć mapowanie przestrzenne i jak zarządzać danymi przestrzennmi zbieranych przez urządzenie HoloLens.

## <a name="choosing-and-setting-up-and-your-space"></a>Wybieranie i konfigurowanie miejsca

Funkcje w środowisku mogą utrudnić zinterpretować przestrzeń na urządzeniach HoloLens. Poziomy światła, materiały w przestrzeni, układ obiektów i inne mogą mieć wpływ na sposób mapowania obszaru na urządzenia HoloLens.

Urządzenie HoloLens działa najlepiej w niektórych rodzajach środowisk. Aby utworzyć najlepszą mapę przestrzenną, wybierz pomieszczenie z odpowiednim oświetleniem i dużą ilością miejsca. Unikaj ciemnych przestrzeni i pomieszczeń, które mają dużo ciemnych, cykanych lub przezroczystych powierzchni (na przykład dublowanych lub gauzy).

Urządzenie HoloLens jest zoptymalizowane pod kątem użytku w pomieszczeniu. Mapowanie przestrzenne działa również najlepiej, Wi-Fi jest włączone, chociaż nie musi być połączone z siecią. Urządzenie HoloLens może uzyskać Wi-Fi dostępu, nawet jeśli nie jest połączony ani uwierzytelniony. Funkcja urządzenia HoloLens nie zmienia tego, czy punkty dostępu są połączone z Internetem, czy tylko intranet/lokalne.

Urządzenia HoloLens należy używać tylko w bezpiecznych miejscach bez zagrożeń związanych z trippingiem. [Więcej informacji na temat bezpieczeństwa.](https://support.microsoft.com/help/4023454/safety-information)

## <a name="mapping-your-space"></a>Mapowanie miejsca

Teraz możesz rozpocząć mapowanie zapasowej.  Gdy urządzenie HoloLens zacznie mapować twoje otoczenia, zobaczysz siatkę rozkładającą się na przestrzeń.  W domu rzeczywistości mieszanej można wyzwolić wyświetlanie mapy, wybierając pozycję na zamapowanej powierzchni.

Poniżej znajdują się wskazówki dotyczące tworzenia wspaniałej mapy przestrzennej.

### <a name="understand-the-scenarios-for-the-area"></a>Opis scenariuszy dla obszaru

Ważne jest, aby spędzać najwięcej czasu na używaniu urządzenia HoloLens, aby mapa była istotna i kompletna. Jeśli na przykład scenariusz użytkownika urządzenia HoloLens obejmuje przejście z punktu A do punktu B, przekieruj ścieżkę od dwóch do trzech razy, patrząc we wszystkich kierunkach podczas przenoszenia.  

### <a name="walk-slowly-around-the-space"></a>Powolne poruszanie się po przestrzeni

Jeśli będziesz zbyt szybko przechodzić przez ten obszar, prawdopodobnie na urządzeniach HoloLens brakuje obszarów mapowania. Poruszaj się powoli po przestrzeni, zatrzymując się co 5–8 metrów, aby rozejrzeć się po okolicy.  

Płynne ruchy ułatwiają również wydajniejszą mapę urządzenia HoloLens.

### <a name="look-in-all-directions"></a>Spójrz we wszystkich kierunkach

Podczas mapowania obszar zapewnia hololensowi więcej danych na temat tego, gdzie punkty są względem siebie względne.  

Jeśli na przykład nie poszukasz, urządzenie HoloLens może nie wiedzieć, gdzie znajduje się limit w pomieszczeniu.  

Nie zapomnij zajrzeć na podłogę podczas mapowania przestrzeni.

### <a name="cover-key-areas-multiple-times"></a>Wielokrotne osłanianie kluczowych obszarów

Wielokrotne poruszanie się po obszarze pomoże w odebraniu funkcji, które mogą zostać pominięte w pierwszym przewodniku. Aby utworzyć idealną mapę, spróbuj wykonać przechodzenie przez obszar od dwóch do trzech razy.

Jeśli to możliwe, powtarzając te ruchy, spędzaj czas na poruszaniu się po obszarze w jednym kierunku, a następnie zawróć i wrócić do celu.

### <a name="take-your-time-mapping-the-area"></a>Mapowanie obszaru w czasie

Pełne mapowanie urządzenia HoloLens i dostosowanie się do jego otoczenia może potrwać od 15 do 20 minut. Jeśli masz miejsce, w którym planujesz często używać urządzenia HoloLens, późniejsze mapowanie tego miejsca może zapobiec problemom.  

## <a name="possible-errors-in-the-spatial-map"></a>Możliwe błędy na mapie przestrzennej

Błędy w danych mapowania przestrzennego można podzielone na kilka kategorii:

- *Otwory:* w danych mapowania przestrzennego brakuje rzeczywistych powierzchni.
- *Omamy:* Powierzchnie istnieją w danych mapowania przestrzennego, które nie istnieją w świecie rzeczywistym.
- *Wormholes*: urządzenie HoloLens "traci" część mapy przestrzennej, myśląc, że znajduje się w innej części mapy niż w rzeczywistości.
- Stronniczość: Powierzchnie w danych mapowania przestrzennego są niedoskonałie wyrównane z powierzchniami rzeczywistymi, wypychane lub ściągane.

Jeśli zostanie wyświetlony dowolny z tych błędów, użyj usługi [FeedbackHub,](hololens-feedback.md) aby przesłać opinię.

## <a name="security-and-storage-for-spatial-data"></a>Zabezpieczenia i magazyn danych przestrzennych

Windows 10 wersji 1803 dla programu Microsoft HoloLens i nowszych przechowuje dane mapowania w lokalnej bazie danych (na urządzeniu).

Użytkownicy urządzenia HoloLens nie mogą bezpośrednio uzyskać dostępu do bazy danych map, nawet jeśli urządzenie jest podłączone do komputera lub gdy jest Eksplorator plików aplikacji. Po włączeniu funkcji BitLocker na urządzeniu HoloLens przechowywane dane mapy są również szyfrowane wraz z całym woluminem.

### <a name="remove-map-data-and-known-spaces-from-hololens"></a>Usuwanie danych mapy i znanych miejsc z urządzenia HoloLens

Istnieją dwie opcje usuwania danych mapy w ustawieniach **> systemowych > Hologramach:**

- Aby usunąć hologramy w pobliżu, wybierz **pozycję Usuń hologramy w pobliżu.** To polecenie wyczyści dane mapy i zakotwiczone hologramy dla bieżącej przestrzeni. Jeśli nadal używasz urządzenia w tym samym miejscu, tworzy i przechowuje zupełnie nową sekcję mapy w celu zastąpienia usuniętych informacji.

   > [!NOTE]
   > Hologramy "W pobliżu" to hologramy zakotwiczone w tej samej sekcji mapy w bieżącej przestrzeni.

   Można na przykład użyć tej opcji, aby wyczyścić dane mapy związane z pracą bez wpływu na żadne dane mapy dotyczące domu.

- Aby usunąć wszystkie hologramy, wybierz **pozycję Usuń wszystkie hologramy**. To polecenie wyczyści wszystkie dane mapy przechowywane na urządzeniu, a także wszystkie zakotwiczone hologramy. Należy jawnie umieścić wszelkie hologramy. Nie będzie można ponownie odnaleźć wcześniej umieszczonych hologramów.

> [!NOTE]
> Po usunięciu pobliskich lub wszystkich hologramów urządzenie HoloLens natychmiast rozpoczyna skanowanie i mapowanie bieżącego miejsca.

### <a name="wi-fi-data-in-spatial-maps"></a>Wi-Fi danych w mapach przestrzennych

Urządzenie HoloLens przechowuje Wi-Fi, aby ułatwić korelowanie lokalizacji hologramów i sekcji mapy przechowywanych w bazie danych HoloLens znanych miejsc. Informacje o Wi-Fi są niedostępne dla użytkowników i nie są wysyłane do firmy Microsoft przy użyciu chmury ani telemetrii.

Tak długo, Wi-Fi jest włączona, urządzenie HoloLens koreluje dane mapy z pobliskimi Wi-Fi punktami dostępu. Nie ma różnicy w zachowaniu tego, czy sieć jest połączona, czy po prostu wykryto w pobliżu. Jeśli Wi-Fi jest wyłączona, urządzenie HoloLens nadal wyszukuje miejsce. Jednak urządzenie HoloLens musi przeszukiwać więcej danych mapy w bazie danych spaces i może potrzebować więcej czasu na znalezienie hologramów. Bez informacji Wi-Fi urządzenia HoloLens musi porównać aktywne skanowania ze wszystkimi kotwicami hologramów i sekcjami mapy przechowywanymi na urządzeniu, aby zlokalizować poprawną część mapy.

## <a name="related-topics"></a>Powiązane tematy

- [Projekt mapowania przestrzennego](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping)
