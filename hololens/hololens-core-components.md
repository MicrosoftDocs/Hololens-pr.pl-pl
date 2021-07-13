---
title: Planowanie HoloLens 2 w środowisku komercyjnym
description: Poznaj podstawowe potrzeby dotyczące wdrażania aplikacji i zarządzania nimi HoloLens środowiskach przedsiębiorstwa, w tym infrastruktury, usługi Azure Active Directory i zarządzania urządzeniami przenośnymi.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 43162389eae82bc09135c62acd40d71048d14db1
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639084"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a><span data-ttu-id="1461f-103">Planowanie HoloLens 2 w środowisku komercyjnym</span><span class="sxs-lookup"><span data-stu-id="1461f-103">Planning HoloLens 2 deployment in a commercial environment</span></span>

## <a name="overview"></a><span data-ttu-id="1461f-104">Omówienie</span><span class="sxs-lookup"><span data-stu-id="1461f-104">Overview</span></span>

> [!NOTE]
> <span data-ttu-id="1461f-105">To omówienie ma na celu pomóc specjalistom IT zrozumieć zagadnienia dotyczące wdrażania i zarządzania Microsoft HoloLens 2 urządzeniami w organizacji.</span><span class="sxs-lookup"><span data-stu-id="1461f-105">This overview is intended to help IT professionals understand considerations for deploying and managing Microsoft HoloLens 2 devices within an organization.</span></span> <span data-ttu-id="1461f-106">W przypadku użytkowników końcowych urządzeń zobacz [Get your HoloLens 2 ready to use](hololens2-setup.md) to get started (Przygotuj urządzenie do użycia w celu rozpoczęcia pracy).</span><span class="sxs-lookup"><span data-stu-id="1461f-106">For device end users, see [Get your HoloLens 2 ready to use](hololens2-setup.md) to get started.</span></span>

<span data-ttu-id="1461f-107">HoloLens 2 działa na platformie Windows 10 Holographic która zapewnia organizacjom niezawodne, elastyczne, wbudowane technologie zarządzania urządzeniami przenośnymi i aplikacją.</span><span class="sxs-lookup"><span data-stu-id="1461f-107">HoloLens 2 runs on Windows 10 Holographic which provides organizations with robust, flexible, built-in mobile device and app management technologies.</span></span> <span data-ttu-id="1461f-108">Windows 10 Holographic obsługuje zarządzanie całym cyklem życia urządzeń, aby zapewnić firmom kontrolę nad ich urządzeniami, danymi i aplikacjami.</span><span class="sxs-lookup"><span data-stu-id="1461f-108">Windows 10 Holographic supports end-to-end device lifecycle management to give companies control over their devices, data, and apps.</span></span> <span data-ttu-id="1461f-109">Usługę HoloLens 2 można łatwo włączyć do standardowych rozwiązań cyklu życia, od rejestracji urządzeń, konfiguracji i zarządzania aplikacją po konserwację i wycofanie przy użyciu kompleksowego rozwiązania do zarządzania urządzeniami przenośnymi.</span><span class="sxs-lookup"><span data-stu-id="1461f-109">The HoloLens 2 can easily be incorporated into standard lifecycle practices, from device enrollment, configuration, and application management to maintenance and retirement using a comprehensive mobile device management solution.</span></span>

<span data-ttu-id="1461f-110">Poniższe kroki i wideo mogą pomóc w sposobie wdrożenia HoloLens 2 w organizacji.</span><span class="sxs-lookup"><span data-stu-id="1461f-110">The following steps and video can help guide you through the process of HoloLens 2 adoption within your organization.</span></span>

| &nbsp; | &nbsp; |
|--|--|
| ![Krok 1](images/1green.png)| <br/> <span data-ttu-id="1461f-112">**[Typowe scenariusze wdrażania:](hololens-requirements.md)** Poznaj scenariusze wdrażania i poznaj podstawowe składniki potrzebne do wdrożenia HoloLens 2 urządzeń.</span><span class="sxs-lookup"><span data-stu-id="1461f-112">**[Common Deployment Scenarios](hololens-requirements.md)**: Understand deployment scenarios and explore the core components needed to deploy HoloLens 2 devices.</span></span> |
| ![Krok 2](images/2green.png)| <br/> <span data-ttu-id="1461f-114">**[Przygotowanie:](#prepare)** zapoznaj się z podstawowymi elementami infrastruktury wymaganymi w HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="1461f-114">**[Prepare](#prepare)**: Become familiar with the infrastructure essentials needed for HoloLens 2.</span></span> |
| ![Krok 3](images/3green.png) | <br/> <span data-ttu-id="1461f-116">**[Konfigurowanie:](#configure)** dowiedz się, jak skonfigurować podstawowe składniki dla wdrożenia opartego na chmurze.</span><span class="sxs-lookup"><span data-stu-id="1461f-116">**[Configure](#configure)**: Learn how to configure your essential components for a cloud-based deployment.</span></span> |
| ![Krok 4](images/4green.png) | <br/> <span data-ttu-id="1461f-118">**[Wdrażanie:](#deploy)** dowiedz się, jak wdrażać urządzenia oraz bezpiecznie i wydajnie dystrybuować aplikacje.</span><span class="sxs-lookup"><span data-stu-id="1461f-118">**[Deploy](#deploy)**: Discover how to deploy your devices and distribute your applications securely and efficiently.</span></span> |
| ![Krok 5](images/5green.png) | <br/> <span data-ttu-id="1461f-120">**[Obsługa:](#maintain)** dowiedz się, co jest potrzebne do prawidłowego utrzymania stanu urządzeń z systemem HoloLens 2 i zapewnienia zgodności z zasadami firmowym.</span><span class="sxs-lookup"><span data-stu-id="1461f-120">**[Maintain](#maintain)**: Find out what's needed to properly maintain the state of your HoloLens 2 devices and ensure compliance with corporate policy.</span></span> |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a><span data-ttu-id="1461f-121">Przygotowywanie</span><span class="sxs-lookup"><span data-stu-id="1461f-121">Prepare</span></span>

<span data-ttu-id="1461f-122">Dowiedz się więcej o podstawowych usługach infrastruktury wymaganych do obsługi pełnego zestawu HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="1461f-122">Learn about essential infrastructure services required to support the full set of HoloLens 2 capabilities.</span></span>

| <span data-ttu-id="1461f-123">Składnik</span><span class="sxs-lookup"><span data-stu-id="1461f-123">Component</span></span> | <span data-ttu-id="1461f-124">Opis</span><span class="sxs-lookup"><span data-stu-id="1461f-124">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="1461f-125">Azure AD</span><span class="sxs-lookup"><span data-stu-id="1461f-125">Azure AD</span></span>](hololens-identity.md) | <span data-ttu-id="1461f-126">Zapewnia zarządzanie tożsamościami i dostępem dla HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="1461f-126">Provides identity and access management for the HoloLens 2</span></span>  |
| [<span data-ttu-id="1461f-127">Zarządzanie urządzeniami przenośnymi</span><span class="sxs-lookup"><span data-stu-id="1461f-127">Mobile Device Management</span></span>](hololens-mdm-configure.md)| <span data-ttu-id="1461f-128">Zarządza 2 HoloLens połączonymi z dzierżawą</span><span class="sxs-lookup"><span data-stu-id="1461f-128">Manages HoloLens 2 devices connected to your tenant</span></span>  |
| [<span data-ttu-id="1461f-129">Sieć Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="1461f-129">Wi-Fi Network</span></span>](hololens-commercial-infrastructure.md)| <span data-ttu-id="1461f-130">Wi-Fi jest dostępna, a urządzenia mogą być połączone z Internetem</span><span class="sxs-lookup"><span data-stu-id="1461f-130">Wi-Fi is available and devices can be connected to the Internet</span></span>  |

## <a name="configure"></a><span data-ttu-id="1461f-131">Konfigurowanie</span><span class="sxs-lookup"><span data-stu-id="1461f-131">Configure</span></span>

<span data-ttu-id="1461f-132">Użyj usługi Intune i rozwiązania Autopilot jako rozwiązań o niskim poziomie dotyku do rejestrowania i konfigurowania HoloLens 2 w dzierżawie usługi Azure AD i rozwiązaniu MDM organizacji.</span><span class="sxs-lookup"><span data-stu-id="1461f-132">Use Intune and Autopilot as low-touch solutions for enrolling and configuring HoloLens 2 to your organization’s Azure AD tenant and MDM.</span></span>

| <span data-ttu-id="1461f-133">Składnik</span><span class="sxs-lookup"><span data-stu-id="1461f-133">Component</span></span> | <span data-ttu-id="1461f-134">Opis</span><span class="sxs-lookup"><span data-stu-id="1461f-134">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="1461f-135">Automatyczne rejestrowanie</span><span class="sxs-lookup"><span data-stu-id="1461f-135">Auto Enrollment</span></span>](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | <span data-ttu-id="1461f-136">Po początkowym zalogowaniu urządzenia automatycznie rejestrują się w usłudze Azure AD i rejestrują się w usłudze MDM</span><span class="sxs-lookup"><span data-stu-id="1461f-136">After initial login, devices automatically register with Azure AD and enroll into MDM</span></span>  |
| [<span data-ttu-id="1461f-137">Licencje aplikacji</span><span class="sxs-lookup"><span data-stu-id="1461f-137">Application Licenses</span></span>](hololens2-cloud-connected-configure.md#application-licenses)| <span data-ttu-id="1461f-138">Można stosować do użytkowników, grup użytkowników lub grup urządzeń</span><span class="sxs-lookup"><span data-stu-id="1461f-138">Can be applied to either users, user groups, or device groups</span></span>  |
| [<span data-ttu-id="1461f-139">Użytkownicy i grupy platformy Azure</span><span class="sxs-lookup"><span data-stu-id="1461f-139">Azure Users and Groups</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups) | <span data-ttu-id="1461f-140">Ułatwia przypisywanie konfiguracji i licencji dla HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="1461f-140">Helps assign configurations and licenses for the HoloLens 2</span></span>  |

## <a name="deploy"></a><span data-ttu-id="1461f-141">Wdróż</span><span class="sxs-lookup"><span data-stu-id="1461f-141">Deploy</span></span>

<span data-ttu-id="1461f-142">Rozdystrybuuj HoloLens 2 urządzenia i zweryfikuj ich konfigurację.</span><span class="sxs-lookup"><span data-stu-id="1461f-142">Distribute your HoloLens 2 devices and validate their configuration.</span></span> 

| <span data-ttu-id="1461f-143">Składnik</span><span class="sxs-lookup"><span data-stu-id="1461f-143">Component</span></span> | <span data-ttu-id="1461f-144">Opis</span><span class="sxs-lookup"><span data-stu-id="1461f-144">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="1461f-145">Walidacja rejestracji</span><span class="sxs-lookup"><span data-stu-id="1461f-145">Enrollment Validation</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation) | <span data-ttu-id="1461f-146">Sprawdzanie, czy urządzenie jest przyłączone do usługi Azure AD Ustawienia lub w witrynie Azure Portal</span><span class="sxs-lookup"><span data-stu-id="1461f-146">Validate the device has Azure AD Joined from Settings or the Azure Portal</span></span> |
| [<span data-ttu-id="1461f-147">Walidacja certyfikatu</span><span class="sxs-lookup"><span data-stu-id="1461f-147">Certificate Validation</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | <span data-ttu-id="1461f-148">Sprawdzanie ustawień i sprawdzanie, czy zostały one poprawnie dystrybuowane</span><span class="sxs-lookup"><span data-stu-id="1461f-148">Check settings and validate they have been distributed correctly</span></span> |
| [<span data-ttu-id="1461f-149">Weryfikowanie instalacji aplikacji</span><span class="sxs-lookup"><span data-stu-id="1461f-149">Validate app installs</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install) | <span data-ttu-id="1461f-150">Potwierdzanie, że aplikacja jest obecna i działa na komputerze HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="1461f-150">Confirm the app is present and working on your HoloLens 2</span></span> |

## <a name="maintain"></a><span data-ttu-id="1461f-151">Obsługa</span><span class="sxs-lookup"><span data-stu-id="1461f-151">Maintain</span></span>

<span data-ttu-id="1461f-152">Użyj Windows Update dla Firm wraz z systemem MDM lub Microsoft Store, aby zapewnić aktualizowanie floty maszyn HoloLens 2 i aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1461f-152">Use Windows Update for Business along with your MDM system or the Microsoft Store to keep your fleet of HoloLens 2 and apps updated.</span></span>

| <span data-ttu-id="1461f-153">Składnik</span><span class="sxs-lookup"><span data-stu-id="1461f-153">Component</span></span> | <span data-ttu-id="1461f-154">Opis</span><span class="sxs-lookup"><span data-stu-id="1461f-154">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="1461f-155">Aktualizacja HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="1461f-155">Update HoloLens 2</span></span>](hololens-updates.md) | <span data-ttu-id="1461f-156">Konfigurowanie aktualizacji zgodnie z potrzebami za pomocą Windows Updates for Business</span><span class="sxs-lookup"><span data-stu-id="1461f-156">Configure updates as needed through Windows Updates for Business</span></span> |
| [<span data-ttu-id="1461f-157">Aktualizowanie aplikacji</span><span class="sxs-lookup"><span data-stu-id="1461f-157">Update apps</span></span>](app-deploy-overview.md) | <span data-ttu-id="1461f-158">Konfigurowanie za pomocą systemu MDM lub Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="1461f-158">Configure through your MDM system or the Microsoft Store</span></span>
