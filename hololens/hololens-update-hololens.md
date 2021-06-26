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
# <a name="update-hololens-2"></a>Aktualizowanie urządzenia HoloLens 2

Urządzenie HoloLens używa Windows Update, podobnie jak inne Windows 10 urządzenia. Urządzenie HoloLens będzie automatycznie pobierać i instalować aktualizacje systemu za każdym razem, gdy jest podłączony do zasilania i połączony z Internetem, nawet jeśli jest w stanie wstrzymania.

Ten artykuł zawiera informacje na temat narzędzi dla urządzenia HoloLens:

- wyświetlanie bieżącej wersji systemu operacyjnego (numer kompilacji)
- sprawdzanie aktualizacji
- ręczne aktualizowanie urządzenia HoloLens
- wycofywanie do starszej aktualizacji

## <a name="check-your-operating-system-version-build-number"></a>Sprawdź wersję systemu operacyjnego (numer kompilacji)

Numer wersji systemu (numer kompilacji) możesz sprawdzić, otwierając aplikację Ustawienia i wybierając pozycję System About **(Informacje o**  >  **systemie).**

## <a name="check-for-updates-and-manually-update"></a>Sprawdzanie aktualizacji i ręczne aktualizowanie

Aktualizacje można sprawdzić w dowolnym momencie w ustawieniach.  Aby wyświetlić dostępne aktualizacje i sprawdzić, czy są dostępne nowe aktualizacje:

1. Otwórz aplikację **Ustawienia**.
1. Przejdź do **usługi Update & Security**  >  **Windows Update**.
1. Wybierz pozycję **Sprawdź dostępność aktualizacji**.

Jeśli aktualizacja jest dostępna, rozpocznie pobieranie nowej wersji. Po zakończeniu pobierania wybierz przycisk Uruchom ponownie **teraz,** aby wyzwolić instalację. Jeśli urządzenie jest poniżej 40% i nie jest podłączone do sieci, ponowne uruchomienie nie rozpocznie instalowania aktualizacji.

Podczas instalowania aktualizacji na urządzeniach HoloLens będą wyświetlane obracające się koła zębate i wskaźnik postępu. Nie wyłączaj urządzenia HoloLens w tym czasie. Zostanie ona automatycznie ponownie uruchomiona po zakończeniu instalacji.

Urządzenie HoloLens stosuje po jednej aktualizacji na raz.  Jeśli urządzenie HoloLens ma więcej niż jedną wersję niż najnowsza, może być konieczne wielokrotne uruchomienie procesu aktualizacji, aby w pełni go zaktualizować.

## <a name="go-back-to-a-previous-version"></a>Wstecz do poprzedniej wersji

W niektórych przypadkach może być konieczne powrót do poprzedniej wersji oprogramowania HoloLens. Zalecane czynności to:

1. Skontaktuj się z pomocą techniczną, aby sprawdzić, czy może rozwiązać problem.
    1. Upewnij **się, że włączono** **opcjonalną lub** pełną telemetrię — dzięki temu usterka będzie bardziej aktywna i łatwiejsza do zdiagnozowania przez inżynierów.
    1. [Opinia o pliku](hololens-feedback.md) jest jak najbardziej opisowa. Zanotuj tytuł lub użyj funkcji udostępniania, aby udostępnić usterkę pomocy technicznej.
    1. Skontaktuj się [z pomocą techniczną.](https://aka.ms/hlsupport) Jeśli problem należy rozwiązać, wracając do poprzedniej wersji, może dostarczyć urządzenie FFU do flashowania urządzenia.

1. Jeśli to nie zadziała, [zresetuj lub odwróć ukośnik urządzenia HoloLens 2 za pomocą narzędzia Advanced Recovery Companion](hololens-recovery.md).
    1. Na komputerze pobierz program [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) z Microsoft Store.
    1. Upewnij się, że nie masz żadnych telefonów ani urządzeń z systemem Windows podłączonych do komputera.
    1. Wybierz wersję, w której chcesz flashować:
        1. Możesz pobrać [najnowszą wersję urządzenia HoloLens 2.](https://aka.ms/hololens2download)
        1. Można użyć domyślnej kompilacji hostów ARC. (Jeśli wybierzesz tę opcję, pomiń następny krok).
        1. Możesz użyć dostarczonej pomocy technicznej kompilacji.
    1. Po zakończeniu pobierania otwórz plik **Eksplorator plików**  >  **Pliki do pobrania.** Kliknij prawym przyciskiem myszy właśnie pobrany folder, a następnie wybierz polecenie **Wyodrębnij wszystkie** wyodrębnij,  >   aby go rozpakować.
    1. Podłącz urządzenie HoloLens do komputera za pomocą kabla USB-A do USB-C. (Nawet jeśli do łączenia urządzenia HoloLens używasz innych kabli, ten z nich działa najlepiej).
    1. Pomocnik odzyskiwania zaawansowanego automatycznie wykrywa urządzenie HoloLens. Wybierz **kafelek Microsoft HoloLens** aplikacji.
    1. Na następnym ekranie wybierz opcję **Ręczne** wybieranie pakietu, a następnie wybierz plik instalacyjny zawarty w folderze rozpakowany w kroku 4. (Poszukaj pliku z rozszerzeniem ffu).
    1. Wybierz **pozycję Zainstaluj oprogramowanie** i postępuj zgodnie z instrukcjami.

> [!NOTE]
> Powrót do wcześniejszej wersji powoduje usunięcie osobistych plików i ustawień.

Ponadto jeśli chcesz pozostać w aktualnie zainstalowanej wersji, możesz również ręcznie wstrzymać [aktualizacje.](hololens-updates.md#pause-updates-via-device) Pozwoli to zespołowi inżynierów na rozwiązanie problemu.

## <a name="windows-insider-program-on-hololens"></a>Niejawny program testów systemu Windows na urządzeniach HoloLens

Chcesz zobaczyć najnowsze funkcje na urządzeniach HoloLens?  Jeśli tak, dołącz Niejawny program testów systemu Windows; Będziesz mieć dostęp do kompilacji oprogramowania holoLens w wersji zapoznawczej, zanim będą one dostępne publicznie.

[Pobierz niejawny tester systemu Windows zapoznawczą dla Microsoft HoloLens](hololens-insider.md).
