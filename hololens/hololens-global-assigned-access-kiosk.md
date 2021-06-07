---
title: Przypisany dostęp globalny
description: Rozpoczynanie pracy z naszym przewodnikiem dotyczącym używania OMA-URI dla kiosków z dostępem przypisanym globalnie przy użyciu usługi Intune i projektanta konfiguracji systemu Windows.
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens, hololens 2, przypisany dostęp, kiosk
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b86d88c7487043c6fcb057f03f353a57e44ef781
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379754"
---
# <a name="global-assigned-access--kiosk"></a><span data-ttu-id="56c12-104">Dostęp przypisany globalnie — kiosk</span><span class="sxs-lookup"><span data-stu-id="56c12-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="56c12-105">Ta funkcja konfiguruje urządzenie HoloLens 2 dla trybu kiosku z wieloma aplikacjami, który ma zastosowanie na poziomie systemu, nie ma koligacji z żadną tożsamością w systemie i ma zastosowanie do wszystkich użytkowników, którzy się na nim inserują.</span><span class="sxs-lookup"><span data-stu-id="56c12-105">This feature configures HoloLens 2 device for multiple app kiosk mode, which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span>

> [!NOTE]
> <span data-ttu-id="56c12-106">Ta funkcja jest obecnie dostępna tylko w niejawny tester systemu Windows kompilacjach.</span><span class="sxs-lookup"><span data-stu-id="56c12-106">This feature is currently only available in Windows Insider builds.</span></span> <span data-ttu-id="56c12-107">Jeśli chcesz wypróbować tę funkcję, zanim będzie ogólnie dostępna w wersjach [](hololens-insider.md) urządzenia HoloLens, przeczytaj więcej na temat niejawny tester systemu Windows kompilacji.</span><span class="sxs-lookup"><span data-stu-id="56c12-107">If you would like to try this feature before it is generally available in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>

## <a name="how-to-use-global-assigned-access-in-intune"></a><span data-ttu-id="56c12-108">Jak używać przypisanego globalnie dostępu w usłudze Intune?</span><span class="sxs-lookup"><span data-stu-id="56c12-108">How to use Global Assigned Access in Intune?</span></span>

> [!NOTE]
> <span data-ttu-id="56c12-109">Pamiętaj o obszarach oznaczonych literą "<!-".</span><span class="sxs-lookup"><span data-stu-id="56c12-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="56c12-110">Te obszary będą wymagały wprowadzania modyfikacji na podstawie Twoich preferencji.</span><span class="sxs-lookup"><span data-stu-id="56c12-110">These areas will require you to make modifications based on your preferences.</span></span>

1. <span data-ttu-id="56c12-111">Utwórz niestandardowy profil konfiguracji urządzenia OMA URI w następujący sposób i zastosuj go do grupy urządzeń HoloLens:</span><span class="sxs-lookup"><span data-stu-id="56c12-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group:</span></span>

    <span data-ttu-id="56c12-112">Wartość URI: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span><span class="sxs-lookup"><span data-stu-id="56c12-112">URI value: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="56c12-113">![Globalnie przypisany dostęp OMA-URI w usłudze Intune](images/global-assigned-access-omauri.png)</span><span class="sxs-lookup"><span data-stu-id="56c12-113">![Global Assigned Access OMA-URI in Intune](images/global-assigned-access-omauri.png)</span></span>

2. <span data-ttu-id="56c12-114">Jako wartość zaktualizuj i wklej następującą zawartość:</span><span class="sxs-lookup"><span data-stu-id="56c12-114">For value, update and paste following content:</span></span>

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a><span data-ttu-id="56c12-115">Jak używać przypisanego globalnie dostępu w programie Windows Configuration Designer?</span><span class="sxs-lookup"><span data-stu-id="56c12-115">How to use Global Assigned Access in Windows Configuration Designer?</span></span>

1. <span data-ttu-id="56c12-116">Zaktualizuj i zapisz obiekt blob XML wymieniony powyżej jako plik XML.</span><span class="sxs-lookup"><span data-stu-id="56c12-116">Update and save XML blob mentioned above as XML file.</span></span> 

2. <span data-ttu-id="56c12-117">Wykonaj kroki opisane w [sekcji Używanie](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)pakietu aprowizowania, aby skonfigurować kiosk z pojedynczą aplikacją lub z wieloma aplikacjami, a w szczególności sekcję "Prov.</span><span class="sxs-lookup"><span data-stu-id="56c12-117">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="56c12-118">package, step 2 — Add the kiosk configuration XML file to a provisioning package" (Dodaj plik XML konfiguracji kiosku do pakietu aprowizowania) i odwołaj się do pliku XML zapisanego w poprzednim kroku.</span><span class="sxs-lookup"><span data-stu-id="56c12-118">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span>

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a><span data-ttu-id="56c12-119">Czy mogę utworzyć konfigurację, w której konfiguracja globalna ma zastosowanie do wszystkich, a oddzielna konfiguracja dotyczy 1 konta usługi Azure AD lub grupy usługi Azure AD?</span><span class="sxs-lookup"><span data-stu-id="56c12-119">Can I create a configuration where global applies to everyone and separate configuration applies to 1 Azure AD account or Azure AD group?</span></span> 

<span data-ttu-id="56c12-120">Tak, zapoznaj się z poniższym przykładem obiektu blob XML.</span><span class="sxs-lookup"><span data-stu-id="56c12-120">Yes, refer to the example XML blob below.</span></span> <span data-ttu-id="56c12-121">Profil przypisany globalnie dostępu jest stosowany na urządzeniach HoloLens, gdy nie zostanie znaleziony konkretny profil dla zalogowaowego użytkownika, dlatego jest to domyślna konfiguracja trybu kiosku dla zalogowaowego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="56c12-121">Global Assigned Access profile is applied on HoloLens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span>
<span data-ttu-id="56c12-122">Oto przykład obiektu blob XML, który ma być używany:</span><span class="sxs-lookup"><span data-stu-id="56c12-122">Here is an example of XML blob to be used:</span></span>

> [!NOTE]
> <span data-ttu-id="56c12-123">Pamiętaj o wyróżnione obszary oznaczone znakiem `<!-` .</span><span class="sxs-lookup"><span data-stu-id="56c12-123">Please be aware of the highlighted areas marked with `<!-`.</span></span> <span data-ttu-id="56c12-124">Te obszary będą wymagały wprowadzania modyfikacji na podstawie Twoich preferencji.</span><span class="sxs-lookup"><span data-stu-id="56c12-124">These areas will require you to make modifications based on your preferences.</span></span>

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a><span data-ttu-id="56c12-125">Wykluczanie właścicieli urządzeń z globalnego przypisanego profilu dostępu</span><span class="sxs-lookup"><span data-stu-id="56c12-125">Excluding DeviceOwners from Global Assigned Access Profile</span></span>

<span data-ttu-id="56c12-126">Ta funkcja umożliwia wykluczenie użytkownika, który jest uznawany za["właściciela urządzenia"](security-adminless-os.md)na urządzeniu HoloLens, z dostępu przypisanego globalnie.</span><span class="sxs-lookup"><span data-stu-id="56c12-126">This feature allows a user who is considered “[Device owner](security-adminless-os.md)" on HoloLens to be excluded from Global Assigned Access.</span></span> <span data-ttu-id="56c12-127">Aby móc korzystać z tej funkcji, w obiekcie blob XML dla konfiguracji kiosku z wieloma aplikacjami upewnij się, że dodano wyróżnione wiersze:</span><span class="sxs-lookup"><span data-stu-id="56c12-127">In order to take advantage of this feature, in the XML blob for multiple-app kiosk configuration, ensure highlighted lines are added:</span></span>

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a><span data-ttu-id="56c12-128">Dodatkowe przykłady przypisanego dostępu globalnego</span><span class="sxs-lookup"><span data-stu-id="56c12-128">Additional Global Assigned Access Examples</span></span>

<span data-ttu-id="56c12-129">Jest to przykład kiosku z przypisanym dostępem globalnym, w którym każdy użytkownik, który się do niego insyguje, będzie miał kiosk z wieloma aplikacjami z aplikacją Ustawienia, Centrum opinii i Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="56c12-129">This is an example Global Assigned Access kiosk that when any user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

<span data-ttu-id="56c12-130">W tym przykładzie jest to kiosk z dostępem przypisanym globalnie, który wyklucza właściciela urządzenia. Gdy inny użytkownik usługi Azure AD się na nim insyguje, będzie miał kiosk z wieloma aplikacjami z aplikacją Ustawienia, Centrum opinii i Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="56c12-130">This example is a Global Assigned Access kiosk that excludes the device owner, when any other Azure AD user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span> <span data-ttu-id="56c12-131">Ten kiosk obejmuje również dodatkową konfigurację kiosku dla konta gościa, do którego może się zalogować każda osoba na ekranie blokady.</span><span class="sxs-lookup"><span data-stu-id="56c12-131">This kiosk also includes a secondary kiosk configuration for a Visitor account, which may be signed into by anyone on the lock screen.</span></span> <span data-ttu-id="56c12-132">Gdy użytkownik się na konto gościa, będzie mieć kiosk z wieloma Centrum opinii aplikacji.</span><span class="sxs-lookup"><span data-stu-id="56c12-132">When a user signs into the Visitor account they will have a multi-app kiosk that only has the Feedback Hub app.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
