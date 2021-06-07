---
title: Znajdowanie i zapisywanie plików na urządzeniach HoloLens
description: Dowiedz się, jak używać Eksplorator plików urządzeniu HoloLens do otwierania i wyświetlania plików na urządzeniu rzeczywistości mieszanej oraz zarządzania nimi.
keywords: how-to, file picker, files, photos, videos, pictures, OneDrive, storage, file explorer, hololens
ms.assetid: 77d2e357-f65f-43c8-b62f-6cd9bf37070a
author: mattzmsft
ms.author: mazeller
manager: v-miegge
ms.reviewer: jarrettrenshaw
ms.date: 12/30/2019
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2d979b2cffd20589ddef7f11db5c7206eaea23cb
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378263"
---
# <a name="find-open-and-save-files-on-hololens"></a><span data-ttu-id="36f64-104">Znajdowanie, otwieranie i zapisywanie plików na urządzeniach HoloLens</span><span class="sxs-lookup"><span data-stu-id="36f64-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="36f64-105">Pliki, które tworzysz na urządzeniu HoloLens, w tym zdjęcia i wideo, są zapisywane bezpośrednio na urządzeniu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="36f64-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="36f64-106">Wyświetlaj je i zarządzaj nimi w taki sam sposób, w jaki zarządzasz plikami na Windows 10:</span><span class="sxs-lookup"><span data-stu-id="36f64-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="36f64-107">Używanie aplikacji Eksplorator plików do uzyskiwania dostępu do folderów lokalnych.</span><span class="sxs-lookup"><span data-stu-id="36f64-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="36f64-108">W magazynie aplikacji.</span><span class="sxs-lookup"><span data-stu-id="36f64-108">Within an app's storage.</span></span>
- <span data-ttu-id="36f64-109">W specjalnym folderze (takim jak biblioteka wideo lub music).</span><span class="sxs-lookup"><span data-stu-id="36f64-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="36f64-110">Korzystanie z usługi magazynu, która zawiera aplikację i s wyboru plików (na przykład OneDrive).</span><span class="sxs-lookup"><span data-stu-id="36f64-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="36f64-111">Korzystanie z komputera stacjonarnego podłączonego do urządzenia HoloLens za pomocą kabla USB z obsługą protokołu MTP (Media Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="36f64-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <a name="view-files-on-hololens-using-file-explorer"></a><span data-ttu-id="36f64-112">Wyświetlanie plików na urządzeniach HoloLens przy użyciu Eksplorator plików</span><span class="sxs-lookup"><span data-stu-id="36f64-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="36f64-113">Dotyczy wszystkich urządzeń HoloLens 2 i HoloLens (1. generacji) od [Aktualizacja systemu Windows 10 z kwietnia 2018 (RS4) dla urządzenia HoloLens.](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)</span><span class="sxs-lookup"><span data-stu-id="36f64-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="36f64-114">Użyj Eksplorator plików urządzeniu HoloLens, aby wyświetlać pliki na urządzeniu, w tym obiekty 3D, dokumenty i obrazy, oraz zarządzać nimi.</span><span class="sxs-lookup"><span data-stu-id="36f64-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="36f64-115">Przejdź do **Wszystkie aplikacje**   >     >  **Eksplorator plików,** aby rozpocząć pracę.</span><span class="sxs-lookup"><span data-stu-id="36f64-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="36f64-116">Jeśli na liście nie ma żadnych plików Eksplorator plików, wybierz pozycję **To urządzenie** w lewym górnym okienku.</span><span class="sxs-lookup"><span data-stu-id="36f64-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="36f64-117">Jeśli nie widzisz żadnych plików w Eksplorator plików, filtr "Ostatnie" może być aktywny (ikona zegara jest wyróżniona w okienku po lewej stronie).</span><span class="sxs-lookup"><span data-stu-id="36f64-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="36f64-118">Aby rozwiązać ten problem, wybierz ikonę To **urządzenie** w okienku po lewej stronie (poniżej ikony zegara) lub otwórz menu i wybierz **pozycję To urządzenie.**</span><span class="sxs-lookup"><span data-stu-id="36f64-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <a name="find-and-view-your-photos-and-videos"></a><span data-ttu-id="36f64-119">Znajdowanie i wyświetlanie zdjęć i filmów wideo</span><span class="sxs-lookup"><span data-stu-id="36f64-119">Find and view your photos and videos</span></span>

<span data-ttu-id="36f64-120">[Funkcja przechwytywania rzeczywistości mieszanej](holographic-photos-and-videos.md) umożliwia tworzenie zdjęć i filmów wideo rzeczywistości mieszanej na urządzeniach HoloLens.</span><span class="sxs-lookup"><span data-stu-id="36f64-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="36f64-121">Te zdjęcia i wideo są zapisywane w folderze Roll aparatu urządzenia.</span><span class="sxs-lookup"><span data-stu-id="36f64-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="36f64-122">Dostęp do zdjęć i filmów wideo na urządzeniach HoloLens można uzyskać, korzystając z:</span><span class="sxs-lookup"><span data-stu-id="36f64-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="36f64-123">uzyskiwanie dostępu do aplikacji Camera Roll bezpośrednio za [pośrednictwem aplikacji Zdjęcia.](holographic-photos-and-videos.md)</span><span class="sxs-lookup"><span data-stu-id="36f64-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="36f64-124">przekazywanie zdjęć i wideo do magazynu w chmurze przez synchronizowanie zdjęć i wideo do usługi OneDrive.</span><span class="sxs-lookup"><span data-stu-id="36f64-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="36f64-125">za pomocą Przechwytywanie rzeczywistości mieszanej strony [Portal urządzeń z systemem Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span><span class="sxs-lookup"><span data-stu-id="36f64-125">using the Mixed Reality Capture page of the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <a name="photos-app"></a><span data-ttu-id="36f64-126">Aplikacja Zdjęcia</span><span class="sxs-lookup"><span data-stu-id="36f64-126">Photos app</span></span>

<span data-ttu-id="36f64-127">Aplikacja Zdjęcia jest jedną z domyślnych aplikacji w menu **Start** i jest wbudowana w urządzenie HoloLens.</span><span class="sxs-lookup"><span data-stu-id="36f64-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="36f64-128">Dowiedz się więcej [o używaniu aplikacji Zdjęcia do wyświetlania zawartości.](holographic-photos-and-videos.md)</span><span class="sxs-lookup"><span data-stu-id="36f64-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="36f64-129">Możesz również zainstalować aplikację [OneDrive z](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) aplikacji Microsoft Store, aby synchronizować zdjęcia z innymi urządzeniami.</span><span class="sxs-lookup"><span data-stu-id="36f64-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <a name="onedrive-app"></a><span data-ttu-id="36f64-130">Aplikacja OneDrive</span><span class="sxs-lookup"><span data-stu-id="36f64-130">OneDrive app</span></span>

<span data-ttu-id="36f64-131">[Aplikacja OneDrive](https://onedrive.live.com/) umożliwia dostęp do zdjęć i filmów wideo oraz zarządzanie nimi za pomocą dowolnego urządzenia i dowolnego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="36f64-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="36f64-132">Aby uzyskać dostęp do zdjęć i wideo przechwyconych na urządzeniach HoloLens, pobierz aplikację [OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) z aplikacji Microsoft Store urządzenia HoloLens.</span><span class="sxs-lookup"><span data-stu-id="36f64-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="36f64-133">Po pobraniu otwórz aplikację OneDrive i wybierz pozycję **Ustawienia**  >  **Przekaż** aparat, a następnie włącz pozycję **Przekaż za pomocą aparatu.**</span><span class="sxs-lookup"><span data-stu-id="36f64-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <a name="connect-to-a-pc"></a><span data-ttu-id="36f64-134">Nawiązywanie połączenia z komputerem</span><span class="sxs-lookup"><span data-stu-id="36f64-134">Connect to a PC</span></span>

<span data-ttu-id="36f64-135">Jeśli na urządzeniu HoloLen Windows 10 s jest uruchomiona aktualizacja z kwietnia [2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) r. lub nowszej wersji, możesz podłączyć urządzenie HoloLens do komputera Windows 10 za pomocą kabla USB, aby przeglądać zdjęcia i filmy wideo na urządzeniu przy użyciu protokołu MTP (media transfer protocol).</span><span class="sxs-lookup"><span data-stu-id="36f64-135">If your HoloLens is running the [Windows 10 April 2018 update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="36f64-136">Upewnij się, że urządzenie jest odblokowane, aby przeglądać pliki, jeśli na urządzeniu jest ustawiony numer PIN lub hasło.</span><span class="sxs-lookup"><span data-stu-id="36f64-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="36f64-137">Jeśli włączono funkcję [Portal urządzeń z systemem Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), można jej używać do przeglądania i pobierania zdjęć oraz filmów wideo przechowywanych na urządzeniu oraz zarządzania nimi.</span><span class="sxs-lookup"><span data-stu-id="36f64-137">If you have enabled the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <a name="access-files-within-an-app"></a><span data-ttu-id="36f64-138">Uzyskiwanie dostępu do plików w aplikacji</span><span class="sxs-lookup"><span data-stu-id="36f64-138">Access files within an app</span></span>

<span data-ttu-id="36f64-139">Jeśli aplikacja zapisuje pliki na urządzeniu, możesz użyć tej aplikacji, aby uzyskać do nich dostęp.</span><span class="sxs-lookup"><span data-stu-id="36f64-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <a name="requesting-files-from-another-app"></a><span data-ttu-id="36f64-140">Żądanie plików z innej aplikacji</span><span class="sxs-lookup"><span data-stu-id="36f64-140">Requesting files from another app</span></span>

<span data-ttu-id="36f64-141">Aplikacja może zażądać zapisania pliku lub otwarcia pliku z innej aplikacji przy użyciu [s wyboru plików](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span><span class="sxs-lookup"><span data-stu-id="36f64-141">An application can request to save a file or open a file from another app by using [file pickers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span></span>

### <a name="known-folders"></a><span data-ttu-id="36f64-142">Znane foldery</span><span class="sxs-lookup"><span data-stu-id="36f64-142">Known folders</span></span>

<span data-ttu-id="36f64-143">Urządzenie HoloLens obsługuje wiele znanych [folderów,](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) do których aplikacje mogą żądać uprawnień dostępu.</span><span class="sxs-lookup"><span data-stu-id="36f64-143">HoloLens supports a number of [known folders](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <a name="view-hololens-files-on-your-pc"></a><span data-ttu-id="36f64-144">Wyświetlanie plików urządzenia HoloLens na komputerze</span><span class="sxs-lookup"><span data-stu-id="36f64-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="36f64-145">Podobnie jak w przypadku innych urządzeń przenośnych, podłącz urządzenie HoloLens do komputera stacjonarnego przy użyciu protokołu MTP (Media Transfer Protocol) i otwórz aplikację Eksplorator plików na komputerze, aby uzyskać dostęp do bibliotek holoLens w celu łatwego transferu.</span><span class="sxs-lookup"><span data-stu-id="36f64-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="36f64-146">Aby wyświetlić pliki urządzenia HoloLens w Eksplorator plików na komputerze:</span><span class="sxs-lookup"><span data-stu-id="36f64-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="36f64-147">Zaloguj się do urządzenia HoloLens, a następnie podłącz go do komputera za pomocą kabla USB, który jest podłączony do urządzenia HoloLens.</span><span class="sxs-lookup"><span data-stu-id="36f64-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="36f64-148">Wybierz **pozycję Otwórz urządzenie,** aby wyświetlić pliki Eksplorator plików , lub otwórz Eksplorator plików na komputerze i przejdź do urządzenia.</span><span class="sxs-lookup"><span data-stu-id="36f64-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="36f64-149">Aby wyświetlić informacje o urządzeniu HoloLens, kliknij prawym przyciskiem myszy nazwę urządzenia Eksplorator plików komputerze, a następnie wybierz pozycję **Właściwości.**</span><span class="sxs-lookup"><span data-stu-id="36f64-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="36f64-150">Urządzenie HoloLens (1. generacji) nie obsługuje nawiązywania połączenia z zewnętrznymi dyskami twardymi ani kartami SD.</span><span class="sxs-lookup"><span data-stu-id="36f64-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <a name="sync-to-the-cloud"></a><span data-ttu-id="36f64-151">Synchronizowanie z chmurą</span><span class="sxs-lookup"><span data-stu-id="36f64-151">Sync to the cloud</span></span>

<span data-ttu-id="36f64-152">Aby zsynchronizować zdjęcia i inne pliki z urządzenia HoloLens z chmurą, zainstaluj i skonfiguruj usługę OneDrive na urządzeniach HoloLens.</span><span class="sxs-lookup"><span data-stu-id="36f64-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="36f64-153">Aby uzyskać usługę OneDrive, wyszukaj ją w Microsoft Store na urządzeniach HoloLens.</span><span class="sxs-lookup"><span data-stu-id="36f64-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="36f64-154">Urządzenie HoloLens nie zapisuje kopii zapasowej plików i danych aplikacji, dlatego dobrym pomysłem jest zapisanie ważnych informacji w usłudze OneDrive.</span><span class="sxs-lookup"><span data-stu-id="36f64-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="36f64-155">W ten sposób w przypadku zresetowania urządzenia lub odinstalowania aplikacji zostanie kopii zapasowej informacji.</span><span class="sxs-lookup"><span data-stu-id="36f64-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
