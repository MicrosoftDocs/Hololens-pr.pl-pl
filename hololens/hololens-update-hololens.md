---
title: Aktualizacja HoloLens 2
description: Dowiedz się, jak sprawdzić numer HoloLens kompilacji, być na bieżąco z aktualizacjami urządzeń, dołączyć do programu dla niejawnych testerów i wycofać aktualizacje.
keywords: kompilowanie, aktualizowanie, wycofywanie, HoloLens, sprawdzanie kompilacji, numer kompilacji
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
audience: ITPro
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: f39fc2c6c0aaf16f304f38216a424c3811eb439d
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033817"
---
# <a name="update-hololens-2"></a>Aktualizacja HoloLens 2

## <a name="overview"></a>Omówienie

Zawsze pracujemy nad nowymi funkcjami, poprawkami błędów i aktualizacjami zabezpieczeń. Otrzymasz powiadomienie, gdy te aktualizacje będą gotowe.

Zgodnie z preferencjami urządzenie HoloLens automatycznie pobierać i instalować aktualizacje systemu zawsze wtedy, gdy jest podłączony do zasilania, połączony z Internetem, a nawet w stanie wstrzymania.

Aby upewnić się, HoloLens jest zawsze aktualizowana, pozostaw podłączony do niego chłoń, który jest z nim podłączony. Chcesz również, aby HoloLens z Internetem. W ten sposób automatycznie pobierze i zainstaluje aktualizacje systemu. 

Dzięki Windows Update Service będziesz kontrolować wiele aspektów procesu aktualizacji, na przykład to, które urządzenia mogą pobrać aktualizacje w czasie. Ta kontrolka jest przydatna, ponieważ umożliwia przeprowadzanie aktualizacji do podzbioru urządzeń HoloLens do testowania. Następnie wdaj aktualizacje dla pozostałych. Można również zdefiniować różne harmonogramy aktualizacji dla różnych typów aktualizacji.

## <a name="types-of-updates"></a>Typy aktualizacji

Na HoloLens można automatycznie zarządzać dwoma typami aktualizacji. 

- Aktualizacje funkcji: wydane dwa razy w roku.
- Aktualizacje dotyczące jakości: obejmują krytyczne aktualizacje zabezpieczeń. Są one zwalniane co miesiąc lub zgodnie z wymaganiami.

Użyj **aktualizacji** / **AllowAutoUpdate** do zarządzania skanowaniem, pobieraniem i instalowaniem aktualizacji. 

## <a name="scheduling-updates"></a>Planowanie aktualizacji

Można również ustawić harmonogram aktualizacji. Może to być określony dzień lub codziennie o określonej porze. Na przykład o godzinie 17:00 lub poza godzinami aktywności.

Na koniec kilka słów dotyczących planowania strategii aktualizacji. Obsługujemy odroczenia aktualizacji. Możesz więc zdecydować, jak długo czekać po wydaniu aktualizacji przez firmę Microsoft, aby zainstalować tę aktualizację na urządzeniach.

Czasami firma lubi najpierw wypróbować wszystkie nowe funkcje, aby upewnić się, że wszystko działa, i znają nowe aktualizacje, aby przygotować zespół pomocy technicznej. Po potwierdzeniu, że wszystko jest w dobrym stanie, wdają aktualizacje w całej firmie. Kojarząc podzestawy urządzeń z różnymi zasadami odroczenia, znanymi jako pierścienie aktualizacji, można skoordynować strategię aktualizacji dla organizacji.

## <a name="hololens-update-tools"></a>HoloLens narzędzi aktualizacji

Ta sekcja zawiera opis HoloLens narzędzi do:

- sprawdzanie aktualizacji
- ręczne aktualizowanie HoloLens
- wyświetlanie bieżącej wersji systemu operacyjnego (numer kompilacji)
- wycofywanie do starszej aktualizacji

### <a name="check-for-updates-and-manually-update"></a>Sprawdź aktualizacje i ręcznie je zaktualizuj

Aktualizacje można sprawdzić w dowolnym momencie w ustawieniach.  Aby wyświetlić dostępne aktualizacje i sprawdzić, czy są dostępne nowe aktualizacje:

1. Otwórz aplikację **Ustawienia**.
1. Przejdź do **usługi Update & Security** Windows  >  **Update.**
1. Wybierz pozycję **Sprawdź dostępność aktualizacji**.

Jeśli aktualizacja jest dostępna, rozpocznie pobieranie nowej wersji. Po zakończeniu pobierania wybierz przycisk Uruchom ponownie **teraz,** aby wyzwolić instalację. Jeśli urządzenie jest poniżej 40% i nie jest podłączone do sieci, ponowne uruchomienie nie rozpocznie instalowania aktualizacji.

Podczas HoloLens aktualizacji zostaną w nim wyświetlane obracające się koła zębate i wskaźnik postępu. Nie należy wyłączać HoloLens w tym czasie. Zostanie ona automatycznie ponownie uruchomiona po zakończeniu instalacji.

HoloLens stosuje po jednej aktualizacji na raz.  Jeśli Twoja HoloLens ma więcej niż jedną wersję niż najnowsza, może być konieczne wielokrotne uruchomienie procesu aktualizacji, aby w pełni go zaktualizować.

### <a name="check-your-operating-system-version-build-number"></a>Sprawdź wersję systemu operacyjnego (numer kompilacji)

Numer wersji systemu (numer kompilacji) możesz zweryfikować, otwierając Ustawienia **wybierz** pozycję System About **(Informacje o**  >  **systemie).**

### <a name="go-back-to-a-previous-version"></a>Wstecz do poprzedniej wersji

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
    1. Po zakończeniu pobierania otwórz plik do **pobrania Eksplorator plików**  >  **pobierania.** Kliknij prawym przyciskiem myszy pobrany folder, a następnie wybierz polecenie **Wyodrębnij wszystkie** wyodrębnij,  >   aby go rozpakować.
    1. Połączenie urządzenie HoloLens do komputera przy użyciu kabla USB-A do USB-C. (Nawet jeśli używasz innych kabli do łączenia urządzenia HoloLens, ten z nich działa najlepiej).
    1. Pomocnik odzyskiwania zaawansowanego automatycznie wykrywa HoloLens. Wybierz **kafelek Microsoft HoloLens** aplikacji.
    1. Na następnym ekranie wybierz opcję **Ręczne** wybieranie pakietu, a następnie wybierz plik instalacyjny zawarty w folderze rozpakowany w kroku 4. (Poszukaj pliku z `.ffu` rozszerzeniem ).
    1. Wybierz **pozycję Zainstaluj oprogramowanie** i postępuj zgodnie z instrukcjami.

> [!NOTE]
> Powrót do wcześniejszej wersji powoduje usunięcie osobistych plików i ustawień.

Ponadto jeśli chcesz pozostać w aktualnie zainstalowanej wersji, możesz również ręcznie wstrzymać [aktualizacje.](hololens-updates.md#pause-updates-via-device) Pozwoli to zespołowi inżynierów na rozwiązanie problemu.

## <a name="windows-insider-program-on-hololens"></a>Windows niejawny program testów na HoloLens

Chcesz zobaczyć najnowsze funkcje w HoloLens?  Jeśli tak, dołącz Windows niejawny program testów; Będziesz mieć dostęp do wersji zapoznawczej kompilacji HoloLens oprogramowania, zanim będą one dostępne publicznie.

[Pobierz Windows Insider Preview dla Microsoft HoloLens.](hololens-insider.md)