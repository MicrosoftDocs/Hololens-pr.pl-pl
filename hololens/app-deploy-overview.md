---
title: Omówienie — zarządzanie aplikacją
description: Rozpoczynanie pracy z omówieniem zarządzania aplikacjami rzeczywistości mieszanej za pomocą zarządzania urządzeniami przenośnymi, sklepu Microsoft Store dla Firm i pakietów aprowizowania.
keywords: HoloLens, użytkownik, konto, aplikacja, zarządzanie aplikacją,
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ca87f34718319d489b69ba33ad24731628d87fac
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635555"
---
# <a name="app-management-overview"></a><span data-ttu-id="c8849-104">Zarządzanie aplikacją: Omówienie</span><span class="sxs-lookup"><span data-stu-id="c8849-104">App Management: Overview</span></span>

<span data-ttu-id="c8849-105">Aplikacje można wdrażać w czterech różnych ścieżkach: **mobile Zarządzanie urządzeniami (MDM),** **Microsoft Store dla Firm,** **Microsoft Store** lub przez zainstalowanie ich za pomocą **aprowizowania**.</span><span class="sxs-lookup"><span data-stu-id="c8849-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="c8849-106">Mobile Zarządzanie urządzeniami (MDM)</span><span class="sxs-lookup"><span data-stu-id="c8849-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="c8849-107">Rozwiązanie MDM umożliwia twórcom i administratorom IT prywatną automatyczną instalację (wypychanie) własnych aplikacji biznesowych lub kupowanie aplikacji za pośrednictwem sklepu dla grupy użytkowników.</span><span class="sxs-lookup"><span data-stu-id="c8849-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="c8849-108">HoloLens działają najlepiej z usługą Microsoft Endpoint Manager (Intune) do [zarządzania aplikacją.](app-deploy-intune.md)</span><span class="sxs-lookup"><span data-stu-id="c8849-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="c8849-109">Usługa Intune oferuje również użytkownikom wędszą kontrolę nad aplikacjami zarządzanymi przez it za pośrednictwem Portal firmy do pobrania.</span><span class="sxs-lookup"><span data-stu-id="c8849-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="c8849-110">Poniższe instrukcje są dostępne dla użytkowników, którzy chcą zarządzać aplikacjami za pomocą usługi Intune.</span><span class="sxs-lookup"><span data-stu-id="c8849-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="c8849-111">Firma Microsoft zaleca używanie usługi Intune do zarządzania aplikacją i urządzeniami.</span><span class="sxs-lookup"><span data-stu-id="c8849-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="c8849-112">Rozwiązanie mobile Zarządzanie urządzeniami (MDM) ma zastosowanie do:</span><span class="sxs-lookup"><span data-stu-id="c8849-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="c8849-113">Wdrożone rozwiązanie MDM i Portal firmy</span><span class="sxs-lookup"><span data-stu-id="c8849-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="c8849-114">Aplikacje biznesowe (nie publiczna)</span><span class="sxs-lookup"><span data-stu-id="c8849-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="c8849-115">Ręczna instalacja dostępnych aplikacji za pośrednictwem Portal firmy</span><span class="sxs-lookup"><span data-stu-id="c8849-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="c8849-116">Wypychanie przez administratora za pośrednictwem zasad zarządzania urządzeniami przenośnymi</span><span class="sxs-lookup"><span data-stu-id="c8849-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="c8849-117">Automatyczna aktualizacja za pośrednictwem rozwiązania MDM</span><span class="sxs-lookup"><span data-stu-id="c8849-117">Auto update through MDM</span></span>

## <a name="microsoft-store-for-business"></a><span data-ttu-id="c8849-118">Sklep Microsoft dla Firm</span><span class="sxs-lookup"><span data-stu-id="c8849-118">Microsoft Store for Business</span></span>

<span data-ttu-id="c8849-119">Ten [Microsoft Store dla Firm](app-deploy-store-business.md) dla osób decyzyjnych IT i administratorów w firmach w celu znalezienia, pozyskania i rozpowszechniania bezpłatnych i płatnych aplikacji oraz zarządzania nimi.</span><span class="sxs-lookup"><span data-stu-id="c8849-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="c8849-120">Administratorzy IT mogą zarządzać Microsoft Store i prywatnymi aplikacjami biznesowymi w jednym spisie oraz przypisywać i ponownie używać licencji zgodnie z potrzebami.</span><span class="sxs-lookup"><span data-stu-id="c8849-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="c8849-121">Aby uzyskać więcej informacji, odwiedź [stronę Prerequisites for using the Microsoft Store dla Firm](/microsoft-store/prerequisites-microsoft-store-for-business).</span><span class="sxs-lookup"><span data-stu-id="c8849-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="c8849-122">Ten Microsoft Store dla Firm ma zastosowanie do:</span><span class="sxs-lookup"><span data-stu-id="c8849-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="c8849-123">Aplikacje publiczne lub biznesowe</span><span class="sxs-lookup"><span data-stu-id="c8849-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="c8849-124">Automatyczna instalacja wymaganych aplikacji za pośrednictwem skojarzenia MDM</span><span class="sxs-lookup"><span data-stu-id="c8849-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="c8849-125">Użytkownik ręcznie pobiera aplikacje</span><span class="sxs-lookup"><span data-stu-id="c8849-125">User manually downloads apps</span></span>
* <span data-ttu-id="c8849-126">Automatyczna aktualizacja</span><span class="sxs-lookup"><span data-stu-id="c8849-126">Auto Update</span></span>

## <a name="microsoft-store-apps"></a><span data-ttu-id="c8849-127">Aplikacje ze Sklepu Microsoft</span><span class="sxs-lookup"><span data-stu-id="c8849-127">Microsoft Store apps</span></span>

<span data-ttu-id="c8849-128">Ten Microsoft Store to, że decydenci IT i administratorzy w firmach mogą znaleźć, pozyskiwać i rozpowszechniać aplikacje publiczne oraz zarządzać nimi.</span><span class="sxs-lookup"><span data-stu-id="c8849-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="c8849-129">Ten Microsoft Store ma zastosowanie do:</span><span class="sxs-lookup"><span data-stu-id="c8849-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="c8849-130">Tylko aplikacje publiczne</span><span class="sxs-lookup"><span data-stu-id="c8849-130">Public apps only</span></span>
* <span data-ttu-id="c8849-131">Użytkownik ręcznie pobiera aplikacje</span><span class="sxs-lookup"><span data-stu-id="c8849-131">User manually downloads apps</span></span>
* <span data-ttu-id="c8849-132">Automatyczna aktualizacja w przypadku połączenia z Internetem</span><span class="sxs-lookup"><span data-stu-id="c8849-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="c8849-133">Aby uzyskać więcej informacji, odwiedź stronę Holographic Store Apps ( [Aplikacje ze sklepu Holographic Store).](/hololens/holographic-store-apps)</span><span class="sxs-lookup"><span data-stu-id="c8849-133">For more information, visit [Holographic Store Apps](/hololens/holographic-store-apps).</span></span>

## <a name="install-via-provisioning-packages"></a><span data-ttu-id="c8849-134">Instalowanie za pośrednictwem pakietów aprowingu</span><span class="sxs-lookup"><span data-stu-id="c8849-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="c8849-135">[Pakiety aprowizowania](app-deploy-provisioning-package.md) umożliwiają instalowanie niestandardowych lub biznesowych aplikacji, dzięki czemu informatycy i administratorzy mogą szybko instalować aplikacje na urządzeniach lokalnych za pośrednictwem portu USB.</span><span class="sxs-lookup"><span data-stu-id="c8849-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="c8849-136">Tę instalację można wykonać bez połączenia internetowego i dla dowolnego typu tożsamości.</span><span class="sxs-lookup"><span data-stu-id="c8849-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="c8849-137">Instalowanie za pomocą pakietów aprowizowania ma zastosowanie w przypadku:</span><span class="sxs-lookup"><span data-stu-id="c8849-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="c8849-138">Aplikacje biznesowe/samodzielnie opracowane (nie publiczne)</span><span class="sxs-lookup"><span data-stu-id="c8849-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="c8849-139">Aplikacje publiczne (jeśli dostępny jest instalator offline)</span><span class="sxs-lookup"><span data-stu-id="c8849-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="c8849-140">Tylko ładowanie boczne USB</span><span class="sxs-lookup"><span data-stu-id="c8849-140">USB side-loading only</span></span>
* <span data-ttu-id="c8849-141">Brak automatycznej aktualizacji (wymaga ręcznej aktualizacji za pośrednictwem pakietu aprowizowania)</span><span class="sxs-lookup"><span data-stu-id="c8849-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="c8849-142">Instalowanie aplikacji na HoloLens 2 za pośrednictwem Instalator aplikacji</span><span class="sxs-lookup"><span data-stu-id="c8849-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="c8849-143">Użytkownicy usługi [Instalator aplikacji](app-deploy-app-installer.md) mogą mieć środowisko, które jest proste do instalowania aplikacji na urządzeniach lokalnych lub udostępniania aplikacji innej osobie, która nie jest zaznajomina z innymi metodami instalowania aplikacji na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="c8849-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="c8849-144">Można to zrobić bez konieczności włączania trybu dewelopera ani używania Portal urządzeń.</span><span class="sxs-lookup"><span data-stu-id="c8849-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="c8849-145">Jest to prosta metoda dystrybucji całkowicie sbudowaną aplikacji.</span><span class="sxs-lookup"><span data-stu-id="c8849-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="c8849-146">Bez względu na to, czy chcesz po prostu zmienić wersję aplikacji na wersję demonstracyjną dla innego użytkownika z HoloLens, czy chcesz wdrożyć aplikację, ta metoda działa łatwo.</span><span class="sxs-lookup"><span data-stu-id="c8849-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="c8849-147">Instalowanie za pośrednictwem Instalator aplikacji ma zastosowanie w przypadku:</span><span class="sxs-lookup"><span data-stu-id="c8849-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="c8849-148">Aplikacje biznesowe/samodzielnie opracowane (nie publiczne)</span><span class="sxs-lookup"><span data-stu-id="c8849-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="c8849-149">Tylko ładowanie boczne</span><span class="sxs-lookup"><span data-stu-id="c8849-149">Side-load only</span></span>
* <span data-ttu-id="c8849-150">Nie wymaga trybu dewelopera ani portalu urządzeń</span><span class="sxs-lookup"><span data-stu-id="c8849-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="c8849-151">Łatwość instalacji przez użytkownika końcowego</span><span class="sxs-lookup"><span data-stu-id="c8849-151">Easy for end user to install</span></span>
