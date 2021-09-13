---
title: Konfigurowanie CSP i Zarządzanie urządzeniami omówienie
description: Dowiedz się, jak skonfigurować CSP, zasady i zarządzanie urządzeniami przy użyciu pakietów Zarządzanie urządzeniami mobilnych i inicjowania obsługi administracyjnej.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b312f9d20c9a75c5e4c1906c4ec55f42fda977f6
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032945"
---
# <a name="configure-csps-and-device-management-overview"></a>Konfigurowanie CSP i Zarządzanie urządzeniami omówienie

Administratorzy IT mogą definiować i implementować ustawienia zasad na HoloLens 2. Ustawienia konfiguracji, których używasz, będą się różnić w zależności od scenariusza wdrażania, a urządzenia firmowe będą oferować it najszerszy zakres kontroli. W Windows 10 dostawcy usług konfiguracji (CSP) to interfejs do odczytywania, konfigurowania, modyfikowania lub usuwania ustawień konfiguracji na urządzeniu. Te ustawienia są mapowanie na klucze rejestru lub pliki. Niektórzy dostawcy usług konfiguracji obsługują format WAP, niektórzy obsługują syncML, a niektórzy obsługują oba te formaty.

Aby uzyskać więcej informacji o Windows 10 Holographic zarządzania urządzeniami, zobacz pełną listę CSP obsługiwanych na [HoloLens urządzeniach.](/windows/client-management/mdm/configuration-service-provider-reference#hololens)
Administratorzy IT mogą również zarządzać programem Policy CSP na urządzeniach. Zobacz pełną listę administratorów CSP zasad obsługiwanych przez program [HoloLens 2.](/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="configuration-methods"></a>Metody konfiguracji

### <a name="configure-with-mdm"></a>Konfigurowanie przy użyciu rozwiązania MDM

Usługami CSP i zasadami można łatwo zarządzać na dowolnym urządzeniu osobistym lub firmowym zarejestrowanym w systemie MDM. Po zarejestrowaniu urządzenia w rozwiązaniu MDM będzie można zarządzać tym urządzeniem lub zestawem urządzeń przy użyciu konfiguracji urządzeń. Dowiedz się więcej na temat zarządzania [urządzeniami przenośnymi HoloLens zarządzania urządzeniami przenośnymi.](hololens-mdm-configure.md)

### <a name="configure-with-provisioning-packages"></a>Konfigurowanie za pomocą pakietów aprowizowania

HoloLens 2 obsługuje również ustawianie ograniczonego zestawu konfiguracji CSP dla urządzeń HoloLens 2 za pośrednictwem niestandardowych pakietów aprowingu. Pakiety aprowizowania są zwykle używane w przypadku urządzeń innych niż zarządzane przez rozwiązanie MDM i wymagają ręcznego zastosowania do każdego urządzenia. Przeczytaj informacje na temat tworzenia [niestandardowych pakietów aprowizowania dla HoloLens](hololens-provisioning.md).

## <a name="configurations"></a>Konfiguracje

### <a name="common-device-restrictions"></a>Typowe ograniczenia dotyczące urządzeń

Niektóre ograniczenia dotyczące urządzeń są równie proste i wyłączane są funkcje lub połączenia z urządzeniem. Aby dowiedzieć się więcej o tych ograniczeniach, przeczytaj [więcej na temat typowych ograniczeń urządzenia.](hololens-common-device-restrictions.md)

### <a name="kiosk-modes"></a>Tryby kiosku

Użyj trybu kiosku, aby kontrolować, które tożsamości mają domyślnie dostęp do których aplikacji. Kiosków można używać dla jednej aplikacji lub wielu interfejsów użytkownika aplikacji. Konfiguracje kiosku mogą się różnić od pojedynczej aplikacji dla każdego, kto korzysta z urządzenia, po różne aplikacje dla różnych grup. Tryb kiosku nie zatrzymuje uruchamiania innych aplikacji przez "dozwolone aplikacje" i nie był nigdy przeznaczony. Dowiedz się [więcej, czytając o trybach kiosku i używaniu ich.](hololens-kiosk.md)

### <a name="settings-page-visibility"></a>Ustawienia Widoczność strony

Użyj Ustawienia zasad aplikacji, aby kontrolować, które tożsamości mają domyślnie dostęp do ustawień. Za pomocą tych zasad Ustawienia aplikację można skonfigurować tak, aby wyświetlała tylko wybrane strony lub ukrywała wszystkie wybrane strony. [Przeczytaj o tym, jak skonfigurować dostępne strony.](settings-uri-list.md)

Ta funkcja jest obecnie dostępna tylko w [kompilacjach niejawnych Windows niejawnych testerów.](hololens-insider.md) Upewnij się, że urządzenia, dla których zamierzasz używać tej funkcji, są w kompilacji 19041.1349+.

### <a name="wdac"></a>WDAC

Konfiguracja funkcji WDAC umożliwia kontrolowanie, które aplikacje/procesy mają być dozwolone/niedozwolone niezależnie od tego, czy system jest w trybie kiosku.
[Zobacz nasze omówienie funkcji WDAC.](windows-defender-application-control-wdac.md)
