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
ms.openlocfilehash: ffae65a6e1c096242ae7a28c488896c65df1c62d
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379763"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="f021d-103">Nawiązywanie połączenia z urządzeniami Bluetooth i USB-C</span><span class="sxs-lookup"><span data-stu-id="f021d-103">Connect to Bluetooth and USB-C devices</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="f021d-104">Parowanie urządzeń Bluetooth</span><span class="sxs-lookup"><span data-stu-id="f021d-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="f021d-105">Urządzenie HoloLens 2 obsługuje następujące klasy urządzeń Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="f021d-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="f021d-106">[HID:](https://docs.microsoft.com/windows-hardware/drivers/hid/)</span><span class="sxs-lookup"><span data-stu-id="f021d-106">[HID](https://docs.microsoft.com/windows-hardware/drivers/hid/):</span></span>
    - <span data-ttu-id="f021d-107">Mysz</span><span class="sxs-lookup"><span data-stu-id="f021d-107">Mouse</span></span>
    - <span data-ttu-id="f021d-108">Klawiatura</span><span class="sxs-lookup"><span data-stu-id="f021d-108">Keyboard</span></span>
- <span data-ttu-id="f021d-109">Urządzenia wyjściowe audio (A2DP)</span><span class="sxs-lookup"><span data-stu-id="f021d-109">Audio output (A2DP) devices</span></span>

<span data-ttu-id="f021d-110">Urządzenie HoloLens 2 obsługuje następujące interfejsy API bluetooth:</span><span class="sxs-lookup"><span data-stu-id="f021d-110">HoloLens 2 supports the following Bluetooth APIs:</span></span>
- <span data-ttu-id="f021d-111">Serwer [](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) i klient [ZOI](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client)</span><span class="sxs-lookup"><span data-stu-id="f021d-111">GATT [Server](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) and [Client](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client)</span></span>
- [<span data-ttu-id="f021d-112">RFCOMM</span><span class="sxs-lookup"><span data-stu-id="f021d-112">RFCOMM</span></span>](https://docs.microsoft.com/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> <span data-ttu-id="f021d-113">Może być trzeba zainstalować odpowiednie aplikacje towarzyszące z Microsoft Store, aby w rzeczywistości korzystać z urządzeń HID i THE.</span><span class="sxs-lookup"><span data-stu-id="f021d-113">You may have to install corresponding companion apps from Microsoft Store to actually use the HID and GATT devices.</span></span>

<span data-ttu-id="f021d-114">Urządzenie HoloLens (1. generacji) obsługuje następujące klasy urządzeń Bluetooth:</span><span class="sxs-lookup"><span data-stu-id="f021d-114">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="f021d-115">Mysz</span><span class="sxs-lookup"><span data-stu-id="f021d-115">Mouse</span></span>
- <span data-ttu-id="f021d-116">Klawiatura</span><span class="sxs-lookup"><span data-stu-id="f021d-116">Keyboard</span></span>
- [<span data-ttu-id="f021d-117">Kliknięcie urządzenia HoloLens (1. generacji)</span><span class="sxs-lookup"><span data-stu-id="f021d-117">HoloLens (1st gen) clicker</span></span>](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> <span data-ttu-id="f021d-118">Inne typy urządzeń Bluetooth, takie jak głośniky, zestawy nagłowne, smartfony i konsoli do gier, mogą być wyświetlane jako dostępne w ustawieniach urządzenia HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f021d-118">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="f021d-119">Jednak te urządzenia nie są obsługiwane na urządzeniu HoloLens (1. generacji).</span><span class="sxs-lookup"><span data-stu-id="f021d-119">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="f021d-120">Aby uzyskać więcej informacji, zobacz [Ustawienia urządzenia HoloLens zawiera](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)listę urządzeń jako dostępnych, ale urządzenia nie działają.</span><span class="sxs-lookup"><span data-stu-id="f021d-120">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="f021d-121">Parowanie klawiatury lub myszy Bluetooth</span><span class="sxs-lookup"><span data-stu-id="f021d-121">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="f021d-122">Włącz klawiaturę lub mysz, aby było możliwe do odnajdywania.</span><span class="sxs-lookup"><span data-stu-id="f021d-122">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="f021d-123">Aby dowiedzieć się, jak sprawić, aby urządzenie było wykrywalne, poszukaj informacji na urządzeniu (lub w jego dokumentacji) lub odwiedź witrynę internetową producenta.</span><span class="sxs-lookup"><span data-stu-id="f021d-123">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="f021d-124">Użyj gestu Blooma (HoloLens (1. generacja)) lub gestu uruchamiania (HoloLens 2), aby przejść do menu **Start,** a następnie wybrać pozycję **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="f021d-124">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="f021d-125">Wybierz **pozycję Urządzenia** i upewnij się, że połączenie Bluetooth jest wł.</span><span class="sxs-lookup"><span data-stu-id="f021d-125">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="f021d-126">Gdy zobaczysz nazwę urządzenia, wybierz pozycję **Sparuj,** a następnie postępuj zgodnie z instrukcjami.</span><span class="sxs-lookup"><span data-stu-id="f021d-126">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="f021d-127">Wyłącz funkcję Bluetooth</span><span class="sxs-lookup"><span data-stu-id="f021d-127">Disable Bluetooth</span></span>

<span data-ttu-id="f021d-128">Ta procedura powoduje wyłączenie składników RF przycisku radiowego Bluetooth i wyłączenie wszystkich funkcji Bluetooth na Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f021d-128">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="f021d-129">Użyj gestu Blooma (HoloLens (1. generacja)) lub gestu uruchamiania (HoloLens 2), aby przejść do menu **Start,** a następnie wybrać pozycję  >  **Ustawienia Urządzenia.**</span><span class="sxs-lookup"><span data-stu-id="f021d-129">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="f021d-130">Przesuń przełącznik suwaka dla **połączenia Bluetooth** do **pozycji** Wyłączone.</span><span class="sxs-lookup"><span data-stu-id="f021d-130">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="f021d-131">HoloLens 2: łączenie urządzeń USB-C</span><span class="sxs-lookup"><span data-stu-id="f021d-131">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="f021d-132">Urządzenie HoloLens 2 obsługuje następujące klasy urządzeń USB-C:</span><span class="sxs-lookup"><span data-stu-id="f021d-132">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="f021d-133">Urządzenia pamięci masowej (takie jak dyski miniatur)</span><span class="sxs-lookup"><span data-stu-id="f021d-133">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="f021d-134">Karty Ethernet (w tym karty Ethernet i ładowanie)</span><span class="sxs-lookup"><span data-stu-id="f021d-134">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="f021d-135">Adaptery usb-C-to-3.5mm do cyfrowych audio</span><span class="sxs-lookup"><span data-stu-id="f021d-135">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="f021d-136">Cyfrowe zestawy audio USB-C (w tym adaptery nagłowne i ładowanie)</span><span class="sxs-lookup"><span data-stu-id="f021d-136">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="f021d-137">Zewnętrzne mikrofony USB-C[(system Windows Holographic, wersja 21H1](hololens-release-notes.md#windows-holographic-version-21h1) lub nowsza)</span><span class="sxs-lookup"><span data-stu-id="f021d-137">USB-C External Microphones ([Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher)</span></span>
- <span data-ttu-id="f021d-138">Mysz przewodowa</span><span class="sxs-lookup"><span data-stu-id="f021d-138">Wired mouse</span></span>
- <span data-ttu-id="f021d-139">Klawiatura przewodowa</span><span class="sxs-lookup"><span data-stu-id="f021d-139">Wired keyboard</span></span>
- <span data-ttu-id="f021d-140">Koncentratory z kombinacją pd (ładowanie za pomocą portu USB A i pd)</span><span class="sxs-lookup"><span data-stu-id="f021d-140">Combination PD hubs (USB A plus PD charging)</span></span>


> [!NOTE]
> <span data-ttu-id="f021d-141">W odpowiedzi na opinie klientów włączyliśmy ograniczoną obsługę łączności komórkowej bezpośrednio z urządzeniem HoloLens za pośrednictwem portu USB-C.</span><span class="sxs-lookup"><span data-stu-id="f021d-141">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="f021d-142">Aby uzyskać więcej informacji, zobacz [Connect to Cellular and 5G (Łączenie](hololens-cellular.md) z siecią komórkową i 5G).</span><span class="sxs-lookup"><span data-stu-id="f021d-142">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-external-microphone-support"></a><span data-ttu-id="f021d-143">Obsługa zewnętrznego mikrofonu USB-C</span><span class="sxs-lookup"><span data-stu-id="f021d-143">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f021d-144">Podłączanie **mikrofonu USB nie ustawi go** automatycznie jako urządzenia wejściowego .</span><span class="sxs-lookup"><span data-stu-id="f021d-144">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="f021d-145">Podczas podłączania zestawu słuchawki USB-C użytkownicy zauważą, że dźwięk telefonu komórkowego zostanie automatycznie przekierowany do słuchawki, ale system operacyjny HoloLens określa priorytet wewnętrznej macierzy mikrofonów nad innym urządzeniem wejściowym.</span><span class="sxs-lookup"><span data-stu-id="f021d-145">When plugging in a set of USB-C headphones, users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> <span data-ttu-id="f021d-146">**Aby użyć mikrofonu USB-C, wykonaj poniższe kroki.**</span><span class="sxs-lookup"><span data-stu-id="f021d-146">**In order to use a USB-C microphone follow the steps below.**</span></span>

> [!NOTE]
> <span data-ttu-id="f021d-147">Nie można używać mikrofonów zewnętrznych w kompilacjach wcześniejszych niż Windows Holographic w wersji [21H1](hololens-release-notes.md#windows-holographic-version-21h1) lub wyższej.</span><span class="sxs-lookup"><span data-stu-id="f021d-147">External microphones cannot be used in builds prior to [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher.</span></span> 

<span data-ttu-id="f021d-148">Użytkownicy mogą wybierać zewnętrzne mikrofony podłączone do dysku USB C przy użyciu **panelu Ustawień** dźwięku.</span><span class="sxs-lookup"><span data-stu-id="f021d-148">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="f021d-149">Mikrofony USB-C mogą służyć do wywoływania, nagrywania itp.</span><span class="sxs-lookup"><span data-stu-id="f021d-149">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="f021d-150">Otwórz aplikację **Ustawienia** i wybierz **pozycję Dźwięk**  >  **systemowy.**</span><span class="sxs-lookup"><span data-stu-id="f021d-150">Open the **Settings** app and select **System** > **Sound**.</span></span>

![Ustawienia dźwięku](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="f021d-152">Aby używać mikrofonów zewnętrznych z **usługą Remote Assist,** użytkownicy będą musieli kliknąć hiperlink "Zarządzanie urządzeniami dźwiękowymi".</span><span class="sxs-lookup"><span data-stu-id="f021d-152">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="f021d-153">Następnie użyj listy rozwijanej, aby ustawić zewnętrzny mikrofon jako **domyślny lub** domyślny **dla komunikacji.**</span><span class="sxs-lookup"><span data-stu-id="f021d-153">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="f021d-154">Wybranie **opcji** Domyślne oznacza, że zewnętrzny mikrofon będzie używany wszędzie.</span><span class="sxs-lookup"><span data-stu-id="f021d-154">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="f021d-155">Wybranie **opcji Domyślna** komunikacja oznacza, że zewnętrzny mikrofon będzie używany w uchęce Remote Assist i innych aplikacjach komunikacyjnych, ale macierz mikrofonu HoloLens może być nadal używana do innych zadań.</span><span class="sxs-lookup"><span data-stu-id="f021d-155">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![Zarządzanie urządzeniami dźwiękowymi](images/usbc-mic-2.png)

<br>

![Ustawianie domyślnego mikrofonu](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a><span data-ttu-id="f021d-158">A co z obsługą mikrofonu Bluetooth?</span><span class="sxs-lookup"><span data-stu-id="f021d-158">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="f021d-159">Niestety mikrofony Bluetooth nadal nie są obecnie obsługiwane na urządzeniu HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="f021d-159">Unfortunately, Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

#### <a name="troubleshooting-usb-c-microphones"></a><span data-ttu-id="f021d-160">Rozwiązywanie problemów z mikrofonami USB-C</span><span class="sxs-lookup"><span data-stu-id="f021d-160">Troubleshooting USB-C microphones</span></span>

<span data-ttu-id="f021d-161">Należy pamiętać, że niektóre mikrofony USB-C nieprawidłowo zgłaszają się jako mikrofon i *prelegent.*</span><span class="sxs-lookup"><span data-stu-id="f021d-161">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="f021d-162">Jest to problem z mikrofonem, a nie z urządzeniem HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f021d-162">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="f021d-163">Podczas podłączania jednego z tych mikrofonów do urządzenia HoloLens dźwięk może zostać utracony.</span><span class="sxs-lookup"><span data-stu-id="f021d-163">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="f021d-164">Na szczęście istnieje prosta poprawka.</span><span class="sxs-lookup"><span data-stu-id="f021d-164">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="f021d-165">W   ->  **ustawieniach Dźwięk** systemowy jawnie ustaw wbudowane osoby mówiące (sterownik audio funkcji analogicznej) jako domyślne  ->   **urządzenie**. </span><span class="sxs-lookup"><span data-stu-id="f021d-165">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="f021d-166">Urządzenie HoloLens powinno zapamiętać to ustawienie, nawet jeśli mikrofon zostanie później usunięty i ponownie podłączony.</span><span class="sxs-lookup"><span data-stu-id="f021d-166">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![Rozwiązywanie problemów z mikrofonami USB-C](images/usbc-mic-4.png)
### <a name="usb-c-hubs"></a><span data-ttu-id="f021d-168">Koncentratory USB-C</span><span class="sxs-lookup"><span data-stu-id="f021d-168">USB-C Hubs</span></span>

<span data-ttu-id="f021d-169">Niektórzy użytkownicy mogą wymagać połączenia wielu urządzeń jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="f021d-169">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="f021d-170">W przypadku użytkowników, którzy chcą używać mikrofonu [USB-C](#usb-c-external-microphone-support) wraz z innym połączonym urządzeniem, koncentratory USB-C mogą być dopasowane do potrzeb klienta.</span><span class="sxs-lookup"><span data-stu-id="f021d-170">For users who would like to use a [USB-C microphone](#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="f021d-171">Firma Microsoft nie przetestowała tych urządzeń ani nie może zalecać żadnych konkretnych marek.</span><span class="sxs-lookup"><span data-stu-id="f021d-171">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

<span data-ttu-id="f021d-172">**Wymagania dotyczące koncentratora USB-C i podłączonych urządzeń:**</span><span class="sxs-lookup"><span data-stu-id="f021d-172">**Requirements for USB-C hub and connected devices:**</span></span>

- <span data-ttu-id="f021d-173">Podłączone urządzenia nie mogą wymagać zainstalowania sterownika.</span><span class="sxs-lookup"><span data-stu-id="f021d-173">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="f021d-174">Całkowity pobór mocy wszystkich połączonych urządzeń musi być poniżej 4,5 Watów.</span><span class="sxs-lookup"><span data-stu-id="f021d-174">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="f021d-175">Nawiązywanie połączenia z miracastem</span><span class="sxs-lookup"><span data-stu-id="f021d-175">Connect to Miracast</span></span>

<span data-ttu-id="f021d-176">Aby użyć funkcji Miracast, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="f021d-176">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="f021d-177">Wykonaj jedną z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="f021d-177">Do one of the following:</span></span>  

   - <span data-ttu-id="f021d-178">Otwórz menu **Start** i wybierz **ikonę Wyświetl.**</span><span class="sxs-lookup"><span data-stu-id="f021d-178">Open the **Start** menu, and select the **Display** icon.</span></span>
   - <span data-ttu-id="f021d-179">Powiedz "Połącz", gdy spojrzysz na menu **Start.**</span><span class="sxs-lookup"><span data-stu-id="f021d-179">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="f021d-180">Na wyświetlonej liście urządzeń wybierz dostępne urządzenie.</span><span class="sxs-lookup"><span data-stu-id="f021d-180">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="f021d-181">Ukończ parowanie, aby rozpocząć rzutowanie.</span><span class="sxs-lookup"><span data-stu-id="f021d-181">Complete the pairing to begin projecting.</span></span>
