---
title: Aktualizowanie urządzenia HoloLens 2
description: Dowiedz się, jak sprawdzić numer kompilacji urządzenia HoloLens, być na bieżąco z aktualizacjami urządzeń, dołączyć do programu dla niejawnych testerów i wycofać aktualizacje.
keywords: kompilowanie, aktualizowanie, wycofywanie, HoloLens, sprawdzanie kompilacji, numer kompilacji
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: a27eb1d5eb32a6654f60aac98090cba1aab529d3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924115"
---
# <a name="update-hololens-2"></a><span data-ttu-id="0ad5e-104">Aktualizowanie urządzenia HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="0ad5e-104">Update HoloLens 2</span></span>

<span data-ttu-id="0ad5e-105">Urządzenie HoloLens używa Windows Update, podobnie jak inne Windows 10 urządzenia.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="0ad5e-106">Urządzenie HoloLens będzie automatycznie pobierać i instalować aktualizacje systemu za każdym razem, gdy jest podłączony do zasilania i połączony z Internetem, nawet jeśli jest w stanie wstrzymania.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="0ad5e-107">Ten artykuł zawiera informacje na temat narzędzi dla urządzenia HoloLens:</span><span class="sxs-lookup"><span data-stu-id="0ad5e-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="0ad5e-108">wyświetlanie bieżącej wersji systemu operacyjnego (numer kompilacji)</span><span class="sxs-lookup"><span data-stu-id="0ad5e-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="0ad5e-109">sprawdzanie aktualizacji</span><span class="sxs-lookup"><span data-stu-id="0ad5e-109">checking for updates</span></span>
- <span data-ttu-id="0ad5e-110">ręczne aktualizowanie urządzenia HoloLens</span><span class="sxs-lookup"><span data-stu-id="0ad5e-110">manually updating HoloLens</span></span>
- <span data-ttu-id="0ad5e-111">wycofywanie do starszej aktualizacji</span><span class="sxs-lookup"><span data-stu-id="0ad5e-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="0ad5e-112">Sprawdź wersję systemu operacyjnego (numer kompilacji)</span><span class="sxs-lookup"><span data-stu-id="0ad5e-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="0ad5e-113">Numer wersji systemu (numer kompilacji) możesz sprawdzić, otwierając aplikację Ustawienia i wybierając pozycję System About **(Informacje o**  >  **systemie).**</span><span class="sxs-lookup"><span data-stu-id="0ad5e-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="0ad5e-114">Sprawdzanie aktualizacji i ręczne aktualizowanie</span><span class="sxs-lookup"><span data-stu-id="0ad5e-114">Check for updates and manually update</span></span>

<span data-ttu-id="0ad5e-115">Aktualizacje można sprawdzić w dowolnym momencie w ustawieniach.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="0ad5e-116">Aby wyświetlić dostępne aktualizacje i sprawdzić, czy są dostępne nowe aktualizacje:</span><span class="sxs-lookup"><span data-stu-id="0ad5e-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="0ad5e-117">Otwórz aplikację **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="0ad5e-118">Przejdź do **usługi Update & Security**  >  **Windows Update**.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="0ad5e-119">Wybierz pozycję **Sprawdź dostępność aktualizacji**.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-119">Select **Check for updates**.</span></span>

<span data-ttu-id="0ad5e-120">Jeśli aktualizacja jest dostępna, rozpocznie pobieranie nowej wersji.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="0ad5e-121">Po zakończeniu pobierania wybierz przycisk Uruchom ponownie **teraz,** aby wyzwolić instalację.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="0ad5e-122">Jeśli urządzenie jest poniżej 40% i nie jest podłączone do sieci, ponowne uruchomienie nie rozpocznie instalowania aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="0ad5e-123">Podczas instalowania aktualizacji na urządzeniach HoloLens będą wyświetlane obracające się koła zębate i wskaźnik postępu.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="0ad5e-124">Nie wyłączaj urządzenia HoloLens w tym czasie.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="0ad5e-125">Zostanie ona automatycznie ponownie uruchomiona po zakończeniu instalacji.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="0ad5e-126">Urządzenie HoloLens stosuje po jednej aktualizacji na raz.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="0ad5e-127">Jeśli urządzenie HoloLens ma więcej niż jedną wersję niż najnowsza, może być konieczne wielokrotne uruchomienie procesu aktualizacji, aby w pełni go zaktualizować.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version"></a><span data-ttu-id="0ad5e-128">Wstecz do poprzedniej wersji</span><span class="sxs-lookup"><span data-stu-id="0ad5e-128">Go back to a previous version</span></span>

<span data-ttu-id="0ad5e-129">W niektórych przypadkach może być konieczne powrót do poprzedniej wersji oprogramowania HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="0ad5e-130">Zalecane czynności to:</span><span class="sxs-lookup"><span data-stu-id="0ad5e-130">The recommended steps are:</span></span>

1. <span data-ttu-id="0ad5e-131">Skontaktuj się z pomocą techniczną, aby sprawdzić, czy może rozwiązać problem.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-131">Contact Support to see if they can fix your issue.</span></span>
    1. <span data-ttu-id="0ad5e-132">Upewnij **się, że włączono** **opcjonalną lub** pełną telemetrię — dzięki temu usterka będzie bardziej aktywna i łatwiejsza do zdiagnozowania przez inżynierów.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-132">Ensure that **Optional** or **Full** telemetry is enabled -  this makes your bug more actionable and easier for engineers to diagnose.</span></span>
    1. <span data-ttu-id="0ad5e-133">[Opinia o pliku](hololens-feedback.md) jest jak najbardziej opisowa.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-133">[File Feedback](hololens-feedback.md) being as descriptive as possible.</span></span> <span data-ttu-id="0ad5e-134">Zanotuj tytuł lub użyj funkcji udostępniania, aby udostępnić usterkę pomocy technicznej.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-134">Take note of the title or use the share feature so you can share your bug with Support.</span></span>
    1. <span data-ttu-id="0ad5e-135">Skontaktuj się [z pomocą techniczną.](https://aka.ms/hlsupport)</span><span class="sxs-lookup"><span data-stu-id="0ad5e-135">Contact [Support](https://aka.ms/hlsupport).</span></span> <span data-ttu-id="0ad5e-136">Jeśli problem należy rozwiązać, wracając do poprzedniej wersji, może dostarczyć urządzenie FFU do flashowania urządzenia.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-136">If your issue is one that needs to be solved by returning to a previous version, they can supply you the FFU to flash your device.</span></span>

1. <span data-ttu-id="0ad5e-137">Jeśli to nie zadziała, [zresetuj lub odwróć ukośnik urządzenia HoloLens 2 za pomocą narzędzia Advanced Recovery Companion](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="0ad5e-137">If that does not work, then [reset or reflash your HoloLens 2 with the Advanced Recovery Companion](hololens-recovery.md).</span></span>
    1. <span data-ttu-id="0ad5e-138">Na komputerze pobierz program [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) z Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-138">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
    1. <span data-ttu-id="0ad5e-139">Upewnij się, że nie masz żadnych telefonów ani urządzeń z systemem Windows podłączonych do komputera.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-139">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
    1. <span data-ttu-id="0ad5e-140">Wybierz wersję, w której chcesz flashować:</span><span class="sxs-lookup"><span data-stu-id="0ad5e-140">Choose which version you want to flash to:</span></span>
        1. <span data-ttu-id="0ad5e-141">Możesz pobrać [najnowszą wersję urządzenia HoloLens 2.](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="0ad5e-141">You can download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
        1. <span data-ttu-id="0ad5e-142">Można użyć domyślnej kompilacji hostów ARC.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-142">You can use the default build that ARC hosts.</span></span> <span data-ttu-id="0ad5e-143">(Jeśli wybierzesz tę opcję, pomiń następny krok).</span><span class="sxs-lookup"><span data-stu-id="0ad5e-143">(If you choose this option skip the next step.)</span></span>
        1. <span data-ttu-id="0ad5e-144">Możesz użyć dostarczonej pomocy technicznej kompilacji.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-144">You can use a build Support provided you with.</span></span>
    1. <span data-ttu-id="0ad5e-145">Po zakończeniu pobierania otwórz plik **Eksplorator plików**  >  **Pliki do pobrania.**</span><span class="sxs-lookup"><span data-stu-id="0ad5e-145">When you have finished these downloads, open **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="0ad5e-146">Kliknij prawym przyciskiem myszy właśnie pobrany folder, a następnie wybierz polecenie **Wyodrębnij wszystkie** wyodrębnij,  >   aby go rozpakować.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-146">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
    1. <span data-ttu-id="0ad5e-147">Podłącz urządzenie HoloLens do komputera za pomocą kabla USB-A do USB-C.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-147">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="0ad5e-148">(Nawet jeśli do łączenia urządzenia HoloLens używasz innych kabli, ten z nich działa najlepiej).</span><span class="sxs-lookup"><span data-stu-id="0ad5e-148">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
    1. <span data-ttu-id="0ad5e-149">Pomocnik odzyskiwania zaawansowanego automatycznie wykrywa urządzenie HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-149">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="0ad5e-150">Wybierz **kafelek Microsoft HoloLens** aplikacji.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-150">Select the **Microsoft HoloLens** tile.</span></span>
    1. <span data-ttu-id="0ad5e-151">Na następnym ekranie wybierz opcję **Ręczne** wybieranie pakietu, a następnie wybierz plik instalacyjny zawarty w folderze rozpakowany w kroku 4.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-151">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="0ad5e-152">(Poszukaj pliku z rozszerzeniem ffu).</span><span class="sxs-lookup"><span data-stu-id="0ad5e-152">(Look for a file with the .ffu extension.)</span></span>
    1. <span data-ttu-id="0ad5e-153">Wybierz **pozycję Zainstaluj oprogramowanie** i postępuj zgodnie z instrukcjami.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-153">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="0ad5e-154">Powrót do wcześniejszej wersji powoduje usunięcie osobistych plików i ustawień.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-154">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="0ad5e-155">Ponadto jeśli chcesz pozostać w aktualnie zainstalowanej wersji, możesz również ręcznie wstrzymać [aktualizacje.](hololens-updates.md#pause-updates-via-device)</span><span class="sxs-lookup"><span data-stu-id="0ad5e-155">Additionally, if you would like to stay on your currently installed release, you can also manually [pause updates](hololens-updates.md#pause-updates-via-device).</span></span> <span data-ttu-id="0ad5e-156">Pozwoli to zespołowi inżynierów na rozwiązanie problemu.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-156">This will give the Engineering Team time to fix the issue.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="0ad5e-157">Niejawny program testów systemu Windows na urządzeniach HoloLens</span><span class="sxs-lookup"><span data-stu-id="0ad5e-157">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="0ad5e-158">Chcesz zobaczyć najnowsze funkcje na urządzeniach HoloLens?</span><span class="sxs-lookup"><span data-stu-id="0ad5e-158">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="0ad5e-159">Jeśli tak, dołącz Niejawny program testów systemu Windows; Będziesz mieć dostęp do kompilacji oprogramowania holoLens w wersji zapoznawczej, zanim będą one dostępne publicznie.</span><span class="sxs-lookup"><span data-stu-id="0ad5e-159">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="0ad5e-160">[Pobierz niejawny tester systemu Windows zapoznawczą dla Microsoft HoloLens](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="0ad5e-160">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
