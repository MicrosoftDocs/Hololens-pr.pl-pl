---
title: Ponowne uruchamianie, resetowanie lub odzyskiwanie urządzenia HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Jak używać narzędzia do odzyskiwania urządzeń z systemem Windows do flashowania obrazu na urządzeniu HoloLens 1. generacji.
keywords: How-to, reboot, reset, recover, hard reset, soft reset, power cycle, HoloLens, shut down, wdrt, windows device recovery tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f855aa84a347edc85e5b9f02458721778eb2515a
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378319"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="9d5f1-104">Ponowne uruchamianie, resetowanie lub odzyskiwanie urządzenia HoloLens (1. generacja)</span><span class="sxs-lookup"><span data-stu-id="9d5f1-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="9d5f1-105">Jeśli występują problemy z urządzeniem HoloLens, możesz spróbować ponownie uruchomić lub zresetować urządzenie, a nawet zmienić jego ukośnik przy użyciu funkcji odzyskiwania urządzenia.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="9d5f1-106">Ten artykuł przeprowadzi Cię przez zalecane kroki odzyskiwania w kolejności.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="9d5f1-107">Jeśli chcesz odzyskać urządzenie HoloLens 2, zobacz [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery)(Odzyskiwanie urządzenia HoloLens 2), ponieważ ten proces się różni.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="9d5f1-108">Ten artykuł koncentruje się na urządzeniu HoloLens i oprogramowaniu.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="9d5f1-109">Jeśli Twoje hologramy nie wyglądają dobrze, zobacz Zagadnienia dotyczące środowiska **[HoloLens,](hololens-environment-considerations.md)** aby uzyskać informacje o czynnikach, które poprawiają jakość hologramów.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="9d5f1-110">Uruchom ponownie</span><span class="sxs-lookup"><span data-stu-id="9d5f1-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="9d5f1-111">Wykonaj bezpieczne ponowne uruchomienie przy użyciu Cortany</span><span class="sxs-lookup"><span data-stu-id="9d5f1-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="9d5f1-112">Najbezpieczniejszym sposobem ponownego uruchomienia urządzenia HoloLens jest użycie Cortany, która zazwyczaj jest pierwszą rzeczą, którą należy wypróbować, gdy wystąpi problem z urządzeniem HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="9d5f1-113">Cortana nie jest dostępna na wszystkich urządzeniach.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="9d5f1-114">Cortana jest dostępna na wszystkich urządzeniach HoloLens (1. generacji).</span><span class="sxs-lookup"><span data-stu-id="9d5f1-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="9d5f1-115">Cortana jest dostępna na urządzeniach HoloLens 2 w kompilacjach poprzedzających aktualizację systemu Windows Holograpic w wersji 2004.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="9d5f1-116">Włącz urządzenie HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="9d5f1-117">Upewnij się, że użytkownik jest zalogowany i urządzenie nie czeka na odblokowanie hasła.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="9d5f1-118">Powiedz "Hey Cortana, reboot" lub "Hey Cortana, restart".</span><span class="sxs-lookup"><span data-stu-id="9d5f1-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="9d5f1-119">Cortana odpowie i wyświetli monit o potwierdzenie.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="9d5f1-120">Poczekaj na odtwarzanie dźwięku po pytaniu, a następnie powiedz "Yes".</span><span class="sxs-lookup"><span data-stu-id="9d5f1-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="9d5f1-121">Urządzenie zostanie uruchomione ponownie.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="9d5f1-122">Używanie przycisku zasilania w celu bezpiecznego ponownego uruchomienia</span><span class="sxs-lookup"><span data-stu-id="9d5f1-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="9d5f1-123">Jeśli nadal nie możesz ponownie uruchomić urządzenia, spróbuj uruchomić je ponownie przy użyciu **przycisku** zasilania:</span><span class="sxs-lookup"><span data-stu-id="9d5f1-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="9d5f1-124">Naciśnij i przytrzymaj **przycisk zasilania** przez 5 sekund.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="9d5f1-125">Po upływie 1 sekundy wszystkie pięć diod LED będzie się obracać, a następnie wolno wyłączać po kolei od prawej do lewej.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="9d5f1-126">Po 5 sekundach wszystkie diody LED będą wyłączone, co oznacza pomyślne zamknięcie.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="9d5f1-127">Zatrzymaj naciskanie przycisku natychmiast po wyłączeniu wszystkich diod LED.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="9d5f1-128">Poczekaj 1 minutę na zakończenie zamykania.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="9d5f1-129">Zamknięcie może być nadal w toku nawet po wyłączeniu ekranów.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="9d5f1-130">Włącz ponownie urządzenie, naciskając i przytrzymując **przycisk** zasilania przez 1 sekundę.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="9d5f1-131">Wykonaj bezpieczne ponowne uruchomienie przy użyciu Portal urządzeń z systemem Windows</span><span class="sxs-lookup"><span data-stu-id="9d5f1-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="9d5f1-132">W tym procesie urządzenie HoloLens musi zostać skonfigurowane jako urządzenie dewelopera.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="9d5f1-133">Dowiedz się więcej na [Portal urządzeń z systemem Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="9d5f1-133">Learn more at [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="9d5f1-134">Jeśli poprzednia procedura nie zadziałała, spróbuj ponownie uruchomić urządzenie przy [użyciu](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)Portal urządzeń z systemem Windows .</span><span class="sxs-lookup"><span data-stu-id="9d5f1-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="9d5f1-135">W prawym górnym rogu znajdź opcję ponownego uruchomienia lub zamknięcia urządzenia.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="9d5f1-136">Wykonaj niebezpieczne wymuszone ponowne uruchomienie</span><span class="sxs-lookup"><span data-stu-id="9d5f1-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="9d5f1-137">Jeśli poprzednie metody nie uruchomiły ponownie urządzenia HoloLens, wymusz ponowne uruchomienie.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="9d5f1-138">Ta metoda jest odpowiednikiem usuwania i ponownego instalowania baterii.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="9d5f1-139">Jest to niebezpieczne, ponieważ może pozostawić urządzenie w stanie uszkodzenia.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="9d5f1-140">W takim przypadku musisz flashować urządzenie HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="9d5f1-141">Jest to potencjalnie szkodliwy sposób i należy go używać tylko wtedy, gdy wcześniej cytowane metody nie zadziałały.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="9d5f1-142">Naciśnij i przytrzymaj **przycisk zasilania** przez co najmniej 10 sekund.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="9d5f1-143">Można przytrzymać przycisk dłużej niż 10 sekund.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="9d5f1-144">Można bezpiecznie ignorować wszelkie działania diody LED.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="9d5f1-145">Zwolnij przycisk i poczekaj 2–3 sekundy.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="9d5f1-146">Naciśnij i przytrzymaj **przycisk zasilania** przez 1 sekundę.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="9d5f1-147">Jeśli nadal występują problemy,  naciskaj przycisk zasilania przez 4 sekundy, aż wszystkie wskaźniki baterii znikną i ekran przestanie wyświetlać hologramów.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="9d5f1-148">Poczekaj 1 minutę, a następnie ponownie naciśnij **przycisk** zasilania, aby włączyć urządzenie.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="9d5f1-149">Resetowanie do ustawień fabrycznych</span><span class="sxs-lookup"><span data-stu-id="9d5f1-149">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="9d5f1-150">Do zresetowania baterii jest potrzebne co najmniej 40 procent opłat.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-150">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="9d5f1-151">Jeśli nadal występuje problem z urządzeniem HoloLens, spróbuj zresetować go do stanu fabrycznego.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-151">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="9d5f1-152">Ten krok zachowuje zainstalowaną wersję oprogramowania Windows Holographic i przywraca wszystkie inne dane do ustawień fabrycznych.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-152">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="9d5f1-153">Zresetowanie urządzenia spowoduje usunięcie wszystkich danych osobowych, aplikacji i ustawień, w tym informacji o resetowaniu modułu TPM.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-153">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="9d5f1-154">Zresetowanie spowoduje zainstalowanie tylko najnowszej zainstalowanej wersji systemu Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-154">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="9d5f1-155">Należy ponownie wykonać wszystkie kroki inicjowania (skalibrować, połączyć się z siecią Wi-Fi, utworzyć konto użytkownika, pobrać aplikacje itd.).</span><span class="sxs-lookup"><span data-stu-id="9d5f1-155">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="9d5f1-156">Otwórz aplikację Ustawienia, a następnie wybierz pozycję **Zaktualizuj**  >  **odzyskiwanie.**</span><span class="sxs-lookup"><span data-stu-id="9d5f1-156">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="9d5f1-157">Wybierz opcję **Resetuj urządzenie** i przeczytaj komunikat potwierdzający.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="9d5f1-158">Potwierdź zresetowanie.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-158">Confirm the reset.</span></span> <span data-ttu-id="9d5f1-159">Urządzenie zostanie uruchomione ponownie i wyświetli zestaw wirowania koła zębatego oraz pasek postępu.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-159">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="9d5f1-160">Poczekaj około 30 minut na ukończenie tego procesu.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-160">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="9d5f1-161">Gdy wszystko będzie gotowe, urządzenie zostanie ponownie uruchomione w gotowej do pracy.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-161">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="9d5f1-162">Ponowne instalowanie systemu operacyjnego</span><span class="sxs-lookup"><span data-stu-id="9d5f1-162">Reinstall the operating system</span></span>

<span data-ttu-id="9d5f1-163">Jeśli po ponownym uruchomieniu i zresetowaniu urządzenia nadal występuje problem, możesz ponownie zainstalować system operacyjny i oprogramowanie układowe HoloLens za pomocą narzędzia do odzyskiwania na komputerze.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-163">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="9d5f1-164">Dane, których urządzenie HoloLens potrzebuje do zresetowania, są spakowane w pełnej aktualizacji flash (FFU), która jest podobna do pliku ISO, WIM lub VHD.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-164">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="9d5f1-165">Dowiedz się więcej o formatach plików obrazów FFU.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="9d5f1-166">Nowy system operacyjny można zainstalować na urządzeniu HoloLens (1. generacji) przy użyciu narzędzia do odzyskiwania urządzeń z systemem Windows.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-166">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="9d5f1-167">Przed użyciem tego narzędzia sprawdź, czy ponowne uruchomienie lub zresetowanie urządzenia HoloLens rozwiąże problem.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-167">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="9d5f1-168">Proces odzyskiwania może chwilę potrwać.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-168">The recovery process may take a while.</span></span> <span data-ttu-id="9d5f1-169">Po jego zainstalowaniu zostanie zainstalowana najnowsza wersja oprogramowania Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-169">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="9d5f1-170">Aby korzystać z tego narzędzia, potrzebny jest komputer z systemem Windows 10 lub nowszym z co najmniej 4 GB wolnego miejsca.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-170">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="9d5f1-171">Nie można uruchomić tego narzędzia na maszynie wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-171">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="9d5f1-172">Odzyskiwanie urządzenia HoloLens</span><span class="sxs-lookup"><span data-stu-id="9d5f1-172">Recover your HoloLens</span></span>

1. <span data-ttu-id="9d5f1-173">Pobierz i zainstaluj narzędzie [do odzyskiwania urządzeń z systemem Windows](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) na komputerze.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="9d5f1-174">Podłącz urządzenie HoloLens (1. generacja) do komputera przy użyciu kabla Micro USB, który jest podłączony do urządzenia HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-174">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="9d5f1-175">Otwórz narzędzie do odzyskiwania urządzeń z systemem Windows i postępuj zgodnie z instrukcjami.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-175">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="9d5f1-176">Jeśli urządzenie HoloLens (1. generacja) nie zostanie wykryte automatycznie, wybierz pozycję **Moje urządzenie nie zostało wykryte.**</span><span class="sxs-lookup"><span data-stu-id="9d5f1-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="9d5f1-177">Następnie postępuj zgodnie z instrukcjami, aby przełożyć urządzenie w tryb odzyskiwania.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-177">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="9d5f1-178">Tryb ręcznego flashowania</span><span class="sxs-lookup"><span data-stu-id="9d5f1-178">Manual flashing mode</span></span>

<span data-ttu-id="9d5f1-179">Jeśli urządzenie nie zostanie wykryte, wykonaj następujące kroki, aby przełożyć urządzenie w tryb flashowania:</span><span class="sxs-lookup"><span data-stu-id="9d5f1-179">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="9d5f1-180">Odłącz urządzenie od dowolnego źródła zasilania.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-180">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="9d5f1-181">Jeśli urządzenie jest wł., przytrzymaj przycisk zasilania **do** momentu całkowitego wyłączenia.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-181">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="9d5f1-182">Przytrzymaj przycisk **regulacji głośności** i naciśnij na krótko **przycisk** zasilania.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-182">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="9d5f1-183">Urządzenie powinno uruchamiać się i wyświetlać tylko środkową diodę LED.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-183">The device should start and display only the middle LED.</span></span>
3. <span data-ttu-id="9d5f1-184">Podłącz urządzenie do komputera.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-184">Plug the device into your PC.</span></span>
4. <span data-ttu-id="9d5f1-185">Otwórz narzędzie do odzyskiwania urządzeń z systemem Windows.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-185">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="9d5f1-186">Wybierz **pozycję Moje urządzenie nie zostało wykryte,** a następnie pozycję **HoloLens.**</span><span class="sxs-lookup"><span data-stu-id="9d5f1-186">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="9d5f1-187">Postępuj zgodnie z instrukcjami, aby odzyskać urządzenie.</span><span class="sxs-lookup"><span data-stu-id="9d5f1-187">Follow the instructions to recover your device.</span></span>
