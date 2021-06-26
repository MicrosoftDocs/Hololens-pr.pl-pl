---
title: Nawiązywanie połączenia z urządzeniami Bluetooth i USB-C
description: Rozpoczynanie nawiązywania połączenia z urządzeniami Bluetooth i USB-C oraz akcesoriami z urządzeń HoloLens rzeczywistości mieszanej.
ms.assetid: 01af0848-3b36-4c13-b797-f38ad3977e30
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 03/11/2020
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e02950bf6cb70e381e3bc5850509bc65267759c1
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924183"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="271a4-103">Nawiązywanie połączenia z urządzeniami Bluetooth i USB-C</span><span class="sxs-lookup"><span data-stu-id="271a4-103">Connect to Bluetooth and USB-C devices</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="271a4-104">Parowanie urządzeń Bluetooth</span><span class="sxs-lookup"><span data-stu-id="271a4-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="271a4-105">Urządzenie HoloLens 2 obsługuje następujące klasy urządzeń Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="271a4-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="271a4-106">[HID:](https://docs.microsoft.com/windows-hardware/drivers/hid/)</span><span class="sxs-lookup"><span data-stu-id="271a4-106">[HID](https://docs.microsoft.com/windows-hardware/drivers/hid/):</span></span>
    - <span data-ttu-id="271a4-107">Mysz</span><span class="sxs-lookup"><span data-stu-id="271a4-107">Mouse</span></span>
    - <span data-ttu-id="271a4-108">Klawiatura</span><span class="sxs-lookup"><span data-stu-id="271a4-108">Keyboard</span></span>
- <span data-ttu-id="271a4-109">Urządzenia wyjściowe audio (A2DP)</span><span class="sxs-lookup"><span data-stu-id="271a4-109">Audio output (A2DP) devices</span></span>

<span data-ttu-id="271a4-110">Urządzenie HoloLens 2 obsługuje następujące interfejsy API bluetooth:</span><span class="sxs-lookup"><span data-stu-id="271a4-110">HoloLens 2 supports the following Bluetooth APIs:</span></span>
- <span data-ttu-id="271a4-111">Serwer [](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) i [klient](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client) DHCP</span><span class="sxs-lookup"><span data-stu-id="271a4-111">GATT [Server](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) and [Client](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client)</span></span>
- [<span data-ttu-id="271a4-112">RFCOMM</span><span class="sxs-lookup"><span data-stu-id="271a4-112">RFCOMM</span></span>](https://docs.microsoft.com/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> <span data-ttu-id="271a4-113">Może być trzeba zainstalować odpowiednie aplikacje towarzyszące z Microsoft Store, aby w rzeczywistości korzystać z urządzeń HID i THE.</span><span class="sxs-lookup"><span data-stu-id="271a4-113">You may have to install corresponding companion apps from Microsoft Store to actually use the HID and GATT devices.</span></span>

<span data-ttu-id="271a4-114">Urządzenie HoloLens (1. generacji) obsługuje następujące klasy urządzeń Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="271a4-114">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="271a4-115">Mysz</span><span class="sxs-lookup"><span data-stu-id="271a4-115">Mouse</span></span>
- <span data-ttu-id="271a4-116">Klawiatura</span><span class="sxs-lookup"><span data-stu-id="271a4-116">Keyboard</span></span>
- [<span data-ttu-id="271a4-117">Kliknięcie urządzenia HoloLens (1. generacji)</span><span class="sxs-lookup"><span data-stu-id="271a4-117">HoloLens (1st gen) clicker</span></span>](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> <span data-ttu-id="271a4-118">Inne typy urządzeń Bluetooth, takie jak głośniki, zestawy nagłowne, smartfony i konsoli do gier, mogą być wyświetlane jako dostępne w ustawieniach urządzenia HoloLens.</span><span class="sxs-lookup"><span data-stu-id="271a4-118">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="271a4-119">Jednak te urządzenia nie są obsługiwane na urządzeniu HoloLens (1. generacji).</span><span class="sxs-lookup"><span data-stu-id="271a4-119">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="271a4-120">Aby uzyskać więcej informacji, zobacz [Ustawienia urządzenia HoloLens](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work)wyświetla listę urządzeń jako dostępnych, ale urządzenia nie działają.</span><span class="sxs-lookup"><span data-stu-id="271a4-120">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="271a4-121">Parowanie klawiatury lub myszy Bluetooth</span><span class="sxs-lookup"><span data-stu-id="271a4-121">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="271a4-122">Włącz klawiaturę lub mysz, aby było możliwe do odnajdywania.</span><span class="sxs-lookup"><span data-stu-id="271a4-122">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="271a4-123">Aby dowiedzieć się, jak sprawić, aby urządzenie było wykrywalne, poszukaj informacji na urządzeniu (lub w jego dokumentacji) lub odwiedź witrynę internetową producenta.</span><span class="sxs-lookup"><span data-stu-id="271a4-123">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="271a4-124">Użyj gestu Blooma (HoloLens (1. generacja)) lub gestu uruchamiania (HoloLens 2), aby przejść do menu **Start,** a następnie wybierz pozycję **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="271a4-124">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="271a4-125">Wybierz **pozycję Urządzenia** i upewnij się, że funkcja Bluetooth jest wł.</span><span class="sxs-lookup"><span data-stu-id="271a4-125">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="271a4-126">Po wyświetleniu nazwy urządzenia wybierz pozycję **Sparuj**, a następnie postępuj zgodnie z instrukcjami.</span><span class="sxs-lookup"><span data-stu-id="271a4-126">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="271a4-127">Wyłączanie połączenia Bluetooth</span><span class="sxs-lookup"><span data-stu-id="271a4-127">Disable Bluetooth</span></span>

<span data-ttu-id="271a4-128">Ta procedura wyłącza składniki RADIOWE przycisku radiowego Bluetooth i wyłącza wszystkie funkcje Bluetooth na Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="271a4-128">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="271a4-129">Użyj gestu Blooma (HoloLens (1. generacja)) lub gestu uruchamiania (HoloLens 2), aby przejść do menu **Start,** a następnie wybrać pozycję  >  **Ustawienia Urządzenia.**</span><span class="sxs-lookup"><span data-stu-id="271a4-129">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="271a4-130">Przesuń przełącznik suwaka dla połączenia **Bluetooth** do **pozycji** Wyłączone.</span><span class="sxs-lookup"><span data-stu-id="271a4-130">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="271a4-131">HoloLens 2: podłączanie urządzeń USB-C</span><span class="sxs-lookup"><span data-stu-id="271a4-131">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="271a4-132">Urządzenie HoloLens 2 obsługuje następujące klasy urządzeń USB-C:</span><span class="sxs-lookup"><span data-stu-id="271a4-132">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="271a4-133">Urządzenia pamięci masowej (takie jak dyski kciuka)</span><span class="sxs-lookup"><span data-stu-id="271a4-133">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="271a4-134">Karty Ethernet (w tym ethernet i ładowanie)</span><span class="sxs-lookup"><span data-stu-id="271a4-134">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="271a4-135">Adaptery audio usb-C-do-3,5 mm</span><span class="sxs-lookup"><span data-stu-id="271a4-135">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="271a4-136">Cyfrowe zestawy nagłowne USB-C (w tym adaptery zestawów nagłownych i ładowanie)</span><span class="sxs-lookup"><span data-stu-id="271a4-136">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="271a4-137">Zewnętrzne mikrofony USB-C ([Windows Holographic, wersja 21H1 lub](hololens-release-notes.md#windows-holographic-version-21h1) nowsza)</span><span class="sxs-lookup"><span data-stu-id="271a4-137">USB-C External Microphones ([Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher)</span></span>
- <span data-ttu-id="271a4-138">Mysz przewodowa</span><span class="sxs-lookup"><span data-stu-id="271a4-138">Wired mouse</span></span>
- <span data-ttu-id="271a4-139">Klawiatura przewodowa</span><span class="sxs-lookup"><span data-stu-id="271a4-139">Wired keyboard</span></span>
- <span data-ttu-id="271a4-140">Koncentratory PD z kombinacją (ładowanie za pomocą portu USB A i PD)</span><span class="sxs-lookup"><span data-stu-id="271a4-140">Combination PD hubs (USB A plus PD charging)</span></span>


> [!NOTE]
> <span data-ttu-id="271a4-141">W odpowiedzi na opinie klientów włączyliśmy ograniczoną obsługę łączności komórkowej bezpośrednio z urządzeniem HoloLens za pośrednictwem portu USB-C.</span><span class="sxs-lookup"><span data-stu-id="271a4-141">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="271a4-142">Aby uzyskać więcej informacji, zobacz [Connect to Cellular and 5G (Łączenie](hololens-cellular.md) z siecią komórkową i 5G).</span><span class="sxs-lookup"><span data-stu-id="271a4-142">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-external-microphone-support"></a><span data-ttu-id="271a4-143">Obsługa mikrofonu zewnętrznego USB-C</span><span class="sxs-lookup"><span data-stu-id="271a4-143">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="271a4-144">Podłączanie **mikrofonu USB nie ustawi go** automatycznie jako urządzenia wejściowego .</span><span class="sxs-lookup"><span data-stu-id="271a4-144">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="271a4-145">Podczas podłączania zestawu słuchawki USB-C użytkownicy zauważą, że dźwięk telefonu komórkowego zostanie automatycznie przekierowany do mikrofonu, ale system operacyjny HoloLens określa priorytet wewnętrznej macierzy mikrofonu nad każdym innym urządzeniem wejściowym.</span><span class="sxs-lookup"><span data-stu-id="271a4-145">When plugging in a set of USB-C headphones, users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> <span data-ttu-id="271a4-146">**Aby użyć mikrofonu USB-C, wykonaj poniższe kroki.**</span><span class="sxs-lookup"><span data-stu-id="271a4-146">**In order to use a USB-C microphone follow the steps below.**</span></span>

> [!NOTE]
> <span data-ttu-id="271a4-147">Nie można używać zewnętrznych mikrofonów w kompilacjach wcześniejszych niż Windows Holographic w wersji [21H1](hololens-release-notes.md#windows-holographic-version-21h1) lub wyższej.</span><span class="sxs-lookup"><span data-stu-id="271a4-147">External microphones cannot be used in builds prior to [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher.</span></span> 

<span data-ttu-id="271a4-148">Użytkownicy mogą wybierać zewnętrzne mikrofony podłączone do portu USB C przy użyciu **panelu Ustawień** dźwięku.</span><span class="sxs-lookup"><span data-stu-id="271a4-148">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="271a4-149">Mikrofony USB-C mogą służyć do wywoływania, nagrywania itp.</span><span class="sxs-lookup"><span data-stu-id="271a4-149">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="271a4-150">Otwórz aplikację **Ustawienia** i wybierz **pozycję Dźwięk**  >  **systemowy.**</span><span class="sxs-lookup"><span data-stu-id="271a4-150">Open the **Settings** app and select **System** > **Sound**.</span></span>

![Ustawienia dźwięku](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="271a4-152">Aby używać mikrofonów zewnętrznych z **usługą Remote Assist,** użytkownicy muszą kliknąć hiperlink "Zarządzanie urządzeniami dźwiękowymi".</span><span class="sxs-lookup"><span data-stu-id="271a4-152">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="271a4-153">Następnie użyj listy rozwijanej, aby ustawić zewnętrzny mikrofon jako **Domyślny lub** Domyślny **dla komunikacji.**</span><span class="sxs-lookup"><span data-stu-id="271a4-153">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="271a4-154">Wybranie **opcji Domyślne** oznacza, że zewnętrzny mikrofon będzie używany wszędzie.</span><span class="sxs-lookup"><span data-stu-id="271a4-154">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="271a4-155">Wybranie **opcji Domyślna** komunikacja oznacza, że zewnętrzny mikrofon będzie używany w funkcji Remote Assist i innych aplikacjach komunikacyjnych, ale macierz mikrofonu HoloLens może być nadal używana do innych zadań.</span><span class="sxs-lookup"><span data-stu-id="271a4-155">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![Zarządzanie urządzeniami dźwiękowymi](images/usbc-mic-2.png)

<br>

![Ustaw wartość domyślną mikrofonu](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a><span data-ttu-id="271a4-158">Co z obsługą mikrofonu Bluetooth?</span><span class="sxs-lookup"><span data-stu-id="271a4-158">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="271a4-159">Niestety mikrofony Bluetooth nadal nie są obecnie obsługiwane na urządzeniu HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="271a4-159">Unfortunately, Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

### <a name="usb-c-hubs"></a><span data-ttu-id="271a4-160">Koncentratory USB-C</span><span class="sxs-lookup"><span data-stu-id="271a4-160">USB-C Hubs</span></span>

<span data-ttu-id="271a4-161">Niektórzy użytkownicy mogą wymagać połączenia wielu urządzeń jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="271a4-161">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="271a4-162">W przypadku użytkowników, którzy chcą używać mikrofonu [USB-C](#usb-c-external-microphone-support) wraz z innym połączonym urządzeniem, koncentratory USB-C mogą pasować do potrzeb klienta.</span><span class="sxs-lookup"><span data-stu-id="271a4-162">For users who would like to use a [USB-C microphone](#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="271a4-163">Firma Microsoft nie przetestowała tych urządzeń ani nie możemy zalecić żadnych określonych marek.</span><span class="sxs-lookup"><span data-stu-id="271a4-163">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

<span data-ttu-id="271a4-164">**Wymagania dotyczące koncentratora USB-C i podłączonych urządzeń:**</span><span class="sxs-lookup"><span data-stu-id="271a4-164">**Requirements for USB-C hub and connected devices:**</span></span>

- <span data-ttu-id="271a4-165">Podłączone urządzenia nie mogą wymagać zainstalowania sterownika.</span><span class="sxs-lookup"><span data-stu-id="271a4-165">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="271a4-166">Łączny pobór mocy wszystkich połączonych urządzeń musi być poniżej 4,5 Watów.</span><span class="sxs-lookup"><span data-stu-id="271a4-166">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="271a4-167">Nawiązywanie połączenia z miracastem</span><span class="sxs-lookup"><span data-stu-id="271a4-167">Connect to Miracast</span></span>

<span data-ttu-id="271a4-168">Aby użyć Miracast, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="271a4-168">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="271a4-169">Wykonaj jedną z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="271a4-169">Do one of the following:</span></span>  

   - <span data-ttu-id="271a4-170">Otwórz menu **Start** i wybierz **ikonę Wyświetl.**</span><span class="sxs-lookup"><span data-stu-id="271a4-170">Open the **Start** menu, and select the **Display** icon.</span></span>
   - <span data-ttu-id="271a4-171">Powiedz "Połącz", gdy spojrzysz na menu **Start.**</span><span class="sxs-lookup"><span data-stu-id="271a4-171">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="271a4-172">Na wyświetlonej liście urządzeń wybierz dostępne urządzenie.</span><span class="sxs-lookup"><span data-stu-id="271a4-172">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="271a4-173">Ukończ parowanie, aby rozpocząć rzutowanie.</span><span class="sxs-lookup"><span data-stu-id="271a4-173">Complete the pairing to begin projecting.</span></span>
