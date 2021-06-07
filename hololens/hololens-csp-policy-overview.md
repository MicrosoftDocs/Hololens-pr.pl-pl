---
title: Konfigurowanie CSP i Zarządzanie urządzeniami omówienie
description: Dowiedz się, jak skonfigurować CSP, zasady i zarządzanie urządzeniami przy użyciu pakietów Zarządzanie urządzeniami mobilnych i aprowizowania.
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
ms.openlocfilehash: 60e73a9a70a70c5c583edc73a0add2f0f502ef80
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378392"
---
# <a name="configure-csps-and-device-management-overview"></a>Konfigurowanie CSP i Zarządzanie urządzeniami omówienie

Administratorzy IT mogą definiować i implementować ustawienia zasad na urządzeniach HoloLens 2. Ustawienia konfiguracji, których użyjemy, różnią się w zależności od scenariusza wdrażania, a urządzenia firmowe będą oferować it najszerszy zakres kontroli. W Windows 10 dostawcy usług konfiguracji (CSP) to interfejs do odczytywania, konfigurowania, modyfikowania lub usuwania ustawień konfiguracji na urządzeniu. Te ustawienia są mapowe na klucze lub pliki rejestru. Niektórzy dostawcy usług konfiguracji obsługują format WAP, niektórzy obsługują syncML, a niektórzy obsługują oba te formaty.

Aby uzyskać więcej informacji na Windows 10 Holographic zarządzania urządzeniami, zobacz pełną listę adresów CSP obsługiwanych na [urządzeniach HoloLens.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)
Administratorzy IT mogą również zarządzać programem Policy CSP na urządzeniach. Zobacz pełną listę serwerów CSP zasad obsługiwanych przez [urządzenie HoloLens 2.](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="configuration-methods"></a>Metody konfiguracji

### <a name="configure-with-mdm"></a>Konfigurowanie przy użyciu rozwiązania MDM

Usługami CSP i zasadami można łatwo zarządzać na dowolnym urządzeniu osobistym lub firmowym zarejestrowanym w systemie MDM. Po zarejestrowaniu urządzenia w rozwiązaniu MDM będzie można zarządzać tym urządzeniem lub zestawem urządzeń przy użyciu konfiguracji urządzeń. Dowiedz się więcej na temat zarządzania [urządzeniami HoloLens za pomocą rozwiązania MDM.](hololens-mdm-configure.md)

### <a name="configure-with-provisioning-packages"></a>Konfigurowanie za pomocą pakietów aprowizowania

Urządzenie HoloLens 2 obsługuje również ustawianie ograniczonego zestawu konfiguracji CSP dla urządzeń HoloLens 2 za pośrednictwem niestandardowych pakietów aprowingu. Pakiety aprowizowania są zwykle używane w przypadku urządzeń innych niż zarządzane przez rozwiązanie MDM i wymagają ręcznego zastosowania do każdego urządzenia. Przeczytaj informacje na temat tworzenia niestandardowych [pakietów aprowizowania dla urządzenia HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="configurations"></a>Konfiguracje

### <a name="common-device-restrictions"></a>Typowe ograniczenia dotyczące urządzeń

Niektóre ograniczenia dotyczące urządzeń są tak proste, jak wyłączenie funkcjonalności lub połączenia z urządzeniem. Aby dowiedzieć się więcej o tych ograniczeniach, przeczytaj [więcej na temat typowych ograniczeń dotyczących urządzeń.](hololens-common-device-restrictions.md)

### <a name="kiosk-modes"></a>Tryby kiosku

Użyj trybu kiosku, aby kontrolować, które tożsamości mają domyślnie dostęp do których aplikacji. Kiosków można używać dla jednej aplikacji lub wielu interfejsów użytkownika aplikacji. Konfiguracje kiosku mogą się różnić od pojedynczej aplikacji dla każdego, kto korzysta z urządzenia, po różne aplikacje dla różnych grup. Tryb kiosku nie zatrzymuje uruchamiania innych aplikacji przez "dozwolone aplikacje" i nie był nigdy przeznaczony. Aby dowiedzieć się więcej, zapoznaj się [z tematem Tryby kiosku i sposoby ich używania.](hololens-kiosk.md)

### <a name="settings-page-visibility"></a>Widoczność strony ustawień

Użyj zasad aplikacji Ustawienia, aby kontrolować, które tożsamości domyślnie mają dostęp do ustawień. Za pomocą tych zasad aplikację Ustawienia można skonfigurować tak, aby wyświetlała tylko wybrane strony lub ukrywała wszystkie wybrane strony. [Przeczytaj o tym, jak skonfigurować dostępne strony.](settings-uri-list.md)

Ta funkcja jest obecnie dostępna tylko [w niejawny tester systemu Windows kompilacjach.](hololens-insider.md) Upewnij się, że urządzenia, dla których zamierzasz używać tej funkcji, są w kompilacji 19041.1349+.

### <a name="wdac"></a>WDAC

Konfiguracja funkcji WDAC umożliwia kontrolowanie, które aplikacje/procesy mają być dozwolone lub niedozwolone niezależnie od tego, czy system jest w trybie kiosku, czy nie.
[Zobacz nasze omówienie usług WDAC.](windows-defender-application-control-wdac.md)
