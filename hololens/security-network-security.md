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
ms.openlocfilehash: 416a4f7b9e3cf2e52b79fb29f50424a9c573a18a
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036594"
---
# <a name="network-security"></a>Bezpieczeństwo sieci

## <a name="network-protocols"></a>Protokoły sieciowe

Nieaktualny system NetBIOS (Network Basic Input/Output System) był powszechnie używany w przeszłości w scenariuszach sieci LAN — często do zapewniania rozpoznawania nazw komputerowi i folderom udostępnionym. Jednak z czasem netBIOS okazał się podatny na wiele ataków, a jego istotność spadła na rzecz innych bezpieczniejszych protokołów. Aby usunąć ten problem z luką w zabezpieczeniach, HoloLens 2 wyeliminował kod związany z netBIOS z systemu operacyjnego.

Protokoły TLS (Transport Layer Security) stale ewoluują. Aby być na bieżąco z różnymi lukami w zabezpieczeniach, które zostały ujawnione w tym obszarze, branża obliczeniowa została przesuowana do nowszej i bardziej efektywnej wersji. Ze względu na czas wymagany do wdrożenia nowych wersji protokołu TLS przez wszystkie wdrożenia serwera można zaimplementować mechanizm rezerwowy, który umożliwia klientowi i serwerom w różnych domyślnych wersjach protokołu nadal komunikowanie się w okresie przejściowym.

## <a name="secure-connectivity"></a>Bezpieczna łączność 

Zapora Windows Defender zapewnia krytyczne funkcje w celu zabezpieczenia łączności urządzenia. W HoloLens 2 zapora jest zawsze włączona i nie ma możliwości wyłączenia jej programowo ani za pośrednictwem interfejsu użytkownika.

Prywatność dostępu zdalnego i połączeń dla klientów mobilnych można zapewnić za pośrednictwem platformy wtyczek [sieci VPN platformy uniwersalnej systemu Windows.](/uwp/api/Windows.Networking.Vpn?view=winrt-19041) Dostawcy sieci VPN innych firm mogą tworzyć własne wtyczki przy użyciu interfejsów API WinRT, które będą uruchamiane w piaskownicy AppContainer, eliminując złożoność i problemy często związane z pisaniem sterowników na poziomie systemu.
