---
title: Konfigurowanie CSP i Zarządzanie urządzeniami omówienie
description: Dowiedz się, jak skonfigurować CSP, zasady i zarządzanie urządzeniami przy użyciu pakietów Zarządzanie urządzeniami mobilnych i aprowizowania.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b312f9d20c9a75c5e4c1906c4ec55f42fda977f6
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640461"
---
# <a name="configure-csps-and-device-management-overview"></a><span data-ttu-id="04c5d-103">Konfigurowanie CSP i Zarządzanie urządzeniami omówienie</span><span class="sxs-lookup"><span data-stu-id="04c5d-103">Configure CSPs and Device Management overview</span></span>

<span data-ttu-id="04c5d-104">Administratorzy IT mogą definiować i implementować ustawienia zasad na HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="04c5d-104">IT Administrators can define and implement policy settings on HoloLens 2.</span></span> <span data-ttu-id="04c5d-105">Ustawienia konfiguracji, których użyjemy, różnią się w zależności od scenariusza wdrażania, a urządzenia firmowe będą oferować it najszerszy zakres kontroli.</span><span class="sxs-lookup"><span data-stu-id="04c5d-105">What configuration settings you use will differ based on the deployment scenario, and corporate devices will offer IT the broadest range of control.</span></span> <span data-ttu-id="04c5d-106">W Windows 10 dostawcy usług konfiguracji (CSP) to interfejs do odczytywania, konfigurowania, modyfikowania lub usuwania ustawień konfiguracji na urządzeniu.</span><span class="sxs-lookup"><span data-stu-id="04c5d-106">In Windows 10, Configuration Service Providers (CSP)s are an interface to read, set, modify, or delete configuration settings on the device.</span></span> <span data-ttu-id="04c5d-107">Te ustawienia są mapowe na klucze lub pliki rejestru.</span><span class="sxs-lookup"><span data-stu-id="04c5d-107">These settings map to registry keys or files.</span></span> <span data-ttu-id="04c5d-108">Niektórzy dostawcy usług konfiguracji obsługują format WAP, niektórzy obsługują syncML, a niektórzy obsługują oba te formaty.</span><span class="sxs-lookup"><span data-stu-id="04c5d-108">Some configuration service providers support the WAP format, some support SyncML, and some support both.</span></span>

<span data-ttu-id="04c5d-109">Aby uzyskać więcej informacji o Windows 10 Holographic zarządzania urządzeniami sieciowymi, zobacz pełną listę CSP obsługiwanych na [HoloLens urządzeniach.](/windows/client-management/mdm/configuration-service-provider-reference#hololens)</span><span class="sxs-lookup"><span data-stu-id="04c5d-109">For more information about Windows 10 Holographic device management CSPs, see the full list of [CSPs supported in HoloLens devices](/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span></span>
<span data-ttu-id="04c5d-110">Administratorzy IT mogą również zarządzać programem Policy CSP na urządzeniach. Zobacz pełną listę adresów CSP zasad obsługiwanych przez program [HoloLens 2.](/windows/client-management/mdm/policy-csps-supported-by-hololens2)</span><span class="sxs-lookup"><span data-stu-id="04c5d-110">IT Administrators can also manage Policy CSP on devices, see the full list of [Policy CSPs supported by HoloLens 2](/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span></span>

## <a name="configuration-methods"></a><span data-ttu-id="04c5d-111">Metody konfiguracji</span><span class="sxs-lookup"><span data-stu-id="04c5d-111">Configuration methods</span></span>

### <a name="configure-with-mdm"></a><span data-ttu-id="04c5d-112">Konfigurowanie przy użyciu rozwiązania MDM</span><span class="sxs-lookup"><span data-stu-id="04c5d-112">Configure with MDM</span></span>

<span data-ttu-id="04c5d-113">Usługami CSP i zasadami można łatwo zarządzać na dowolnym urządzeniu osobistym lub firmowym zarejestrowanym w systemie MDM.</span><span class="sxs-lookup"><span data-stu-id="04c5d-113">CSPs and Policies can be easily managed on any personal or corporate device enrolled in an MDM system.</span></span> <span data-ttu-id="04c5d-114">Po zarejestrowaniu urządzenia w rozwiązaniu MDM będzie można zarządzać tym urządzeniem lub zestawem urządzeń przy użyciu konfiguracji urządzeń.</span><span class="sxs-lookup"><span data-stu-id="04c5d-114">Once a device is enrolled in your MDM solution, you will be able to manage that device, or set of devices using device configurations.</span></span> <span data-ttu-id="04c5d-115">Dowiedz się więcej na temat zarządzania [urządzeniami przenośnymi HoloLens zarządzania urządzeniami przenośnymi.](hololens-mdm-configure.md)</span><span class="sxs-lookup"><span data-stu-id="04c5d-115">Learn more about how to [manage your HoloLens devices through MDM](hololens-mdm-configure.md).</span></span>

### <a name="configure-with-provisioning-packages"></a><span data-ttu-id="04c5d-116">Konfigurowanie za pomocą pakietów aprowizowania</span><span class="sxs-lookup"><span data-stu-id="04c5d-116">Configure with Provisioning Packages</span></span>

<span data-ttu-id="04c5d-117">HoloLens 2 obsługuje również ustawianie ograniczonego zestawu konfiguracji CSP dla urządzeń z systemem HoloLens 2 za pomocą niestandardowych pakietów aprowingu.</span><span class="sxs-lookup"><span data-stu-id="04c5d-117">HoloLens 2 also supports setting a limited set of CSP configurations for HoloLens 2 devices through custom Provisioning Packages.</span></span> <span data-ttu-id="04c5d-118">Pakiety aprowizowania są zwykle używane w przypadku urządzeń innych niż zarządzane przez rozwiązanie MDM i wymagają ręcznego zastosowania do każdego urządzenia.</span><span class="sxs-lookup"><span data-stu-id="04c5d-118">Provisioning Packages are typically leveraged for non-MDM managed devices and require to be manually applied to each device.</span></span> <span data-ttu-id="04c5d-119">Przeczytaj informacje na temat tworzenia niestandardowych [pakietów aprowizowania dla HoloLens](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="04c5d-119">Read information on building custom [Provisioning Packages for HoloLens](hololens-provisioning.md).</span></span>

## <a name="configurations"></a><span data-ttu-id="04c5d-120">Konfiguracje</span><span class="sxs-lookup"><span data-stu-id="04c5d-120">Configurations</span></span>

### <a name="common-device-restrictions"></a><span data-ttu-id="04c5d-121">Typowe ograniczenia dotyczące urządzeń</span><span class="sxs-lookup"><span data-stu-id="04c5d-121">Common device restrictions</span></span>

<span data-ttu-id="04c5d-122">Niektóre ograniczenia dotyczące urządzeń są tak proste, jak wyłączenie funkcjonalności lub połączenia z urządzeniem.</span><span class="sxs-lookup"><span data-stu-id="04c5d-122">Some device restrictions are as simple and disabling a functionality or connection to the device.</span></span> <span data-ttu-id="04c5d-123">Aby dowiedzieć się więcej o tych ograniczeniach, przeczytaj [więcej na temat typowych ograniczeń dotyczących urządzeń.](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="04c5d-123">To learn about these read more about [common device restrictions.](hololens-common-device-restrictions.md)</span></span>

### <a name="kiosk-modes"></a><span data-ttu-id="04c5d-124">Tryby kiosku</span><span class="sxs-lookup"><span data-stu-id="04c5d-124">Kiosk modes</span></span>

<span data-ttu-id="04c5d-125">Użyj trybu kiosku, aby kontrolować, które tożsamości mają domyślnie dostęp do których aplikacji.</span><span class="sxs-lookup"><span data-stu-id="04c5d-125">Use Kiosk mode to control which identities have access to which apps by default.</span></span> <span data-ttu-id="04c5d-126">Kiosków można używać dla jednej aplikacji lub wielu interfejsów użytkownika aplikacji.</span><span class="sxs-lookup"><span data-stu-id="04c5d-126">Kiosks can be used for a single app or multiple app UI experience.</span></span> <span data-ttu-id="04c5d-127">Konfiguracje kiosku mogą się różnić od pojedynczej aplikacji dla każdego, kto korzysta z urządzenia, po różne aplikacje dla różnych grup.</span><span class="sxs-lookup"><span data-stu-id="04c5d-127">Kiosk configurations range from a single app for anyone using the device, to different selections of apps for different groups.</span></span> <span data-ttu-id="04c5d-128">Tryb kiosku nie zatrzymuje uruchamiania innych aplikacji przez "dozwolone aplikacje" i nie był nigdy przeznaczony.</span><span class="sxs-lookup"><span data-stu-id="04c5d-128">Kiosk mode does not stop “allowed apps” from launching other apps and was not intended to ever.</span></span> <span data-ttu-id="04c5d-129">Aby dowiedzieć się więcej, zapoznaj się [z tematem Tryby kiosku i sposoby ich używania.](hololens-kiosk.md)</span><span class="sxs-lookup"><span data-stu-id="04c5d-129">Learn more by [reading about Kiosk modes and how to use them](hololens-kiosk.md).</span></span>

### <a name="settings-page-visibility"></a><span data-ttu-id="04c5d-130">Ustawienia Widoczność strony</span><span class="sxs-lookup"><span data-stu-id="04c5d-130">Settings Page Visibility</span></span>

<span data-ttu-id="04c5d-131">Użyj Ustawienia aplikacji, aby kontrolować, które tożsamości domyślnie mają dostęp do ustawień.</span><span class="sxs-lookup"><span data-stu-id="04c5d-131">Use Settings app policy to control which identities have access to settings by default.</span></span> <span data-ttu-id="04c5d-132">Za pomocą tych zasad Ustawienia aplikację można skonfigurować tak, aby pokazywała tylko wybrane strony lub ukrywała wszystkie wybrane strony.</span><span class="sxs-lookup"><span data-stu-id="04c5d-132">Using this policy the Settings app can be configured to either show only the select pages, or hide all selected pages.</span></span> <span data-ttu-id="04c5d-133">[Przeczytaj o tym, jak skonfigurować dostępne strony.](settings-uri-list.md)</span><span class="sxs-lookup"><span data-stu-id="04c5d-133">[Read about how to configure the pages available](settings-uri-list.md).</span></span>

<span data-ttu-id="04c5d-134">Ta funkcja jest obecnie dostępna tylko w [kompilacjach niejawnych Windows niejawnych testerów.](hololens-insider.md)</span><span class="sxs-lookup"><span data-stu-id="04c5d-134">This feature is currently only available in [Windows Insider builds](hololens-insider.md).</span></span> <span data-ttu-id="04c5d-135">Upewnij się, że urządzenia, dla których zamierzasz używać tej funkcji, są w kompilacji 19041.1349+.</span><span class="sxs-lookup"><span data-stu-id="04c5d-135">Ensure devices you intend to use this feature for are on build 19041.1349+.</span></span>

### <a name="wdac"></a><span data-ttu-id="04c5d-136">WDAC</span><span class="sxs-lookup"><span data-stu-id="04c5d-136">WDAC</span></span>

<span data-ttu-id="04c5d-137">Konfiguracja funkcji WDAC umożliwia kontrolowanie, które aplikacje/procesy mają być dozwolone lub niedozwolone niezależnie od tego, czy system jest w trybie kiosku, czy nie.</span><span class="sxs-lookup"><span data-stu-id="04c5d-137">Use WDAC configuration to control which apps / processes are allowed / disallowed to be launched irrespective of whether system is in kiosk mode or not.</span></span>
[<span data-ttu-id="04c5d-138">Zobacz nasze omówienie usług WDAC.</span><span class="sxs-lookup"><span data-stu-id="04c5d-138">See our overview for WDAC.</span></span>](windows-defender-application-control-wdac.md)
