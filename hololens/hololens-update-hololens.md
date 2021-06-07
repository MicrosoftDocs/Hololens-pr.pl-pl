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
# <a name="update-hololens"></a>Aktualizowanie urządzenia HoloLens

Urządzenie HoloLens używa Windows Update, podobnie jak inne Windows 10 urządzenia. Urządzenie HoloLens będzie automatycznie pobierać i instalować aktualizacje systemu za każdym razem, gdy jest podłączony do zasilania i połączony z Internetem, nawet jeśli jest w stanie wstrzymania.

Ten artykuł zawiera informacje na temat narzędzi dla urządzenia HoloLens:

- wyświetlanie bieżącej wersji systemu operacyjnego (numer kompilacji)
- sprawdzanie aktualizacji
- ręczne aktualizowanie urządzenia HoloLens
- wycofywanie do starszej aktualizacji

## <a name="check-your-operating-system-version-build-number"></a>Sprawdź wersję systemu operacyjnego (numer kompilacji)

Numer wersji systemu (numer kompilacji) możesz sprawdzić, otwierając aplikację Ustawienia i wybierając pozycję System About **(Informacje o**  >  **systemie).**

## <a name="check-for-updates-and-manually-update"></a>Sprawdź aktualizacje i ręcznie je zaktualizuj

Aktualizacje można sprawdzić w dowolnym momencie w ustawieniach.  Aby wyświetlić dostępne aktualizacje i sprawdzić, czy są dostępne nowe aktualizacje:

1. Otwórz aplikację **Ustawienia**.
1. Przejdź do **usługi Update & Security**  >  **Windows Update**.
1. Wybierz pozycję **Sprawdź dostępność aktualizacji**.

Jeśli aktualizacja jest dostępna, rozpocznie pobieranie nowej wersji. Po zakończeniu pobierania wybierz przycisk Uruchom ponownie **teraz,** aby wyzwolić instalację. Jeśli urządzenie jest poniżej 40% i nie jest podłączone do sieci, ponowne uruchomienie nie rozpocznie instalowania aktualizacji.

Podczas instalowania aktualizacji na urządzeniach HoloLens będą wyświetlane obracające się koła zębate i wskaźnik postępu. Nie wyłączaj urządzenia HoloLens w tym czasie. Zostanie ona automatycznie ponownie uruchomiona po zakończeniu instalacji.

Urządzenie HoloLens stosuje po jednej aktualizacji na raz.  Jeśli urządzenie HoloLens ma więcej niż jedną wersję niż najnowsza, może być konieczne wielokrotne uruchomienie procesu aktualizacji, aby w pełni go zaktualizować.

## <a name="go-back-to-a-previous-version---hololens-2"></a>Wstecz do poprzedniej wersji — HoloLens 2

W niektórych przypadkach może być konieczne powrót do poprzedniej wersji oprogramowania HoloLens. Możesz to zrobić za pomocą narzędzia Advanced Recovery Companion, aby zresetować urządzenie HoloLens do starszej wersji.

> [!NOTE]
> Powrót do wcześniejszej wersji powoduje usunięcie osobistych plików i ustawień.

Aby wrócić do poprzedniej wersji urządzenia HoloLens 2, wykonaj następujące kroki:

1. Upewnij się, że nie masz żadnych telefonów ani urządzeń z systemem Windows podłączonych do komputera.
1. Na komputerze pobierz program [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) z Microsoft Store.
1. Pobierz [najnowszą wersję urządzenia HoloLens 2.](https://aka.ms/hololens2download)
1. Po zakończeniu pobierania otwórz Eksploratora plików Pliki  >  **do pobrania.** Kliknij prawym przyciskiem myszy właśnie pobrany folder, a następnie wybierz polecenie **Wyodrębnij wszystkie** wyodrębnij,  >   aby go rozpakować.
1. Podłącz urządzenie HoloLens do komputera za pomocą kabla USB-A do USB-C. (Nawet jeśli do łączenia urządzenia HoloLens używasz innych kabli, ten z nich działa najlepiej).
1. Pomocnik odzyskiwania zaawansowanego automatycznie wykrywa urządzenie HoloLens. Wybierz **kafelek Microsoft HoloLens** aplikacji.
1. Na następnym ekranie wybierz opcję **Ręczne** wybieranie pakietu, a następnie wybierz plik instalacyjny zawarty w folderze rozpakowany w kroku 4. (Poszukaj pliku z rozszerzeniem ffu).
1. Wybierz **pozycję Zainstaluj oprogramowanie** i postępuj zgodnie z instrukcjami.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>Wstecz do poprzedniej wersji — HoloLens (1. generacja)

W niektórych przypadkach może być konieczne powrót do poprzedniej wersji oprogramowania HoloLens. Możesz to zrobić przy użyciu narzędzia do odzyskiwania urządzeń z systemem Windows, aby zresetować urządzenie HoloLens do starszej wersji.

> [!NOTE]
> Powrót do wcześniejszej wersji powoduje usunięcie osobistych plików i ustawień.

Aby wrócić do poprzedniej wersji urządzenia HoloLens 1, wykonaj następujące kroki:

1. Upewnij się, że nie masz żadnych telefonów ani urządzeń z systemem Windows podłączonych do komputera.
1. Na komputerze pobierz narzędzie [Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379)
1. Pobierz pakiet [odzyskiwania rocznicowej aktualizacji urządzenia HoloLens.](https://aka.ms/hololensrecovery)
1. Po zakończeniu pobierania otwórz **Eksploratora plików**—  >  **pliki do pobrania.** Kliknij prawym przyciskiem myszy właśnie pobrany folder, a następnie wybierz polecenie **Wyodrębnij wszystkie** wyodrębnij,  >   aby go rozpakować.
1. Podłącz urządzenie HoloLens do komputera przy użyciu kabla mikro USB, który został do niego podłączony. (Nawet jeśli do łączenia urządzenia HoloLens używasz innych kabli, ten z nich działa najlepiej).
1. Funkcja WDRT automatycznie wykryje urządzenie HoloLens. Wybierz **kafelek Microsoft HoloLens** aplikacji.
1. Na następnym ekranie wybierz opcję **Ręczne wybieranie** pakietu i wybierz plik instalacyjny zawarty w folderze rozpakowany w kroku 4. (Poszukaj pliku z rozszerzeniem ffu).
1. Wybierz **pozycję Zainstaluj oprogramowanie** i postępuj zgodnie z instrukcjami.

> [!NOTE]
> Jeśli WDRT nie wykryje urządzenia HoloLens, spróbuj ponownie uruchomić komputer. Jeśli to nie zadziała, wybierz pozycję **Moje urządzenie** nie zostało wykryte, wybierz pozycję **Microsoft HoloLens**, a następnie postępuj zgodnie z instrukcjami.

## <a name="windows-insider-program-on-hololens"></a>Niejawny program testów systemu Windows na urządzeniach HoloLens

Chcesz zobaczyć najnowsze funkcje na urządzeniach HoloLens?  Jeśli tak, dołącz do Niejawny program testów systemu Windows; Będziesz mieć dostęp do kompilacji oprogramowania holoLens w wersji zapoznawczej, zanim będą one dostępne publicznie.

[Pobierz niejawny tester systemu Windows zapoznawczą dla Microsoft HoloLens](hololens-insider.md).
