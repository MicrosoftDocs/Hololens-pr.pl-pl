---
title: Bezpieczeństwo sieci
description: zabezpieczenia sieci
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: zabezpieczenia, hololens, sieć, zabezpieczenia sieciowe
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f1e5304408a9a9543eb0703ad7321725484eef01
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379711"
---
# <a name="network-security"></a>Bezpieczeństwo sieci

## <a name="network-protocols"></a>Protokoły sieciowe

Nieaktualny system NetBIOS (Network Basic Input/Output System) był powszechnie używany w przeszłości w scenariuszach sieci LAN — często do zapewniania rozpoznawania nazw komputerowi i folderom udostępnionym. Jednak z czasem netBIOS okazał się podatny na wiele ataków, a jego istotność spadła na rzecz innych bezpieczniejszych protokołów. Aby usunąć ten problem z luką w zabezpieczeniach, system HoloLens 2 wyeliminował kod związany z systemem NetBIOS z systemu operacyjnego.

Protokoły TLS (Transport Layer Security) stale ewoluują. Aby być na bieżąco z różnymi lukami w zabezpieczeniach, które zostały ujawnione w tym obszarze, branża obliczeniowa została przesuowana do nowszej i bardziej efektywnej wersji. Ze względu na czas wymagany do wdrożenia nowych wersji protokołu TLS przez wszystkie wdrożenia serwera można zaimplementować mechanizm rezerwowy, który umożliwia klientowi i serwerom w różnych domyślnych wersjach protokołów nadal komunikowanie się w okresie przejściowym.

## <a name="secure-connectivity"></a>Bezpieczna łączność 

Ten Zapora Windows Defender zapewnia krytyczne funkcje w celu zabezpieczenia łączności urządzeń. W przypadku urządzenia HoloLens 2 zapora jest zawsze włączona i nie ma możliwości wyłączenia jej programowo ani za pośrednictwem interfejsu użytkownika.

Prywatność dostępu zdalnego i połączeń dla klientów mobilnych można zapewnić za pośrednictwem platformy wtyczek [sieci VPN platformy uniwersalnej systemu Windows.](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041) Dostawcy sieci VPN innych firm mogą tworzyć własne wtyczki przy użyciu interfejsów API WinRT, które będą uruchamiane w piaskownicy AppContainer, eliminując złożoność i problemy często związane z pisaniem sterowników na poziomie systemu.
