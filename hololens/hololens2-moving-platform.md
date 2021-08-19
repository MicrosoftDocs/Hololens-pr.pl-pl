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
ms.openlocfilehash: 9c37baa6fb63e9b049378799515ef107ed0ea7a8
ms.sourcegitcommit: 7b666c63a0367032a4a3f366b7f9029b2613e345
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2021
ms.locfileid: "122401172"
---
# <a name="moving-platform-mode-on-low-dynamic-motion-moving-platforms"></a>Przenoszenie trybu platformy na platformach o niskim ruchu dynamicznym

W **kompilacji Insider Build 20348.1411** dodaliśmy obsługę wersji beta śledzenia na platformach ruchu o niskiej dynamice na platformach HoloLens 2. Po zainstalowaniu kompilacji i włączeniu trybu przenoszenia platformy będzie można używać urządzenia HoloLens 2 w wcześniej niedostępnych środowiskach, takich jak duże jednostki i duże statku. Obecnie ta funkcja jest ukierunkowana na włączanie tylko tych konkretnych ruchomych platform. Chociaż nic nie uniemożliwia próby użycia tej funkcji w innych środowiskach, ta funkcja koncentruje się najpierw na dodawaniu obsługi tych środowisk.

> [!NOTE]
> Ta funkcja jest obecnie dostępna tylko za [pośrednictwem Windows Insiders.](hololens-insider.md)

Ten artykuł obejmuje:

1. [Dlaczego przenoszenie platformy jest konieczne](#why-moving-platform-mode-is-necessary)
1. [Włączanie trybu przenoszenia platformy](#enabling-moving-platform-mode)

## <a name="why-moving-platform-mode-is-necessary"></a>Dlaczego przenoszenie trybu platformy jest konieczne

HoloLens musi mieć możliwość śledzenia pozycji głowy z [6](https://en.wikipedia.org/wiki/Six_degrees_of_freedom) stopniami swobody (tłumaczenie i rzut X, Y, Z, wysokość, obrót osią) w celu pokazania stabilnych hologramów. W tym celu HoloLens dwóch podobnych informacji z dwóch oddzielnych źródeł:

1. Widoczne jasne kamery — śledzące środowisko, na przykład fizyczne pomieszczenie, w którym używasz urządzenia HoloLens
1. Inertial Measurement Unit (IMU) — który składa się z akcelerometru, żyrometru i akceleratora, który śledzi ruch i orientację głowy względem Ziemi

Informacje z tych dwóch źródeł są złożone w celu śledzenia pozycji głowy z małym opóźnieniem i wystarczająco dużą częstotliwością, aby renderować płynne hologramy.

Jednak takie podejście opiera się na założeniach krytycznych; środowisko (śledzone przez kamery) pozostaje względne względem Ziemi (względem której IMU może dokonać pomiarów). Jeśli tak nie jest, na przykład w węzłem w wodnych źródłach, informacje z obu źródeł mogą powodować konflikty ze sobą i spowodować utracony moduł śledzący. Ten konflikt powoduje nieprawidłowe informacje o pozycji i powoduje błąd hologramów, a nawet śledzenie utraty.

Przeniesienie trybu platformy pozwala na rozwiązania tego problemu. Włączenie trybu przenoszenia platformy jest wskazówką dla naszego modułu śledzącego, że nie możemy polegać na danych wejściowych czujników w celu całkowitej zgody na siebie przez cały czas. Zamiast tego musimy bardziej polegać na śledzeniu wizualnym i szybko identyfikować niepogodne dane ruchu bezwładnego i odpowiednio je odfiltrować&#39;aby można było użyć danych wejściowych IMU.

## <a name="supported-environments-and-known-limitations"></a>Obsługiwane środowiska i znane ograniczenia

Chociaż tryb przenoszenia platformy został opracowany w celu inteligentnego obsługi przypadków konfliktu danych bezwładnych i wizualnych, obecnie jest on ograniczony do dużych samolotów, w których występuje ruch o niskiej dynamice. Oznacza to, że istnieją z pewnością ograniczenia i nieobsługiwane scenariusze.

### <a name="known-limitations"></a>Znane ograniczenia

- Jedynymi obsługiwanymi środowiskami dla trybu przenoszenia platformy (MPM) są duże jednostki z ruchem o niskiej dynamice. Innymi słowy, wiele typowych środowisk/sytuacji nie jest jeszcze obsługiwanych ze względu na ich ruch o wysokiej częstotliwości oraz wysokie poziomy przyspieszenia i [prędkości](https://en.wikipedia.org/wiki/Jerk_(physics)).  Na przykład: samoloty, pociągi, samochody, rowery, busy, małe rowery, windy itp.
- Hologramy mogą się nieznacznie chylić po włączeniu funkcji MPM, szczególnie w przypadku korzystania z wody zieniowej.
- Nic nie uniemożliwia użytkownikom próby korzystania z mpM w nieobsługiwanych środowiskach, jednak użytkownicy mogą wystąpić niepożądane skutki uboczne, jeśli urządzenie jest w stanie zachować śledzenie w nieobsługiwanym miejscu. Na przykład w przypadku mpm użytkownicy mogą&#39;w windzie podczas zmiany podłogi, natomiast wcześniej było to niemożliwe. Niestety, chociaż program MPM umożliwia urządzeniu utrzymanie śledzenia, obecnie nie obsługuje zarządzania mapami. Użytkownicy zobaczą więc, że zmiana podłogi w windzie spowoduje, że urządzenie zmyli górną i dolną podłogę i niekorzystnie wpłynie na jakość mapy.

## <a name="prerequisites"></a>Wymagania wstępne

Obsługa wersji beta dla przenoszenia trybu platformy wymaga tylko kilku wymagań wstępnych:

1. Zainstaluj kompilację 20348.1411 lub nowszą, flashując najnowszą kompilację niejawnych testerów za pośrednictwem usługi [ARC](hololens-insider.md#ffu-download-and-flash-directions) lub rejestrując i [aktualizując urządzenie.](hololens-insider.md#start-receiving-insider-builds)
   - Uwaga: Ta kompilacja jest obecnie dostępna tylko w [niejawnym kanale deweloperów.](hololens-insider.md#start-receiving-insider-builds)
2. Włączanie [trybu dewelopera i Portal urządzeń](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

## <a name="enabling-moving-platform-mode"></a>Włączanie trybu przenoszenia platformy

Aby włączyć tryb przenoszenia platformy, najpierw [włącz Portal urządzeń](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).

1. Wybierz pozycję **System** accordion w menu po lewej stronie
2. Wybierz stronę **Przenoszenie trybu platformy** i zaznacz pole wyboru Przenoszenie **trybu** platformy

   ![Pierwszy obraz](.\images\moving-platform-1x.png)
 
     ![Drugi obraz](.\images\moving-platform-2x.png)

3. Po wyświetleniu monitu z ostrzeżeniem wybierz przycisk **OK**

   ![Trzeci obraz](.\images\moving-platform-3x.png)

4. Uruchom ponownie urządzenie, co można wykonać za pomocą menu Portal urządzeń **Power** w prawym górnym rogu lub przez wydanie następującego polecenia głosowego Uruchom ponownie urządzenie i wybierz &quot; pozycję &quot; &quot; &quot; Tak.

   ![Czwarty obraz](.\images\moving-platform-4x.png)

Jeśli nie widzisz opcji Przenoszenie trybu platformy w Portal urządzeń, prawdopodobnie oznacza to, że nie jesteś jeszcze w odpowiedniej kompilacji. Zobacz [sekcję Wymagania](#prerequisites) wstępne.
