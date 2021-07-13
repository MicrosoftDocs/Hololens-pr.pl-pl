---
title: Windows Defender Kontrola aplikacji — WDAC
description: Omówienie tego, czym Windows Defender jest kontrola aplikacji i jak za jej pomocą zarządzać HoloLens rzeczywistości mieszanej.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/26/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: a27a16913873c5245f734dbe084eb2b7ed007c20
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639934"
---
# <a name="windows-defender-application-control---wdac"></a><span data-ttu-id="58202-103">Windows Defender Kontrola aplikacji — WDAC</span><span class="sxs-lookup"><span data-stu-id="58202-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="58202-104">Funkcja WDAC umożliwia administratorowi IT skonfigurowanie urządzeń tak, aby blokowały uruchamianie aplikacji na urządzeniach.</span><span class="sxs-lookup"><span data-stu-id="58202-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="58202-105">Różni się to od metod ograniczeń dotyczących urządzeń, takich jak tryb kiosku, w którym użytkownik jest prezentowany za pomocą interfejsu użytkownika, który ukrywa aplikacje na urządzeniu, ale można je nadal uruchomiać.</span><span class="sxs-lookup"><span data-stu-id="58202-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="58202-106">Podczas implementowania usługi WDAC aplikacje są nadal widoczne na liście Wszystkie aplikacje, ale wdac zatrzymuje te aplikacje i procesy mogą być uruchomione przez użytkownika urządzenia.</span><span class="sxs-lookup"><span data-stu-id="58202-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="58202-107">Do urządzenia można przypisać więcej niż jedną zasady WDAC.</span><span class="sxs-lookup"><span data-stu-id="58202-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="58202-108">Jeśli w systemie ustawiono wiele zasad WDAC, zostaną one wprowadzone w najbardziej restrykcyjnych zasadach.</span><span class="sxs-lookup"><span data-stu-id="58202-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="58202-109">Gdy użytkownicy końcowi spróbują uruchomić aplikację zablokowaną przez centrum WDAC, na HoloLens nie otrzymają powiadomienia o tym, że nie można uruchomić tej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="58202-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="58202-110">Poniżej przedstawiono przewodnik dla użytkowników, aby dowiedzieć się, jak używać funkcji [WDAC i Windows PowerShell](/mem/intune/configuration/custom-profile-hololens)do zezwalania na aplikacje lub blokowania ich na urządzeniach z systemem HoloLens 2 przy użyciu usługi Microsoft Intune .</span><span class="sxs-lookup"><span data-stu-id="58202-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="58202-111">Gdy użytkownicy wyszukują aplikacje zainstalowane na komputerze Windows 10 przy użyciu pierwszego przykładowego kroku, może być konieczne kilku prób zawężenia wyników.</span><span class="sxs-lookup"><span data-stu-id="58202-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="58202-112">Jeśli nie znasz pełnej nazwy pakietu, być może trzeba będzie kilka razy uruchomić "Get-AppxPackage -name \* YourGueGuess", aby \* go znaleźć.</span><span class="sxs-lookup"><span data-stu-id="58202-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="58202-113">Następnie po nazwie uruchom "$package 1 = Get-AppxPackage -name Actual.PackageName"</span><span class="sxs-lookup"><span data-stu-id="58202-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="58202-114">Na przykład uruchomienie następującej Microsoft Edge spowoduje zwrócenie więcej niż jednego wyniku, ale z tej listy można zidentyfikować, że pełna nazwa, która jest potrzebna, to Microsoft.MicrosoftEdge.</span><span class="sxs-lookup"><span data-stu-id="58202-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a><span data-ttu-id="58202-115">Nazwy rodzin pakietów dla aplikacji na HoloLens</span><span class="sxs-lookup"><span data-stu-id="58202-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="58202-116">W powyższym przewodniku można ręcznie edytować i dodawać newPolicy.xml dla aplikacji, które są instalowane tylko na HoloLens z nazwami rodzin pakietów.</span><span class="sxs-lookup"><span data-stu-id="58202-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="58202-117">Czasami istnieją aplikacje, których można użyć, które nie znajdują się na komputerze stacjonarnym, które chcesz dodać do zasad.</span><span class="sxs-lookup"><span data-stu-id="58202-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="58202-118">Poniżej znajduje się lista najczęściej używanych i używanych In-Box dla HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="58202-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="58202-119">Nazwa aplikacji</span><span class="sxs-lookup"><span data-stu-id="58202-119">App Name</span></span>                   | <span data-ttu-id="58202-120">Nazwa rodziny pakietów</span><span class="sxs-lookup"><span data-stu-id="58202-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="58202-121">Przeglądarka 3D</span><span class="sxs-lookup"><span data-stu-id="58202-121">3D Viewer</span></span>                  | <span data-ttu-id="58202-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="58202-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="58202-123">Instalator aplikacji</span><span class="sxs-lookup"><span data-stu-id="58202-123">App Installer</span></span>              | <span data-ttu-id="58202-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="58202-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span></span>         |
| <span data-ttu-id="58202-125">Kalendarz</span><span class="sxs-lookup"><span data-stu-id="58202-125">Calendar</span></span>                   | <span data-ttu-id="58202-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="58202-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="58202-127">Aparat fotograficzny</span><span class="sxs-lookup"><span data-stu-id="58202-127">Camera</span></span>                     | <span data-ttu-id="58202-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="58202-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="58202-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="58202-129">Cortana</span></span>                    | <span data-ttu-id="58202-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="58202-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="58202-131">Przewodniki dotyczące usługi Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="58202-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="58202-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="58202-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="58202-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="58202-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="58202-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="58202-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="58202-135">Centrum opinii</span><span class="sxs-lookup"><span data-stu-id="58202-135">Feedback Hub</span></span>               | <span data-ttu-id="58202-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="58202-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="58202-137">Eksplorator plików</span><span class="sxs-lookup"><span data-stu-id="58202-137">File Explorer</span></span>              | <span data-ttu-id="58202-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="58202-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="58202-139">Mail</span><span class="sxs-lookup"><span data-stu-id="58202-139">Mail</span></span>                       | <span data-ttu-id="58202-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="58202-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="58202-141">Sklepie Microsoft</span><span class="sxs-lookup"><span data-stu-id="58202-141">Microsoft Store</span></span>            | <span data-ttu-id="58202-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="58202-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="58202-143">Filmy & TV</span><span class="sxs-lookup"><span data-stu-id="58202-143">Movies & TV</span></span>                | <span data-ttu-id="58202-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="58202-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="58202-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="58202-145">OneDrive</span></span>                   | <span data-ttu-id="58202-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="58202-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="58202-147">Zdjęcia</span><span class="sxs-lookup"><span data-stu-id="58202-147">Photos</span></span>                     | <span data-ttu-id="58202-148">Microsoft. Windows. Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="58202-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="58202-149">Ustawienia</span><span class="sxs-lookup"><span data-stu-id="58202-149">Settings</span></span>                   | <span data-ttu-id="58202-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="58202-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="58202-151">Porady</span><span class="sxs-lookup"><span data-stu-id="58202-151">Tips</span></span>                       | <span data-ttu-id="58202-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="58202-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="58202-153">1 — Blokowanie Instalator aplikacji blokuje tylko aplikację Instalator aplikacji, a nie aplikacje zainstalowane z innych źródeł, takich jak Microsoft Store lub z rozwiązania MDM.</span><span class="sxs-lookup"><span data-stu-id="58202-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <a name="how-to-find-a-package-family-name"></a><span data-ttu-id="58202-154">Jak znaleźć nazwę rodziny pakietów</span><span class="sxs-lookup"><span data-stu-id="58202-154">How to find a Package Family Name</span></span>

<span data-ttu-id="58202-155">Jeśli aplikacja nie znajduje się na tej liście, użytkownik może użyć nazwy Portal urządzeń połączonej z urządzeniem HoloLens 2, na których zainstalowano aplikację, w celu określenia wartości PackageRelativeID, a następnie uzyskania wartości PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="58202-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="58202-156">Zainstaluj aplikację na urządzeniu HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="58202-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="58202-157">Otwórz Ustawienia -> Updates & Security -> Dla deweloperów, włącz tryb dewelopera, a następnie **portal urządzeń.** </span><span class="sxs-lookup"><span data-stu-id="58202-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="58202-158">Aby uzyskać więcej szczegółowych instrukcji, przeczytaj więcej na temat konfigurowania i [używania portalu urządzeń tutaj.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="58202-158">More more details instructions read more about [setup and use of device portal here](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="58202-159">Po Portal urządzeń przejdź do menu **Widoki,** a następnie **wybierz pozycję Aplikacje.**</span><span class="sxs-lookup"><span data-stu-id="58202-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="58202-160">Na panelu Zainstalowane aplikacje użyj listy rozwijanej, aby wybrać zainstalowaną aplikację.</span><span class="sxs-lookup"><span data-stu-id="58202-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="58202-161">Znajdź pakiet PackageRelativeID.</span><span class="sxs-lookup"><span data-stu-id="58202-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="58202-162">Skopiuj znaki aplikacji przed znakiem !. Będą to twoje znaki PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="58202-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


