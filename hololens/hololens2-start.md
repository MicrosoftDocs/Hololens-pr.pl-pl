---
title: Konfigurowanie urządzenia HoloLens 2
description: Dowiedz się, jak po raz pierwszy skonfigurować urządzenie HoloLens 2 za pośrednictwem sieci Wi-Fi przy użyciu konta Microsoft (MSA) lub Azure Active Directory (AAD).
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 9/17/2019
keywords: Hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: d46deaf4048e6a649345dc1676a7f8b94d3ad2fc
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379770"
---
# <a name="set-up-your-hololens-2"></a>Konfigurowanie urządzenia HoloLens 2

Przy pierwszym włączeniu urządzenia HoloLens zostaniesz pokierowany przez proces konfigurowania urządzenia, logowania się przy użyciu konta użytkownika i skalibrowania urządzenia HoloLens dla oczu.  Ta sekcja zawiera informacje na temat konfiguracji początkowej urządzenia HoloLens 2.

W następnej sekcji dowiesz się, jak pracować z urządzeniem HoloLens i korzystać z hologramów. Aby przejść do tego artykułu, zobacz [Wprowadzenie do urządzenia HoloLens 2.](hololens2-basic-usage.md)

## <a name="before-you-start"></a>Przed rozpoczęciem

Przed rozpoczęciem upewnij się, że są dostępne następujące elementy:

**Połączenie sieciowe**. Aby go skonfigurować, musisz połączyć urządzenie HoloLens z siecią. Urządzenie HoloLens 2 umożliwia nawiązywanie połączeń za pomocą Wi-Fi lub ethernet (potrzebny jest adapter USB-C-to-Ethernet). Przy pierwszym połączeniu będzie potrzebna otwarta sieć chroniona hasłem, która nie wymaga przechodzenia do witryny internetowej ani używania certyfikatów do nawiązywania połączenia. [Dowiedz się więcej o witrynach internetowych, z których korzysta urządzenie HoloLens.](hololens-offline.md)

**W konto Microsoft**. Musisz również zalogować się na urządzeniu HoloLens przy użyciu konto Microsoft (lub przy użyciu konta służbowego, jeśli twoja organizacja jest właścicielem urządzenia). Jeśli nie masz bezpłatnej konto Microsoft przejdź do account.microsoft.com [i](https://account.microsoft.com) skonfiguruj go bezpłatnie.

**Bezpieczna, dobrze oświetlona przestrzeń bez zagrożeń związanych z trippingiem.** [Informacje o kondycji i bezpieczeństwie.](https://go.microsoft.com/fwlink/p/?LinkId=746661)

**Opcjonalne akcesoria komfortu,** które są dostępne wraz z urządzeniem HoloLens, aby ułatwić ci wygodne dopasowanie. [Więcej informacji na temat dopasowania i komfortu.](hololens2-setup.md#adjust-fit)

## <a name="set-up-windows"></a>Instalowanie systemu Windows

Przy pierwszym uruchomieniu urządzenia HoloLens 2 pierwszym zadaniem jest skonfigurowanie systemu Windows Holographic.  Po uruchomieniu urządzenia HoloLens usłyszysz muzyka i zobaczysz logo systemu Windows.

![Pierwszy ekran podczas pierwszego rozruchu](images/01-magic-moment.png)

Na urządzeniach HoloLens 2 zostaną opisane następujące kroki:

1. Wybierz język.

    ![Wybierz język](images/04-language.png)

1. Wybierz swój region.

    ![Wybierz region](images/05-region.png)

1. Skalibruj urządzenie HoloLens dla oczu.  Jeśli zdecydujesz się pominąć sekcję, przy następnym logowaniu zostanie wyświetlony monit.

    Aby skalibrować, przyjrzymy się zestawowi celów (nazywanym gemami). Jest w porządku, jeśli migasz lub zamykasz wzrok podczas odtęchnięcia, ale próbujesz nie zaglądać na inne obiekty w pomieszczeniu lub w przestrzeni fizycznej. Urządzenie HoloLens używa tego procesu, aby dowiedzieć się więcej o pozycji oka, dzięki czemu może lepiej renderować świat holograficzny. Po nachłoeniu hologramy będą wyświetlane prawidłowo nawet wtedy, gdy przyszła na twoją łbę.

    Informacje o lokalizacji są przechowywane lokalnie na urządzeniu i nie są skojarzone z żadnymi informacjami o koncie. Aby uzyskać więcej informacji, zobacz [Temat Dane i zabezpieczenia dotyczące bezpieczeństwa.](hololens-calibration.md#calibration-data-and-security)

    ![Ekran wyboru kryteriów](images/06-et-corners.png)

1. Połącz się z Internetem (wybierz Wi-Fi lub połączenie Ethernet.

     Urządzenie HoloLens automatycznie ustawia strefę czasową na podstawie informacji uzyskanych Wi-Fi sieci. Po zakończeniu instalacji możesz zmienić strefę czasową przy użyciu aplikacji Ustawienia.

    ![Łączenie z siecią Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > Jeśli po zakończeniu kroku Wi-Fi konieczne będzie przełączenie się do innej sieci podczas instalacji, możesz nacisnąć jednocześnie przyciski Volume **Down** i **Power,** aby powrócić do tego kroku, jeśli używasz systemu operacyjnego w wersji z października 2019 r. lub nowszej. W przypadku wcześniejszych wersji [](hololens-recovery.md) może być konieczne zresetowanie urządzenia lub jego ponowne uruchomienie w lokalizacji, w której sieć Wi-Fi jest dostępna, aby uniemożliwić automatyczne nawiązywanie połączenia.
    > 
    > Należy również pamiętać, że podczas konfigurowania urządzenia HoloLens istnieje limit czasu poświadczeń, który wynosi dwie minuty. Nazwę użytkownika/hasło należy wprowadzić w ciągu dwóch minut. W przeciwnym razie pole nazwy użytkownika zostanie automatycznie wyczyszone.

1. Zaloguj się do konta użytkownika. Możesz wybrać pozycję **Moja praca lub szkoła** jest jego właścicielem, a ja jestem **jego właścicielem.**

    - Gdy wybierzesz pozycję My work or school owns it (Moja praca lub szkoła jest jego **właścicielem),** zaloguj się przy użyciu konta usługi Azure AD. Jeśli Twoja organizacja korzysta z Azure AD — wersja Premium i skonfigurowała automatyczną rejestrację mdm, urządzenie HoloLens automatycznie rejestruje się w funkcji MDM. Jeśli Twoja organizacja nie używa usługi Azure AD — wersja Premium, automatyczna rejestracja w uciekinie mdm nie jest dostępna. W takim przypadku należy ręcznie zarejestrować [urządzenie HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)w celu zarządzania urządzeniami .

        1. Wprowadź informacje o koncie organizacyjnym.
        1. Zaakceptuj oświadczenie o ochronie prywatności i umowę licencyjną użytkownika końcowego.
        1. Zaloguj się przy użyciu poświadczeń usługi Azure AD. Może to spowodować przekierowanie do strony logowania organizacji.
        1. Kontynuuj konfigurowanie urządzenia.

    - Gdy wybierzesz **pozycję Jestem właścicielem,** zaloguj się przy użyciu konto Microsoft. Po zakończeniu konfiguracji możesz ręcznie zarejestrować [urządzenie HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)w u użytkownikach zarządzania urządzeniami .

        1. Wprowadź informacje konto Microsoft użytkownika.
        2. Wprowadź hasło. Jeśli Twoja konto Microsoft wymaga [weryfikacji dwuetapowej (2FA),](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)ukończ proces weryfikacji.

    ![Ustawianie użytkownika](images/13-device-owner.png)

1. Wybierz, czy włączyć mowę na urządzeniach HoloLens 2 i czy wysyłać telemetrię diagnostyczną.

    ![Włączanie Cortany](images/22-do-more-with-voice.png)

1. Wybierz poziom telemetrii. Jeśli możesz, włącz opcję Pełna telemetria. Te informacje naprawdę pomagają zespołowi inżynierów urządzenia HoloLens.

     ![Poziom telemetrii](images/24-telemetry.png)

1. Dowiedz się, jak używać gestu uruchamiania na urządzeniach HoloLens 2.

     ![Dowiedz się, jak używać gestu uruchamiania, obraz 1 Dowiedz się, jak używać ](images/26-01-startmenu-learning.png) ![ gestu uruchamiania, obraz 2](images/26-02-startmenu-learning.png)

Gratulacje!  Konfiguracja jest ukończona i wszystko jest gotowe do użycia urządzenia HoloLens.

## <a name="next-steps"></a>Następne kroki

1. Zacznij od razu korzystać z Mixed Reality i nawigować po urządzeniach Windows 10 na urządzeniach HoloLens — zapoznaj się z aplikacją **Porady,** aby uzyskać praktyczne samouczki dotyczące interakcji za pomocą rąk. Użyj gestu uruchamiania, aby przejść do strony Start lub powiedzieć "Przejdź do startu" i wybrać pozycję Porady.

1. Kliknij poniżej, aby kontynuować czytanie o urządzeniach HoloLens 2.

> [!div class="nextstepaction"]
> [Wprowadzenie do urządzenia HoloLens 2](hololens2-basic-usage.md)
