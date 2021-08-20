---
title: HoloLens 2 Przenoszenie trybu platformy
description: Jak używać funkcji HoloLens na ruchomych platformach
keywords: przenoszenie platform, ruch dynamiczny, hololens, tryb przenoszenia platformy
author: evmill
ms.author: v-evmill
ms.reviewer: yabahman
ms.date: 8/10/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: high
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 64aaf726fab27c997eea26208f17daae4fa3179d
ms.sourcegitcommit: 938fa78e1b6c59626e12399c9babc277eb30c29c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/19/2021
ms.locfileid: "122448709"
---
# <a name="moving-platform-mode-on-low-dynamic-motion-moving-platforms"></a>Przenoszenie trybu platformy na platformach o niskim ruchu dynamicznym

W **kompilacji Insider Build 20348.1411** dodaliśmy obsługę wersji beta śledzenia na platformach ruchu o niskiej dynamice na platformach w wersji HoloLens 2. Po zainstalowaniu kompilacji i włączeniu trybu przenoszenia platformy będzie można używać urządzenia HoloLens 2 w wcześniej niedostępnych środowiskach, takich jak duże statku i duże statku. Obecnie funkcja jest ukierunkowana na włączanie tylko tych konkretnych ruchomych platform. Chociaż nic nie uniemożliwia próby użycia tej funkcji w innych środowiskach, ta funkcja koncentruje się najpierw na dodawaniu obsługi tych środowisk.

> [!NOTE]
> Ta funkcja jest obecnie dostępna tylko za [pośrednictwem Windows niejawnych testerów.](hololens-insider.md)

Ten artykuł obejmuje:

1. [Dlaczego przenoszenie platformy jest konieczne](#why-moving-platform-mode-is-necessary)
1. [Włączanie trybu przenoszenia platformy](#enabling-moving-platform-mode)

## <a name="why-moving-platform-mode-is-necessary"></a>Dlaczego przenoszenie trybu platformy jest konieczne

HoloLens musi być w stanie śledzić pozycję głowy z [6](https://en.wikipedia.org/wiki/Six_degrees_of_freedom) stopniami swobody (X, Y, Z, tłumaczenie i rzut, rzut, obrót osią), aby pokazać stabilne hologramy. W tym celu HoloLens dwóch podobnych informacji z dwóch oddzielnych źródeł:

1. Widoczne jasne kamery — śledzące środowisko, na przykład fizyczne pomieszczenie, w którym używasz urządzenia HoloLens
1. Inertial Measurement Unit (IMU) — który składa się z akcelerometru, gyroscope i akceleratora, który śledzi ruch i orientację głowy względem Ziemi

Informacje z tych dwóch źródeł są złożone w celu śledzenia pozycji głowy z małym opóźnieniem i wystarczająco dużą częstotliwością w celu renderowania płynnych hologramów.

Jednak takie podejście opiera się na założeniu krytycznym; środowisko (śledzone przez kamery) pozostaje chybne względem Ziemi (względem której IMU może dokonać pomiarów). Jeśli tak nie jest, tak jak w przypadku wody, informacje z obu źródeł mogą powodować konflikty ze sobą i spowodować zagubiony moduł śledzący. Ten konflikt powoduje niepoprawne informacje o pozycji i powoduje hologramy wykresu, a nawet śledzenie utraty.

Przeniesienie trybu platformy pozwala na rozwiązania tego problemu. Włączenie trybu przenoszenia platformy jest wskazówką dla naszego modułu śledzącego, że nie możemy polegać na danych wejściowych czujników, aby całkowicie się ze sobą zgadzać przez cały czas. Zamiast tego musimy polegać bardziej na śledzeniu wizualnym i szybko identyfikować dane ruchu bezwładnego i odpowiednio je odfiltrować, zanim będziemy mogli użyć danych wejściowych IMU.

## <a name="supported-environments-and-known-limitations"></a>Obsługiwane środowiska i znane ograniczenia

Chociaż tryb przenoszenia platformy został opracowany w celu inteligentnej obsługi przypadków konfliktu danych bezwładnych i wizualnych, jest on obecnie ograniczony do dużych łańcowych, w których występują ruchy o niskiej dynamice. Oznacza to, że istnieją pewne ograniczenia i nieobsługiwane scenariusze.

### <a name="known-limitations"></a>Znane ograniczenia

- Jedynymi obsługiwanymi środowiskami dla trybu przenoszenia platformy (MPM, Moving Platform Mode) są duże jednostki z ruchami o niskiej dynamice. Innymi słowy, wiele typowych środowisk/sytuacji nie jest jeszcze obsługiwanych ze względu na ich ruch o wysokiej częstotliwości oraz wysokie poziomy przyspieszenia i [procesów .](https://en.wikipedia.org/wiki/Jerk_(physics))  Na przykład: samoloty, pociągi, samochody, rowery, busy, małe wypożyczalnie, windy itp.
- Hologramy nieco się nie pochylić, gdy program MPM jest włączony, szczególnie w przypadku korzystania z wody w cieku.
- Nic nie uniemożliwia użytkownikom korzystania z mpm w nieobsługiwanych środowiskach, jednak użytkownicy mogą wystąpić niepożądane skutki uboczne, jeśli urządzenie jest w stanie utrzymać śledzenie w nieobsługiwanym miejscu. Na przykład w przypadku aplikacji MPM użytkownicy mogą korzystać z windy podczas zmiany podłogi, ale wcześniej było to niemożliwe. Niestety, chociaż program MPM umożliwia urządzeniu utrzymanie śledzenia, obecnie nie obsługuje zarządzania mapami. Użytkownicy zobaczą, że zmiana podłogi w windzie spowoduje, że urządzenie będzie mylić górne i niższe podłogi oraz negatywnie wpłynąć na jakość mapy.

## <a name="prerequisites"></a>Wymagania wstępne

Obsługa wersji beta dla przenoszenia trybu platformy wymaga tylko kilku wymagań wstępnych:

1. Zainstaluj kompilację 20348.1411 lub nowszą, flashując najnowszą kompilację niejawnych testerów za pośrednictwem usługi [ARC](hololens-insider.md#ffu-download-and-flash-directions) lub rejestrując i aktualizując [urządzenie.](hololens-insider.md#start-receiving-insider-builds)

   > [!NOTE]
   > Ta kompilacja jest obecnie dostępna tylko w kanale [niejawnych testerów deweloperów.](hololens-insider.md#start-receiving-insider-builds)

2. Włączanie [trybu dewelopera i trybu Portal urządzeń](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

## <a name="enabling-moving-platform-mode"></a>Włączanie trybu przenoszenia platformy

Aby włączyć tryb Przenoszenia platformy, najpierw [włącz Portal urządzeń](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).

1. Wybierz pozycję **System** accordion w menu po lewej stronie

   ![Pierwszy obraz](.\images\moving-platform-1z.png)

2. Wybierz stronę **Przenoszenie trybu platformy** i zaznacz pole wyboru **Tryb** przenoszenia platformy

    ![Drugi obraz](.\images\moving-platform-2z.png)

3. Po wyświetleniu monitu z ostrzeżeniem wybierz przycisk **OK**

   ![Trzeci obraz](.\images\moving-platform-3z.png)

4. Uruchom ponownie urządzenie, co można wykonać za pomocą menu Portal urządzeń **Power** w prawym górnym rogu lub za pomocą następującego polecenia głosowego Uruchom ponownie urządzenie i wybierz &quot; pozycję &quot; &quot; &quot; Tak.

   ![Czwarty obraz](.\images\moving-platform-4z.png)

Jeśli nie widzisz opcji Przenoszenie trybu platformy w Portal urządzeń, prawdopodobnie oznacza to, że nie jesteś jeszcze na właściwej kompilacji. Zobacz [sekcję Wymagania](#prerequisites) wstępne.

## <a name="reporting-issues"></a>Problemy z raportowaniem

Jak wspomniano powyżej, ta funkcja jest funkcją w wersji beta dostępną tylko w trybie dewelopera, co oznacza, że mogą wystąpić problemy. W takim przypadku możemy zbadać i ulepszyć produkt.

1. Zgłoś problem za [pośrednictwem Centrum opinii](hololens-feedback.md) kategorii Dokładność, stabilność i niezawodność **hologramu** i uwzględnij następujące informacje:
    1. Opis problemu, w tym oczekiwane i doświadczone zachowanie
    1. Zrzut Mixed Reality [wideo o](holographic-photos-and-videos.md#capture-a-mixed-reality-video) problemie
2.  Otwórz sprawę pomocy technicznej pod adresem i udostępnij adres URL Centrum opinii, abyśmy mieli do nich dostęp w [https://aka.ms/hlsupport](https://aka.ms/hlsupport) przypadku, gdy będziemy mieć kolejne pytania