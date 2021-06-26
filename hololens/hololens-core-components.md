---
title: Planowanie wdrożenia urządzenia HoloLens 2 w środowisku komercyjnym
description: Poznaj podstawowe potrzeby dotyczące wdrażania urządzenia HoloLens i zarządzania nim w środowiskach przedsiębiorstwa, w tym infrastruktury, usługi Azure Active Directory i zarządzania urządzeniami przenośnymi.
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
ms.openlocfilehash: 684059b1ab91860dc6af63cbd6f0927876fefb8c
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961482"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a><span data-ttu-id="c659b-103">Planowanie wdrożenia urządzenia HoloLens 2 w środowisku komercyjnym</span><span class="sxs-lookup"><span data-stu-id="c659b-103">Planning HoloLens 2 deployment in a commercial environment</span></span>

## <a name="overview"></a><span data-ttu-id="c659b-104">Omówienie</span><span class="sxs-lookup"><span data-stu-id="c659b-104">Overview</span></span>
> [!NOTE]
> <span data-ttu-id="c659b-105">To omówienie ma na celu pomoc specjalistom IT w zrozumieniu kwestii, które należy wziąć pod uwagę podczas wdrażania 2 urządzeń w Microsoft HoloLens i zarządzania nimi w organizacji.</span><span class="sxs-lookup"><span data-stu-id="c659b-105">This overview is intended to help IT professionals understand considerations for deploying and managing Microsoft HoloLens 2 devices within an organization.</span></span> <span data-ttu-id="c659b-106">Aby rozpocząć pracę, zobacz [Podstawowe informacje](hololens2-setup.md) dla użytkowników końcowych urządzeń.</span><span class="sxs-lookup"><span data-stu-id="c659b-106">For device end users, see [The Basics](hololens2-setup.md) to get started.</span></span>

<span data-ttu-id="c659b-107">Urządzenie HoloLens 2 działa na platformie Windows 10 Holographic która zapewnia organizacjom niezawodne, elastyczne, wbudowane technologie zarządzania urządzeniami przenośnymi i aplikacją.</span><span class="sxs-lookup"><span data-stu-id="c659b-107">HoloLens 2 runs on Windows 10 Holographic which provides organizations with robust, flexible, built-in mobile device and app management technologies.</span></span> <span data-ttu-id="c659b-108">Windows 10 Holographic obsługuje zarządzanie całym cyklem życia urządzeń, aby zapewnić firmom kontrolę nad ich urządzeniami, danymi i aplikacjami.</span><span class="sxs-lookup"><span data-stu-id="c659b-108">Windows 10 Holographic supports end-to-end device lifecycle management to give companies control over their devices, data, and apps.</span></span> <span data-ttu-id="c659b-109">Urządzenie HoloLens 2 można łatwo włączyć do standardowych rozwiązań w zakresie cyklu życia, od rejestracji urządzeń, konfiguracji i zarządzania aplikacją po konserwację i wycofanie przy użyciu kompleksowego rozwiązania do zarządzania urządzeniami przenośnymi.</span><span class="sxs-lookup"><span data-stu-id="c659b-109">The HoloLens 2 can easily be incorporated into standard lifecycle practices, from device enrollment, configuration, and application management to maintenance and retirement using a comprehensive mobile device management solution.</span></span>

<span data-ttu-id="c659b-110">Poniższe kroki mogą pomóc w sposobie wdrożenia urządzenia HoloLens 2 w organizacji.</span><span class="sxs-lookup"><span data-stu-id="c659b-110">The following steps can help guide you through the process of HoloLens 2 adoption within your organization.</span></span>

| | |
|--|--|
| ![Krok 1](images/1green.png)| <br/> <span data-ttu-id="c659b-112">**[Typowe scenariusze wdrażania:](hololens-requirements.md)** Poznaj scenariusze wdrażania i poznaj podstawowe składniki potrzebne do wdrożenia urządzeń HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="c659b-112">**[Common Deployment Scenarios](hololens-requirements.md)**: Understand deployment scenarios and explore the core components needed to deploy HoloLens 2 devices.</span></span> |
| ![Krok 2](images/2green.png)| <br/> <span data-ttu-id="c659b-114">**[Przygotowanie:](#prepare)** zapoznaj się z podstawowymi elementami infrastruktury potrzebnymi dla urządzenia HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="c659b-114">**[Prepare](#prepare)**: Become familiar with the infrastructure essentials needed for HoloLens 2.</span></span> |
| ![Krok 3](images/3green.png) | <br/> <span data-ttu-id="c659b-116">**[Konfigurowanie:](#configure)** dowiedz się, jak skonfigurować podstawowe składniki dla wdrożenia opartego na chmurze.</span><span class="sxs-lookup"><span data-stu-id="c659b-116">**[Configure](#configure)**: Learn how to configure your essential components for a cloud-based deployment.</span></span> |
| ![Krok 4](images/4green.png) | <br/> <span data-ttu-id="c659b-118">**[Wdrażanie:](#deploy)** dowiedz się, jak wdrażać urządzenia oraz bezpiecznie i wydajnie dystrybuować aplikacje.</span><span class="sxs-lookup"><span data-stu-id="c659b-118">**[Deploy](#deploy)**: Discover how to deploy your devices and distribute your applications securely and efficiently.</span></span> |
| ![Krok 5](images/5green.png) | <br/> <span data-ttu-id="c659b-120">**[Obsługa:](#maintain)** dowiedz się, co jest potrzebne do prawidłowego zachowania stanu urządzeń HoloLens 2 i zapewnienia zgodności z zasadami firmowym.</span><span class="sxs-lookup"><span data-stu-id="c659b-120">**[Maintain](#maintain)**: Find out what's needed to properly maintain the state of your HoloLens 2 devices and ensure compliance with corporate policy.</span></span> |

## <a name="prepare"></a><span data-ttu-id="c659b-121">Przygotowywanie</span><span class="sxs-lookup"><span data-stu-id="c659b-121">Prepare</span></span>

<span data-ttu-id="c659b-122">Dowiedz się więcej o podstawowych usługach infrastruktury wymaganych do obsługi pełnego zestawu funkcji urządzenia HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="c659b-122">Learn about essential infrastructure services required to support the full set of HoloLens 2 capabilities.</span></span> 

| <span data-ttu-id="c659b-123">Składnik</span><span class="sxs-lookup"><span data-stu-id="c659b-123">Component</span></span> | <span data-ttu-id="c659b-124">Opis</span><span class="sxs-lookup"><span data-stu-id="c659b-124">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="c659b-125">Azure AD</span><span class="sxs-lookup"><span data-stu-id="c659b-125">Azure AD</span></span>](hololens-identity.md) | <span data-ttu-id="c659b-126">Zapewnia zarządzanie tożsamościami i dostępem dla urządzenia HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="c659b-126">Provides identity and access management for the HoloLens 2</span></span>  |
| [<span data-ttu-id="c659b-127">Zarządzanie urządzeniami przenośnymi</span><span class="sxs-lookup"><span data-stu-id="c659b-127">Mobile Device Management</span></span>](hololens-mdm-configure.md)| <span data-ttu-id="c659b-128">Zarządza urządzeniami HoloLens 2 połączonymi z dzierżawą</span><span class="sxs-lookup"><span data-stu-id="c659b-128">Manages HoloLens 2 devices connected to your tenant</span></span>  |
| [<span data-ttu-id="c659b-129">Sieć Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="c659b-129">Wi-Fi Network</span></span>](hololens-commercial-infrastructure.md)| <span data-ttu-id="c659b-130">Wi-Fi jest dostępna, a urządzenia mogą być połączone z Internetem</span><span class="sxs-lookup"><span data-stu-id="c659b-130">Wi-Fi is available and devices can be connected to the Internet</span></span>  |

## <a name="configure"></a><span data-ttu-id="c659b-131">Konfigurowanie</span><span class="sxs-lookup"><span data-stu-id="c659b-131">Configure</span></span>

<span data-ttu-id="c659b-132">Użyj usługi Intune i rozwiązania Autopilot jako rozwiązań o niskim poziomie dotyku do rejestrowania i konfigurowania urządzenia HoloLens 2 w dzierżawie usługi Azure AD i rozwiązaniu MDM organizacji.</span><span class="sxs-lookup"><span data-stu-id="c659b-132">Use Intune and Autopilot as low-touch solutions for enrolling and configuring HoloLens 2 to your organization’s Azure AD tenant and MDM.</span></span>

| <span data-ttu-id="c659b-133">Składnik</span><span class="sxs-lookup"><span data-stu-id="c659b-133">Component</span></span> | <span data-ttu-id="c659b-134">Opis</span><span class="sxs-lookup"><span data-stu-id="c659b-134">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="c659b-135">Automatyczne rejestrowanie</span><span class="sxs-lookup"><span data-stu-id="c659b-135">Auto Enrollment</span></span>](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | <span data-ttu-id="c659b-136">Po początkowym zalogowaniu urządzenia automatycznie rejestrują się w usłudze Azure AD i rejestrują się w usłudze MDM</span><span class="sxs-lookup"><span data-stu-id="c659b-136">After initial login, devices automatically register with Azure AD and enroll into MDM</span></span>  |
| [<span data-ttu-id="c659b-137">Licencje aplikacji</span><span class="sxs-lookup"><span data-stu-id="c659b-137">Application Licenses</span></span>](hololens2-cloud-connected-configure.md#application-licenses)| <span data-ttu-id="c659b-138">Można stosować do użytkowników, grup użytkowników lub grup urządzeń</span><span class="sxs-lookup"><span data-stu-id="c659b-138">Can be applied to either users, user groups, or device groups</span></span>  |
| [<span data-ttu-id="c659b-139">Użytkownicy i grupy platformy Azure</span><span class="sxs-lookup"><span data-stu-id="c659b-139">Azure Users and Groups</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups) | <span data-ttu-id="c659b-140">Ułatwia przypisywanie konfiguracji i licencji dla urządzenia HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="c659b-140">Helps assign configurations and licenses for the HoloLens 2</span></span>  |

## <a name="deploy"></a><span data-ttu-id="c659b-141">Wdróż</span><span class="sxs-lookup"><span data-stu-id="c659b-141">Deploy</span></span>

<span data-ttu-id="c659b-142">Rozdystrybuuj urządzenia HoloLens 2 i zweryfikuj ich konfigurację.</span><span class="sxs-lookup"><span data-stu-id="c659b-142">Distribute your HoloLens 2 devices and validate their configuration.</span></span> 

| <span data-ttu-id="c659b-143">Składnik</span><span class="sxs-lookup"><span data-stu-id="c659b-143">Component</span></span> | <span data-ttu-id="c659b-144">Opis</span><span class="sxs-lookup"><span data-stu-id="c659b-144">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="c659b-145">Walidacja rejestracji</span><span class="sxs-lookup"><span data-stu-id="c659b-145">Enrollment Validation</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation) | <span data-ttu-id="c659b-146">Sprawdzanie, czy urządzenie jest przyłączone do usługi Azure AD z ustawień lub witryny Azure Portal</span><span class="sxs-lookup"><span data-stu-id="c659b-146">Validate the device has Azure AD Joined from Settings or the Azure Portal</span></span> |
| [<span data-ttu-id="c659b-147">Walidacja certyfikatu</span><span class="sxs-lookup"><span data-stu-id="c659b-147">Certificate Validation</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | <span data-ttu-id="c659b-148">Sprawdzanie ustawień i sprawdzanie, czy zostały one poprawnie dystrybuowane</span><span class="sxs-lookup"><span data-stu-id="c659b-148">Check settings and validate they have been distributed correctly</span></span> |
| [<span data-ttu-id="c659b-149">Weryfikowanie instalacji aplikacji</span><span class="sxs-lookup"><span data-stu-id="c659b-149">Validate app installs</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install) | <span data-ttu-id="c659b-150">Potwierdzanie, że aplikacja jest obecna i działa na urządzeniach HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="c659b-150">Confirm the app is present and working on your HoloLens 2</span></span> |

## <a name="maintain"></a><span data-ttu-id="c659b-151">Obsługa</span><span class="sxs-lookup"><span data-stu-id="c659b-151">Maintain</span></span>

<span data-ttu-id="c659b-152">Używaj Windows Update dla Firm z systemem MDM lub Microsoft Store, aby zachować swoją flotę urządzeń HoloLens 2 i aplikacji na bieżąco.</span><span class="sxs-lookup"><span data-stu-id="c659b-152">Use Windows Update for Business along with your MDM system or the Microsoft Store to keep your fleet of HoloLens 2 and apps updated.</span></span>

| <span data-ttu-id="c659b-153">Składnik</span><span class="sxs-lookup"><span data-stu-id="c659b-153">Component</span></span> | <span data-ttu-id="c659b-154">Opis</span><span class="sxs-lookup"><span data-stu-id="c659b-154">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="c659b-155">Aktualizowanie urządzenia HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="c659b-155">Update HoloLens 2</span></span>](hololens-updates.md) | <span data-ttu-id="c659b-156">Konfigurowanie aktualizacji zgodnie z potrzebami za pomocą aktualizacji systemu Windows dla firm</span><span class="sxs-lookup"><span data-stu-id="c659b-156">Configure updates as needed through Windows Updates for Business</span></span> |
| [<span data-ttu-id="c659b-157">Aktualizowanie aplikacji</span><span class="sxs-lookup"><span data-stu-id="c659b-157">Update apps</span></span>](app-deploy-overview.md) | <span data-ttu-id="c659b-158">Konfigurowanie za pośrednictwem systemu MDM lub Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="c659b-158">Configure through your MDM system or the Microsoft Store</span></span>
