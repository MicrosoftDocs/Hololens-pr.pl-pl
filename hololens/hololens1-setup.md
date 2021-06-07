---
title: Przygotowywanie nowego urządzenia HoloLens
description: Dowiedz się, jak po raz pierwszy przygotować, dostosować i skonfigurować urządzenie rzeczywistości mieszanej HoloLens (1. generacji).
ms.prod: hololens
ms.sitesec: library
author: JesseMcCulloch
ms.author: jemccull
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/12/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- Hololens (1st gen)
ms.openlocfilehash: 30912fda53d5d8b9ea5e60f29eeb93ea29cca2d2
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378327"
---
# <a name="get-your-hololens-1st-gen-ready-to-use"></a>Przygotuj urządzenie HoloLens (1. generacja) do użycia

Postępuj zgodnie z śledzeniami, aby po raz pierwszy skonfigurować urządzenie HoloLens (1. generacja).

## <a name="charge-your-hololens-1st-gen"></a>Ładowanie urządzenia HoloLens (1. generacja)

Aby naładować urządzenie HoloLens, podłącz zasilacz do portu ładowania przy użyciu dołączonego kabla Micro USB. Następnie podłącz zasilacz do źródła zasilania. Gdy urządzenie jest ładowane, wskaźnik naładowania baterii będzie się rozświetlać we wzorcu falowym.

![Obraz, na który pokazano, jak podłączyć kabel Micro USB do urządzenia HoloLens](./images/hololens-charging.png)

Gdy urządzenie HoloLens jest wł., wskaźnik naładowania baterii pokazuje poziom naładowania baterii w przyrostach. Gdy tylko jedno z pięciu światła jest w zasilania, poziom naładowania baterii jest poniżej 20 procent. Jeśli poziom naładowania baterii jest krytycznie niski i spróbujesz włączyć urządzenie, jedno światło miga krótko, a następnie wygania.

> [!TIP]
> Aby oszacować bieżący poziom naładowania baterii, powiedz "Hey Cortana, how much battery do I have left?" (Hej Cortana, ile baterii pozostało?"

Zasilacz i kabel USB, które są wyposażone w urządzenie, to najlepszy sposób ładowania urządzenia HoloLens (pierwszej generacji).  Zasilacz zapewnia moc 18 W (9V 2A).

Szybkość i szybkość ładowania mogą się różnić w zależności od środowiska, w którym działa urządzenie.

## <a name="adjust-fit"></a>Dopasowywanie dopasowania

> [!VIDEO https://www.microsoft.com/videoplayer/embed/be3cb527-f2f1-4f85-b4f7-a34fbaba980d]

|     |     |
|:--- |:--- |
|1. Obróć pałąk w górę do około 20–30 stopni.|![Krok 1. Obracanie pałąka](./images/FitGuideStep1.png)|
|2. Wypchnąć z powrotem pałąk. Nie ściągaj go z powrotem ani nie manipuluj pasmem za chybem, ponieważ z czasem może to przerwać zespół.|![Krok 2. Wypchnąć z powrotem pałąk](./images/FitGuideStep2.png)|
|3. Obrócić koło korekty, aby rozszerzyć pasek na całej drodze. |![Krok 3. Rozszerzanie pałąka przy użyciu kółka regulacji](./images/FitGuideStep3.png)|
|4. Przytrzymaj urządzenie przy ramce urządzenia i umieść je na głowy. Upewnij się, że pałąk znajduje się w górnej części twojego koła, a następnie zwężaj koło korekty.|![Krok 4. Włóż urządzenie i dostosuj pasek](./images/FitGuideStep4.png)|
|5. Przesuń daszek z powrotem, a następnie sprawdź dopasowanie urządzenia. Pałąk powinien być w górnej części głowy, tuż poniżej linii głowy, z prelegentami nad Twoimi cygami. Obiektywy powinny być wyśrodkowane na oku.|![Krok 5. Przesuń daszek do tyłu i sprawdź dopasowanie](./images/FitGuideSetep5.png)|

## <a name="turn-on-your-hololens"></a>Włączanie urządzenia HoloLens

Użyj przycisku zasilania, aby włączyć i wyłączyć urządzenie HoloLens lub przełączyć je w tryb wstrzymania.

![Obraz z przyciskiem zasilania urządzenia HoloLens](./images/hololens-power.png)

Jeśli urządzenie nie odpowiada lub nie uruchamia się, zobacz [Restart, reset, or recover HoloLens (Ponowne uruchamianie, resetowanie lub odzyskiwanie urządzenia HoloLens).](hololens-restart-recover.md)

Gdy urządzenie HoloLens jest wyłączone lub jest w stanie wstrzymania, włącz je, naciskając przycisk zasilania przez jedną sekundę. Jeśli nie zostanie ona włączyć, podłącz ją i załaduj ją przez co najmniej 30 minut.

> [!TIP]
> Aby ponownie uruchomić urządzenie HoloLens, powiedz "Hey Cortana, reboot the device".

### <a name="put-hololens-in-standby"></a>Umieść urządzenie HoloLens w stanie wstrzymania

Aby umieścić urządzenie HoloLens w stanie wstrzymania, gdy jest włączone, naciśnij raz przycisk zasilania. Wskaźniki baterii migają. Aby wznowić ją ze stanu wstrzymania, naciśnij ponownie przycisk zasilania.

Urządzenie HoloLens automatycznie przechodzi w stan wstrzymania po 3 minutach braku aktywności. Gdy jest w stanie gotowości, automatycznie wyłącza się po 4 godzinach lub gdy poziom naładowania baterii spadnie o 10 procent.

### <a name="shut-down-hololens"></a>Zamykanie urządzenia HoloLens

Aby wyłączyć (wyłączyć) urządzenie HoloLens, przytrzymaj przycisk zasilania na cztery sekundy. Wskaźniki baterii wyłączają się jeden po drugiej, a urządzenie jest zamykane.

Urządzenie HoloLens jest automatycznie wyłączane, gdy poziom naładowania baterii spadnie do jednego procenta, nawet jeśli jest podłączony do sieci. Po naładowaniu baterii do trzech procent będzie można ponownie włączyć urządzenie HoloLens.

## <a name="adjust-volume-and-brightness"></a>Dostosowywanie głośności i jasność

Przyciski jasność i regulacji głośności znajdują się na górze głośności urządzenia i znajdują się po prawej stronie, a &mdash; przyciski jasność po lewej stronie.

![Obraz z przyciskami urządzenia HoloLens](./images/hololens-buttons.jpg)

## <a name="hololens-indicator-lights"></a>Wskaźniki HoloLens

![Obraz, na przykładzie wskaźników HoloLens](./images/hololens-lights.png)

Nie masz pewności, co oznaczają wskaźniki na urządzeniach HoloLens? Oto kilka pomocy.

|Kiedy światła to robią |Oznacza, że |
| - | - |
|Przewiń od środka na zewnątrz. |Urządzenie HoloLens jest uruchamiane. |
|Pozostań oświetlony (wszystkie lub niektóre). |Urządzenie HoloLens jest wł. i jest gotowe do użycia. Czas pracy baterii jest wyświetlany w przyrostach o 20 procent. |
|Przewiń, a następnie zajmij światło, a następnie przewiń. |Urządzenie HoloLens jest wł. i jest ładowane. Czas pracy baterii jest wyświetlany w przyrostach o 20 procent. |
|Wyłącz po kolei. |Urządzenie HoloLens jest zamykane. |
|Wyłącz wszystkie jednocześnie. |Urządzenie HoloLens przechodzi w stan wstrzymania. |
|Wszystko jest zasysane, a następnie miga na krótko, a wszystkie są wyłączane. |Poziom naładowania baterii jest bardzo niski. Urządzenie HoloLens musi być ładowane. |
|Wszystkie przewijanie, następnie jedno miga, a następnie wszystkie przewijanie. |Poziom naładowania baterii jest bardzo niski. Urządzenie HoloLens jest ładowane. |

## <a name="safety-and-comfort"></a>Bezpieczeństwo i komfort

### <a name="use-in-safe-surroundings"></a>Używanie w bezpiecznym środowisku

Urządzenia HoloLens można używać w bezpiecznym miejscu, które nie ma żadnych przeszkód i zagrożeń. Nie używaj go, gdy potrzebujesz jasnego pola widzenia i twojej pełnej uwagi, na przykład podczas obsługi pojazdu lub wykonywania innych potencjalnie niebezpiecznych działań.

### <a name="stay-comfortable"></a>Nie przejmuj się

Zachowaj krótki czas pierwszych kilku sesji z urządzeniem HoloLens i pamiętaj, aby zrobić przerwy. Jeśli masz doświadczenie w pracy, zatrzymywaj się i odpoczywaj, dopóki nie poczujesz się lepiej. Może to obejmować tymczasowe odczucie chłoniaka, ruch po ruchach, pogorsze, dezorientację, chłoniak, odmężenie oczu lub suchość oczu.

> [!div class="nextstepaction"]
> [Uruchamianie i konfigurowanie urządzenia HoloLens (1. generacja)](hololens1-start.md)
