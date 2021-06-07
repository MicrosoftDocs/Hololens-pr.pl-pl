---
title: Aktualizowanie urządzenia HoloLens
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378348"
---
# <a name="update-hololens"></a><span data-ttu-id="727cd-104">Aktualizowanie urządzenia HoloLens</span><span class="sxs-lookup"><span data-stu-id="727cd-104">Update HoloLens</span></span>

<span data-ttu-id="727cd-105">Urządzenie HoloLens używa Windows Update, podobnie jak inne Windows 10 urządzenia.</span><span class="sxs-lookup"><span data-stu-id="727cd-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="727cd-106">Urządzenie HoloLens będzie automatycznie pobierać i instalować aktualizacje systemu za każdym razem, gdy jest podłączony do zasilania i połączony z Internetem, nawet jeśli jest w stanie wstrzymania.</span><span class="sxs-lookup"><span data-stu-id="727cd-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="727cd-107">Ten artykuł zawiera informacje na temat narzędzi dla urządzenia HoloLens:</span><span class="sxs-lookup"><span data-stu-id="727cd-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="727cd-108">wyświetlanie bieżącej wersji systemu operacyjnego (numer kompilacji)</span><span class="sxs-lookup"><span data-stu-id="727cd-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="727cd-109">sprawdzanie aktualizacji</span><span class="sxs-lookup"><span data-stu-id="727cd-109">checking for updates</span></span>
- <span data-ttu-id="727cd-110">ręczne aktualizowanie urządzenia HoloLens</span><span class="sxs-lookup"><span data-stu-id="727cd-110">manually updating HoloLens</span></span>
- <span data-ttu-id="727cd-111">wycofywanie do starszej aktualizacji</span><span class="sxs-lookup"><span data-stu-id="727cd-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="727cd-112">Sprawdź wersję systemu operacyjnego (numer kompilacji)</span><span class="sxs-lookup"><span data-stu-id="727cd-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="727cd-113">Numer wersji systemu (numer kompilacji) możesz sprawdzić, otwierając aplikację Ustawienia i wybierając pozycję System About **(Informacje o**  >  **systemie).**</span><span class="sxs-lookup"><span data-stu-id="727cd-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="727cd-114">Sprawdź aktualizacje i ręcznie je zaktualizuj</span><span class="sxs-lookup"><span data-stu-id="727cd-114">Check for updates and manually update</span></span>

<span data-ttu-id="727cd-115">Aktualizacje można sprawdzić w dowolnym momencie w ustawieniach.</span><span class="sxs-lookup"><span data-stu-id="727cd-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="727cd-116">Aby wyświetlić dostępne aktualizacje i sprawdzić, czy są dostępne nowe aktualizacje:</span><span class="sxs-lookup"><span data-stu-id="727cd-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="727cd-117">Otwórz aplikację **Ustawienia**.</span><span class="sxs-lookup"><span data-stu-id="727cd-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="727cd-118">Przejdź do **usługi Update & Security**  >  **Windows Update**.</span><span class="sxs-lookup"><span data-stu-id="727cd-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="727cd-119">Wybierz pozycję **Sprawdź dostępność aktualizacji**.</span><span class="sxs-lookup"><span data-stu-id="727cd-119">Select **Check for updates**.</span></span>

<span data-ttu-id="727cd-120">Jeśli aktualizacja jest dostępna, rozpocznie pobieranie nowej wersji.</span><span class="sxs-lookup"><span data-stu-id="727cd-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="727cd-121">Po zakończeniu pobierania wybierz przycisk Uruchom ponownie **teraz,** aby wyzwolić instalację.</span><span class="sxs-lookup"><span data-stu-id="727cd-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="727cd-122">Jeśli urządzenie jest poniżej 40% i nie jest podłączone do sieci, ponowne uruchomienie nie rozpocznie instalowania aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="727cd-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="727cd-123">Podczas instalowania aktualizacji na urządzeniach HoloLens będą wyświetlane obracające się koła zębate i wskaźnik postępu.</span><span class="sxs-lookup"><span data-stu-id="727cd-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="727cd-124">Nie wyłączaj urządzenia HoloLens w tym czasie.</span><span class="sxs-lookup"><span data-stu-id="727cd-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="727cd-125">Zostanie ona automatycznie ponownie uruchomiona po zakończeniu instalacji.</span><span class="sxs-lookup"><span data-stu-id="727cd-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="727cd-126">Urządzenie HoloLens stosuje po jednej aktualizacji na raz.</span><span class="sxs-lookup"><span data-stu-id="727cd-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="727cd-127">Jeśli urządzenie HoloLens ma więcej niż jedną wersję niż najnowsza, może być konieczne wielokrotne uruchomienie procesu aktualizacji, aby w pełni go zaktualizować.</span><span class="sxs-lookup"><span data-stu-id="727cd-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version---hololens-2"></a><span data-ttu-id="727cd-128">Wstecz do poprzedniej wersji — HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="727cd-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="727cd-129">W niektórych przypadkach może być konieczne powrót do poprzedniej wersji oprogramowania HoloLens.</span><span class="sxs-lookup"><span data-stu-id="727cd-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="727cd-130">Możesz to zrobić za pomocą narzędzia Advanced Recovery Companion, aby zresetować urządzenie HoloLens do starszej wersji.</span><span class="sxs-lookup"><span data-stu-id="727cd-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="727cd-131">Powrót do wcześniejszej wersji powoduje usunięcie osobistych plików i ustawień.</span><span class="sxs-lookup"><span data-stu-id="727cd-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="727cd-132">Aby wrócić do poprzedniej wersji urządzenia HoloLens 2, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="727cd-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="727cd-133">Upewnij się, że nie masz żadnych telefonów ani urządzeń z systemem Windows podłączonych do komputera.</span><span class="sxs-lookup"><span data-stu-id="727cd-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="727cd-134">Na komputerze pobierz program [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) z Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="727cd-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="727cd-135">Pobierz [najnowszą wersję urządzenia HoloLens 2.](https://aka.ms/hololens2download)</span><span class="sxs-lookup"><span data-stu-id="727cd-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="727cd-136">Po zakończeniu pobierania otwórz Eksploratora plików Pliki  >  **do pobrania.**</span><span class="sxs-lookup"><span data-stu-id="727cd-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="727cd-137">Kliknij prawym przyciskiem myszy właśnie pobrany folder, a następnie wybierz polecenie **Wyodrębnij wszystkie** wyodrębnij,  >   aby go rozpakować.</span><span class="sxs-lookup"><span data-stu-id="727cd-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="727cd-138">Podłącz urządzenie HoloLens do komputera za pomocą kabla USB-A do USB-C.</span><span class="sxs-lookup"><span data-stu-id="727cd-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="727cd-139">(Nawet jeśli do łączenia urządzenia HoloLens używasz innych kabli, ten z nich działa najlepiej).</span><span class="sxs-lookup"><span data-stu-id="727cd-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="727cd-140">Pomocnik odzyskiwania zaawansowanego automatycznie wykrywa urządzenie HoloLens.</span><span class="sxs-lookup"><span data-stu-id="727cd-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="727cd-141">Wybierz **kafelek Microsoft HoloLens** aplikacji.</span><span class="sxs-lookup"><span data-stu-id="727cd-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="727cd-142">Na następnym ekranie wybierz opcję **Ręczne** wybieranie pakietu, a następnie wybierz plik instalacyjny zawarty w folderze rozpakowany w kroku 4.</span><span class="sxs-lookup"><span data-stu-id="727cd-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="727cd-143">(Poszukaj pliku z rozszerzeniem ffu).</span><span class="sxs-lookup"><span data-stu-id="727cd-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="727cd-144">Wybierz **pozycję Zainstaluj oprogramowanie** i postępuj zgodnie z instrukcjami.</span><span class="sxs-lookup"><span data-stu-id="727cd-144">Select **Install software**, and follow the instructions.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="727cd-145">Wstecz do poprzedniej wersji — HoloLens (1. generacja)</span><span class="sxs-lookup"><span data-stu-id="727cd-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="727cd-146">W niektórych przypadkach może być konieczne powrót do poprzedniej wersji oprogramowania HoloLens.</span><span class="sxs-lookup"><span data-stu-id="727cd-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="727cd-147">Możesz to zrobić przy użyciu narzędzia do odzyskiwania urządzeń z systemem Windows, aby zresetować urządzenie HoloLens do starszej wersji.</span><span class="sxs-lookup"><span data-stu-id="727cd-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="727cd-148">Powrót do wcześniejszej wersji powoduje usunięcie osobistych plików i ustawień.</span><span class="sxs-lookup"><span data-stu-id="727cd-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="727cd-149">Aby wrócić do poprzedniej wersji urządzenia HoloLens 1, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="727cd-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="727cd-150">Upewnij się, że nie masz żadnych telefonów ani urządzeń z systemem Windows podłączonych do komputera.</span><span class="sxs-lookup"><span data-stu-id="727cd-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="727cd-151">Na komputerze pobierz narzędzie [Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379)</span><span class="sxs-lookup"><span data-stu-id="727cd-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="727cd-152">Pobierz pakiet [odzyskiwania rocznicowej aktualizacji urządzenia HoloLens.](https://aka.ms/hololensrecovery)</span><span class="sxs-lookup"><span data-stu-id="727cd-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="727cd-153">Po zakończeniu pobierania otwórz **Eksploratora plików**—  >  **pliki do pobrania.**</span><span class="sxs-lookup"><span data-stu-id="727cd-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="727cd-154">Kliknij prawym przyciskiem myszy właśnie pobrany folder, a następnie wybierz polecenie **Wyodrębnij wszystkie** wyodrębnij,  >   aby go rozpakować.</span><span class="sxs-lookup"><span data-stu-id="727cd-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="727cd-155">Podłącz urządzenie HoloLens do komputera przy użyciu kabla mikro USB, który został do niego podłączony.</span><span class="sxs-lookup"><span data-stu-id="727cd-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="727cd-156">(Nawet jeśli do łączenia urządzenia HoloLens używasz innych kabli, ten z nich działa najlepiej).</span><span class="sxs-lookup"><span data-stu-id="727cd-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="727cd-157">Funkcja WDRT automatycznie wykryje urządzenie HoloLens.</span><span class="sxs-lookup"><span data-stu-id="727cd-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="727cd-158">Wybierz **kafelek Microsoft HoloLens** aplikacji.</span><span class="sxs-lookup"><span data-stu-id="727cd-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="727cd-159">Na następnym ekranie wybierz opcję **Ręczne wybieranie** pakietu i wybierz plik instalacyjny zawarty w folderze rozpakowany w kroku 4.</span><span class="sxs-lookup"><span data-stu-id="727cd-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="727cd-160">(Poszukaj pliku z rozszerzeniem ffu).</span><span class="sxs-lookup"><span data-stu-id="727cd-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="727cd-161">Wybierz **pozycję Zainstaluj oprogramowanie** i postępuj zgodnie z instrukcjami.</span><span class="sxs-lookup"><span data-stu-id="727cd-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="727cd-162">Jeśli WDRT nie wykryje urządzenia HoloLens, spróbuj ponownie uruchomić komputer.</span><span class="sxs-lookup"><span data-stu-id="727cd-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="727cd-163">Jeśli to nie zadziała, wybierz pozycję **Moje urządzenie** nie zostało wykryte, wybierz pozycję **Microsoft HoloLens**, a następnie postępuj zgodnie z instrukcjami.</span><span class="sxs-lookup"><span data-stu-id="727cd-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="727cd-164">Niejawny program testów systemu Windows na urządzeniach HoloLens</span><span class="sxs-lookup"><span data-stu-id="727cd-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="727cd-165">Chcesz zobaczyć najnowsze funkcje na urządzeniach HoloLens?</span><span class="sxs-lookup"><span data-stu-id="727cd-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="727cd-166">Jeśli tak, dołącz do Niejawny program testów systemu Windows; Będziesz mieć dostęp do kompilacji oprogramowania holoLens w wersji zapoznawczej, zanim będą one dostępne publicznie.</span><span class="sxs-lookup"><span data-stu-id="727cd-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="727cd-167">[Pobierz niejawny tester systemu Windows zapoznawczą dla Microsoft HoloLens](hololens-insider.md).</span><span class="sxs-lookup"><span data-stu-id="727cd-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
