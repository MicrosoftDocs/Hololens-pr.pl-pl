---
title: Konfigurowanie aplikacji HoloLens 2
description: Dowiedz się, jak po raz pierwszy HoloLens 2 za pośrednictwem sieci Wi-Fi przy użyciu konta Microsoft (MSA) lub Azure Active Directory (AAD).
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
ms.openlocfilehash: 8f07ed42c873b62b3b4201c2756b55bbb29707d3
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428611"
---
# <a name="set-up-your-hololens-2"></a>Konfigurowanie aplikacji HoloLens 2

Przy pierwszym włączeniu urządzenia HoloLens użytkownik zostanie pokierowany przez proces konfigurowania urządzenia, logowania przy użyciu konta użytkownika i skalibrowania HoloLens pamięci.  Ta sekcja zawiera 2 HoloLens konfiguracji początkowej.

W następnej sekcji dowiesz się, jak pracować z HoloLens hologramami. Aby przejść do tego artykułu, zobacz [Getting around HoloLens 2 (HoloLens 2).](hololens2-basic-usage.md)

## <a name="before-you-start"></a>Przed rozpoczęciem

Przed rozpoczęciem upewnij się, że są dostępne następujące elementy:

**Połączenie sieciowe**. Aby ją skonfigurować, musisz HoloLens siecią. W HoloLens 2 można nawiązać połączenie z siecią Wi-Fi lub ethernet (potrzebny będzie adapter USB C-to-Ethernet). Przy pierwszym połączeniu będzie potrzebna otwarta sieć chroniona hasłem, która nie wymaga przechodzenia do witryny internetowej ani używania certyfikatów do nawiązywania połączenia. [Dowiedz się więcej o witrynach internetowych, HoloLens korzystają z usługi](hololens-offline.md).

**W konto Microsoft**. Musisz również zalogować się do aplikacji HoloLens przy użyciu konta konto Microsoft (lub przy użyciu konta służbowego, jeśli twoja organizacja jest właścicielem urządzenia). Jeśli nie masz bezpłatnej konto Microsoft przejdź do account.microsoft.com [i](https://account.microsoft.com) skonfiguruj je bezpłatnie.

**Bezpieczna, dobrze oświetlona przestrzeń bez zagrożeń związanych z trippingiem.** [Informacje o kondycji i bezpieczeństwie.](https://go.microsoft.com/fwlink/p/?LinkId=746661)

**Opcjonalne akcesoria komfortu,** które są HoloLens, aby pomóc Ci uzyskać najbardziej wygodne dopasowanie. [Więcej informacji na temat dopasowania i komfortu.](hololens2-setup.md#adjust-fit)

## <a name="set-up-windows"></a>Instalowanie systemu Windows

Przy pierwszym uruchomieniu komputera HoloLens 2 pierwszym zadaniem jest skonfigurowanie Windows Holographic.  Po uruchomieniu aplikacji HoloLens muzyka i logo firmy Microsoft.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGGGk]

<br/>
<img src="images/01-magic-moment.png" width="500px" alt="First screen during first boot">

Zobaczysz, jak chyli się kolibra.

<img src="images/hummingbird-1.png" width="500px" alt="Hummingbird flying">

Będzie ona podążać Twoją rękę.

<img src="images/hummingbird-2.png" width="500px" alt="Hummingbird flying close up">

Pojawi się przycisk z logo firmy Microsoft. Naciśnij przycisk , a HoloLens 2 pomoże Ci wykonać następujące kroki:

1. Wybierz język.

    <img src="images/04-language.png" width="500px" alt="Select language">

1. Wybierz swój region.

    <img src="images/05-region.png" width="500px" alt="Select region">

1. Skalibruj HoloLens dla oczu.  Jeśli zdecydujesz się pominąć sekcję, przy następnym logowaniu zostanie wyświetlony monit. 

    1. Najpierw dostosujesz swoją wizję.
    
    <img src="images/06-et-corners.png" width="500px" alt="Calibration selection screen">
    
    2. Aby skalibrować, przyjrzymy się zestawowi celów (nazywanym gemami). Jest w porządku, jeśli migasz lub zamykasz wzrok podczas odtęchnięcia, ale próbujesz nie zaglądać na inne obiekty w pomieszczeniu lub w przestrzeni fizycznej. HoloLens używa tego procesu, aby dowiedzieć się więcej o pozycji oka, dzięki czemu może lepiej renderować świat holograficzny. 

        <img src="images/07-adjust-eyes.png" width="500px" alt="Adjust for your eyes">

        Po nachłoeniu hologramy będą wyświetlane prawidłowo nawet wtedy, gdy przyczomienie przesuwa się w kierunku głowy. Informacje o lokalizacji są przechowywane lokalnie na urządzeniu i nie są skojarzone z żadnymi informacjami o koncie. Aby uzyskać więcej informacji, zobacz [Temat Dane i zabezpieczenia dotyczące bezpieczeństwa.](hololens-calibration.md#calibration-data-and-security)

        <img src="images/calibration-complete.png" width="500px" alt="Calibration is complete">

1. Połączenie z Internetem (wybierz pozycję Wi-Fi lub połączenie Ethernet).

     HoloLens automatycznie ustawia strefę czasową na podstawie informacji uzyskanych z Wi-Fi sieci. Po zakończeniu instalacji możesz zmienić strefę czasową przy użyciu Ustawienia aplikacji.

    ![Połączenie do sieci Wi-Fi.](images/11-network.png)

    > [!NOTE] 
    > Jeśli po zakończeniu kroku Wi-Fi konieczne będzie przełączenie się do innej sieci podczas instalacji, możesz nacisnąć jednocześnie przyciski Volume **Down** i **Power,** aby wrócić do tego kroku, jeśli używasz systemu operacyjnego w wersji z października 2019 r. lub nowszej. W przypadku wcześniejszych wersji [](hololens-recovery.md) może być konieczne zresetowanie urządzenia lub jego ponowne uruchomienie w lokalizacji, w której sieć Wi-Fi jest dostępna, aby uniemożliwić automatyczne nawiązywanie połączenia.
    > 
    > Należy również pamiętać, że HoloLens instalacji istnieje limit czasu poświadczeń, który wynosi dwie minuty. Nazwę użytkownika/hasło należy wprowadzić w ciągu dwóch minut. W przeciwnym razie pole nazwy użytkownika zostanie automatycznie wyczyszone.

1. HoloLens 2 wyszuka i zastosuje profil rozwiązania Autopilot, jeśli istnieje. Na tym ekranie nie jest potrzebna żadna akcja.
 
    ![Wyszukiwanie profilów rozwiązania Autopilot.](images/autopilot-profile-search.png) 

1. Kliknij **przycisk Akceptuj** na ekranie licencjonowania.

    ![Windows umowy licencyjnej.](images/windows-license-agreement.png)

1. Zaloguj się do konta użytkownika. Możesz wybrać pozycję **Moja praca lub szkoła** jest jego właścicielem, a ja jestem **jego właścicielem.**

    ![Ustaw użytkownika.](images/13-device-owner.png)
    - Gdy wybierzesz pozycję My work or school owns it (Moja praca lub szkoła jest jego **właścicielem),** zaloguj się przy użyciu konta usługi Azure AD. Jeśli Twoja organizacja korzysta z Azure AD — wersja Premium i skonfigurowała automatyczną rejestrację mdm, HoloLens automatycznie rejestruje się w funkcji MDM. Jeśli Twoja organizacja nie korzysta z Azure AD — wersja Premium, automatyczna rejestracja mdm nie jest dostępna. W takim przypadku należy ręcznie zarejestrować usługę HoloLens [zarządzania urządzeniami.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Wprowadź informacje o koncie organizacyjnym.
        1. Zaakceptuj oświadczenie o ochronie prywatności i umowę licencyjną użytkownika końcowego.
        1. Zaloguj się przy użyciu poświadczeń usługi Azure AD. Może to spowodować przekierowanie do strony logowania organizacji.
        1. Kontynuuj konfigurowanie urządzenia.

    - Gdy wybierzesz **pozycję I own it (Jestem właścicielem),** zaloguj się przy użyciu konto Microsoft. Po zakończeniu konfiguracji możesz ręcznie zarejestrować urządzenie w [HoloLens zarządzania urządzeniami.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Wprowadź swoje konto Microsoft informacje.
        2. Wprowadź hasło. Jeśli Twoja konto Microsoft wymaga [weryfikacji dwuetapowej (2FA),](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)ukończ proces weryfikacji.

        
1. Skonfiguruj logowanie irysów, wybierając pozycję **Dalej.** Będziesz przechodzić przez podobne środowisko, jak w przypadku wzroku. Po **zakończeniu** skanowania wybierz pozycję Gotowe. Możesz również wybrać pozycję **Pomiń,** aby pominąć ten krok.
    
    <img src="images/setup-iris.png" width="500px" alt="Iris setup">

    <img src="images/iris-setup-complete.png" width="500px" alt="Iris setup completion">

     
  
1. Skonfigurujesz numer PIN, aby zalogować się do urządzenia. Ten numer PIN jest specyficzny dla urządzenia. 

    ![Skonfiguruj Windows Hello.](images/setup-windows-hello.png)

    ![Skonfiguruj Windows Hello PIN.](images/windows-hello-pin.png)

    ![Windows Hello Instalacja powiodła się.](images/windows-hello-successful.png) 

    
1. Wybierz, czy włączyć mowę na HoloLens 2.

    <img src="images/22-do-more-with-voice.png" width="500px" alt="Enable Cortana">

1. Wybierz, czy włączyć lokalizację na HoloLens 2.
    
    <img src="images/setup-location-services.png" width="500px" alt="Enable location services">

1. Wybierz poziom telemetrii. Jeśli możesz, włącz opcję Opcjonalna telemetria. Te informacje naprawdę pomagają zespołowi HoloLens inżynieryjnemu.

    <img src="images/24-telemetry.png" width="500px" alt="Telemetry level">


1. Dowiedz się, jak używać gestu uruchamiania na HoloLens 2.

    <img src="images/26-01-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 1">

    <img src="images/26-02-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 2">
    
    > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3Wxng]
    
    Gratulacje!  Konfiguracja jest ukończona i wszystko jest gotowe do użycia HoloLens!

## <a name="next-steps"></a>Następne kroki

1. Zacznij od razu korzystać z aplikacji Mixed Reality i nawigować po aplikacji Windows 10 na platformie HoloLens — zapoznaj się z aplikacją **Wskazówki,** aby uzyskać praktyczne samouczki dotyczące interakcji za pomocą rąk. Użyj gestu uruchamiania, aby przejść do przycisku Start lub powiedzieć "Go to Start" (Przejdź do startu) i Wskazówki.

1. Kliknij poniżej, aby kontynuować czytanie o HoloLens 2.

> [!div class="nextstepaction"]
> [Więcej informacji o urządzeniu HoloLens 2](hololens2-basic-usage.md)
