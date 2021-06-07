---
title: Wymagania licencyjne
description: Bądź na bieżąco ze wszystkimi wymaganiami i wytycznymi dotyczącymi licencjonowania potrzebnymi do zarządzania urządzeniami przenośnymi, urządzenia HoloLens i usługi Remote Assist.
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2f7af532d2172dcaa6514ee11dbb0d6ab5631929
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379753"
---
# <a name="license-requirements"></a><span data-ttu-id="0553f-103">Wymagania licencyjne</span><span class="sxs-lookup"><span data-stu-id="0553f-103">License requirements</span></span>

## <a name="mobile-device-management-mdm-licenses-guidance"></a><span data-ttu-id="0553f-104">Wskazówki dotyczące licencji usługi Mobile Zarządzanie urządzeniami (MDM)</span><span class="sxs-lookup"><span data-stu-id="0553f-104">Mobile Device Management (MDM) Licenses Guidance</span></span>

<span data-ttu-id="0553f-105">Jeśli planujesz zarządzanie urządzeniami HoloLens, potrzebujesz usługi Azure AD i rozwiązania MDM.</span><span class="sxs-lookup"><span data-stu-id="0553f-105">If you plan on managing your HoloLens devices, you will need Azure AD and an MDM.</span></span> <span data-ttu-id="0553f-106">Usługi Active Director (AD) nie można używać do zarządzania urządzeniami HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0553f-106">Active Director (AD) cannot be used to manage HoloLens devices.</span></span>
<span data-ttu-id="0553f-107">Jeśli planujesz korzystanie z rozwiązania MDM innego niż usługa Intune, [wymagana jest Azure Active Directory zarządzania urządzeniami](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) przenośnymi.</span><span class="sxs-lookup"><span data-stu-id="0553f-107">If you plan on using an MDM other than Intune, an [Azure Active Directory Licenses](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) is required.</span></span>
<span data-ttu-id="0553f-108">Jeśli planujesz używać usługi Intune jako rozwiązania MDM, zapoznaj się z [listą](https://docs.microsoft.com/intune/fundamentals/licenses) pakietów, które obejmują licencje usługi Intune.</span><span class="sxs-lookup"><span data-stu-id="0553f-108">If you plan on using Intune as your MDM, read up on the [list of suites](https://docs.microsoft.com/intune/fundamentals/licenses) that include Intune licenses.</span></span> <span data-ttu-id="0553f-109">**Należy pamiętać, że usługa Azure AD jest uwzględniona w większości tych pakietów.**</span><span class="sxs-lookup"><span data-stu-id="0553f-109">**Please note that Azure AD is included in the majority of these suites.**</span></span>

## <a name="identify-the-licenses-needed-for-your-scenario-and-products"></a><span data-ttu-id="0553f-110">Identyfikowanie licencji wymaganych dla scenariusza i produktów</span><span class="sxs-lookup"><span data-stu-id="0553f-110">Identify the licenses needed for your scenario and products</span></span>

### <a name="hololens-1st-gen-licenses-requirements"></a><span data-ttu-id="0553f-111">Wymagania dotyczące licencji urządzenia HoloLens (1. generacji)</span><span class="sxs-lookup"><span data-stu-id="0553f-111">HoloLens (1st gen) Licenses Requirements</span></span>

<span data-ttu-id="0553f-112">Może być konieczne uaktualnienie urządzenia HoloLens (1. generacji) do Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="0553f-112">You may need to upgrade your HoloLens (1st gen) device to Windows Holographic for Business.</span></span> <span data-ttu-id="0553f-113">(Zobacz Funkcje [komercyjne urządzenia HoloLens,](holoLens-commercial-features.md#feature-comparison-between-editions) aby ustalić, czy należy je uaktualnić).</span><span class="sxs-lookup"><span data-stu-id="0553f-113">(See [HoloLens commercial features](holoLens-commercial-features.md#feature-comparison-between-editions) to determine if you need to upgrade).</span></span>

 <span data-ttu-id="0553f-114">Jeśli tak, należy wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="0553f-114">If so, you will need to do the following:</span></span>

- <span data-ttu-id="0553f-115">Uzyskaj plik XML licencji urządzenia HoloLens Enterprise</span><span class="sxs-lookup"><span data-stu-id="0553f-115">Acquire a HoloLens Enterprise license XML file</span></span>
- <span data-ttu-id="0553f-116">Zastosuj plik XML do urządzenia HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0553f-116">Apply the XML file to the HoloLens.</span></span> <span data-ttu-id="0553f-117">Można to zrobić za pomocą pakietu [aprowizowania](hololens-provisioning.md) lub za pośrednictwem usługi [Mobile Menedżer urządzeń](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span><span class="sxs-lookup"><span data-stu-id="0553f-117">You can do this through a [Provisioning package](hololens-provisioning.md) or through your [Mobile Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span></span>

### <a name="remote-assist-license-requirements"></a><span data-ttu-id="0553f-118">Wymagania licencyjne usługi Remote Assist</span><span class="sxs-lookup"><span data-stu-id="0553f-118">Remote Assist License Requirements</span></span>

<span data-ttu-id="0553f-119">Upewnij się, że masz wymagane licencje i urządzenie, które możesz sprawdzić w [dokumentacji](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements) wymagań.</span><span class="sxs-lookup"><span data-stu-id="0553f-119">Make sure you have the required licensing and device, which you can check in the [requirements](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements) documentation.</span></span>

1. [<span data-ttu-id="0553f-120">Licencja usługi Remote Assist</span><span class="sxs-lookup"><span data-stu-id="0553f-120">Remote Assist License</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. <span data-ttu-id="0553f-121">Możesz też wypróbować wersję [próbną usługi Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="0553f-121">Or try a [Remote Assist trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span></span>
1. [<span data-ttu-id="0553f-122">Teams Freemium/Teams</span><span class="sxs-lookup"><span data-stu-id="0553f-122">Teams Freemium/Teams</span></span>](https://products.office.com/microsoft-teams/free)
1. [<span data-ttu-id="0553f-123">Azure Active Directory licencji usługi (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="0553f-123">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

<span data-ttu-id="0553f-124">Jeśli planujesz wdrożenie tego scenariusza między **[dzierżawami,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)** może być potrzebna licencja information barriers.</span><span class="sxs-lookup"><span data-stu-id="0553f-124">If you plan on implementing **[this cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, you may need an Information Barriers license.</span></span> <span data-ttu-id="0553f-125">Zapoznaj się z [tym artykułem,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) aby ustalić, czy wymagana jest licencja Information Barrier.</span><span class="sxs-lookup"><span data-stu-id="0553f-125">Please see [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <a name="guides-license-requirements"></a><span data-ttu-id="0553f-126">Wymagania licencyjne przewodników</span><span class="sxs-lookup"><span data-stu-id="0553f-126">Guides License Requirements</span></span>

<span data-ttu-id="0553f-127">Zapoznaj się ze [zaktualizowanymi wymaganiami w zakresie licencjonowania i urządzeń.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements)</span><span class="sxs-lookup"><span data-stu-id="0553f-127">Check out the [updated licensing and device requirements](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span></span>

1. [<span data-ttu-id="0553f-128">Azure Active Directory licencji usługi (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="0553f-128">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [<span data-ttu-id="0553f-129">Power BI</span><span class="sxs-lookup"><span data-stu-id="0553f-129">Power BI</span></span>](https://powerbi.microsoft.com/desktop/)
1. [<span data-ttu-id="0553f-130">Przewodniki</span><span class="sxs-lookup"><span data-stu-id="0553f-130">Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
