---
title: Konfigurowanie urządzenia HoloLens (1. generacja)
description: Dowiedz się, jak po raz pierwszy skonfigurować urządzenie HoloLens (1. generacja) za pośrednictwem sieci Wi-Fi przy użyciu konta Microsoft (MSA) lub Azure Active Directory (AAD).
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
ms.openlocfilehash: f0ec62e55f15fda6d5a8304ea2bb77039d644b9e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378312"
---
# <a name="set-up-your-hololens-1st-gen"></a>Konfigurowanie urządzenia HoloLens (1. generacja)

Przy pierwszym włączeniu urządzenia HoloLens zostaniesz pokierowany przez proces skalibrowania urządzenia, konfigurowania urządzenia i logowania.  Ten artykuł zawiera informacje na temat pierwszego uruchomienia i konfiguracji urządzenia HoloLens (1. generacji).

W następnej sekcji dowiesz się, jak pracować z urządzeniem HoloLens i korzystać z hologramów. Aby przejść do tego artykułu, zobacz [Wprowadzenie do urządzenia HoloLens (1. generacja).](hololens1-basic-usage.md)

## <a name="before-you-start"></a>Przed rozpoczęciem

Przed rozpoczęciem upewnij się, że są dostępne następujące elementy:

**Połączenie Wi-Fi .** Aby go skonfigurować, musisz połączyć urządzenie HoloLens Wi-Fi siecią. Przy pierwszym połączeniu będzie potrzebna otwarta sieć chroniona hasłem, która nie wymaga przechodzenia do witryny internetowej ani używania certyfikatów do nawiązywania połączenia. [Dowiedz się więcej o witrynach internetowych, z których korzysta urządzenie HoloLens.](hololens-offline.md)

**Konto konto Microsoft lub konto służbowe.** Musisz również użyć konta konto Microsoft (lub konta służbowego, jeśli Twoja organizacja jest właścicielem urządzenia) do logowania się na urządzeniu HoloLens. Jeśli nie masz bezpłatnej konto Microsoft przejdź do account.microsoft.com [i](https://account.microsoft.com) skonfiguruj go bezpłatnie.

**Bezpieczna, dobrze oświetlona przestrzeń bez zagrożeń związanych z trippingiem.** [Informacje o kondycji i bezpieczeństwie.](https://go.microsoft.com/fwlink/p/?LinkId=746661)

**Opcjonalne akcesoria komfortu,** które są dostępne wraz z urządzeniem HoloLens, aby ułatwić ci wygodne dopasowanie. [Więcej informacji na temat dopasowania i komfortu.](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)

> [!NOTE]
>  
> - Gdy po raz pierwszy używasz urządzenia HoloLens, [Cortana](hololens-cortana.md) jest już w trybie i jest gotowa do przewodnika (chociaż nie będzie w stanie odpowiedzieć na Twoje pytania do momentu skonfigurowania urządzenia). Cortanę można wyłączyć w dowolnym momencie w ustawieniach Cortany.
> - Aby przełączyć się do chińskiej lub japońskiej wersji urządzenia HoloLens, należy pobrać kompilację dla języka na komputerze, a następnie zainstalować ją na urządzeniach HoloLens. Aby uzyskać więcej informacji, zobacz Instalowanie zlokalizowanych wersji urządzenia [HoloLens (1. generacja).](hololens1-install-localized.md)

## <a name="start-your-hololens-and-set-up-windows"></a>Uruchamianie urządzenia Hololens i konfigurowanie systemu Windows

Przy pierwszym uruchomieniu urządzenia HoloLens pierwszym zadaniem jest skonfigurowanie systemu Windows Holographic na urządzeniu.

1. Połącz się z Internetem (urządzenie HoloLens przeprowadzi Cię przez Wi-Fi sieć).

1. Zaloguj się do konta użytkownika. Wybieraj **między właścicielem jest** moja praca lub **szkoła, a ja jestem jego właścicielem.**
    - Jeśli wybierzesz pozycję My work or school owns it (Moja praca lub szkoła jest jego **właścicielem),** zaloguj się przy użyciu konta usługi Azure AD. Jeśli Twoja organizacja korzysta z Azure AD — wersja Premium i skonfigurowała automatyczną rejestrację mdm, urządzenie HoloLens automatycznie rejestruje się w funkcji MDM. Jeśli Twoja organizacja nie używa urządzenia Azure AD — wersja Premium, automatyczna rejestracja w uowie mdm nie jest dostępna, dlatego konieczne będzie ręczne zarejestrowanie urządzenia [HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)w funkcji zarządzania urządzeniami . Aby zalogować się do urządzenia po raz pierwszy przy użyciu konta służbowego, wykonaj następujące kroki:
        1. Wprowadź informacje o koncie organizacyjnym.
        1. Zaakceptuj zasady zachowania poufności informacji.
        1. Zaloguj się przy użyciu poświadczeń usługi Azure AD. Może to spowodować przekierowanie do strony logowania organizacji.
        1. Kontynuuj konfigurowanie urządzenia.
    - Gdy wybierzesz **pozycję I own it (Jestem właścicielem),** zaloguj się przy użyciu konto Microsoft. Po zakończeniu konfiguracji możesz ręcznie zarejestrować [urządzenie HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)w u użytkownikach zarządzania urządzeniami .
        1. Wprowadź informacje konto Microsoft użytkownika.
        1. Wprowadź hasło. Jeśli Twoja konto Microsoft wymaga [weryfikacji dwuetapowej (2FA),](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)ukończ proces weryfikacji.

1. Urządzenie ustawia strefę czasową na podstawie informacji uzyskiwanych z Wi-Fi sieci.

## <a name="calibration"></a>Kalibracja

Po wprowadzeniu Cortany następnym krokiem konfiguracji jest odejmowanie. Aby uzyskać najlepsze środowisko dla urządzenia HoloLens, należy ukończyć proces odszukania podczas instalacji.

Urządzenie HoloLens (1. generacja) używa odległości między [](https://en.wikipedia.org/wiki/Interpupillary_distance)źrenicy (ipd lub odległość międzypoczelniowa), aby hologramów było jasne i łatwe w interakcji. Jeśli adres IPD jest nieprawidłowy, hologramy mogą wydawać się niestabilne lub w nieprawidłowej odległości.

Podczas ciąży urządzenie HoloLens prosi o wyrównanie palca do serii sześciu obiektów docelowych na oko. Urządzenie HoloLens używa tego procesu do ustawienia poprawnego adresu IPD dla oczu. Jeśli trzeba zaktualizować lub dostosować strefę dla nowego użytkownika, nowy użytkownik może uruchomić aplikację Namów poza konfiguracją.

![Ekran wyrównywania linii papilarnych usługi IPD w drugim kroku](./images/ipd-finger-alignment-300px.jpg)

*Ekran wyrównywania linii papilarnych usługi IPD w drugim kroku*

Gratulacje! Konfiguracja jest ukończona i możesz rozpocząć korzystanie z urządzenia HoloLens.

## <a name="next-steps"></a>Następne kroki

> [!div class="nextstepaction"]
> [Wprowadzenie do urządzenia HoloLens (1. generacja)](hololens1-basic-usage.md)
