---
title: Konfigurowanie HoloLens (1. generacja)
description: Dowiedz się, jak skonfigurować usługę HoloLens (1. generacja) po raz pierwszy za pośrednictwem sieci Wi-Fi przy użyciu konta Microsoft (MSA) lub Azure Active Directory (AAD).
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 06b7142be471d0db3f45812654288a33425abd60
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427758"
---
# <a name="set-up-your-hololens-1st-gen"></a>Konfigurowanie aplikacji HoloLens (1. generacja)

Przy pierwszym włączeniu urządzenia HoloLens zostaniesz pokierowany przez skalibrowanie urządzenia, skonfigurowanie urządzenia i zalogowanie się.  W tym artykule o krok po HoloLens (1. generacji) pierwszego uruchomienia i konfiguracji.

W następnej sekcji dowiesz się, jak pracować z HoloLens hologramami. Aby przejść do tego artykułu, zobacz Wprowadzenie do HoloLens [(1. generacji).](hololens1-basic-usage.md)

## <a name="before-you-start"></a>Przed rozpoczęciem

Przed rozpoczęciem upewnij się, że są dostępne następujące elementy:

**Połączenie Wi-Fi .** Aby ją skonfigurować, musisz HoloLens z siecią Wi-Fi sieciową. Przy pierwszym połączeniu będzie potrzebna otwarta sieć chroniona hasłem, która nie wymaga przechodzenia do witryny internetowej ani używania certyfikatów do nawiązywania połączenia. [Dowiedz się więcej o witrynach internetowych, HoloLens korzystają z usługi](hololens-offline.md).

**Konto konto Microsoft lub konto służbowe.** Musisz również użyć konta konto Microsoft (lub konta służbowego, jeśli Twoja organizacja jest właścicielem urządzenia), aby zalogować się do HoloLens. Jeśli nie masz bezpłatnej konto Microsoft przejdź do [](https://account.microsoft.com) account.microsoft.com i skonfiguruj je bezpłatnie.

**Bezpieczna, dobrze oświetlona przestrzeń bez zagrożeń związanych z trippingiem.** [Informacje o kondycji i bezpieczeństwie.](https://go.microsoft.com/fwlink/p/?LinkId=746661)

**Opcjonalne akcesoria komfortu,** które są HoloLens, aby pomóc Ci uzyskać najbardziej wygodne dopasowanie. [Więcej informacji na temat dopasowania i komfortu.](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)

> [!NOTE]
>  
> - Przy pierwszym użyciu usługi HoloLens program [Cortana](hololens-cortana.md) jest już wł. i gotowy do przewodnika (chociaż nie będzie w stanie odpowiedzieć na Twoje pytania do momentu skonfigurowania urządzenia). Możesz wyłączyć Cortana w dowolnym momencie w Cortana ustawień aplikacji.
> - Aby przełączyć się do chińskiej lub japońskiej wersji języka HoloLens, musisz pobrać kompilację dla języka na komputerze, a następnie zainstalować ją na komputerze HoloLens. Aby uzyskać więcej informacji, zobacz [Instalowanie zlokalizowanych wersji HoloLens (1. generacji).](hololens1-install-localized.md)

## <a name="start-your-hololens-and-set-up-windows"></a>Uruchamianie urządzenia Hololens i konfigurowanie Windows

Przy pierwszym uruchomieniu aplikacji HoloLens pierwszym zadaniem jest skonfigurowanie Windows Holographic na urządzeniu.

1. Połączenie do Internetu (HoloLens do wybrania Wi-Fi sieci).

1. Zaloguj się do konta użytkownika. Wybieraj **między właścicielem jest** moja praca lub szkoła, a ja jestem jego **właścicielem.**
    - Jeśli wybierzesz pozycję My work or school owns it (Moja praca lub szkoła jest jego **właścicielem),** zaloguj się przy użyciu konta usługi Azure AD. Jeśli Organizacja korzysta z usługi Azure AD — wersja Premium i skonfigurowała automatyczną rejestrację mdm, HoloLens automatycznie rejestruje się w uścibce MDM. Jeśli Twoja organizacja nie korzysta z usługi Azure AD — wersja Premium, automatyczna rejestracja mdm nie jest dostępna, dlatego konieczne będzie ręczne zarejestrowanie HoloLens [zarządzania urządzeniami.](hololens-enroll-mdm.md#different-ways-to-enroll) Aby zalogować się do urządzenia po raz pierwszy przy użyciu konta służbowego, wykonaj następujące kroki:
        1. Wprowadź informacje o koncie organizacyjnym.
        1. Zaakceptuj zasady zachowania poufności informacji.
        1. Zaloguj się przy użyciu poświadczeń usługi Azure AD. Może to spowodować przekierowanie do strony logowania organizacji.
        1. Kontynuuj konfigurowanie urządzenia.
    - Jeśli wybierzesz **pozycję I own it (Jestem właścicielem),** zaloguj się przy użyciu konto Microsoft. Po zakończeniu konfiguracji możesz ręcznie zarejestrować urządzenia [w HoloLens zarządzania urządzeniami.](hololens-enroll-mdm.md#different-ways-to-enroll)
        1. Wprowadź informacje konto Microsoft użytkownika.
        1. Wprowadź hasło. Jeśli Twoja konto Microsoft wymaga [weryfikacji dwuetapowej (2FA),](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)ukończ proces weryfikacji.

1. Urządzenie ustawia strefę czasową na podstawie informacji, które uzyskuje z Wi-Fi sieci.

## <a name="calibration"></a>Kalibracja

Po Cortana się, następnym krokiem konfiguracji jest odejmowanie od siebie. Aby uzyskać najlepsze HoloLens środowisko pracy, należy ukończyć proces konserwacji podczas instalacji.

HoloLens (1. generacja) używa odległości między źrenicy [](https://en.wikipedia.org/wiki/Interpupillary_distance)(ipd lub odległość międzypoczelniowa), aby hologramów było jasne i łatwe w interakcjach. Jeśli adres IPD jest nieprawidłowy, hologramy mogą wydawać się niestabilne lub mieć nieprawidłową odległość.

Podczas ciąży HoloLens, aby wyrównać palcem z serią sześciu obiektów docelowych na oko. HoloLens używa tego procesu do ustawienia poprawnego adresu IPD dla oczu. Jeśli trzeba zaktualizować lub dostosować strefę dla nowego użytkownika, nowy użytkownik może uruchomić aplikację Namów poza konfiguracją.

![Ekran wyrównywania linii papilarnych IPD w drugim kroku.](./images/ipd-finger-alignment-300px.jpg)

*Ekran wyrównywania linii papilarnych usługi IPD w drugim kroku*

Gratulacje! Konfiguracja jest ukończona i można rozpocząć korzystanie z HoloLens.

## <a name="next-steps"></a>Następne kroki

> [!div class="nextstepaction"]
> [Wprowadzenie do HoloLens (1. generacja)](hololens1-basic-usage.md)
