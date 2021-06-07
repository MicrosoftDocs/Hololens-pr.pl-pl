---
title: Baterii i ładowania
description: Jak ładować urządzenie HoloLens i używać zewnętrznych pakietów baterii.
ms.assetid: E0AB903E-454E-46F6-AB25-4DFA0A475B0C
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 05/14/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: 15ecc698a515987857f556fed97d74f861cd6b20
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379816"
---
# <a name="battery-and-charging"></a><span data-ttu-id="7df49-103">Baterii i ładowania</span><span class="sxs-lookup"><span data-stu-id="7df49-103">Battery and Charging</span></span>

<span data-ttu-id="7df49-104">Ta strona zawiera szczegółowe informacje o ładowaniu urządzenia HoloLens 2 i używaniu zewnętrznych pakietów baterii.</span><span class="sxs-lookup"><span data-stu-id="7df49-104">This page offers details about charging HoloLens 2 and using external battery packs.</span></span>

## <a name="included-charger"></a><span data-ttu-id="7df49-105">Uwzględniony wańcowy</span><span class="sxs-lookup"><span data-stu-id="7df49-105">Included Charger</span></span>

<span data-ttu-id="7df49-106">Urządzenie HoloLens 2 zapewnia do 9V przy 2A (18W).</span><span class="sxs-lookup"><span data-stu-id="7df49-106">The charger included with HoloLens 2 provides up to 9V @ 2A (18W).</span></span> <span data-ttu-id="7df49-107">Jeśli to możliwe, zdecydowanie zaleca się naliczanie opłat za pomocą dołączonej baterii.</span><span class="sxs-lookup"><span data-stu-id="7df49-107">When possible, it's highly recommended to charge using the included charger.</span></span>  

## <a name="specifications"></a><span data-ttu-id="7df49-108">Specyfikacje</span><span class="sxs-lookup"><span data-stu-id="7df49-108">Specifications</span></span>

<span data-ttu-id="7df49-109">Urządzenie HoloLens 2 można ładować za pomocą źródeł [zasilania USB](https://www.usb.org/usb-charger-pd) o mocy do 27 watów.</span><span class="sxs-lookup"><span data-stu-id="7df49-109">HoloLens 2 can be charged by [USB Power Delivery](https://www.usb.org/usb-charger-pd) sources up to 27 Watts.</span></span> <span data-ttu-id="7df49-110">Jeśli źródło jest w stanie dostarczyć co najmniej 10 watów, czas działania urządzenia HoloLens można wydłużyć (potencjalnie na czas nieokreślony dla niektórych obciążeń).</span><span class="sxs-lookup"><span data-stu-id="7df49-110">If the source is able supply at least 10 Watts, HoloLens operating time can be extended (potentially indefinitely for some workloads).</span></span> 

> [!NOTE]
> <span data-ttu-id="7df49-111">Użycie kabla ładowania USB-A do USB-C spowoduje ograniczenie opłaty do 7,5 Watów.</span><span class="sxs-lookup"><span data-stu-id="7df49-111">Using a USB-A to USB-C charging cable will limit the charge to 7.5 Watts.</span></span> <span data-ttu-id="7df49-112">Czas pracy nadal zostanie wydłużony, ale nie tak długo, jak długo będzie używać usb-C do C.</span><span class="sxs-lookup"><span data-stu-id="7df49-112">Operating time will still be extended, but not as long as using USB-C to C.</span></span>

<span data-ttu-id="7df49-113">Gdy urządzenie HoloLens jest w trybie rezerwy, 18 watów jest wystarczające, aby osiągnąć maksymalną stawkę za wewnętrzną baterii.</span><span class="sxs-lookup"><span data-stu-id="7df49-113">When HoloLens is in standby mode, 18 Watts is sufficient to reach the maximum charge rate for the internal battery.</span></span> <span data-ttu-id="7df49-114">Gdy urządzenie HoloLens jest w użyciu, stawka opłaty może zostać obniżona, ponieważ urządzenie HoloLens ma priorytet operacyjny od opłat.</span><span class="sxs-lookup"><span data-stu-id="7df49-114">When HoloLens is in use, the charge rate may be reduced since HoloLens prioritizes operating over charging.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7df49-115">Zaleca się, aby opłata za urządzenie HoloLens 2 była naliczana co najmniej przy wartości 5V/1,5 A.</span><span class="sxs-lookup"><span data-stu-id="7df49-115">It's recommended that HoloLens 2 be charged at 5V/1.5A minimum.</span></span> <span data-ttu-id="7df49-116">Nie należy używać zasilaczy, które nie mogą dostarczyć co najmniej 5V/1,5A.</span><span class="sxs-lookup"><span data-stu-id="7df49-116">Chargers that can't supply at least 5V/1.5A should not be used.</span></span> 

## <a name="external-battery-packs"></a><span data-ttu-id="7df49-117">Zewnętrzne pakiety baterii</span><span class="sxs-lookup"><span data-stu-id="7df49-117">External Battery Packs</span></span>

<span data-ttu-id="7df49-118">Z urządzeniem HoloLens 2 można używać pakietów baterii, które spełniają powyższe specyfikacje.</span><span class="sxs-lookup"><span data-stu-id="7df49-118">Battery packs that meet the specifications above can be used with HoloLens 2.</span></span> <span data-ttu-id="7df49-119">Należy jednak pamiętać, że niektóre pakiety baterii USB-C są ładowane i zapewniają zasilanie za pośrednictwem tego samego portu USB-C.</span><span class="sxs-lookup"><span data-stu-id="7df49-119">However, note that some USB-C battery packs recharge and provide power through the same USB-C port.</span></span> <span data-ttu-id="7df49-120">Ważne jest, aby te pakiety baterii implementują [try. SRC,](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) aby upewnić się, że urządzenie HoloLens jest ładowane, a nie naliczane z niego opłaty.</span><span class="sxs-lookup"><span data-stu-id="7df49-120">It's important that these battery packs implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) to ensure they charge HoloLens rather than charge from it.</span></span> 

## <a name="managing-heat"></a><span data-ttu-id="7df49-121">Zarządzanie ciepłom</span><span class="sxs-lookup"><span data-stu-id="7df49-121">Managing Heat</span></span>

<span data-ttu-id="7df49-122">Podobnie jak w przypadku dowolnego urządzenia, ładowanie urządzenia HoloLens generuje ciepło.</span><span class="sxs-lookup"><span data-stu-id="7df49-122">As with any device, charging HoloLens generates heat.</span></span> <span data-ttu-id="7df49-123">Im szybsze ładowanie, tym więcej ciepła jest generowane.</span><span class="sxs-lookup"><span data-stu-id="7df49-123">The more rapid the charge, the more heat is generated.</span></span> <span data-ttu-id="7df49-124">Ponadto uruchomienie ładowania na niższym poziomie baterii spowoduje wygenerowanie większej energii cieplnej niż w przypadku, gdy poziom naładowania baterii jest w większości pełny.</span><span class="sxs-lookup"><span data-stu-id="7df49-124">Also, starting a charge at a lower battery level will generate more heat than starting a charge when the battery is mostly full.</span></span> <span data-ttu-id="7df49-125">Klienci, którzy muszą korzystać z urządzenia HoloLens przez dłuższy czas w gorących środowiskach, mogą używać następujących technik:</span><span class="sxs-lookup"><span data-stu-id="7df49-125">Customers who need to operate HoloLens for extended periods of time in hot environments can use the following techniques:</span></span>

- <span data-ttu-id="7df49-126">Urządzenie HoloLens 2 można podłączyć do zewnętrznego źródła zasilania nawet wtedy, gdy wewnętrzna bateria jest w pełni obciążona.</span><span class="sxs-lookup"><span data-stu-id="7df49-126">It's OK to connect HoloLens 2 to an external power source even when the internal battery is fully charged.</span></span>
- <span data-ttu-id="7df49-127">Po wyczerpaniu baterii zewnętrznej urządzenie HoloLens będzie nadal działać na wewnętrznej baterii.</span><span class="sxs-lookup"><span data-stu-id="7df49-127">When an external battery is depleted, HoloLens will continue operating on its internal battery.</span></span>    
- <span data-ttu-id="7df49-128">Jeśli po powyższych krokach nadal występuje problem z ciepłom, rozważ użycie baterii lub baterii, która ogranicza poziom ładowania do 1,5 A.</span><span class="sxs-lookup"><span data-stu-id="7df49-128">If heat is still an issue after following steps above, consider using a charger or battery pack that limits charging to 1.5A.</span></span> <span data-ttu-id="7df49-129">Pamiętaj, że ta opcja nie zapewni tak dużo czasu pracy, ponieważ poziom naładowania baterii wewnętrznej będzie nadal powoli wyczerpywalny.</span><span class="sxs-lookup"><span data-stu-id="7df49-129">Note that this option won't provide as much operating time since the internal battery will still slowly deplete.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="7df49-130">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="7df49-130">Troubleshooting</span></span>


### <a name="hololens-charges-external-battery"></a><span data-ttu-id="7df49-131">Zewnętrzna bateria ładowania urządzenia HoloLens</span><span class="sxs-lookup"><span data-stu-id="7df49-131">HoloLens Charges External Battery</span></span>
<span data-ttu-id="7df49-132">Jeśli urządzenie HoloLens 2 jest zasilane z baterii zewnętrznej, a nie przez nie, oznacza to, że baterii nie implementuje [try. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20).</span><span class="sxs-lookup"><span data-stu-id="7df49-132">If HoloLens 2 charges an external battery rather than being charged by it, this indicates that the battery doesn't implement [TRY.SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20).</span></span> <span data-ttu-id="7df49-133">Przełączanie do nowszego pakietu baterii jest zalecanym sposobem rozwiązania tego problemu, ale alternatywnie możesz spróbować przełączyć się na kabel USB-A na USB-C.</span><span class="sxs-lookup"><span data-stu-id="7df49-133">Switching to a newer battery pack is the recommended way to solve this issue, but alternatively you can try switching to a USB-A to USB-C cable.</span></span> <span data-ttu-id="7df49-134">Należy pamiętać, że spowoduje to ograniczenie stawki do 7,5 watów.</span><span class="sxs-lookup"><span data-stu-id="7df49-134">Keep in mind this will limit the charging rate to 7.5 watts.</span></span>
