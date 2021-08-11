---
title: Aktualizacja HoloLens 2
description: Dowiedz się, jak HoloLens kompilacji, być na bieżąco z aktualizacjami urządzeń, dołączyć do programu dla niejawnych testerów i wycofać aktualizacje.
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
ms.openlocfilehash: 7e63fcab4c64f151684a634bb24d9fc31826f6805d52b23c5672add0b6269430
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662837"
---
# <a name="update-hololens-2"></a>Aktualizacja HoloLens 2

HoloLens korzysta z Windows Update, podobnie jak inne Windows 10 urządzeń. Urządzenie HoloLens automatycznie pobierać i instalować aktualizacje systemu zawsze wtedy, gdy jest podłączony do zasilania i połączony z Internetem, nawet jeśli jest w stanie wstrzymania.

Ten artykuł zawiera opis HoloLens narzędzi do:

- wyświetlanie bieżącej wersji systemu operacyjnego (numer kompilacji)
- sprawdzanie aktualizacji
- ręczne aktualizowanie HoloLens
- wycofywanie do starszej aktualizacji

## <a name="check-your-operating-system-version-build-number"></a>Sprawdź wersję systemu operacyjnego (numer kompilacji)

Numer wersji systemu (numer kompilacji) możesz sprawdzić, otwierając aplikację Ustawienia i wybierając pozycję System About **(Informacje o**  >  **systemie).**

## <a name="check-for-updates-and-manually-update"></a>Sprawdź aktualizacje i ręcznie je zaktualizuj

Aktualizacje można sprawdzić w dowolnym momencie w ustawieniach.  Aby wyświetlić dostępne aktualizacje i sprawdzić, czy są dostępne nowe aktualizacje:

1. Otwórz aplikację **Ustawienia**.
1. Przejdź do **usługi Update & Security** Windows  >  **Update.**
1. Wybierz pozycję **Sprawdź dostępność aktualizacji**.

Jeśli aktualizacja jest dostępna, rozpocznie pobieranie nowej wersji. Po zakończeniu pobierania wybierz przycisk Uruchom ponownie **teraz,** aby wyzwolić instalację. Jeśli urządzenie jest poniżej 40% i nie jest podłączone do sieci, ponowne uruchomienie nie rozpocznie instalowania aktualizacji.

Podczas HoloLens aktualizacji zostaną w nim wyświetlane obracające się koła zębate i wskaźnik postępu. Nie należy wyłączać HoloLens w tym czasie. Zostanie ona automatycznie ponownie uruchomiona po zakończeniu instalacji.

HoloLens stosuje po jednej aktualizacji na raz.  Jeśli twoja HoloLens jest więcej niż jedna wersja, która jest najnowsza, może być konieczne wielokrotne uruchomienie procesu aktualizacji, aby w pełni go zaktualizować.

## <a name="go-back-to-a-previous-version"></a>Wstecz do poprzedniej wersji

W niektórych przypadkach może być konieczne powrót do poprzedniej wersji HoloLens oprogramowania. Zalecane czynności to:

1. Skontaktuj się z pomocą techniczną, aby sprawdzić, czy może rozwiązać problem.
    1. Upewnij **się, że włączono** **opcjonalną lub** pełną telemetrię — dzięki temu usterka będzie bardziej aktywna i łatwiejsza do zdiagnozowania przez inżynierów.
    1. [Opinia o pliku](hololens-feedback.md) jest tak opisowa, jak to możliwe. Zanotuj tytuł lub użyj funkcji udostępniania, aby udostępnić usterkę pomocy technicznej.
    1. Skontaktuj się [z pomocą techniczną.](https://aka.ms/hlsupport) Jeśli problem należy rozwiązać, wracając do poprzedniej wersji, może dostarczyć urządzenie FFU do flashowania urządzenia.

1. Jeśli to nie zadziała, [zresetuj lub odwróć ukośnik HoloLens 2 za pomocą narzędzia Advanced Recovery Companion.](hololens-recovery.md)
    1. Na komputerze pobierz program [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) z Microsoft Store.
    1. Upewnij się, że nie masz żadnych telefonów ani urządzeń Windows podłączonych do komputera.
    1. Wybierz wersję, w której chcesz flashować:
        1. Możesz pobrać [najnowszą wersję HoloLens 2.](https://aka.ms/hololens2download)
        1. Można użyć domyślnej kompilacji hostów ARC. (Jeśli wybierzesz tę opcję, pomiń następny krok).
        1. Możesz użyć dostarczonej pomocy technicznej kompilacji.
    1. Po zakończeniu pobierania otwórz plik **Eksplorator plików**  >  **pobrane.** Kliknij prawym przyciskiem myszy właśnie pobrany folder, a następnie wybierz polecenie **Wyodrębnij** wszystkie wyodrębnij,  >   aby go rozpakować.
    1. Połączenie urządzenie HoloLens z komputerem pc za pomocą kabla USB-A do USB-C. (Nawet jeśli używasz innych kabli do łączenia urządzenia HoloLens, ten z nich działa najlepiej).
    1. Pomocnik odzyskiwania zaawansowanego automatycznie wykrywa HoloLens. Wybierz **kafelek Microsoft HoloLens** aplikacji.
    1. Na następnym ekranie wybierz opcję **Ręczne** wybieranie pakietu, a następnie wybierz plik instalacyjny zawarty w folderze rozpakowany w kroku 4. (Poszukaj pliku z rozszerzeniem ffu).
    1. Wybierz **pozycję Zainstaluj oprogramowanie** i postępuj zgodnie z instrukcjami.

> [!NOTE]
> Powrót do wcześniejszej wersji powoduje usunięcie osobistych plików i ustawień.

Ponadto jeśli chcesz pozostać w aktualnie zainstalowanej wersji, możesz również ręcznie wstrzymać [aktualizacje.](hololens-updates.md#pause-updates-via-device) Pozwoli to zespołowi inżynierów na rozwiązanie problemu.

## <a name="windows-insider-program-on-hololens"></a>Windows niejawny program testów na HoloLens

Chcesz zobaczyć najnowsze funkcje w HoloLens?  Jeśli tak, dołącz Windows niejawny program testów; Będziesz mieć dostęp do wersji zapoznawczej kompilacji HoloLens oprogramowania, zanim będą one dostępne publicznie.

[Pobierz Windows Insider Preview dla Microsoft HoloLens.](hololens-insider.md)
