---
title: Inżynieria zabezpieczeń
description: Inżynieria zabezpieczeń
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: zabezpieczenia, hololens, zabezpieczenia, inżynieria
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: cecc556841033ee394f36915f4cae8839dad08df
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379716"
---
# <a name="security-engineering"></a><span data-ttu-id="383ba-104">Inżynieria zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="383ba-104">Security engineering</span></span>

<span data-ttu-id="383ba-105">Firma Microsoft ma kilka zasobów i zespołów poświęconych optymalizacji protokołów inżynieryjnych firmy, zapewnianiu zgodności i zapewnieniu zaufania klientów.</span><span class="sxs-lookup"><span data-stu-id="383ba-105">Microsoft has several resources and teams devoted to optimizing the company’s engineering protocols, addressing compliance, and ensuring customer trust.</span></span> 

  * <span data-ttu-id="383ba-106">Aby dowiedzieć się więcej na temat praktyk programistów inżynierii zabezpieczeń firmy Microsoft, zobacz [Security Development Lifecycle (SDL)](https://www.microsoft.com/securityengineering/sdl).</span><span class="sxs-lookup"><span data-stu-id="383ba-106">To learn more about Microsoft’s security engineering development practices, see the [Security Development Lifecycle (SDL)](https://www.microsoft.com/securityengineering/sdl).</span></span>
  * <span data-ttu-id="383ba-107">Firma Microsoft, a w związku z tym urządzenie HoloLens 2, umożliwia klientom wybór sposobu i przyczyny zbierania i przetwarzania danych, co można dodatkowo zbadać w zasadach zachowania poufności informacji firmy [Microsoft.](https://privacy.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="383ba-107">Microsoft, and therefore HoloLens 2, empowers customers to make choices about how and why data is collected and used, which can be further explored in [Microsoft’s Privacy policy](https://privacy.microsoft.com/).</span></span> 
  * <span data-ttu-id="383ba-108">[Centrum zabezpieczeń firmy Microsoft (MSRC)](https://www.microsoft.com/msrc) jest częścią społeczności usługi Defender, zapewniając wydajne środowisko raportowania luk w zabezpieczeniach oraz efektywną kategoryzację i reagowanie na błędy zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="383ba-108">[Microsoft Security Response Center (MSRC)](https://www.microsoft.com/msrc) is part of the defender community, providing an efficient vulnerability reporting experience and an effective categorization and response to security bugs.</span></span> 

## <a name="updates-and-patches"></a><span data-ttu-id="383ba-109">Aktualizacje i poprawki</span><span class="sxs-lookup"><span data-stu-id="383ba-109">Updates and patches</span></span>

<span data-ttu-id="383ba-110">Aktualizacje zabezpieczeń i poprawki są zwalniane w drugi wtorek każdego miesiąca.</span><span class="sxs-lookup"><span data-stu-id="383ba-110">Security updates and patches are released on the second Tuesday of each month.</span></span> <span data-ttu-id="383ba-111">Aby zrozumieć kryteria używane przez firmę Microsoft do oceny następnych kroków w przypadku zgłoszonej luki w zabezpieczeniach, zobacz stronę Centrum zabezpieczeń firmy Microsoft [Security Servicing Criteria](https://www.microsoft.com/msrc/windows-security-servicing-criteria)(Kryteria obsługi zabezpieczeń).</span><span class="sxs-lookup"><span data-stu-id="383ba-111">In order to understand the criteria used by Microsoft to evaluate next steps for a reported vulnerability, see the Microsoft Security Response Center’s [Security Servicing Criteria page](https://www.microsoft.com/msrc/windows-security-servicing-criteria).</span></span> 

<span data-ttu-id="383ba-112">Aby uzyskać wskazówki dotyczące zarządzania aktualizacjami urządzenia HoloLens 2 za pomocą rozwiązania MDM, zobacz Manage HoloLens updates (Zarządzanie [aktualizacjami urządzenia HoloLens).](https://docs.microsoft.com/hololens/hololens-updates)</span><span class="sxs-lookup"><span data-stu-id="383ba-112">For guidance on managing HoloLens 2 updates via MDM, see [Manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates).</span></span> <span data-ttu-id="383ba-113">Czas aktualizacji systemu operacyjnego dla urządzenia HoloLens 2 jest taki Windows 10; w ciągu roku są dostępne dwie aktualizacje, jedna na wiosnę, a druga na wiosnę.</span><span class="sxs-lookup"><span data-stu-id="383ba-113">The operating system update cadence for HoloLens 2 matches that of Windows 10; there are two updates per year, one taking place in Spring and the other in Fall.</span></span> <span data-ttu-id="383ba-114">Aby uzyskać więcej informacji na temat sposobu zabezpieczania urządzeń podczas aktualizacji systemu operacyjnego, zobacz [State separation and isolation (Separacja i izolacja stanu).](security-state-separation-isolation.md)</span><span class="sxs-lookup"><span data-stu-id="383ba-114">For more on how devices are secured during OS updates, see [State separation and isolation](security-state-separation-isolation.md).</span></span> 

<span data-ttu-id="383ba-115">Administratorzy IT mogą dowiedzieć się więcej na temat zasad aktualizacji na stronie Policy CSP - Update (Zasady [CSP — aktualizacja).](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update)</span><span class="sxs-lookup"><span data-stu-id="383ba-115">IT admins can learn more about update policy at [Policy CSP - Update](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update).</span></span> 
