---
title: Instalowanie zlokalizowanych wersji urządzenia HoloLens
description: Dowiedz się, jak zainstalować zlokalizowane wersje urządzenia HoloLens (1. generacji), w tym chińskie i japońskie.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 74eb003aafd23218b90988abe113d35f1fc3035a
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378460"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a><span data-ttu-id="f15d8-103">Instalowanie zlokalizowanych wersji urządzenia HoloLens (1. generacji)</span><span class="sxs-lookup"><span data-stu-id="f15d8-103">Install localized versions of HoloLens (1st gen)</span></span>

<span data-ttu-id="f15d8-104">Aby przełączyć się do chińskiej lub japońskiej wersji urządzenia HoloLens, musisz użyć narzędzia Windows Device Recovery Tool (WDRT), aby pobrać kompilację dla języka na komputerze, a następnie zainstalować ją na urządzeniu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f15d8-104">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to use the Windows Device Recovery Tool (WDRT) to download the build for the language on a PC and then install it on your HoloLens.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f15d8-105">Zainstalowanie chińskich lub japońskich kompilacji urządzenia HoloLens przy użyciu narzędzia WDRT powoduje usunięcie z urządzenia HoloLens istniejących danych, takich jak pliki i ustawienia osobiste.</span><span class="sxs-lookup"><span data-stu-id="f15d8-105">Using WDRT to install the Chinese or Japanese builds of HoloLens deletes existing data, such as personal files and settings, from your HoloLens.</span></span> 

1. <span data-ttu-id="f15d8-106">Na komputerze pobierz i zainstaluj narzędzie [Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379)</span><span class="sxs-lookup"><span data-stu-id="f15d8-106">On your PC, download and install [the Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="f15d8-107">Pobierz pakiet dla języka, którego chcesz użyć na komputerze: [chiński uproszczony](https://aka.ms/hololensdownload-ch) lub [japoński.](https://aka.ms/hololensdownload-jp)</span><span class="sxs-lookup"><span data-stu-id="f15d8-107">Download the package for the language you want to your PC:  [Simplified Chinese](https://aka.ms/hololensdownload-ch) or [Japanese](https://aka.ms/hololensdownload-jp).</span></span>
1. <span data-ttu-id="f15d8-108">Po zakończeniu pobierania wybierz pozycję Pobierz **Eksplorator plików**  >  **pobrane.**</span><span class="sxs-lookup"><span data-stu-id="f15d8-108">When the download finishes, select **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="f15d8-109">Kliknij prawym przyciskiem myszy właśnie pobrany folder, a następnie wybierz polecenie **Wyodrębnij wszystkie** wyodrębnij,  >   aby go rozpakować.</span><span class="sxs-lookup"><span data-stu-id="f15d8-109">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="f15d8-110">Podłącz urządzenie HoloLens do komputera przy użyciu dostarczonego z nim kabla mikro USB.</span><span class="sxs-lookup"><span data-stu-id="f15d8-110">Connect your HoloLens to your PC using the micro-USB cable that it shipped with.</span></span> <span data-ttu-id="f15d8-111">(Nawet jeśli używasz innych kabli do podłączania urządzenia HoloLens, ten z nich działa najlepiej).</span><span class="sxs-lookup"><span data-stu-id="f15d8-111">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="f15d8-112">Po tym, jak narzędzie automatycznie wykryje urządzenie HoloLens, wybierz Microsoft HoloLens kafelka.</span><span class="sxs-lookup"><span data-stu-id="f15d8-112">After the tool automatically detects your HoloLens, select the Microsoft HoloLens tile.</span></span>
1. <span data-ttu-id="f15d8-113">Na następnym ekranie wybierz opcję **Ręczne** wybieranie pakietu i wybierz plik instalacyjny, który znajduje się w folderze rozpakowanym   w kroku 4.</span><span class="sxs-lookup"><span data-stu-id="f15d8-113">On the next screen, select **Manual package selection** and select the installation file that resides in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="f15d8-114">(Poszukaj pliku z rozszerzeniem ".ffu".</span><span class="sxs-lookup"><span data-stu-id="f15d8-114">(Look for a file that has the extension “.ffu”.)</span></span> 
1. <span data-ttu-id="f15d8-115">Wybierz **pozycję Zainstaluj oprogramowanie** i postępuj zgodnie z instrukcjami.</span><span class="sxs-lookup"><span data-stu-id="f15d8-115">Select **Install software** and follow the instructions.</span></span> 
1. <span data-ttu-id="f15d8-116">Po zainstalowaniu kompilacji zostanie automatycznie uruchomiony instalator urządzenia HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f15d8-116">After the build installs, HoloLens setup automatically starts.</span></span> <span data-ttu-id="f15d8-117">Umieść urządzenie i postępuj zgodnie z instrukcjami konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="f15d8-117">Put on the device and follow the setup directions.</span></span> 

<span data-ttu-id="f15d8-118">Po zakończeniu instalacji przejdź do strony Ustawienia Zaktualizuj & Security Niejawny program testów systemu Windows i sprawdź, czy skonfigurowano odbieranie najnowszych kompilacji  >    >  w wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="f15d8-118">When you’re done with setup, go to **Settings** > **Update & Security** > **Windows Insider Program**, and check that you’re configured to receive the latest preview builds.</span></span> <span data-ttu-id="f15d8-119">Podobnie jak w przypadku kompilacji w wersji zapoznawczej w języku angielskim, Niejawny program testów systemu Windows zapewnia, że chińskie i japońskie wersje urządzenia HoloLens są aktualne dzięki najnowszym kompilacjom w wersji zapoznawczej.</span><span class="sxs-lookup"><span data-stu-id="f15d8-119">Like the English preview builds, the Windows Insider Program keeps the Chinese and Japanese versions of HoloLens up-to-date with the latest preview builds.</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="f15d8-120">Nie można użyć aplikacji Ustawienia, aby zmienić język systemowy między językiem angielskim, japońskim i chińskim.</span><span class="sxs-lookup"><span data-stu-id="f15d8-120">You can’t use the Settings app to change the system language between English, Japanese, and Chinese.</span></span> <span data-ttu-id="f15d8-121">Flashowanie nowej kompilacji jest jedynym obsługiwanym sposobem zmiany języka systemu urządzenia.</span><span class="sxs-lookup"><span data-stu-id="f15d8-121">Flashing a new build is the only supported way to change the device system language.</span></span>
> - <span data-ttu-id="f15d8-122">Klawiatury Pinyin na ekranie można używać do wprowadzania tekstu w języku chińskim uproszczonym lub japońskim, ale używanie klawiatury sprzętowej Bluetooth do wpisywania uproszczonego tekstu w języku chińskim lub japońskim nie jest obecnie obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="f15d8-122">While you can use the on-screen Pinyin keyboard to enter Simplified Chinese or Japanese text, using a Bluetooth hardware keyboard to type Simplified Chinese or Japanese text is not supported at this time.</span></span>  <span data-ttu-id="f15d8-123">Jednak na chińskim lub japońskim urządzeniu HoloLens można nadal używać klawiatury Bluetooth do wpisywania w języku angielskim (aby przełączyć klawiaturę sprzętową do wpisywania w języku angielskim, naciśnij klawisz ~).</span><span class="sxs-lookup"><span data-stu-id="f15d8-123">However, on Chinese or Japanese HoloLens, you can continue to use a Bluetooth keyboard to type in English (to toggle a hardware keyboard to type in English, press the ~ key).</span></span>
