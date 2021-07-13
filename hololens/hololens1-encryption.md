---
title: HoloLens Szyfrowanie funkcją BitLocker
description: Dowiedz się, jak włączyć szyfrowanie urządzeń funkcją BitLocker w celu ochrony plików przechowywanych na urządzeniach HoloLens rzeczywistości mieszanej.
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
ms.openlocfilehash: 37efab3ef3d68a9641320e144619008612f6efa2
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635249"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a>HoloLens (1. generacji) szyfrowanie funkcją BitLocker

HoloLens (1. generacji) i HoloLens 2 obsługują szyfrowanie urządzenia przy użyciu funkcji BitLocker, jednak funkcja BitLocker jest zawsze włączona w HoloLens 2.

Ten artykuł pomoże włączyć funkcję BitLocker i zarządzać HoloLens (1. generacji).

Na HoloLens (1. generacji) można ręcznie włączyć szyfrowanie urządzenia za pomocą funkcji BitLocker lub przy użyciu funkcji zarządzania urządzeniami przenośnymi (MDM). Postępuj zgodnie z tymi instrukcjami, aby włączyć szyfrowanie urządzenia za pomocą funkcji [BitLocker,](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) aby chronić pliki i informacje przechowywane HoloLens. Szyfrowanie urządzenia pomaga chronić dane przy użyciu metody szyfrowania AES-CBC 128, która jest odpowiednikiem metody [3 EncryptionMethodByDriveType](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) w dostawcy usług konfiguracji funkcji BitLocker. Personel, który ma prawidłowy klucz szyfrowania (na przykład hasło), może go odszyfrować lub przeprowadzić odzyskiwanie danych.

## <a name="enable-device-encryption-using-mdm"></a>Włączanie szyfrowania urządzenia przy użyciu rozwiązania MDM

Możesz użyć dostawcy usługi Mobile Zarządzanie urządzeniami (MDM), aby zastosować zasady, które wymagają szyfrowania urządzenia. Zasady do użycia to ustawienie [Security/RequireDeviceEncryption](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) w programie Policy CSP.

[Zapoznaj się z instrukcjami dotyczącymi włączania szyfrowania urządzenia przy użyciu Microsoft Intune.](/intune/compliance-policy-create-windows#windows-holographic-for-business)

Instrukcje dotyczące innych narzędzi MDM można znaleźć w dokumentacji dostawcy usług MDM. Jeśli dostawca rozwiązania MDM wymaga niestandardowego URI szyfrowania urządzenia, użyj następującej konfiguracji:

- **Nazwa:** nazwa, która jest wybierana
- **Opis:** opcjonalny
- **OMA-URI:**`./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **Typ danych:** liczba całkowita
- **Wartość**: `1`

## <a name="enable-device-encryption-using-a-provisioning-package"></a>Włączanie szyfrowania urządzenia przy użyciu pakietu aprowizowania

Pakiety aprowizowania to pliki utworzone przez Windows Configuration Designer, które stosują określoną konfigurację do urządzenia. 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a>Tworzenie pakietu aprowizowania, który uaktualnia wersję Windows Holographic i włącza szyfrowanie

1. [Utwórz pakiet aprowizowania dla HoloLens.](hololens-provisioning.md)
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
1. Kliknij **przycisk** Dalej, aby określić lokalizację wyjściową, do której ma przejść pakiet aprowizowania po jego s zbudowaniu. Domyślnie program Windows ICD używa folderu projektu jako lokalizacji wyjściowej.

    Opcjonalnie możesz kliknąć przycisk Przeglądaj, aby zmienić domyślną lokalizację wyjściową.

1. Kliknij przycisk **Dalej**.
1. Kliknij **pozycję Build (Kompilacja),** aby rozpocząć kompilowanie pakietu. Informacje o projekcie są wyświetlane na stronie kompilacji, a pasek postępu wskazuje stan kompilacji.
1. Po zakończeniu kompilacji kliknij przycisk **Zakończ.**

### <a name="apply-the-provisioning-package-to-hololens"></a>Zastosuj pakiet aprowizowania do HoloLens

1. Połączenie urządzenie za pośrednictwem portu USB na komputer i uruchom urządzenie, ale nie przejmij strony dopasowania początkowej konfiguracji (pierwsza strona z niebieskim polem). 
1. Naciśnij krótko i zwolnij przyciski **Volume Down** i **Power** jednocześnie.
1. HoloLens będzie wyświetlane jako urządzenie w Eksplorator plików na komputerze.
1. W Eksplorator plików przeciągnij i upuść pakiet aprowizowania (ppkg) do magazynu urządzenia.
1. Naciśnij krótko i zwolnij przyciski **Volume Down** i **Power** jednocześnie na **stronie** dopasowania.
1. Urządzenie zapyta, czy pakiet jest zaufany i czy chcesz go zastosować. Upewnij się, że pakiet jest zaufany.
1. Zobaczysz, czy pakiet został zastosowany pomyślnie. Jeśli to się nie powiedzie, możesz naprawić pakiet i spróbować ponownie. Jeśli to się powiodło, przejdź do konfiguracji urządzenia.

> [!NOTE]
> Jeśli urządzenie zostało zakupione przed sierpniem 2016 r., musisz zalogować się do urządzenia przy użyciu usługi konto Microsoft, pobrać najnowszą aktualizację systemu operacyjnego, a następnie zresetować system operacyjny, aby zastosować pakiet aprowizowania.

## <a name="verify-device-encryption"></a>Weryfikowanie szyfrowania urządzenia

Szyfrowanie jest dyskretne na HoloLens. Aby sprawdzić stan szyfrowania urządzenia:

- Na HoloLens przejdź do tematu **Ustawienia** System About  >  **(Informacje o**  >  **systemie).** **Funkcja BitLocker** **jest włączona,** jeśli urządzenie jest zaszyfrowane. 

    ![Ekran Informacje z włączoną funkcją BitLocker](images/about-encryption.png)
