---
title: Omówienie urządzenia HoloLens 2 połączonego z chmurą z usługą Remote Assist
description: Dowiedz się, jak zarejestrować urządzenia HoloLens 2 za pośrednictwem sieci połączonej z chmurą przy użyciu usługi Dynamics 365 Remote Assist.
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
ms.openlocfilehash: a44247b4afea747e4b75c974fcae344380909989
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923537"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="19195-104">Przewodnik wdrażania — urządzenie HoloLens 2 połączone z chmurą z usługą Remote Assist — omówienie</span><span class="sxs-lookup"><span data-stu-id="19195-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="19195-105">Ten przewodnik pomoże specjalistom IT w planowaniu i wdrażaniu Microsoft HoloLens 2 urządzeń z usługą Remote Assist w organizacji.</span><span class="sxs-lookup"><span data-stu-id="19195-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Remote Assist to their organization.</span></span> <span data-ttu-id="19195-106">Będzie to model wdrożeń weryfikacji koncepcji w organizacji w różnych przypadkach użycia urządzenia HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="19195-106">This will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span> <span data-ttu-id="19195-107">Konfiguracja jest podobna do scenariusza [A: wdrażanie na urządzeniach podłączonych do chmury.](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)</span><span class="sxs-lookup"><span data-stu-id="19195-107">The setup is similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a).</span></span> 

<span data-ttu-id="19195-108">W tym przewodniku opisano sposób rejestrowania urządzeń w zarządzaniu urządzeniami, stosowania licencji zgodnie z potrzebami i sprawdzania, czy użytkownicy końcowi mogą natychmiast korzystać z usługi Remote Assist podczas konfigurowania urządzenia.</span><span class="sxs-lookup"><span data-stu-id="19195-108">During the guide, we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="19195-109">W tym celu przejmiemy ważne elementy infrastruktury potrzebne do skonfigurowania i uruchomienia — osiągnięcie wdrożenia na dużą skalę za pomocą urządzenia HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="19195-109">To do this, we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span> <span data-ttu-id="19195-110">W tym przewodniku nie będą stosowane żadne inne ograniczenia ani konfiguracje dotyczące urządzeń, jednak zachęcamy do eksplorowania tych opcji po zakończeniu.</span><span class="sxs-lookup"><span data-stu-id="19195-110">No other device restrictions or configurations will be applied in this guide, however, we encourage you to explore those options after finishing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="19195-111">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="19195-111">Prerequisites</span></span>

<span data-ttu-id="19195-112">Aby wdrożyć urządzenie HoloLens 2, należy wdrożyć następującą infrastrukturę.</span><span class="sxs-lookup"><span data-stu-id="19195-112">The following infrastructure should be in place in order to deploy the HoloLens 2.</span></span> <span data-ttu-id="19195-113">Jeśli nie, konfigurowanie platformy Azure i usługi Intune jest uwzględnione w tym przewodniku:</span><span class="sxs-lookup"><span data-stu-id="19195-113">If not, setting up Azure and Intune is included in this guide:</span></span>

- <span data-ttu-id="19195-114">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="19195-114">Wi-Fi</span></span>
    - <span data-ttu-id="19195-115">Sieci są zwykle otwarte dla Internetu i usług w chmurze</span><span class="sxs-lookup"><span data-stu-id="19195-115">Networks are typically open to the Internet and Cloud services</span></span>
- <span data-ttu-id="19195-116">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment (Wymagane są subskrypcje[usługi Azure AD P1)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="19195-116">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="19195-117">Zarządzanie urządzeniami przenośnymi (Intune)</span><span class="sxs-lookup"><span data-stu-id="19195-117">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="19195-118">Co najmniej jedna aplikacja jest wdrażana za pośrednictwem rozwiązania MDM.</span><span class="sxs-lookup"><span data-stu-id="19195-118">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="19195-119">Użytkownicy logują się przy użyciu własnego konta firmowego (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="19195-119">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="19195-120">Obsługiwana jest jedna lub wielu użytkowników na urządzenie.</span><span class="sxs-lookup"><span data-stu-id="19195-120">Single or multiple users per device is supported.</span></span>

:::image type="content" alt-text="Scenariusz połączony z chmurą" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a><span data-ttu-id="19195-122">Dowiedz się więcej na temat usługi Remote Assist</span><span class="sxs-lookup"><span data-stu-id="19195-122">Learn about Remote Assist</span></span>

<span data-ttu-id="19195-123">Usługa Remote Assist umożliwia współpracę w zakresie konserwacji i naprawy, zdalną inspekcję, a także udostępnianie i szkolenie wiedzy.</span><span class="sxs-lookup"><span data-stu-id="19195-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="19195-124">Łącząc osoby w różnych rolach i lokalizacjach, technik korzystający z usługi Remote Assist może nawiązać połączenie ze zdalnym współpracownikiem w aplikacji Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="19195-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="19195-125">Mogą łączyć filmy wideo, zrzuty ekranu i adnotacje, aby rozwiązywać problemy w czasie rzeczywistym nawet wtedy, gdy&#39;nie w tej samej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="19195-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="19195-126">Zdalni współpracownicy mogą wstawiać obrazy referencyjne, schematy i inne przydatne informacje, które technik&#39;w przestrzeni fizycznej, dzięki czemu mogą odwoływać się do schematu podczas pracy na urządzeniach HoloLens bez pracy praktycznej i pracy na urządzeniach HoloLens.</span><span class="sxs-lookup"><span data-stu-id="19195-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a><span data-ttu-id="19195-127">Licencjonowanie i wymagania dotyczące usługi Remote Assist</span><span class="sxs-lookup"><span data-stu-id="19195-127">Remote Assist Licensing and Requirements</span></span>

- <span data-ttu-id="19195-128">Konto usługi Azure AD (wymagane do zakupu subskrypcji i przypisywania licencji)</span><span class="sxs-lookup"><span data-stu-id="19195-128">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="19195-129">[Subskrypcja usługi Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (lub [wersja próbna usługi Remote Assist)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="19195-129">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="19195-130">Użytkownik usługi Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="19195-130">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="19195-131">Licencja usługi Remote Assist</span><span class="sxs-lookup"><span data-stu-id="19195-131">Remote Assist license</span></span>
- <span data-ttu-id="19195-132">Łączność sieciowa</span><span class="sxs-lookup"><span data-stu-id="19195-132">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="19195-133">Użytkownik aplikacji Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="19195-133">Microsoft Teams user</span></span>

- <span data-ttu-id="19195-134">Microsoft Teams lub [Teams Freemium](https://products.office.com/microsoft-teams/free).</span><span class="sxs-lookup"><span data-stu-id="19195-134">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>
- <span data-ttu-id="19195-135">Łączność sieciowa</span><span class="sxs-lookup"><span data-stu-id="19195-135">Network connectivity</span></span>

<span data-ttu-id="19195-136">Jeśli planujesz wdrożenie tego scenariusza między [dzierżawami,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)być może potrzebujesz licencji Information Barriers.</span><span class="sxs-lookup"><span data-stu-id="19195-136">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="19195-137">Zapoznaj [się z tym artykułem,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) aby ustalić, czy jest wymagana licencja information barrier.</span><span class="sxs-lookup"><span data-stu-id="19195-137">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="19195-138">Ten przewodnik zawiera informacje na temat:</span><span class="sxs-lookup"><span data-stu-id="19195-138">In this guide you will:</span></span>

<span data-ttu-id="19195-139">Przygotować:</span><span class="sxs-lookup"><span data-stu-id="19195-139">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="19195-140">Dowiedz się więcej na temat podstawowych informacji o infrastrukturze dla urządzeń HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="19195-140">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="19195-141">Dowiedz się więcej o usłudze Azure AD i skonfiguruj ją, jeśli&#39;jej nie masz.</span><span class="sxs-lookup"><span data-stu-id="19195-141">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="19195-142">Dowiedz się więcej na temat zarządzania tożsamościami i sposobu najlepszego skonfigurowania kont usługi Azure AD.</span><span class="sxs-lookup"><span data-stu-id="19195-142">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="19195-143">Dowiedz się więcej na temat zarządzania urządzeniami przenośnymi i skonfiguruj usługę Intune, jeśli&#39;jeszcze nie jest gotowa.</span><span class="sxs-lookup"><span data-stu-id="19195-143">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="19195-144">Dowiedz się więcej o wymaganiach dotyczących sieci usługi Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="19195-144">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="19195-145">Opcjonalnie: sieć VPN do łączenia się z zasobami organizacji</span><span class="sxs-lookup"><span data-stu-id="19195-145">Optionally: VPN to connect to organizational resources</span></span>](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="19195-146">Skonfiguruj:</span><span class="sxs-lookup"><span data-stu-id="19195-146">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="19195-147">Jak utworzyć użytkowników i grupy.</span><span class="sxs-lookup"><span data-stu-id="19195-147">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="19195-148">Jak skonfigurować automatyczne rejestrowanie w usłudze Azure AD.</span><span class="sxs-lookup"><span data-stu-id="19195-148">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="19195-149">Jak przypisać licencje aplikacji.</span><span class="sxs-lookup"><span data-stu-id="19195-149">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="19195-150">Wdrażanie:</span><span class="sxs-lookup"><span data-stu-id="19195-150">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="19195-151">Skonfiguruj urządzenie HoloLens 2 i zweryfikuj rejestrację.</span><span class="sxs-lookup"><span data-stu-id="19195-151">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="19195-152">Sprawdź, czy można wykonać wywołanie funkcji Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="19195-152">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="19195-153">Utrzymania:</span><span class="sxs-lookup"><span data-stu-id="19195-153">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="19195-154">Jak zaktualizować usługę Remote Assist przy użyciu Microsoft Store aplikacji.</span><span class="sxs-lookup"><span data-stu-id="19195-154">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="19195-155">Tworzenie planu pomocy technicznej.</span><span class="sxs-lookup"><span data-stu-id="19195-155">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="19195-156">Plan rozwoju.</span><span class="sxs-lookup"><span data-stu-id="19195-156">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="19195-157">Następny krok</span><span class="sxs-lookup"><span data-stu-id="19195-157">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="19195-158">Wdrożenie połączone z chmurą — przygotowanie</span><span class="sxs-lookup"><span data-stu-id="19195-158">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

