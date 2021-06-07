---
title: Baterii i ładowania
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
ms.openlocfilehash: 15ecc698a515987857f556fed97d74f861cd6b20
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379816"
---
# <a name="battery-and-charging"></a>Baterii i ładowania

Ta strona zawiera szczegółowe informacje o ładowaniu urządzenia HoloLens 2 i używaniu zewnętrznych pakietów baterii.

## <a name="included-charger"></a>Uwzględniony wańcowy

Urządzenie HoloLens 2 zapewnia do 9V przy 2A (18W). Jeśli to możliwe, zdecydowanie zaleca się naliczanie opłat za pomocą dołączonej baterii.  

## <a name="specifications"></a>Specyfikacje

Urządzenie HoloLens 2 można ładować za pomocą źródeł [zasilania USB](https://www.usb.org/usb-charger-pd) o mocy do 27 watów. Jeśli źródło jest w stanie dostarczyć co najmniej 10 watów, czas działania urządzenia HoloLens można wydłużyć (potencjalnie na czas nieokreślony dla niektórych obciążeń). 

> [!NOTE]
> Użycie kabla ładowania USB-A do USB-C spowoduje ograniczenie opłaty do 7,5 Watów. Czas pracy nadal zostanie wydłużony, ale nie tak długo, jak długo będzie używać usb-C do C.

Gdy urządzenie HoloLens jest w trybie rezerwy, 18 watów jest wystarczające, aby osiągnąć maksymalną stawkę za wewnętrzną baterii. Gdy urządzenie HoloLens jest w użyciu, stawka opłaty może zostać obniżona, ponieważ urządzenie HoloLens ma priorytet operacyjny od opłat.

> [!IMPORTANT]
> Zaleca się, aby opłata za urządzenie HoloLens 2 była naliczana co najmniej przy wartości 5V/1,5 A. Nie należy używać zasilaczy, które nie mogą dostarczyć co najmniej 5V/1,5A. 

## <a name="external-battery-packs"></a>Zewnętrzne pakiety baterii

Z urządzeniem HoloLens 2 można używać pakietów baterii, które spełniają powyższe specyfikacje. Należy jednak pamiętać, że niektóre pakiety baterii USB-C są ładowane i zapewniają zasilanie za pośrednictwem tego samego portu USB-C. Ważne jest, aby te pakiety baterii implementują [try. SRC,](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20) aby upewnić się, że urządzenie HoloLens jest ładowane, a nie naliczane z niego opłaty. 

## <a name="managing-heat"></a>Zarządzanie ciepłom

Podobnie jak w przypadku dowolnego urządzenia, ładowanie urządzenia HoloLens generuje ciepło. Im szybsze ładowanie, tym więcej ciepła jest generowane. Ponadto uruchomienie ładowania na niższym poziomie baterii spowoduje wygenerowanie większej energii cieplnej niż w przypadku, gdy poziom naładowania baterii jest w większości pełny. Klienci, którzy muszą korzystać z urządzenia HoloLens przez dłuższy czas w gorących środowiskach, mogą używać następujących technik:

- Urządzenie HoloLens 2 można podłączyć do zewnętrznego źródła zasilania nawet wtedy, gdy wewnętrzna bateria jest w pełni obciążona.
- Po wyczerpaniu baterii zewnętrznej urządzenie HoloLens będzie nadal działać na wewnętrznej baterii.    
- Jeśli po powyższych krokach nadal występuje problem z ciepłom, rozważ użycie baterii lub baterii, która ogranicza poziom ładowania do 1,5 A. Pamiętaj, że ta opcja nie zapewni tak dużo czasu pracy, ponieważ poziom naładowania baterii wewnętrznej będzie nadal powoli wyczerpywalny.

## <a name="troubleshooting"></a>Rozwiązywanie problemów


### <a name="hololens-charges-external-battery"></a>Zewnętrzna bateria ładowania urządzenia HoloLens
Jeśli urządzenie HoloLens 2 jest zasilane z baterii zewnętrznej, a nie przez nie, oznacza to, że baterii nie implementuje [try. SRC](https://usb.org/document-library/usb-type-cr-cable-and-connector-specification-revision-20). Przełączanie do nowszego pakietu baterii jest zalecanym sposobem rozwiązania tego problemu, ale alternatywnie możesz spróbować przełączyć się na kabel USB-A na USB-C. Należy pamiętać, że spowoduje to ograniczenie stawki do 7,5 watów.
