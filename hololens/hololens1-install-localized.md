---
title: Instalowanie zlokalizowanych wersji HoloLens
description: Dowiedz się, jak zainstalować zlokalizowane wersje programu HoloLens (1. generacji), w tym chińskie i japońskie.
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
ms.openlocfilehash: fe29e4ed611f86764f0db576b1a8794fa0ceec3047cadd26f502209faadea8b0
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661793"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>Instalowanie zlokalizowanych wersji HoloLens (1. generacja)

Aby przełączyć się do chińskiej lub japońskiej wersji programu HoloLens, należy pobrać kompilację dla języka na komputerze przy użyciu narzędzia Windows Device Recovery Tool (WDRT), a następnie zainstalować ją na komputerze HoloLens.

> [!IMPORTANT]
> Zainstalowanie kompilacji języka chińskiego lub japońskiego przy użyciu programu WDRT HoloLens usunięcie istniejących danych, takich jak pliki i ustawienia osobiste, z HoloLens. 

1. Na komputerze pobierz i zainstaluj narzędzie [Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379)
1. Pobierz pakiet dla języka, którego chcesz użyć na komputerze: [chiński uproszczony](https://aka.ms/hololensdownload-ch) lub [japoński.](https://aka.ms/hololensdownload-jp)
1. Po zakończeniu pobierania wybierz **pozycję** Eksplorator plików Pliki do  >  **pobrania.** Kliknij prawym przyciskiem myszy właśnie pobrany folder, a następnie wybierz polecenie **Wyodrębnij** wszystkie wyodrębnij,  >   aby go rozpakować.
1. Połączenie urządzenie HoloLens do komputera przy użyciu dostarczonego kabla mikro USB. (Nawet jeśli używasz innych kabli do łączenia urządzenia HoloLens, ten z nich działa najlepiej).
1. Po tym, jak narzędzie automatycznie wykryje HoloLens, wybierz kafelek Microsoft HoloLens aplikacji.
1. Na następnym ekranie wybierz opcję **Ręczne** wybieranie pakietu i wybierz plik instalacyjny, który znajduje się w folderze rozpakowanym   w kroku 4. (Poszukaj pliku z rozszerzeniem ".ffu". 
1. Wybierz **pozycję Zainstaluj oprogramowanie** i postępuj zgodnie z instrukcjami. 
1. Po zainstalowaniu kompilacji automatycznie HoloLens instalacji. Umieść urządzenie i postępuj zgodnie z instrukcjami konfiguracji. 

Po zakończeniu instalacji przejdź do usługi **Ustawienia** Update & Security Windows niejawny program testów i sprawdź, czy skonfigurowano odbieranie najnowszych kompilacji w wersji  >    >  zapoznawczej. Podobnie jak w przypadku kompilacji angielskiej wersji zapoznawczej, Windows niejawny program testów zapewnia, że wersje chińskie i japońskie HoloLens są aktualne dzięki najnowszym kompilacjom w wersji zapoznawczej.

> [!NOTE]
>  
> - Nie można używać aplikacji Ustawienia do zmiany języka systemowego na angielski, japoński i chiński. Flashowanie nowej kompilacji jest jedynym obsługiwanym sposobem zmiany języka systemu urządzenia.
> - Chociaż możesz użyć klawiatury Pinyin na ekranie, aby wprowadzić tekst w języku chińskim uproszczonym lub japońskim, używanie klawiatury sprzętowej Bluetooth do wpisywania tekstu w języku chińskim uproszczonym lub japońskim nie jest obecnie obsługiwane.  Jednak w języku chińskim lub japońskim HoloLens można nadal używać klawiatury Bluetooth do wpisywania w języku angielskim (aby przełączyć klawiaturę sprzętową do wpisywania w języku angielskim, naciśnij klawisz ~).
