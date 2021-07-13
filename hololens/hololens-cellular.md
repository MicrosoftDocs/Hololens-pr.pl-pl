---
title: Połączenie do sieci komórkowej i 5G
description: Nawiązywanie połączenia z sieciami komórkowymi z HoloLens rzeczywistości mieszanej.
ms.assetid: f1aaadce-8762-41f8-bfeb-3b6067a2ec78
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 02/24/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: 6f7da0263e8637486f0151fd2b9da55da8feccc1
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635844"
---
# <a name="connect-to-cellular-and-5g"></a><span data-ttu-id="585eb-103">Połączenie do sieci komórkowej i 5G</span><span class="sxs-lookup"><span data-stu-id="585eb-103">Connect to Cellular and 5G</span></span>

<span data-ttu-id="585eb-104">HoloLens 2 obsługuje dwie metody łączenia się z sieciami komórkowymi i 5G:</span><span class="sxs-lookup"><span data-stu-id="585eb-104">HoloLens 2 supports two methods for connecting to cellular and 5G networks:</span></span>

- <span data-ttu-id="585eb-105">Sieć Wi-Fi ad hoc dostarczana przez urządzenie komórkowe, często nazywana "hotspotem"</span><span class="sxs-lookup"><span data-stu-id="585eb-105">An ad hoc WiFi network provided by the cellular device, commonly referred to as a "Hotspot"</span></span>
- <span data-ttu-id="585eb-106">Ograniczona obsługa urządzeń z tetheredami USB-C</span><span class="sxs-lookup"><span data-stu-id="585eb-106">Limited support for USB-C tethered devices</span></span>

## <a name="hotspot-wifi"></a><span data-ttu-id="585eb-107">Hotspot (WiFi)</span><span class="sxs-lookup"><span data-stu-id="585eb-107">Hotspot (WiFi)</span></span>

<span data-ttu-id="585eb-108">Większość potrzeb w zakresie łączności komórkowej można spełnić za pomocą hotspotu.</span><span class="sxs-lookup"><span data-stu-id="585eb-108">Most cellular connectivity needs can be met with a hotspot.</span></span> <span data-ttu-id="585eb-109">HoloLens 2 sieć Wi-Fi obsługuje sieć 802.11ac, która może zapewnić wymagania dotyczące przepustowości i opóźnienia niezbędne w większości typowych przypadków użycia.</span><span class="sxs-lookup"><span data-stu-id="585eb-109">HoloLens 2 WiFi supports 802.11ac, which can provide the bandwidth and latency requirements necessary for most common use cases.</span></span> <span data-ttu-id="585eb-110">Sieć Wi-Fi jest również bezpłatna i zapewnia zgodność z największą liczbą urządzeń komórkowych.</span><span class="sxs-lookup"><span data-stu-id="585eb-110">WiFi is also cable-free and offers compatibility with the largest number of cellular devices.</span></span>

### <a name="connecting-to-a-hotspot"></a><span data-ttu-id="585eb-111">Nawiązywanie połączenia z hotspotem</span><span class="sxs-lookup"><span data-stu-id="585eb-111">Connecting to a Hotspot</span></span>

1. <span data-ttu-id="585eb-112">Zapoznaj się z podręcznikiem urządzenia, aby dowiedzieć się, jak włączyć jego tryb hotspotu.</span><span class="sxs-lookup"><span data-stu-id="585eb-112">Consult your device's manual on how to enable its hotspot mode.</span></span>
1. <span data-ttu-id="585eb-113">Włącz tryb hotspot, podając nazwę sieci, a także znane hasło.</span><span class="sxs-lookup"><span data-stu-id="585eb-113">Enable hotspot mode, supplying a name for the network as well as a known password.</span></span>
1. <span data-ttu-id="585eb-114">W HoloLens 2 sieci znajdź sieć Wi-Fi utworzoną w kroku 2 i dołącz ją.</span><span class="sxs-lookup"><span data-stu-id="585eb-114">In HoloLens 2 Network settings, locate the WiFi network created in step 2 and join it.</span></span>

## <a name="usb-c-tethering"></a><span data-ttu-id="585eb-115">USB-C Tethering</span><span class="sxs-lookup"><span data-stu-id="585eb-115">USB-C Tethering</span></span>

<span data-ttu-id="585eb-116">Tethering USB-C może zapewnić mniejsze opóźnienie dla zaawansowanych obciążeń, które go potrzebują.</span><span class="sxs-lookup"><span data-stu-id="585eb-116">USB-C tethering can provide lower latency for advanced workloads that need it.</span></span> <span data-ttu-id="585eb-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), na przykład może korzystać z tetheringu.</span><span class="sxs-lookup"><span data-stu-id="585eb-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), for example, can benefit from tethering.</span></span> <span data-ttu-id="585eb-118">Należy pamiętać, że tethering wymaga kabla między urządzeniem komórkowym i HoloLens, a tethering jest obsługiwany przez ograniczoną liczbę urządzeń.</span><span class="sxs-lookup"><span data-stu-id="585eb-118">Note that tethering requires a cable between the cellular device and HoloLens, and tethering is supported by a limited number of devices.</span></span>

### <a name="usb-c-compatibility"></a><span data-ttu-id="585eb-119">Zgodność z usb-C</span><span class="sxs-lookup"><span data-stu-id="585eb-119">USB-C compatibility</span></span>

<span data-ttu-id="585eb-120">Z platformą Holographic w wersji 2004 lub nowszej można używać ograniczonej liczby urządzeń, które Windows jako adapter Ethernet.</span><span class="sxs-lookup"><span data-stu-id="585eb-120">A limited number of devices that present themselves as an ethernet adaptor can be used with Windows Holographic version 2004 and later.</span></span>

<span data-ttu-id="585eb-121">Urządzenia, które nie są obecne jako karty Ethernet, muszą obsługiwać ogólny sterownik [RNDIS firmy](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) Microsoft.</span><span class="sxs-lookup"><span data-stu-id="585eb-121">Devices that do not present themselves as an ethernet adapter must support the generic Microsoft [RNDIS](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver.</span></span> <span data-ttu-id="585eb-122">Jednak tylko ograniczona liczba tych urządzeń jest zgodna z HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="585eb-122">But, only a limited number of those devices are compatible with HoloLens 2.</span></span> <span data-ttu-id="585eb-123">Aby uzyskać szczegółowe informacje na temat tego, czy obsługuje ono ogólny sterownik RNDIS firmy Microsoft, skontaktuj się z producentem urządzenia.</span><span class="sxs-lookup"><span data-stu-id="585eb-123">Please consult your device's manufacturer for details on whether it supports the generic Microsoft RNDIS driver.</span></span>

<span data-ttu-id="585eb-124">Urządzenia, które nie są zgodne ze standardem RNDIS lub wymagają zainstalowania sterownika lub aplikacji, nie są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="585eb-124">Devices that are not RNDIS compatible, or require a driver or application to be installed, are not supported.</span></span>

<span data-ttu-id="585eb-125">Firma Microsoft nie utrzymuje listy zgodnych urządzeń, ale w tym miejscu jest dyskusyjna społeczności na [ten temat.](https://aka.ms/HLCommunityCell)</span><span class="sxs-lookup"><span data-stu-id="585eb-125">While Microsoft does not maintain a list of compatible devices, there is a community discussion on the topic [here](https://aka.ms/HLCommunityCell).</span></span>

### <a name="connecting-to-a-tethered-device"></a><span data-ttu-id="585eb-126">Nawiązywanie połączenia z urządzeniem połączonym</span><span class="sxs-lookup"><span data-stu-id="585eb-126">Connecting to a tethered device</span></span>

1. <span data-ttu-id="585eb-127">Zapoznaj się z podręcznikiem urządzenia, aby dowiedzieć się, jak włączyć udostępnianie danych za pośrednictwem portu USB.</span><span class="sxs-lookup"><span data-stu-id="585eb-127">Consult your device's manual on how to enable data sharing over USB.</span></span> <span data-ttu-id="585eb-128">To ustawienie jest często określane jako "Tethering USB", "Udostępnianie danych" lub "Modem USB".</span><span class="sxs-lookup"><span data-stu-id="585eb-128">This setting is often referred to as "USB Tethering", "Data Sharing" or "USB Modem".</span></span>
1. <span data-ttu-id="585eb-129">Włącz udostępnianie danych za pośrednictwem portu USB.</span><span class="sxs-lookup"><span data-stu-id="585eb-129">Enable data sharing over USB.</span></span>
1. <span data-ttu-id="585eb-130">Połączenie urządzenie do portu HoloLens USB-C.</span><span class="sxs-lookup"><span data-stu-id="585eb-130">Connect your device to the HoloLens USB-C port.</span></span>
1. <span data-ttu-id="585eb-131">W HoloLens 2 ustawienia sieci urządzenie zostanie automatycznie wyświetlone jako połączenie Ethernet.</span><span class="sxs-lookup"><span data-stu-id="585eb-131">In HoloLens 2 Network settings, the device will automatically appear as an Ethernet connection.</span></span>
