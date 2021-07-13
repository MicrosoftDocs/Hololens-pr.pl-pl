---
title: Omówienie usługi Cloud Connected HoloLens 2 z usługą Remote Assist
description: Dowiedz się, jak zarejestrować 2 HoloLens za pośrednictwem sieci połączonej z chmurą przy użyciu usługi Dynamics 365 Remote Assist.
keywords: HoloLens, zarządzanie, połączone z chmurą, Remote Assist, AAD, Azure AD, MDM, Mobile Zarządzanie urządzeniami
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 86d36275d5cf1296ca3e9fec90684a188a29f3f0
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635130"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="7214b-104">Przewodnik wdrażania — połączone z chmurą HoloLens 2 ze zdalną asystą — omówienie</span><span class="sxs-lookup"><span data-stu-id="7214b-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="7214b-105">Ten przewodnik pomoże specjalistom IT w planowaniu i wdrażaniu Microsoft HoloLens 2 urządzeń za pomocą usługi Remote Assist w organizacji.</span><span class="sxs-lookup"><span data-stu-id="7214b-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Remote Assist to their organization.</span></span> <span data-ttu-id="7214b-106">Będzie to model wdrożeń weryfikacji koncepcji w organizacji w różnych HoloLens 2 przypadkach użycia.</span><span class="sxs-lookup"><span data-stu-id="7214b-106">This will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span> <span data-ttu-id="7214b-107">Konfiguracja jest podobna do [scenariusza A: wdrażanie na urządzeniach z programem Cloud Connect.](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)</span><span class="sxs-lookup"><span data-stu-id="7214b-107">The setup is similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a).</span></span> 

<span data-ttu-id="7214b-108">W tym przewodniku opisano sposób rejestrowania urządzeń w zarządzaniu urządzeniami, stosowania licencji zgodnie z potrzebami i sprawdzania, czy użytkownicy końcowi mogą natychmiast korzystać z usługi Remote Assist podczas konfigurowania urządzenia.</span><span class="sxs-lookup"><span data-stu-id="7214b-108">During the guide, we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="7214b-109">W tym celu przejmiemy ważne elementy infrastruktury potrzebne do skonfigurowania i uruchomienia — osiągnięcie wdrożenia na dużą skalę przy HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="7214b-109">To do this, we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span> <span data-ttu-id="7214b-110">W tym przewodniku nie zostaną zastosowane żadne inne ograniczenia ani konfiguracje urządzeń, jednak zachęcamy do eksplorowania tych opcji po zakończeniu.</span><span class="sxs-lookup"><span data-stu-id="7214b-110">No other device restrictions or configurations will be applied in this guide, however, we encourage you to explore those options after finishing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7214b-111">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="7214b-111">Prerequisites</span></span>

<span data-ttu-id="7214b-112">W celu wdrożenia usługi należy wdrożyć następującą infrastrukturę HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="7214b-112">The following infrastructure should be in place in order to deploy the HoloLens 2.</span></span> <span data-ttu-id="7214b-113">Jeśli nie, konfigurowanie platformy Azure i usługi Intune jest zawarte w tym przewodniku:</span><span class="sxs-lookup"><span data-stu-id="7214b-113">If not, setting up Azure and Intune is included in this guide:</span></span>

<span data-ttu-id="7214b-114">Jest to konfiguracja podobna do scenariusza [A:](/hololens/common-scenarios#scenario-a)wdrażanie na urządzeniach z połączeniami w chmurze, co jest dobrą opcją dla wielu wdrożeń weryfikacji koncepcji, które obejmują:</span><span class="sxs-lookup"><span data-stu-id="7214b-114">This is a set up similar to [Scenario A: Deploy to cloud connect devices](/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="7214b-115">Wi-Fi są zwykle w pełni otwarte dla Internetu i usług w chmurze</span><span class="sxs-lookup"><span data-stu-id="7214b-115">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="7214b-116">Dołączanie do usługi Azure AD z automatyczną rejestracją w usłudze MDM — zarządzane przez rozwiązanie MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="7214b-116">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="7214b-117">Użytkownicy logują się przy użyciu własnego konta firmowego (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="7214b-117">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="7214b-118">Obsługiwana jest jedna lub wielu użytkowników na urządzenie.</span><span class="sxs-lookup"><span data-stu-id="7214b-118">Single or multiple users per device is supported.</span></span>

:::image type="content" alt-text="Scenariusz połączony z chmurą" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a><span data-ttu-id="7214b-120">Dowiedz się więcej o pomocy zdalnej</span><span class="sxs-lookup"><span data-stu-id="7214b-120">Learn about Remote Assist</span></span>

<span data-ttu-id="7214b-121">Usługa Remote Assist umożliwia wspólną konserwację i naprawę, zdalną inspekcję, a także udostępnianie i szkolenie wiedzy.</span><span class="sxs-lookup"><span data-stu-id="7214b-121">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="7214b-122">Łącząc osoby w różnych rolach i lokalizacjach, technik korzystający z usługi Remote Assist może nawiązać połączenie ze zdalnym współpracownikiem na Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7214b-122">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="7214b-123">Mogą one łączyć wideo, zrzuty ekranu i adnotacje, aby rozwiązywać problemy w czasie rzeczywistym, nawet&#39;nie w tej samej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="7214b-123">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="7214b-124">Zdalni współpracownicy mogą wstawiać obrazy referencyjne, schematy i inne przydatne informacje, które technik&#39;w fizycznej przestrzeni, dzięki czemu mogą odwoływać się do schematu podczas pracy z komputerami bez HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7214b-124">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a><span data-ttu-id="7214b-125">Licencjonowanie i wymagania dotyczące usługi Remote Assist</span><span class="sxs-lookup"><span data-stu-id="7214b-125">Remote Assist Licensing and Requirements</span></span>

- <span data-ttu-id="7214b-126">Konto usługi Azure AD (wymagane do zakupu subskrypcji i przypisywania licencji)</span><span class="sxs-lookup"><span data-stu-id="7214b-126">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="7214b-127">[Subskrypcja usługi Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (lub wersja [próbna usługi Remote Assist)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="7214b-127">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="7214b-128">Użytkownik usługi Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="7214b-128">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="7214b-129">Licencja usługi Remote Assist</span><span class="sxs-lookup"><span data-stu-id="7214b-129">Remote Assist license</span></span>
- <span data-ttu-id="7214b-130">Łączność sieciowa</span><span class="sxs-lookup"><span data-stu-id="7214b-130">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="7214b-131">Microsoft Teams użytkownika</span><span class="sxs-lookup"><span data-stu-id="7214b-131">Microsoft Teams user</span></span>

- <span data-ttu-id="7214b-132">Microsoft Teams lub [Teams Freemium.](https://products.office.com/microsoft-teams/free)</span><span class="sxs-lookup"><span data-stu-id="7214b-132">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>
- <span data-ttu-id="7214b-133">Łączność sieciowa</span><span class="sxs-lookup"><span data-stu-id="7214b-133">Network connectivity</span></span>

<span data-ttu-id="7214b-134">Jeśli planujesz wdrożenie tego scenariusza między [dzierżawami,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)może być potrzebna licencja na bariery informacyjne.</span><span class="sxs-lookup"><span data-stu-id="7214b-134">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="7214b-135">Zapoznaj [się z tym artykułem,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) aby ustalić, czy wymagana jest licencja information barrier.</span><span class="sxs-lookup"><span data-stu-id="7214b-135">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="7214b-136">Ten przewodnik zawiera informacje na temat:</span><span class="sxs-lookup"><span data-stu-id="7214b-136">In this guide you will:</span></span>

<span data-ttu-id="7214b-137">Przygotować:</span><span class="sxs-lookup"><span data-stu-id="7214b-137">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="7214b-138">Dowiedz się więcej na temat podstawowych informacji o infrastrukturze HoloLens 2 urządzeń.</span><span class="sxs-lookup"><span data-stu-id="7214b-138">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="7214b-139">Dowiedz się więcej o usłudze Azure AD i skonfiguruj ją, jeśli&#39;jej nie masz.</span><span class="sxs-lookup"><span data-stu-id="7214b-139">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="7214b-140">Dowiedz się więcej na temat zarządzania tożsamościami i sposobu najlepszego skonfigurowania kont usługi Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7214b-140">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="7214b-141">Dowiedz się więcej na temat zarządzania urządzeniami przenośnymi i skonfiguruj usługę Intune, jeśli&#39;jeszcze nie jest gotowa.</span><span class="sxs-lookup"><span data-stu-id="7214b-141">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="7214b-142">Dowiedz się więcej o wymaganiach dotyczących sieci usługi Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="7214b-142">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="7214b-143">Opcjonalnie: sieć VPN do łączenia się z zasobami organizacji</span><span class="sxs-lookup"><span data-stu-id="7214b-143">Optionally: VPN to connect to organizational resources</span></span>](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="7214b-144">Skonfiguruj:</span><span class="sxs-lookup"><span data-stu-id="7214b-144">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="7214b-145">Jak utworzyć użytkowników i grupy.</span><span class="sxs-lookup"><span data-stu-id="7214b-145">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="7214b-146">Jak skonfigurować automatyczne rejestrowanie w usłudze Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7214b-146">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="7214b-147">Jak przypisać licencje aplikacji.</span><span class="sxs-lookup"><span data-stu-id="7214b-147">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="7214b-148">Wdrażanie:</span><span class="sxs-lookup"><span data-stu-id="7214b-148">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="7214b-149">Skonfiguruj swój HoloLens 2 i zweryfikuj rejestrację.</span><span class="sxs-lookup"><span data-stu-id="7214b-149">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="7214b-150">Zweryfikuj, czy można wykonać wywołanie funkcji Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="7214b-150">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="7214b-151">Utrzymania:</span><span class="sxs-lookup"><span data-stu-id="7214b-151">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="7214b-152">Jak zaktualizować usługę Remote Assist przy użyciu Microsoft Store aplikacji.</span><span class="sxs-lookup"><span data-stu-id="7214b-152">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="7214b-153">Tworzenie planu pomocy technicznej.</span><span class="sxs-lookup"><span data-stu-id="7214b-153">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="7214b-154">Plan rozwoju.</span><span class="sxs-lookup"><span data-stu-id="7214b-154">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="7214b-155">Następny krok</span><span class="sxs-lookup"><span data-stu-id="7214b-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="7214b-156">Wdrożenie połączone z chmurą — przygotowanie</span><span class="sxs-lookup"><span data-stu-id="7214b-156">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

