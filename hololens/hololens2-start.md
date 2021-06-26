---
title: Konfigurowanie urządzenia HoloLens 2
description: Dowiedz się, jak skonfigurować urządzenie HoloLens 2 po raz pierwszy za pośrednictwem sieci Wi-Fi przy użyciu konta Microsoft (MSA) lub Azure Active Directory (AAD).
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 6/09/2021
keywords: Hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 0d087037e94bcaed2cd79d9cff77ed3039919a09
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923786"
---
# <a name="set-up-your-hololens-2"></a><span data-ttu-id="53a72-104">Konfigurowanie urządzenia HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="53a72-104">Set up your HoloLens 2</span></span>

<span data-ttu-id="53a72-105">Przy pierwszym włączeniu urządzenia HoloLens zostaniesz pokierowany przez proces konfigurowania urządzenia, logowania się przy użyciu konta użytkownika i skalibrowania urządzenia HoloLens dla twoich oczu.</span><span class="sxs-lookup"><span data-stu-id="53a72-105">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="53a72-106">Ta sekcja zawiera informacje na temat konfiguracji początkowej urządzenia HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="53a72-106">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="53a72-107">W następnej sekcji dowiesz się, jak pracować z urządzeniem HoloLens i korzystać z hologramów.</span><span class="sxs-lookup"><span data-stu-id="53a72-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="53a72-108">Aby przejść do tego artykułu, zobacz [Getting around HoloLens 2 (Poruszanie się po urządzeniach HoloLens 2).](hololens2-basic-usage.md)</span><span class="sxs-lookup"><span data-stu-id="53a72-108">To skip ahead to that article, see [Getting around HoloLens 2](hololens2-basic-usage.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="53a72-109">Przed rozpoczęciem</span><span class="sxs-lookup"><span data-stu-id="53a72-109">Before you start</span></span>

<span data-ttu-id="53a72-110">Przed rozpoczęciem upewnij się, że są dostępne następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="53a72-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="53a72-111">**Połączenie sieciowe**.</span><span class="sxs-lookup"><span data-stu-id="53a72-111">**A network connection**.</span></span> <span data-ttu-id="53a72-112">Aby ją skonfigurować, musisz połączyć urządzenie HoloLens z siecią.</span><span class="sxs-lookup"><span data-stu-id="53a72-112">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="53a72-113">Za pomocą urządzenia HoloLens 2 można nawiązać połączenie za pomocą interfejsu Wi-Fi lub ethernet (potrzebny będzie adapter USB C-to-Ethernet).</span><span class="sxs-lookup"><span data-stu-id="53a72-113">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="53a72-114">Przy pierwszym połączeniu będzie potrzebna otwarta sieć chroniona hasłem, która nie wymaga przechodzenia do witryny internetowej ani używania certyfikatów do nawiązywania połączenia.</span><span class="sxs-lookup"><span data-stu-id="53a72-114">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="53a72-115">[Dowiedz się więcej o witrynach internetowych, z których korzysta urządzenie HoloLens.](hololens-offline.md)</span><span class="sxs-lookup"><span data-stu-id="53a72-115">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="53a72-116">**W konto Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="53a72-116">**A Microsoft account**.</span></span> <span data-ttu-id="53a72-117">Musisz również zalogować się na urządzeniu HoloLens przy użyciu konto Microsoft (lub przy użyciu konta służbowego, jeśli organizacja jest właścicielem urządzenia).</span><span class="sxs-lookup"><span data-stu-id="53a72-117">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="53a72-118">Jeśli nie masz bezpłatnej konto Microsoft, przejdź do account.microsoft.com [i](https://account.microsoft.com) skonfiguruj go bezpłatnie.</span><span class="sxs-lookup"><span data-stu-id="53a72-118">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="53a72-119">**Bezpieczna, dobrze oświetlona przestrzeń bez zagrożeń związanych z trippingiem.**</span><span class="sxs-lookup"><span data-stu-id="53a72-119">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="53a72-120">[Informacje o kondycji i bezpieczeństwie.](https://go.microsoft.com/fwlink/p/?LinkId=746661)</span><span class="sxs-lookup"><span data-stu-id="53a72-120">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="53a72-121">**Opcjonalne akcesoria komfortu,** które są dostępne wraz z urządzeniem HoloLens, aby ułatwić ci wygodne dopasowanie.</span><span class="sxs-lookup"><span data-stu-id="53a72-121">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="53a72-122">[Więcej informacji na temat dopasowania i komfortu.](hololens2-setup.md#adjust-fit)</span><span class="sxs-lookup"><span data-stu-id="53a72-122">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <a name="set-up-windows"></a><span data-ttu-id="53a72-123">Instalowanie systemu Windows</span><span class="sxs-lookup"><span data-stu-id="53a72-123">Set up Windows</span></span>

<span data-ttu-id="53a72-124">Przy pierwszym uruchomieniu urządzenia HoloLens 2 pierwszym zadaniem jest skonfigurowanie systemu Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="53a72-124">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="53a72-125">Po uruchomieniu urządzenia HoloLens usłyszysz muzyka i zobaczysz logo systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="53a72-125">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![Pierwszy ekran podczas pierwszego rozruchu](images/01-magic-moment.png)

<span data-ttu-id="53a72-127">Urządzenie HoloLens 2 pomoże Ci wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="53a72-127">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="53a72-128">Wybierz język.</span><span class="sxs-lookup"><span data-stu-id="53a72-128">Select your language.</span></span>

    ![Wybierz język](images/04-language.png)

1. <span data-ttu-id="53a72-130">Wybierz swój region.</span><span class="sxs-lookup"><span data-stu-id="53a72-130">Select your region.</span></span>

    ![Wybieranie regionu](images/05-region.png)

1. <span data-ttu-id="53a72-132">Skalibruj urządzenie HoloLens dla oczu.</span><span class="sxs-lookup"><span data-stu-id="53a72-132">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="53a72-133">Jeśli zdecydujesz się pominąć przechodzenie, przy następnym logowaniu zostanie wyświetlony monit.</span><span class="sxs-lookup"><span data-stu-id="53a72-133">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span> 

    1. <span data-ttu-id="53a72-134">Najpierw dostosujesz swoją wizję.</span><span class="sxs-lookup"><span data-stu-id="53a72-134">First, you'll adjust your visor.</span></span>
    
        ![Ekran wyboru odwzorowania](images/06-et-corners.png)

    2. <span data-ttu-id="53a72-136">Aby skalibrować, przyjrzymy się zestawowi celów (nazywanym gemami).</span><span class="sxs-lookup"><span data-stu-id="53a72-136">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="53a72-137">Jest w porządku, jeśli migasz lub zamykasz wzrok podczas ciąży, ale nie patrzysz na inne obiekty w pomieszczeniu lub w przestrzeni fizycznej.</span><span class="sxs-lookup"><span data-stu-id="53a72-137">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="53a72-138">Urządzenie HoloLens używa tego procesu, aby dowiedzieć się więcej o pozycji oka, aby lepiej renderować świat holograficzny.</span><span class="sxs-lookup"><span data-stu-id="53a72-138">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> 

        ![Dostosuj się dla twoich oczu](images/07-adjust-eyes.png)

        <span data-ttu-id="53a72-140">Po połyceniu hologramy będą wyświetlane prawidłowo nawet wtedy, gdy wizjer przesuwa się w łb.</span><span class="sxs-lookup"><span data-stu-id="53a72-140">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span> <span data-ttu-id="53a72-141">Informacje o lokalizacji są przechowywane lokalnie na urządzeniu i nie są skojarzone z żadnymi informacjami o koncie.</span><span class="sxs-lookup"><span data-stu-id="53a72-141">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="53a72-142">Aby uzyskać więcej informacji, zobacz [Dane dotyczące pomięć i zabezpieczenia](hololens-calibration.md#calibration-data-and-security).</span><span class="sxs-lookup"><span data-stu-id="53a72-142">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

        ![Ukończenie procesu](images/calibration-complete.png)

1. <span data-ttu-id="53a72-144">Połącz się z Internetem (wybierz Wi-Fi lub połączenie Ethernet).</span><span class="sxs-lookup"><span data-stu-id="53a72-144">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>

     <span data-ttu-id="53a72-145">Urządzenie HoloLens automatycznie ustawia strefę czasową na podstawie informacji uzyskanych Wi-Fi sieci.</span><span class="sxs-lookup"><span data-stu-id="53a72-145">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="53a72-146">Po zakończeniu instalacji możesz zmienić strefę czasową przy użyciu aplikacji Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="53a72-146">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![Łączenie z siecią Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > <span data-ttu-id="53a72-148">Jeśli po zakończeniu kroku Wi-Fi trzeba przełączyć się do innej sieci podczas nadal  w konfiguracji, możesz jednocześnie nacisnąć przyciski Regulacji głośności i Zasilanie, aby powrócić do tego kroku, jeśli używasz systemu operacyjnego w wersji z października 2019 r. lub nowszej. </span><span class="sxs-lookup"><span data-stu-id="53a72-148">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="53a72-149">W przypadku wcześniejszych wersji [](hololens-recovery.md) może być konieczne zresetowanie urządzenia lub ponowne uruchomienie go w lokalizacji, w której sieć Wi-Fi nie jest dostępna, aby uniemożliwić automatyczne nawiązywanie połączenia.</span><span class="sxs-lookup"><span data-stu-id="53a72-149">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
    > 
    > <span data-ttu-id="53a72-150">Należy również pamiętać, że podczas konfigurowania urządzenia HoloLens istnieje limit czasu poświadczeń, który wynosi dwie minuty.</span><span class="sxs-lookup"><span data-stu-id="53a72-150">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="53a72-151">Nazwę użytkownika/hasło należy wprowadzić w ciągu dwóch minut. W przeciwnym razie pole nazwy użytkownika zostanie automatycznie wyczyszone.</span><span class="sxs-lookup"><span data-stu-id="53a72-151">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="53a72-152">Urządzenie HoloLens 2 wyszuka i zastosuje profil rozwiązania Autopilot, jeśli istnieje.</span><span class="sxs-lookup"><span data-stu-id="53a72-152">HoloLens 2 will search and apply an Autopilot profile if one exists.</span></span> <span data-ttu-id="53a72-153">Na tym ekranie nie jest potrzebna żadna akcja.</span><span class="sxs-lookup"><span data-stu-id="53a72-153">No action is needed on this screen.</span></span>
 
    ![Wyszukiwanie profilów rozwiązania Autopilot](images/autopilot-profile-search.png) 

1. <span data-ttu-id="53a72-155">Kliknij **przycisk Akceptuj** na ekranie licencjonowania.</span><span class="sxs-lookup"><span data-stu-id="53a72-155">Click **Accept** on the licensing screen.</span></span>

    ![Umowa licencyjna systemu Windows](images/windows-license-agreement.png)

1. <span data-ttu-id="53a72-157">Zaloguj się do konta użytkownika.</span><span class="sxs-lookup"><span data-stu-id="53a72-157">Sign in to your user account.</span></span> <span data-ttu-id="53a72-158">Wybierz między **właścicielem jest moja praca lub** szkoła, a **właścicielem jest moja .**</span><span class="sxs-lookup"><span data-stu-id="53a72-158">You'll choose between **My work or school owns it** and **I own it**.</span></span>

    - <span data-ttu-id="53a72-159">Po wybraniu opcji **Moja praca lub szkoła jest jego** właścicielem, zaloguj się przy użyciu konta usługi Azure AD.</span><span class="sxs-lookup"><span data-stu-id="53a72-159">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="53a72-160">Jeśli Twoja organizacja korzysta z Azure AD — wersja Premium i skonfigurowała automatyczną rejestrację w uciece MDM, urządzenie HoloLens zostanie automatycznie rejestrowane w funkcji MDM.</span><span class="sxs-lookup"><span data-stu-id="53a72-160">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="53a72-161">Jeśli Twoja organizacja nie używa usługi Azure AD — wersja Premium, automatyczna rejestracja w uciekierach mdm nie jest dostępna.</span><span class="sxs-lookup"><span data-stu-id="53a72-161">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="53a72-162">W takim przypadku należy ręcznie zarejestrować [urządzenie HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)w programie device management .</span><span class="sxs-lookup"><span data-stu-id="53a72-162">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="53a72-163">Wprowadź informacje o koncie organizacyjnym.</span><span class="sxs-lookup"><span data-stu-id="53a72-163">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="53a72-164">Zaakceptuj zasady zachowania poufności informacji i umowę licencyjną użytkownika końcowego.</span><span class="sxs-lookup"><span data-stu-id="53a72-164">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="53a72-165">Zaloguj się przy użyciu poświadczeń usługi Azure AD.</span><span class="sxs-lookup"><span data-stu-id="53a72-165">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="53a72-166">Może to spowodować przekierowanie do strony logowania organizacji.</span><span class="sxs-lookup"><span data-stu-id="53a72-166">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="53a72-167">Kontynuuj konfigurowanie urządzenia.</span><span class="sxs-lookup"><span data-stu-id="53a72-167">Continue setting up the device.</span></span>

    - <span data-ttu-id="53a72-168">Po wybraniu opcji **I own it (Jestem** właścicielem) zaloguj się przy użyciu konto Microsoft.</span><span class="sxs-lookup"><span data-stu-id="53a72-168">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="53a72-169">Po zakończeniu konfiguracji możesz ręcznie [zarejestrować urządzenie HoloLens w u użytkownikach zarządzania urządzeniami.](hololens-enroll-mdm.md#different-ways-to-enroll)</span><span class="sxs-lookup"><span data-stu-id="53a72-169">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="53a72-170">Wprowadź informacje konto Microsoft użytkownika.</span><span class="sxs-lookup"><span data-stu-id="53a72-170">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="53a72-171">Wprowadź hasło.</span><span class="sxs-lookup"><span data-stu-id="53a72-171">Enter your password.</span></span> <span data-ttu-id="53a72-172">Jeśli Twoja konto Microsoft wymaga [weryfikacji dwuetapowej (2FA),](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)ukończ proces weryfikacji.</span><span class="sxs-lookup"><span data-stu-id="53a72-172">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

    ![Ustawianie użytkownika](images/13-device-owner.png)

1. <span data-ttu-id="53a72-174">Skonfiguruj logowanie irysów, wybierając pozycję **Dalej.**</span><span class="sxs-lookup"><span data-stu-id="53a72-174">Setup Iris sign-in by selecting **Next**.</span></span> <span data-ttu-id="53a72-175">Będziesz przechodzić przez proces podobny do oczu.</span><span class="sxs-lookup"><span data-stu-id="53a72-175">You will go through a similar experience to the eye calibration.</span></span> <span data-ttu-id="53a72-176">Po **zakończeniu** skanowania wybierz pozycję Gotowe.</span><span class="sxs-lookup"><span data-stu-id="53a72-176">Select **Done** when the scan is complete.</span></span> <span data-ttu-id="53a72-177">Możesz również wybrać pozycję **Pomiń,** aby pominąć ten krok.</span><span class="sxs-lookup"><span data-stu-id="53a72-177">You may also select **Skip** to bypass this step.</span></span>
    
    <span data-ttu-id="53a72-178">![Ukończenie konfiguracji ](images/setup-iris.png) ![ irysów](images/iris-setup-complete.png)</span><span class="sxs-lookup"><span data-stu-id="53a72-178">![Iris setup](images/setup-iris.png) ![Iris setup completion](images/iris-setup-complete.png)</span></span> 
     
  
1. <span data-ttu-id="53a72-179">Skonfigurujesz numer PIN, aby zalogować się do urządzenia.</span><span class="sxs-lookup"><span data-stu-id="53a72-179">You'll setup a PIN to log into the device.</span></span> <span data-ttu-id="53a72-180">Ten numer PIN jest specyficzny dla urządzenia.</span><span class="sxs-lookup"><span data-stu-id="53a72-180">This PIN is device specific.</span></span> 

    ![Konfigurowanie Windows Hello](images/setup-windows-hello.png)

    ![Konfigurowanie Windows Hello PIN](images/windows-hello-pin.png)

    ![Windows Hello instalacja powiodła się](images/windows-hello-successful.png) 
    
1. <span data-ttu-id="53a72-184">Wybierz, czy włączyć mowę na urządzeniach HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="53a72-184">Select whether to enable speech on HoloLens 2.</span></span>

    ![Włączanie Cortany](images/22-do-more-with-voice.png)

1. <span data-ttu-id="53a72-186">Wybierz, czy włączyć lokalizację na urządzeniach HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="53a72-186">Select whether to enable location on HoloLens 2.</span></span>
    
    ![Włączanie usług lokalizowych](images/setup-location-services.png)

1. <span data-ttu-id="53a72-188">Wybierz poziom telemetrii.</span><span class="sxs-lookup"><span data-stu-id="53a72-188">Select your telemetry level.</span></span> <span data-ttu-id="53a72-189">Jeśli możesz, włącz opcję Opcjonalna telemetria.</span><span class="sxs-lookup"><span data-stu-id="53a72-189">If you can, please enable Optional telemetry.</span></span> <span data-ttu-id="53a72-190">Te informacje naprawdę pomagają zespołowi inżynieryjnemu urządzenia HoloLens.</span><span class="sxs-lookup"><span data-stu-id="53a72-190">This information really helps the HoloLens engineering team.</span></span>

     ![Poziom telemetrii](images/24-telemetry.png)

1. <span data-ttu-id="53a72-192">Dowiedz się, jak używać gestu uruchamiania na urządzeniach HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="53a72-192">Learn how to use the start gesture on HoloLens 2.</span></span>

     ![Dowiedz się, jak używać gestu uruchamiania, obraz 1](images/26-01-startmenu-learning.png)

     ![Dowiedz się, jak używać gestu uruchamiania, obraz 2](images/26-02-startmenu-learning.png)

<span data-ttu-id="53a72-195">Gratulacje!</span><span class="sxs-lookup"><span data-stu-id="53a72-195">Congratulations!</span></span>  <span data-ttu-id="53a72-196">Konfiguracja jest ukończona i wszystko jest gotowe do korzystania z urządzenia HoloLens!</span><span class="sxs-lookup"><span data-stu-id="53a72-196">Setup is complete and you're ready to use HoloLens!</span></span>

## <a name="next-steps"></a><span data-ttu-id="53a72-197">Następne kroki</span><span class="sxs-lookup"><span data-stu-id="53a72-197">Next steps</span></span>

1. <span data-ttu-id="53a72-198">Zacznij od razu korzystać z Mixed Reality i nawigować po Windows 10 na urządzeniach HoloLens — zapoznaj się z aplikacją **Porady,** aby uzyskać praktyczne samouczki dotyczące interakcji za pomocą rąk.</span><span class="sxs-lookup"><span data-stu-id="53a72-198">Start interacting right away with Mixed Reality and navigating Windows 10 on your HoloLens - check out the **Tips** app for hands-on tutorials for hand interactions.</span></span> <span data-ttu-id="53a72-199">Użyj gestu uruchamiania, aby przejść do strony Start lub powiedzieć "Przejdź do startu" i wybrać pozycję Porady.</span><span class="sxs-lookup"><span data-stu-id="53a72-199">Use the start gesture to go to Start or say "Go to Start" and select Tips.</span></span>

1. <span data-ttu-id="53a72-200">Kliknij poniżej, aby kontynuować czytanie o urządzeniach HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="53a72-200">Click below to continue reading about getting around HoloLens 2.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="53a72-201">Więcej informacji o urządzeniu HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="53a72-201">Getting around HoloLens 2</span></span>](hololens2-basic-usage.md)
