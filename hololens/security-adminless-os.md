---
title: Zabezpieczenia systemu operacyjnego bez uprawnień administratora
description: Dowiedz się więcej o systemach operacyjnych bez uprawnień administratora, właścicielach urządzeń i zabezpieczeniach na HoloLens rzeczywistości mieszanej.
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, adminless, admin-less, operating system, admin-less operating system, admin os, admin-less os, hololens 2, hololens2 security,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ed2d5134a6bc5952063f7dc5dc5d0e31db972b08
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639407"
---
# <a name="admin-less-operating-system"></a><span data-ttu-id="2bae4-104">System operacyjny bez uprawnień administratora</span><span class="sxs-lookup"><span data-stu-id="2bae4-104">Admin-less operating system</span></span>

<span data-ttu-id="2bae4-105">HoloLens 2 minimalizuje obszar powierzchni dla podwyższenia poziomu uprawnień, wyłączając obsługę grupy Administratorzy i ograniczając wszystkie kod aplikacji platformy UWP innych firm tak, aby był wykonywany tylko jako użytkownicy standardowi w piaskownicy appContainer.</span><span class="sxs-lookup"><span data-stu-id="2bae4-105">HoloLens 2 minimizes the surface area for privilege escalation by disabling support for the Administrators group and limiting all third-party UWP application code to only execute as standard users within the AppContainer sandbox.</span></span> <span data-ttu-id="2bae4-106">Ten kod ma przyznawany dostęp tylko do tych zasobów chronionych przez funkcje jawnie manifestowane w aplikacji dla użytkownika bez uprawnień, oprócz zasobów dostępnych dla wszystkich urządzeń AppContainer.</span><span class="sxs-lookup"><span data-stu-id="2bae4-106">This code is only granted access to those resources protected by capabilities explicitly manifested in the application for an unelevated user in addition to resources accessible to all AppContainers.</span></span>
<span data-ttu-id="2bae4-107">Te możliwości aplikacji nadal mają trzywarstwowy model klasyfikacji:</span><span class="sxs-lookup"><span data-stu-id="2bae4-107">These application capabilities continue to have the three-tiered classification model:</span></span>
  * <span data-ttu-id="2bae4-108">Ogólne</span><span class="sxs-lookup"><span data-stu-id="2bae4-108">General</span></span>
  * <span data-ttu-id="2bae4-109">Z ograniczeniami</span><span class="sxs-lookup"><span data-stu-id="2bae4-109">Restricted</span></span>
  * <span data-ttu-id="2bae4-110">Windows</span><span class="sxs-lookup"><span data-stu-id="2bae4-110">Windows</span></span>

<span data-ttu-id="2bae4-111">Windows mogą również korzystać z piaskownicy AppContainer za pośrednictwem ujścia systemu.</span><span class="sxs-lookup"><span data-stu-id="2bae4-111">Windows components can also leverage the AppContainer sandbox through System UWPs.</span></span> <span data-ttu-id="2bae4-112">Aby dowiedzieć się więcej o platformie uniwersalnej Windows (UWP), zobacz [dokumentację platformy UWP.](/windows/uwp/)</span><span class="sxs-lookup"><span data-stu-id="2bae4-112">To learn more about Universal Windows Platform (UWP), see [UWP documentation](/windows/uwp/).</span></span> <span data-ttu-id="2bae4-113">Ponadto składniki usługi Windows z większymi potrzebami redukcji uprawnień (takie jak strony zawartości przeglądarki lub parsery) korzystają z piaskownicy Less Privileged AppContainer (LPAC), która odcięła dostęp do zestawu zasobów dostępnych dla wszystkich aplikacji AppContainer.</span><span class="sxs-lookup"><span data-stu-id="2bae4-113">Additionally, Windows components with greater privilege reduction needs (like browser content pages or parsers) use the Less Privileged AppContainer (LPAC) sandbox, which cuts off access to the set of resources accessible to all AppContainers.</span></span>

## <a name="device-owner"></a><span data-ttu-id="2bae4-114">Właściciel urządzenia</span><span class="sxs-lookup"><span data-stu-id="2bae4-114">Device owner</span></span>

<span data-ttu-id="2bae4-115">Ponadto wykonywanie określonych operacji na całym urządzeniu, takich jak dołączanie urządzenia do dzierżawy lub zarządzania użytkownikami, jest dozwolone tylko dla "właścicieli urządzeń".</span><span class="sxs-lookup"><span data-stu-id="2bae4-115">Finally, the execution of specific device-wide operations, such as joining the device to a tenant or user management, is only permitted for “device owners”.</span></span> <span data-ttu-id="2bae4-116">Ta grupa jest wypełniana przez użytkowników na urządzeniu za pomocą jednego z następujących kroków:</span><span class="sxs-lookup"><span data-stu-id="2bae4-116">This group is populated by users on the device through one of the following steps:</span></span>
  * <span data-ttu-id="2bae4-117">Pierwszy użytkownik na urządzeniu jest zawsze wyznaczony jako właściciel.</span><span class="sxs-lookup"><span data-stu-id="2bae4-117">The first user on the device is always designated an Owner.</span></span> 
> [!IMPORTANT]
><span data-ttu-id="2bae4-118">W przypadku użytkowników usługi Azure AD wyjątkiem od tej reguły jest to, że jeśli urządzenie jest przyłączone do usługi Azure AD za pośrednictwem rozwiązania Autopilot lub rejestracji zbiorczej w usłudze Azure AD, która korzysta z nie rzeczywistego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="2bae4-118">For Azure AD Users, the exception to this rule is that if the device is Azure AD joined via Autopilot or bulk Azure AD enrollment, which uses a non-real user.</span></span> <span data-ttu-id="2bae4-119">W takim przypadku pierwszy użytkownik usługi AAD, który ma zalogować się na urządzeniu, może nie zostać automatycznie właścicielem urządzenia, chyba że ma przypisaną rolę "administrator globalny" lub "administrator urządzenia" w Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="2bae4-119">In this case, the first AAD user to sign into the device may not be made device owner automatically unless that user has the "global administrator" or "device administrator" role assigned in Azure portal.</span></span> <span data-ttu-id="2bae4-120">Aby uzyskać więcej informacji, zobacz uwaga poniżej.</span><span class="sxs-lookup"><span data-stu-id="2bae4-120">For more information, see the note below.</span></span>  

  * <span data-ttu-id="2bae4-121">Gdy użytkownik ma zostać właścicielem z witryny Ustawienia użytkownika przez innego właściciela urządzenia.</span><span class="sxs-lookup"><span data-stu-id="2bae4-121">When a user is promoted to be an Owner from the Settings UX by another Owner on the device.</span></span>
  * <span data-ttu-id="2bae4-122">Jeśli właściciel urządzenia nie jest już dostępny (opuszcza firmę), a urządzenie jest przyłączone do usługi Azure AD, administrator dzierżawy może zmienić właściciela urządzenia na nowego użytkownika w usłudze Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="2bae4-122">If the device owner is no longer available (leaves the company) and the device is Azure AD joined, the Tenant Admin can change the device owner to a new user in Azure portal.</span></span> <span data-ttu-id="2bae4-123">Administratorzy globalni i administratorzy urządzeń dzierżawy usługi Azure AD są niejawnie zalogowani jako właściciele na urządzeniu bez konieczności poprzednich kroków.</span><span class="sxs-lookup"><span data-stu-id="2bae4-123">Global Administrators and Device Administrators of an Azure AD tenant are implicitly signed in as Owners on the device without requiring either of the previous steps.</span></span>  

 <span data-ttu-id="2bae4-124">Administratorzy IT mogą zarządzać tym, do jakich aplikacji mogą uzyskać dostęp za [pośrednictwem zasad](/windows/client-management/mdm/policy-csp-privacy) ochrony prywatności.</span><span class="sxs-lookup"><span data-stu-id="2bae4-124">IT administrators can manage what apps can access through [Privacy](/windows/client-management/mdm/policy-csp-privacy) policies.</span></span> 

> [!NOTE]
> <span data-ttu-id="2bae4-125">Aby dowiedzieć się więcej na temat tego, kto jest właścicielem urządzenia przyłączonego do usługi Azure AD, zobacz dokumentację "Przypisywanie administratora lokalnego" (ale przeczytaj "administrator [lokalny"](/azure/active-directory/devices/assign-local-admin) jako "właściciel urządzenia", ponieważ administrator nie istnieje na HoloLens).</span><span class="sxs-lookup"><span data-stu-id="2bae4-125">To understand more about who is made a device owner on an Azure AD joined device, see [“Assign Local Admin” documentation](/azure/active-directory/devices/assign-local-admin) (but read ‘local admin’ as ‘device owner’ since admin does not exist on HoloLens).</span></span>