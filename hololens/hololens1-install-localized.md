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
# <a name="install-localized-versions-of-hololens-1st-gen"></a>Instalowanie zlokalizowanych wersji urządzenia HoloLens (1. generacji)

Aby przełączyć się do chińskiej lub japońskiej wersji urządzenia HoloLens, musisz użyć narzędzia Windows Device Recovery Tool (WDRT), aby pobrać kompilację dla języka na komputerze, a następnie zainstalować ją na urządzeniu HoloLens.

> [!IMPORTANT]
> Zainstalowanie chińskich lub japońskich kompilacji urządzenia HoloLens przy użyciu narzędzia WDRT powoduje usunięcie z urządzenia HoloLens istniejących danych, takich jak pliki i ustawienia osobiste. 

1. Na komputerze pobierz i zainstaluj narzędzie [Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379)
1. Pobierz pakiet dla języka, którego chcesz użyć na komputerze: [chiński uproszczony](https://aka.ms/hololensdownload-ch) lub [japoński.](https://aka.ms/hololensdownload-jp)
1. Po zakończeniu pobierania wybierz pozycję Pobierz **Eksplorator plików**  >  **pobrane.** Kliknij prawym przyciskiem myszy właśnie pobrany folder, a następnie wybierz polecenie **Wyodrębnij wszystkie** wyodrębnij,  >   aby go rozpakować.
1. Podłącz urządzenie HoloLens do komputera przy użyciu dostarczonego z nim kabla mikro USB. (Nawet jeśli używasz innych kabli do podłączania urządzenia HoloLens, ten z nich działa najlepiej).
1. Po tym, jak narzędzie automatycznie wykryje urządzenie HoloLens, wybierz Microsoft HoloLens kafelka.
1. Na następnym ekranie wybierz opcję **Ręczne** wybieranie pakietu i wybierz plik instalacyjny, który znajduje się w folderze rozpakowanym   w kroku 4. (Poszukaj pliku z rozszerzeniem ".ffu". 
1. Wybierz **pozycję Zainstaluj oprogramowanie** i postępuj zgodnie z instrukcjami. 
1. Po zainstalowaniu kompilacji zostanie automatycznie uruchomiony instalator urządzenia HoloLens. Umieść urządzenie i postępuj zgodnie z instrukcjami konfiguracji. 

Po zakończeniu instalacji przejdź do strony Ustawienia Zaktualizuj & Security Niejawny program testów systemu Windows i sprawdź, czy skonfigurowano odbieranie najnowszych kompilacji  >    >  w wersji zapoznawczej. Podobnie jak w przypadku kompilacji w wersji zapoznawczej w języku angielskim, Niejawny program testów systemu Windows zapewnia, że chińskie i japońskie wersje urządzenia HoloLens są aktualne dzięki najnowszym kompilacjom w wersji zapoznawczej.

> [!NOTE]
>  
> - Nie można użyć aplikacji Ustawienia, aby zmienić język systemowy między językiem angielskim, japońskim i chińskim. Flashowanie nowej kompilacji jest jedynym obsługiwanym sposobem zmiany języka systemu urządzenia.
> - Klawiatury Pinyin na ekranie można używać do wprowadzania tekstu w języku chińskim uproszczonym lub japońskim, ale używanie klawiatury sprzętowej Bluetooth do wpisywania uproszczonego tekstu w języku chińskim lub japońskim nie jest obecnie obsługiwane.  Jednak na chińskim lub japońskim urządzeniu HoloLens można nadal używać klawiatury Bluetooth do wpisywania w języku angielskim (aby przełączyć klawiaturę sprzętową do wpisywania w języku angielskim, naciśnij klawisz ~).
