---
title: Zarządzanie aplikacjami niestandardowymi dla HoloLens (1. generacja)
description: Dowiedz się, jak instalować, odinstalowywać i ładować po stronie niestandardowe aplikacje holograficzne HoloLens urządzeniach przy użyciu Portal urządzeń i Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, sideload, side load, side-load, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: a179032978e1fc062273a6754e3b0a1ad50a5211
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635912"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a><span data-ttu-id="5de9c-104">Zarządzanie aplikacjami niestandardowymi dla HoloLens (1. generacja)</span><span class="sxs-lookup"><span data-stu-id="5de9c-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="5de9c-105">HoloLens obsługuje wiele istniejących aplikacji z Microsoft Store, a także nowe aplikacje opracowane specjalnie dla HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5de9c-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="5de9c-106">Ten artykuł koncentruje się na niestandardowych aplikacjach holograficznych.</span><span class="sxs-lookup"><span data-stu-id="5de9c-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="5de9c-107">Aby uzyskać więcej informacji na temat aplikacji ze sklepu, zobacz [Zarządzanie aplikacjami w sklepie](holographic-store-apps.md).</span><span class="sxs-lookup"><span data-stu-id="5de9c-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5de9c-108">Następujące informacje zostały utworzone dla HoloLens (1. generacji), nazywanej również HoloLens Developer Edition w tym czasie.</span><span class="sxs-lookup"><span data-stu-id="5de9c-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="5de9c-109">W związku z tym ładowanie bezpośrednio aplikacji za pośrednictwem portalu urządzeń i instalowanie aplikacji za pośrednictwem Visual Studio wtedy były powszechnie spotykane.</span><span class="sxs-lookup"><span data-stu-id="5de9c-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="5de9c-110">W przypadku wdrożeń dla przedsiębiorstw nie zalecamy włączania trybu dewelopera, którego używają obie te metody.</span><span class="sxs-lookup"><span data-stu-id="5de9c-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="5de9c-111">Jeśli interesuje Cię metoda bezpiecznego wdrażania aplikacji, zapoznaj się z naszym [tematem Zarządzanie aplikacją: Omówienie.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="5de9c-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="5de9c-112">Jeśli szukasz metody instalacji aplikacji dla deweloperów dla urządzeń z systemem HoloLens 2, zapoznaj się z tematem:</span><span class="sxs-lookup"><span data-stu-id="5de9c-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
>
> - [<span data-ttu-id="5de9c-113">Portal urządzeń: Instalowanie aplikacji</span><span class="sxs-lookup"><span data-stu-id="5de9c-113">Device Portal: Installing an App</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="5de9c-114">Wdrażanie i Visual Studio debugowanie aplikacji przy użyciu usługi Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5de9c-114">Using Visual Studio to deploy and debug Apps</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a><span data-ttu-id="5de9c-115">Instalowanie aplikacji niestandardowych</span><span class="sxs-lookup"><span data-stu-id="5de9c-115">Install custom apps</span></span>

<span data-ttu-id="5de9c-116">Możesz instalować własne aplikacje na HoloLens za pomocą Portal urządzeń lub wdrażając aplikacje z Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5de9c-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <a name="installing-an-application-package-with-the-device-portal"></a><span data-ttu-id="5de9c-117">Instalowanie pakietu aplikacji przy użyciu Portal urządzeń</span><span class="sxs-lookup"><span data-stu-id="5de9c-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="5de9c-118">Ustanów połączenie [z Portal urządzeń](/windows/mixed-reality/using-the-windows-device-portal) do docelowego HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5de9c-118">Establish a connection from [Device Portal](/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="5de9c-119">W lewym okienku nawigacji przejdź do **strony** Aplikacje.</span><span class="sxs-lookup"><span data-stu-id="5de9c-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="5de9c-120">W **obszarze Pakiet aplikacji** przejdź do pliku appx skojarzonego z aplikacją.</span><span class="sxs-lookup"><span data-stu-id="5de9c-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="5de9c-121">Pamiętaj, aby odwołać się do wszystkich skojarzonych plików zależności i certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="5de9c-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="5de9c-122">Wybierz **pozycję Przejdź.**</span><span class="sxs-lookup"><span data-stu-id="5de9c-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5de9c-123">![Instalowanie formularza aplikacji w Windows Portal urządzeń na Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span><span class="sxs-lookup"><span data-stu-id="5de9c-123">![Install app form in Windows Device Portal on Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span></span>

### <a name="deploying-from-microsoft-visual-studio-2015"></a><span data-ttu-id="5de9c-124">Wdrażanie od Microsoft Visual Studio 2015 r.</span><span class="sxs-lookup"><span data-stu-id="5de9c-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="5de9c-125">Otwórz rozwiązanie aplikacji Visual Studio (plik sln).</span><span class="sxs-lookup"><span data-stu-id="5de9c-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="5de9c-126">Otwórz okno **Właściwości projektu**.</span><span class="sxs-lookup"><span data-stu-id="5de9c-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="5de9c-127">Wybierz następującą konfigurację kompilacji: **Master/x86/Remote Machine**.</span><span class="sxs-lookup"><span data-stu-id="5de9c-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="5de9c-128">Po wybraniu opcji **Maszyna zdalna:**</span><span class="sxs-lookup"><span data-stu-id="5de9c-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="5de9c-129">Upewnij się, że adres wskazuje Wi-Fi adres IP HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5de9c-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="5de9c-130">Ustaw uwierzytelnianie na **wartość Universal (Unencrypted Protocol).**</span><span class="sxs-lookup"><span data-stu-id="5de9c-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="5de9c-131">Skompilowanie rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="5de9c-131">Build your solution.</span></span>

1. <span data-ttu-id="5de9c-132">Aby wdrożyć aplikację z komputera dewelopera na komputerze HoloLens, wybierz **pozycję Komputer zdalny.**</span><span class="sxs-lookup"><span data-stu-id="5de9c-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="5de9c-133">Jeśli masz już istniejącą kompilację na HoloLens, wybierz pozycję **Tak,** aby zainstalować nowszą wersję.</span><span class="sxs-lookup"><span data-stu-id="5de9c-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Wdrażanie na maszynie zdalnej dla aplikacji do Microsoft HoloLens w Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="5de9c-135">Aplikacja zostanie automatycznie instalowana i uruchamiana na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="5de9c-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="5de9c-136">Po zainstalowaniu aplikacji znajdziesz ją na liście  Wszystkie aplikacje ( Uruchom  >  **Wszystkie aplikacje**).</span><span class="sxs-lookup"><span data-stu-id="5de9c-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
