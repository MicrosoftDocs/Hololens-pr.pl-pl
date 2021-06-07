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
ms.openlocfilehash: 951c79e49d67c1a0308e236e4283ffa498a7139f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378291"
---
# <a name="app-management-overview"></a><span data-ttu-id="05061-104">Zarządzanie aplikacją: Omówienie</span><span class="sxs-lookup"><span data-stu-id="05061-104">App Management: Overview</span></span>

<span data-ttu-id="05061-105">Aplikacje można wdrażać w czterech różnych ścieżkach: mobile **Zarządzanie urządzeniami (MDM),** **Microsoft Store dla Firm,** **Microsoft Store**, lub przez zainstalowanie ich za pomocą **aprowizowania**.</span><span class="sxs-lookup"><span data-stu-id="05061-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="05061-106">Mobile Zarządzanie urządzeniami (MDM)</span><span class="sxs-lookup"><span data-stu-id="05061-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="05061-107">Rozwiązanie MDM umożliwia twórcom i administratorom IT prywatną automatyczną instalację (wypychanie) własnych aplikacji biznesowych lub kupowanie aplikacji za pośrednictwem sklepu dla grupy użytkowników.</span><span class="sxs-lookup"><span data-stu-id="05061-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="05061-108">Urządzenia HoloLens działają najlepiej z usługą Microsoft Endpoint Manager (Intune) w celu [zarządzania aplikacją.](app-deploy-intune.md)</span><span class="sxs-lookup"><span data-stu-id="05061-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="05061-109">Usługa Intune oferuje również użytkownikom precyzyjne sterowanie aplikacjami zarządzanymi przez system IT za pośrednictwem Portal firmy do pobrania.</span><span class="sxs-lookup"><span data-stu-id="05061-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="05061-110">Poniższe instrukcje są dostępne dla użytkowników, którzy chcą zarządzać aplikacjami za pomocą usługi Intune.</span><span class="sxs-lookup"><span data-stu-id="05061-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="05061-111">Firma Microsoft zaleca używanie usługi Intune do zarządzania aplikacją i urządzeniami.</span><span class="sxs-lookup"><span data-stu-id="05061-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="05061-112">Rozwiązanie mobile Zarządzanie urządzeniami (MDM) ma zastosowanie do:</span><span class="sxs-lookup"><span data-stu-id="05061-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="05061-113">Wdrożone rozwiązanie MDM i Portal firmy</span><span class="sxs-lookup"><span data-stu-id="05061-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="05061-114">Aplikacje biznesowe (nie publiczna)</span><span class="sxs-lookup"><span data-stu-id="05061-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="05061-115">Ręczna instalacja dostępnych aplikacji za pośrednictwem Portal firmy</span><span class="sxs-lookup"><span data-stu-id="05061-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="05061-116">Wypychanie przez administratora za pośrednictwem zasad zarządzania urządzeniami przenośnymi</span><span class="sxs-lookup"><span data-stu-id="05061-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="05061-117">Automatyczna aktualizacja za pośrednictwem rozwiązania MDM</span><span class="sxs-lookup"><span data-stu-id="05061-117">Auto update through MDM</span></span>

## <a name="microsoft-store-for-business"></a><span data-ttu-id="05061-118">Sklep Microsoft dla Firm</span><span class="sxs-lookup"><span data-stu-id="05061-118">Microsoft Store for Business</span></span>

<span data-ttu-id="05061-119">Ten [Microsoft Store dla Firm](app-deploy-store-business.md) to, że decydenci IT i administratorzy w firmach mogą znaleźć, pozyskiwać i rozpowszechniać bezpłatne i płatne aplikacje oraz zarządzać nimi.</span><span class="sxs-lookup"><span data-stu-id="05061-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="05061-120">Administratorzy IT mogą zarządzać Microsoft Store i prywatnymi aplikacjami biznesowymi w jednym spisie oraz przypisywać i ponownie używać licencji zgodnie z potrzebami.</span><span class="sxs-lookup"><span data-stu-id="05061-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="05061-121">Aby uzyskać więcej informacji, odwiedź [stronę Prerequisites for using the Microsoft Store dla Firm](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span><span class="sxs-lookup"><span data-stu-id="05061-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="05061-122">Ten Microsoft Store dla Firm ma zastosowanie do:</span><span class="sxs-lookup"><span data-stu-id="05061-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="05061-123">Aplikacje publiczne lub biznesowe</span><span class="sxs-lookup"><span data-stu-id="05061-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="05061-124">Automatyczna instalacja wymaganych aplikacji za pośrednictwem skojarzenia MDM</span><span class="sxs-lookup"><span data-stu-id="05061-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="05061-125">Użytkownik ręcznie pobiera aplikacje</span><span class="sxs-lookup"><span data-stu-id="05061-125">User manually downloads apps</span></span>
* <span data-ttu-id="05061-126">Automatyczna aktualizacja</span><span class="sxs-lookup"><span data-stu-id="05061-126">Auto Update</span></span>

## <a name="microsoft-store-apps"></a><span data-ttu-id="05061-127">Aplikacje ze Sklepu Microsoft</span><span class="sxs-lookup"><span data-stu-id="05061-127">Microsoft Store apps</span></span>

<span data-ttu-id="05061-128">Ten Microsoft Store dla osób decyzyjnych IT i administratorów w firmach w celu znalezienia, pozyskiwania i rozpowszechniania aplikacji publicznych oraz zarządzania nimi.</span><span class="sxs-lookup"><span data-stu-id="05061-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="05061-129">Ten Microsoft Store ma zastosowanie do:</span><span class="sxs-lookup"><span data-stu-id="05061-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="05061-130">Tylko aplikacje publiczne</span><span class="sxs-lookup"><span data-stu-id="05061-130">Public apps only</span></span>
* <span data-ttu-id="05061-131">Użytkownik ręcznie pobiera aplikacje</span><span class="sxs-lookup"><span data-stu-id="05061-131">User manually downloads apps</span></span>
* <span data-ttu-id="05061-132">Automatyczna aktualizacja w przypadku połączenia z Internetem</span><span class="sxs-lookup"><span data-stu-id="05061-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="05061-133">Aby uzyskać więcej informacji, odwiedź stronę Holographic Store Apps ( [Aplikacje ze sklepu Holographic Store).](https://docs.microsoft.com/hololens/holographic-store-apps)</span><span class="sxs-lookup"><span data-stu-id="05061-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <a name="install-via-provisioning-packages"></a><span data-ttu-id="05061-134">Instalowanie za pośrednictwem pakietów aprowingu</span><span class="sxs-lookup"><span data-stu-id="05061-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="05061-135">[Pakiety aprowizowania](app-deploy-provisioning-package.md) umożliwiają instalowanie niestandardowych lub biznesowych aplikacji, dzięki czemu informatycy i administratorzy mogą szybko instalować aplikacje na urządzeniach lokalnych za pośrednictwem portu USB.</span><span class="sxs-lookup"><span data-stu-id="05061-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="05061-136">Tę instalację można wykonać bez połączenia internetowego i dla dowolnego typu tożsamości.</span><span class="sxs-lookup"><span data-stu-id="05061-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="05061-137">Instalowanie za pomocą pakietów aprowizowania ma zastosowanie w przypadku:</span><span class="sxs-lookup"><span data-stu-id="05061-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="05061-138">Aplikacje biznesowe/samodzielnie opracowane (nie publiczne)</span><span class="sxs-lookup"><span data-stu-id="05061-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="05061-139">Aplikacje publiczne (jeśli dostępny jest instalator offline)</span><span class="sxs-lookup"><span data-stu-id="05061-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="05061-140">Tylko ładowanie boczne USB</span><span class="sxs-lookup"><span data-stu-id="05061-140">USB side-loading only</span></span>
* <span data-ttu-id="05061-141">Brak automatycznej aktualizacji (wymaga ręcznej aktualizacji za pośrednictwem pakietu aprowizowania)</span><span class="sxs-lookup"><span data-stu-id="05061-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="05061-142">Instalowanie aplikacji na urządzeniach HoloLens 2 za pośrednictwem Instalator aplikacji</span><span class="sxs-lookup"><span data-stu-id="05061-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="05061-143">Przy [](app-deploy-app-installer.md) użyciu interfejsu Instalator aplikacji użytkownicy mogą mieć środowisko proste do instalowania aplikacji na urządzeniach lokalnych lub udostępniania aplikacji innej osobie, która nie jest zaznajomina z innymi metodami instalowania aplikacji na urządzeniu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="05061-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="05061-144">Można to zrobić bez konieczności włączania trybu dewelopera ani używania Portal urządzeń.</span><span class="sxs-lookup"><span data-stu-id="05061-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="05061-145">Jest to prosta metoda dystrybucji całkowicie sbudowaną aplikacji.</span><span class="sxs-lookup"><span data-stu-id="05061-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="05061-146">Bez względu na to, czy chcesz po prostu pokazać aplikację in inemiucie za pomocą urządzenia HoloLens, czy chcesz wdrożyć aplikację, ta metoda działa łatwo.</span><span class="sxs-lookup"><span data-stu-id="05061-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="05061-147">Instalowanie za pośrednictwem Instalator aplikacji ma zastosowanie w przypadku:</span><span class="sxs-lookup"><span data-stu-id="05061-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="05061-148">Aplikacje biznesowe/samodzielnie opracowane (nie publiczne)</span><span class="sxs-lookup"><span data-stu-id="05061-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="05061-149">Tylko ładowanie boczne</span><span class="sxs-lookup"><span data-stu-id="05061-149">Side-load only</span></span>
* <span data-ttu-id="05061-150">Nie wymaga trybu dewelopera ani portalu urządzeń</span><span class="sxs-lookup"><span data-stu-id="05061-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="05061-151">Łatwość instalacji przez użytkownika końcowego</span><span class="sxs-lookup"><span data-stu-id="05061-151">Easy for end user to install</span></span>
