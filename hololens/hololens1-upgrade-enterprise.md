---
title: Odblokowywanie Windows Holographic for Business zabezpieczeń
description: Po uaktualnieniu do wersji Windows Holographic for Business holoLens udostępnia dodatkowe funkcje, które są przeznaczone dla firm.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 8d42c935e698f156aed894e4fa5012c9f04d8d49
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378341"
---
# <a name="unlock-windows-holographic-for-business-features"></a>Odblokowywanie Windows Holographic for Business zabezpieczeń

> [!IMPORTANT]
> Ta strona dotyczy tylko urządzenia HoloLens 1st Gen.

Microsoft HoloLens jest dostępna w wersji *Development Edition*, na której działa system Windows Holographic (wersja systemu Windows 10 przeznaczona dla urządzenia HoloLens) oraz w pakiecie [Commercial Suite,](hololens-commercial-features.md)który udostępnia dodatkowe funkcje przeznaczone dla firm.

Po zakupie pakietu Commercial Suite otrzymasz licencję, która uaktualni system Windows Holographic do wersji Windows Holographic for Business. Tę licencję można zastosować do urządzenia przy użyciu dostawcy zarządzania urządzeniami przenośnymi [(MDM)](#edition-upgrade-by-using-mdm) organizacji lub pakietu [aprowizowania](#edition-upgrade-by-using-a-provisioning-package).

> [!TIP]
> W Windows 10 wersji 1803 możesz sprawdzić, czy urządzenie HoloLens zostało uaktualnione do wersji biznesowej, wybierając pozycję  >  **System ustawień**.

## <a name="edition-upgrade-by-using-mdm"></a>Uaktualnianie wersji przy użyciu rozwiązania MDM

Licencję przedsiębiorstwa może stosować dowolny dostawca mdm obsługujący dostawcę usług konfiguracji [(CSP) systemu WindowsLicensing.](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) Najnowsza wersja interfejsu API zarządzania urządzeniami przenośnymi firmy Microsoft będzie obsługiwać usługę WindowsLicensing CSP.

Aby uzyskać instrukcje krok po kroku dotyczące uaktualniania urządzenia HoloLens przy użyciu urządzenia Microsoft Intune, zobacz Uaktualnianie urządzeń z systemem [Windows Holographic](https://docs.microsoft.com/intune/holographic-upgrade)do Windows Holographic for Business .

 W przypadku innych dostawców zarządzania urządzeniami przenośnymi konkretne kroki konfigurowania i wdrażania zasad mogą się różnić.

## <a name="edition-upgrade-by-using-a-provisioning-package"></a>Uaktualnianie wersji przy użyciu pakietu aprowizowania

Pakiety aprowizowania to pliki utworzone przez narzędzie Windows Configuration Designer, które stosują określoną konfigurację do urządzenia.

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a>Tworzenie pakietu aprowizowania, który uaktualnia wersję systemu Windows Holographic

1. [Utwórz pakiet aprowizowania dla urządzenia HoloLens.](hololens-provisioning.md)
1. Przejdź do **opcji Ustawienia środowiska**  >  **uruchomieniowego EditionUpgrade** i wybierz **pozycję EditionUpgradeWithLicense.**

    ![Uaktualnianie wersji z wybranym ustawieniem licencji](images/icd1.png)

1. Znajdź plik licencji XML dostarczony podczas zakupu pakietu Commercial Suite.

    > [!NOTE]
    > Dodatkowe ustawienia [można skonfigurować w pakiecie aprowizowania.](hololens-provisioning.md)

1. W menu **File** (Plik) wybierz polecenie **Save** (Zapisz). 

1. Przeczytaj ostrzeżenie, że pliki projektu mogą zawierać poufne informacje, a następnie kliknij przycisk **OK.**

    > [!IMPORTANT]
    > Podczas kompilowania pakietu aprowizowania możesz uwzględnić informacje poufne w plikach projektu i pliku pakietu aprowizowania (ppkg). Mimo że istnieje możliwość zaszyfrowania pliku ppkg, pliki projektu nie są szyfrowane. Pliki projektu należy przechowywać w bezpiecznej lokalizacji i usuwać je, gdy nie będą już potrzebne.

1. W menu **Eksport** wybierz pozycję **Pakiet aprowizowania.**

1. Zmień **właściciela** na **administratora IT,** który ustawia pierwszeństwo tego pakietu aprowizowania na wyższy niż inne, które mają zastosowanie do tego urządzenia z różnych źródeł, a następnie wybierz pozycję **Dalej.**

1. Ustaw wartość dla wersji **pakietu**.

    > [!TIP]
    > Możesz wprowadzić zmiany w istniejących pakietach i zmienić numer wersji, aby zaktualizować wcześniej zastosowane pakiety.

1. Na stronie Select security details for the provisioning package (Wybierz szczegóły zabezpieczeń **pakietu aprowizowania)** wybierz pozycję **Next (Dalej).**

1. Wybierz **przycisk** Dalej, aby określić lokalizację wyjściową, do której ma przejść pakiet aprowizowania po jego sbudowaną zawartość. Domyślnie funkcja ICD systemu Windows używa folderu projektu jako lokalizacji wyjściowej.

    Opcjonalnie możesz wybrać pozycję **Przeglądaj,** aby zmienić domyślną lokalizację wyjściową.

1. Wybierz opcję **Dalej**.

1. Wybierz **pozycję Kompilacja,** aby rozpocząć kompilowanie pakietu. Na stronie kompilacji są wyświetlane informacje o projekcie, a pasek postępu wskazuje stan kompilacji.

1. Po zakończeniu kompilacji wybierz pozycję **Zakończ.**

### <a name="apply-the-provisioning-package-to-hololens"></a>Stosowanie pakietu aprowizowania na urządzeniach HoloLens

1. Za pomocą kabla USB podłącz urządzenie do komputera. Uruchom urządzenie, ale nie przeszukaj strony dopasowania początkowej konfiguracji (pierwsza strona z niebieskim polem).  Na komputerze urządzenie HoloLens jest Eksplorator plików.

    > [!NOTE]
    > Jeśli na urządzeniu HoloLens działa urządzenie Windows 10 w wersji 1607 lub starszej, otwórz program Eksplorator plików przez krótkie naciśnięcie i zwolnienie przycisków **Volume Down** i **Power** jednocześnie na urządzeniu.

1. W Eksplorator plików przeciągnij i upuść pakiet aprowizowania (ppkg) do magazynu urządzenia.

1. Chociaż urządzenie HoloLens nadal znajduje się na **stronie** dopasowania, naciśnij krótko i ponownie zwolnij przyciski **Volume Down** i **Power.**

1. Urządzenie HoloLens zapyta, czy ufasz pakietowi i chcesz go zastosować. Upewnij się, że pakiet jest zaufany.

1. Zobaczysz, czy pakiet został zastosowany pomyślnie. Jeśli nie został on zastosowany pomyślnie, możesz naprawić pakiet i spróbować ponownie. Jeśli to się powiedzie, przejdź do konfiguracji urządzenia.
