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
ms.openlocfilehash: 1c043b721590e8245f694b3e4f6e5b6ce57f1ecf
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639356"
---
# <a name="security-engineering"></a><span data-ttu-id="bb6e1-104">Inżynieria zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="bb6e1-104">Security engineering</span></span>

<span data-ttu-id="bb6e1-105">Firma Microsoft ma kilka zasobów i zespołów poświęconych optymalizacji protokołów inżynieryjnych firmy, zapewnianiu zgodności i zapewnieniu zaufania klientów.</span><span class="sxs-lookup"><span data-stu-id="bb6e1-105">Microsoft has several resources and teams devoted to optimizing the company’s engineering protocols, addressing compliance, and ensuring customer trust.</span></span> 

  * <span data-ttu-id="bb6e1-106">Aby dowiedzieć się więcej na temat rozwiązań firmy Microsoft dotyczących projektowania inżynierii zabezpieczeń, zobacz [Security Development Lifecycle (SDL)](https://www.microsoft.com/securityengineering/sdl).</span><span class="sxs-lookup"><span data-stu-id="bb6e1-106">To learn more about Microsoft’s security engineering development practices, see the [Security Development Lifecycle (SDL)](https://www.microsoft.com/securityengineering/sdl).</span></span>
  * <span data-ttu-id="bb6e1-107">Firma Microsoft, HoloLens 2, umożliwia klientom wybór sposobu i przyczyny zbierania i przetwarzania danych, co można bardziej eksplorować w zasadach zachowania poufności informacji [firmy Microsoft.](https://privacy.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="bb6e1-107">Microsoft, and therefore HoloLens 2, empowers customers to make choices about how and why data is collected and used, which can be further explored in [Microsoft’s Privacy policy](https://privacy.microsoft.com/).</span></span> 
  * <span data-ttu-id="bb6e1-108">[Centrum zabezpieczeń firmy Microsoft (MSRC)](https://www.microsoft.com/msrc) jest częścią społeczności usługi Defender, zapewniając wydajne środowisko raportowania luk w zabezpieczeniach oraz efektywną kategoryzację i reagowanie na błędy zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="bb6e1-108">[Microsoft Security Response Center (MSRC)](https://www.microsoft.com/msrc) is part of the defender community, providing an efficient vulnerability reporting experience and an effective categorization and response to security bugs.</span></span> 

## <a name="updates-and-patches"></a><span data-ttu-id="bb6e1-109">Aktualizacje i poprawki</span><span class="sxs-lookup"><span data-stu-id="bb6e1-109">Updates and patches</span></span>

<span data-ttu-id="bb6e1-110">Aktualizacje zabezpieczeń i poprawki zostaną wydane w drugi wtorek każdego miesiąca.</span><span class="sxs-lookup"><span data-stu-id="bb6e1-110">Security updates and patches are released on the second Tuesday of each month.</span></span> <span data-ttu-id="bb6e1-111">Aby zrozumieć kryteria używane przez firmę Microsoft do oceny następnych kroków w przypadku zgłoszonej luki w zabezpieczeniach, zobacz stronę security [servicing criteria](https://www.microsoft.com/msrc/windows-security-servicing-criteria)(Kryteria obsługi zabezpieczeń) Centrum zabezpieczeń firmy Microsoft firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bb6e1-111">In order to understand the criteria used by Microsoft to evaluate next steps for a reported vulnerability, see the Microsoft Security Response Center’s [Security Servicing Criteria page](https://www.microsoft.com/msrc/windows-security-servicing-criteria).</span></span> 

<span data-ttu-id="bb6e1-112">Aby uzyskać wskazówki dotyczące zarządzania aktualizacjami HoloLens 2 za pośrednictwem rozwiązania MDM, zobacz [Zarządzanie HoloLens aktualizacjami.](hololens-updates.md)</span><span class="sxs-lookup"><span data-stu-id="bb6e1-112">For guidance on managing HoloLens 2 updates via MDM, see [Manage HoloLens updates](hololens-updates.md).</span></span> <span data-ttu-id="bb6e1-113">Czas aktualizacji systemu operacyjnego dla HoloLens 2 jest taki Windows 10; W ciągu roku są dostępne dwie aktualizacje, jedna na wiosnę, a druga na wiosnę.</span><span class="sxs-lookup"><span data-stu-id="bb6e1-113">The operating system update cadence for HoloLens 2 matches that of Windows 10; there are two updates per year, one taking place in Spring and the other in Fall.</span></span> <span data-ttu-id="bb6e1-114">Aby uzyskać więcej informacji na temat sposobu zabezpieczania urządzeń podczas aktualizacji systemu operacyjnego, zobacz [State separation and isolation (Separacja i izolacja stanu).](security-state-separation-isolation.md)</span><span class="sxs-lookup"><span data-stu-id="bb6e1-114">For more on how devices are secured during OS updates, see [State separation and isolation](security-state-separation-isolation.md).</span></span> 

<span data-ttu-id="bb6e1-115">Administratorzy IT mogą dowiedzieć się więcej na temat zasad aktualizacji na stronie [Policy CSP - Update](/windows/client-management/mdm/policy-csp-update).</span><span class="sxs-lookup"><span data-stu-id="bb6e1-115">IT admins can learn more about update policy at [Policy CSP - Update](/windows/client-management/mdm/policy-csp-update).</span></span> 
