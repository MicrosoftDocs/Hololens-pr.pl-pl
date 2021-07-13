---
title: Przewodnik wdrażania — połączone z HoloLens 2 z usługą Dynamics 365 — przewodniki — omówienie
description: Dowiedz się, jak zarejestrować HoloLens 2 za pomocą przewodników usługi Dynamics 365 za pośrednictwem połączonej sieci firmowej.
keywords: HoloLens, zarządzanie, połączenie firmowe, przewodniki usługi Dynamics 365, AAD, Azure AD, MDM, Mobile Zarządzanie urządzeniami
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f2f7e1425a208e1f466d995f66118b7e68984242
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637017"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="62586-104">Przewodnik wdrażania — przewodnik po rozwiązaniach HoloLens 2 z usługą Dynamics 365 — omówienie</span><span class="sxs-lookup"><span data-stu-id="62586-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="62586-105">Ten przewodnik pomoże specjalistom IT w planowaniu i wdrażaniu urządzeń Microsoft HoloLens 2 za pomocą przewodników usługi Dynamics 365 (przewodników) w organizacji.</span><span class="sxs-lookup"><span data-stu-id="62586-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="62586-106">Ten przewodnik jest doskonały dla wdrożeń pilotażowych i produkcyjnych i jest podobny do scenariusza B: wdrażanie wewnątrz [sieci organizacji.](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network)</span><span class="sxs-lookup"><span data-stu-id="62586-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="62586-107">Po przetestowaniu weryfikacji koncepcji skorzystaj z tego przewodnika, aby przejść dalej dzięki integracji HoloLens z twoją organizacją.</span><span class="sxs-lookup"><span data-stu-id="62586-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="62586-108">W tym przewodniku opisano sposób rejestrowania urządzeń w istniejącym zarządzaniu urządzeniami, stosowania licencji zgodnie z potrzebami i sprawdzania, czy użytkownicy końcowi mogą korzystać z przewodnika usługi Dynamics 365, a także jak korzystać z niestandardowych aplikacji biznesowych po skonfigurowaniu urządzenia.</span><span class="sxs-lookup"><span data-stu-id="62586-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="62586-109">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="62586-109">Prerequisites</span></span>

<span data-ttu-id="62586-110">Powinna być już w tym miejscu następująca infrastruktura:</span><span class="sxs-lookup"><span data-stu-id="62586-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="62586-111">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="62586-111">Wi-Fi</span></span>
    - <span data-ttu-id="62586-112">Wewnętrzna sieć firmowa z dostępem do zasobów wewnętrznych i ograniczonym dostępem do Internetu lub usług w chmurze</span><span class="sxs-lookup"><span data-stu-id="62586-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="62586-113">Uwierzytelnianie certyfikatu opartego na urządzeniach.</span><span class="sxs-lookup"><span data-stu-id="62586-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="62586-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment (Azure AD P1 subscription needed) (Dołączanie do usługi Azure AD za pomocą automatycznej rejestracji w usłudze MDM ([potrzebna jest subskrypcja usługi Azure AD P1)](/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="62586-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="62586-115">Zarządzanie urządzeniami przenośnymi (Intune)</span><span class="sxs-lookup"><span data-stu-id="62586-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="62586-116">Co najmniej jedna aplikacja jest wdrażana za pośrednictwem rozwiązania MDM.</span><span class="sxs-lookup"><span data-stu-id="62586-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="62586-117">Sieć</span><span class="sxs-lookup"><span data-stu-id="62586-117">Network</span></span> 
    - <span data-ttu-id="62586-118">Certyfikaty (SCEP lub PKCS)</span><span class="sxs-lookup"><span data-stu-id="62586-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="62586-119">Konfiguracja serwera proxy</span><span class="sxs-lookup"><span data-stu-id="62586-119">Proxy configuration</span></span>
- <span data-ttu-id="62586-120">Użytkownicy logują się przy użyciu własnego konta firmowego (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="62586-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="62586-121">Obsługiwana jest jedna lub wielu użytkowników na urządzenie.</span><span class="sxs-lookup"><span data-stu-id="62586-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="62586-122">Różne poziomy konfiguracji blokady urządzeń stosowanych na podstawie konkretnych przypadków użycia, od w pełni otwartego do kiosku z jedną aplikacją.</span><span class="sxs-lookup"><span data-stu-id="62586-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## <a name="guides-licensing-and-requirements"></a>[<span data-ttu-id="62586-123">Licencjonowanie przewodników i wymagania</span><span class="sxs-lookup"><span data-stu-id="62586-123">Guides Licensing and Requirements</span></span>](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- <span data-ttu-id="62586-124">Konto usługi Azure AD</span><span class="sxs-lookup"><span data-stu-id="62586-124">Azure AD account</span></span>
- <span data-ttu-id="62586-125">Dynamics 365 Prowadzi aplikacje na komputerach pc i HoloLens</span><span class="sxs-lookup"><span data-stu-id="62586-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="62586-126">Subskrypcja przewodników usługi Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="62586-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="62586-127">Microsoft Dataverse (dołączone)</span><span class="sxs-lookup"><span data-stu-id="62586-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="62586-128">Power Apps (dołączone)</span><span class="sxs-lookup"><span data-stu-id="62586-128">Power Apps (included)</span></span>
- <span data-ttu-id="62586-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="62586-129">Power BI Desktop</span></span>
- <span data-ttu-id="62586-130">Łączność sieciowa</span><span class="sxs-lookup"><span data-stu-id="62586-130">Network Connectivity</span></span>

<span data-ttu-id="62586-131">[![Diagram sieci połączony z firmami, etap 1 ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="62586-131">[ ![Corp connected network diagram, stage 1](./images/deployment-guides-revised-scenario-b-01-1.png) ](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="62586-132">[![Diagram sieci połączony z firmami, etap 2 ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="62586-132">[ ![Corp connected network diagram, stage 2](./images/deployment-guides-revised-scenario-b-02-1.png) ](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="62586-133">Ten przewodnik zawiera informacje na temat:</span><span class="sxs-lookup"><span data-stu-id="62586-133">In this guide you will:</span></span>
### <a name="prepare"></a><span data-ttu-id="62586-134">Przygotowywanie</span><span class="sxs-lookup"><span data-stu-id="62586-134">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="62586-135">Poznaj podstawowe informacje o infrastrukturze dla HoloLens 2 urządzeń.</span><span class="sxs-lookup"><span data-stu-id="62586-135">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="62586-136">Dowiedz się więcej o usłudze Azure AD i skonfiguruj ją, jeśli jej nie masz.</span><span class="sxs-lookup"><span data-stu-id="62586-136">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="62586-137">Dowiedz się więcej na temat zarządzania tożsamościami i sposobu najlepszego skonfigurowania kont usługi Azure AD.</span><span class="sxs-lookup"><span data-stu-id="62586-137">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="62586-138">Dowiedz się więcej o usłudze MDM i skonfiguruj usługę Intune, jeśli jeszcze jej nie masz.</span><span class="sxs-lookup"><span data-stu-id="62586-138">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="62586-139">Zapoznaj się z siecią Wi-Fi opartą na certyfikatach.</span><span class="sxs-lookup"><span data-stu-id="62586-139">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="62586-140">Zapoznaj się z serwerem proxy.</span><span class="sxs-lookup"><span data-stu-id="62586-140">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="62586-141">Dowiedz się, jak używać aplikacji biznesowych.</span><span class="sxs-lookup"><span data-stu-id="62586-141">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="62586-142">Dowiedz się więcej na temat sposobu korzystania z przewodników w organizacji.</span><span class="sxs-lookup"><span data-stu-id="62586-142">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="62586-143">Konfigurowanie</span><span class="sxs-lookup"><span data-stu-id="62586-143">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="62586-144">Jak tworzyć użytkowników i grupy.</span><span class="sxs-lookup"><span data-stu-id="62586-144">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="62586-145">Jak skonfigurować rejestrację automatyczną.</span><span class="sxs-lookup"><span data-stu-id="62586-145">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="62586-146">Jak skonfigurować certyfikaty Wi-Fi profilów dla połączeń Wi-Fi firmowych.</span><span class="sxs-lookup"><span data-stu-id="62586-146">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="62586-147">Upload i przypisywanie pakietów aplikacji biznesowych.</span><span class="sxs-lookup"><span data-stu-id="62586-147">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="62586-148">Konfigurowanie przewodników usługi Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="62586-148">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="62586-149">Jak skonfigurować tryb kiosku (opcjonalnie).</span><span class="sxs-lookup"><span data-stu-id="62586-149">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="62586-150">Jak skonfigurować usługę WDAC (opcjonalnie).</span><span class="sxs-lookup"><span data-stu-id="62586-150">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="62586-151">Wdróż</span><span class="sxs-lookup"><span data-stu-id="62586-151">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="62586-152">Zweryfikuj rejestrację za pośrednictwem urządzenia i rozwiązania MDM.</span><span class="sxs-lookup"><span data-stu-id="62586-152">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="62586-153">Zweryfikuj Wi-Fi certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="62586-153">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="62586-154">Zweryfikuj instalację aplikacji LOB.</span><span class="sxs-lookup"><span data-stu-id="62586-154">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="62586-155">Zweryfikuj przewodniki za pośrednictwem tworzenia i obsługi.</span><span class="sxs-lookup"><span data-stu-id="62586-155">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="62586-156">Obsługa</span><span class="sxs-lookup"><span data-stu-id="62586-156">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="62586-157">Zaktualizuj HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="62586-157">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="62586-158">Jak aktualizować przewodniki (aplikacje ze sklepu).</span><span class="sxs-lookup"><span data-stu-id="62586-158">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="62586-159">Jak aktualizować aplikacje LOB.</span><span class="sxs-lookup"><span data-stu-id="62586-159">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="62586-160">Plan rozwoju.</span><span class="sxs-lookup"><span data-stu-id="62586-160">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="62586-161">Tworzenie planu pomocy technicznej.</span><span class="sxs-lookup"><span data-stu-id="62586-161">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="62586-162">Opcje zarządzania urządzeniami.</span><span class="sxs-lookup"><span data-stu-id="62586-162">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="62586-163">Następny krok</span><span class="sxs-lookup"><span data-stu-id="62586-163">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="62586-164">Wdrożenie połączone z firmą — przygotowanie</span><span class="sxs-lookup"><span data-stu-id="62586-164">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
