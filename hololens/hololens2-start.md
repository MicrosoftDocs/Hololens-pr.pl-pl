---
title: Konfigurowanie urządzenia HoloLens 2
description: Dowiedz się, jak skonfigurować urządzenie HoloLens 2 po raz pierwszy za pośrednictwem sieci Wi-Fi przy użyciu konta Microsoft (MSA) lub Azure Active Directory (AAD).
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 6/09/2021
keywords: Hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 0d087037e94bcaed2cd79d9cff77ed3039919a09
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923786"
---
# <a name="set-up-your-hololens-2"></a>Konfigurowanie urządzenia HoloLens 2

Przy pierwszym włączeniu urządzenia HoloLens zostaniesz pokierowany przez proces konfigurowania urządzenia, logowania się przy użyciu konta użytkownika i skalibrowania urządzenia HoloLens dla twoich oczu.  Ta sekcja zawiera informacje na temat konfiguracji początkowej urządzenia HoloLens 2.

W następnej sekcji dowiesz się, jak pracować z urządzeniem HoloLens i korzystać z hologramów. Aby przejść do tego artykułu, zobacz [Getting around HoloLens 2 (Poruszanie się po urządzeniach HoloLens 2).](hololens2-basic-usage.md)

## <a name="before-you-start"></a>Przed rozpoczęciem

Przed rozpoczęciem upewnij się, że są dostępne następujące elementy:

**Połączenie sieciowe**. Aby ją skonfigurować, musisz połączyć urządzenie HoloLens z siecią. Za pomocą urządzenia HoloLens 2 można nawiązać połączenie za pomocą interfejsu Wi-Fi lub ethernet (potrzebny będzie adapter USB C-to-Ethernet). Przy pierwszym połączeniu będzie potrzebna otwarta sieć chroniona hasłem, która nie wymaga przechodzenia do witryny internetowej ani używania certyfikatów do nawiązywania połączenia. [Dowiedz się więcej o witrynach internetowych, z których korzysta urządzenie HoloLens.](hololens-offline.md)

**W konto Microsoft**. Musisz również zalogować się na urządzeniu HoloLens przy użyciu konto Microsoft (lub przy użyciu konta służbowego, jeśli organizacja jest właścicielem urządzenia). Jeśli nie masz bezpłatnej konto Microsoft, przejdź do account.microsoft.com [i](https://account.microsoft.com) skonfiguruj go bezpłatnie.

**Bezpieczna, dobrze oświetlona przestrzeń bez zagrożeń związanych z trippingiem.** [Informacje o kondycji i bezpieczeństwie.](https://go.microsoft.com/fwlink/p/?LinkId=746661)

**Opcjonalne akcesoria komfortu,** które są dostępne wraz z urządzeniem HoloLens, aby ułatwić ci wygodne dopasowanie. [Więcej informacji na temat dopasowania i komfortu.](hololens2-setup.md#adjust-fit)

## <a name="set-up-windows"></a>Instalowanie systemu Windows

Przy pierwszym uruchomieniu urządzenia HoloLens 2 pierwszym zadaniem jest skonfigurowanie systemu Windows Holographic.  Po uruchomieniu urządzenia HoloLens usłyszysz muzyka i zobaczysz logo systemu Windows.

![Pierwszy ekran podczas pierwszego rozruchu](images/01-magic-moment.png)

Urządzenie HoloLens 2 pomoże Ci wykonać następujące kroki:

1. Wybierz język.

    ![Wybierz język](images/04-language.png)

1. Wybierz swój region.

    ![Wybieranie regionu](images/05-region.png)

1. Skalibruj urządzenie HoloLens dla oczu.  Jeśli zdecydujesz się pominąć przechodzenie, przy następnym logowaniu zostanie wyświetlony monit. 

    1. Najpierw dostosujesz swoją wizję.
    
        ![Ekran wyboru odwzorowania](images/06-et-corners.png)

    2. Aby skalibrować, przyjrzymy się zestawowi celów (nazywanym gemami). Jest w porządku, jeśli migasz lub zamykasz wzrok podczas ciąży, ale nie patrzysz na inne obiekty w pomieszczeniu lub w przestrzeni fizycznej. Urządzenie HoloLens używa tego procesu, aby dowiedzieć się więcej o pozycji oka, aby lepiej renderować świat holograficzny. 

        ![Dostosuj się dla twoich oczu](images/07-adjust-eyes.png)

        Po połyceniu hologramy będą wyświetlane prawidłowo nawet wtedy, gdy wizjer przesuwa się w łb. Informacje o lokalizacji są przechowywane lokalnie na urządzeniu i nie są skojarzone z żadnymi informacjami o koncie. Aby uzyskać więcej informacji, zobacz [Dane dotyczące pomięć i zabezpieczenia](hololens-calibration.md#calibration-data-and-security).

        ![Ukończenie procesu](images/calibration-complete.png)

1. Połącz się z Internetem (wybierz Wi-Fi lub połączenie Ethernet).

     Urządzenie HoloLens automatycznie ustawia strefę czasową na podstawie informacji uzyskanych Wi-Fi sieci. Po zakończeniu instalacji możesz zmienić strefę czasową przy użyciu aplikacji Ustawienia.

    ![Łączenie z siecią Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > Jeśli po zakończeniu kroku Wi-Fi trzeba przełączyć się do innej sieci podczas nadal  w konfiguracji, możesz jednocześnie nacisnąć przyciski Regulacji głośności i Zasilanie, aby powrócić do tego kroku, jeśli używasz systemu operacyjnego w wersji z października 2019 r. lub nowszej.  W przypadku wcześniejszych wersji [](hololens-recovery.md) może być konieczne zresetowanie urządzenia lub ponowne uruchomienie go w lokalizacji, w której sieć Wi-Fi nie jest dostępna, aby uniemożliwić automatyczne nawiązywanie połączenia.
    > 
    > Należy również pamiętać, że podczas konfigurowania urządzenia HoloLens istnieje limit czasu poświadczeń, który wynosi dwie minuty. Nazwę użytkownika/hasło należy wprowadzić w ciągu dwóch minut. W przeciwnym razie pole nazwy użytkownika zostanie automatycznie wyczyszone.

1. Urządzenie HoloLens 2 wyszuka i zastosuje profil rozwiązania Autopilot, jeśli istnieje. Na tym ekranie nie jest potrzebna żadna akcja.
 
    ![Wyszukiwanie profilów rozwiązania Autopilot](images/autopilot-profile-search.png) 

1. Kliknij **przycisk Akceptuj** na ekranie licencjonowania.

    ![Umowa licencyjna systemu Windows](images/windows-license-agreement.png)

1. Zaloguj się do konta użytkownika. Wybierz między **właścicielem jest moja praca lub** szkoła, a **właścicielem jest moja .**

    - Po wybraniu opcji **Moja praca lub szkoła jest jego** właścicielem, zaloguj się przy użyciu konta usługi Azure AD. Jeśli Twoja organizacja korzysta z Azure AD — wersja Premium i skonfigurowała automatyczną rejestrację w uciece MDM, urządzenie HoloLens zostanie automatycznie rejestrowane w funkcji MDM. Jeśli Twoja organizacja nie używa usługi Azure AD — wersja Premium, automatyczna rejestracja w uciekierach mdm nie jest dostępna. W takim przypadku należy ręcznie zarejestrować [urządzenie HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)w programie device management .

        1. Wprowadź informacje o koncie organizacyjnym.
        1. Zaakceptuj zasady zachowania poufności informacji i umowę licencyjną użytkownika końcowego.
        1. Zaloguj się przy użyciu poświadczeń usługi Azure AD. Może to spowodować przekierowanie do strony logowania organizacji.
        1. Kontynuuj konfigurowanie urządzenia.

    - Po wybraniu opcji **I own it (Jestem** właścicielem) zaloguj się przy użyciu konto Microsoft. Po zakończeniu konfiguracji możesz ręcznie [zarejestrować urządzenie HoloLens w u użytkownikach zarządzania urządzeniami.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Wprowadź informacje konto Microsoft użytkownika.
        2. Wprowadź hasło. Jeśli Twoja konto Microsoft wymaga [weryfikacji dwuetapowej (2FA),](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)ukończ proces weryfikacji.

    ![Ustawianie użytkownika](images/13-device-owner.png)

1. Skonfiguruj logowanie irysów, wybierając pozycję **Dalej.** Będziesz przechodzić przez proces podobny do oczu. Po **zakończeniu** skanowania wybierz pozycję Gotowe. Możesz również wybrać pozycję **Pomiń,** aby pominąć ten krok.
    
    ![Ukończenie konfiguracji ](images/setup-iris.png) ![ irysów](images/iris-setup-complete.png) 
     
  
1. Skonfigurujesz numer PIN, aby zalogować się do urządzenia. Ten numer PIN jest specyficzny dla urządzenia. 

    ![Konfigurowanie Windows Hello](images/setup-windows-hello.png)

    ![Konfigurowanie Windows Hello PIN](images/windows-hello-pin.png)

    ![Windows Hello instalacja powiodła się](images/windows-hello-successful.png) 
    
1. Wybierz, czy włączyć mowę na urządzeniach HoloLens 2.

    ![Włączanie Cortany](images/22-do-more-with-voice.png)

1. Wybierz, czy włączyć lokalizację na urządzeniach HoloLens 2.
    
    ![Włączanie usług lokalizowych](images/setup-location-services.png)

1. Wybierz poziom telemetrii. Jeśli możesz, włącz opcję Opcjonalna telemetria. Te informacje naprawdę pomagają zespołowi inżynieryjnemu urządzenia HoloLens.

     ![Poziom telemetrii](images/24-telemetry.png)

1. Dowiedz się, jak używać gestu uruchamiania na urządzeniach HoloLens 2.

     ![Dowiedz się, jak używać gestu uruchamiania, obraz 1](images/26-01-startmenu-learning.png)

     ![Dowiedz się, jak używać gestu uruchamiania, obraz 2](images/26-02-startmenu-learning.png)

Gratulacje!  Konfiguracja jest ukończona i wszystko jest gotowe do korzystania z urządzenia HoloLens!

## <a name="next-steps"></a>Następne kroki

1. Zacznij od razu korzystać z Mixed Reality i nawigować po Windows 10 na urządzeniach HoloLens — zapoznaj się z aplikacją **Porady,** aby uzyskać praktyczne samouczki dotyczące interakcji za pomocą rąk. Użyj gestu uruchamiania, aby przejść do strony Start lub powiedzieć "Przejdź do startu" i wybrać pozycję Porady.

1. Kliknij poniżej, aby kontynuować czytanie o urządzeniach HoloLens 2.

> [!div class="nextstepaction"]
> [Więcej informacji o urządzeniu HoloLens 2](hololens2-basic-usage.md)
