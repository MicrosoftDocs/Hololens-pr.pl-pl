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
ms.openlocfilehash: 4b07bb87b34ec966472bcbde000106590570fd7e7063ab503724884fa266bb34
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662740"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a>HoloLens (1. generacji) szyfrowanie funkcją BitLocker

HoloLens (1. generacji) i HoloLens 2 obsługują szyfrowanie urządzenia przy użyciu funkcji BitLocker, jednak funkcja BitLocker jest zawsze włączona w HoloLens 2.

Ten artykuł pomoże włączyć funkcję BitLocker i zarządzać HoloLens (1. generacji).

Na HoloLens (1. generacji) można ręcznie włączyć szyfrowanie urządzenia za pomocą funkcji BitLocker lub przy użyciu funkcji zarządzania urządzeniami przenośnymi (MDM). Postępuj zgodnie z tymi instrukcjami, aby włączyć szyfrowanie urządzenia za pomocą funkcji [BitLocker,](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) aby chronić pliki i informacje przechowywane na HoloLens. Szyfrowanie urządzenia pomaga chronić dane przy użyciu metody szyfrowania AES-CBC 128, która jest odpowiednikiem metody [EncryptionMethodByDriveType 3](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) w dostawcy usług konfiguracji funkcji BitLocker (CSP). Personel, który ma prawidłowy klucz szyfrowania (na przykład hasło), może go odszyfrować lub przeprowadzić odzyskiwanie danych.

## <a name="enable-device-encryption-using-mdm"></a>Włączanie szyfrowania urządzenia przy użyciu rozwiązania MDM

Możesz użyć dostawcy usługi Mobile Zarządzanie urządzeniami (MDM), aby zastosować zasady, które wymagają szyfrowania urządzenia. Zasady do użycia to ustawienie [Security/RequireDeviceEncryption](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) w programie Policy CSP.

[Zobacz instrukcje dotyczące włączania szyfrowania urządzenia przy użyciu Microsoft Intune.](/intune/compliance-policy-create-windows#windows-holographic-for-business)

Aby uzyskać instrukcje dotyczące innych narzędzi MDM, zapoznaj się z dokumentacją dostawcy oprogramowania MDM. Jeśli dostawca mdm wymaga niestandardowego URI szyfrowania urządzenia, użyj następującej konfiguracji:

- **Nazwa:** nazwa do wyboru
- **Opis:** opcjonalny
- **OMA-URI:**`./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **Typ danych:** liczba całkowita
- **Wartość**: `1`

## <a name="enable-device-encryption-using-a-provisioning-package"></a>Włączanie szyfrowania urządzenia przy użyciu pakietu aprowizowania

Pakiety aprowizowania to pliki utworzone przez narzędzie Windows Configuration Designer, które stosuje określoną konfigurację do urządzenia. 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a>Tworzenie pakietu aprowizowania, który uaktualnia wersję Windows Holographic i włącza szyfrowanie

1. [Utwórz pakiet aprowizowania dla HoloLens.](hololens-provisioning.md)
1. Przejdź do **opcji Ustawienia środowiska**  >  **uruchomieniowego**  >  **Zabezpieczenia zasad** i wybierz pozycję **WymagajUrządzajSzyfruj.**

    ![Wymagaj ustawienia szyfrowania urządzenia skonfigurowanego na tak](images/device-encryption.png)

1. Znajdź plik licencji XML dostarczony podczas zakupu pakietu komercyjnego.

1. Przejdź do pliku licencji XML dostarczonego podczas zakupu pakietu komercyjnego i wybierz go.
    > [!NOTE]
    > W [pakiecie aprowizowania można skonfigurować dodatkowe ustawienia.](hololens-provisioning.md)

1. W menu **Plik** kliknij polecenie **Zapisz**. 

1. Przeczytaj ostrzeżenie z wyjaśnieniem, że pliki projektu mogą zawierać poufne informacje, a następnie kliknij przycisk **OK**.

    > [!IMPORTANT]
    > Podczas tworzenia pakietu aprowizowania możesz uwzględnić informacje poufne w plikach projektu i pliku pakietu aprowizowania (ppkg). Mimo że istnieje możliwość zaszyfrowania pliku ppkg, pliki projektu nie są szyfrowane. Pliki projektu należy przechowywać w bezpiecznej lokalizacji i usuwać je, gdy nie będą już potrzebne.

1. W menu **Eksportuj** kliknij pozycję **Pakiet aprowizowania.**
1. Zmień **ustawienie Właściciel** na Administrator **IT**, co spowoduje ustawienie pierwszeństwa tego pakietu aprowizowania wyższego niż pakiet aprowizowania zastosowany do tego urządzenia z innych źródeł, a następnie wybierz pozycję **Dalej.**
1. Ustaw wartość dla wersji **pakietu**.

    > [!TIP]
    > Możesz wprowadzić zmiany w istniejących pakietach i zmienić numer wersji, aby zaktualizować wcześniej zastosowane pakiety.

1. Na stronie **Wybierz szczegóły zabezpieczeń dla pakietu aprowizowania** kliknij przycisk **Dalej.**
1. Kliknij **przycisk** Dalej, aby określić lokalizację wyjściową, w której ma przejść pakiet aprowizowania po jego s zbudowaniu. Domyślnie program Windows ICD używa folderu projektu jako lokalizacji wyjściowej.

    Opcjonalnie możesz kliknąć przycisk Przeglądaj, aby zmienić domyślną lokalizację wyjściową.

1. Kliknij przycisk **Dalej**.
1. Kliknij **pozycję Kompilacja,** aby rozpocząć tworzenie pakietu. Informacje o projekcie są wyświetlane na stronie kompilacji, a pasek postępu wskazuje stan kompilacji.
1. Po zakończeniu kompilacji kliknij przycisk **Zakończ.**

### <a name="apply-the-provisioning-package-to-hololens"></a>Zastosuj pakiet aprowizowania do HoloLens

1. Połączenie urządzenie za pośrednictwem portu USB na komputer i uruchom urządzenie, ale nie przeszukaj strony dopasowania początkowego procesu konfiguracji (pierwsza strona z niebieskim polem). 
1. Naciśnij krótko i zwolnij przyciski **Volume Down** i **Power** jednocześnie.
1. HoloLens będzie wyświetlane jako urządzenie w Eksplorator plików na komputerze.
1. W Eksplorator plików przeciągnij i upuść pakiet aprowizowania (ppkg) do magazynu urządzenia.
1. Naciśnij krótko i zwolnij przyciski **Regulacji głośności i** **Zasilania** jednocześnie na **stronie** dopasowania.
1. Urządzenie zapyta, czy ufasz pakietowi i chcesz go zastosować. Upewnij się, że pakiet jest zaufany.
1. Zobaczysz, czy pakiet został zastosowany pomyślnie, czy nie. Jeśli to się nie powiedzie, możesz naprawić pakiet i spróbować ponownie. Jeśli to się powiodło, przejdź do konfiguracji urządzenia.

> [!NOTE]
> Jeśli urządzenie zostało zakupione przed sierpniem 2016 r., musisz zalogować się do urządzenia przy użyciu usługi konto Microsoft, pobrać najnowszą aktualizację systemu operacyjnego, a następnie zresetować system operacyjny, aby zastosować pakiet aprowizowania.

## <a name="verify-device-encryption"></a>Weryfikowanie szyfrowania urządzenia

Szyfrowanie jest dyskretne na HoloLens. Aby sprawdzić stan szyfrowania urządzenia:

- Na HoloLens przejdź do **tematu Ustawienia** System About  >  **(Informacje o**  >  **systemie).** **Funkcja BitLocker** **jest włączona,** jeśli urządzenie jest zaszyfrowane. 

    ![Ekran Informacje z włączoną funkcją BitLocker](images/about-encryption.png)
