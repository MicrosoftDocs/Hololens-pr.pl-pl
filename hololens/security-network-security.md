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
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640495"
---
# <a name="network-security"></a><span data-ttu-id="a8cd7-104">Bezpieczeństwo sieci</span><span class="sxs-lookup"><span data-stu-id="a8cd7-104">Network security</span></span>

## <a name="network-protocols"></a><span data-ttu-id="a8cd7-105">Protokoły sieciowe</span><span class="sxs-lookup"><span data-stu-id="a8cd7-105">Network protocols</span></span>

<span data-ttu-id="a8cd7-106">Nieaktualny system NetBIOS (Network Basic Input/Output System) był powszechnie używany w przeszłości w scenariuszach sieci LAN — często do zapewniania rozpoznawania nazw komputerowi i folderom udostępnionym.</span><span class="sxs-lookup"><span data-stu-id="a8cd7-106">The outdated NetBIOS (Network Basic Input/Output System) was widely used in the past in LAN scenarios – often for providing name resolution to a computer and shared folders.</span></span> <span data-ttu-id="a8cd7-107">Jednak z czasem netBIOS okazał się podatny na wiele ataków, a jego istotność spadła na rzecz innych bezpieczniejszych protokołów.</span><span class="sxs-lookup"><span data-stu-id="a8cd7-107">But over time, NetBIOS proved to be susceptible to multiple attacks, and its relevance decreased in favor of other more secure protocols.</span></span> <span data-ttu-id="a8cd7-108">Aby usunąć ten problem z luką w zabezpieczeniach, HoloLens 2 wyeliminował kod związany z systemem NetBIOS z systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="a8cd7-108">To remove this vulnerability issue, HoloLens 2 has eliminated the NetBIOS-related code from the operating system.</span></span>

<span data-ttu-id="a8cd7-109">Protokoły TLS (Transport Layer Security) stale ewoluują.</span><span class="sxs-lookup"><span data-stu-id="a8cd7-109">TLS (Transport Layer Security) protocols are constantly evolving.</span></span> <span data-ttu-id="a8cd7-110">Aby być na bieżąco z różnymi lukami w zabezpieczeniach, które zostały ujawnione w tym obszarze, branża obliczeniowa została przesuowana do nowszej i bardziej efektywnej wersji.</span><span class="sxs-lookup"><span data-stu-id="a8cd7-110">To keep up with the various security exploits that have been uncovered in this area, the computing industry has graduated to newer and more effective versions.</span></span> <span data-ttu-id="a8cd7-111">Ze względu na czas wymagany do wdrożenia nowych wersji protokołu TLS przez wszystkie wdrożenia serwera można zaimplementować mechanizm rezerwowy, który umożliwia klientowi i serwerom w różnych domyślnych wersjach protokołów nadal komunikowanie się w okresie przejściowym.</span><span class="sxs-lookup"><span data-stu-id="a8cd7-111">Due to the time required for all server deployments to adopt the new TLS protocol versions, a fallback mechanism can be implemented that permits the client and servers on different default protocol versions to still be able to communicate during the transition period.</span></span>

## <a name="secure-connectivity"></a><span data-ttu-id="a8cd7-112">Bezpieczna łączność</span><span class="sxs-lookup"><span data-stu-id="a8cd7-112">Secure connectivity</span></span> 

<span data-ttu-id="a8cd7-113">Zapora Windows Defender zapewnia krytyczne funkcje w celu zabezpieczenia łączności urządzenia.</span><span class="sxs-lookup"><span data-stu-id="a8cd7-113">The Windows Defender Firewall delivers critical functionality to secure device connectivity.</span></span> <span data-ttu-id="a8cd7-114">W HoloLens 2 zapora jest zawsze włączona i nie ma możliwości wyłączenia jej programowo ani za pośrednictwem interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="a8cd7-114">With HoloLens 2, the firewall is always enabled and there are no ways to disable it programmatically or through the UI.</span></span>

<span data-ttu-id="a8cd7-115">Prywatność dostępu zdalnego i połączeń dla klientów mobilnych można zapewnić za pośrednictwem platformy wtyczek [sieci VPN platformy uniwersalnej systemu Windows.](/uwp/api/Windows.Networking.Vpn?view=winrt-19041)</span><span class="sxs-lookup"><span data-stu-id="a8cd7-115">Remote access and connection privacy for mobile clients can be assured through the [UWP VPN plug-in platform](/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span></span> <span data-ttu-id="a8cd7-116">Dostawcy sieci VPN innych firm mogą tworzyć własne wtyczki przy użyciu interfejsów API WinRT, które będą uruchamiane w piaskownicy AppContainer, eliminując złożoność i problemy często związane z pisaniem sterowników na poziomie systemu.</span><span class="sxs-lookup"><span data-stu-id="a8cd7-116">Third-party VPN providers can create their own plug-ins using WinRT APIs which will run within the AppContainer sandbox, eliminating the complexity and issues often associated with writing system-level drivers.</span></span>
