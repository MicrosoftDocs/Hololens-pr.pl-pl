---
title: HoloLens 2 baterii i ładowania
description: Jak ładować urządzenie HoloLens i używać zewnętrznych pakietów baterii.
ms.assetid: E0AB903E-454E-46F6-AB25-4DFA0A475B0C
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 05/14/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: b4692468942da88877370864eda2ce173cc499af
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036471"
---
# <a name="hololens-2-battery-and-charging"></a>HoloLens 2 baterii i ładowania

Ta strona zawiera szczegółowe informacje o ładowaniu HoloLens 2 i używaniu zewnętrznych pakietów baterii.

## <a name="charging-the-device"></a>Ładowanie urządzenia

Użyj [kabla USB typu C,](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) który jest HoloLens 2, ponieważ jest to najlepszy sposób ładowania urządzenia. Nawiązana z HoloLens 2 zapewnia do 9V @ 2A (18W). Wraz z dostarczonym osłoną ściany HoloLens 2 urządzenia mogą ładować baterii do pełnej w czasie krótszym niż 65 minut, gdy urządzenie jest w stanie wstrzymania. Jeśli te akcesoria nie są dostępne, upewnij się, że dostępne akcesoria mogą obsługiwać moc co najmniej 15 W.

> [!NOTE]
> Jeśli to możliwe, unikaj używania komputera do ładowania urządzenia za pośrednictwem portu USB, co działa wolno.

## <a name="checking-the-battery-charge-level"></a>Sprawdzanie poziomu naładowania baterii
Jeśli urządzenie jest prawidłowo uruchomione, istnieją trzy sposoby sprawdzania poziomu naładowania baterii:

- Z menu głównego interfejsu użytkownika HoloLens urządzenia.
- Wyświetl diodę LED w pobliżu przycisku zasilania (w przypadku opłaty 40 procent powinna być co najmniej dwie ciągłe diody LED).
    - Gdy urządzenie jest ładowane, wskaźnik baterii jest zapalany, aby wskazać bieżący poziom naładowania.  Ostatnie światło będzie zanikać i zanikać, aby wskazać aktywne ładowanie.
    - Gdy urządzenie HoloLens, wskaźnik baterii wyświetla poziom naładowania baterii w pięciu przyrostach.
    - Gdy tylko jedno z pięciu światła jest w zasilania, poziom naładowania baterii jest poniżej 20 procent.
    - Jeśli poziom naładowania baterii jest krytycznie niski i spróbujesz włączyć urządzenie, jedno światło miga krótko, a następnie wygania.
- Na komputerze hosta otwórz **Eksplorator plików** i poszukaj urządzenia z systemem HoloLens 2 po lewej stronie w obszarze Ten **komputer.** Kliknij prawym przyciskiem myszy urządzenie, a następnie wybierz pozycję **Właściwości.** Zostanie wyświetlone okno dialogowe z poziomem naładowania baterii.

   ![Ekran HoloLens 2 przedstawia poziom zmiany baterii.](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a>Alternatywne specyfikacje dotyczące opłat

HoloLens 2 można ładować za pomocą źródeł [zasilania USB](https://www.usb.org/usb-charger-pd) o mocy do 27 watów. Jeśli źródło jest w stanie dostarczyć co najmniej 10 watów, HoloLens czasu pracy można wydłużyć (potencjalnie przez czas nieokreślony dla niektórych obciążeń). 

> [!NOTE]
> Użycie kabla ładujące USB-A do USB-C spowoduje ograniczenie opłaty do 7,5 Watów. Czas pracy nadal zostanie wydłużony, ale nie tak długo, jak przy użyciu USB-C do C.

Gdy HoloLens jest w trybie rezerwy, 18 Watów jest wystarczające, aby osiągnąć maksymalną szybkość ładowania baterii wewnętrznej. Gdy HoloLens jest już w użyciu, stawka opłaty może zostać obniżona, ponieważ HoloLens priorytetów operacyjnych nad naliczaniami.

> [!IMPORTANT]
> Zaleca się, aby za HoloLens 2 było naliczane co najmniej 5V/1,5 A. Nie należy używać 5V/1,5A, które nie mogą dostarczać co najmniej 5V/1,5A. 

### <a name="external-battery-packs"></a>Zewnętrzne pakiety baterii

Pakiety baterii spełniające powyższe specyfikacje mogą być używane z HoloLens 2. Należy jednak pamiętać, że niektóre pakiety baterii USB-C są ładowane i zapewniają zasilanie za pośrednictwem tego samego portu USB-C. Ważne jest, aby te pakiety baterii implementować [try. SRC,](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) aby upewnić się, że HoloLens opłaty, a nie opłaty z niego. 

### <a name="managing-heat"></a>Zarządzanie ciepłom

Podobnie jak w przypadku każdego urządzenia, HoloLens generuje ciepło. Im szybsze ładowanie, tym więcej ciepła jest generowanych. Ponadto rozpoczęcie ładowania na niższym poziomie baterii spowoduje wygenerowanie większej energii cieplnej niż podczas ładowania, gdy bateria jest w większości pełna. Klienci, którzy muszą HoloLens przez dłuższy czas w gorących środowiskach, mogą korzystać z następujących technik:

- Można podłączyć urządzenie HoloLens 2 do zewnętrznego źródła zasilania, nawet jeśli wewnętrzna bateria jest w pełni obciążona.
- Po wyczerpaniu baterii zewnętrznej HoloLens będzie nadal zasilana z baterii wewnętrznej.    
- Jeśli po powyższych krokach nadal występuje problem z ciepłom, rozważ użycie baterii lub baterii, która ogranicza ładowanie do 1,5 A. Należy pamiętać, że ta opcja nie zapewni tak dużo czasu pracy, ponieważ bateria wewnętrzna nadal będzie powoli zubożone.

## <a name="troubleshooting"></a>Rozwiązywanie problemów


### <a name="hololens-charges-external-battery"></a>HoloLens Opłaty za zewnętrzną pojemność baterii
Jeśli HoloLens 2 ładuje zewnętrzną baterii, a nie ładowane przez niego, oznacza to, że baterii nie implementuje [TRY. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). Przełączenie do nowszego pakietu baterii jest zalecanym sposobem rozwiązania tego problemu, ale alternatywnie możesz spróbować przełączyć się na kabel USB-A na USB-C. Należy pamiętać, że spowoduje to ograniczenie stawki ładowania do 7,5 watów.
