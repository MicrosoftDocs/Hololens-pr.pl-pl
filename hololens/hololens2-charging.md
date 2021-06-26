---
title: HoloLens 2 Battery and Charging
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
ms.openlocfilehash: acbc3e52240f420d384fa372684966d7220d53c6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923588"
---
# <a name="hololens-2-battery-and-charging"></a>HoloLens 2 Battery and Charging

Ta strona zawiera szczegółowe informacje o ładowaniu urządzenia HoloLens 2 i używaniu zewnętrznych pakietów baterii.

## <a name="charging-the-device"></a>Ładowanie urządzenia

Użyj [kabla usb typu C,](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) który jest podłączony do urządzenia HoloLens 2, ponieważ jest to najlepszy sposób ładowania urządzenia. Urządzenie HoloLens 2 zapewnia do 9V przy 2A (18W). Wraz z dostarczonym urządzeniem naścienowym urządzenie HoloLens 2 może w ciągu mniej niż 65 minut ładować baterii, gdy urządzenie jest w stanie wstrzymania. Jeśli te akcesoria nie są dostępne, upewnij się, że dostępne akcesoria mogą obsługiwać moc co najmniej 15 W.

> [!NOTE]
> Jeśli to możliwe, unikaj używania komputera do ładowania urządzenia przez port USB, który działa wolno.

## <a name="checking-the-battery-charge-level"></a>Sprawdzanie poziomu naładowania baterii
Jeśli urządzenie jest prawidłowo uruchomione, istnieją trzy sposoby sprawdzenia poziomu naładowania baterii:

- Z menu głównego interfejsu użytkownika urządzenia HoloLens.
- Wyświetl diodę LED w pobliżu przycisku zasilania (w przypadku 40-procentowego naładowania powinny być co najmniej dwie ciągłe diody LED).
    - Gdy urządzenie jest ładowane, wskaźnik naładowania baterii jest osłaniany, aby wskazać bieżący poziom naładowania.  Ostatnie światło zaniknie i pojawi się, aby wskazać aktywne opłaty.
    - Gdy urządzenie HoloLens jest wł., wskaźnik naładowania baterii wyświetla poziom naładowania baterii z pięcioma przyrostami.
    - Gdy tylko jedno z pięciu światła jest wł., poziom naładowania baterii jest poniżej 20 procent.
    - Jeśli poziom naładowania baterii jest krytycznie niski i spróbujesz włączyć urządzenie, jedno światło miga przez krótki czas, a następnie wychodzie.
- Na komputerze hosta otwórz okno **Eksplorator plików** i poszukaj urządzenia HoloLens 2 po lewej stronie w obszarze **Ten komputer**. Kliknij prawym przyciskiem myszy urządzenie, a następnie wybierz pozycję **Właściwości.** Zostanie wyświetlone okno dialogowe z poziomem naładowania baterii.

   ![Ekran właściwości urządzenia HoloLens 2 pokazuje poziom zmiany baterii](images/ResetRecovery2.png)

## <a name="alternative-charging-specifications"></a>Alternatywne specyfikacje dotyczące opłat

Urządzenie HoloLens 2 można ładować za pomocą źródeł [zasilania USB](https://www.usb.org/usb-charger-pd) o mocy do 27 watów. Jeśli źródło jest w stanie dostarczyć co najmniej 10 watów, czas działania urządzenia HoloLens można wydłużyć (potencjalnie na czas nieokreślony dla niektórych obciążeń). 

> [!NOTE]
> Użycie kabla ładowania USB-A do USB-C spowoduje ograniczenie opłaty do 7,5 Watów. Czas pracy nadal zostanie wydłużony, ale nie tak długo, jak długo będzie używać usb-C do C.

Gdy urządzenie HoloLens jest w trybie rezerwy, 18 watów jest wystarczające do osiągnięcia maksymalnej szybkości ładowania baterii wewnętrznej. Gdy urządzenie HoloLens jest w użyciu, stawka opłaty może zostać obniżona, ponieważ urządzenie HoloLens ma priorytet operacyjny od opłat.

> [!IMPORTANT]
> Zaleca się, aby opłata za urządzenie HoloLens 2 była naliczana co najmniej przy wartości 5V/1,5 A. Nie należy używać zasilaczy, które nie mogą dostarczyć co najmniej 5V/1,5A. 

### <a name="external-battery-packs"></a>Zewnętrzne pakiety baterii

Z urządzeniem HoloLens 2 można używać pakietów baterii spełniających powyższe specyfikacje. Należy jednak pamiętać, że niektóre pakiety baterii USB-C są ładowane i zapewniają zasilanie za pośrednictwem tego samego portu USB-C. Ważne jest, aby te pakiety baterii implementują [try. SRC,](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) aby upewnić się, że urządzenie HoloLens jest ładowane, a nie naliczane z niego opłaty. 

### <a name="managing-heat"></a>Zarządzanie ciepłom

Podobnie jak w przypadku dowolnego urządzenia, ładowanie urządzenia HoloLens generuje ciepło. Im szybsze ładowanie, tym więcej ciepła jest generowane. Ponadto uruchomienie ładowania na niższym poziomie baterii spowoduje wygenerowanie większej energii cieplnej niż w przypadku, gdy poziom naładowania baterii jest w większości pełny. Klienci, którzy muszą korzystać z urządzenia HoloLens przez dłuższy czas w gorących środowiskach, mogą używać następujących technik:

- Urządzenie HoloLens 2 można podłączyć do zewnętrznego źródła zasilania nawet wtedy, gdy wewnętrzna bateria jest w pełni obciążona.
- Po wyczerpaniu baterii zewnętrznej urządzenie HoloLens będzie nadal działać na wewnętrznej baterii.    
- Jeśli po powyższych krokach nadal występuje problem z ciepłom, rozważ użycie baterii lub baterii, która ogranicza poziom ładowania do 1,5 A. Pamiętaj, że ta opcja nie zapewni tak dużo czasu pracy, ponieważ wewnętrzny poziom baterii będzie nadal powoli wyczerpywalny.

## <a name="troubleshooting"></a>Rozwiązywanie problemów


### <a name="hololens-charges-external-battery"></a>Zewnętrzna bateria ładowania urządzenia HoloLens
Jeśli urządzenie HoloLens 2 jest zasilane z baterii zewnętrznej, a nie przez nie, oznacza to, że baterii nie implementuje [try. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). Przełączenie do nowszego pakietu baterii jest zalecanym sposobem rozwiązania tego problemu, ale alternatywnie możesz spróbować przełączyć się na kabel USB-A na USB-C. Należy pamiętać, że spowoduje to ograniczenie stawki do 7,5 watów.
