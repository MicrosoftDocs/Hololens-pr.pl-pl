---
title: Zarządzanie aplikacjami niestandardowymi dla HoloLens 2
description: Dowiedz się, jak instalować, odinstalowywać i ładować po stronie niestandardowe aplikacje holograficzne na urządzeniach z systemem HoloLens 2 przy użyciu Portal urządzeń i Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 01/21/2021
manager: yannisle
keywords: hololens, hololens 2, sideload, side load, side-load, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: joyjaz
ms.author: v-jjaswinski
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens 2
ms.openlocfilehash: d2280a794455090c61a7bf30bc5dc5b8faf5adbe
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636405"
---
# <a name="manage-custom-apps-for-hololens-2"></a><span data-ttu-id="0c7e3-104">Zarządzanie aplikacjami niestandardowymi dla HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="0c7e3-104">Manage custom apps for HoloLens 2</span></span>

<span data-ttu-id="0c7e3-105">HoloLens obsługuje wiele istniejących aplikacji z Microsoft Store, a także nowe aplikacje opracowane specjalnie dla HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0c7e3-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> 

<span data-ttu-id="0c7e3-106">Aby uzyskać więcej informacji na temat aplikacji ze sklepu, zobacz [Zarządzanie aplikacjami w sklepie](holographic-store-apps.md).</span><span class="sxs-lookup"><span data-stu-id="0c7e3-106">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c7e3-107">W przypadku wdrożeń dla przedsiębiorstw nie zalecamy włączania trybu dewelopera, którego używają obie te metody.</span><span class="sxs-lookup"><span data-stu-id="0c7e3-107">For enterprise deployments, we don't recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="0c7e3-108">Jeśli interesuje Cię metoda bezpiecznego wdrażania aplikacji, zapoznaj się z naszym tematem [Zarządzanie aplikacją: Omówienie.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="0c7e3-108">If you're interested in a secure app deployment method, please review our [App Management: Overview](app-deploy-overview.md).</span></span>

<span data-ttu-id="0c7e3-109">Jeśli szukasz metody instalacji aplikacji dla deweloperów dla urządzeń z HoloLens 2, zapoznaj się z tematem:</span><span class="sxs-lookup"><span data-stu-id="0c7e3-109">If you're looking for either developer method of app installation for HoloLens 2 devices, refer to:</span></span>

- [<span data-ttu-id="0c7e3-110">Portal urządzeń: Instalowanie aplikacji</span><span class="sxs-lookup"><span data-stu-id="0c7e3-110">Device Portal: Installing an App</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
- [<span data-ttu-id="0c7e3-111">Wdrażanie i Visual Studio debugowanie aplikacji przy użyciu usługi Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0c7e3-111">Using Visual Studio to deploy and debug Apps</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

<span data-ttu-id="0c7e3-112">Zapoznaj się [z naszym przewodnikiem,](holographic-custom-apps.md) jeśli chcesz wdrażać aplikacje niestandardowe HoloLens (1. generacji).</span><span class="sxs-lookup"><span data-stu-id="0c7e3-112">See our [guide](holographic-custom-apps.md) if you'd like to deploy custom apps on HoloLens (1st gen).</span></span>
