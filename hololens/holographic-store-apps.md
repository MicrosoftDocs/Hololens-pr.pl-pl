---
title: Znajdowanie, instalowanie i odinstalowywanie aplikacji
description: Aplikacja Microsoft Store źródło aplikacji i gier, które działają z urządzeniem HoloLens.  Dowiedz się więcej na temat znajdowania, instalowania i odinstalowywania aplikacji holograficznych.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 10/27/2020
manager: jarrettr
keywords: hololens, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b44ee3f9ce5aa31205feb9bb27202351e0014364
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379691"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a><span data-ttu-id="6e678-105">Znajdowanie, instalowanie i odinstalowywanie aplikacji z Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="6e678-105">Find, install, and uninstall applications from the Microsoft Store</span></span>

<span data-ttu-id="6e678-106">Urządzenie Microsoft Store to źródło aplikacji i gier, które działają z urządzeniem HoloLens.</span><span class="sxs-lookup"><span data-stu-id="6e678-106">The Microsoft Store is your go-to source for apps and games that work with HoloLens.</span></span> <span data-ttu-id="6e678-107">Po przejdź do sklepu na urządzeniach HoloLens wszystkie aplikacje, które tam zobaczysz, będą na nim uruchamiane.</span><span class="sxs-lookup"><span data-stu-id="6e678-107">When you go to the Store on your HoloLens, any apps you see there will run on it.</span></span>

<span data-ttu-id="6e678-108">Aplikacje na urządzeniach HoloLens używają widoku 2D lub widoku holograficznego.</span><span class="sxs-lookup"><span data-stu-id="6e678-108">Apps on HoloLens use either 2D view or holographic view.</span></span> <span data-ttu-id="6e678-109">Aplikacje, które używają widoku 2D, wyglądają jak okna i mogą być rozmieszowane wokół Ciebie.</span><span class="sxs-lookup"><span data-stu-id="6e678-109">Apps that use 2D view look like windows and can be positioned all around you.</span></span> <span data-ttu-id="6e678-110">Aplikacje, które korzystają z widoku holograficznego, otaczają Cię i stają się jedyną zobaczysz.</span><span class="sxs-lookup"><span data-stu-id="6e678-110">Apps that use holographic view surround you and become the only app you see.</span></span>

<span data-ttu-id="6e678-111">Urządzenie HoloLens obsługuje wiele istniejących aplikacji z Microsoft Store, a nowe aplikacje opracowane specjalnie dla urządzenia HoloLens.</span><span class="sxs-lookup"><span data-stu-id="6e678-111">HoloLens supports many existing applications from the Microsoft Store, and new apps built specifically for HoloLens.</span></span>  <span data-ttu-id="6e678-112">Ten artykuł koncentruje się na aplikacjach holograficznych z Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="6e678-112">This article focuses on holographic applications from the Microsoft Store.</span></span>

<span data-ttu-id="6e678-113">Aby dowiedzieć się więcej na temat instalowania i uruchamiania aplikacji niestandardowych, przeczytaj [temat Niestandardowe aplikacje holograficzne](holographic-custom-apps.md).</span><span class="sxs-lookup"><span data-stu-id="6e678-113">To learn more about installing and running custom apps, read [Custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="find-apps"></a><span data-ttu-id="6e678-114">Znajdź aplikacje</span><span class="sxs-lookup"><span data-stu-id="6e678-114">Find apps</span></span>

<span data-ttu-id="6e678-115">Otwórz Microsoft Store menu **Start.**</span><span class="sxs-lookup"><span data-stu-id="6e678-115">Open the Microsoft Store from the **Start** menu.</span></span> <span data-ttu-id="6e678-116">Następnie wyszukaj aplikacje i gry.</span><span class="sxs-lookup"><span data-stu-id="6e678-116">Then browse for apps and games.</span></span> <span data-ttu-id="6e678-117">Możesz wyszukiwać [przy](hololens-cortana.md) użyciu poleceń głosowych, mówiąc "Wyszukaj", po wyświetleniu okna wyszukiwania powiedz "Rozpocznij dyktowanie", a następnie po wyświetleniu monitu zacznij wypowiadać terminy wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="6e678-117">You can use [voice commands](hololens-cortana.md) to search by saying "Search", once the search window opens say "Start dictating" and then when prompted begin saying your search terms.</span></span>

> [!NOTE]
> <span data-ttu-id="6e678-118">Wymagania systemowe dla urządzeń HoloLens są oparte na architekturze kompilacji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6e678-118">The System Requirements for HoloLens devices are based on the architecture of the app build.</span></span> <span data-ttu-id="6e678-119">Jeśli kompilacja aplikacji dla urządzenia HoloLens (1. generacji) nie została zaktualizowana do nowszej platformy UWP w sklepie w celu dołączyć pakiet architektury ARM, nie będzie ona dostępna dla urządzeń HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="6e678-119">If an app build for HoloLens (1st gen) has not been updated with to a newer UWP in the store to include the ARM architecture package, then it will not be available for HoloLens 2 devices.</span></span> <span data-ttu-id="6e678-120">Podobnie jeśli aplikacja holoLens 2 nie zawiera pakietu architektury x86, nie będzie dostępna dla urządzeń HoloLens (1. generacji).</span><span class="sxs-lookup"><span data-stu-id="6e678-120">Likewise, if a HoloLens 2 app does not include the x86 architecture package, it will not be available for HoloLens (1st gen) devices.</span></span> <span data-ttu-id="6e678-121">Architektury urządzeń HoloLens:</span><span class="sxs-lookup"><span data-stu-id="6e678-121">HoloLens device architectures:</span></span>
> - <span data-ttu-id="6e678-122">x86 = HoloLens (1. generacja)</span><span class="sxs-lookup"><span data-stu-id="6e678-122">x86 = HoloLens (1st gen)</span></span>
> - <span data-ttu-id="6e678-123">ARM = HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="6e678-123">ARM = HoloLens 2</span></span>

> [!NOTE]
> <span data-ttu-id="6e678-124">12 stycznia 2021 r. następujące aplikacje zakończą wsparcie na urządzeniach HoloLens.</span><span class="sxs-lookup"><span data-stu-id="6e678-124">On January 12, 2021 the following apps will reach End of Support on HoloLens devices.</span></span> <span data-ttu-id="6e678-125">Zachęcamy do korzystania z internetowej wersji aplikacji na urządzeniu za pomocą następującego linku.</span><span class="sxs-lookup"><span data-stu-id="6e678-125">We encourage you to use the following link on your device to use the web version of the app.</span></span>

| <span data-ttu-id="6e678-126">Aplikacja</span><span class="sxs-lookup"><span data-stu-id="6e678-126">App</span></span>        | <span data-ttu-id="6e678-127">Link</span><span class="sxs-lookup"><span data-stu-id="6e678-127">Link</span></span>                                          |
|------------|-----------------------------------------------|
| <span data-ttu-id="6e678-128">Excel mobile</span><span class="sxs-lookup"><span data-stu-id="6e678-128">Excel mobile</span></span>      | https://office.live.com/start/Excel.aspx      |
| <span data-ttu-id="6e678-129">Word Mobile</span><span class="sxs-lookup"><span data-stu-id="6e678-129">Word mobile</span></span>       | https://office.live.com/start/Word.aspx       |
| <span data-ttu-id="6e678-130">PowerPoint dla urządzeń przenośnych</span><span class="sxs-lookup"><span data-stu-id="6e678-130">PowerPoint mobile</span></span> | https://office.live.com/start/PowerPoint.aspx |

## <a name="install-apps"></a><span data-ttu-id="6e678-131">Instalowanie aplikacji</span><span class="sxs-lookup"><span data-stu-id="6e678-131">Install apps</span></span>

<span data-ttu-id="6e678-132">Aby pobrać aplikacje, musisz zalogować się przy użyciu konto Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6e678-132">To download apps, you'll need to be signed in with a Microsoft account.</span></span> <span data-ttu-id="6e678-133">Niektóre aplikacje są bezpłatne i można je od razu pobrać.</span><span class="sxs-lookup"><span data-stu-id="6e678-133">Some apps are free and can be downloaded right away.</span></span> <span data-ttu-id="6e678-134">W przypadku aplikacji, które wymagają zakupu, musisz zalogować się do Sklepu przy użyciu konta konto Microsoft mieć prawidłową formę płatności.</span><span class="sxs-lookup"><span data-stu-id="6e678-134">For apps that require a purchase, you must be signed in to the Store with your Microsoft account and have a valid payment method.</span></span>

> [!NOTE]
> <span data-ttu-id="6e678-135">Konto, za pomocą Microsoft Store nie musi być takie samo jak konto, za pomocą których się zalogowano.</span><span class="sxs-lookup"><span data-stu-id="6e678-135">The account you use on Microsoft Store does not have to be the same as the account you are signed in with.</span></span> <span data-ttu-id="6e678-136">Jeśli używasz konta służbowego na urządzeniach HoloLens, może być konieczne zalogowanie się przy użyciu konta osobistego w aplikacji ze sklepu, aby dokonać zakupu.</span><span class="sxs-lookup"><span data-stu-id="6e678-136">If you are using a Work or School account on your HoloLens then you may need to sign in with your personal account in the Store App to make a purchase.</span></span>

> [!TIP]
> <span data-ttu-id="6e678-137">Aby skonfigurować formę płatności, [](https://account.microsoft.com/) przejdź do account.microsoft.com i wybierz pozycję & **płatności** Opcje płatności  >    >  **Dodaj opcję płatności.**</span><span class="sxs-lookup"><span data-stu-id="6e678-137">To set up a payment method, go to [account.microsoft.com](https://account.microsoft.com/) and select **Payment & billing** > **Payment options** > **Add a payment option**.</span></span>

1. <span data-ttu-id="6e678-138">Aby otworzyć menu [ **Start,**](holographic-home.md)wykonaj gest [Start lub](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) [gest Blooma](hololens1-basic-usage.md) na urządzeniach HoloLens (1. generacja).</span><span class="sxs-lookup"><span data-stu-id="6e678-138">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>

1. <span data-ttu-id="6e678-139">Wybierz Microsoft Store aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6e678-139">Select the Microsoft Store app.</span></span> <span data-ttu-id="6e678-140">Po otworeniu aplikacji ze Sklepu:</span><span class="sxs-lookup"><span data-stu-id="6e678-140">After the Store app opens:</span></span>
   1. <span data-ttu-id="6e678-141">Użyj paska wyszukiwania, aby wyszukać aplikacje.</span><span class="sxs-lookup"><span data-stu-id="6e678-141">Use the search bar to look for applications.</span></span> 
   1. <span data-ttu-id="6e678-142">Wybierz podstawowe aplikacje lub aplikacje przeznaczone specjalnie dla urządzenia HoloLens z jednej z wybranych kategorii.</span><span class="sxs-lookup"><span data-stu-id="6e678-142">Select essential apps or apps made specifically for HoloLens from one of the curated categories.</span></span>
   1. <span data-ttu-id="6e678-143">W prawym górnym rogu aplikacji Ze sklepu wybierz przycisk **"...",** a następnie wybierz pozycję **Moja** biblioteka, aby wyświetlić wszystkie wcześniej zakupione aplikacje.</span><span class="sxs-lookup"><span data-stu-id="6e678-143">On the top right of the Store app, select the **"..."** button and then select **My Library** to view any previously purchased apps.</span></span>

1. <span data-ttu-id="6e678-144">Wybierz **pozycję** **Pobierz lub Zainstaluj** na stronie aplikacji (może być wymagany zakup).</span><span class="sxs-lookup"><span data-stu-id="6e678-144">Select **Get** or **Install** on the application's page (a purchase may be required).</span></span>

## <a name="update-apps"></a><span data-ttu-id="6e678-145">Aktualizowanie aplikacji</span><span class="sxs-lookup"><span data-stu-id="6e678-145">Update Apps</span></span>

<span data-ttu-id="6e678-146">Aby zaktualizować aplikację zainstalowaną z Microsoft Store, możesz ją zaktualizować z Microsoft Store aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6e678-146">To update an app you installed from the Microsoft Store, you can update the app from the Microsoft Store app.</span></span> <span data-ttu-id="6e678-147">W przypadku aplikacji zainstalowanych Microsoft Store dla Firm można również aktualizować te aplikacje z Microsoft Store dla Firm.</span><span class="sxs-lookup"><span data-stu-id="6e678-147">For apps installed for the Microsoft Store for Business, you can also update those apps from the Microsoft Store for Business.</span></span> 

1. <span data-ttu-id="6e678-148">Aby otworzyć menu [ **Start,**](holographic-home.md)wykonaj gest [Start lub](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) [gest Blooma](hololens1-basic-usage.md) na urządzeniach HoloLens (1. generacja).</span><span class="sxs-lookup"><span data-stu-id="6e678-148">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>

1. <span data-ttu-id="6e678-149">Wybierz aplikację Ze sklepu.</span><span class="sxs-lookup"><span data-stu-id="6e678-149">Select the Store app.</span></span>

1. <span data-ttu-id="6e678-150">Spójrz w prawym górnym rogu aplikacji Ze sklepu.</span><span class="sxs-lookup"><span data-stu-id="6e678-150">Look to the top right of the Store app.</span></span> 

1. <span data-ttu-id="6e678-151">Wybierz przycisk **"..."** lub "Zobacz więcej".</span><span class="sxs-lookup"><span data-stu-id="6e678-151">Select the **"..."** or “See more” button.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6e678-152">![Microsoft Store zrzut ekranu aplikacji.](images/store-update-1.png)</span><span class="sxs-lookup"><span data-stu-id="6e678-152">![Microsoft Store app screenshot.](images/store-update-1.png)</span></span>

1. <span data-ttu-id="6e678-153">Wybierz **pozycję Pliki do pobrania i aktualizacje.**</span><span class="sxs-lookup"><span data-stu-id="6e678-153">Select **Downloads and updates**.</span></span>
    1. <span data-ttu-id="6e678-154">Jeśli urządzenie wcześniej zidentyfikował aktualizacje, może to być strzałka w dół i liczba reprezentująca oczekujące aktualizacje.</span><span class="sxs-lookup"><span data-stu-id="6e678-154">If your device has previously identified updates, there may be a down arrow and a number that represents pending updates.</span></span>

1. <span data-ttu-id="6e678-155">Wybierz **pozycję Pobierz aktualizacje.**</span><span class="sxs-lookup"><span data-stu-id="6e678-155">Select **Get updates**.</span></span> <span data-ttu-id="6e678-156">Urządzenie będzie teraz wyszukiwać aktualizacje i ustawiać je na pobieranie i instalowanie.</span><span class="sxs-lookup"><span data-stu-id="6e678-156">Your device will now search for updates and set them to download and install.</span></span> 
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6e678-157">![Microsoft Store aplikacji zrzut ekranu przedstawiający pobieranie aktualizacji.](images/store-update-2.png.jpg)</span><span class="sxs-lookup"><span data-stu-id="6e678-157">![Microsoft Store app screenshot of getting updates..](images/store-update-2.png.jpg)</span></span>

> [!NOTE]
> <span data-ttu-id="6e678-158">Jeśli aplikacje na urządzeniu zostały dystrybuowane przez organizację, można je zaktualizować za pomocą tych samych metod zarządzania aplikacjami komercyjnymi.</span><span class="sxs-lookup"><span data-stu-id="6e678-158">If the apps on your device were distributed by your organization they can be updated through the same commercial app management methods.</span></span> <span data-ttu-id="6e678-159">Jeśli dotyczy to Twojej sytuacji, przeczytaj więcej za pośrednictwem [naszego przeglądu wdrażania aplikacji komercyjnych.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6e678-159">If this applies to your situation, read more via our [overview of commercial app deployment.](app-deploy-overview.md)</span></span>
>
> <span data-ttu-id="6e678-160">Jeśli chcesz zaktualizować aplikację niestandardową, która została załadowana w sposób sideloaded lub wdrożona, musisz użyć tej samej metody ze zaktualizowaną wersją aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6e678-160">If you would like to update a custom app that has been sideloaded or deployed, you will need to use the same method with the updated version of your app.</span></span> <span data-ttu-id="6e678-161">Aby dowiedzieć się więcej na temat instalowania i uruchamiania aplikacji niestandardowych, przeczytaj [niestandardowe aplikacje holograficzne](holographic-custom-apps.md).</span><span class="sxs-lookup"><span data-stu-id="6e678-161">To learn more about installing and running custom apps, read [custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="uninstall-apps"></a><span data-ttu-id="6e678-162">Odinstaluj aplikacje</span><span class="sxs-lookup"><span data-stu-id="6e678-162">Uninstall apps</span></span>

<span data-ttu-id="6e678-163">Istnieją trzy sposoby odinstalowywania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6e678-163">There are three ways to uninstall applications.</span></span> <span data-ttu-id="6e678-164">Aplikacje można odinstalować za pośrednictwem Microsoft Store, menu Start lub z ustawień.</span><span class="sxs-lookup"><span data-stu-id="6e678-164">You can uninstall applications through the Microsoft Store, Start menu or from Settings.</span></span> 

> [!WARNING]
> <span data-ttu-id="6e678-165">Nie można odinstalować aplikacji systemowej ani samej Microsoft Store aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6e678-165">You can not uninstall a system app or the Microsoft Store itself.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e678-166">Jeśli urządzenie HoloLens 2 ma wielu użytkowników, musisz być zalogowany jako użytkownik, który zainstalował aplikację, aby ją odinstalować.</span><span class="sxs-lookup"><span data-stu-id="6e678-166">If your HoloLens 2 has multiple users, you must be logged in as the user who installed the app to uninstall it.</span></span> 

### <a name="uninstall-from-the-microsoft-store"></a><span data-ttu-id="6e678-167">Odinstalowywanie z Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="6e678-167">Uninstall from the Microsoft Store</span></span>

<span data-ttu-id="6e678-168">Otwórz Microsoft Store menu **Start,** a następnie wyszukaj aplikację, którą chcesz odinstalować.</span><span class="sxs-lookup"><span data-stu-id="6e678-168">Open the Microsoft Store from the **Start** menu, and then browse for the application you want to uninstall.</span></span>  <span data-ttu-id="6e678-169">Na stronie Sklep każda zainstalowana aplikacja ma przycisk **Odinstaluj.**</span><span class="sxs-lookup"><span data-stu-id="6e678-169">On the Store page, each installed application has an **Uninstall** button.</span></span>

### <a name="uninstall-from-the-start-menu"></a><span data-ttu-id="6e678-170">Odinstalowywanie z menu Start</span><span class="sxs-lookup"><span data-stu-id="6e678-170">Uninstall from the Start menu</span></span>

<span data-ttu-id="6e678-171">W menu **Start** lub na **Wszystkie aplikacje** przejdź do aplikacji.</span><span class="sxs-lookup"><span data-stu-id="6e678-171">On the **Start** menu or in the **All apps** list, browse to the app.</span></span> <span data-ttu-id="6e678-172">Wybieraj i przytrzymaj, aż pojawi się menu, a następnie wybierz pozycję **Odinstaluj**.</span><span class="sxs-lookup"><span data-stu-id="6e678-172">Select and hold until the menu appears, then select **Uninstall**.</span></span>

### <a name="uninstall-from-settings"></a><span data-ttu-id="6e678-173">Odinstalowywanie z ustawień</span><span class="sxs-lookup"><span data-stu-id="6e678-173">Uninstall from Settings</span></span>
<span data-ttu-id="6e678-174">W menu **Start** wybierz pozycję **Ustawienia -> Aplikacje.**</span><span class="sxs-lookup"><span data-stu-id="6e678-174">On the **Start** menu, select **Settings -> Apps.**</span></span> <span data-ttu-id="6e678-175">Znajdź aplikację z listy, wybierz ją, a następnie kliknij przycisk **Odinstaluj.**</span><span class="sxs-lookup"><span data-stu-id="6e678-175">Find the app from the list, select it and then click **Uninstall**.</span></span>

<span data-ttu-id="6e678-176">Jeśli nie możesz odinstalować aplikacji, prosimy o opinię [przy](https://docs.microsoft.com/hololens/hololens-feedback) użyciu Centrum opinii.</span><span class="sxs-lookup"><span data-stu-id="6e678-176">If you are unable to uninstall an app, please file [feedback](https://docs.microsoft.com/hololens/hololens-feedback) using the Feedback Hub.</span></span>
