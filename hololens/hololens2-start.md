---
title: Konfigurowanie urządzenia HoloLens 2
description: Dowiedz się, jak po raz pierwszy skonfigurować urządzenie HoloLens 2 za pośrednictwem sieci Wi-Fi przy użyciu konta Microsoft (MSA) lub Azure Active Directory (AAD).
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 9/17/2019
keywords: Hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: d46deaf4048e6a649345dc1676a7f8b94d3ad2fc
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379770"
---
# <a name="set-up-your-hololens-2"></a><span data-ttu-id="9e326-104">Konfigurowanie urządzenia HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="9e326-104">Set up your HoloLens 2</span></span>

<span data-ttu-id="9e326-105">Przy pierwszym włączeniu urządzenia HoloLens zostaniesz pokierowany przez proces konfigurowania urządzenia, logowania się przy użyciu konta użytkownika i skalibrowania urządzenia HoloLens dla oczu.</span><span class="sxs-lookup"><span data-stu-id="9e326-105">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="9e326-106">Ta sekcja zawiera informacje na temat konfiguracji początkowej urządzenia HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="9e326-106">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="9e326-107">W następnej sekcji dowiesz się, jak pracować z urządzeniem HoloLens i korzystać z hologramów.</span><span class="sxs-lookup"><span data-stu-id="9e326-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="9e326-108">Aby przejść do tego artykułu, zobacz [Wprowadzenie do urządzenia HoloLens 2.](hololens2-basic-usage.md)</span><span class="sxs-lookup"><span data-stu-id="9e326-108">To skip ahead to that article, see [Get started with HoloLens 2](hololens2-basic-usage.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="9e326-109">Przed rozpoczęciem</span><span class="sxs-lookup"><span data-stu-id="9e326-109">Before you start</span></span>

<span data-ttu-id="9e326-110">Przed rozpoczęciem upewnij się, że są dostępne następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="9e326-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="9e326-111">**Połączenie sieciowe**.</span><span class="sxs-lookup"><span data-stu-id="9e326-111">**A network connection**.</span></span> <span data-ttu-id="9e326-112">Aby go skonfigurować, musisz połączyć urządzenie HoloLens z siecią.</span><span class="sxs-lookup"><span data-stu-id="9e326-112">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="9e326-113">Urządzenie HoloLens 2 umożliwia nawiązywanie połączeń za pomocą Wi-Fi lub ethernet (potrzebny jest adapter USB-C-to-Ethernet).</span><span class="sxs-lookup"><span data-stu-id="9e326-113">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="9e326-114">Przy pierwszym połączeniu będzie potrzebna otwarta sieć chroniona hasłem, która nie wymaga przechodzenia do witryny internetowej ani używania certyfikatów do nawiązywania połączenia.</span><span class="sxs-lookup"><span data-stu-id="9e326-114">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="9e326-115">[Dowiedz się więcej o witrynach internetowych, z których korzysta urządzenie HoloLens.](hololens-offline.md)</span><span class="sxs-lookup"><span data-stu-id="9e326-115">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="9e326-116">**W konto Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="9e326-116">**A Microsoft account**.</span></span> <span data-ttu-id="9e326-117">Musisz również zalogować się na urządzeniu HoloLens przy użyciu konto Microsoft (lub przy użyciu konta służbowego, jeśli twoja organizacja jest właścicielem urządzenia).</span><span class="sxs-lookup"><span data-stu-id="9e326-117">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="9e326-118">Jeśli nie masz bezpłatnej konto Microsoft przejdź do account.microsoft.com [i](https://account.microsoft.com) skonfiguruj go bezpłatnie.</span><span class="sxs-lookup"><span data-stu-id="9e326-118">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="9e326-119">**Bezpieczna, dobrze oświetlona przestrzeń bez zagrożeń związanych z trippingiem.**</span><span class="sxs-lookup"><span data-stu-id="9e326-119">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="9e326-120">[Informacje o kondycji i bezpieczeństwie.](https://go.microsoft.com/fwlink/p/?LinkId=746661)</span><span class="sxs-lookup"><span data-stu-id="9e326-120">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="9e326-121">**Opcjonalne akcesoria komfortu,** które są dostępne wraz z urządzeniem HoloLens, aby ułatwić ci wygodne dopasowanie.</span><span class="sxs-lookup"><span data-stu-id="9e326-121">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="9e326-122">[Więcej informacji na temat dopasowania i komfortu.](hololens2-setup.md#adjust-fit)</span><span class="sxs-lookup"><span data-stu-id="9e326-122">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <a name="set-up-windows"></a><span data-ttu-id="9e326-123">Instalowanie systemu Windows</span><span class="sxs-lookup"><span data-stu-id="9e326-123">Set up Windows</span></span>

<span data-ttu-id="9e326-124">Przy pierwszym uruchomieniu urządzenia HoloLens 2 pierwszym zadaniem jest skonfigurowanie systemu Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="9e326-124">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="9e326-125">Po uruchomieniu urządzenia HoloLens usłyszysz muzyka i zobaczysz logo systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="9e326-125">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![Pierwszy ekran podczas pierwszego rozruchu](images/01-magic-moment.png)

<span data-ttu-id="9e326-127">Na urządzeniach HoloLens 2 zostaną opisane następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="9e326-127">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="9e326-128">Wybierz język.</span><span class="sxs-lookup"><span data-stu-id="9e326-128">Select your language.</span></span>

    ![Wybierz język](images/04-language.png)

1. <span data-ttu-id="9e326-130">Wybierz swój region.</span><span class="sxs-lookup"><span data-stu-id="9e326-130">Select your region.</span></span>

    ![Wybierz region](images/05-region.png)

1. <span data-ttu-id="9e326-132">Skalibruj urządzenie HoloLens dla oczu.</span><span class="sxs-lookup"><span data-stu-id="9e326-132">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="9e326-133">Jeśli zdecydujesz się pominąć sekcję, przy następnym logowaniu zostanie wyświetlony monit.</span><span class="sxs-lookup"><span data-stu-id="9e326-133">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span>

    <span data-ttu-id="9e326-134">Aby skalibrować, przyjrzymy się zestawowi celów (nazywanym gemami).</span><span class="sxs-lookup"><span data-stu-id="9e326-134">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="9e326-135">Jest w porządku, jeśli migasz lub zamykasz wzrok podczas odtęchnięcia, ale próbujesz nie zaglądać na inne obiekty w pomieszczeniu lub w przestrzeni fizycznej.</span><span class="sxs-lookup"><span data-stu-id="9e326-135">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="9e326-136">Urządzenie HoloLens używa tego procesu, aby dowiedzieć się więcej o pozycji oka, dzięki czemu może lepiej renderować świat holograficzny.</span><span class="sxs-lookup"><span data-stu-id="9e326-136">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> <span data-ttu-id="9e326-137">Po nachłoeniu hologramy będą wyświetlane prawidłowo nawet wtedy, gdy przyszła na twoją łbę.</span><span class="sxs-lookup"><span data-stu-id="9e326-137">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span>

    <span data-ttu-id="9e326-138">Informacje o lokalizacji są przechowywane lokalnie na urządzeniu i nie są skojarzone z żadnymi informacjami o koncie.</span><span class="sxs-lookup"><span data-stu-id="9e326-138">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="9e326-139">Aby uzyskać więcej informacji, zobacz [Temat Dane i zabezpieczenia dotyczące bezpieczeństwa.](hololens-calibration.md#calibration-data-and-security)</span><span class="sxs-lookup"><span data-stu-id="9e326-139">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

    ![Ekran wyboru kryteriów](images/06-et-corners.png)

1. <span data-ttu-id="9e326-141">Połącz się z Internetem (wybierz Wi-Fi lub połączenie Ethernet.</span><span class="sxs-lookup"><span data-stu-id="9e326-141">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>

     <span data-ttu-id="9e326-142">Urządzenie HoloLens automatycznie ustawia strefę czasową na podstawie informacji uzyskanych Wi-Fi sieci.</span><span class="sxs-lookup"><span data-stu-id="9e326-142">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="9e326-143">Po zakończeniu instalacji możesz zmienić strefę czasową przy użyciu aplikacji Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="9e326-143">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![Łączenie z siecią Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > <span data-ttu-id="9e326-145">Jeśli po zakończeniu kroku Wi-Fi konieczne będzie przełączenie się do innej sieci podczas instalacji, możesz nacisnąć jednocześnie przyciski Volume **Down** i **Power,** aby powrócić do tego kroku, jeśli używasz systemu operacyjnego w wersji z października 2019 r. lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="9e326-145">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="9e326-146">W przypadku wcześniejszych wersji [](hololens-recovery.md) może być konieczne zresetowanie urządzenia lub jego ponowne uruchomienie w lokalizacji, w której sieć Wi-Fi jest dostępna, aby uniemożliwić automatyczne nawiązywanie połączenia.</span><span class="sxs-lookup"><span data-stu-id="9e326-146">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
    > 
    > <span data-ttu-id="9e326-147">Należy również pamiętać, że podczas konfigurowania urządzenia HoloLens istnieje limit czasu poświadczeń, który wynosi dwie minuty.</span><span class="sxs-lookup"><span data-stu-id="9e326-147">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="9e326-148">Nazwę użytkownika/hasło należy wprowadzić w ciągu dwóch minut. W przeciwnym razie pole nazwy użytkownika zostanie automatycznie wyczyszone.</span><span class="sxs-lookup"><span data-stu-id="9e326-148">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="9e326-149">Zaloguj się do konta użytkownika.</span><span class="sxs-lookup"><span data-stu-id="9e326-149">Sign in to your user account.</span></span> <span data-ttu-id="9e326-150">Możesz wybrać pozycję **Moja praca lub szkoła** jest jego właścicielem, a ja jestem **jego właścicielem.**</span><span class="sxs-lookup"><span data-stu-id="9e326-150">You'll choose between **My work or school owns it** and **I own it**.</span></span>

    - <span data-ttu-id="9e326-151">Gdy wybierzesz pozycję My work or school owns it (Moja praca lub szkoła jest jego **właścicielem),** zaloguj się przy użyciu konta usługi Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9e326-151">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="9e326-152">Jeśli Twoja organizacja korzysta z Azure AD — wersja Premium i skonfigurowała automatyczną rejestrację mdm, urządzenie HoloLens automatycznie rejestruje się w funkcji MDM.</span><span class="sxs-lookup"><span data-stu-id="9e326-152">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="9e326-153">Jeśli Twoja organizacja nie używa usługi Azure AD — wersja Premium, automatyczna rejestracja w uciekinie mdm nie jest dostępna.</span><span class="sxs-lookup"><span data-stu-id="9e326-153">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="9e326-154">W takim przypadku należy ręcznie zarejestrować [urządzenie HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)w celu zarządzania urządzeniami .</span><span class="sxs-lookup"><span data-stu-id="9e326-154">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="9e326-155">Wprowadź informacje o koncie organizacyjnym.</span><span class="sxs-lookup"><span data-stu-id="9e326-155">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="9e326-156">Zaakceptuj oświadczenie o ochronie prywatności i umowę licencyjną użytkownika końcowego.</span><span class="sxs-lookup"><span data-stu-id="9e326-156">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="9e326-157">Zaloguj się przy użyciu poświadczeń usługi Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9e326-157">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="9e326-158">Może to spowodować przekierowanie do strony logowania organizacji.</span><span class="sxs-lookup"><span data-stu-id="9e326-158">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="9e326-159">Kontynuuj konfigurowanie urządzenia.</span><span class="sxs-lookup"><span data-stu-id="9e326-159">Continue setting up the device.</span></span>

    - <span data-ttu-id="9e326-160">Gdy wybierzesz **pozycję Jestem właścicielem,** zaloguj się przy użyciu konto Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9e326-160">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="9e326-161">Po zakończeniu konfiguracji możesz ręcznie zarejestrować [urządzenie HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)w u użytkownikach zarządzania urządzeniami .</span><span class="sxs-lookup"><span data-stu-id="9e326-161">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="9e326-162">Wprowadź informacje konto Microsoft użytkownika.</span><span class="sxs-lookup"><span data-stu-id="9e326-162">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="9e326-163">Wprowadź hasło.</span><span class="sxs-lookup"><span data-stu-id="9e326-163">Enter your password.</span></span> <span data-ttu-id="9e326-164">Jeśli Twoja konto Microsoft wymaga [weryfikacji dwuetapowej (2FA),](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)ukończ proces weryfikacji.</span><span class="sxs-lookup"><span data-stu-id="9e326-164">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

    ![Ustawianie użytkownika](images/13-device-owner.png)

1. <span data-ttu-id="9e326-166">Wybierz, czy włączyć mowę na urządzeniach HoloLens 2 i czy wysyłać telemetrię diagnostyczną.</span><span class="sxs-lookup"><span data-stu-id="9e326-166">Select whether to enable speech on HoloLens 2, and whether to send diagnostic telemetry.</span></span>

    ![Włączanie Cortany](images/22-do-more-with-voice.png)

1. <span data-ttu-id="9e326-168">Wybierz poziom telemetrii.</span><span class="sxs-lookup"><span data-stu-id="9e326-168">Select your telemetry level.</span></span> <span data-ttu-id="9e326-169">Jeśli możesz, włącz opcję Pełna telemetria.</span><span class="sxs-lookup"><span data-stu-id="9e326-169">If you can, please enable Full telemetry.</span></span> <span data-ttu-id="9e326-170">Te informacje naprawdę pomagają zespołowi inżynierów urządzenia HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9e326-170">This information really helps the HoloLens engineering team.</span></span>

     ![Poziom telemetrii](images/24-telemetry.png)

1. <span data-ttu-id="9e326-172">Dowiedz się, jak używać gestu uruchamiania na urządzeniach HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="9e326-172">Learn how to use the start gesture on HoloLens 2.</span></span>

     <span data-ttu-id="9e326-173">![Dowiedz się, jak używać gestu uruchamiania, obraz 1 Dowiedz się, jak używać ](images/26-01-startmenu-learning.png) ![ gestu uruchamiania, obraz 2](images/26-02-startmenu-learning.png)</span><span class="sxs-lookup"><span data-stu-id="9e326-173">![Learn how to use the start gesture, image 1](images/26-01-startmenu-learning.png) ![Learn how to use the start gesture, image 2](images/26-02-startmenu-learning.png)</span></span>

<span data-ttu-id="9e326-174">Gratulacje!</span><span class="sxs-lookup"><span data-stu-id="9e326-174">Congratulations!</span></span>  <span data-ttu-id="9e326-175">Konfiguracja jest ukończona i wszystko jest gotowe do użycia urządzenia HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9e326-175">Setup is complete and you're ready to use HoloLens!</span></span>

## <a name="next-steps"></a><span data-ttu-id="9e326-176">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="9e326-176">Next steps</span></span>

1. <span data-ttu-id="9e326-177">Zacznij od razu korzystać z Mixed Reality i nawigować po urządzeniach Windows 10 na urządzeniach HoloLens — zapoznaj się z aplikacją **Porady,** aby uzyskać praktyczne samouczki dotyczące interakcji za pomocą rąk.</span><span class="sxs-lookup"><span data-stu-id="9e326-177">Start interacting right away with Mixed Reality and navigating Windows 10 on your HoloLens - check out the **Tips** app for hands-on tutorials for hand interactions.</span></span> <span data-ttu-id="9e326-178">Użyj gestu uruchamiania, aby przejść do strony Start lub powiedzieć "Przejdź do startu" i wybrać pozycję Porady.</span><span class="sxs-lookup"><span data-stu-id="9e326-178">Use the start gesture to go to Start or say "Go to Start" and select Tips.</span></span>

1. <span data-ttu-id="9e326-179">Kliknij poniżej, aby kontynuować czytanie o urządzeniach HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="9e326-179">Click below to continue reading about getting around HoloLens 2.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9e326-180">Wprowadzenie do urządzenia HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="9e326-180">Get started with HoloLens 2</span></span>](hololens2-basic-usage.md)
