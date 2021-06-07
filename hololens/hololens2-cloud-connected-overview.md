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
ms.openlocfilehash: 43fbcc3a841f6c3f15006f285188e55d22f10599
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378247"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="34513-104">Przewodnik wdrażania — urządzenie HoloLens 2 połączone z chmurą ze zdalną asystą — omówienie</span><span class="sxs-lookup"><span data-stu-id="34513-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="34513-105">Ten przewodnik pomaga specjalistom IT w planowaniu i wdrażaniu urządzeń z systemem Microsoft HoloLens 2 w organizacji w ogólnym celu, aby chmura tych urządzeń była połączona z twoją organizacją przy użyciu usługi Dynamics 365 Remote Assist gotowej do użycia.</span><span class="sxs-lookup"><span data-stu-id="34513-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="34513-106">Należy pamiętać, że będzie to model wdrożeń weryfikacji koncepcji w organizacji w różnych przypadkach użycia urządzenia HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="34513-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="34513-107">W tym przewodniku opisano sposób rejestrowania urządzeń w zarządzaniu urządzeniami, stosowania licencji zgodnie z potrzebami i sprawdzania, czy użytkownicy końcowi mogą natychmiast korzystać z usługi Remote Assist podczas konfigurowania urządzenia.</span><span class="sxs-lookup"><span data-stu-id="34513-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="34513-108">W tym celu przejmiemy ważne elementy infrastruktury potrzebne do skonfigurowania i uruchomienia — osiągnięcie wdrożenia na dużą skalę za pomocą urządzenia HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="34513-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

<span data-ttu-id="34513-109">[![Scenariusz połączony z chmurą ](./images/deployment-guides-revised-scenario-a.png)](./images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="34513-109">[ ![Cloud connected scenario](./images/deployment-guides-revised-scenario-a.png) ](./images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>
## <a name="in-this-guide"></a><span data-ttu-id="34513-110">W tym przewodniku</span><span class="sxs-lookup"><span data-stu-id="34513-110">In this Guide</span></span>

<span data-ttu-id="34513-111">Celem tego przewodnika jest skonfigurowanie usługi Remote Assist w organizacji na urządzeniach HoloLens.</span><span class="sxs-lookup"><span data-stu-id="34513-111">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="34513-112">Zostaną pokrytą koniecznością niezbędną do osiągnięcia tego celu.</span><span class="sxs-lookup"><span data-stu-id="34513-112">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="34513-113">Aby można było skupić się na tym celu, niektóre przygotowania i konfiguracje zostaną wstępnie wybrane w celu zoptymalizowania pod kątem tego wdrożenia lub zmniejszenia ilości elementów wymaganych do skonfigurowania.</span><span class="sxs-lookup"><span data-stu-id="34513-113">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="34513-114">Będziesz mieć informacje o tych wyborach i będziesz w stanie dostosować wdrożenie do swoich potrzeb biznesowych.</span><span class="sxs-lookup"><span data-stu-id="34513-114">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="34513-115">Jest to konfiguracja podobna do scenariusza [A:](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)wdrażanie na urządzeniach z połączeniami w chmurze, co jest dobrą opcją dla wielu wdrożeń weryfikacji koncepcji, które obejmują:</span><span class="sxs-lookup"><span data-stu-id="34513-115">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="34513-116">Wi-Fi są zwykle w pełni otwarte dla Internetu i usług w chmurze</span><span class="sxs-lookup"><span data-stu-id="34513-116">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="34513-117">Dołączanie do usługi Azure AD z automatyczną rejestracją w usłudze MDM — zarządzane przez rozwiązanie MDM (Intune)</span><span class="sxs-lookup"><span data-stu-id="34513-117">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="34513-118">Użytkownicy logują się przy użyciu własnego konta firmowego (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="34513-118">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="34513-119">Obsługiwanych jest jeden lub wielu użytkowników na urządzenie</span><span class="sxs-lookup"><span data-stu-id="34513-119">Single or multiple users per device supported</span></span>
- <span data-ttu-id="34513-120">Różne poziomy konfiguracji blokady urządzeń są stosowane na podstawie konkretnych przypadków użycia, od całkowitego otwarcia do kiosku z jedną aplikacją</span><span class="sxs-lookup"><span data-stu-id="34513-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>



<span data-ttu-id="34513-121">W tym przewodniku nie będą stosowane żadne inne ograniczenia ani konfiguracje urządzeń, jednak zachęcamy do eksplorowania tych opcji po zakończeniu.</span><span class="sxs-lookup"><span data-stu-id="34513-121">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <a name="learn-about-remote-assist"></a><span data-ttu-id="34513-122">Dowiedz się więcej o pomocy zdalnej</span><span class="sxs-lookup"><span data-stu-id="34513-122">Learn about Remote Assist</span></span>

<span data-ttu-id="34513-123">Usługa Remote Assist umożliwia wspólną konserwację i naprawę, zdalną inspekcję, a także udostępnianie i szkolenie wiedzy.</span><span class="sxs-lookup"><span data-stu-id="34513-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="34513-124">Łącząc osoby w różnych rolach i lokalizacjach, technik korzystający z usługi Remote Assist może nawiązać połączenie ze zdalnym współpracownikiem w aplikacji Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="34513-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="34513-125">Mogą one łączyć wideo, zrzuty ekranu i adnotacje, aby rozwiązywać problemy w czasie rzeczywistym, nawet&#39;nie w tej samej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="34513-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="34513-126">Zdalni współpracownicy mogą wstawiać obrazy referencyjne, schematy i inne przydatne informacje, które technik&#39;w fizycznej przestrzeni, dzięki czemu mogą odwoływać się do schematu podczas pracy z orzełami i bez rąk na urządzeniach HoloLens.</span><span class="sxs-lookup"><span data-stu-id="34513-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="34513-127">Ten przewodnik zawiera informacje na temat:</span><span class="sxs-lookup"><span data-stu-id="34513-127">In this guide you will:</span></span>

<span data-ttu-id="34513-128">Przygotować:</span><span class="sxs-lookup"><span data-stu-id="34513-128">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="34513-129">Dowiedz się więcej na temat podstawowych informacji o infrastrukturze dla urządzeń HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="34513-129">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="34513-130">Dowiedz się więcej o usłudze Azure AD i skonfiguruj ją, jeśli&#39;jej nie masz.</span><span class="sxs-lookup"><span data-stu-id="34513-130">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="34513-131">Dowiedz się więcej na temat zarządzania tożsamościami i sposobu najlepszego skonfigurowania kont usługi Azure AD.</span><span class="sxs-lookup"><span data-stu-id="34513-131">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="34513-132">Dowiedz się więcej na temat zarządzania urządzeniami przenośnymi i skonfiguruj usługę Intune, jeśli&#39;jeszcze nie jest gotowa.</span><span class="sxs-lookup"><span data-stu-id="34513-132">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="34513-133">Dowiedz się więcej o wymaganiach dotyczących sieci usługi Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="34513-133">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="34513-134">Opcjonalnie: sieć VPN do łączenia się z zasobami organizacji</span><span class="sxs-lookup"><span data-stu-id="34513-134">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="34513-135">Skonfiguruj:</span><span class="sxs-lookup"><span data-stu-id="34513-135">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="34513-136">Jak utworzyć użytkowników i grupy.</span><span class="sxs-lookup"><span data-stu-id="34513-136">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="34513-137">Jak skonfigurować automatyczne rejestrowanie w usłudze Azure AD.</span><span class="sxs-lookup"><span data-stu-id="34513-137">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="34513-138">Jak przypisać licencje aplikacji.</span><span class="sxs-lookup"><span data-stu-id="34513-138">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="34513-139">Wdrażanie:</span><span class="sxs-lookup"><span data-stu-id="34513-139">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="34513-140">Skonfiguruj urządzenie HoloLens 2 i zweryfikuj rejestrację.</span><span class="sxs-lookup"><span data-stu-id="34513-140">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="34513-141">Zweryfikuj, czy można wykonać wywołanie funkcji Remote Assist.</span><span class="sxs-lookup"><span data-stu-id="34513-141">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="34513-142">Utrzymania:</span><span class="sxs-lookup"><span data-stu-id="34513-142">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="34513-143">Jak zaktualizować usługę Remote Assist przy użyciu Microsoft Store aplikacji.</span><span class="sxs-lookup"><span data-stu-id="34513-143">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="34513-144">Tworzenie planu pomocy technicznej.</span><span class="sxs-lookup"><span data-stu-id="34513-144">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="34513-145">Plan rozwoju.</span><span class="sxs-lookup"><span data-stu-id="34513-145">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="34513-146">Następny krok</span><span class="sxs-lookup"><span data-stu-id="34513-146">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="34513-147">Wdrożenie połączone z chmurą — przygotowanie</span><span class="sxs-lookup"><span data-stu-id="34513-147">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

