---
title: Bezpieczeństwo sieci
description: zabezpieczenia sieci
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: zabezpieczenia, hololens, sieć, zabezpieczenia sieci
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: c5ac42ee272becfd404a1f00931fa05237e31993288fee16d79d73f79aade646
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665390"
---
# <a name="network-security"></a>Bezpieczeństwo sieci

## <a name="network-protocols"></a>Protokoły sieciowe

Nieaktualny system NetBIOS (Network Basic Input/Output System) był powszechnie używany w przeszłości w scenariuszach sieci LAN — często do rozpoznawania nazw komputera i folderów udostępnionych. Jednak z czasem netBIOS okazał się podatny na wiele ataków, a jego istotność spadała na rzecz innych bezpieczniejszych protokołów. Aby usunąć ten problem z luką w zabezpieczeniach, HoloLens 2 wyeliminowała kod związany z systemem operacyjnym NetBIOS.

Protokoły TLS (Transport Layer Security) stale ewoluują. Aby być na bieżąco z różnymi lukami w zabezpieczeniach, które zostały ujawnione w tym obszarze, branża obliczeniowa została przesuowana do nowszej i bardziej efektywnej wersji. Ze względu na czas wymagany do wdrożenia nowych wersji protokołu TLS przez wszystkie wdrożenia serwera można zaimplementować mechanizm rezerwowy, który umożliwia klientowi i serwerom w różnych domyślnych wersjach protokołu nadal komunikowanie się w okresie przejściowym.

## <a name="secure-connectivity"></a>Bezpieczna łączność 

Zapora Windows Defender zapewnia krytyczne funkcje zabezpieczania łączności z urządzeniami. W HoloLens 2 zapora jest zawsze włączona i nie ma możliwości wyłączenia jej programowo ani za pośrednictwem interfejsu użytkownika.

Prywatność dostępu zdalnego i połączeń dla klientów mobilnych można zapewnić za pośrednictwem platformy wtyczek [sieci VPN platformy uniwersalnej systemu Windows.](/uwp/api/Windows.Networking.Vpn?view=winrt-19041) Dostawcy sieci VPN innych firm mogą tworzyć własne wtyczki przy użyciu interfejsów API winRT, które będą uruchamiane w piaskownicy AppContainer, eliminując złożoność i problemy często związane z pisaniem sterowników na poziomie systemu.
