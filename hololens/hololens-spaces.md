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
# <a name="map-physical-spaces-with-hololens"></a><span data-ttu-id="0c530-105">Mapowanie przestrzeni fizycznych za pomocą HoloLens</span><span class="sxs-lookup"><span data-stu-id="0c530-105">Map physical spaces with HoloLens</span></span>

<span data-ttu-id="0c530-106">HoloLens łączy hologramy ze światem fizycznym.</span><span class="sxs-lookup"><span data-stu-id="0c530-106">HoloLens blends holograms with your physical world.</span></span> <span data-ttu-id="0c530-107">Aby to zrobić, HoloLens poznać świat fizyczny wokół Ciebie i zapamiętać, gdzie umieszczasz hologramy w tej przestrzeni.</span><span class="sxs-lookup"><span data-stu-id="0c530-107">To do that, HoloLens has to learn about the physical world around you and remember where you place holograms within that space.</span></span>

<span data-ttu-id="0c530-108">W czasie HoloLens tworzy mapę *przestrzenną* środowiska, które widział.</span><span class="sxs-lookup"><span data-stu-id="0c530-108">Over time, the HoloLens builds up a *spatial map* of the environment that it has seen.</span></span>  <span data-ttu-id="0c530-109">HoloLens aktualizuje mapę w przypadku zmiany środowiska.</span><span class="sxs-lookup"><span data-stu-id="0c530-109">HoloLens updates the map as the environment changes.</span></span> <span data-ttu-id="0c530-110">Tak długo, jak użytkownik jest zalogowany i urządzenie jest włączone, HoloLens tworzy i aktualizuje mapy przestrzenne.</span><span class="sxs-lookup"><span data-stu-id="0c530-110">As long as you are logged in and the device is turned on, HoloLens creates and updates your spatial maps.</span></span> <span data-ttu-id="0c530-111">Jeśli urządzenie jest wstrzymywane lub zużywane przy użyciu kamer wskazywanych w przestrzeni, HoloLens próbuje zamapować obszar.</span><span class="sxs-lookup"><span data-stu-id="0c530-111">If you hold or wear the device with the cameras pointed at a space, the HoloLens tries to map the area.</span></span> <span data-ttu-id="0c530-112">Chociaż HoloLens uczy się przestrzeni w naturalny sposób, istnieją sposoby, dzięki którym można HoloLens szybciej i wydajniej mapować przestrzeń.</span><span class="sxs-lookup"><span data-stu-id="0c530-112">While the HoloLens learns a space naturally over time, there are ways in which you can help HoloLens map your space more quickly and efficiently.</span></span>  

> [!NOTE]
> <span data-ttu-id="0c530-113">Jeśli urządzenie HoloLens nie może zamapować przestrzeni lub nie jest nachylić, może HoloLens tryb ograniczony.</span><span class="sxs-lookup"><span data-stu-id="0c530-113">If your HoloLens can't map your space or is out of calibration, HoloLens may enter Limited mode.</span></span> <span data-ttu-id="0c530-114">W trybie ograniczonym nie będzie można umieszczać hologramów w okolicy.</span><span class="sxs-lookup"><span data-stu-id="0c530-114">In Limited mode, you won't be able to place holograms in your surroundings.</span></span>

<span data-ttu-id="0c530-115">W tym artykule wyjaśniono, HoloLens obszarów mapy, jak poprawić mapowanie przestrzenne i jak zarządzać danymi przestrzennych, które HoloLens dane.</span><span class="sxs-lookup"><span data-stu-id="0c530-115">This article explains how HoloLens maps spaces, how to improve spatial mapping, and how to manage the spatial data that HoloLens collects.</span></span>

## <a name="choosing-and-setting-up-and-your-space"></a><span data-ttu-id="0c530-116">Wybieranie i konfigurowanie miejsca</span><span class="sxs-lookup"><span data-stu-id="0c530-116">Choosing and setting up and your space</span></span>

<span data-ttu-id="0c530-117">Funkcje w środowisku mogą utrudniać HoloLens interpretacji spacji.</span><span class="sxs-lookup"><span data-stu-id="0c530-117">Features in your environment can make it difficult for the HoloLens to interpret a space.</span></span> <span data-ttu-id="0c530-118">Poziomy światła, materiały w przestrzeni, układ obiektów i inne mogą mieć wpływ na sposób mapowania HoloLens obszaru.</span><span class="sxs-lookup"><span data-stu-id="0c530-118">Light levels, materials in the space, the layout of objects, and more can all affect how HoloLens maps an area.</span></span>

<span data-ttu-id="0c530-119">HoloLens działa najlepiej w niektórych rodzajach środowisk.</span><span class="sxs-lookup"><span data-stu-id="0c530-119">HoloLens works best in certain kinds of environments.</span></span> <span data-ttu-id="0c530-120">Aby utworzyć najlepszą mapę przestrzenną, wybierz pomieszczenie z odpowiednim oświetleniem i dużą ilością miejsca.</span><span class="sxs-lookup"><span data-stu-id="0c530-120">To produce the best spatial map, choose a room that has adequate light and plenty of space.</span></span> <span data-ttu-id="0c530-121">Unikaj ciemnych przestrzeni i pomieszczeń, które mają dużo ciemnych, cykanych lub przezroczystych powierzchni (na przykład dublowanych lub gauzy).</span><span class="sxs-lookup"><span data-stu-id="0c530-121">Avoid dark spaces and rooms that have a lot of dark, shiny, or translucent surfaces (for instance, mirrors or gauzy curtains).</span></span>

<span data-ttu-id="0c530-122">HoloLens jest zoptymalizowany do użytku w pomieszczeniu.</span><span class="sxs-lookup"><span data-stu-id="0c530-122">HoloLens is optimized for indoor use.</span></span> <span data-ttu-id="0c530-123">Mapowanie przestrzenne działa również najlepiej, Wi-Fi jest włączone, chociaż nie musi być połączone z siecią.</span><span class="sxs-lookup"><span data-stu-id="0c530-123">Spatial mapping also works best when Wi-Fi is turned on, although it doesn't have to be connected to a network.</span></span> <span data-ttu-id="0c530-124">HoloLens uzyskać dostęp do Wi-Fi dostępu, nawet jeśli nie są połączone ani uwierzytelnione.</span><span class="sxs-lookup"><span data-stu-id="0c530-124">HoloLens can obtain Wi-Fi access points even if it is not connected or authenticated.</span></span> <span data-ttu-id="0c530-125">HoloLens nie zmienia tego, czy punkty dostępu są połączone z Internetem, czy tylko intranet/lokalne.</span><span class="sxs-lookup"><span data-stu-id="0c530-125">HoloLens functionality does not change whether the access points are internet-connected or intranet/local only.</span></span>

<span data-ttu-id="0c530-126">Używaj tylko HoloLens w bezpiecznych miejscach bez zagrożeń związanych z trippingiem.</span><span class="sxs-lookup"><span data-stu-id="0c530-126">Only use HoloLens in safe places with no tripping hazards.</span></span> <span data-ttu-id="0c530-127">[Więcej informacji na temat bezpieczeństwa.](https://support.microsoft.com/help/4023454/safety-information)</span><span class="sxs-lookup"><span data-stu-id="0c530-127">[More on safety](https://support.microsoft.com/help/4023454/safety-information).</span></span>

## <a name="mapping-your-space"></a><span data-ttu-id="0c530-128">Mapowanie miejsca</span><span class="sxs-lookup"><span data-stu-id="0c530-128">Mapping your space</span></span>

<span data-ttu-id="0c530-129">Teraz możesz rozpocząć mapowanie zapasowej.</span><span class="sxs-lookup"><span data-stu-id="0c530-129">Now you're ready to start mapping your spare.</span></span>  <span data-ttu-id="0c530-130">Gdy HoloLens mapowanie otoczenia, zobaczysz siatkę rozkładającą się na przestrzeń.</span><span class="sxs-lookup"><span data-stu-id="0c530-130">When HoloLens starts mapping your surroundings, you'll see a mesh graphic spreading over the space.</span></span>  <span data-ttu-id="0c530-131">W domu rzeczywistości mieszanej można wyzwolić wyświetlanie mapy, wybierając pozycję na zamapowanej powierzchni.</span><span class="sxs-lookup"><span data-stu-id="0c530-131">In mixed reality home, you can trigger the map to show by selecting on a mapped surface.</span></span>

<span data-ttu-id="0c530-132">Poniżej znajdują się wskazówki dotyczące tworzenia wspaniałej mapy przestrzennej.</span><span class="sxs-lookup"><span data-stu-id="0c530-132">Here are guidelines for building a great spatial map.</span></span>

### <a name="understand-the-scenarios-for-the-area"></a><span data-ttu-id="0c530-133">Opis scenariuszy dla obszaru</span><span class="sxs-lookup"><span data-stu-id="0c530-133">Understand the scenarios for the area</span></span>

<span data-ttu-id="0c530-134">Ważne jest, aby poświęcać najwięcej czasu na korzystanie z HoloLens, aby mapa była istotna i kompletna.</span><span class="sxs-lookup"><span data-stu-id="0c530-134">It is important to spend the most time where you will be using the HoloLens, so that the map is relevant and complete.</span></span> <span data-ttu-id="0c530-135">Jeśli na przykład scenariusz użytkownika dla usługi HoloLens obejmuje przejście z punktu A do punktu B, należy przejść przez ścieżkę od dwóch do trzech razy, patrząc we wszystkich kierunkach podczas przenoszenia.</span><span class="sxs-lookup"><span data-stu-id="0c530-135">For example, if a user scenario for HoloLens involves moving from Point A to Point B, walk that path two to three times, looking in all directions as you move.</span></span>  

### <a name="walk-slowly-around-the-space"></a><span data-ttu-id="0c530-136">Powolne poruszanie się po przestrzeni</span><span class="sxs-lookup"><span data-stu-id="0c530-136">Walk slowly around the space</span></span>

<span data-ttu-id="0c530-137">Jeśli będziesz zbyt szybko przechodzić przez ten obszar, prawdopodobnie nie HoloLens obszarów mapowania.</span><span class="sxs-lookup"><span data-stu-id="0c530-137">If you walk too quickly around the area, it's likely that the HoloLens will miss mapping areas.</span></span> <span data-ttu-id="0c530-138">Poruszaj się powoli po przestrzeni, zatrzymując się co 5–8 metrów, aby rozejrzeć się po okolicy.</span><span class="sxs-lookup"><span data-stu-id="0c530-138">Walk slowly around the space, stopping every 5-8 feet to look around at your surroundings.</span></span>  

<span data-ttu-id="0c530-139">Płynne ruchy ułatwiają również HoloLens mapy.</span><span class="sxs-lookup"><span data-stu-id="0c530-139">Smooth movements also help the HoloLens map more efficiently.</span></span>

### <a name="look-in-all-directions"></a><span data-ttu-id="0c530-140">Spójrz we wszystkich kierunkach</span><span class="sxs-lookup"><span data-stu-id="0c530-140">Look in all directions</span></span>

<span data-ttu-id="0c530-141">Przyglądanie się obszarowi podczas mapowania zapewnia HoloLens danych na temat tego, gdzie punkty są względem siebie względne.</span><span class="sxs-lookup"><span data-stu-id="0c530-141">Looking around as you map the space gives the HoloLens more data on where points are relative to each other.</span></span>  

<span data-ttu-id="0c530-142">Jeśli na przykład nie poszukasz, HoloLens może nie wiedzieć, gdzie znajduje się limit w pomieszczeniu.</span><span class="sxs-lookup"><span data-stu-id="0c530-142">If you don't look up, for example, the HoloLens may not know where the ceiling in a room is.</span></span>  

<span data-ttu-id="0c530-143">Nie zapomnij zajrzeć na podłogę podczas mapowania przestrzeni.</span><span class="sxs-lookup"><span data-stu-id="0c530-143">Don't forget to look down at the floor as you map the space.</span></span>

### <a name="cover-key-areas-multiple-times"></a><span data-ttu-id="0c530-144">Wielokrotne osłanianie kluczowych obszarów</span><span class="sxs-lookup"><span data-stu-id="0c530-144">Cover key areas multiple times</span></span>

<span data-ttu-id="0c530-145">Wielokrotne poruszanie się po obszarze pomoże w odebraniu funkcji, które mogą zostać pominięte w pierwszym przewodniku.</span><span class="sxs-lookup"><span data-stu-id="0c530-145">Moving through an area multiple times will help pick up features you may have missed on the first walkthrough.</span></span> <span data-ttu-id="0c530-146">Aby utworzyć idealną mapę, spróbuj wykonać przechodzenie przez obszar od dwóch do trzech razy.</span><span class="sxs-lookup"><span data-stu-id="0c530-146">To build an ideal map, try traversing an area two to three times.</span></span>

<span data-ttu-id="0c530-147">Jeśli to możliwe, powtarzając te ruchy, spędzaj czas na poruszaniu się po obszarze w jednym kierunku, a następnie zawróć i wrócić do celu.</span><span class="sxs-lookup"><span data-stu-id="0c530-147">If possible, while repeating these movements, spend time walking through an area in one direction, then turn around and walk back the way you came.</span></span>

### <a name="take-your-time-mapping-the-area"></a><span data-ttu-id="0c530-148">Mapowanie obszaru w czasie</span><span class="sxs-lookup"><span data-stu-id="0c530-148">Take your time mapping the area</span></span>

<span data-ttu-id="0c530-149">Pełne mapowanie HoloLens dostosowanie się do jej otoczenia może potrwać od 15 do 20 minut.</span><span class="sxs-lookup"><span data-stu-id="0c530-149">It can take between 15 and 20 minutes for the HoloLens to fully map and adjust itself to its surroundings.</span></span> <span data-ttu-id="0c530-150">Jeśli masz miejsce, w którym planujesz często używać HoloLens, późniejsze mapowanie obszaru może zapobiec problemom.</span><span class="sxs-lookup"><span data-stu-id="0c530-150">If you have a space in which you plan to use a HoloLens frequently, taking that time up front to map the space can prevent issues later on.</span></span>  

## <a name="possible-errors-in-the-spatial-map"></a><span data-ttu-id="0c530-151">Możliwe błędy na mapie przestrzennej</span><span class="sxs-lookup"><span data-stu-id="0c530-151">Possible errors in the spatial map</span></span>

<span data-ttu-id="0c530-152">Błędy w danych mapowania przestrzennego można podzielone na kilka kategorii:</span><span class="sxs-lookup"><span data-stu-id="0c530-152">Errors in spatial mapping data fall into a few categories:</span></span>

- <span data-ttu-id="0c530-153">*Otwory:* w danych mapowania przestrzennego brakuje rzeczywistych powierzchni.</span><span class="sxs-lookup"><span data-stu-id="0c530-153">*Holes*: Real-world surfaces are missing from the spatial mapping data.</span></span>
- <span data-ttu-id="0c530-154">*Omamy:* Powierzchnie istnieją w danych mapowania przestrzennego, które nie istnieją w świecie rzeczywistym.</span><span class="sxs-lookup"><span data-stu-id="0c530-154">*Hallucinations*: Surfaces exist in the spatial mapping data that do not exist in the real world.</span></span>
- <span data-ttu-id="0c530-155">*Wormholes*: HoloLens "traci" część mapy przestrzennej, myśląc, że znajduje się ona w innej części mapy niż w rzeczywistości.</span><span class="sxs-lookup"><span data-stu-id="0c530-155">*Wormholes*: HoloLens 'loses' part of the spatial map by thinking it is in a different part of the map than it actually is.</span></span>
- <span data-ttu-id="0c530-156">Stronniczość: Powierzchnie w danych mapowania przestrzennego są niedoskonałie wyrównane z powierzchniami rzeczywistymi, wypychane lub ściągane.</span><span class="sxs-lookup"><span data-stu-id="0c530-156">*Bias*: Surfaces in the spatial mapping data are imperfectly aligned with real-world surfaces, either pushed in or pulled out.</span></span>

<span data-ttu-id="0c530-157">Jeśli zostanie wyświetlony dowolny z tych błędów, użyj usługi [FeedbackHub,](hololens-feedback.md) aby przesłać opinię.</span><span class="sxs-lookup"><span data-stu-id="0c530-157">If you see any of these errors please use the [FeedbackHub](hololens-feedback.md) to send feedback.</span></span>

## <a name="security-and-storage-for-spatial-data"></a><span data-ttu-id="0c530-158">Zabezpieczenia i magazyn danych przestrzennych</span><span class="sxs-lookup"><span data-stu-id="0c530-158">Security and storage for spatial data</span></span>

<span data-ttu-id="0c530-159">Windows 10 wersji 1803 dla programu Microsoft HoloLens i nowszych przechowuje dane mapowania w lokalnej bazie danych (na urządzeniu).</span><span class="sxs-lookup"><span data-stu-id="0c530-159">Windows 10 version 1803 update for Microsoft HoloLens and later stores mapping data in a local (on-device) database.</span></span>

<span data-ttu-id="0c530-160">HoloLens użytkownicy nie mogą bezpośrednio uzyskać dostępu do bazy danych mapy, nawet jeśli urządzenie jest podłączone do komputera lub podczas korzystania z Eksplorator plików danych.</span><span class="sxs-lookup"><span data-stu-id="0c530-160">HoloLens users cannot directly access the map database, even when the device is plugged into a PC or when using the File Explorer app.</span></span> <span data-ttu-id="0c530-161">Gdy funkcja BitLocker jest włączona HoloLens, przechowywane dane mapy są również szyfrowane wraz z całym woluminem.</span><span class="sxs-lookup"><span data-stu-id="0c530-161">When BitLocker is enabled on HoloLens, the stored map data is also encrypted along with the entire volume.</span></span>

### <a name="remove-map-data-and-known-spaces-from-hololens"></a><span data-ttu-id="0c530-162">Usuwanie danych mapy i znanych spacji z HoloLens</span><span class="sxs-lookup"><span data-stu-id="0c530-162">Remove map data and known spaces from HoloLens</span></span>

<span data-ttu-id="0c530-163">Istnieją dwie opcje usuwania danych mapy w Ustawienia > **System > Hologramy:**</span><span class="sxs-lookup"><span data-stu-id="0c530-163">There are two options for deleting map data in **Settings > System > Holograms**:</span></span>

- <span data-ttu-id="0c530-164">Aby usunąć hologramy w pobliżu, wybierz **pozycję Usuń hologramy w pobliżu.**</span><span class="sxs-lookup"><span data-stu-id="0c530-164">To delete nearby holograms, select **Remove nearby holograms**.</span></span> <span data-ttu-id="0c530-165">To polecenie wyczyści dane mapy i zakotwiczone hologramy dla bieżącej przestrzeni.</span><span class="sxs-lookup"><span data-stu-id="0c530-165">This command clears the map data and anchored holograms for the current space.</span></span> <span data-ttu-id="0c530-166">Jeśli nadal używasz urządzenia w tym samym miejscu, tworzy i przechowuje zupełnie nową sekcję mapy w celu zastąpienia usuniętych informacji.</span><span class="sxs-lookup"><span data-stu-id="0c530-166">If you continue to use the device in the same space, it creates and stores a brand new map section to replace the deleted information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0c530-167">Hologramy "W pobliżu" to hologramy zakotwiczone w tej samej sekcji mapy w bieżącej przestrzeni.</span><span class="sxs-lookup"><span data-stu-id="0c530-167">"Nearby" holograms are holograms that are anchored within the same map section in the current space.</span></span>

   <span data-ttu-id="0c530-168">Można na przykład użyć tej opcji, aby wyczyścić dane mapy związane z pracą bez wpływu na żadne dane mapy dotyczące domu.</span><span class="sxs-lookup"><span data-stu-id="0c530-168">For example, you can use this option to clear work-related map data without affecting any home-related map data.</span></span>

- <span data-ttu-id="0c530-169">Aby usunąć wszystkie hologramy, wybierz **pozycję Usuń wszystkie hologramy**.</span><span class="sxs-lookup"><span data-stu-id="0c530-169">To delete all holograms, select **Remove all holograms**.</span></span> <span data-ttu-id="0c530-170">To polecenie wyczyści wszystkie dane mapy przechowywane na urządzeniu, a także wszystkie zakotwiczone hologramy.</span><span class="sxs-lookup"><span data-stu-id="0c530-170">This command clears all map data that is stored on the device as well as all anchored holograms.</span></span> <span data-ttu-id="0c530-171">Należy jawnie umieścić wszelkie hologramy.</span><span class="sxs-lookup"><span data-stu-id="0c530-171">You will need to explicitly place any holograms.</span></span> <span data-ttu-id="0c530-172">Nie będzie można ponownie odnaleźć wcześniej umieszczonych hologramów.</span><span class="sxs-lookup"><span data-stu-id="0c530-172">You will not be able to rediscover the previously-placed holograms.</span></span>

> [!NOTE]
> <span data-ttu-id="0c530-173">Po usunięciu pobliskich lub wszystkich hologramów HoloLens natychmiast rozpocznie się skanowanie i mapowanie bieżącego miejsca.</span><span class="sxs-lookup"><span data-stu-id="0c530-173">After you remove nearby or all holograms, HoloLens immediately starts scanning and mapping the current space.</span></span>

### <a name="wi-fi-data-in-spatial-maps"></a><span data-ttu-id="0c530-174">Wi-Fi danych w mapach przestrzennych</span><span class="sxs-lookup"><span data-stu-id="0c530-174">Wi-Fi data in spatial maps</span></span>

<span data-ttu-id="0c530-175">HoloLens przechowuje Wi-Fi, aby ułatwić korelowanie lokalizacji hologramów i sekcji map przechowywanych w bazie HoloLens znanych miejsc.</span><span class="sxs-lookup"><span data-stu-id="0c530-175">HoloLens stores Wi-Fi characteristics to help correlate hologram locations and map sections that are stored within the HoloLens database of known spaces.</span></span> <span data-ttu-id="0c530-176">Informacje o Wi-Fi są niedostępne dla użytkowników i nie są wysyłane do firmy Microsoft przy użyciu chmury ani telemetrii.</span><span class="sxs-lookup"><span data-stu-id="0c530-176">Information about Wi-Fi characteristics is not accessible to users, and not sent to Microsoft using the cloud or using telemetry.</span></span>

<span data-ttu-id="0c530-177">Tak długo, Wi-Fi jest włączona, HoloLens dane mapy są skorelowane z pobliskimi Wi-Fi dostępu.</span><span class="sxs-lookup"><span data-stu-id="0c530-177">As long as Wi-Fi is enabled, HoloLens correlates map data with nearby Wi-Fi access points.</span></span> <span data-ttu-id="0c530-178">Nie ma różnicy w zachowaniu tego, czy sieć jest połączona, czy po prostu wykryto w pobliżu.</span><span class="sxs-lookup"><span data-stu-id="0c530-178">There is no difference in behavior whether a network is connected or just detected nearby.</span></span> <span data-ttu-id="0c530-179">Jeśli Wi-Fi jest wyłączona, HoloLens nadal przeszukiwać miejsce.</span><span class="sxs-lookup"><span data-stu-id="0c530-179">If Wi-Fi is disabled, HoloLens still searches the space.</span></span> <span data-ttu-id="0c530-180">Jednak HoloLens musi przeszukiwać więcej danych mapy w bazie danych spacji i może potrzebować więcej czasu na znalezienie hologramów.</span><span class="sxs-lookup"><span data-stu-id="0c530-180">However, HoloLens has to search more of the map data within the spaces database, and may need more time to find holograms.</span></span> <span data-ttu-id="0c530-181">Bez informacji Wi-Fi, HoloLens musi porównać aktywne skanowania ze wszystkimi kotwicami hologramów i sekcjami mapy przechowywanymi na urządzeniu, aby zlokalizować poprawną część mapy.</span><span class="sxs-lookup"><span data-stu-id="0c530-181">Without the Wi-Fi info, the HoloLens has to compare active scans to all hologram anchors and map sections that are stored on the device in order to locate the correct portion of the map.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0c530-182">Powiązane tematy</span><span class="sxs-lookup"><span data-stu-id="0c530-182">Related topics</span></span>

- [<span data-ttu-id="0c530-183">Projekt mapowania przestrzennego</span><span class="sxs-lookup"><span data-stu-id="0c530-183">Spatial mapping design</span></span>](/windows/mixed-reality/spatial-mapping)
