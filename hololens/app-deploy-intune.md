---
title: Intune i Portal firmy
description: Dowiedz się, jak skonfigurować, przypisać i utworzyć wygodne środowisko użytkownika za pomocą usługi Intune, zarządzania urządzeniami przenośnymi i portalu firmy.
keywords: intune, zarządzanie aplikacją, aplikacja, portal firmy, portal, hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378394"
---
# <a name="intune--company-portal"></a><span data-ttu-id="4ddc7-104">Intune & Portal firmy</span><span class="sxs-lookup"><span data-stu-id="4ddc7-104">Intune & Company Portal</span></span>

<span data-ttu-id="4ddc7-105">Usługa Mobile Zarządzanie urządzeniami (MDM) umożliwia wdrażanie własnych aplikacji niestandardowych za pośrednictwem usługi [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) bezpośrednio na urządzeniach HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4ddc7-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="4ddc7-106">Microsoft Intune to usługa chmurowa, której głównym celem jest zarządzanie urządzeniami mobilnymi (MDM, mobile device management) i zarządzanie aplikacjami mobilnymi (MAM, mobile application management).</span><span class="sxs-lookup"><span data-stu-id="4ddc7-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="4ddc7-107">Usługa Intune jest zawarta w pakiecie [Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security) firmy Microsoft i pozwala użytkownikom na wydajną pracę przy zachowaniu ochrony danych organizacji.</span><span class="sxs-lookup"><span data-stu-id="4ddc7-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="4ddc7-108">Aby dowiedzieć się więcej o usłudze Intune, przeczytaj [Co to jest usługa Intune.](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)</span><span class="sxs-lookup"><span data-stu-id="4ddc7-108">To learn more about Intune, read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <a name="setup"></a><span data-ttu-id="4ddc7-109">Konfigurowanie</span><span class="sxs-lookup"><span data-stu-id="4ddc7-109">Setup</span></span>

1. <span data-ttu-id="4ddc7-110">Przekaż aplikację do aplikacji biznesowej lub przekaż aplikację niestandardową do dzierżawy usługi Intune.</span><span class="sxs-lookup"><span data-stu-id="4ddc7-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="4ddc7-111">Zobacz też: [Zarządzanie aplikacją dla przedsiębiorstw.](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)</span><span class="sxs-lookup"><span data-stu-id="4ddc7-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="4ddc7-112">[Przypisz aplikację do grupy](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span><span class="sxs-lookup"><span data-stu-id="4ddc7-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="4ddc7-113">W zależności od wybranego typu przypisania aplikacja może zostać dostarczona automatycznie lub może być łatwo ściągnięta, jeśli masz do wyboru aplikacje.</span><span class="sxs-lookup"><span data-stu-id="4ddc7-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="4ddc7-114">Podczas budowania pakietu appx pamiętaj o uwzględnieniu architektury dla urządzeń, na których jest wdrażane.</span><span class="sxs-lookup"><span data-stu-id="4ddc7-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="4ddc7-115">HoloLens 2 to urządzenie ARM64, a HoloLens (1. generacja) to x86.</span><span class="sxs-lookup"><span data-stu-id="4ddc7-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="4ddc7-116">Jeśli planujesz środowisko urządzeń mieszanych, możesz uwzględnić je w jednym pakiecie appx.</span><span class="sxs-lookup"><span data-stu-id="4ddc7-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <a name="assignment-types"></a><span data-ttu-id="4ddc7-117">Typy przypisań</span><span class="sxs-lookup"><span data-stu-id="4ddc7-117">Assignment types</span></span>

<span data-ttu-id="4ddc7-118">Aby aplikacja została automatycznie zainstalowana na urządzeniu po rejestracji, wybierz pozycję Wymagane **dla** tych grup.</span><span class="sxs-lookup"><span data-stu-id="4ddc7-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="4ddc7-119">Aby udostępnić aplikację do pobrania na urządzeniach zarejestrowanych za pośrednictwem portalu firmy, wybierz pozycję **Dostępne dla zarejestrowanych urządzeń.**</span><span class="sxs-lookup"><span data-stu-id="4ddc7-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <a name="end-user-experience"></a><span data-ttu-id="4ddc7-120">End-User użytkownika</span><span class="sxs-lookup"><span data-stu-id="4ddc7-120">End-User Experience</span></span>

<span data-ttu-id="4ddc7-121">Po skonfigurowaniu konfiguracji w usłudze Intune użytkownicy końcowi mogą odbierać wybrane aplikacje.</span><span class="sxs-lookup"><span data-stu-id="4ddc7-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="4ddc7-122">Wykonaj następujące kroki, aby automatycznie pobrać aplikacje:</span><span class="sxs-lookup"><span data-stu-id="4ddc7-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="4ddc7-123">Zarejestruj urządzenie w dzierżawie.</span><span class="sxs-lookup"><span data-stu-id="4ddc7-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="4ddc7-124">Po zakończeniu rejestracji urządzenia aplikacja powinna zostać na twoim urządzeniu.</span><span class="sxs-lookup"><span data-stu-id="4ddc7-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="4ddc7-125">Jeśli nie widzisz aplikacji natychmiast, przejdź do tematu Ustawienia Konta służbowe Informacje o koncie i przewiń w dół, aby wyświetlić informacje o  >    >    >   stanie zainstalowanej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="4ddc7-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="4ddc7-126">Jak uzyskać dostęp do aplikacji za pośrednictwem Portal firmy:</span><span class="sxs-lookup"><span data-stu-id="4ddc7-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="4ddc7-127">Otwórz **menu Start i** wybierz **pozycję Microsoft Store**.</span><span class="sxs-lookup"><span data-stu-id="4ddc7-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="4ddc7-128">Wyszukaj **Portal firmy** i pobierz aplikację.</span><span class="sxs-lookup"><span data-stu-id="4ddc7-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="4ddc7-129">Zaloguj się do swojego konta.</span><span class="sxs-lookup"><span data-stu-id="4ddc7-129">Sign into your account.</span></span>
4. <span data-ttu-id="4ddc7-130">Wybierz aplikację, którą chcesz otrzymać i pobrać.</span><span class="sxs-lookup"><span data-stu-id="4ddc7-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="4ddc7-131">Dowiedz się więcej na [temat automatycznego instalowania aplikacji Portal firmy](https://docs.microsoft.com/mem/intune/apps/company-portal-app) i [wdrażania aplikacji oraz zarządzania nimi w usłudze Intune.](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)</span><span class="sxs-lookup"><span data-stu-id="4ddc7-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
