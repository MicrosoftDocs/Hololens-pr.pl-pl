---
title: Menedżer certyfikatów
description: Dowiedz się, jak ręcznie instalować i usuwać certyfikaty oraz zarządzać nimi na HoloLens 2 urządzeń rzeczywistości mieszanej.
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032961"
---
# <a name="certificate-manager"></a>Menedżer certyfikatów

- Ulepszono narzędzia do inspekcji, diagnostyki i weryfikacji zabezpieczeń i zgodności urządzeń za pośrednictwem nowego Menedżera certyfikatów. Ta funkcja umożliwi wdrażanie, rozwiązywanie problemów i weryfikowanie certyfikatów na dużą skalę w środowiskach komercyjnych.

Na Windows Holographic w wersji 20H2 dodajemy Menedżera certyfikatów w HoloLens 2 Ustawienia aplikacji. Przejdź do **Ustawienia > Update & Security > Certificates**. Ta funkcja zapewnia prosty i przyjazny dla użytkownika sposób wyświetlania, instalowania i usuwania certyfikatów na urządzeniu. Dzięki nowej funkcji Menedżer certyfikatów administratorzy i użytkownicy mają teraz ulepszone narzędzia inspekcji, diagnostyki i walidacji, aby zapewnić, że urządzenia pozostaną bezpieczne i zgodne. 

-   **Inspekcja:** Możliwość zweryfikowania, czy certyfikat został wdrożony poprawnie, lub potwierdzenia, że został on odpowiednio usunięty. 
-   **Diagnostyka:** W przypadku problemów podczas sprawdzania, czy na urządzeniu istnieją odpowiednie certyfikaty, oszczędzasz czas i pomagasz w rozwiązywaniu problemów. 
-   **Walidacja:** Sprawdzenie, czy certyfikat służy zamierzony cel i jest funkcjonalny, może zaoszczędzić dużo czasu, szczególnie w środowiskach komercyjnych przed wdrożeniem certyfikatów na większą skalę.

Aby szybko znaleźć określony certyfikat na liście, dostępne są opcje sortowania według nazwy, magazynu lub daty wygaśnięcia. Użytkownicy mogą również bezpośrednio wyszukiwać certyfikat. Aby wyświetlić właściwości poszczególnych certyfikatów, wybierz certyfikat i kliknij pozycję **Informacje.** 

Instalacja certyfikatu obsługuje obecnie pliki cer i crt. Właściciele urządzeń mogą instalować certyfikaty na komputerze lokalnym i bieżącym użytkowniku;  Wszyscy inni użytkownicy mogą instalować tylko w programie Current User.

## <a name="to-install-a-certificate"></a>Aby zainstalować certyfikat: 

1.  Połączenie komputer HoloLens 2.
1.  Umieść plik certyfikatu, który chcesz zainstalować, w lokalizacji na komputerze HoloLens 2.
1.  Przejdź do **Ustawienia App > Update & Security > Certificates**(Certyfikaty > zabezpieczeń), a następnie wybierz pozycję Install a certificate (Zainstaluj certyfikat).
1.  Kliknij **pozycję Importuj** plik i przejdź do lokalizacji, w którym zapisano certyfikat.
1.  Wybierz **pozycję Store Location (Lokalizacja sklepu).**
1.  Wybierz **pozycję Magazyn certyfikatów.**
1.  Kliknij przycisk **Zainstaluj**.

Certyfikat powinien być teraz zainstalowany na urządzeniu.

![Przeglądarka certyfikatów w aplikacji Ustawienia w obszarze Certyfikaty.](images/certificate-viewer-device.jpg)

![Obraz przedstawiający sposób instalowania certyfikatu w programie przy użyciu interfejsu użytkownika Ustawienia.](images/certificate-device-install.jpg)

## <a name="to-remove-a-certificate"></a>Aby usunąć certyfikat:

> [!WARNING]
> Za pomocą Menedżera certyfikatów użytkownicy mogą usuwać tylko certyfikaty zainstalowane bezpośrednio z Ustawienia użytkownika. Jeśli certyfikat został zainstalowany za pośrednictwem innych środków, należy go również usunąć za pomocą tego samego mechanizmu i nie można go usunąć z Menedżera certyfikatów. Chociaż certyfikaty wdrożone przez rozwiązanie MDM można wyświetlić w Menedżerze certyfikatów, nie można ich odinstalować w Menedżerze certyfikatów. Należy je odinstalować za pośrednictwem rozwiązania MDM.

1. Przejdź do **Ustawienia App > Update i Security > Certificates**.
1. Wyszukaj certyfikat według nazwy w polu wyszukiwania.
1. Wybierz certyfikat.
1. Kliknij pozycję **Usuń.**
1. Po **wyświetleniu** monitu o potwierdzenie wybierz pozycję Tak.

