---
title: Połączenie do sieci komórkowej i 5G
description: Łączenie z sieciami komórkowymi z urządzeń HoloLens rzeczywistości mieszanej.
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
ms.openlocfilehash: 0a31ff0af0af5b60fc0a44ef8fc5a85b5b50e766201d5441d508fd23dd0369e4
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664489"
---
# <a name="connect-to-cellular-and-5g"></a>Połączenie do sieci komórkowej i 5G

HoloLens 2 obsługuje dwie metody łączenia się z sieciami komórkowymi i 5G:

- Sieć Wi-Fi ad hoc dostarczana przez urządzenie komórkowe, często nazywana "hotspotem"
- Ograniczona obsługa urządzeń z tethered USB-C

## <a name="hotspot-wifi"></a>Hotspot (WiFi)

Większość potrzeb w zakresie łączności komórkowej można spełnić za pomocą hotspotu. HoloLens 2 sieć Wi-Fi obsługuje sieć 802.11ac, która może zapewnić wymagania dotyczące przepustowości i opóźnienia niezbędne do większości typowych przypadków użycia. Sieć Wi-Fi jest również bezpłatna i zapewnia zgodność z największą liczbą urządzeń komórkowych.

### <a name="connecting-to-a-hotspot"></a>Nawiązywanie połączenia z hotspotem

1. Zapoznaj się z podręcznikiem urządzenia, aby dowiedzieć się, jak włączyć tryb hotspotu.
1. Włącz tryb hotspot, podając nazwę sieci oraz znane hasło.
1. W HoloLens 2 sieci znajdź sieć Wi-Fi utworzoną w kroku 2 i dołącz ją.

## <a name="usb-c-tethering"></a>USB-C Tethering

Tethering USB-C może zapewnić mniejsze opóźnienie dla zaawansowanych obciążeń, które tego potrzebują. [Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), na przykład może korzystać z tetheringu. Należy pamiętać, że tethering wymaga kabla między urządzeniem komórkowym a HoloLens, a tethering jest obsługiwany przez ograniczoną liczbę urządzeń.

### <a name="usb-c-compatibility"></a>Zgodność z usb-C

Z platformą Holographic w wersji 2004 lub nowszej można używać ograniczonej liczby urządzeń, które Windows jako adapter Ethernet.

Urządzenia, które nie są obecne jako karty Ethernet, muszą obsługiwać ogólny sterownik [RNDIS firmy](/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) Microsoft. Jednak tylko ograniczona liczba tych urządzeń jest zgodna z HoloLens 2. Skontaktuj się z producentem urządzenia, aby uzyskać szczegółowe informacje na temat tego, czy obsługuje ono ogólny sterownik RNDIS firmy Microsoft.

Urządzenia, które nie są zgodne ze standardem RNDIS lub wymagają zainstalowania sterownika lub aplikacji, nie są obsługiwane.

Firma Microsoft nie utrzymuje listy zgodnych urządzeń, ale w tym miejscu znajduje się omówienie społeczności na [ten temat.](https://aka.ms/HLCommunityCell)

### <a name="connecting-to-a-tethered-device"></a>Nawiązywanie połączenia z urządzeniem połączonym

1. Zapoznaj się z podręcznikiem urządzenia, aby dowiedzieć się, jak włączyć udostępnianie danych za pośrednictwem portu USB. To ustawienie jest często określane jako "Tethering USB", "Udostępnianie danych" lub "Modem USB".
1. Włącz udostępnianie danych za pośrednictwem portu USB.
1. Połączenie urządzenie do portu HoloLens USB-C.
1. W HoloLens 2 ustawienia sieci urządzenie zostanie automatycznie wyświetlone jako połączenie Ethernet.
