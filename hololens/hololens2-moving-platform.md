---
title: HoloLens 2 Przenoszenie trybu platformy
description: Jak używać funkcji HoloLens na przenoszenie platform
keywords: przenoszenie platform, ruch dynamiczny, hololens, tryb przenoszenia platformy
author: evmill
ms.author: v-evmill
ms.reviewer: yabahman
ms.date: 10/12/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: high
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 7c636cd97e31c74d4976e71ec3f41ac5afe5bdcc
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924430"
---
# <a name="moving-platform-mode-on-low-dynamic-motion-moving-platforms"></a>Przenoszenie trybu platformy na platformach o niskim ruchu dynamicznym

W Windows Holographic w wersji [21H2](hololens-release-notes.md#windows-holographic-version-21h2) dodaliśmy obsługę wersji beta do śledzenia na platformach o niskim dynamicznym ruchu na platformach HoloLens 2. Po zainstalowaniu kompilacji i włączeniu trybu przenoszenia platformy będzie można korzystać z urządzenia HoloLens 2 w wcześniej niedostępnych środowiskach, takich jak duże jednostki i duże statku. Obecnie ta funkcja jest ukierunkowana na włączanie tylko tych konkretnych ruchomych platform. Chociaż nic nie uniemożliwia próby użycia tej funkcji w innych środowiskach, ta funkcja koncentruje się najpierw na dodawaniu obsługi tych środowisk.

![Przykład przenoszenia platformy.](./images/mpm-compare.gif)

Ten artykuł obejmuje:

1. [Dlaczego przenoszenie platformy jest konieczne](#why-moving-platform-mode-is-necessary)
1. [Włączanie trybu przenoszenia platformy](#enabling-moving-platform-mode)

## <a name="why-moving-platform-mode-is-necessary"></a>Dlaczego przenoszenie trybu platformy jest konieczne

HoloLens musi mieć możliwość śledzenia pozycji głowy z [6](https://en.wikipedia.org/wiki/Six_degrees_of_freedom) stopniami swobody (X, Y, Z, tłumaczenie i rzut, wysokość, obrót osi) w celu pokazania stabilnych hologramów. Aby to zrobić, HoloLens śledzi dwie podobne informacje z dwóch oddzielnych źródeł:

1. **Widoczne jasne kamery.** Te kamery śledzą środowisko, na przykład fizyczne pomieszczenie, w którym używasz urządzenia HoloLens
1. **Inertial Measurement Unit (IMU).** IMU składa się z akcelerometru, żyrometru i akcelerometru, który śledzi ruch i orientację głowy względem Ziemi

Informacje z tych dwóch źródeł są złożone w celu śledzenia pozycji głowy z małym opóźnieniem i wystarczająco dużą częstotliwością, aby renderować płynne hologramy.

Jednak takie podejście opiera się na założeniach krytycznych; środowisko (śledzone przez kamery) pozostaje względne względem Ziemi (względem której IMU może dokonać pomiarów). Jeśli tak nie jest, na przykład w kącie w wodnych źródłach, informacje z obu źródeł mogą powodować konflikty ze sobą i spowodować utracony moduł śledzący. Ten konflikt powoduje niepoprawne informacje o pozycji i powoduje błąd hologramów, a nawet śledzenie utraty.

Przeniesienie trybu platformy pozwala na rozwiązania tego problemu. Włączenie trybu przenoszenia platformy jest wskazówką dla naszego modułu śledzącego, że nie możemy polegać na danych wejściowych czujników w celu całkowitej zgody na siebie przez cały czas. Zamiast tego musimy bardziej polegać na śledzeniu wizualnym i szybko identyfikować dane ruchu bezwładnego i odpowiednio je odfiltrować, zanim będziemy mogli użyć danych wejściowych IMU.

## <a name="supported-environments-and-known-limitations"></a>Obsługiwane środowiska i znane ograniczenia

Chociaż tryb przenoszenia platformy został opracowany w celu inteligentnego obsługi przypadków konfliktu danych bezwładnych i wizualnych, obecnie jest on ograniczony do dużych zbiorników, w których występuje ruch o niskiej dynamice. Oznacza to, że istnieją pewne ograniczenia i nieobsługiwane scenariusze.

### <a name="known-limitations"></a>Znane ograniczenia

- Jedynymi obsługiwanymi środowiskami dla trybu przenoszenia platformy (MPM) są duże jednostki z ruchem o niskiej dynamice. Innymi słowy, wiele typowych środowisk/sytuacji nie jest jeszcze obsługiwanych ze względu na ich ruch o wysokiej częstotliwości oraz wysokie poziomy przyspieszenia i [prędkości](https://en.wikipedia.org/wiki/Jerk_(physics)).  Na przykład: samoloty, pociągi, samochody, rowery, busy, małe rowery, windy itp.
- Hologramy mogą się nieznacznie chylić po włączeniu funkcji MPM, szczególnie w przypadku korzystania z wody w wodnych urządzeniach.
- Nic nie uniemożliwia użytkownikom próby korzystania z mpM w nieobsługiwanych środowiskach, jednak użytkownicy mogą wystąpić niepożądane skutki uboczne, jeśli urządzenie jest w stanie zachować śledzenie w nieobsługiwanym miejscu. Na przykład w przypadku mpm użytkownicy mogą znaleźć możliwość użycia w windzie podczas zmiany podłogi, podczas gdy wcześniej było to niemożliwe. Niestety, chociaż program MPM umożliwia urządzeniu utrzymanie śledzenia, obecnie nie obsługuje zarządzania mapami. Użytkownicy zobaczą, że zmiana podłogi w windzie spowoduje, że urządzenie zmyli górną i dolną podłogę i niekorzystnie wpłynie na jakość mapy.

## <a name="prerequisites"></a>Wymagania wstępne

Obsługa wersji beta dla przenoszenia trybu platformy wymaga tylko kilku wymagań wstępnych:

1. Zainstaluj Windows Holographic w wersji [21H2](hololens-release-notes.md#windows-holographic-version-21h2) lub nowszej, aktualizując lub flashując najnowszą [kompilację](https://aka.ms/hololens2download) [za pośrednictwem usługi ARC.](hololens-recovery.md#clean-reflash-the-device)

2. Włączanie [trybu dewelopera i Portal urządzeń](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

## <a name="enabling-moving-platform-mode"></a>Włączanie trybu przenoszenia platformy

Aby włączyć tryb przenoszenia platformy, najpierw [włącz Portal urządzeń](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).

1. Wybierz pozycję **System** accordion w menu po lewej stronie

   ![Pierwszy obraz.](.\images\mpm-01.png)

2. Wybierz stronę **Przenoszenie trybu platformy** i zaznacz pole wyboru Przenoszenie **trybu** platformy

    ![Drugi obraz.](.\images\mpm-02.png)

3. Po wyświetleniu monitu z ostrzeżeniem wybierz przycisk **OK**

   ![Trzeci obraz.](.\images\mpm-03.png)

4. Uruchom ponownie urządzenie, co można wykonać za pomocą menu Portal urządzeń **Power** w prawym górnym rogu lub przez wydanie następującego polecenia głosowego Uruchom ponownie urządzenie i wybierz &quot; pozycję &quot; &quot; &quot; Tak.

   ![Czwarty obraz.](.\images\mpm-04.png)

Jeśli nie widzisz opcji Przenoszenie trybu platformy w Portal urządzeń, prawdopodobnie oznacza to, że nie jesteś jeszcze w odpowiedniej kompilacji. Zobacz [sekcję Wymagania](#prerequisites) wstępne.

## <a name="reporting-issues"></a>Problemy z raportowaniem

Jak wspomniano powyżej, ta funkcja jest funkcją w wersji beta dostępną tylko w trybie dewelopera, co oznacza, że mogą wystąpić problemy. Jeśli tak się stanie, możemy zbadać i ulepszyć produkt:

1. Zgłoś problem za [pośrednictwem Centrum opinii](hololens-feedback.md) kategorii Dokładność, stabilność i niezawodność **hologramu** i uwzględnij następujące informacje:
    1. Opis problemu, w tym oczekiwane i doświadczone zachowanie
    1. Zrzut Mixed Reality [wideo z](holographic-photos-and-videos.md#capture-a-mixed-reality-video) problemem
2.  Otwórz sprawę pomocy technicznej pod adresem i udostępnij adres URL Centrum opinii, abyśmy się z to zdążyli na wypadek, gdy będziemy mieć [https://aka.ms/hlsupport](https://aka.ms/hlsupport) kolejne pytania