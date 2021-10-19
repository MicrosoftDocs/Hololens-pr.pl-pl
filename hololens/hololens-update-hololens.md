---
title: Aktualizacja HoloLens 2
description: Dowiedz się, jak sprawdzić numer HoloLens kompilacji, być na bieżąco z aktualizacjami urządzeń, dołączyć do programu dla niejawnych testerów i wycofać aktualizacje.
keywords: how-to, update, roll back, HoloLens, check build, build number
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-beehanson
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/11/2021
audience: ITPro
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: 080fb184c7eca3fdb978e860a29764f5012a179e
ms.sourcegitcommit: f105a770814ccd61e88b650448902a03c95b7a3c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/19/2021
ms.locfileid: "130151696"
---
# <a name="update-hololens-2"></a>Aktualizacja HoloLens 2

## <a name="overview"></a>Omówienie

Zawsze pracujemy nad nowymi funkcjami, poprawkami błędów i aktualizacjami zabezpieczeń. Otrzymasz powiadomienie, gdy te aktualizacje będą gotowe.

Zgodnie z preferencjami urządzenie HoloLens automatycznie pobierać i instalować aktualizacje systemu za każdym razem, gdy jest podłączony do zasilania, połączony z Internetem, a nawet w stanie wstrzymania.

Aby upewnić się, HoloLens jest zawsze aktualizowana, pozostaw ją podłączaną do komputera z jego urządzeniem. Chcesz również, aby HoloLens z Internetem. W ten sposób program automatycznie pobierze i zainstaluje aktualizacje systemu. 

Dzięki Windows Update service będziesz kontrolować wiele aspektów procesu aktualizacji, takich jak to, które urządzenia mogą pobrać aktualizacje o każdej godzinie. Ta kontrolka jest przydatna, ponieważ w celu testowania można HoloLens w podzestawie urządzeń. Następnie wdaj aktualizacje dla pozostałych. Można również zdefiniować różne harmonogramy aktualizacji dla różnych typów aktualizacji.

## <a name="types-of-updates"></a>Typy aktualizacji

Na HoloLens można automatycznie zarządzać dwoma typami aktualizacji.

- Aktualizacje funkcji: wydane dwa razy w roku.
- Aktualizacje dotyczące jakości: obejmują krytyczne aktualizacje zabezpieczeń. Są one zwalniane co miesiąc lub zgodnie z wymaganiami.

Użyj **funkcji Update** / **AllowAutoUpdate,** aby zarządzać skanowaniem, pobieraniem i instalowaniem aktualizacji. 

## <a name="scheduling-updates"></a>Planowanie aktualizacji

Można również ustawić harmonogram aktualizacji. Może to być określony dzień lub dzień o określonej godzinie. Na przykład o godzinie 17:00 lub poza godzinami aktywności.

Na koniec kilka słów na temat planowania strategii aktualizacji. Obsługujemy odroczenia aktualizacji, dzięki czemu możesz zdecydować, jak długo czekać po wydaniu aktualizacji przez firmę Microsoft w celu zainstalowania tej aktualizacji na urządzeniach.

Czasami firma lubi najpierw wypróbować wszystkie nowe funkcje, aby upewnić się, że wszystko działa, i zna nowe aktualizacje, aby przygotować zespół pomocy technicznej. Po potwierdzeniu, że wszystko jest dobre, wdają aktualizacje w całej firmie. Kojarząc podzestawy urządzeń z różnymi zasadami odroczenia, znanymi jako pierścienie aktualizacji, można skoordynować strategię aktualizacji dla organizacji.

## <a name="hololens-update-tools"></a>HoloLens narzędzi aktualizacji

Ta sekcja zawiera informacje na temat HoloLens narzędzi do:

- sprawdzanie aktualizacji
- ręczne aktualizowanie HoloLens
- wyświetlanie bieżącej wersji systemu operacyjnego (numer kompilacji)
- wycofywanie do starszej aktualizacji

### <a name="check-for-updates-and-manually-update"></a>Sprawdzanie aktualizacji i aktualizacja ręczna

Aktualizacje można sprawdzić w dowolnym momencie w ustawieniach.  Aby wyświetlić dostępne aktualizacje i sprawdzić, czy są dostępne nowe aktualizacje:

1. Otwórz aplikację **Ustawienia**.
1. Przejdź do **usługi Update & Security** Windows  >  **Update.**
1. Wybierz pozycję **Sprawdź dostępność aktualizacji**.

Jeśli aktualizacja jest dostępna, rozpocznie pobieranie nowej wersji. Po zakończeniu pobierania wybierz przycisk Uruchom ponownie **teraz,** aby wyzwolić instalację. Jeśli urządzenie jest poniżej 40% i nie jest podłączone do sieci, ponowne uruchomienie nie rozpocznie instalowania aktualizacji.

Podczas HoloLens aktualizacji zostaną w nim wyświetlane obracające się koła zębate i wskaźnik postępu. Nie należy wyłączać HoloLens w tym czasie. Zostanie ono automatycznie uruchomione ponownie po zakończeniu instalacji.

HoloLens stosuje po jednej aktualizacji na raz.  Jeśli twoja HoloLens jest więcej niż jedna wersja najnowszej wersji, może być konieczne uruchomienie procesu aktualizacji wiele razy, aby w pełni go zaktualizować.

### <a name="check-your-operating-system-version-build-number"></a>Sprawdź wersję systemu operacyjnego (numer kompilacji)

Numer wersji systemu (numer kompilacji) można sprawdzić, **otwierając** Ustawienia i wybierz pozycję System About **(Informacje o**  >  **systemie).**

### <a name="go-back-to-a-previous-version"></a>Wstecz do poprzedniej wersji

W niektórych przypadkach może być konieczne powrót do poprzedniej wersji HoloLens oprogramowania. Zalecane czynności to:

1. Skontaktuj się z pomocą techniczną, aby sprawdzić, czy może rozwiązać problem.
    1. Upewnij **się, że włączono** **opcjonalną** lub pełną telemetrię — dzięki temu usterka będzie bardziej aktywna i łatwiejsza do zdiagnozowania przez inżynierów.
    1. W [pliku opinii być](hololens-feedback.md) jak najbardziej opisowe. Zanotuj tytuł lub użyj funkcji udostępniania, aby udostępnić usterkę pomocy technicznej.
    1. Skontaktuj się z [pomocą techniczną.](https://aka.ms/hlsupport) Jeśli problem należy rozwiązać, wracając do poprzedniej wersji, może dostarczyć ci ffu do flashowania urządzenia.

1. Alternatywnie można zmienić ukośnik HoloLens [2 za pomocą pomocnika odzyskiwania zaawansowanego.](hololens-recovery.md#clean-reflash-the-device)
    1.  Wybierz wersję, w której chcesz flashować: 
        1.  Możesz pobrać [najnowszą wersję HoloLens 2.](https://aka.ms/hololens2download)
        1.  Można użyć domyślnej kompilacji hostów ARC.
        1.  Możesz użyć dostarczonej pomocy technicznej kompilacji.

> [!NOTE]
> Powrót do wcześniejszej wersji powoduje usunięcie osobistych plików i ustawień.

Ponadto jeśli chcesz pozostać w aktualnie zainstalowanej wersji, możesz również ręcznie wstrzymać [aktualizacje.](hololens-updates.md#pause-updates-via-device) Pozwoli to zespołowi inżynierów na rozwiązanie problemu.

## <a name="windows-insider-program-on-hololens"></a>Windows niejawny program testów na HoloLens

Chcesz zobaczyć najnowsze funkcje w HoloLens?  Jeśli tak, dołącz do Windows niejawny program testów; Będziesz mieć dostęp do wersji zapoznawczej kompilacji HoloLens oprogramowania, zanim będą one dostępne publicznie.

[Pobierz Windows Insider Preview dla Microsoft HoloLens.](hololens-insider.md)