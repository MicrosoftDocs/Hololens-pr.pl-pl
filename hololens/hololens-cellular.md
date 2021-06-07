---
title: Nawiązywanie połączenia z siecią komórkową i siecią 5G
description: Nawiązywanie połączenia z sieciami komórkowymi z urządzeń HoloLens rzeczywistości mieszanej.
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
ms.openlocfilehash: 8318d011d6a593c1036b6bcf6f7973870b0dc294
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379679"
---
# <a name="connect-to-cellular-and-5g"></a>Nawiązywanie połączenia z siecią komórkową i siecią 5G

Urządzenie HoloLens 2 obsługuje dwie metody łączenia się z sieciami komórkowymi i 5G:

- Sieć Wi-Fi ad hoc dostarczana przez urządzenie komórkowe, często nazywana "hotspotem"
- Ograniczona obsługa urządzeń z tetheredami USB-C

## <a name="hotspot-wifi"></a>Hotspot (WiFi)

Większość potrzeb w zakresie łączności komórkowej można spełnić za pomocą hotspotu. Sieć Wi-Fi urządzenia HoloLens 2 obsługuje technologię 802.11ac, która może zapewnić wymagania dotyczące przepustowości i opóźnienia niezbędne w większości typowych przypadków użycia. Sieć Wi-Fi jest również bezpłatna i zapewnia zgodność z największą liczbą urządzeń komórkowych.

### <a name="connecting-to-a-hotspot"></a>Nawiązywanie połączenia z hotspotem

1. Zapoznaj się z podręcznikiem urządzenia, aby dowiedzieć się, jak włączyć jego tryb hotspotu.
1. Włącz tryb hotspot, podając nazwę sieci, a także znane hasło.
1. W ustawieniach sieciowych urządzenia HoloLens 2 znajdź sieć Wi-Fi utworzoną w kroku 2 i dołącz ją.

## <a name="usb-c-tethering"></a>USB-C Tethering

Tethering USB-C może zapewnić mniejsze opóźnienie dla zaawansowanych obciążeń, które go potrzebują. [Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), na przykład może korzystać z tetheringu. Należy pamiętać, że tethering wymaga kabla między urządzeniem komórkowym i urządzeniem HoloLens, a tethering jest obsługiwany przez ograniczoną liczbę urządzeń.

### <a name="usb-c-compatibility"></a>Zgodność z usb-C

Z systemem Windows Holographic w wersji 2004 lub nowszej można korzystać z ograniczonej liczby urządzeń, które są obecne jako adapter Ethernet.

Urządzenia, które nie są obecne jako karty Ethernet, muszą obsługiwać ogólny sterownik [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) firmy Microsoft. Jednak tylko ograniczona liczba tych urządzeń jest zgodna z urządzeniem HoloLens 2. Aby uzyskać szczegółowe informacje na temat tego, czy obsługuje ono ogólny sterownik RNDIS firmy Microsoft, skontaktuj się z producentem urządzenia.

Urządzenia, które nie są zgodne ze standardem RNDIS lub wymagają zainstalowania sterownika lub aplikacji, nie są obsługiwane.

Firma Microsoft nie utrzymuje listy zgodnych urządzeń, ale w tym miejscu jest dyskusyjna społeczności na [ten temat.](https://aka.ms/HLCommunityCell)

### <a name="connecting-to-a-tethered-device"></a>Nawiązywanie połączenia z urządzeniem połączonym

1. Zapoznaj się z podręcznikiem urządzenia, aby dowiedzieć się, jak włączyć udostępnianie danych za pośrednictwem portu USB. To ustawienie jest często określane jako "Tethering USB", "Udostępnianie danych" lub "Modem USB".
1. Włącz udostępnianie danych za pośrednictwem portu USB.
1. Podłącz urządzenie do portu USB-C urządzenia HoloLens.
1. W ustawieniach sieciowych urządzenia HoloLens 2 urządzenie zostanie automatycznie wyświetlone jako połączenie Ethernet.
