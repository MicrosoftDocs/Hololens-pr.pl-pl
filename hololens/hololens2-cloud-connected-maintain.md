---
title: Przewodnik wdrażania — wdrażanie urządzenia HoloLens 2 połączonego z chmurą na dużą skalę przy użyciu funkcji Remote Assist — konserwacja
description: Bądź na bieżąco z naszymi poradami dotyczącymi konserwacji i obsługi urządzeń HoloLens za pośrednictwem sieci połączonej z chmurą.
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
ms.openlocfilehash: bc34c4e41c5a6cee8f3f9a0a97407ee38d419bbc
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378405"
---
# <a name="maintain---cloud-connected-guide"></a><span data-ttu-id="3b8be-104">Obsługa — przewodnik po chmurze</span><span class="sxs-lookup"><span data-stu-id="3b8be-104">Maintain - Cloud connected Guide</span></span>

## <a name="updates"></a><span data-ttu-id="3b8be-105">Aktualizacje</span><span class="sxs-lookup"><span data-stu-id="3b8be-105">Updates</span></span>

<span data-ttu-id="3b8be-106">Firma Microsoft zaprojektowała Windows Update dla Firm, aby zapewnić administratorom IT dodatkowe funkcje zarządzania zorientowane na funkcje Windows Update, takie jak możliwość wdrażania aktualizacji w grupach urządzeń i definiowania okien obsługi w celu instalowania aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="3b8be-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="3b8be-107">Dowiedz się, jak zarządzać aktualizacjami urządzenia [HoloLens,](https://docs.microsoft.com/hololens/hololens-updates) w tym zaplanowanymi dniami, zaplanowanym czasem i ustawianiem aktywnych godzin na urządzeniu, aby było ono aktualizowane poza godzinami pracy.</span><span class="sxs-lookup"><span data-stu-id="3b8be-107">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="3b8be-108">Usługa Remote Assist jest In-Box aplikacji i można ją aktualizować za pośrednictwem Microsoft Store aplikacji.</span><span class="sxs-lookup"><span data-stu-id="3b8be-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="3b8be-109">W przypadku wszystkich aplikacji pobranych za pośrednictwem Microsoft Store można je zaktualizować za pośrednictwem Microsoft Store [ręcznie.](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps)</span><span class="sxs-lookup"><span data-stu-id="3b8be-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="support-plan"></a><span data-ttu-id="3b8be-110">Plan pomocy technicznej</span><span class="sxs-lookup"><span data-stu-id="3b8be-110">Support Plan</span></span>

<span data-ttu-id="3b8be-111">Plan pomocy technicznej jest doskonałym rozwiązaniem.</span><span class="sxs-lookup"><span data-stu-id="3b8be-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="3b8be-112">Przydatne jest wytrenowanie kogoś lub grupy na temat rozwiązywania problemów z procesem rejestracji na urządzeniach HoloLens, a także ogólnego użycia urządzenia HoloLens w organizacji.</span><span class="sxs-lookup"><span data-stu-id="3b8be-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="3b8be-113">Aby umożliwić użytkownikom szybsze rozwiązanie ich problemów, sugerujemy, aby proces eskalacji był obsługiwany w podobny sposób jak w tej kolejności:</span><span class="sxs-lookup"><span data-stu-id="3b8be-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="3b8be-114">Pomoc techniczna.</span><span class="sxs-lookup"><span data-stu-id="3b8be-114">Your Support desk.</span></span>
2. <span data-ttu-id="3b8be-115">Zespół ekspertów ds. urządzenia HoloLens</span><span class="sxs-lookup"><span data-stu-id="3b8be-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="3b8be-116">[HoloLens Docs](https://docs.microsoft.com/hololens/)  /  [Dokumenty dotyczące rozwiązywania problemów z urządzeniem HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="3b8be-116">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="3b8be-117">Kontakt z pomocą techniczną</span><span class="sxs-lookup"><span data-stu-id="3b8be-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a><span data-ttu-id="3b8be-118">Plan rozwoju</span><span class="sxs-lookup"><span data-stu-id="3b8be-118">Development Plan</span></span>

<span data-ttu-id="3b8be-119">Po pomyślnym zarejestrowaniu urządzenia możesz teraz przygotować się do wdrożenia aplikacji biznesowych (aplikacji biznesowych) na urządzeniach.</span><span class="sxs-lookup"><span data-stu-id="3b8be-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="3b8be-120">Są to aplikacje niestandardowe, które są dostosowane do potrzeb&#39;organizacji.</span><span class="sxs-lookup"><span data-stu-id="3b8be-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="3b8be-121">Jeśli masz już aplikację biznesową, możesz&#39;ponownie wdrożyć aplikację za pomocą [rozwiązania MDM.](https://docs.microsoft.com/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="3b8be-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="3b8be-122">Jeśli w&#39;wolisz inną metodę, zapoznaj się z omówieniem wdrażania aplikacji dla urządzenia [HoloLens 2,](https://docs.microsoft.com/hololens/app-deploy-overview) aby dowiedzieć się więcej na temat metod wdrażania aplikacji LOB na urządzeniach.</span><span class="sxs-lookup"><span data-stu-id="3b8be-122">If you&#39;d prefer a different method then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="3b8be-123">Jeśli nie&#39;tworzenia własnej aplikacji LOB lub nadal trwa proces jej tworzenia, zapoznaj się z naszymi dokumentami programistyczną rzeczywistości mieszanej, aby rozpocząć projektowanie i [tworzenie prototypów,](https://docs.microsoft.com/windows/mixed-reality/design/design) lub poznasz podstawowe pojęcia, aby rozpocząć tworzenie rzeczywistości [mieszanej.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="3b8be-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="device-management"></a><span data-ttu-id="3b8be-124">Zarządzanie urządzeniami</span><span class="sxs-lookup"><span data-stu-id="3b8be-124">Device Management</span></span> 

<span data-ttu-id="3b8be-125">Chociaż ten przewodnik dotyczył konfigurowania usługi Mobile Zarządzanie urządzeniami (MDM), nie został on zastosowany do stosowania ograniczeń dotyczących urządzeń ani stosowania zasad do urządzeń.</span><span class="sxs-lookup"><span data-stu-id="3b8be-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="3b8be-126">Zarządzanie urządzeniami może służyć zarówno do zezwalania na dostęp przez wypychanie certyfikatów, jak i ograniczania dostępu z różnymi ograniczeniami dotyczącymi urządzeń.</span><span class="sxs-lookup"><span data-stu-id="3b8be-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="3b8be-127">W wielu przypadkach urządzenia mogą mieć ograniczenia łączności, takie jak Bluetooth, VPN, USB, a nawet wyłączenie dostępu do aparatu lub mikrofonu.</span><span class="sxs-lookup"><span data-stu-id="3b8be-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="3b8be-128">Jeśli którekolwiek z tych zainteresowań Cię interesuje, zachęcamy do przeczytania naszej strony [typowych ograniczeń dotyczących urządzeń](hololens-common-device-restrictions.md).</span><span class="sxs-lookup"><span data-stu-id="3b8be-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="3b8be-129">Istnieją inne, bardziej złożone ograniczenia dotyczące urządzeń, których można użyć.</span><span class="sxs-lookup"><span data-stu-id="3b8be-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="3b8be-130">Przykładowe metody:</span><span class="sxs-lookup"><span data-stu-id="3b8be-130">Such as:</span></span>

- <span data-ttu-id="3b8be-131">Ograniczanie stron, które można wyświetlać w aplikacji Ustawienia, za pomocą właściwości [SettingsPageVisibility](settings-uri-list.md), dzięki czemu użytkownicy mogą uzyskać dostęp tylko do ustawień, które muszą dostosować, takich jak Wi-Fi połączenia.</span><span class="sxs-lookup"><span data-stu-id="3b8be-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="3b8be-132">Użyj [trybu kiosku,](hololens-kiosk.md) aby ograniczyć interfejs użytkownika prezentowany użytkownikom na urządzeniu.</span><span class="sxs-lookup"><span data-stu-id="3b8be-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="3b8be-133">Możesz ustawić kioski tak, aby wyświetlały pojedynczą aplikację, lub wiele aplikacji z niestandardową stroną startową.</span><span class="sxs-lookup"><span data-stu-id="3b8be-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="3b8be-134">Kioski mogą również prezentować różne środowisko różnym użytkownikom.</span><span class="sxs-lookup"><span data-stu-id="3b8be-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="3b8be-135">[Kontrola aplikacji systemu Windows (WDAC, Windows Application Control),](windows-defender-application-control-wdac.md) aby całkowicie nie uruchamiać określonych aplikacji lub procesów.</span><span class="sxs-lookup"><span data-stu-id="3b8be-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="3b8be-136">Jeśli chcesz dowiedzieć się więcej na temat różnych metod zarządzania urządzeniami lub ograniczeń dotyczących urządzeń, zapoznaj się z następnym krokiem i zapoznaj się z Zarządzanie urządzeniami Omówienie.</span><span class="sxs-lookup"><span data-stu-id="3b8be-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <a name="next-step"></a><span data-ttu-id="3b8be-137">Następny krok</span><span class="sxs-lookup"><span data-stu-id="3b8be-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3b8be-138">Przeczytaj omówienie CSP i Zarządzanie urządzeniami CSP</span><span class="sxs-lookup"><span data-stu-id="3b8be-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)