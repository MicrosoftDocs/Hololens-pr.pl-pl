---
title: Wymagania licencyjne
description: Bądź na bieżąco ze wszystkimi wymaganiami i wytycznymi dotyczącymi licencjonowania, które są potrzebne do zarządzania urządzeniami przenośnymi, HoloLens i usługi Remote Assist.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens 2
ms.openlocfilehash: d0d8aa648df7901dec8636942e43aa549e626d7e
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635895"
---
# <a name="license-requirements"></a><span data-ttu-id="57073-103">Wymagania licencyjne</span><span class="sxs-lookup"><span data-stu-id="57073-103">License requirements</span></span>

## <a name="hololens-2-device-managed"></a><span data-ttu-id="57073-104">HoloLens 2 (zarządzane)</span><span class="sxs-lookup"><span data-stu-id="57073-104">HoloLens 2 Device (managed)</span></span>

[<span data-ttu-id="57073-105">Konto usługi Azure AD</span><span class="sxs-lookup"><span data-stu-id="57073-105">Azure AD Account</span></span>](https://docs.microsoft.com/azure/active-directory/)

> [!IMPORTANT]
> <span data-ttu-id="57073-106">Usługi Active Directory (AD) nie można używać do zarządzania HoloLens urządzeniami.</span><span class="sxs-lookup"><span data-stu-id="57073-106">Active Directory (AD) cannot be used to manage HoloLens devices.</span></span>

<span data-ttu-id="57073-107">[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) lub innego rozwiązania MDM.</span><span class="sxs-lookup"><span data-stu-id="57073-107">[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) or another MDM.</span></span>
- <span data-ttu-id="57073-108">[Windows Autopilot for HoloLens 2](hololens2-autopilot.md)— upraszcza aprowizowanie zarówno dla administratorów IT, jak i użytkowników końcowych.</span><span class="sxs-lookup"><span data-stu-id="57073-108">[Windows Autopilot for HoloLens 2](hololens2-autopilot.md)- simplifies the provisioning experience for both IT admins and end users.</span></span> <span data-ttu-id="57073-109">Administratorzy IT mogą wstępnie skonfigurować zasady HoloLens 2, a przy pierwszym rozruchu urządzenia zostaną wdrożone w stanie gotowości do działania firmy bez interakcji użytkownika końcowego.</span><span class="sxs-lookup"><span data-stu-id="57073-109">IT admins can preconfigure HoloLens 2 policies, and upon first boot, devices will be deployed in business-ready state with zero end-user interaction.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="57073-110">Windows Funkcja Autopilot wymaga [](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) skonfigurowania [platformy Azure P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) i automatycznego rejestrowania w celu wdrożenia przepływu rozwiązania Autopilot z niskim poziomem dotyku i wdrażania urządzeń.</span><span class="sxs-lookup"><span data-stu-id="57073-110">Windows Autopilot requires [Azure P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) and [Auto-enrollment](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) to be configured first for the low-touch Autopilot flow and device deployment.</span></span> 

### <a name="business-use-case"></a><span data-ttu-id="57073-111">Przypadek użycia biznesowego:</span><span class="sxs-lookup"><span data-stu-id="57073-111">Business Use Case:</span></span> 

- <span data-ttu-id="57073-112">[Scenariusz wdrażania A](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) — wdrożenie weryfikacji koncepcji lub wdrożenia pilotażowego.</span><span class="sxs-lookup"><span data-stu-id="57073-112">[Deployment Scenario A](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) - proof-of-concept or pilot deployment.</span></span>

- <span data-ttu-id="57073-113">[Scenariusz wdrażania B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) — wdrażanie na dużą skalę.</span><span class="sxs-lookup"><span data-stu-id="57073-113">[Deployment Scenario B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) - deployment at scale.</span></span>

## <a name="hololens-2-device-only-non-managed"></a><span data-ttu-id="57073-114">HoloLens 2 Tylko urządzenie (nieza zarządzane)</span><span class="sxs-lookup"><span data-stu-id="57073-114">HoloLens 2 Device-only (non-managed)</span></span>

<span data-ttu-id="57073-115">W przypadku korzystania z konta Microsoft (MSA) lub konta lokalnego nie są wymagane żadne dodatkowe licencje dla tych kont.</span><span class="sxs-lookup"><span data-stu-id="57073-115">When using either a Microsoft Account (MSA) or Local account no additional licenses are required for these accounts.</span></span>

[<span data-ttu-id="57073-116">Konto lokalne</span><span class="sxs-lookup"><span data-stu-id="57073-116">Local Account</span></span>](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts)

- <span data-ttu-id="57073-117">To konto należy [aprowizować](hololens-provisioning.md#provisioning-package-hololens-wizard) z wyprzedzeniem za pomocą Windows Configuration Designer (WCD).</span><span class="sxs-lookup"><span data-stu-id="57073-117">This account must be [provisioned](hololens-provisioning.md#provisioning-package-hololens-wizard) ahead of time with Windows Configuration Designer (WCD).</span></span>

[<span data-ttu-id="57073-118">Konto Microsoft (MSA)</span><span class="sxs-lookup"><span data-stu-id="57073-118">Microsoft Account (MSA)</span></span>](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts)

> [!WARNING]
> <span data-ttu-id="57073-119">Wielu użytkowników nie jest obsługiwanych na urządzeniu przy użyciu jednego z tych kont.</span><span class="sxs-lookup"><span data-stu-id="57073-119">Multiple users are not supported for a device using either of these accounts.</span></span>

### <a name="business-use-case"></a><span data-ttu-id="57073-120">Przypadek użycia biznesowego:</span><span class="sxs-lookup"><span data-stu-id="57073-120">Business Use Case:</span></span> 

- <span data-ttu-id="57073-121">[Scenariusz wdrażania C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) — wdrożenie w trybie offline lub bezpieczne.</span><span class="sxs-lookup"><span data-stu-id="57073-121">[Deployment Scenario C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) - offline or secure deployment.</span></span>
 
## <a name="dynamics-365-licensing-and-requirements"></a><span data-ttu-id="57073-122">Dynamics 365 Licensing and Requirements</span><span class="sxs-lookup"><span data-stu-id="57073-122">Dynamics 365 Licensing and Requirements</span></span>

### <a name="dynamics-365-remote-assist"></a><span data-ttu-id="57073-123">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="57073-123">Dynamics 365 Remote Assist</span></span> 

#### <a name="admin"></a><span data-ttu-id="57073-124">Administrator</span><span class="sxs-lookup"><span data-stu-id="57073-124">Admin</span></span>

- <span data-ttu-id="57073-125">Konto usługi Azure AD (wymagane do zakupu subskrypcji i przypisywania licencji)</span><span class="sxs-lookup"><span data-stu-id="57073-125">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="57073-126">[Subskrypcja usługi Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (lub wersja [próbna usługi Remote Assist)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="57073-126">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="57073-127">Użytkownik usługi Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="57073-127">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="57073-128">Konto usługi Azure AD</span><span class="sxs-lookup"><span data-stu-id="57073-128">Azure AD account</span></span>

- <span data-ttu-id="57073-129">Licencja usługi Remote Assist</span><span class="sxs-lookup"><span data-stu-id="57073-129">Remote Assist license</span></span> 

  > [!NOTE]
  > <span data-ttu-id="57073-130">Microsoft Teams jest w pakiecie z usługą Remote Assist</span><span class="sxs-lookup"><span data-stu-id="57073-130">Microsoft Teams is bundled with Remote Assist</span></span>

- <span data-ttu-id="57073-131">Łączność sieciowa</span><span class="sxs-lookup"><span data-stu-id="57073-131">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="57073-132">Microsoft Teams użytkownika</span><span class="sxs-lookup"><span data-stu-id="57073-132">Microsoft Teams user</span></span>

- <span data-ttu-id="57073-133">Konto usługi Azure AD</span><span class="sxs-lookup"><span data-stu-id="57073-133">Azure AD account</span></span>

- <span data-ttu-id="57073-134">Microsoft Teams lub [Teams Freemium.](https://products.office.com/microsoft-teams/free)</span><span class="sxs-lookup"><span data-stu-id="57073-134">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>

- <span data-ttu-id="57073-135">Łączność sieciowa</span><span class="sxs-lookup"><span data-stu-id="57073-135">Network connectivity</span></span>

<span data-ttu-id="57073-136">Jeśli planujesz wdrożenie tego scenariusza między [dzierżawami,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)może być potrzebna licencja na bariery informacyjne.</span><span class="sxs-lookup"><span data-stu-id="57073-136">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="57073-137">Zapoznaj [się z tym artykułem,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) aby ustalić, czy wymagana jest licencja information barrier.</span><span class="sxs-lookup"><span data-stu-id="57073-137">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <a name="dynamics-365-guides"></a><span data-ttu-id="57073-138">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="57073-138">Dynamics 365 Guides</span></span> 

#### <a name="admin"></a><span data-ttu-id="57073-139">Administrator</span><span class="sxs-lookup"><span data-stu-id="57073-139">Admin</span></span>

- <span data-ttu-id="57073-140">Konto usługi Azure AD (wymagane do zakupu subskrypcji i przypisywania licencji)</span><span class="sxs-lookup"><span data-stu-id="57073-140">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="57073-141">Subskrypcja przewodników usługi Dynamics 365 [lub bezpłatna wersja próbna](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one)</span><span class="sxs-lookup"><span data-stu-id="57073-141">Dynamics 365 [Guides subscription or free trial](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one)</span></span>

#### <a name="guides-author"></a><span data-ttu-id="57073-142">Tworzenie przewodników</span><span class="sxs-lookup"><span data-stu-id="57073-142">Guides Author</span></span>

1. <span data-ttu-id="57073-143">Konto usługi Azure AD</span><span class="sxs-lookup"><span data-stu-id="57073-143">Azure AD account</span></span>
1. [<span data-ttu-id="57073-144">Licencja przewodników usługi Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="57073-144">Dynamics 365 Guides license</span></span>](/dynamics365/mixed-reality/guides/requirements)
1. <span data-ttu-id="57073-145">Aplikacja Dynamics 365 Guides zainstalowana na komputerze pc lub HoloLens</span><span class="sxs-lookup"><span data-stu-id="57073-145">Dynamics 365 Guides application installed on a PC or HoloLens</span></span>
1. <span data-ttu-id="57073-146">[Power BI Desktop](https://powerbi.microsoft.com/desktop/) (używane do wyświetlania pulpitu nawigacyjnego analizy)</span><span class="sxs-lookup"><span data-stu-id="57073-146">[Power BI Desktop](https://powerbi.microsoft.com/desktop/) (used to view the Analytics dashboard)</span></span>
1. <span data-ttu-id="57073-147">Rola autora (do tworzenia przewodników)</span><span class="sxs-lookup"><span data-stu-id="57073-147">Author role (for creating guides)</span></span>
1. <span data-ttu-id="57073-148">Łączność sieciowa</span><span class="sxs-lookup"><span data-stu-id="57073-148">Network Connectivity</span></span>

#### <a name="guides-user"></a><span data-ttu-id="57073-149">Przewodniki użytkownika</span><span class="sxs-lookup"><span data-stu-id="57073-149">Guides User</span></span>

1. <span data-ttu-id="57073-150">Konto usługi Azure AD</span><span class="sxs-lookup"><span data-stu-id="57073-150">Azure AD account</span></span>
1. [<span data-ttu-id="57073-151">Licencja przewodników usługi Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="57073-151">Dynamics 365 Guides license</span></span>](/dynamics365/mixed-reality/guides/requirements)
1. <span data-ttu-id="57073-152">Aplikacja Dynamics 365 Guides zainstalowana na HoloLens</span><span class="sxs-lookup"><span data-stu-id="57073-152">Dynamics 365 Guides app installed on a HoloLens</span></span>
1. <span data-ttu-id="57073-153">Rola operatora (do testowania lub używania przewodników)</span><span class="sxs-lookup"><span data-stu-id="57073-153">Operator role (for testing or using guides)</span></span>
1. <span data-ttu-id="57073-154">Łączność sieciowa</span><span class="sxs-lookup"><span data-stu-id="57073-154">Network Connectivity</span></span>
