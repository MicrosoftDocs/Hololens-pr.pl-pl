---
title: Menedżer certyfikatów
description: Dowiedz się, jak ręcznie instalować i usuwać certyfikaty oraz zarządzać nimi na urządzeniach z rzeczywistością mieszaną HoloLens 2.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 8b1869e786e3f3324494cecbfd596f61811e1893
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427640"
---
# <a name="certificate-manager"></a>Menedżer certyfikatów

- Ulepszono narzędzia do inspekcji, diagnostyki i walidacji w celu zapewnienia bezpieczeństwa i zgodności urządzeń za pośrednictwem nowego Menedżera certyfikatów. Ta funkcja umożliwi wdrażanie, rozwiązywanie problemów i weryfikowanie certyfikatów na dużą skalę w środowiskach komercyjnych.

Na platformie Windows Holographic w wersji 20H2 dodajemy Menedżera certyfikatów w aplikacji Ustawienia urządzenia HoloLens 2. Przejdź do **ustawień > Aktualizacji & zabezpieczeń > certyfikatów**. Ta funkcja zapewnia prosty i przyjazny dla użytkownika sposób wyświetlania, instalowania i usuwania certyfikatów na urządzeniu. Dzięki noweowi Menedżerowi certyfikatów administratorzy i użytkownicy mają teraz ulepszone narzędzia do inspekcji, diagnostyki i walidacji, aby zapewnić, że urządzenia pozostaną bezpieczne i zgodne. 

-   **Inspekcja:** Możliwość zweryfikowania, czy certyfikat został wdrożony poprawnie, lub potwierdzenia, że został on odpowiednio usunięty. 
-   **Diagnostyka:** W przypadku problemów podczas sprawdzania, czy na urządzeniu istnieją odpowiednie certyfikaty, można zaoszczędzić czas i pomóc w rozwiązywaniu problemów. 
-   **Walidacja:** Sprawdzenie, czy certyfikat służy zamierzony i działa, może zaoszczędzić dużo czasu, szczególnie w środowiskach komercyjnych, przed wdrożeniem certyfikatów na większą skalę.

Aby szybko znaleźć konkretny certyfikat na liście, dostępne są opcje sortowania według nazwy, magazynu lub daty wygaśnięcia. Użytkownicy mogą również bezpośrednio wyszukać certyfikat. Aby wyświetlić właściwości poszczególnych certyfikatów, wybierz certyfikat i kliknij pozycję **Informacje.** 

Instalacja certyfikatu obsługuje obecnie pliki cer i crt. Właściciele urządzeń mogą instalować certyfikaty na komputerze lokalnym i w bieżącym użytkowniku;  Wszyscy inni użytkownicy mogą instalować tylko w programie Current User.

## <a name="to-install-a-certificate"></a>Aby zainstalować certyfikat: 

1.  Podłącz urządzenie HoloLens 2 do komputera.
1.  Umieść plik certyfikatu, który chcesz zainstalować, w lokalizacji na urządzeniach HoloLens 2.
1.  Przejdź do **opcji Ustawienia > Zaktualizuj & security > certyfikatów** i wybierz pozycję Zainstaluj certyfikat.
1.  Kliknij **przycisk Importuj** plik i przejdź do lokalizacji, w którym zapisano certyfikat.
1.  Wybierz **pozycję Store Location (Lokalizacja sklepu).**
1.  Wybierz **pozycję Magazyn certyfikatów.**
1.  Kliknij przycisk **Zainstaluj**.

Certyfikat powinien być teraz zainstalowany na urządzeniu.

![Przeglądarka certyfikatów w aplikacji Ustawienia w obszarze Certyfikaty.](images/certificate-viewer-device.jpg)

![Obraz przedstawiający sposób używania interfejsu użytkownika certyfikatu do instalowania certyfikatu w ustawieniach.](images/certificate-device-install.jpg)

## <a name="to-remove-a-certificate"></a>Aby usunąć certyfikat:

> [!WARNING]
> Za pomocą Menedżera certyfikatów użytkownicy mogą usuwać tylko certyfikaty zainstalowane bezpośrednio z interfejsu użytkownika ustawień. Jeśli certyfikat został zainstalowany w inny sposób, musi zostać również usunięty za pomocą tego samego mechanizmu i nie można go usunąć z Menedżera certyfikatów. Chociaż certyfikaty wdrożone przez rozwiązanie MDM można wyświetlić w Menedżerze certyfikatów, nie można ich odinstalować w Menedżerze certyfikatów. Należy je odinstalować za pośrednictwem rozwiązania MDM.

1. Przejdź do **ustawień Aplikacji > aktualizacji i zabezpieczeń > certyfikatów.**
1. Wyszukaj certyfikat według nazwy w polu wyszukiwania.
1. Wybierz certyfikat.
1. Kliknij pozycję **Usuń.**
1. Po **wyświetleniu** monitu o potwierdzenie wybierz pozycję Tak.

