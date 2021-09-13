---
title: Odblokowywanie Windows Holographic for Business funkcji
description: Po uaktualnieniu do wersji Windows Holographic for Business HoloLens dodatkowe funkcje, które są przeznaczone dla firm.
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
ms.openlocfilehash: c6d1225dc6da1c039a34fc2782f23330ae40f280
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033619"
---
# <a name="unlock-windows-holographic-for-business-features"></a>Odblokowywanie Windows Holographic for Business funkcji

> [!IMPORTANT]
> Ta strona dotyczy tylko HoloLens pierwszej generacji.

Microsoft HoloLens jest dostępna w wersji *Development Edition*, która działa z platformą Windows Holographic (edycją systemu Windows 10 zaprojektowaną dla systemu HoloLens) oraz w pakiecie [Commercial Suite](hololens-commercial-features.md), który udostępnia dodatkowe funkcje przeznaczone dla firm.

Po zakupie pakietu Commercial Suite otrzymasz licencję, która uaktualnia platformę Windows Holographic do Windows Holographic for Business. Tę licencję można zastosować do urządzenia przy użyciu dostawcy zarządzania urządzeniami przenośnymi [(MDM)](#edition-upgrade-by-using-mdm) organizacji lub pakietu [aprowizowania.](#edition-upgrade-by-using-a-provisioning-package)

> [!TIP]
> W Windows 10 wersji 1803 można sprawdzić, czy HoloLens została uaktualniona do wersji biznesowej, wybierając pozycję **Ustawienia**  >  **System**.

## <a name="edition-upgrade-by-using-mdm"></a>Uaktualnianie wersji przy użyciu rozwiązania MDM

Licencję przedsiębiorstwa może stosować dowolny dostawca mdm obsługujący dostawcę usług konfiguracji [(CSP) systemu WindowsLicensing.](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) Najnowsza wersja interfejsu API zarządzania urządzeniami przenośnymi firmy Microsoft będzie obsługiwać usługę WindowsLicensing CSP.

Aby uzyskać instrukcje krok po kroku dotyczące uaktualniania HoloLens przy użyciu programu Microsoft Intune, zobacz Uaktualnianie urządzeń z systemem [Windows Holographic](/intune/holographic-upgrade)do Windows Holographic for Business .

 W przypadku innych dostawców zarządzania urządzeniami przenośnymi konkretne kroki konfigurowania i wdrażania zasad mogą się różnić.

## <a name="edition-upgrade-by-using-a-provisioning-package"></a>Uaktualnianie wersji przy użyciu pakietu aprowizowania

Pakiety aprowizowania to pliki utworzone przez narzędzie Windows Configuration Designer, które stosuje określoną konfigurację do urządzenia.

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a>Tworzenie pakietu aprowizowania uaktualnia Windows Holographic Edition

1. [Utwórz pakiet aprowizowania dla HoloLens.](hololens-provisioning.md)
1. Przejdź do **ustawień środowiska**  >  **uruchomieniowego EditionUpgrade** i wybierz **pozycję EditionUpgradeWithLicense.**

    ![Uaktualnij wydanie z wybranym ustawieniem licencji.](images/icd1.png)

1. Znajdź plik licencji XML dostarczony podczas zakupu pakietu komercyjnego.

    > [!NOTE]
    > W [pakiecie aprowizowania można skonfigurować dodatkowe ustawienia.](hololens-provisioning.md)

1. W menu **File** (Plik) wybierz polecenie **Save** (Zapisz). 

1. Przeczytaj ostrzeżenie, że pliki projektu mogą zawierać poufne informacje, a następnie kliknij przycisk **OK**.

    > [!IMPORTANT]
    > Podczas tworzenia pakietu aprowizowania możesz uwzględnić informacje poufne w plikach projektu i pliku pakietu aprowizowania (ppkg). Mimo że istnieje możliwość zaszyfrowania pliku ppkg, pliki projektu nie są szyfrowane. Pliki projektu należy przechowywać w bezpiecznej lokalizacji i usuwać je, gdy nie będą już potrzebne.

1. W menu **Eksportuj** wybierz pozycję **Pakiet aprowizowania.**

1. Zmień **ustawienie Właściciel** na Administrator **IT**, które ustawia pierwszeństwo tego pakietu aprowizowania na wyższe niż inne zastosowane do tego urządzenia z różnych źródeł, a następnie wybierz przycisk **Dalej.**

1. Ustaw wartość dla wersji **pakietu**.

    > [!TIP]
    > Możesz wprowadzić zmiany w istniejących pakietach i zmienić numer wersji, aby zaktualizować wcześniej zastosowane pakiety.

1. Na stronie Select security details for the provisioning package (Wybierz szczegóły zabezpieczeń **dla pakietu aprowizowania)** wybierz **pozycję Next (Dalej).**

1. Wybierz **przycisk** Dalej, aby określić lokalizację wyjściową, w której ma zostać sbudowaną zawartość pakietu aprowizowania. Domyślnie program Windows ICD używa folderu projektu jako lokalizacji wyjściowej.

    Opcjonalnie możesz wybrać pozycję **Przeglądaj,** aby zmienić domyślną lokalizację wyjściową.

1. Wybierz opcję **Dalej**.

1. Wybierz **pozycję Kompilacja,** aby rozpocząć tworzenie pakietu. Na stronie kompilacji są wyświetlane informacje o projekcie, a pasek postępu wskazuje stan kompilacji.

1. Po zakończeniu kompilacji wybierz pozycję **Zakończ.**

### <a name="apply-the-provisioning-package-to-hololens"></a>Zastosuj pakiet aprowizowania do HoloLens

1. Za pomocą kabla USB podłącz urządzenie do komputera. Uruchom urządzenie, ale nie przeszukaj strony dopasowania w początkowym oknie konfiguracji (pierwsza strona z niebieskim polem).  Na komputerze HoloLens jako urządzenie w Eksplorator plików.

    > [!NOTE]
    > Jeśli na HoloLens jest uruchomiony program Windows 10 w wersji 1607 lub starszej, otwórz program Eksplorator plików przez krótkie naciśnięcie i zwolnienie przycisków Volume **Down** i **Power** jednocześnie na urządzeniu.

1. W Eksplorator plików przeciągnij i upuść pakiet aprowizowania (ppkg) do magazynu urządzenia.

1. Chociaż HoloLens nadal znajduje się na stronie **dopasowania,** naciśnij krótko  i ponownie zwolnij przyciski **Regulacji** głośności i Zasilania.

1. HoloLens pytanie, czy ufasz pakietowi i chcesz go zastosować. Upewnij się, że pakiet jest zaufany.

1. Zobaczysz, czy pakiet został zastosowany pomyślnie, czy nie. Jeśli nie został on zastosowany pomyślnie, możesz naprawić pakiet i spróbować ponownie. Jeśli to się powiedzie, przejdź do konfiguracji urządzenia.
