---
title: Ponowne uruchamianie, resetowanie lub odzyskiwanie urządzenia HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Jak za pomocą narzędzia Advanced Recovery Companion flashować obraz na urządzeniaCh HoloLens 2.
keywords: how-to, reboot, reset, recover, hard reset, soft reset, power cycle, HoloLens, shut down, arc, advanced recovery companion
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: be33eb5d06ee7d63f1f598792ff75605b0eb4424
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923639"
---
# <a name="restart-reset-or-recover-hololens-2"></a><span data-ttu-id="16564-104">Ponowne uruchamianie, resetowanie lub odzyskiwanie urządzenia HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="16564-104">Restart, reset, or recover HoloLens 2</span></span>

>[!IMPORTANT]
> <span data-ttu-id="16564-105">Przed rozpoczęciem procedury rozwiązywania problemów upewnij się, że urządzenie jest obciążane od **20 do 40%** pojemności baterii, jeśli jest to możliwe.</span><span class="sxs-lookup"><span data-stu-id="16564-105">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="16564-106">Wskaźniki [naładowania baterii znajdujące](hololens2-setup.md#lights-that-indicate-the-battery-level) się pod przyciskiem zasilania to szybki sposób na sprawdzenie pojemności baterii bez logowania się do urządzenia.</span><span class="sxs-lookup"><span data-stu-id="16564-106">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<span data-ttu-id="16564-107">Użyj [kabla USB typu C,](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) który jest podłączony do urządzenia HoloLens 2, ponieważ jest to najlepszy sposób ładowania urządzenia.</span><span class="sxs-lookup"><span data-stu-id="16564-107">Use the [charger and the USB Type-C cable](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) that came with the HoloLens 2 as that is the best way to charge your device.</span></span> <span data-ttu-id="16564-108">Zasilacz dostarcza moc 18W (9V przy 2A).</span><span class="sxs-lookup"><span data-stu-id="16564-108">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="16564-109">Korzystając z dostarczonego urządzenia HoloLens 2, urządzenie HoloLens 2 może ładować baterii do pełnej baterii w mniej niż 65 minut, gdy urządzenie jest w stanie wstrzymania.</span><span class="sxs-lookup"><span data-stu-id="16564-109">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="16564-110">Jeśli te akcesoria nie są dostępne, upewnij się, że dostępne akcesoria mogą obsługiwać moc co najmniej 15 W.</span><span class="sxs-lookup"><span data-stu-id="16564-110">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="16564-111">Jeśli to możliwe, unikaj używania komputera do ładowania urządzenia za pośrednictwem portu USB, co działa wolno.</span><span class="sxs-lookup"><span data-stu-id="16564-111">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="16564-112">Jeśli urządzenie jest prawidłowo uruchomione, istnieją trzy sposoby sprawdzania poziomu naładowania baterii:</span><span class="sxs-lookup"><span data-stu-id="16564-112">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="16564-113">Z menu głównego interfejsu użytkownika urządzenia HoloLens.</span><span class="sxs-lookup"><span data-stu-id="16564-113">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="16564-114">Wyświetl diodę LED w pobliżu przycisku zasilania (w przypadku 40-procentowego obciążenia powinny być na przykład co najmniej dwie ciągłe diody LED).</span><span class="sxs-lookup"><span data-stu-id="16564-114">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDs).</span></span>
    - <span data-ttu-id="16564-115">Gdy urządzenie jest ładowane, wskaźnik baterii jest oświetlany, aby wskazać bieżący poziom naładowania.</span><span class="sxs-lookup"><span data-stu-id="16564-115">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="16564-116">Ostatnie światło będzie zanikać i zanikać, aby wskazać aktywne ładowanie.</span><span class="sxs-lookup"><span data-stu-id="16564-116">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="16564-117">Gdy urządzenie HoloLens jest wł., wskaźnik baterii wyświetla poziom naładowania baterii w pięciu przyrostach.</span><span class="sxs-lookup"><span data-stu-id="16564-117">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="16564-118">Gdy tylko jedno z pięciu światła jest w zasilania, poziom naładowania baterii jest poniżej 20 procent.</span><span class="sxs-lookup"><span data-stu-id="16564-118">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="16564-119">Jeśli poziom naładowania baterii jest krytycznie niski i spróbujesz włączyć urządzenie, jedno światło miga przez krótki czas, a następnie wychodzie.</span><span class="sxs-lookup"><span data-stu-id="16564-119">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="16564-120">Na komputerze hosta otwórz **Eksplorator plików** i poszukaj urządzenia HoloLens 2 po lewej stronie w obszarze Ten **komputer.**</span><span class="sxs-lookup"><span data-stu-id="16564-120">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="16564-121">Kliknij prawym przyciskiem myszy urządzenie, a następnie wybierz pozycję **Właściwości.**</span><span class="sxs-lookup"><span data-stu-id="16564-121">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="16564-122">Zostanie wyświetlone okno dialogowe z poziomem naładowania baterii.</span><span class="sxs-lookup"><span data-stu-id="16564-122">A dialog box will show the battery charge level.</span></span>

   ![Ekran właściwości urządzenia HoloLens 2 pokazuje poziom zmiany baterii](images/ResetRecovery2.png)

<span data-ttu-id="16564-124">Jeśli urządzenie nie może uruchomić się w menu startowym, zwróć uwagę na wygląd diody LED i wyliczenie urządzenia na komputerze hosta.</span><span class="sxs-lookup"><span data-stu-id="16564-124">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="16564-125">Następnie postępuj zgodnie z [przewodnikiem rozwiązywania problemów.](hololens-troubleshooting.md)</span><span class="sxs-lookup"><span data-stu-id="16564-125">Then follow the [troubleshooting guide](hololens-troubleshooting.md).</span></span> <span data-ttu-id="16564-126">Jeśli stan urządzenia nie pasuje do żadnego ze stanów wymienionych w przewodniku rozwiązywania problemów, wykonaj procedurę resetowania na czas z urządzeniem podłączonym do źródła zasilania, a nie z komputerem hosta. [](hololens-recovery.md#hard-reset-procedure)</span><span class="sxs-lookup"><span data-stu-id="16564-126">If the state of the device doesn't match any of the states listed in the troubleshooting guide, perform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="16564-127">Zaczekaj co najmniej godzinę na obciążenie urządzenia.</span><span class="sxs-lookup"><span data-stu-id="16564-127">Wait at least one hour for the device to charge.</span></span>

## <a name="reset-the-device"></a><span data-ttu-id="16564-128">Resetowanie urządzenia</span><span class="sxs-lookup"><span data-stu-id="16564-128">Reset the device</span></span>

<span data-ttu-id="16564-129">W pewnych okolicznościach może być trzeba ręcznie zresetować urządzenie bez korzystania z interfejsu użytkownika oprogramowania.</span><span class="sxs-lookup"><span data-stu-id="16564-129">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <a name="standard-procedure"></a><span data-ttu-id="16564-130">Standardowa procedura</span><span class="sxs-lookup"><span data-stu-id="16564-130">Standard procedure</span></span>

1. <span data-ttu-id="16564-131">Odłącz kabel typu C, aby odłączyć urządzenie od zasilacza lub komputera hosta.</span><span class="sxs-lookup"><span data-stu-id="16564-131">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="16564-132">Naciśnij i przytrzymaj **przycisk zasilania** przez 15 sekund.</span><span class="sxs-lookup"><span data-stu-id="16564-132">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="16564-133">Wszystkie diody LED powinny być wyłączone.</span><span class="sxs-lookup"><span data-stu-id="16564-133">All LEDs should be off.</span></span>

3. <span data-ttu-id="16564-134">Poczekaj 2–3 sekundy, a następnie naciśnij krótko **przycisk** zasilania.</span><span class="sxs-lookup"><span data-stu-id="16564-134">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="16564-135">Diody LED w pobliżu przycisku zasilania zostaną zasypne, a urządzenie zacznie się uruchamiać.</span><span class="sxs-lookup"><span data-stu-id="16564-135">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="16564-136">Podłącz urządzenie do komputera hosta, a następnie otwórz Menedżer urządzeń.</span><span class="sxs-lookup"><span data-stu-id="16564-136">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="16564-137">(Aby Windows 10, naciśnij klawisz **systemu Windows,** a następnie **klawisz X,** a następnie wybierz **pozycję Menedżer urządzeń).** Upewnij się, że urządzenie jest prawidłowo wyliczane *Microsoft HoloLens* jak pokazano na poniższej ilustracji:</span><span class="sxs-lookup"><span data-stu-id="16564-137">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftLensRecovery devive manager](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a><span data-ttu-id="16564-139">Procedura resetowania na twardym dysku</span><span class="sxs-lookup"><span data-stu-id="16564-139">Hard-reset procedure</span></span>

<span data-ttu-id="16564-140">Jeśli standardowa procedura resetowania nie zadziałała, użyj procedury resetowania na dysku twardym:</span><span class="sxs-lookup"><span data-stu-id="16564-140">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="16564-141">Odłącz kabel typu C, aby odłączyć urządzenie od zasilacza lub komputera hosta.</span><span class="sxs-lookup"><span data-stu-id="16564-141">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="16564-142">Przytrzymaj w dół **przyciski zasilania** głośności przez  +   15 sekund.</span><span class="sxs-lookup"><span data-stu-id="16564-142">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="16564-143">Urządzenie zostanie automatycznie uruchomione ponownie.</span><span class="sxs-lookup"><span data-stu-id="16564-143">The device will automatically restart.</span></span>

4. <span data-ttu-id="16564-144">Podłącz urządzenie do komputera hosta.</span><span class="sxs-lookup"><span data-stu-id="16564-144">Connect the device to the host PC.</span></span>

5. <span data-ttu-id="16564-145">Otwórz Menedżer urządzeń (w Windows 10 naciśnij klawisz **systemu Windows,** a następnie **klawisz X,** a następnie wybierz pozycję **Menedżer urządzeń**).</span><span class="sxs-lookup"><span data-stu-id="16564-145">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="16564-146">Upewnij się, że urządzenie jest prawidłowo wyliczane *Microsoft HoloLens* jak pokazano na poniższej ilustracji:</span><span class="sxs-lookup"><span data-stu-id="16564-146">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![Urządzenie HoloLens 2 MicrosoftKlensRecovery maanger 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a><span data-ttu-id="16564-148">Czyszczenie i reflash urządzenia</span><span class="sxs-lookup"><span data-stu-id="16564-148">Clean-reflash the device</span></span>

<span data-ttu-id="16564-149">W wyjątkowych sytuacjach może być trzeba "oczyścić flash" urządzenia HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="16564-149">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="16564-150">Należy pamiętać, że clean-reflash nie powinien mieć wpływu na następujące problemy:</span><span class="sxs-lookup"><span data-stu-id="16564-150">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="16564-151">Wyświetlanie jednolitego koloru</span><span class="sxs-lookup"><span data-stu-id="16564-151">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="16564-152">Rozruch z dźwiękami, ale bez wyświetlania danych wyjściowych</span><span class="sxs-lookup"><span data-stu-id="16564-152">Booting with sound but no display output</span></span>
- [<span data-ttu-id="16564-153">Wzorzec 1-3-5-LED</span><span class="sxs-lookup"><span data-stu-id="16564-153">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="16564-154">Przegrzanie</span><span class="sxs-lookup"><span data-stu-id="16564-154">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="16564-155">Awarie systemu operacyjnego (różniące się od awarii aplikacji)</span><span class="sxs-lookup"><span data-stu-id="16564-155">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="16564-156">Istnieją dwa sposoby reflash urządzenia.</span><span class="sxs-lookup"><span data-stu-id="16564-156">There are two ways to reflash the device.</span></span> <span data-ttu-id="16564-157">W obu przypadkach należy najpierw zainstalować program [Advanced Recovery Companion ze Sklepu Windows.](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="16564-157">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="16564-158">W przypadku zmiany ukośnika urządzenia wszystkie dane osobowe, aplikacje i ustawienia zostaną usunięte, w tym informacje dotyczące resetowania modułu TPM.</span><span class="sxs-lookup"><span data-stu-id="16564-158">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="16564-159">Domyślnie opcja Pomocnik odzyskiwania zaawansowanego jest ustawiona na pobieranie najnowszej [](hololens-release-notes.md#) kompilacji wydania funkcji. Przeczytaj nasze informacje o wersji, aby dowiedzieć się więcej o najnowszej wersji funkcji.</span><span class="sxs-lookup"><span data-stu-id="16564-159">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="16564-160">Aby uzyskać najnowszy pakiet Aktualizacji pełnej flash urządzenia HoloLens 2 (FFU) w celu reflashowania urządzenia za pomocą narzędzia Advanced Recovery Companion, kliknij tutaj, aby pobrać najnowszy obraz [urządzenia HoloLens 2 w miesiącu.](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="16564-160">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="16564-161">Jest to najnowsza ogólnie dostępna kompilacja.</span><span class="sxs-lookup"><span data-stu-id="16564-161">This version is the latest generally available build.</span></span>

<span data-ttu-id="16564-162">Przed rozpoczęciem procedury reflash upewnij się, że aplikacja jest zainstalowana i uruchomiona na komputerze Windows 10 i jest gotowa do wykrywania urządzenia.</span><span class="sxs-lookup"><span data-stu-id="16564-162">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span> <span data-ttu-id="16564-163">Upewnij się również, że opłaty za urządzenie HoloLens są naliczane co najmniej 40%.</span><span class="sxs-lookup"><span data-stu-id="16564-163">Also ensure that your HoloLens is charged to a minimum of 40%.</span></span>

![Zrzut ekranu z czystym ukośnikiem holoLens 2](images/ARC1.png)

### <a name="normal-procedure"></a><span data-ttu-id="16564-165">Normalna procedura</span><span class="sxs-lookup"><span data-stu-id="16564-165">Normal procedure</span></span>

1. <span data-ttu-id="16564-166">Gdy urządzenie HoloLens jest uruchomione, połącz je z komputerem Windows 10, na którym wcześniej otwarto aplikację Advanced Recovery Companion.</span><span class="sxs-lookup"><span data-stu-id="16564-166">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="16564-167">Urządzenie zostanie wykryte automatycznie, a interfejs użytkownika aplikacji pomocnika odzyskiwania zaawansowanego rozpocznie proces aktualizacji:</span><span class="sxs-lookup"><span data-stu-id="16564-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Początkowy ekran czystego ukośnika HoloLens 2](images/ARC2.png)

3. <span data-ttu-id="16564-169">Wybierz urządzenie HoloLens 2 w interfejsie użytkownika aplikacji Advanced Recovery Companion i postępuj zgodnie z instrukcjami, aby ukończyć reflash.</span><span class="sxs-lookup"><span data-stu-id="16564-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <a name="manual-procedure"></a><span data-ttu-id="16564-170">Procedura ręczna</span><span class="sxs-lookup"><span data-stu-id="16564-170">Manual procedure</span></span>

<span data-ttu-id="16564-171">Jeśli urządzenie HoloLens 2 nie uruchamia się poprawnie lub jeśli program Advanced Recovery Companion nie może wykryć urządzenia, może być konieczne uruchomienie urządzenia w tryb odzyskiwania:</span><span class="sxs-lookup"><span data-stu-id="16564-171">If the HoloLens 2 doesn't start correctly or if Advanced Recovery Companion cannot detect the device, you may need to put the device into recovery mode:</span></span>

1. <span data-ttu-id="16564-172">Odłącz kabel typu C, aby odłączyć urządzenie od zasilacza lub komputera hosta.</span><span class="sxs-lookup"><span data-stu-id="16564-172">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="16564-173">Naciśnij i przytrzymaj **przycisk zasilania** przez 15 sekund.</span><span class="sxs-lookup"><span data-stu-id="16564-173">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="16564-174">Wszystkie diody LED powinny zostać wyłączone.</span><span class="sxs-lookup"><span data-stu-id="16564-174">All LEDs should turn off.</span></span>

3. <span data-ttu-id="16564-175">Naciskając przycisk **regulacji głośności,** naciśnij i zwolnij **przycisk** zasilania, aby uruchomić urządzenie.</span><span class="sxs-lookup"><span data-stu-id="16564-175">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="16564-176">Poczekaj 15 sekund, a następnie zwolnij **przycisk regulacji głośności.**</span><span class="sxs-lookup"><span data-stu-id="16564-176">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="16564-177">Tylko środkowa dioda LED pięciu diod LED będzie się oświetlać.</span><span class="sxs-lookup"><span data-stu-id="16564-177">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="16564-178">Podłącz urządzenie do komputera hosta i otwórz Menedżer urządzeń.</span><span class="sxs-lookup"><span data-stu-id="16564-178">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="16564-179">(Aby Windows 10 naciśnij klawisz **systemu Windows,** a następnie **klawisz X,** a następnie wybierz **pozycję Menedżer urządzeń).** Upewnij się, że urządzenie jest prawidłowo wyliczane Microsoft HoloLens jak pokazano na poniższej ilustracji:</span><span class="sxs-lookup"><span data-stu-id="16564-179">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftLensRecovery](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="16564-181">Urządzenie zostanie wykryte automatycznie, a interfejs użytkownika aplikacji pomocnika odzyskiwania zaawansowanego rozpocznie proces aktualizacji:</span><span class="sxs-lookup"><span data-stu-id="16564-181">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![Czysty ekran reflash urządzenia HoloLens 2](images/ARC2.png)

6. <span data-ttu-id="16564-183">Wybierz urządzenie HoloLens 2 w interfejsie użytkownika aplikacji Advanced Recovery Companion, a następnie postępuj zgodnie z instrukcjami, aby ukończyć reflash.</span><span class="sxs-lookup"><span data-stu-id="16564-183">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <a name="troubleshoot-advanced-recovery-companion"></a><span data-ttu-id="16564-184">Rozwiązywanie problemów z zaawansowaną pomocniką odzyskiwania</span><span class="sxs-lookup"><span data-stu-id="16564-184">Troubleshoot Advanced Recovery Companion</span></span>

1. <span data-ttu-id="16564-185">Przed próbą flashowania upewnij się, że opłata za urządzenie jest naliczana w wysokości co najmniej 40%.</span><span class="sxs-lookup"><span data-stu-id="16564-185">Ensure your device is charged to 40% or more before attempting to flash.</span></span>

2. <span data-ttu-id="16564-186">Sprawdź, czy urządzenie jest odblokowane.</span><span class="sxs-lookup"><span data-stu-id="16564-186">Check that your device is unlocked.</span></span>

3. <span data-ttu-id="16564-187">Jeśli usługa ARC nie wykryje urządzenia, upewnij się, że możesz nawiązać połączenie z urządzeniem za pośrednictwem Eksplorator plików na komputerze.</span><span class="sxs-lookup"><span data-stu-id="16564-187">If ARC does not detect your device, ensure that you can connect to your device via File Explorer on your PC.</span></span> <span data-ttu-id="16564-188">Jeśli nie możesz;</span><span class="sxs-lookup"><span data-stu-id="16564-188">If you cannot;</span></span>

    1.  <span data-ttu-id="16564-189">Urządzenie może mieć zasady USB, które wyłączą to połączenie.</span><span class="sxs-lookup"><span data-stu-id="16564-189">It is possible that your device may have USB policies that disable that connection.</span></span> <span data-ttu-id="16564-190">Jeśli tak, spróbuj [użyć trybu ręcznego flashowania.](hololens-recovery.md#manual-procedure)</span><span class="sxs-lookup"><span data-stu-id="16564-190">If so, try [Manual Flashing mode](hololens-recovery.md#manual-procedure).</span></span>
    2.  <span data-ttu-id="16564-191">Jeśli nie ma żadnych zasad, wypróbuj inny kabel USB.</span><span class="sxs-lookup"><span data-stu-id="16564-191">If there are no policies, try a different USB cable.</span></span>

1. <span data-ttu-id="16564-192">Sprawdź, czy na urządzeniu nie jest wyświetlany wzorzec [1–3-5-LED.](hololens2-setup.md#lights-to-indicate-problems)</span><span class="sxs-lookup"><span data-stu-id="16564-192">Check that your device doesn't display a [1-3-5-LED pattern](hololens2-setup.md#lights-to-indicate-problems).</span></span>

## <a name="download-arc-without-using-the-app-store"></a><span data-ttu-id="16564-193">Pobieranie usługi ARC bez korzystania ze sklepu z aplikacjami</span><span class="sxs-lookup"><span data-stu-id="16564-193">Download ARC without using the app store</span></span>

<span data-ttu-id="16564-194">Jeśli środowisko IT uniemożliwia korzystanie z aplikacji ze Sklepu Windows lub ogranicza dostęp do sklepu detalicznego, administrator IT może udostępnić tę aplikację za pośrednictwem ścieżki wdrażania "w trybie offline".</span><span class="sxs-lookup"><span data-stu-id="16564-194">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE]
 > - <span data-ttu-id="16564-195">Administratorzy IT mogą również rozpowszechniać tę aplikację za pośrednictwem System Center Menedżer konfiguracji (SCCM) lub usługi Intune.</span><span class="sxs-lookup"><span data-stu-id="16564-195">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="16564-196">Ten przewodnik koncentruje się na pomocniku odzyskiwania zaawansowanego, ale ten proces może być również używany w przypadku innych aplikacji "w trybie offline".</span><span class="sxs-lookup"><span data-stu-id="16564-196">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="16564-197">Wykonaj następujące kroki, aby włączyć ścieżkę wdrażania:</span><span class="sxs-lookup"><span data-stu-id="16564-197">Follow these steps to enable the deployment path:</span></span>

1. <span data-ttu-id="16564-198">Przejdź do [Microsoft Store dla Firm](https://businessstore.microsoft.com) i zaloguj się przy użyciu Azure Active Directory tożsamości.</span><span class="sxs-lookup"><span data-stu-id="16564-198">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="16564-199">Przejdź do **zarządzaj — ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="16564-199">Go to **Manage – Settings**.</span></span> <span data-ttu-id="16564-200">Włącz wyświetlanie **aplikacji w trybie offline w** obszarze Środowisko **zakupów.**</span><span class="sxs-lookup"><span data-stu-id="16564-200">Turn on **Show offline apps** under **Shopping experience**.</span></span>

1. <span data-ttu-id="16564-201">Przejdź do **sklepu dla mojej grupy** i wyszukaj [**_pomocnika odzyskiwania zaawansowanego._**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="16564-201">Go to **shop for my group**, and search for [**_Advanced Recovery Companion_**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>

1. <span data-ttu-id="16564-202">Zmień typ **licencji na** \**_offline_*_, a następnie wybierz pozycję _\* Zarządzaj\*\*.</span><span class="sxs-lookup"><span data-stu-id="16564-202">Change the **License Type** to \**_offline_*_, and select _\* Manage\*\*.</span></span>

1. <span data-ttu-id="16564-203">W **obszarze Pobierz pakiet do użycia w trybie offline** wybierz drugi niebieski **przycisk** Pobierz.</span><span class="sxs-lookup"><span data-stu-id="16564-203">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="16564-204">Upewnij się, że rozszerzeniem pliku *jest .appxbundle.*</span><span class="sxs-lookup"><span data-stu-id="16564-204">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="16564-205">Jeśli na tym etapie komputer stacjonarny ma dostęp do Internetu, kliknij dwukrotnie pakiet, aby zainstalować aplikację.</span><span class="sxs-lookup"><span data-stu-id="16564-205">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>

    - <span data-ttu-id="16564-206">Jeśli komputer docelowy nie ma łączności z Internetem, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="16564-206">If the destination PC has no internet connectivity, follow these steps:</span></span>
       1. <span data-ttu-id="16564-207">Wybierz niezakodowana licencję, a następnie wybierz pozycję **Generuj licencję.**</span><span class="sxs-lookup"><span data-stu-id="16564-207">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="16564-208">W **obszarze Wymagane struktury wybierz** pozycję **Pobierz**.</span><span class="sxs-lookup"><span data-stu-id="16564-208">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="16564-209">Użyj funkcji DISM, aby zastosować pakiet z zależnością i licencją.</span><span class="sxs-lookup"><span data-stu-id="16564-209">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="16564-210">W wierszu polecenia administratora uruchom następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="16564-210">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > <span data-ttu-id="16564-211">Numer wersji w tym przykładzie kodu może nie odpowiadać obecnie dostępnej wersji.</span><span class="sxs-lookup"><span data-stu-id="16564-211">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="16564-212">Być może wybrano również inną lokalizację pobierania niż w przykładzie.</span><span class="sxs-lookup"><span data-stu-id="16564-212">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="16564-213">W razie potrzeby należy wprowadzić zmiany w poleceniu.</span><span class="sxs-lookup"><span data-stu-id="16564-213">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="16564-214">Jeśli planujesz użycie pomocnika odzyskiwania zaawansowanego w celu zainstalowania ffu w trybie offline, może być przydatne pobranie obrazu flash.</span><span class="sxs-lookup"><span data-stu-id="16564-214">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="16564-215">[**Pobierz bieżący obraz dla urządzenia HoloLens 2.**](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="16564-215">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span>


<span data-ttu-id="16564-216">Inne zasoby:</span><span class="sxs-lookup"><span data-stu-id="16564-216">Other resources:</span></span>
- [<span data-ttu-id="16564-217">Dystrybuowanie aplikacji w trybie offline</span><span class="sxs-lookup"><span data-stu-id="16564-217">Distribute offline apps</span></span>](/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="16564-218">Opcje wiersza polecenia obsługi pakietu aplikacji DISM (appx lub appxbundle)</span><span class="sxs-lookup"><span data-stu-id="16564-218">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
