---
title: Mapowanie przestrzeni fizycznych za pomocą HoloLens
description: HoloLens, jak wygląda przestrzeń w czasie. Użytkownicy mogą ułatwić ten proces, przenosząc HoloLens w określony sposób przez przestrzeń.
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
ms.openlocfilehash: b8bda049f0ef4610dcf0ca6fe81d89dd5a316e3e
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640045"
---
# <a name="map-physical-spaces-with-hololens"></a>Mapowanie przestrzeni fizycznych za pomocą HoloLens

HoloLens łączy hologramy ze światem fizycznym. Aby to zrobić, HoloLens poznać świat fizyczny wokół Ciebie i zapamiętać, gdzie umieszczasz hologramy w tej przestrzeni.

W czasie HoloLens tworzy mapę *przestrzenną* środowiska, które widział.  HoloLens aktualizuje mapę w przypadku zmiany środowiska. Tak długo, jak użytkownik jest zalogowany i urządzenie jest włączone, HoloLens tworzy i aktualizuje mapy przestrzenne. Jeśli urządzenie jest wstrzymywane lub zużywane przy użyciu kamer wskazywanych w przestrzeni, HoloLens próbuje zamapować obszar. Chociaż HoloLens uczy się przestrzeni w naturalny sposób, istnieją sposoby, dzięki którym można HoloLens szybciej i wydajniej mapować przestrzeń.  

> [!NOTE]
> Jeśli urządzenie HoloLens nie może zamapować przestrzeni lub nie jest nachylić, może HoloLens tryb ograniczony. W trybie ograniczonym nie będzie można umieszczać hologramów w okolicy.

W tym artykule wyjaśniono, HoloLens obszarów mapy, jak poprawić mapowanie przestrzenne i jak zarządzać danymi przestrzennych, które HoloLens dane.

## <a name="choosing-and-setting-up-and-your-space"></a>Wybieranie i konfigurowanie miejsca

Funkcje w środowisku mogą utrudniać HoloLens interpretacji spacji. Poziomy światła, materiały w przestrzeni, układ obiektów i inne mogą mieć wpływ na sposób mapowania HoloLens obszaru.

HoloLens działa najlepiej w niektórych rodzajach środowisk. Aby utworzyć najlepszą mapę przestrzenną, wybierz pomieszczenie z odpowiednim oświetleniem i dużą ilością miejsca. Unikaj ciemnych przestrzeni i pomieszczeń, które mają dużo ciemnych, cykanych lub przezroczystych powierzchni (na przykład dublowanych lub gauzy).

HoloLens jest zoptymalizowany do użytku w pomieszczeniu. Mapowanie przestrzenne działa również najlepiej, Wi-Fi jest włączone, chociaż nie musi być połączone z siecią. HoloLens uzyskać dostęp do Wi-Fi dostępu, nawet jeśli nie są połączone ani uwierzytelnione. HoloLens nie zmienia tego, czy punkty dostępu są połączone z Internetem, czy tylko intranet/lokalne.

Używaj tylko HoloLens w bezpiecznych miejscach bez zagrożeń związanych z trippingiem. [Więcej informacji na temat bezpieczeństwa.](https://support.microsoft.com/help/4023454/safety-information)

## <a name="mapping-your-space"></a>Mapowanie miejsca

Teraz możesz rozpocząć mapowanie zapasowej.  Gdy HoloLens mapowanie otoczenia, zobaczysz siatkę rozkładającą się na przestrzeń.  W domu rzeczywistości mieszanej można wyzwolić wyświetlanie mapy, wybierając pozycję na zamapowanej powierzchni.

Poniżej znajdują się wskazówki dotyczące tworzenia wspaniałej mapy przestrzennej.

### <a name="understand-the-scenarios-for-the-area"></a>Opis scenariuszy dla obszaru

Ważne jest, aby poświęcać najwięcej czasu na korzystanie z HoloLens, aby mapa była istotna i kompletna. Jeśli na przykład scenariusz użytkownika dla usługi HoloLens obejmuje przejście z punktu A do punktu B, należy przejść przez ścieżkę od dwóch do trzech razy, patrząc we wszystkich kierunkach podczas przenoszenia.  

### <a name="walk-slowly-around-the-space"></a>Powolne poruszanie się po przestrzeni

Jeśli będziesz zbyt szybko przechodzić przez ten obszar, prawdopodobnie nie HoloLens obszarów mapowania. Poruszaj się powoli po przestrzeni, zatrzymując się co 5–8 metrów, aby rozejrzeć się po okolicy.  

Płynne ruchy ułatwiają również HoloLens mapy.

### <a name="look-in-all-directions"></a>Spójrz we wszystkich kierunkach

Przyglądanie się obszarowi podczas mapowania zapewnia HoloLens danych na temat tego, gdzie punkty są względem siebie względne.  

Jeśli na przykład nie poszukasz, HoloLens może nie wiedzieć, gdzie znajduje się limit w pomieszczeniu.  

Nie zapomnij zajrzeć na podłogę podczas mapowania przestrzeni.

### <a name="cover-key-areas-multiple-times"></a>Wielokrotne osłanianie kluczowych obszarów

Wielokrotne poruszanie się po obszarze pomoże w odebraniu funkcji, które mogą zostać pominięte w pierwszym przewodniku. Aby utworzyć idealną mapę, spróbuj wykonać przechodzenie przez obszar od dwóch do trzech razy.

Jeśli to możliwe, powtarzając te ruchy, spędzaj czas na poruszaniu się po obszarze w jednym kierunku, a następnie zawróć i wrócić do celu.

### <a name="take-your-time-mapping-the-area"></a>Mapowanie obszaru w czasie

Pełne mapowanie HoloLens dostosowanie się do jej otoczenia może potrwać od 15 do 20 minut. Jeśli masz miejsce, w którym planujesz często używać HoloLens, późniejsze mapowanie obszaru może zapobiec problemom.  

## <a name="possible-errors-in-the-spatial-map"></a>Możliwe błędy na mapie przestrzennej

Błędy w danych mapowania przestrzennego można podzielone na kilka kategorii:

- *Otwory:* w danych mapowania przestrzennego brakuje rzeczywistych powierzchni.
- *Omamy:* Powierzchnie istnieją w danych mapowania przestrzennego, które nie istnieją w świecie rzeczywistym.
- *Wormholes*: HoloLens "traci" część mapy przestrzennej, myśląc, że znajduje się ona w innej części mapy niż w rzeczywistości.
- Stronniczość: Powierzchnie w danych mapowania przestrzennego są niedoskonałie wyrównane z powierzchniami rzeczywistymi, wypychane lub ściągane.

Jeśli zostanie wyświetlony dowolny z tych błędów, użyj usługi [FeedbackHub,](hololens-feedback.md) aby przesłać opinię.

## <a name="security-and-storage-for-spatial-data"></a>Zabezpieczenia i magazyn danych przestrzennych

Windows 10 wersji 1803 dla programu Microsoft HoloLens i nowszych przechowuje dane mapowania w lokalnej bazie danych (na urządzeniu).

HoloLens użytkownicy nie mogą bezpośrednio uzyskać dostępu do bazy danych mapy, nawet jeśli urządzenie jest podłączone do komputera lub podczas korzystania z Eksplorator plików danych. Gdy funkcja BitLocker jest włączona HoloLens, przechowywane dane mapy są również szyfrowane wraz z całym woluminem.

### <a name="remove-map-data-and-known-spaces-from-hololens"></a>Usuwanie danych mapy i znanych spacji z HoloLens

Istnieją dwie opcje usuwania danych mapy w Ustawienia > **System > Hologramy:**

- Aby usunąć hologramy w pobliżu, wybierz **pozycję Usuń hologramy w pobliżu.** To polecenie wyczyści dane mapy i zakotwiczone hologramy dla bieżącej przestrzeni. Jeśli nadal używasz urządzenia w tym samym miejscu, tworzy i przechowuje zupełnie nową sekcję mapy w celu zastąpienia usuniętych informacji.

   > [!NOTE]
   > Hologramy "W pobliżu" to hologramy zakotwiczone w tej samej sekcji mapy w bieżącej przestrzeni.

   Można na przykład użyć tej opcji, aby wyczyścić dane mapy związane z pracą bez wpływu na żadne dane mapy dotyczące domu.

- Aby usunąć wszystkie hologramy, wybierz **pozycję Usuń wszystkie hologramy**. To polecenie wyczyści wszystkie dane mapy przechowywane na urządzeniu, a także wszystkie zakotwiczone hologramy. Należy jawnie umieścić wszelkie hologramy. Nie będzie można ponownie odnaleźć wcześniej umieszczonych hologramów.

> [!NOTE]
> Po usunięciu pobliskich lub wszystkich hologramów HoloLens natychmiast rozpocznie się skanowanie i mapowanie bieżącego miejsca.

### <a name="wi-fi-data-in-spatial-maps"></a>Wi-Fi danych w mapach przestrzennych

HoloLens przechowuje Wi-Fi, aby ułatwić korelowanie lokalizacji hologramów i sekcji map przechowywanych w bazie HoloLens znanych miejsc. Informacje o Wi-Fi są niedostępne dla użytkowników i nie są wysyłane do firmy Microsoft przy użyciu chmury ani telemetrii.

Tak długo, Wi-Fi jest włączona, HoloLens dane mapy są skorelowane z pobliskimi Wi-Fi dostępu. Nie ma różnicy w zachowaniu tego, czy sieć jest połączona, czy po prostu wykryto w pobliżu. Jeśli Wi-Fi jest wyłączona, HoloLens nadal przeszukiwać miejsce. Jednak HoloLens musi przeszukiwać więcej danych mapy w bazie danych spacji i może potrzebować więcej czasu na znalezienie hologramów. Bez informacji Wi-Fi, HoloLens musi porównać aktywne skanowania ze wszystkimi kotwicami hologramów i sekcjami mapy przechowywanymi na urządzeniu, aby zlokalizować poprawną część mapy.

## <a name="related-topics"></a>Powiązane tematy

- [Projekt mapowania przestrzennego](/windows/mixed-reality/spatial-mapping)
