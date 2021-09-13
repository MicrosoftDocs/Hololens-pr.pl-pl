---
title: Znajdowanie i zapisywanie plików na HoloLens
description: Dowiedz się, jak używać Eksplorator plików na HoloLens, aby otwierać i wyświetlać pliki na urządzeniu rzeczywistości mieszanej oraz zarządzać nimi.
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
ms.openlocfilehash: 18dc962b869dafaea9ff9c605eef51fcbb35bfb2
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033185"
---
# <a name="find-open-and-save-files-on-hololens"></a>Znajdowanie, otwieranie i zapisywanie plików na HoloLens

Pliki, które tworzysz na HoloLens, w tym zdjęcia i wideo, są zapisywane bezpośrednio HoloLens urządzeniu. Wyświetlaj je i zarządzaj nimi w taki sam sposób, jak w przypadku plików na Windows 10:

- Używanie aplikacji Eksplorator plików do uzyskiwania dostępu do folderów lokalnych.
- W magazynie aplikacji.
- W specjalnym folderze (takim jak biblioteka wideo lub music).
- Korzystanie z usługi magazynu, która zawiera aplikację i s wyboru plików (na przykład OneDrive).
- Korzystanie z komputera stacjonarnego podłączonego do HoloLens za pomocą kabla USB z obsługą protokołu MTP (Media Transfer Protocol).

## <a name="view-files-on-hololens-using-file-explorer"></a>Wyświetlanie plików na HoloLens użyciu Eksplorator plików

> Dotyczy wszystkich urządzeń HoloLens 2 i HoloLens (1. generacji) od Windows 10 kwietnia 2018 r. Update [(RS4)](/windows/mixed-reality/release-notes-april-2018)dla HoloLens.

Użyj Eksplorator plików na HoloLens, aby wyświetlać pliki na urządzeniu, w tym obiekty 3D, dokumenty i obrazy, oraz zarządzać nimi. Przejdź do **Wszystkie aplikacje**   >     >  **Eksplorator plików,** aby rozpocząć pracę.

> [!TIP]
> Jeśli na liście nie ma żadnych plików Eksplorator plików, wybierz pozycję **To urządzenie** w lewym górnym okienku.

Jeśli nie widzisz żadnych plików w Eksplorator plików, filtr "Ostatnie" może być aktywny (ikona zegara jest wyróżniona w okienku po lewej stronie). Aby rozwiązać ten problem, wybierz ikonę To **urządzenie** w okienku po lewej stronie (poniżej ikony zegara) lub otwórz menu i wybierz **pozycję To urządzenie.**

## <a name="find-and-view-your-photos-and-videos"></a>Znajdowanie i wyświetlanie zdjęć i filmów wideo

[Przechwytywanie rzeczywistości mieszanej](holographic-photos-and-videos.md) umożliwia tworzenie zdjęć i wideo rzeczywistości mieszanej na HoloLens.  Te zdjęcia i wideo są zapisywane w folderze Roll aparatu urządzenia.

Dostęp do zdjęć i filmów wideo HoloLens przez:

- uzyskiwanie dostępu do aplikacji Camera Roll bezpośrednio za [pośrednictwem aplikacji Zdjęcia.](holographic-photos-and-videos.md)
- przekazywanie zdjęć i wideo do magazynu w chmurze przez synchronizowanie zdjęć i wideo z OneDrive.
- za pomocą Przechwytywanie rzeczywistości mieszanej strony [Windows Portal urządzeń](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).

### <a name="photos-app"></a>Aplikacja Zdjęcia

Aplikacja Zdjęcia jest jedną z domyślnych aplikacji w menu **Start** i jest wbudowana w HoloLens. Dowiedz się więcej [o używaniu aplikacji Zdjęcia do wyświetlania zawartości.](holographic-photos-and-videos.md)

Możesz również zainstalować aplikację OneDrive [z](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) aplikacji Microsoft Store, aby synchronizować zdjęcia z innymi urządzeniami.

### <a name="onedrive-app"></a>OneDrive aplikacji

[OneDrive](https://onedrive.live.com/) umożliwia dostęp do zdjęć i filmów wideo oraz zarządzanie nimi za pomocą dowolnego urządzenia i dowolnego użytkownika. Aby uzyskać dostęp do zdjęć i wideo przechwyconych na HoloLens, pobierz aplikację OneDrive [z](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) aplikacji Microsoft Store na HoloLens. Po pobraniu otwórz aplikację OneDrive i wybierz pozycję **Przekaż** Ustawienia  >  **aparatem,** a następnie włącz opcję **Przekaż z aparatu.**

### <a name="connect-to-a-pc"></a>Połączenie na komputer

Jeśli na urządzeniu HoloLens Windows 10 jest uruchomiona aktualizacja z kwietnia 2018 r. lub nowszej aktualizacji z kwietnia [2018](/windows/mixed-reality/release-notes-april-2018) r., możesz podłączyć urządzenie HoloLens do komputera Windows 10 za pomocą kabla USB, aby przeglądać zdjęcia i filmy wideo na urządzeniu przy użyciu protokołu MTP (media transfer protocol). Upewnij się, że urządzenie jest odblokowane, aby przeglądać pliki, jeśli na urządzeniu jest ustawiony numer PIN lub hasło.  

Jeśli włączono funkcję [Windows Portal urządzeń](/windows/mixed-reality/using-the-windows-device-portal), można jej używać do przeglądania i pobierania zdjęć oraz filmów wideo przechowywanych na urządzeniu oraz zarządzania nimi.

## <a name="access-files-within-an-app"></a>Uzyskiwanie dostępu do plików w aplikacji

Jeśli aplikacja zapisuje pliki na urządzeniu, możesz użyć tej aplikacji, aby uzyskać do nich dostęp.

### <a name="requesting-files-from-another-app"></a>Żądanie plików z innej aplikacji

Aplikacja może zażądać zapisania pliku lub otwarcia pliku z innej aplikacji przy użyciu [s wyboru plików](/windows/mixed-reality/app-model#file-pickers).

### <a name="known-folders"></a>Znane foldery

HoloLens obsługuje wiele znanych [folderów,](/windows/mixed-reality/app-model#known-folders) do których aplikacje mogą żądać uprawnień dostępu.

## <a name="view-hololens-files-on-your-pc"></a>Wyświetlanie HoloLens plików na komputerze

Podobnie jak w przypadku innych urządzeń przenośnych, połącz HoloLens z komputerem stacjonarnym przy użyciu protokołu MTP (Media Transfer Protocol) i otwórz program Eksplorator plików na komputerze, aby uzyskać dostęp do bibliotek HoloLens w celu łatwego transferu.

Aby wyświetlić pliki HoloLens w Eksplorator plików na komputerze:

1. Zaloguj się do HoloLens, a następnie podłącz go do komputera przy użyciu kabla USB, który jest podłączony do HoloLens.

1. Wybierz **pozycję Otwórz urządzenie,** aby wyświetlić pliki Eksplorator plików lub otwórz Eksplorator plików na komputerze i przejdź do urządzenia.

Aby wyświetlić informacje o HoloLens, kliknij prawym przyciskiem myszy nazwę urządzenia w Eksplorator plików na komputerze, a następnie wybierz pozycję **Właściwości.**

> [!NOTE]
> HoloLens (1. generacji) nie obsługuje nawiązywania połączenia z zewnętrznymi dyskami twardymi lub kartami SD.

## <a name="sync-to-the-cloud"></a>Synchronizowanie z chmurą

Aby synchronizować zdjęcia i inne pliki z HoloLens z chmurą, zainstaluj i skonfiguruj OneDrive na HoloLens. Aby uzyskać OneDrive, wyszukaj go w Microsoft Store na HoloLens.

HoloLens kopii zapasowej plików i danych aplikacji, dlatego dobrym pomysłem jest zapisanie ważnych informacji w OneDrive. W ten sposób w przypadku zresetowania urządzenia lub odinstalowania aplikacji zostanie kopii zapasowej informacji.
