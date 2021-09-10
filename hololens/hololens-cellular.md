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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427709"
---
# <a name="connect-to-cellular-and-5g"></a>Połączenie do sieci komórkowej i 5G

HoloLens 2 obsługuje dwie metody łączenia się z sieciami komórkowymi i 5G:

- Sieć Wi-Fi ad hoc dostarczana przez urządzenie komórkowe, często nazywana "hotspotem"
- Ograniczona obsługa urządzeń z tethered usb-C

## <a name="hotspot-wifi"></a>Hotspot (WiFi)

Większość potrzeb w zakresie łączności komórkowej można spełnić w przypadku hotspotu. HoloLens 2 sieć Wi-Fi obsługuje sieć 802.11ac, która może zapewnić wymagania dotyczące przepustowości i opóźnienia niezbędne do większości typowych przypadków użycia. Sieć Wi-Fi jest również bezpłatna i zapewnia zgodność z największą liczbą urządzeń komórkowych.

### <a name="connecting-to-a-hotspot"></a>Nawiązywanie połączenia z hotspotem

1. Zapoznaj się z podręcznikiem urządzenia, aby dowiedzieć się, jak włączyć jego tryb hotspotu.
1. Włącz tryb hotspot, podając nazwę sieci, a także znane hasło.
1. W HoloLens 2 Sieci znajdź sieć Wi-Fi utworzoną w kroku 2 i dołącz ją.

## <a name="usb-c-tethering"></a>USB-C Tethering

Tethering USB-C może zapewnić mniejsze opóźnienie dla zaawansowanych obciążeń, które go potrzebują. [Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), na przykład może korzystać z tetheringu. Należy pamiętać, że tethering wymaga kabla między urządzeniem komórkowym i HoloLens, a tethering jest obsługiwany przez ograniczoną liczbę urządzeń.

### <a name="usb-c-compatibility"></a>Zgodność z usb-C

Z platformą Holographic w wersji 2004 lub nowszej można używać ograniczonej liczby urządzeń, które Windows jako adapter Ethernet.

Urządzenia, które nie są obecne jako karty Ethernet, muszą obsługiwać ogólny sterownik [RNDIS](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) firmy Microsoft. Jednak tylko ograniczona liczba tych urządzeń jest zgodna z HoloLens 2. Aby uzyskać szczegółowe informacje na temat tego, czy obsługuje ono ogólny sterownik RNDIS firmy Microsoft, skontaktuj się z producentem urządzenia.

Urządzenia, które nie są zgodne ze standardem RNDIS lub wymagają zainstalowania sterownika lub aplikacji, nie są obsługiwane.

Firma Microsoft nie utrzymuje listy zgodnych urządzeń, ale w tym miejscu znajduje się dyskusja społeczności na [ten temat.](https://aka.ms/HLCommunityCell)

### <a name="connecting-to-a-tethered-device"></a>Nawiązywanie połączenia z urządzeniem połączonym

1. Zapoznaj się z podręcznikiem urządzenia, aby dowiedzieć się, jak włączyć udostępnianie danych za pośrednictwem portu USB. To ustawienie jest często określane jako "Tethering USB", "Udostępnianie danych" lub "Modem USB".
1. Włącz udostępnianie danych za pośrednictwem portu USB.
1. Połączenie urządzenie do portu HoloLens USB-C.
1. W HoloLens 2 ustawienia sieci urządzenie zostanie automatycznie wyświetlone jako połączenie Ethernet.
