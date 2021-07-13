---
title: Połączenie do Bluetooth i USB-C
description: Wprowadzenie do nawiązywania połączenia Bluetooth urządzeniami i akcesoriami USB-C z urządzeń HoloLens rzeczywistości mieszanej.
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
ms.openlocfilehash: 5fed56d7a0beeda0a0d96eddc63aaee872f3e52d
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639101"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="c00d6-103">Połączenie do Bluetooth i USB-C</span><span class="sxs-lookup"><span data-stu-id="c00d6-103">Connect to Bluetooth and USB-C devices</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="c00d6-104">Parowanie Bluetooth urządzeń</span><span class="sxs-lookup"><span data-stu-id="c00d6-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="c00d6-105">HoloLens 2 obsługuje następujące klasy Bluetooth urządzeń:</span><span class="sxs-lookup"><span data-stu-id="c00d6-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="c00d6-106">[HID:](/windows-hardware/drivers/hid/)</span><span class="sxs-lookup"><span data-stu-id="c00d6-106">[HID](/windows-hardware/drivers/hid/):</span></span>
    - <span data-ttu-id="c00d6-107">Mysz</span><span class="sxs-lookup"><span data-stu-id="c00d6-107">Mouse</span></span>
    - <span data-ttu-id="c00d6-108">Klawiatura</span><span class="sxs-lookup"><span data-stu-id="c00d6-108">Keyboard</span></span>
- <span data-ttu-id="c00d6-109">Urządzenia wyjściowe audio (A2DP)</span><span class="sxs-lookup"><span data-stu-id="c00d6-109">Audio output (A2DP) devices</span></span>

<span data-ttu-id="c00d6-110">HoloLens 2 obsługuje następujące interfejsy BLUETOOTH API:</span><span class="sxs-lookup"><span data-stu-id="c00d6-110">HoloLens 2 supports the following Bluetooth APIs:</span></span>
- <span data-ttu-id="c00d6-111">Serwer [](/windows/uwp/devices-sensors/gatt-server) i klient [ZOI](/windows/uwp/devices-sensors/gatt-client)</span><span class="sxs-lookup"><span data-stu-id="c00d6-111">GATT [Server](/windows/uwp/devices-sensors/gatt-server) and [Client](/windows/uwp/devices-sensors/gatt-client)</span></span>
- [<span data-ttu-id="c00d6-112">RFCOMM</span><span class="sxs-lookup"><span data-stu-id="c00d6-112">RFCOMM</span></span>](/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> <span data-ttu-id="c00d6-113">Może być trzeba zainstalować odpowiednie aplikacje towarzyszące z Microsoft Store, aby w rzeczywistości korzystać z urządzeń HID i THE.</span><span class="sxs-lookup"><span data-stu-id="c00d6-113">You may have to install corresponding companion apps from Microsoft Store to actually use the HID and GATT devices.</span></span>

<span data-ttu-id="c00d6-114">HoloLens (1. generacji) obsługuje następujące klasy urządzeń Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="c00d6-114">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="c00d6-115">Mysz</span><span class="sxs-lookup"><span data-stu-id="c00d6-115">Mouse</span></span>
- <span data-ttu-id="c00d6-116">Klawiatura</span><span class="sxs-lookup"><span data-stu-id="c00d6-116">Keyboard</span></span>
- [<span data-ttu-id="c00d6-117">HoloLens (1. generacja)</span><span class="sxs-lookup"><span data-stu-id="c00d6-117">HoloLens (1st gen) clicker</span></span>](hololens1-clicker.md)

> [!NOTE]
> <span data-ttu-id="c00d6-118">Inne typy urządzeń Bluetooth, takie jak głośników, zestawy nagłowne, smartfony i konsoli do gier, mogą być wyświetlane jako dostępne w HoloLens ustawieniach.</span><span class="sxs-lookup"><span data-stu-id="c00d6-118">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="c00d6-119">Jednak te urządzenia nie są obsługiwane na urządzeniach HoloLens (1. generacji).</span><span class="sxs-lookup"><span data-stu-id="c00d6-119">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="c00d6-120">Aby uzyskać więcej informacji, zobacz HoloLens Ustawienia listę urządzeń [jako dostępnych, ale urządzenia nie działają.](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work)</span><span class="sxs-lookup"><span data-stu-id="c00d6-120">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="c00d6-121">Parowanie klawiatury Bluetooth myszy lub klawiatury</span><span class="sxs-lookup"><span data-stu-id="c00d6-121">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="c00d6-122">Włącz klawiaturę lub mysz, aby było możliwe do odnajdywania.</span><span class="sxs-lookup"><span data-stu-id="c00d6-122">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="c00d6-123">Aby dowiedzieć się, jak sprawić, aby urządzenie było wykrywalne, poszukaj informacji na urządzeniu (lub w jego dokumentacji) lub odwiedź witrynę internetową producenta.</span><span class="sxs-lookup"><span data-stu-id="c00d6-123">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="c00d6-124">Użyj gestu Blooma (HoloLens (1. generacja)) lub gestu uruchamiania (HoloLens 2), aby przejść do opcji **Start**, a następnie wybierz pozycję **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="c00d6-124">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="c00d6-125">Wybierz **pozycję** Urządzenia i upewnij się, Bluetooth jest wł.</span><span class="sxs-lookup"><span data-stu-id="c00d6-125">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="c00d6-126">Gdy zobaczysz nazwę urządzenia, wybierz pozycję **Sparuj,** a następnie postępuj zgodnie z instrukcjami.</span><span class="sxs-lookup"><span data-stu-id="c00d6-126">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="c00d6-127">Wyłącz Bluetooth</span><span class="sxs-lookup"><span data-stu-id="c00d6-127">Disable Bluetooth</span></span>

<span data-ttu-id="c00d6-128">Ta procedura wyłącza składniki RF przycisku radiowego Bluetooth i wyłącza wszystkie Bluetooth na Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c00d6-128">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="c00d6-129">Użyj gestu Blooma (HoloLens (1. generacja)) lub gestu uruchamiania (HoloLens 2), aby przejść do strony Start **,** a następnie wybrać pozycję Ustawienia  >  **Urządzenia.**</span><span class="sxs-lookup"><span data-stu-id="c00d6-129">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="c00d6-130">Przenieś przełącznik suwaka dla **Bluetooth** w **położenie** Wyłączone.</span><span class="sxs-lookup"><span data-stu-id="c00d6-130">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="c00d6-131">HoloLens 2: Połączenie USB-C</span><span class="sxs-lookup"><span data-stu-id="c00d6-131">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="c00d6-132">HoloLens 2 obsługuje następujące klasy urządzeń USB-C:</span><span class="sxs-lookup"><span data-stu-id="c00d6-132">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="c00d6-133">Urządzenia pamięci masowej (takie jak dyski miniatur)</span><span class="sxs-lookup"><span data-stu-id="c00d6-133">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="c00d6-134">Karty Ethernet (w tym karty Ethernet i ładowanie)</span><span class="sxs-lookup"><span data-stu-id="c00d6-134">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="c00d6-135">Adaptery usb-C-to-3.5mm do cyfrowych audio</span><span class="sxs-lookup"><span data-stu-id="c00d6-135">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="c00d6-136">Cyfrowe zestawy audio USB-C (w tym adaptery nagłowne i ładowanie)</span><span class="sxs-lookup"><span data-stu-id="c00d6-136">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="c00d6-137">Zewnętrzne mikrofony USB-C ([Windows Holographic, wersja 21H1](hololens-release-notes.md#windows-holographic-version-21h1) lub nowsza)</span><span class="sxs-lookup"><span data-stu-id="c00d6-137">USB-C External Microphones ([Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher)</span></span>
- <span data-ttu-id="c00d6-138">Mysz przewodowa</span><span class="sxs-lookup"><span data-stu-id="c00d6-138">Wired mouse</span></span>
- <span data-ttu-id="c00d6-139">Klawiatura przewodowa</span><span class="sxs-lookup"><span data-stu-id="c00d6-139">Wired keyboard</span></span>
- <span data-ttu-id="c00d6-140">Koncentratory z kombinacją pd (ładowanie za pomocą portu USB A i pd)</span><span class="sxs-lookup"><span data-stu-id="c00d6-140">Combination PD hubs (USB A plus PD charging)</span></span>


> [!NOTE]
> <span data-ttu-id="c00d6-141">W odpowiedzi na opinie klientów włączyliśmy ograniczoną obsługę łączności komórkowej bezpośrednio z siecią HoloLens za pośrednictwem portu USB-C.</span><span class="sxs-lookup"><span data-stu-id="c00d6-141">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="c00d6-142">Zobacz [Połączenie do sieci komórkowej i 5G,](hololens-cellular.md) aby uzyskać więcej informacji.</span><span class="sxs-lookup"><span data-stu-id="c00d6-142">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-external-microphone-support"></a><span data-ttu-id="c00d6-143">Obsługa zewnętrznego mikrofonu USB-C</span><span class="sxs-lookup"><span data-stu-id="c00d6-143">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c00d6-144">Podłączanie **mikrofonu USB nie ustawi go** automatycznie jako urządzenia wejściowego .</span><span class="sxs-lookup"><span data-stu-id="c00d6-144">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="c00d6-145">Podczas podłączania zestawu słuchawki USB-C użytkownicy zauważą, że dźwięk telefonu komórkowego zostanie automatycznie przekierowany do słuchawki, ale system operacyjny HoloLens ustawia priorytet wewnętrznej macierzy mikrofonu nad każdym innym urządzeniem wejściowym.</span><span class="sxs-lookup"><span data-stu-id="c00d6-145">When plugging in a set of USB-C headphones, users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> <span data-ttu-id="c00d6-146">**Aby użyć mikrofonu USB-C, wykonaj poniższe kroki.**</span><span class="sxs-lookup"><span data-stu-id="c00d6-146">**In order to use a USB-C microphone follow the steps below.**</span></span>

> [!NOTE]
> <span data-ttu-id="c00d6-147">Nie można używać mikrofonów zewnętrznych w kompilacjach wcześniejszych niż Windows Holographic w wersji [21H1](hololens-release-notes.md#windows-holographic-version-21h1) lub wyższej.</span><span class="sxs-lookup"><span data-stu-id="c00d6-147">External microphones cannot be used in builds prior to [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher.</span></span> 

<span data-ttu-id="c00d6-148">Użytkownicy mogą wybierać zewnętrzne mikrofony podłączone do dysku USB C przy użyciu **panelu Ustawień** dźwięku.</span><span class="sxs-lookup"><span data-stu-id="c00d6-148">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="c00d6-149">Mikrofony USB-C mogą służyć do wywoływania, nagrywania itp.</span><span class="sxs-lookup"><span data-stu-id="c00d6-149">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="c00d6-150">Otwórz aplikację **Ustawienia** wybierz **pozycję Dźwięk**  >  **systemowy.**</span><span class="sxs-lookup"><span data-stu-id="c00d6-150">Open the **Settings** app and select **System** > **Sound**.</span></span>

![Dźwięk Ustawienia](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="c00d6-152">Aby używać mikrofonów zewnętrznych z **usługą Remote Assist,** użytkownicy będą musieli kliknąć hiperlink "Zarządzanie urządzeniami dźwiękowymi".</span><span class="sxs-lookup"><span data-stu-id="c00d6-152">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="c00d6-153">Następnie użyj listy rozwijanej, aby ustawić zewnętrzny mikrofon jako **domyślny lub** domyślny **dla komunikacji.**</span><span class="sxs-lookup"><span data-stu-id="c00d6-153">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="c00d6-154">Wybranie **opcji** Domyślne oznacza, że zewnętrzny mikrofon będzie używany wszędzie.</span><span class="sxs-lookup"><span data-stu-id="c00d6-154">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="c00d6-155">Wybranie **opcji Domyślna** komunikacja oznacza, że mikrofon zewnętrzny będzie używany w uchęce Zdalnej pomocy i innych aplikacjach komunikacyjnych, ale macierz mikrofonu HoloLens nadal może być używana do innych zadań.</span><span class="sxs-lookup"><span data-stu-id="c00d6-155">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![Zarządzanie urządzeniami dźwiękowymi](images/usbc-mic-2.png)

<br>

![Ustawianie domyślnego mikrofonu](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a><span data-ttu-id="c00d6-158">A co z Bluetooth mikrofonu?</span><span class="sxs-lookup"><span data-stu-id="c00d6-158">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="c00d6-159">Niestety, Bluetooth mikrofony nadal nie są obecnie obsługiwane w HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="c00d6-159">Unfortunately, Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

### <a name="usb-c-hubs"></a><span data-ttu-id="c00d6-160">Koncentratory USB-C</span><span class="sxs-lookup"><span data-stu-id="c00d6-160">USB-C Hubs</span></span>

<span data-ttu-id="c00d6-161">Niektórzy użytkownicy mogą wymagać połączenia wielu urządzeń jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="c00d6-161">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="c00d6-162">W przypadku użytkowników, którzy chcą używać mikrofonu [USB-C](#usb-c-external-microphone-support) wraz z innym połączonym urządzeniem, koncentratory USB-C mogą być dopasowane do potrzeb klienta.</span><span class="sxs-lookup"><span data-stu-id="c00d6-162">For users who would like to use a [USB-C microphone](#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="c00d6-163">Firma Microsoft nie przetestowała tych urządzeń ani nie może zalecać żadnych konkretnych marek.</span><span class="sxs-lookup"><span data-stu-id="c00d6-163">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

<span data-ttu-id="c00d6-164">**Wymagania dotyczące koncentratora USB-C i podłączonych urządzeń:**</span><span class="sxs-lookup"><span data-stu-id="c00d6-164">**Requirements for USB-C hub and connected devices:**</span></span>

- <span data-ttu-id="c00d6-165">Podłączone urządzenia nie mogą wymagać zainstalowania sterownika.</span><span class="sxs-lookup"><span data-stu-id="c00d6-165">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="c00d6-166">Całkowity pobór mocy wszystkich połączonych urządzeń musi być poniżej 4,5 Watów.</span><span class="sxs-lookup"><span data-stu-id="c00d6-166">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="c00d6-167">Połączenie do Miracast</span><span class="sxs-lookup"><span data-stu-id="c00d6-167">Connect to Miracast</span></span>

<span data-ttu-id="c00d6-168">Aby użyć Miracast, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="c00d6-168">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="c00d6-169">Wykonaj jedną z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="c00d6-169">Do one of the following:</span></span>  

   - <span data-ttu-id="c00d6-170">Otwórz menu **Start** i wybierz **ikonę Wyświetl.**</span><span class="sxs-lookup"><span data-stu-id="c00d6-170">Open the **Start** menu, and select the **Display** icon.</span></span>
   - <span data-ttu-id="c00d6-171">Powiedz "Połączenie", gdy spojrzysz na menu **Start.**</span><span class="sxs-lookup"><span data-stu-id="c00d6-171">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="c00d6-172">Na wyświetlonej liście urządzeń wybierz dostępne urządzenie.</span><span class="sxs-lookup"><span data-stu-id="c00d6-172">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="c00d6-173">Ukończ parowanie, aby rozpocząć rzutowanie.</span><span class="sxs-lookup"><span data-stu-id="c00d6-173">Complete the pairing to begin projecting.</span></span>
