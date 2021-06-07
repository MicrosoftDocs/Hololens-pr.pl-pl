---
title: Windows Defender Application Control — WDAC
description: Omówienie funkcji Windows Defender Application Control i sposobu używania jej do zarządzania urządzeniami HoloLens rzeczywistości mieszanej.
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
ms.openlocfilehash: 23c9a274387424e8f084a4729ee621e130820716
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378322"
---
# <a name="windows-defender-application-control---wdac"></a><span data-ttu-id="1edb4-103">Windows Defender Application Control — WDAC</span><span class="sxs-lookup"><span data-stu-id="1edb4-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="1edb4-104">Funkcja WDAC umożliwia administratorowi IT skonfigurowanie urządzeń tak, aby blokowały uruchamianie aplikacji na urządzeniach.</span><span class="sxs-lookup"><span data-stu-id="1edb4-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="1edb4-105">Różni się to od metod ograniczeń urządzenia, takich jak tryb kiosku, w którym użytkownik jest prezentowany z interfejsem użytkownika, który ukrywa aplikacje na urządzeniu, ale można je nadal uruchomiać.</span><span class="sxs-lookup"><span data-stu-id="1edb4-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="1edb4-106">Podczas implementowania usługi WDAC aplikacje są nadal widoczne na liście Wszystkie aplikacje, ale wdac zatrzymuje te aplikacje i procesy nie mogą być uruchomione przez użytkownika urządzenia.</span><span class="sxs-lookup"><span data-stu-id="1edb4-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="1edb4-107">Do urządzenia można przypisać więcej niż jedną zasady WDAC.</span><span class="sxs-lookup"><span data-stu-id="1edb4-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="1edb4-108">Jeśli w systemie ustawiono wiele zasad WDAC, zostaną one wprowadzone w najbardziej restrykcyjnych zasadach.</span><span class="sxs-lookup"><span data-stu-id="1edb4-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="1edb4-109">Gdy użytkownicy końcowi spróbują uruchomić aplikację zablokowaną przez centrum WDAC, na urządzeniach HoloLens nie otrzymają powiadomienia o tym, że nie będą mogli uruchomić tej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1edb4-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="1edb4-110">Poniżej przedstawiono przewodnik dla użytkowników, który pokazuje, jak używać funkcji WDAC i Windows PowerShell do zezwalania na aplikacje lub blokowania ich na urządzeniach [HoloLens 2](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)przy użyciu Microsoft Intune .</span><span class="sxs-lookup"><span data-stu-id="1edb4-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="1edb4-111">Gdy użytkownicy wyszukują aplikacje zainstalowane na komputerze Windows 10 pc przy użyciu pierwszego przykładowego kroku, może być konieczne kilka prób zawężenia wyników.</span><span class="sxs-lookup"><span data-stu-id="1edb4-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="1edb4-112">Jeśli nie znasz pełnej nazwy pakietu, być może trzeba będzie kilka razy uruchomić "Get-AppxPackage -name \* YourGueGuess", aby \* go znaleźć.</span><span class="sxs-lookup"><span data-stu-id="1edb4-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="1edb4-113">Następnie po uruchomieniu nazwy uruchom "$package 1 = Get-AppxPackage -name Actual.PackageName"</span><span class="sxs-lookup"><span data-stu-id="1edb4-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="1edb4-114">Na przykład uruchomienie następującej Microsoft Edge zwróci więcej niż jeden wynik, ale z tej listy można zidentyfikować, że pełna nazwa jest potrzebna: Microsoft.MicrosoftEdge.</span><span class="sxs-lookup"><span data-stu-id="1edb4-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a><span data-ttu-id="1edb4-115">Nazwy rodzin pakietów dla aplikacji na urządzeniach HoloLens</span><span class="sxs-lookup"><span data-stu-id="1edb4-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="1edb4-116">W powyższym przewodniku możesz ręcznie edytować i newPolicy.xml dla aplikacji zainstalowanych tylko na urządzeniach HoloLens z nazwami rodzin pakietów.</span><span class="sxs-lookup"><span data-stu-id="1edb4-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="1edb4-117">Czasami istnieją aplikacje, których można użyć, które nie znajdują się na komputerze stacjonarnym, które chcesz dodać do zasad.</span><span class="sxs-lookup"><span data-stu-id="1edb4-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="1edb4-118">Poniżej znajduje się lista najczęściej używanych i In-Box dla urządzeń HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="1edb4-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="1edb4-119">Nazwa aplikacji</span><span class="sxs-lookup"><span data-stu-id="1edb4-119">App Name</span></span>                   | <span data-ttu-id="1edb4-120">Nazwa rodziny pakietów</span><span class="sxs-lookup"><span data-stu-id="1edb4-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="1edb4-121">Przeglądarka 3D</span><span class="sxs-lookup"><span data-stu-id="1edb4-121">3D Viewer</span></span>                  | <span data-ttu-id="1edb4-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1edb4-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="1edb4-123">Instalator aplikacji</span><span class="sxs-lookup"><span data-stu-id="1edb4-123">App Installer</span></span>              | <span data-ttu-id="1edb4-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="1edb4-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span></span>         |
| <span data-ttu-id="1edb4-125">Kalendarz</span><span class="sxs-lookup"><span data-stu-id="1edb4-125">Calendar</span></span>                   | <span data-ttu-id="1edb4-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1edb4-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="1edb4-127">Aparat fotograficzny</span><span class="sxs-lookup"><span data-stu-id="1edb4-127">Camera</span></span>                     | <span data-ttu-id="1edb4-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="1edb4-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="1edb4-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="1edb4-129">Cortana</span></span>                    | <span data-ttu-id="1edb4-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1edb4-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="1edb4-131">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="1edb4-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="1edb4-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1edb4-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="1edb4-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="1edb4-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="1edb4-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1edb4-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="1edb4-135">Centrum opinii</span><span class="sxs-lookup"><span data-stu-id="1edb4-135">Feedback Hub</span></span>               | <span data-ttu-id="1edb4-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1edb4-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="1edb4-137">Eksplorator plików</span><span class="sxs-lookup"><span data-stu-id="1edb4-137">File Explorer</span></span>              | <span data-ttu-id="1edb4-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="1edb4-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="1edb4-139">Mail</span><span class="sxs-lookup"><span data-stu-id="1edb4-139">Mail</span></span>                       | <span data-ttu-id="1edb4-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1edb4-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="1edb4-141">Sklepie Microsoft</span><span class="sxs-lookup"><span data-stu-id="1edb4-141">Microsoft Store</span></span>            | <span data-ttu-id="1edb4-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1edb4-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="1edb4-143">Filmy & TV</span><span class="sxs-lookup"><span data-stu-id="1edb4-143">Movies & TV</span></span>                | <span data-ttu-id="1edb4-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1edb4-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="1edb4-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="1edb4-145">OneDrive</span></span>                   | <span data-ttu-id="1edb4-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1edb4-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="1edb4-147">Zdjęcia</span><span class="sxs-lookup"><span data-stu-id="1edb4-147">Photos</span></span>                     | <span data-ttu-id="1edb4-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1edb4-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="1edb4-149">Ustawienia</span><span class="sxs-lookup"><span data-stu-id="1edb4-149">Settings</span></span>                   | <span data-ttu-id="1edb4-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="1edb4-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="1edb4-151">Porady</span><span class="sxs-lookup"><span data-stu-id="1edb4-151">Tips</span></span>                       | <span data-ttu-id="1edb4-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1edb4-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="1edb4-153">1 — Blokowanie Instalator aplikacji będzie blokować tylko aplikację Instalator aplikacji, a nie aplikacje zainstalowane z innych źródeł, takich jak Microsoft Store lub z rozwiązania MDM.</span><span class="sxs-lookup"><span data-stu-id="1edb4-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <a name="how-to-find-a-package-family-name"></a><span data-ttu-id="1edb4-154">Jak znaleźć nazwę rodziny pakietów</span><span class="sxs-lookup"><span data-stu-id="1edb4-154">How to find a Package Family Name</span></span>

<span data-ttu-id="1edb4-155">Jeśli aplikacji nie ma na tej liście, użytkownik może użyć usługi Portal urządzeń połączonej z urządzeniem HoloLens 2, na których zainstalowano aplikację, w celu określenia wartości PackageRelativeID, a następnie uzyskania wartości PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="1edb4-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="1edb4-156">Zainstaluj aplikację na urządzeniu HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="1edb4-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="1edb4-157">Otwórz pozycję Ustawienia -> Aktualizacje & Security -> Dla deweloperów i włącz tryb **dewelopera,** a następnie **portal urządzeń.**</span><span class="sxs-lookup"><span data-stu-id="1edb4-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="1edb4-158">Aby uzyskać więcej szczegółowych instrukcji, przeczytaj więcej na temat konfigurowania i [używania portalu urządzeń tutaj.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="1edb4-158">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="1edb4-159">Po Portal urządzeń przejdź do widoków, a **następnie** **wybierz pozycję Aplikacje.**</span><span class="sxs-lookup"><span data-stu-id="1edb4-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="1edb4-160">Na panelu Zainstalowane aplikacje wybierz zainstalowaną aplikację przy użyciu listy rozwijanej.</span><span class="sxs-lookup"><span data-stu-id="1edb4-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="1edb4-161">Znajdź packageRelativeID.</span><span class="sxs-lookup"><span data-stu-id="1edb4-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="1edb4-162">Skopiuj znaki aplikacji przed znakiem !. Będzie to Twoja nazwa PackageFamilyName.</span><span class="sxs-lookup"><span data-stu-id="1edb4-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


