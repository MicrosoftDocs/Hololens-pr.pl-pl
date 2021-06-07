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
ms.openlocfilehash: f9dcf98cbd200ac54cd786648fdfe286bff1aa00
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378278"
---
# <a name="certificate-manager"></a>Menedżer certyfikatów

- Ulepszono narzędzia do inspekcji, diagnostyki i weryfikacji zabezpieczeń i zgodności urządzeń za pośrednictwem nowego Menedżera certyfikatów. Ta funkcja umożliwi wdrażanie, rozwiązywanie problemów i weryfikowanie certyfikatów na dużą skalę w środowiskach komercyjnych.

W systemie Windows Holographic w wersji 20H2 dodajemy Menedżera certyfikatów w aplikacji Ustawienia urządzenia HoloLens 2. Przejdź do **ustawień > Update & Security > Certificates**. Ta funkcja zapewnia prosty i przyjazny dla użytkownika sposób wyświetlania, instalowania i usuwania certyfikatów na urządzeniu. Dzięki nowej funkcji Menedżer certyfikatów administratorzy i użytkownicy mają teraz ulepszone narzędzia inspekcji, diagnostyki i walidacji, aby zapewnić, że urządzenia pozostaną bezpieczne i zgodne. 

-   **Inspekcja:** Możliwość zweryfikowania, czy certyfikat został wdrożony poprawnie, lub potwierdzenia, że został on odpowiednio usunięty. 
-   **Diagnostyka:** W przypadku problemów podczas sprawdzania, czy na urządzeniu istnieją odpowiednie certyfikaty, oszczędzasz czas i pomagasz w rozwiązywaniu problemów. 
-   **Walidacja:** Sprawdzenie, czy certyfikat służy zamierzony cel i jest funkcjonalny, może zaoszczędzić dużo czasu, szczególnie w środowiskach komercyjnych przed wdrożeniem certyfikatów na większą skalę.

Aby szybko znaleźć określony certyfikat na liście, dostępne są opcje sortowania według nazwy, magazynu lub daty wygaśnięcia. Użytkownicy mogą również bezpośrednio wyszukiwać certyfikat. Aby wyświetlić właściwości poszczególnych certyfikatów, wybierz certyfikat i kliknij pozycję **Informacje.** 

Instalacja certyfikatu obsługuje obecnie pliki cer i crt. Właściciele urządzeń mogą instalować certyfikaty na komputerze lokalnym i w bieżącym użytkowniku;  Wszyscy inni użytkownicy mogą instalować tylko w programie Current User. Użytkownicy mogą usuwać tylko certyfikaty zainstalowane bezpośrednio z interfejsu użytkownika ustawień. Jeśli certyfikat został zainstalowany za pośrednictwem innych środków, należy go również usunąć za pomocą tego samego mechanizmu.

## <a name="to-install-a-certificate"></a>Aby zainstalować certyfikat: 

1.  Podłącz urządzenie HoloLens 2 do komputera.
1.  Umieść plik certyfikatu, który chcesz zainstalować, w lokalizacji na urządzeniach HoloLens 2.
1.  Przejdź do **ustawień App > Update & Security > Certificates**, a następnie wybierz pozycję Zainstaluj certyfikat.
1.  Kliknij **pozycję Importuj** plik i przejdź do lokalizacji, w którym zapisano certyfikat.
1.  Wybierz **pozycję Store Location (Lokalizacja sklepu).**
1.  Wybierz **pozycję Magazyn certyfikatów.**
1.  Kliknij przycisk **Zainstaluj**.

Certyfikat powinien być teraz zainstalowany na urządzeniu.

## <a name="to-remove-a-certificate"></a>Aby usunąć certyfikat: 
>[!WARNING]
> Chociaż certyfikaty wdrożone przez rozwiązanie MDM można wyświetlić w Menedżerze certyfikatów, nie można ich odinstalować w Menedżerze certyfikatów. Należy je odinstalować za pośrednictwem rozwiązania MDM.
1. Przejdź do **ustawień App > Update and Security > Certificates**(Aktualizacje i > zabezpieczeń).
1. Wyszukaj certyfikat według nazwy w polu wyszukiwania.
1. Wybierz certyfikat.
1. Kliknij pozycję **Usuń.**
1. Po **wyświetleniu** monitu o potwierdzenie wybierz pozycję Tak.



![Przeglądarka certyfikatów w aplikacji Ustawienia w obszarze Certyfikaty](images/certificate-viewer-device.jpg)

![Obraz przedstawiający sposób instalowania certyfikatu za pomocą interfejsu użytkownika certyfikatu w ustawieniach.](images/certificate-device-install.jpg)
