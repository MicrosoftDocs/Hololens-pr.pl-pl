---
title: Szyfrowanie funkcją BitLocker na urządzeniach HoloLens
description: Dowiedz się, jak włączyć szyfrowanie urządzeń funkcją BitLocker w celu ochrony plików przechowywanych na urządzeniach rzeczywistości mieszanej HoloLens.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 2929cbea826e0cc92a72550c7874995506b94257
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378237"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a>Szyfrowanie funkcją BitLocker na urządzeniach HoloLens (1. generacji)

Urządzenia HoloLens (1. generacja) i HoloLens 2 obsługują szyfrowanie urządzenia przy użyciu funkcji BitLocker, jednak funkcja BitLocker jest zawsze włączona na urządzeniu HoloLens 2.

Ten artykuł pomoże włączyć funkcję BitLocker na urządzeniach HoloLens (1. generacji) i zarządzać nimi.

Na urządzeniu HoloLens (1. generacji) można ręcznie włączyć szyfrowanie za pomocą funkcji BitLocker lub za pomocą funkcji zarządzania urządzeniami przenośnymi (MDM). Postępuj zgodnie z tymi instrukcjami, aby włączyć szyfrowanie urządzenia za pomocą funkcji [BitLocker,](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) aby chronić pliki i informacje przechowywane na urządzeniu HoloLens. Szyfrowanie urządzenia pomaga chronić dane przy użyciu metody szyfrowania AES-CBC 128, która jest odpowiednikiem metody [3 EncryptionMethodByDriveType](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) w dostawcy usług konfiguracji funkcji BitLocker. Personel, który ma prawidłowy klucz szyfrowania (na przykład hasło), może go odszyfrować lub przeprowadzić odzyskiwanie danych.

## <a name="enable-device-encryption-using-mdm"></a>Włączanie szyfrowania urządzenia przy użyciu rozwiązania MDM

Możesz użyć dostawcy usługi Mobile Zarządzanie urządzeniami (MDM), aby zastosować zasady, które wymagają szyfrowania urządzenia. Zasady do użycia to ustawienie [Security/RequireDeviceEncryption](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) w programie Policy CSP.

[Zobacz instrukcje dotyczące włączania szyfrowania urządzenia przy użyciu Microsoft Intune.](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

Instrukcje dotyczące innych narzędzi MDM można znaleźć w dokumentacji dostawcy usług MDM. Jeśli dostawca rozwiązania MDM wymaga niestandardowego URI szyfrowania urządzenia, użyj następującej konfiguracji:

- **Nazwa:** nazwa, która jest wybierana
- **Opis:** opcjonalny
- **OMA-URI:**`./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **Typ danych:** liczba całkowita
- **Wartość**: `1`

## <a name="enable-device-encryption-using-a-provisioning-package"></a>Włączanie szyfrowania urządzenia przy użyciu pakietu aprowizowania

Pakiety aprowizowania to pliki utworzone przez narzędzie Windows Configuration Designer, które stosują określoną konfigurację do urządzenia. 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a>Tworzenie pakietu aprowizowania, który uaktualnia wersję systemu Windows Holographic i włącza szyfrowanie

1. [Utwórz pakiet aprowizowania dla urządzenia HoloLens.](hololens-provisioning.md)
1. Przejdź do **opcji Zabezpieczenia**  >  **zasad ustawień środowiska**  >  **uruchomieniowego** i wybierz pozycję **WymagajUrządzajSzyfruj.**

    ![Wymagaj ustawienia szyfrowania urządzenia skonfigurowanego na tak](images/device-encryption.png)

1. Znajdź plik licencji XML dostarczony podczas zakupu pakietu Commercial Suite.

1. Przejdź do pliku licencji XML i wybierz go, który został podany podczas zakupu pakietu Commercial Suite.
    > [!NOTE]
    > Dodatkowe ustawienia [można skonfigurować w pakiecie aprowizowania.](hololens-provisioning.md)

1. W menu **Plik** kliknij polecenie **Zapisz**. 

1. Przeczytaj ostrzeżenie z wyjaśnieniem, że pliki projektu mogą zawierać poufne informacje, a następnie kliknij przycisk **OK.**

    > [!IMPORTANT]
    > Podczas kompilowania pakietu aprowizowania możesz uwzględnić informacje poufne w plikach projektu i pliku pakietu aprowizowania (ppkg). Mimo że istnieje możliwość zaszyfrowania pliku ppkg, pliki projektu nie są szyfrowane. Pliki projektu należy przechowywać w bezpiecznej lokalizacji i usuwać je, gdy nie będą już potrzebne.

1. W menu **Eksport** kliknij pozycję **Pakiet aprowizowania.**
1. Zmień **właściciela** na **administratora IT**, co spowoduje ustawienie pierwszeństwa tego pakietu aprowizowania wyższego niż pakiet aprowizowania zastosowany do tego urządzenia z innych źródeł, a następnie wybierz pozycję **Dalej.**
1. Ustaw wartość dla wersji **pakietu**.

    > [!TIP]
    > Możesz wprowadzić zmiany w istniejących pakietach i zmienić numer wersji, aby zaktualizować wcześniej zastosowane pakiety.

1. Na stronie Select security details for the provisioning package (Wybierz szczegóły zabezpieczeń **dla pakietu aprowizowania)** kliknij przycisk **Next (Dalej).**
1. Kliknij **przycisk** Dalej, aby określić lokalizację wyjściową, do której ma przejść pakiet aprowizowania po jego s zbudowaniu. Domyślnie funkcja ICD systemu Windows używa folderu projektu jako lokalizacji wyjściowej.

    Opcjonalnie możesz kliknąć przycisk Przeglądaj, aby zmienić domyślną lokalizację wyjściową.

1. Kliknij przycisk **Dalej**.
1. Kliknij **pozycję Build (Kompilacja),** aby rozpocząć kompilowanie pakietu. Informacje o projekcie są wyświetlane na stronie kompilacji, a pasek postępu wskazuje stan kompilacji.
1. Po zakończeniu kompilacji kliknij przycisk **Zakończ.**

### <a name="apply-the-provisioning-package-to-hololens"></a>Stosowanie pakietu aprowizowania na urządzeniach HoloLens

1. Podłącz urządzenie za pośrednictwem portu USB do komputera i  uruchom urządzenie, ale nie przeszukaj strony dopasowania początkowej konfiguracji (pierwsza strona z niebieskim polem).
1. Naciśnij krótko i zwolnij przyciski **Volume Down** i **Power** jednocześnie.
1. Urządzenie HoloLens będzie wyświetlane jako urządzenie w Eksplorator plików na komputerze.
1. W Eksplorator plików przeciągnij i upuść pakiet aprowizowania (ppkg) do magazynu urządzenia.
1. Naciśnij krótko i zwolnij przyciski **Volume Down** i **Power** jednocześnie na **stronie** dopasowania.
1. Urządzenie zapyta, czy pakiet jest zaufany i czy chcesz go zastosować. Upewnij się, że pakiet jest zaufany.
1. Zobaczysz, czy pakiet został zastosowany pomyślnie. Jeśli to się nie powiedzie, możesz naprawić pakiet i spróbować ponownie. Jeśli to się powiodło, przejdź do konfiguracji urządzenia.

> [!NOTE]
> Jeśli urządzenie zostało zakupione przed sierpniem 2016 r., musisz zalogować się do urządzenia przy użyciu usługi konto Microsoft, pobrać najnowszą aktualizację systemu operacyjnego, a następnie zresetować system operacyjny, aby zastosować pakiet aprowizowania.

## <a name="verify-device-encryption"></a>Weryfikowanie szyfrowania urządzenia

Szyfrowanie na urządzeniach HoloLens jest dyskretne. Aby sprawdzić stan szyfrowania urządzenia:

- Na urządzeniach HoloLens przejdź do **tematu Settings** System About  >    >  **(Informacje o systemie ustawień).** **Funkcja BitLocker** **jest włączona,** jeśli urządzenie jest zaszyfrowane. 

    ![Ekran Informacje z włączoną funkcją BitLocker](images/about-encryption.png)
