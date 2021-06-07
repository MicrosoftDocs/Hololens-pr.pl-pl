---
title: Pakiet aprowizowania
description: Dowiedz się więcej na temat pakowania, aprowizowania, wdrażania i wdrażania aplikacji przedsiębiorstwa dla urządzeń HoloLens.
keywords: app, app deployment, enterprise app deployment, provisioning
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378323"
---
# <a name="provisioning-package"></a><span data-ttu-id="2827f-104">Pakiet aprowizowania</span><span class="sxs-lookup"><span data-stu-id="2827f-104">Provisioning Package</span></span>

<span data-ttu-id="2827f-105">Pakiety aprowizowania mogą służyć do przygotowywania i konfigurowania urządzeń w środowisku bez dostępu do zarządzania punktami końcowymi.</span><span class="sxs-lookup"><span data-stu-id="2827f-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="2827f-106">Można je również wdrożyć na urządzeniu niezależnie od tożsamości użytkownika, stanu rejestracji, podczas procesu OOBE (Out of Box Experience) lub przez zastosowanie pakietu aprowizowania podczas [instalacji.](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)</span><span class="sxs-lookup"><span data-stu-id="2827f-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <a name="provisioning-packages-considerations"></a><span data-ttu-id="2827f-107">Zagadnienia dotyczące pakietów aprowiwizowania:</span><span class="sxs-lookup"><span data-stu-id="2827f-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="2827f-108">Aplikacje niepublicznie dostępne</span><span class="sxs-lookup"><span data-stu-id="2827f-108">Non-Public apps</span></span>
* <span data-ttu-id="2827f-109">Tylko ładowanie boczne USB</span><span class="sxs-lookup"><span data-stu-id="2827f-109">USB side-load only</span></span>
* <span data-ttu-id="2827f-110">Brak automatycznej aktualizacji (wymaga aktualizacji ręcznych za pośrednictwem PPKG)</span><span class="sxs-lookup"><span data-stu-id="2827f-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="2827f-111">Aplikacje zainstalowane za pośrednictwem pakietu aprowizowania muszą być podpisane przy użyciu certyfikatu w magazynie komputera lokalnego.</span><span class="sxs-lookup"><span data-stu-id="2827f-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="2827f-112">Pakiety aprowizowania mogą instalować certyfikaty tylko w magazynie urządzenia (komputera lokalnego), w związku z tym aplikacja i certyfikat mogą być instalowane za pośrednictwem tego samego pakietu aprowizowania.</span><span class="sxs-lookup"><span data-stu-id="2827f-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="2827f-113">Jeśli wdrażasz certyfikat z rozwiązania MDM lub instalujesz go za pośrednictwem Menedżera [certyfikatów,](certificate-manager.md)pamiętaj o wdrożeniu certyfikatu w magazynie komputera lokalnego w celu podpisywania zainstalowanych w ten sposób aplikacji.</span><span class="sxs-lookup"><span data-stu-id="2827f-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="2827f-114">Aby poznać podstawy tworzenia pakietu aprowizowania dla urządzeń HoloLens, odwiedź stronę [aprowizowania urządzenia HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning)</span><span class="sxs-lookup"><span data-stu-id="2827f-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="2827f-115">Aby wdrożyć aplikację, musisz rozpocząć od zaawansowanej aprowiwizowania.</span><span class="sxs-lookup"><span data-stu-id="2827f-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="2827f-116">Urządzenie HoloLens (1. generacja) ma ograniczoną obsługę instalowania aplikacji **(UniversalAppInstall**) przy użyciu pakietu aprowizowania.</span><span class="sxs-lookup"><span data-stu-id="2827f-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="2827f-117">Urządzenia HoloLens (1. generacji) obsługują instalowanie aplikacji za pośrednictwem ppkg tylko podczas instalacji OOBE i tylko w przypadku instalacji w kontekście użytkownika.</span><span class="sxs-lookup"><span data-stu-id="2827f-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <a name="setup"></a><span data-ttu-id="2827f-118">Konfigurowanie</span><span class="sxs-lookup"><span data-stu-id="2827f-118">Setup</span></span>

<span data-ttu-id="2827f-119">W [programie Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) należy wykonać następujące cztery kroki.</span><span class="sxs-lookup"><span data-stu-id="2827f-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="2827f-120">Ustaw pozycję ApplicationManagement/AllowAllTrustedApps na wartość "Yes".</span><span class="sxs-lookup"><span data-stu-id="2827f-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="2827f-121">Zobacz: [ApplicationManagement/AllowAllTrustedApps.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)</span><span class="sxs-lookup"><span data-stu-id="2827f-121">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="2827f-122">Przejdź do **pola UniversalAppInstall**  >  **UserContextAppLicense i wprowadź** wartość **PackageFamilyName.**</span><span class="sxs-lookup"><span data-stu-id="2827f-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="2827f-123">Zobacz [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span><span class="sxs-lookup"><span data-stu-id="2827f-123">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="2827f-124">Zobacz też: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="2827f-124">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="2827f-125">Możesz użyć Portal urządzeń na urządzeniu, na które już zainstalowano aplikację.</span><span class="sxs-lookup"><span data-stu-id="2827f-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="2827f-126">Odwiedź stronę Aplikacje i spójrz na wiersz PackageRelativeID, wszystkie informacje przed "!" To twoja **nazwa_pakietu_pakietu.**</span><span class="sxs-lookup"><span data-stu-id="2827f-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="2827f-127">Zobaczysz, że masz nową sekcję **ApplicationFile**.</span><span class="sxs-lookup"><span data-stu-id="2827f-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="2827f-128">Użyj tego obszaru, aby przekazać pakiet appx.</span><span class="sxs-lookup"><span data-stu-id="2827f-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="2827f-129">W zależności od tego, czy zakupiono aplikację lub sbudowaliśmy własną aplikację LOB, konieczne będzie przekazanie pliku licencji lub certyfikatu zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="2827f-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="2827f-130">W przypadku pliku licencji: przejdź do **pozycji UniversalAppInstall**  >  **UserContextAppLicence** i przejdź do lokalizacji licencji i przekaż ją.</span><span class="sxs-lookup"><span data-stu-id="2827f-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="2827f-131">W przypadku pliku zabezpieczeń przejdź do **opcji Certyfikaty** i wybierz certyfikat do zainstalowania wraz z pakietem appx.</span><span class="sxs-lookup"><span data-stu-id="2827f-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="2827f-132">Pamiętaj, aby zapisać projekt w bezpiecznej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="2827f-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="2827f-133">Następnie **wyeksportuj** go jako **pakiet aprowizowania.**</span><span class="sxs-lookup"><span data-stu-id="2827f-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="2827f-134">Zobacz też: [Stosowanie pakietu aprowizowania na urządzeniach HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)</span><span class="sxs-lookup"><span data-stu-id="2827f-134">See also: [Apply your provisioning package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
