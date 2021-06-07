---
title: Zarządzanie aplikacjami niestandardowymi dla urządzenia HoloLens 2
description: Dowiedz się, jak instalować, odinstalowywać i ładować niestandardowe aplikacje holograficzne na urządzeniach HoloLens 2 przy użyciu Portal urządzeń i Visual Studio.
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
ms.openlocfilehash: e3ae180697c889a426108992ba345dc23b96505c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378294"
---
# <a name="manage-custom-apps-for-hololens-2"></a><span data-ttu-id="24811-104">Zarządzanie aplikacjami niestandardowymi dla urządzenia HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="24811-104">Manage custom apps for HoloLens 2</span></span>

<span data-ttu-id="24811-105">Urządzenie HoloLens obsługuje wiele istniejących aplikacji z Microsoft Store, a także nowe aplikacje opracowane specjalnie dla urządzenia HoloLens.</span><span class="sxs-lookup"><span data-stu-id="24811-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> 

<span data-ttu-id="24811-106">Aby uzyskać więcej informacji na temat aplikacji ze sklepu, zobacz [Zarządzanie aplikacjami w sklepie](holographic-store-apps.md).</span><span class="sxs-lookup"><span data-stu-id="24811-106">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="24811-107">W przypadku wdrożeń dla przedsiębiorstw nie zalecamy włączania trybu dewelopera, którego używają obie te metody.</span><span class="sxs-lookup"><span data-stu-id="24811-107">For enterprise deployments, we don't recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="24811-108">Jeśli interesuje Cię metoda bezpiecznego wdrażania aplikacji, zapoznaj się z naszym tematem [Zarządzanie aplikacją: Omówienie.](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="24811-108">If you're interested in a secure app deployment method, please review our [App Management: Overview](app-deploy-overview.md).</span></span>

<span data-ttu-id="24811-109">Jeśli szukasz metody instalacji aplikacji dla urządzeń HoloLens 2 przez dewelopera, zapoznaj się z tematem:</span><span class="sxs-lookup"><span data-stu-id="24811-109">If you're looking for either developer method of app installation for HoloLens 2 devices, refer to:</span></span>
- [<span data-ttu-id="24811-110">Portal urządzeń: Instalowanie aplikacji</span><span class="sxs-lookup"><span data-stu-id="24811-110">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
- [<span data-ttu-id="24811-111">Wdrażanie i debugowanie Visual Studio przy użyciu programu</span><span class="sxs-lookup"><span data-stu-id="24811-111">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

<span data-ttu-id="24811-112">Zapoznaj się [z naszym przewodnikiem,](holographic-custom-apps.md) jeśli chcesz wdrożyć aplikacje niestandardowe na urządzeniach HoloLens (1. generacji).</span><span class="sxs-lookup"><span data-stu-id="24811-112">See our [guide](holographic-custom-apps.md) if you'd like to deploy custom apps on HoloLens (1st gen).</span></span>