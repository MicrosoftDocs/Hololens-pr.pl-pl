---
title: Ponowne uruchamianie, resetowanie lub odzyskiwanie HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Jak za pomocą Windows odzyskiwania urządzenia flashować obraz do HoloLens 1. generacji.
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
ms.openlocfilehash: 4840535030cc81f222cb25357474f1c751426e91
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635232"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="1bddc-104">Ponowne uruchamianie, resetowanie lub odzyskiwanie HoloLens (1. generacja)</span><span class="sxs-lookup"><span data-stu-id="1bddc-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="1bddc-105">Jeśli występują problemy z usługą HoloLens, możesz spróbować ponownie uruchomić lub zresetować urządzenie, a nawet zmienić jego ukośnik przy użyciu funkcji odzyskiwania urządzenia.</span><span class="sxs-lookup"><span data-stu-id="1bddc-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="1bddc-106">Ten artykuł przeprowadzi Cię przez zalecane kroki odzyskiwania w kolejności.</span><span class="sxs-lookup"><span data-stu-id="1bddc-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="1bddc-107">Jeśli chcesz odzyskać dane z HoloLens 2, zobacz [Recovering a HoloLens 2](hololens-recovery.md), as that process differs (Odzyskiwanie HoloLens 2), ponieważ ten proces się różni.</span><span class="sxs-lookup"><span data-stu-id="1bddc-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](hololens-recovery.md), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="1bddc-108">Ten artykuł koncentruje się na HoloLens i oprogramowania.</span><span class="sxs-lookup"><span data-stu-id="1bddc-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="1bddc-109">Jeśli Twoje hologramy nie wyglądają dobrze, zobacz **[HoloLens uwagi](hololens-environment-considerations.md)** dotyczące środowiska, aby uzyskać informacje o czynnikach, które poprawiają jakość hologramów.</span><span class="sxs-lookup"><span data-stu-id="1bddc-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="1bddc-110">Uruchom ponownie</span><span class="sxs-lookup"><span data-stu-id="1bddc-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="1bddc-111">Wykonaj bezpieczne ponowne uruchomienie przy użyciu Cortana</span><span class="sxs-lookup"><span data-stu-id="1bddc-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="1bddc-112">Najbezpieczniejszym sposobem ponownego uruchomienia HoloLens jest użycie usługi Cortana, która zazwyczaj jest pierwszą rzeczą, którą należy wypróbować, gdy wystąpi problem z HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1bddc-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="1bddc-113">Cortana nie jest dostępna na wszystkich urządzeniach.</span><span class="sxs-lookup"><span data-stu-id="1bddc-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="1bddc-114">Cortana jest dostępna na wszystkich HoloLens (1. generacji).</span><span class="sxs-lookup"><span data-stu-id="1bddc-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="1bddc-115">Cortana jest dostępna na HoloLens 2 kompilacjach przed aktualizacją Windows Holograpic w wersji 2004.</span><span class="sxs-lookup"><span data-stu-id="1bddc-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="1bddc-116">Włącz swoje HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1bddc-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="1bddc-117">Upewnij się, że użytkownik jest zalogowany i urządzenie nie czeka na odblokowanie hasła.</span><span class="sxs-lookup"><span data-stu-id="1bddc-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="1bddc-118">Powiedz "Hey Cortana, reboot" lub "Hej, Cortana, restart".</span><span class="sxs-lookup"><span data-stu-id="1bddc-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="1bddc-119">Cortana odpowie i wyświetli monit o potwierdzenie.</span><span class="sxs-lookup"><span data-stu-id="1bddc-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="1bddc-120">Poczekaj na odtwarzanie dźwięku po pytaniu, a następnie powiedz "Yes".</span><span class="sxs-lookup"><span data-stu-id="1bddc-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="1bddc-121">Urządzenie zostanie uruchomione ponownie.</span><span class="sxs-lookup"><span data-stu-id="1bddc-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="1bddc-122">Używanie przycisku zasilania w celu bezpiecznego ponownego uruchomienia</span><span class="sxs-lookup"><span data-stu-id="1bddc-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="1bddc-123">Jeśli nadal nie możesz ponownie uruchomić urządzenia, spróbuj uruchomić je ponownie przy użyciu **przycisku** zasilania:</span><span class="sxs-lookup"><span data-stu-id="1bddc-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="1bddc-124">Naciśnij i przytrzymaj **przycisk zasilania** przez 5 sekund.</span><span class="sxs-lookup"><span data-stu-id="1bddc-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="1bddc-125">Po upływie 1 sekundy wszystkie pięć diod LED będzie się obracać, a następnie wolno wyłączać po kolei od prawej do lewej.</span><span class="sxs-lookup"><span data-stu-id="1bddc-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="1bddc-126">Po 5 sekundach wszystkie diody LED będą wyłączone, co oznacza pomyślne zamknięcie.</span><span class="sxs-lookup"><span data-stu-id="1bddc-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="1bddc-127">Zatrzymaj naciskanie przycisku natychmiast po wyłączeniu wszystkich diod LED.</span><span class="sxs-lookup"><span data-stu-id="1bddc-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="1bddc-128">Poczekaj 1 minutę na zakończenie zamykania.</span><span class="sxs-lookup"><span data-stu-id="1bddc-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="1bddc-129">Zamknięcie może być nadal w toku nawet po wyłączeniu ekranów.</span><span class="sxs-lookup"><span data-stu-id="1bddc-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="1bddc-130">Włącz ponownie urządzenie, naciskając i przytrzymując **przycisk** zasilania przez 1 sekundę.</span><span class="sxs-lookup"><span data-stu-id="1bddc-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="1bddc-131">Wykonaj bezpieczne ponowne uruchomienie przy użyciu Windows Portal urządzeń</span><span class="sxs-lookup"><span data-stu-id="1bddc-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="1bddc-132">W tym procesie HoloLens należy skonfigurować jako urządzenie dewelopera.</span><span class="sxs-lookup"><span data-stu-id="1bddc-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="1bddc-133">Dowiedz się więcej na [Windows Portal urządzeń](/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="1bddc-133">Learn more at [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="1bddc-134">Jeśli poprzednia procedura nie zadziałała, spróbuj ponownie uruchomić urządzenie przy użyciu [Windows Portal urządzeń](/windows/mixed-reality/using-the-windows-device-portal).</span><span class="sxs-lookup"><span data-stu-id="1bddc-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="1bddc-135">W prawym górnym rogu znajdź opcję ponownego uruchomienia lub zamknięcia urządzenia.</span><span class="sxs-lookup"><span data-stu-id="1bddc-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="1bddc-136">Wykonaj niebezpieczne wymuszone ponowne uruchomienie</span><span class="sxs-lookup"><span data-stu-id="1bddc-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="1bddc-137">Jeśli poprzednie metody nie uruchomiły ponownie twojego HoloLens, wymusz ponowne uruchomienie.</span><span class="sxs-lookup"><span data-stu-id="1bddc-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="1bddc-138">Ta metoda jest odpowiednikiem usuwania i ponownego instalowania baterii.</span><span class="sxs-lookup"><span data-stu-id="1bddc-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="1bddc-139">Jest to niebezpieczne, ponieważ może pozostawić urządzenie w stanie uszkodzenia.</span><span class="sxs-lookup"><span data-stu-id="1bddc-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="1bddc-140">W takim przypadku musisz flashować dane HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1bddc-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="1bddc-141">Jest to potencjalnie szkodliwy sposób i należy go używać tylko wtedy, gdy wcześniej cytowane metody nie zadziałały.</span><span class="sxs-lookup"><span data-stu-id="1bddc-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="1bddc-142">Naciśnij i przytrzymaj **przycisk zasilania** przez co najmniej 10 sekund.</span><span class="sxs-lookup"><span data-stu-id="1bddc-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="1bddc-143">Można przytrzymać przycisk dłużej niż 10 sekund.</span><span class="sxs-lookup"><span data-stu-id="1bddc-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="1bddc-144">Można bezpiecznie ignorować wszelkie działania diody LED.</span><span class="sxs-lookup"><span data-stu-id="1bddc-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="1bddc-145">Zwolnij przycisk i poczekaj 2–3 sekundy.</span><span class="sxs-lookup"><span data-stu-id="1bddc-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="1bddc-146">Naciśnij i przytrzymaj **przycisk zasilania** przez 1 sekundę.</span><span class="sxs-lookup"><span data-stu-id="1bddc-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="1bddc-147">Jeśli nadal występują problemy,  naciskaj przycisk zasilania przez 4 sekundy, aż wszystkie wskaźniki baterii znikną i ekran przestanie wyświetlać hologramów.</span><span class="sxs-lookup"><span data-stu-id="1bddc-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="1bddc-148">Poczekaj 1 minutę, a następnie ponownie naciśnij **przycisk** zasilania, aby włączyć urządzenie.</span><span class="sxs-lookup"><span data-stu-id="1bddc-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="1bddc-149">Wstecz do poprzedniej wersji — HoloLens (1. generacja)</span><span class="sxs-lookup"><span data-stu-id="1bddc-149">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="1bddc-150">W niektórych przypadkach może być konieczne powrót do poprzedniej wersji HoloLens oprogramowania.</span><span class="sxs-lookup"><span data-stu-id="1bddc-150">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="1bddc-151">Można to zrobić przy użyciu narzędzia Windows Device Recovery, aby zresetować HoloLens do starszej wersji.</span><span class="sxs-lookup"><span data-stu-id="1bddc-151">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="1bddc-152">Powrót do wcześniejszej wersji powoduje usunięcie osobistych plików i ustawień.</span><span class="sxs-lookup"><span data-stu-id="1bddc-152">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="1bddc-153">Aby wrócić do poprzedniej wersji HoloLens 1, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="1bddc-153">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="1bddc-154">Upewnij się, że nie masz żadnych telefonów ani urządzeń Windows podłączonych do komputera.</span><span class="sxs-lookup"><span data-stu-id="1bddc-154">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="1bddc-155">Na komputerze pobierz narzędzie [Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379)</span><span class="sxs-lookup"><span data-stu-id="1bddc-155">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="1bddc-156">Pobierz pakiet [odzyskiwania HoloLens Anniversary Update.](https://aka.ms/hololensrecovery)</span><span class="sxs-lookup"><span data-stu-id="1bddc-156">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="1bddc-157">Po zakończeniu pobierania otwórz **Eksploratora plików**—  >  **pliki do pobrania.**</span><span class="sxs-lookup"><span data-stu-id="1bddc-157">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="1bddc-158">Kliknij prawym przyciskiem myszy właśnie pobrany folder, a następnie wybierz polecenie **Wyodrębnij wszystkie** wyodrębnij,  >   aby go rozpakować.</span><span class="sxs-lookup"><span data-stu-id="1bddc-158">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="1bddc-159">Połączenie urządzenie HoloLens do komputera przy użyciu kabla mikro USB, który został do niego podłączony.</span><span class="sxs-lookup"><span data-stu-id="1bddc-159">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="1bddc-160">(Nawet jeśli używasz innych kabli do łączenia urządzenia HoloLens, ten z nich działa najlepiej).</span><span class="sxs-lookup"><span data-stu-id="1bddc-160">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="1bddc-161">Program WDRT automatycznie wykryje HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1bddc-161">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="1bddc-162">Wybierz **kafelek Microsoft HoloLens** aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1bddc-162">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="1bddc-163">Na następnym ekranie wybierz opcję **Ręczne wybieranie** pakietu i wybierz plik instalacyjny zawarty w folderze rozpakowany w kroku 4.</span><span class="sxs-lookup"><span data-stu-id="1bddc-163">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="1bddc-164">(Poszukaj pliku z rozszerzeniem ffu).</span><span class="sxs-lookup"><span data-stu-id="1bddc-164">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="1bddc-165">Wybierz **pozycję Zainstaluj oprogramowanie** i postępuj zgodnie z instrukcjami.</span><span class="sxs-lookup"><span data-stu-id="1bddc-165">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="1bddc-166">Jeśli program WDRT nie wykryje twojego HoloLens, spróbuj ponownie uruchomić komputer.</span><span class="sxs-lookup"><span data-stu-id="1bddc-166">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="1bddc-167">Jeśli to nie zadziała, wybierz pozycję **Moje urządzenie** nie zostało wykryte, wybierz pozycję Microsoft HoloLens **,** a następnie postępuj zgodnie z instrukcjami.</span><span class="sxs-lookup"><span data-stu-id="1bddc-167">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="1bddc-168">Resetowanie do ustawień fabrycznych</span><span class="sxs-lookup"><span data-stu-id="1bddc-168">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="1bddc-169">Do zresetowania baterii jest potrzebne co najmniej 40 procent opłat.</span><span class="sxs-lookup"><span data-stu-id="1bddc-169">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="1bddc-170">Jeśli twój HoloLens nadal ma problem, spróbuj zresetować go do stanu fabrycznego.</span><span class="sxs-lookup"><span data-stu-id="1bddc-170">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="1bddc-171">Ten krok zachowuje wersję zainstalowanego Windows Holographic i przywraca wszystkie inne dane do ustawień fabrycznych.</span><span class="sxs-lookup"><span data-stu-id="1bddc-171">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="1bddc-172">Zresetowanie urządzenia spowoduje usunięcie wszystkich danych osobowych, aplikacji i ustawień, w tym informacji o resetowaniu modułu TPM.</span><span class="sxs-lookup"><span data-stu-id="1bddc-172">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="1bddc-173">Zresetowanie spowoduje zainstalowanie tylko najnowszej zainstalowanej wersji systemu Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="1bddc-173">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="1bddc-174">Należy ponownie wykonać wszystkie kroki inicjowania (skalibrować, połączyć się z siecią Wi-Fi, utworzyć konto użytkownika, pobrać aplikacje itd.).</span><span class="sxs-lookup"><span data-stu-id="1bddc-174">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="1bddc-175">Otwórz aplikację Ustawienia, a następnie wybierz pozycję **Zaktualizuj**  >  **odzyskiwanie.**</span><span class="sxs-lookup"><span data-stu-id="1bddc-175">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="1bddc-176">Wybierz opcję **Resetuj urządzenie** i przeczytaj komunikat potwierdzający.</span><span class="sxs-lookup"><span data-stu-id="1bddc-176">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="1bddc-177">Potwierdź zresetowanie.</span><span class="sxs-lookup"><span data-stu-id="1bddc-177">Confirm the reset.</span></span> <span data-ttu-id="1bddc-178">Urządzenie zostanie uruchomione ponownie i wyświetli zestaw wirowania koła zębatego oraz pasek postępu.</span><span class="sxs-lookup"><span data-stu-id="1bddc-178">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="1bddc-179">Poczekaj około 30 minut na ukończenie tego procesu.</span><span class="sxs-lookup"><span data-stu-id="1bddc-179">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="1bddc-180">Gdy wszystko będzie gotowe, urządzenie zostanie ponownie uruchomione w gotowej do pracy.</span><span class="sxs-lookup"><span data-stu-id="1bddc-180">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="1bddc-181">Ponowne instalowanie systemu operacyjnego</span><span class="sxs-lookup"><span data-stu-id="1bddc-181">Reinstall the operating system</span></span>

<span data-ttu-id="1bddc-182">Jeśli po ponownym uruchomieniu i zresetowaniu urządzenia nadal występuje problem, możesz użyć narzędzia do odzyskiwania na komputerze, aby ponownie zainstalować HoloLens systemu operacyjnego i oprogramowania układowego.</span><span class="sxs-lookup"><span data-stu-id="1bddc-182">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="1bddc-183">Dane, które HoloLens do zresetowania, są spakowane w pełnej aktualizacji flash (FFU), która jest podobna do pliku ISO, WIM lub VHD.</span><span class="sxs-lookup"><span data-stu-id="1bddc-183">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="1bddc-184">Dowiedz się więcej o formatach plików obrazów FFU.</span><span class="sxs-lookup"><span data-stu-id="1bddc-184">Learn about FFU image file formats.</span></span>](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="1bddc-185">Nowy system operacyjny można zainstalować na komputerze HoloLens (1. generacji) przy użyciu narzędzia Windows Device Recovery.</span><span class="sxs-lookup"><span data-stu-id="1bddc-185">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="1bddc-186">Przed użyciem tego narzędzia sprawdź, czy ponowne uruchomienie lub zresetowanie HoloLens rozwiązało problem.</span><span class="sxs-lookup"><span data-stu-id="1bddc-186">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="1bddc-187">Proces odzyskiwania może chwilę potrwać.</span><span class="sxs-lookup"><span data-stu-id="1bddc-187">The recovery process may take a while.</span></span> <span data-ttu-id="1bddc-188">Po jego zainstalowaniu zostanie zainstalowana najnowsza wersja Windows Holographic.</span><span class="sxs-lookup"><span data-stu-id="1bddc-188">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="1bddc-189">Aby korzystać z tego narzędzia, potrzebny jest komputer z systemem Windows 10 lub nowszym z co najmniej 4 GB wolnego miejsca.</span><span class="sxs-lookup"><span data-stu-id="1bddc-189">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="1bddc-190">Nie można uruchomić tego narzędzia na maszynie wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="1bddc-190">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="1bddc-191">Odzyskiwanie HoloLens</span><span class="sxs-lookup"><span data-stu-id="1bddc-191">Recover your HoloLens</span></span>

1. <span data-ttu-id="1bddc-192">Pobierz i zainstaluj [Windows odzyskiwania urządzenia](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) na komputerze.</span><span class="sxs-lookup"><span data-stu-id="1bddc-192">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="1bddc-193">Połączenie HoloLens (1. generacji) do komputera przy użyciu kabla Micro USB, który jest podłączony do urządzenia HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1bddc-193">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="1bddc-194">Otwórz narzędzie Windows Device Recovery Tool i postępuj zgodnie z instrukcjami.</span><span class="sxs-lookup"><span data-stu-id="1bddc-194">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="1bddc-195">Jeśli HoloLens (1. generacja) nie zostanie wykryta automatycznie, wybierz pozycję **Moje urządzenie nie zostało wykryte.**</span><span class="sxs-lookup"><span data-stu-id="1bddc-195">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="1bddc-196">Następnie postępuj zgodnie z instrukcjami, aby przełożyć urządzenie w tryb odzyskiwania.</span><span class="sxs-lookup"><span data-stu-id="1bddc-196">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="1bddc-197">Tryb ręcznego flashowania</span><span class="sxs-lookup"><span data-stu-id="1bddc-197">Manual flashing mode</span></span>

<span data-ttu-id="1bddc-198">Jeśli urządzenie nie zostanie wykryte, wykonaj następujące kroki, aby przełożyć urządzenie w tryb flashowania:</span><span class="sxs-lookup"><span data-stu-id="1bddc-198">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="1bddc-199">Odłącz urządzenie od dowolnego źródła zasilania.</span><span class="sxs-lookup"><span data-stu-id="1bddc-199">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="1bddc-200">Jeśli urządzenie jest wł., przytrzymaj przycisk zasilania **do** momentu całkowitego wyłączenia.</span><span class="sxs-lookup"><span data-stu-id="1bddc-200">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="1bddc-201">Przytrzymaj przycisk **regulacji głośności** i naciśnij na krótko **przycisk** zasilania.</span><span class="sxs-lookup"><span data-stu-id="1bddc-201">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="1bddc-202">Urządzenie powinno uruchamiać się i wyświetlać tylko środkową diodę LED.</span><span class="sxs-lookup"><span data-stu-id="1bddc-202">The device should start and display only the middle LED.</span></span>
3. <span data-ttu-id="1bddc-203">Podłącz urządzenie do komputera.</span><span class="sxs-lookup"><span data-stu-id="1bddc-203">Plug the device into your PC.</span></span>
4. <span data-ttu-id="1bddc-204">Otwórz narzędzie Windows odzyskiwania urządzeń.</span><span class="sxs-lookup"><span data-stu-id="1bddc-204">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="1bddc-205">Wybierz **pozycję Moje urządzenie nie zostało wykryte,** a następnie wybierz **HoloLens**.</span><span class="sxs-lookup"><span data-stu-id="1bddc-205">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="1bddc-206">Postępuj zgodnie z instrukcjami, aby odzyskać urządzenie.</span><span class="sxs-lookup"><span data-stu-id="1bddc-206">Follow the instructions to recover your device.</span></span>
