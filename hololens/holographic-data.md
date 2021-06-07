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
# <a name="find-open-and-save-files-on-hololens"></a>Znajdowanie, otwieranie i zapisywanie plików na urządzeniach HoloLens

Pliki, które tworzysz na urządzeniu HoloLens, w tym zdjęcia i wideo, są zapisywane bezpośrednio na urządzeniu HoloLens. Wyświetlaj je i zarządzaj nimi w taki sam sposób, w jaki zarządzasz plikami na Windows 10:

- Używanie aplikacji Eksplorator plików do uzyskiwania dostępu do folderów lokalnych.
- W magazynie aplikacji.
- W specjalnym folderze (takim jak biblioteka wideo lub music).
- Korzystanie z usługi magazynu, która zawiera aplikację i s wyboru plików (na przykład OneDrive).
- Korzystanie z komputera stacjonarnego podłączonego do urządzenia HoloLens za pomocą kabla USB z obsługą protokołu MTP (Media Transfer Protocol).

## <a name="view-files-on-hololens-using-file-explorer"></a>Wyświetlanie plików na urządzeniach HoloLens przy użyciu Eksplorator plików

> Dotyczy wszystkich urządzeń HoloLens 2 i HoloLens (1. generacji) od [Aktualizacja systemu Windows 10 z kwietnia 2018 (RS4) dla urządzenia HoloLens.](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)

Użyj Eksplorator plików urządzeniu HoloLens, aby wyświetlać pliki na urządzeniu, w tym obiekty 3D, dokumenty i obrazy, oraz zarządzać nimi. Przejdź do **Wszystkie aplikacje**   >     >  **Eksplorator plików,** aby rozpocząć pracę.

> [!TIP]
> Jeśli na liście nie ma żadnych plików Eksplorator plików, wybierz pozycję **To urządzenie** w lewym górnym okienku.

Jeśli nie widzisz żadnych plików w Eksplorator plików, filtr "Ostatnie" może być aktywny (ikona zegara jest wyróżniona w okienku po lewej stronie). Aby rozwiązać ten problem, wybierz ikonę To **urządzenie** w okienku po lewej stronie (poniżej ikony zegara) lub otwórz menu i wybierz **pozycję To urządzenie.**

## <a name="find-and-view-your-photos-and-videos"></a>Znajdowanie i wyświetlanie zdjęć i filmów wideo

[Funkcja przechwytywania rzeczywistości mieszanej](holographic-photos-and-videos.md) umożliwia tworzenie zdjęć i filmów wideo rzeczywistości mieszanej na urządzeniach HoloLens.  Te zdjęcia i wideo są zapisywane w folderze Roll aparatu urządzenia.

Dostęp do zdjęć i filmów wideo na urządzeniach HoloLens można uzyskać, korzystając z:

- uzyskiwanie dostępu do aplikacji Camera Roll bezpośrednio za [pośrednictwem aplikacji Zdjęcia.](holographic-photos-and-videos.md)
- przekazywanie zdjęć i wideo do magazynu w chmurze przez synchronizowanie zdjęć i wideo do usługi OneDrive.
- za pomocą Przechwytywanie rzeczywistości mieszanej strony [Portal urządzeń z systemem Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).

### <a name="photos-app"></a>Aplikacja Zdjęcia

Aplikacja Zdjęcia jest jedną z domyślnych aplikacji w menu **Start** i jest wbudowana w urządzenie HoloLens. Dowiedz się więcej [o używaniu aplikacji Zdjęcia do wyświetlania zawartości.](holographic-photos-and-videos.md)

Możesz również zainstalować aplikację [OneDrive z](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) aplikacji Microsoft Store, aby synchronizować zdjęcia z innymi urządzeniami.

### <a name="onedrive-app"></a>Aplikacja OneDrive

[Aplikacja OneDrive](https://onedrive.live.com/) umożliwia dostęp do zdjęć i filmów wideo oraz zarządzanie nimi za pomocą dowolnego urządzenia i dowolnego użytkownika. Aby uzyskać dostęp do zdjęć i wideo przechwyconych na urządzeniach HoloLens, pobierz aplikację [OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) z aplikacji Microsoft Store urządzenia HoloLens. Po pobraniu otwórz aplikację OneDrive i wybierz pozycję **Ustawienia**  >  **Przekaż** aparat, a następnie włącz pozycję **Przekaż za pomocą aparatu.**

### <a name="connect-to-a-pc"></a>Nawiązywanie połączenia z komputerem

Jeśli na urządzeniu HoloLen Windows 10 s jest uruchomiona aktualizacja z kwietnia [2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) r. lub nowszej wersji, możesz podłączyć urządzenie HoloLens do komputera Windows 10 za pomocą kabla USB, aby przeglądać zdjęcia i filmy wideo na urządzeniu przy użyciu protokołu MTP (media transfer protocol). Upewnij się, że urządzenie jest odblokowane, aby przeglądać pliki, jeśli na urządzeniu jest ustawiony numer PIN lub hasło.  

Jeśli włączono funkcję [Portal urządzeń z systemem Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), można jej używać do przeglądania i pobierania zdjęć oraz filmów wideo przechowywanych na urządzeniu oraz zarządzania nimi.

## <a name="access-files-within-an-app"></a>Uzyskiwanie dostępu do plików w aplikacji

Jeśli aplikacja zapisuje pliki na urządzeniu, możesz użyć tej aplikacji, aby uzyskać do nich dostęp.

### <a name="requesting-files-from-another-app"></a>Żądanie plików z innej aplikacji

Aplikacja może zażądać zapisania pliku lub otwarcia pliku z innej aplikacji przy użyciu [s wyboru plików](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).

### <a name="known-folders"></a>Znane foldery

Urządzenie HoloLens obsługuje wiele znanych [folderów,](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) do których aplikacje mogą żądać uprawnień dostępu.

## <a name="view-hololens-files-on-your-pc"></a>Wyświetlanie plików urządzenia HoloLens na komputerze

Podobnie jak w przypadku innych urządzeń przenośnych, podłącz urządzenie HoloLens do komputera stacjonarnego przy użyciu protokołu MTP (Media Transfer Protocol) i otwórz aplikację Eksplorator plików na komputerze, aby uzyskać dostęp do bibliotek holoLens w celu łatwego transferu.

Aby wyświetlić pliki urządzenia HoloLens w Eksplorator plików na komputerze:

1. Zaloguj się do urządzenia HoloLens, a następnie podłącz go do komputera za pomocą kabla USB, który jest podłączony do urządzenia HoloLens.

1. Wybierz **pozycję Otwórz urządzenie,** aby wyświetlić pliki Eksplorator plików , lub otwórz Eksplorator plików na komputerze i przejdź do urządzenia.

Aby wyświetlić informacje o urządzeniu HoloLens, kliknij prawym przyciskiem myszy nazwę urządzenia Eksplorator plików komputerze, a następnie wybierz pozycję **Właściwości.**

> [!NOTE]
> Urządzenie HoloLens (1. generacji) nie obsługuje nawiązywania połączenia z zewnętrznymi dyskami twardymi ani kartami SD.

## <a name="sync-to-the-cloud"></a>Synchronizowanie z chmurą

Aby zsynchronizować zdjęcia i inne pliki z urządzenia HoloLens z chmurą, zainstaluj i skonfiguruj usługę OneDrive na urządzeniach HoloLens. Aby uzyskać usługę OneDrive, wyszukaj ją w Microsoft Store na urządzeniach HoloLens.

Urządzenie HoloLens nie zapisuje kopii zapasowej plików i danych aplikacji, dlatego dobrym pomysłem jest zapisanie ważnych informacji w usłudze OneDrive. W ten sposób w przypadku zresetowania urządzenia lub odinstalowania aplikacji zostanie kopii zapasowej informacji.
