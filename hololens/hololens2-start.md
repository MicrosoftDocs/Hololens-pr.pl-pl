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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036343"
---
# <a name="set-up-your-hololens-2"></a>Konfigurowanie aplikacji HoloLens 2

Przy pierwszym włączeniu urządzenia HoloLens zostanie on pokierowany przez proces konfigurowania urządzenia, logowania się przy użyciu konta użytkownika i HoloLens skalibrowania danych.  Ta sekcja zawiera informacje na temat HoloLens konfiguracji początkowej 2.

W następnej sekcji dowiesz się, jak pracować z HoloLens hologramami. Aby przejść do tego artykułu, zobacz Getting around HoloLens 2 (Poruszanie się [po HoloLens 2).](hololens2-basic-usage.md)

## <a name="before-you-start"></a>Przed rozpoczęciem

Przed rozpoczęciem upewnij się, że są dostępne następujące elementy:

**Połączenie sieciowe**. Aby je skonfigurować, musisz HoloLens siecią. W HoloLens 2 można nawiązać połączenie za pomocą sieci Wi-Fi lub ethernet (potrzebny będzie adapter USB C-to-Ethernet). Przy pierwszym połączeniu będzie potrzebna otwarta sieć chroniona hasłem, która nie wymaga przechodzenia do witryny internetowej ani używania certyfikatów do nawiązywania połączenia. [Dowiedz się więcej o witrynach internetowych, HoloLens korzystają z usługi](hololens-offline.md).

**W konto Microsoft**. Musisz również zalogować się do konta HoloLens przy użyciu konta konto Microsoft (lub przy użyciu konta służbowego, jeśli twoja organizacja jest właścicielem urządzenia). Jeśli nie masz bezpłatnej konto Microsoft, przejdź do account.microsoft.com [i](https://account.microsoft.com) skonfiguruj go bezpłatnie.

**Bezpieczna, dobrze oświetlona przestrzeń bez zagrożeń związanych z trippingiem.** [Informacje o kondycji i bezpieczeństwie.](https://go.microsoft.com/fwlink/p/?LinkId=746661)

**Opcjonalne akcesoria do komfortu,** które są HoloLens, aby pomóc Ci uzyskać najbardziej wygodne dopasowanie. [Więcej informacji na temat dopasowania i komfortu.](hololens2-setup.md#adjust-fit)

## <a name="set-up-windows"></a>Instalowanie systemu Windows

Przy pierwszym uruchomieniu aplikacji HoloLens 2 pierwszym zadaniem jest skonfigurowanie Windows Holographic.  Po uruchomieniu aplikacji HoloLens muzyka i logo firmy Microsoft.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGGGk]

<br/>
<img src="images/01-magic-moment.png" width="500px" alt="First screen during first boot">

Zobaczysz kolibra lecąca wokół.

<img src="images/hummingbird-1.png" width="500px" alt="Hummingbird flying">

Będzie ona podążać Twoją ręką.

<img src="images/hummingbird-2.png" width="500px" alt="Hummingbird flying close up">

Zostanie pojawi się przycisk z logo firmy Microsoft. Naciśnij przycisk , a HoloLens 2 pomoże Ci wykonać następujące kroki:

1. Wybierz język.

    <img src="images/04-language.png" width="500px" alt="Select language">

1. Wybierz swój region.

    <img src="images/05-region.png" width="500px" alt="Select region">

1. Skalibruj HoloLens wzroku.  Jeśli zdecydujesz się pominąć przechodzenie, przy następnym logowaniu zostanie wyświetlony monit. 

    1. Najpierw dostosujesz swoją wizję.
    
    <img src="images/06-et-corners.png" width="500px" alt="Calibration selection screen">
    
    2. Aby skalibrować, przyjrzymy się zestawowi celów (nazywanym gemami). Jest w porządku, jeśli migasz lub zamykasz wzrok podczas ciąży, ale starasz się nie zaglądać na inne obiekty w pomieszczeniu lub w przestrzeni fizycznej. HoloLens używa tego procesu, aby dowiedzieć się więcej o pozycji oka, dzięki czemu może lepiej renderować świat holograficzny. 

        <img src="images/07-adjust-eyes.png" width="500px" alt="Adjust for your eyes">

        Po połyceniu hologramy będą wyświetlane prawidłowo nawet wtedy, gdy wizjer przesuwa się w łb. Informacje o opadach są przechowywane lokalnie na urządzeniu i nie są skojarzone z żadnymi informacjami o koncie. Aby uzyskać więcej informacji, zobacz [Dane dotyczące pomięć i zabezpieczenia](hololens-calibration.md#calibration-data-and-security).

        <img src="images/calibration-complete.png" width="500px" alt="Calibration is complete">

1. Połączenie z Internetem (wybierz pozycję Wi-Fi lub połączenie Ethernet).

     HoloLens automatycznie ustawia strefę czasową na podstawie informacji uzyskanych z Wi-Fi sieci. Po zakończeniu instalacji możesz zmienić strefę czasową przy użyciu Ustawienia aplikacji.

    ![Połączenie do sieci Wi-Fi.](images/11-network.png)

    > [!NOTE] 
    > Jeśli po zakończeniu kroku Wi-Fi konieczne będzie przełączenie się do innej sieci podczas  nadal w  konfiguracji, możesz jednocześnie nacisnąć przyciski Regulacji głośności i Zasilanie, aby powrócić do tego kroku, jeśli używasz systemu operacyjnego w wersji z października 2019 r. lub nowszej. W przypadku wcześniejszych wersji [](hololens-recovery.md) może być konieczne zresetowanie urządzenia lub jego ponowne uruchomienie w lokalizacji, w której sieć Wi-Fi nie jest dostępna, aby uniemożliwić automatyczne nawiązywanie połączenia.
    > 
    > Należy również pamiętać, że HoloLens instalacji istnieje limit czasu poświadczeń o dwóch minutach. Nazwę użytkownika/hasło należy wprowadzić w ciągu dwóch minut. W przeciwnym razie pole nazwy użytkownika zostanie automatycznie wyczyszone.

1. HoloLens 2 wyszuka i zastosuje profil rozwiązania Autopilot, jeśli istnieje. Na tym ekranie nie jest potrzebna żadna akcja.
 
    ![Wyszukiwanie profilów rozwiązania Autopilot.](images/autopilot-profile-search.png) 

1. Kliknij **przycisk Akceptuj** na ekranie licencjonowania.

    ![Windows umowy licencyjnej.](images/windows-license-agreement.png)

1. Zaloguj się do konta użytkownika. Wybierz między **właścicielem jest moja praca lub** szkoła, a **właścicielem jest .**

    ![Ustaw użytkownika.](images/13-device-owner.png)
    - Po wybraniu opcji **My work or school owns it**(Moja praca lub szkoła jest jego właścicielem) zaloguj się przy użyciu konta usługi Azure AD. Jeśli Twoja organizacja korzysta z Azure AD — wersja Premium i skonfigurowała automatyczną rejestrację w HoloLens MDM, program HoloLens automatycznie. Jeśli Twoja organizacja nie korzysta z Azure AD — wersja Premium, automatyczna rejestracja w uciekierach mdm nie jest dostępna. W takim przypadku należy ręcznie zarejestrować [usługę HoloLens zarządzania urządzeniami.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Wprowadź informacje o koncie organizacyjnym.
        1. Zaakceptuj zasady zachowania poufności informacji i umowę licencyjną użytkownika końcowego.
        1. Zaloguj się przy użyciu poświadczeń usługi Azure AD. Może to spowodować przekierowanie do strony logowania organizacji.
        1. Kontynuuj konfigurowanie urządzenia.

    - Po wybraniu opcji **I own it (Jestem** właścicielem) zaloguj się przy użyciu konto Microsoft. Po zakończeniu instalacji można ręcznie zarejestrować program [HoloLens zarządzania urządzeniami.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Wprowadź informacje konto Microsoft użytkownika.
        2. Wprowadź hasło. Jeśli Twoja konto Microsoft wymaga [weryfikacji dwuetapowej (2FA),](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)ukończ proces weryfikacji.

        
1. Skonfiguruj logowanie irysów, wybierając pozycję **Dalej.** Będziesz przechodzić przez proces podobny do oczu. Po **zakończeniu** skanowania wybierz pozycję Gotowe. Możesz również wybrać pozycję **Pomiń,** aby pominąć ten krok.
    
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

1. Zacznij od razu wchodzić w interakcje z Mixed Reality i nawigować po Windows 10 na komputerze HoloLens — zapoznaj się z aplikacją **Wskazówki,** aby uzyskać praktyczne samouczki dotyczące interakcji za pomocą rąk. Użyj gestu uruchamiania, aby przejść do przycisku Start lub powiedzieć "Przejdź do startu", a następnie wybierz Wskazówki.

1. Kliknij poniżej, aby kontynuować czytanie na temat HoloLens 2.

> [!div class="nextstepaction"]
> [Więcej informacji o urządzeniu HoloLens 2](hololens2-basic-usage.md)
