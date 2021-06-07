---
title: Typowe scenariusze — bezpieczne urządzenie HoloLens 2 w trybie offline
description: Dowiedz się, jak skonfigurować scenariusz bezpiecznego wdrażania i wdrażania aplikacji w trybie offline przy użyciu aprowizowania dla urządzeń HoloLens.
keywords: HoloLens, zarządzanie, offline, bezpieczne w trybie offline
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 8828444a69d7e5d46293340ff771f97eb5eb01e6
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378250"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="c81eb-104">Typowe scenariusze — bezpieczne urządzenie HoloLens 2 w trybie offline</span><span class="sxs-lookup"><span data-stu-id="c81eb-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="c81eb-105">Omówienie</span><span class="sxs-lookup"><span data-stu-id="c81eb-105">Overview</span></span>

<span data-ttu-id="c81eb-106">Ten przewodnik zawiera wskazówki dotyczące stosowania przykładowego pakietu aprowizowania, który zablokuje urządzenie HoloLens 2 do użycia w bezpiecznych środowiskach z następującymi ograniczeniami:</span><span class="sxs-lookup"><span data-stu-id="c81eb-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="c81eb-107">Wyłącz sieć Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="c81eb-107">Disable WiFi.</span></span>
-   <span data-ttu-id="c81eb-108">Wyłącz funkcję BlueTooth.</span><span class="sxs-lookup"><span data-stu-id="c81eb-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="c81eb-109">Wyłącz mikrofony.</span><span class="sxs-lookup"><span data-stu-id="c81eb-109">Disable Microphones.</span></span>
-   <span data-ttu-id="c81eb-110">Uniemożliwia dodawanie lub usuwanie pakietów aprowizowania.</span><span class="sxs-lookup"><span data-stu-id="c81eb-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="c81eb-111">Żaden użytkownik nie może włączyć żadnego z powyższych składników z ograniczeniami.</span><span class="sxs-lookup"><span data-stu-id="c81eb-111">No user can enable any of the above restricted components.</span></span>

<span data-ttu-id="c81eb-112">[![Scenariusz zabezpieczenia w trybie ](./images/deployment-guides-revised-scenario-c-01.png) offline](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="c81eb-112">[ ![Offline Secure scenario](./images/deployment-guides-revised-scenario-c-01.png) ](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

## <a name="prepare"></a><span data-ttu-id="c81eb-113">Przygotowywanie</span><span class="sxs-lookup"><span data-stu-id="c81eb-113">Prepare</span></span>

<span data-ttu-id="c81eb-114">Windows 10 konfiguracji komputera</span><span class="sxs-lookup"><span data-stu-id="c81eb-114">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="c81eb-115">[Pobierz najnowszy plik systemu operacyjnego HoloLens 2](https://aka.ms/hololens2download) bezpośrednio na komputer.</span><span class="sxs-lookup"><span data-stu-id="c81eb-115">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="c81eb-116">Obsługa tej konfiguracji jest uwzględniona w kompilacji 19041.1117 i powyższych.</span><span class="sxs-lookup"><span data-stu-id="c81eb-116">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="c81eb-117">Pobierz/zainstaluj narzędzie Advanced Recovery Companion (ARC) [z](https://www.microsoft.com/store/productId/9P74Z35SFRS8) Microsoft Store na komputer</span><span class="sxs-lookup"><span data-stu-id="c81eb-117">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="c81eb-118">Pobierz/zainstaluj najnowsze narzędzie [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) z Microsoft Store na komputerze.</span><span class="sxs-lookup"><span data-stu-id="c81eb-118">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="c81eb-119">[Pobierz folder OfflineSecureHL2_Sample z plikami projektu,](https://aka.ms/HoloLensDocs-SecureOfflineSample) aby skompilować plik PPKG.</span><span class="sxs-lookup"><span data-stu-id="c81eb-119">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="c81eb-120">Przygotuj aplikację [biznesową w trybie offline do wdrożenia ppkg.](app-deploy-provisioning-package.md)</span><span class="sxs-lookup"><span data-stu-id="c81eb-120">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="c81eb-121">Konfigurowanie</span><span class="sxs-lookup"><span data-stu-id="c81eb-121">Configure</span></span>

<span data-ttu-id="c81eb-122">Tworzenie bezpiecznego pakietu aprowizowania konfiguracji</span><span class="sxs-lookup"><span data-stu-id="c81eb-122">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="c81eb-123">Uruchom narzędzie WCD na komputerze.</span><span class="sxs-lookup"><span data-stu-id="c81eb-123">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="c81eb-124">Wybierz **pozycję Plik -> Otwórz projekt.**</span><span class="sxs-lookup"><span data-stu-id="c81eb-124">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="c81eb-125">Przejdź do lokalizacji wcześniej zapisanego folderu OfflineSecureHL2_Sample i wybierz pozycję: OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="c81eb-125">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="c81eb-126">Projekt powinien zostać otwarty i powinna zostać wyświetlona lista Dostępnych dostosowań:</span><span class="sxs-lookup"><span data-stu-id="c81eb-126">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c81eb-127">![Zrzut ekranu przedstawiający pakiet konfiguracyjnych otwarty w UCD](images/offline-secure-sample-wcd.png)</span><span class="sxs-lookup"><span data-stu-id="c81eb-127">![Screenshot of the configuration package open in WCD](images/offline-secure-sample-wcd.png)</span></span>

   <span data-ttu-id="c81eb-128">Konfiguracje ustawione w tym pakiecie aprowizowania:</span><span class="sxs-lookup"><span data-stu-id="c81eb-128">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="c81eb-129">Element</span><span class="sxs-lookup"><span data-stu-id="c81eb-129">Item</span></span>                                                |     <span data-ttu-id="c81eb-130">Ustawienie</span><span class="sxs-lookup"><span data-stu-id="c81eb-130">Setting</span></span>                       |     <span data-ttu-id="c81eb-131">Opis</span><span class="sxs-lookup"><span data-stu-id="c81eb-131">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="c81eb-132">Konta/użytkownicy</span><span class="sxs-lookup"><span data-stu-id="c81eb-132">Accounts / Users</span></span>                                    |     <span data-ttu-id="c81eb-133">Nazwa użytkownika lokalnego & hasło</span><span class="sxs-lookup"><span data-stu-id="c81eb-133">Local User Name & Password</span></span>    |     <span data-ttu-id="c81eb-134">W przypadku tych urządzeń w trybie offline należy ustawić i udostępnić wszystkim użytkownikom urządzenia pojedynczą nazwę użytkownika i hasło.</span><span class="sxs-lookup"><span data-stu-id="c81eb-134">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="c81eb-135">Pierwsze środowisko / HoloLens / SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="c81eb-135">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="c81eb-136">Prawda</span><span class="sxs-lookup"><span data-stu-id="c81eb-136">True</span></span>                          |     <span data-ttu-id="c81eb-137">Pomija pominięcia tylko podczas początkowej konfiguracji urządzenia</span><span class="sxs-lookup"><span data-stu-id="c81eb-137">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="c81eb-138">Pierwsze środowisko / HoloLens / SkipTraining</span><span class="sxs-lookup"><span data-stu-id="c81eb-138">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="c81eb-139">Prawda</span><span class="sxs-lookup"><span data-stu-id="c81eb-139">True</span></span>                          |     <span data-ttu-id="c81eb-140">Pomija trenowania urządzenia podczas początkowej konfiguracji urządzenia</span><span class="sxs-lookup"><span data-stu-id="c81eb-140">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="c81eb-141">Pierwsze środowisko / HoloLens / WiFi</span><span class="sxs-lookup"><span data-stu-id="c81eb-141">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="c81eb-142">Prawda</span><span class="sxs-lookup"><span data-stu-id="c81eb-142">True</span></span>                          |     <span data-ttu-id="c81eb-143">Pomija Wi-Fi konfiguracji podczas początkowej konfiguracji urządzenia</span><span class="sxs-lookup"><span data-stu-id="c81eb-143">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="c81eb-144">Policies/Connectivity/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="c81eb-144">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="c81eb-145">Nie</span><span class="sxs-lookup"><span data-stu-id="c81eb-145">No</span></span>                            |     <span data-ttu-id="c81eb-146">Wyłącza funkcję Bluetooth</span><span class="sxs-lookup"><span data-stu-id="c81eb-146">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="c81eb-147">Zasady/środowisko/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="c81eb-147">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="c81eb-148">Nie</span><span class="sxs-lookup"><span data-stu-id="c81eb-148">No</span></span>                            |     <span data-ttu-id="c81eb-149">Wyłącza Cortanę (aby wyeliminować potencjalne problemy, ponieważ mikrofony są wyłączone)</span><span class="sxs-lookup"><span data-stu-id="c81eb-149">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="c81eb-150">Policies/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="c81eb-150">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="c81eb-151">Tak</span><span class="sxs-lookup"><span data-stu-id="c81eb-151">Yes</span></span>                           |     <span data-ttu-id="c81eb-152">Wyłącza mikrofon</span><span class="sxs-lookup"><span data-stu-id="c81eb-152">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="c81eb-153">Zasady/Prywatność/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="c81eb-153">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="c81eb-154">Wymusz odmowę</span><span class="sxs-lookup"><span data-stu-id="c81eb-154">Force deny</span></span>                    |     <span data-ttu-id="c81eb-155">Uniemożliwia aplikacjom próby uzyskania dostępu do danych lokalizacji (aby wyeliminować potencjalne problemy, ponieważ śledzenie lokalizacji jest wyłączone)</span><span class="sxs-lookup"><span data-stu-id="c81eb-155">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="c81eb-156">Zasady/Prywatność/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="c81eb-156">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="c81eb-157">Wymusz odmowę</span><span class="sxs-lookup"><span data-stu-id="c81eb-157">Force deny</span></span>                    |     <span data-ttu-id="c81eb-158">Uniemożliwia aplikacjom próby uzyskania dostępu do mikrofonów (aby wyeliminować potencjalne problemy, ponieważ mikrofony są wyłączone)</span><span class="sxs-lookup"><span data-stu-id="c81eb-158">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="c81eb-159">Policies/Security/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="c81eb-159">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="c81eb-160">Nie</span><span class="sxs-lookup"><span data-stu-id="c81eb-160">No</span></span>                            |     <span data-ttu-id="c81eb-161">Uniemożliwia dodawanie pakietów aprowizowania, które mogą próbować przesłonić zablokowane zasady.</span><span class="sxs-lookup"><span data-stu-id="c81eb-161">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="c81eb-162">Policies/Security/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="c81eb-162">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="c81eb-163">Nie</span><span class="sxs-lookup"><span data-stu-id="c81eb-163">No</span></span>                            |     <span data-ttu-id="c81eb-164">Uniemożliwia usunięcie tego zablokowanego pakietu aprowizowania przez wszystkie osoby.</span><span class="sxs-lookup"><span data-stu-id="c81eb-164">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="c81eb-165">Zasady/System/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="c81eb-165">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="c81eb-166">Nie</span><span class="sxs-lookup"><span data-stu-id="c81eb-166">No</span></span>                            |     <span data-ttu-id="c81eb-167">Uniemożliwia urządzeniu śledzenie danych lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="c81eb-167">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="c81eb-168">Policies/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="c81eb-168">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="c81eb-169">Nie</span><span class="sxs-lookup"><span data-stu-id="c81eb-169">No</span></span>                            |     <span data-ttu-id="c81eb-170">Wyłącza Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="c81eb-170">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="c81eb-171">W obszarze Ustawienia środowiska uruchomieniowego wybierz **pozycję Accounts / Users / UserName: Holo / Password**.</span><span class="sxs-lookup"><span data-stu-id="c81eb-171">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="c81eb-172">Zanotuj hasło i w razie potrzeby zresetuj je.</span><span class="sxs-lookup"><span data-stu-id="c81eb-172">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="c81eb-173">Przejdź do aplikacji UniversalAppInstall/UserContextApp i skonfiguruj aplikację [LOB,](app-deploy-provisioning-package.md) która będzie wdrażana na tych urządzeniach.</span><span class="sxs-lookup"><span data-stu-id="c81eb-173">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c81eb-174">![Zrzut ekranu przedstawiający miejsce dodawania aplikacji w udaniu WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span><span class="sxs-lookup"><span data-stu-id="c81eb-174">![Screenshot of where to add your app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span></span>

1. <span data-ttu-id="c81eb-175">Po zakończeniu wybierz przycisk "Eksportuj" i postępuj zgodnie ze wszystkimi monitami do momentu utworzenia pakietu aprowizowania.</span><span class="sxs-lookup"><span data-stu-id="c81eb-175">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c81eb-176">![Zrzut ekranu przedstawiający przycisk Eksportuj dla tego pakietu w Uakiecie WCD.](images/offline-secure-sample-wcd-export.png)</span><span class="sxs-lookup"><span data-stu-id="c81eb-176">![Screenshot of the Export button for this package in WCD.](images/offline-secure-sample-wcd-export.png)</span></span>

## <a name="deploy"></a><span data-ttu-id="c81eb-177">Wdróż</span><span class="sxs-lookup"><span data-stu-id="c81eb-177">Deploy</span></span>

1. <span data-ttu-id="c81eb-178">Podłącz hl2 do komputera Windows 10 za pośrednictwem kabla USB.</span><span class="sxs-lookup"><span data-stu-id="c81eb-178">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="c81eb-179">Uruchom narzędzie ARC i wybierz pozycję **HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="c81eb-179">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![Początkowy ekran czystego ukośnika HoloLens 2](images/ARC2.png)

1. <span data-ttu-id="c81eb-181">Na następnym ekranie wybierz opcję **Ręczne wybieranie pakietu.**</span><span class="sxs-lookup"><span data-stu-id="c81eb-181">On the next screen select **Manual package selection**.</span></span>

   ![Ekran informacyjny urządzenia HoloLens 2 ARC](images/arc_device_info.png)

1. <span data-ttu-id="c81eb-183">Przejdź do wcześniej pobranego pliku ffu i wybierz pozycję **Otwórz**.</span><span class="sxs-lookup"><span data-stu-id="c81eb-183">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="c81eb-184">Na stronie Ostrzeżenie wybierz pozycję **Kontynuuj.**</span><span class="sxs-lookup"><span data-stu-id="c81eb-184">At the Warning page select **Continue**.</span></span>

   ![Ekran ostrzegawczy urządzenia HoloLens 2 ARC](images/arc_warning.png)

1. <span data-ttu-id="c81eb-186">Poczekaj, aż narzędzie ARC ukończy instalację systemu operacyjnego HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="c81eb-186">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="c81eb-187">Po zakończeniu instalacji urządzenia i jego uruchamianiu z komputera przejdź do folderu Eksplorator plików i skopiuj wcześniej zapisany plik PPKG do folderu urządzenia.</span><span class="sxs-lookup"><span data-stu-id="c81eb-187">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c81eb-188">![Plik PPKG na komputerze w Eksplorator plików okna.](images/offline-secure-file-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="c81eb-188">![PPKG file on PC in File Explorer window.](images/offline-secure-file-explorer.png)</span></span>

1. <span data-ttu-id="c81eb-189">Na urządzeniach HoloLens 2 naciśnij następujące kombinacje przycisków, aby uruchomić pakiet aprowizowania: naciśnij jednocześnie pozycję Volume **Down** (Wolumin w dół) **i Power Button (Przycisk** zasilania).</span><span class="sxs-lookup"><span data-stu-id="c81eb-189">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="c81eb-190">Zostanie wyświetlony monit o zastosowanie pakietu aprowizowania, wybierz pozycję **Potwierdź**</span><span class="sxs-lookup"><span data-stu-id="c81eb-190">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="c81eb-191">Po zakończeniu pakietu aprowizowania wybierz przycisk **OK.**</span><span class="sxs-lookup"><span data-stu-id="c81eb-191">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="c81eb-192">Następnie powinien zostać wyświetlony monit o zalogowanie się na urządzeniu przy użyciu udostępnionego konta lokalnego i hasła.</span><span class="sxs-lookup"><span data-stu-id="c81eb-192">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="c81eb-193">Obsługa</span><span class="sxs-lookup"><span data-stu-id="c81eb-193">Maintain</span></span>

<span data-ttu-id="c81eb-194">W przypadku tej konfiguracji zaleca się ponowne uruchomienie powyższego procesu i reflashowanie urządzenia za pomocą narzędzia ARC oraz zastosowanie nowego narzędzia PPKG w celu aktualizacji systemu operacyjnego i/lub aplikacji.</span><span class="sxs-lookup"><span data-stu-id="c81eb-194">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
