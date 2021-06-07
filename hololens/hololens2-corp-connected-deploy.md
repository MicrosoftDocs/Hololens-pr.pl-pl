---
title: Przewodnik wdrażania — urządzenie HoloLens 2 połączone z firmą z usługą Dynamics 365 — przewodniki — wdrażanie
description: Dowiedz się, jak skonfigurować wdrożenia urządzeń HoloLens 2 za pośrednictwem firmowej sieci połączonej przy użyciu przewodników usługi Dynamics 365.
keywords: HoloLens, zarządzanie, połączone firmowe, przewodniki usługi Dynamics 365, AAD, Azure AD, MDM, Mobile Zarządzanie urządzeniami
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: febf56f94a5cab623fd7ad08ae7abf7050224717
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378306"
---
# <a name="deploy---corporate-connected-guide"></a>Wdrażanie — przewodnik po połączeniu firmowym

Ważnym elementem każdego wdrożenia jest upewnienie się, że wdrożenie jest prawidłowo skonfigurowane przed jego testowaniem, aby zapewnić bezproblemowe środowisko użytkownika końcowego.

Ponieważ wdrażamy certyfikat Wi-Fi za pośrednictwem rozwiązania MDM, musimy początkowo skonfigurować urządzenie HoloLens i zarejestrować urządzenia w otwartej sieci Wi-Fi lub w sieci, która nie wymaga certyfikatu. Po zakończeniu pracy urządzeń HoloLens z funkcjami OOBE i Enrolled urządzenie otrzyma wcześniej skonfigurowany certyfikat sieciowy i aplikację LOB, a następnie sprawdzimy, czy oba urządzenia zostały odebrane.

Następnie będziesz w stanie potwierdzić, że możesz utworzyć i obsługiwać przewodnik testowy.

## <a name="enrollment-validation"></a>Walidacja rejestracji

Teraz, gdy wszystko jest prawidłowo skonfigurowane dla usługi Azure AD i rejestracji w usłudze MDM, reszta powinna być teraz przystawką. Potrzebne będzie połączenie sieciowe Wi-Fi urządzenie HoloLens oraz jedno z wcześniej skonfigurowanych kont użytkowników usługi Azure AD.

Jeśli urządzenie nie znajduje się obecnie w stanie ustawień fabrycznych, byłby to dobry czas na [reflashowanie urządzenia.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)

1. Gdy urządzenie będzie w stanie OOBE, musisz rozpocząć interakcję i podążać za monitami.

2. Połącz się z otwartą Wi-Fi siecią, która nie wymaga certyfikatów do dołączenia do sieci Wi-Fi. Dzięki temu urządzenie będzie w stanie pobrać certyfikat, który będzie używany na stronie Wi-Fi po wstępnej konfiguracji.

3. Monit krytyczny pojawi się po wyświetleniu monitu **Kto jest właścicielem tego urządzenia HoloLens?** Wybierz **pozycję My work or school owns it and** enter your Azure AD account credentials (Moja praca lub szkoła jest jego właścicielem) i wprowadź poświadczenia konta usługi Azure AD.

4. Po pomyślnym zarejestrowaniu zostanie wyświetlony monit o skonfigurowanie numeru PIN. Ten numer PIN jest unikatowy dla tego urządzenia dla tego użytkownika. Zostanie również wyświetlony monit o przeskanowania irysów, dane głosowe i ustawienia telemetrii, a na koniec dowiesz się, jak otworzyć menu Start i ukończyć OOBE.

5. Po otwarciu strony Mixed Reality Home otwórz ekran menu Start użyciu właśnie poznanych **gestów** Start.

6. Wybierz aplikację **Ustawienia** i wybierz pozycję **System**. Pierwszymi informacjami, które zobaczysz, jest nazwa urządzenia, które dla urządzenia HoloLens 2 będzie hololensem, po którym następuje sześć &quot; &quot; znaków.

7. Zanotuj tę nazwę.

    ![Ekran Ustawień urządzenia HoloLens 2](./images/hololens2-settings-about.jpg)

8. Sprawdź, czy urządzenie zostało pomyślnie przyłączone do usługi Azure AD. Istnieją dwa sposoby:

    1.  Aplikacja Ustawienia. W **menu Ustawienia** wybierz pozycję Konta **Uzyskaj** dostęp do konta  ->  **służbowego.** Na tym ekranie możesz sprawdzić, czy użytkownik został pomyślnie zarejestrowany, widząc komunikat Połączono z &quot; nazwąAAD&#39;usługi Azure AD. Połączone przez *yourusername@nameofAAD.onmicrosoft.com* . Pozwoli to sprawdzić, czy urządzenie jest przyłączone do organizacji&#39;usługi Azure AD.

    1. W [Azure Portal](https://portal.azure.com/#home). Przejdź do **Azure Active Directory**  ->  **Urządzenia**  ->  **Wszystkie urządzenia** i wyszukaj nazwę urządzenia. W obszarze Typ sprzężenia będzie on pokazywany jako "Dołączenia do usługi Azure AD".
        ![Weryfikowanie typu dołączenia w usłudze Azure AD](./images/hololens2-devices-all-devices.png)

9. Sprawdź, czy urządzenie zostało zarejestrowane w usłudze MDM. Istnieją dwa sposoby:

    1. W **menu Ustawienia** wybierz pozycję Konta **Uzyskaj** dostęp do konta  ->  **służbowego.** Na tym ekranie możesz sprawdzić, czy użytkownik został pomyślnie zarejestrowany, widząc komunikat Połączono z &quot; nazwąAAD&#39;usługi Azure AD. Połączone przez *yourusername@nameofAAD.onmicrosoft.com* . Z tego konta uzyskaj dostęp do konta służbowego, wybierając pozycję &quot; Połączono z nazwąAAD&#39;usługi Azure AD. Połączono yourusername@nameofAAD.onmicrosoft.com &quot; się i wybierz **przycisk** Informacje.

    1. [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home). Zaloguj się i wybierz **pozycję Urządzenia, a** **następnie pozycję Wszystkie urządzenia.** W tym miejscu możesz wyszukać nazwę urządzenia HoloLens&#39;s. Urządzenie HoloLens powinno być wyświetlane na liście w usłudze Intune.

        ![Weryfikowanie zarządzania przez usługę Intune w usłudze Azure AD](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi weryfikacji certyfikatu

Do tej pory urządzenie powinno otrzymało certyfikat Wi-Fi. Najprostszą weryfikacją, jaką można wykonać, jest próba nawiązania połączenia Wi-Fi, dla którego&#39;został otrzymany certyfikat. Otwórz aplikację **Ustawienia i** przejdź do sieci **&amp; Internet**  ->  **Wi-Fi,** a następnie wybierz połączenie Wi-Fi. Po na połączeniu otwórz aplikację Microsoft Edge i upewnij się, że możesz przejść do witryny internetowej.

Aby potwierdzić, że certyfikat został otrzymany na urządzeniu, możesz użyć [Menedżera certyfikatów](https://docs.microsoft.com/hololens/certificate-manager).

## <a name="validate-lob-app-install"></a>Weryfikowanie instalacji aplikacji LOB

Aby wyświetlić postęp instalacji aplikacji zarządzanej, możesz sprawdzić, czy aplikacja jest zainstalowana, lub sprawdzić pozycję Ustawienia. Po skonfigurowaniu aplikacji LOB jako wymaganej instalacji dla naszej grupy po zarejestrowaniu urządzenia HoloLens z użytkownikiem w przypisanej grupie aplikacja zostanie automatycznie pobrana na urządzenie HoloLens.

Otwórz menu Start i wybierz **pozycję Wszystkie aplikacje**. W zależności od liczby posiadanych aplikacji może  być konieczne użycie przycisków strony w górę **lub w dół** strony.

Aby zweryfikować instalację aplikacji na urządzeniu, możesz to zrobić za pomocą opcji Ustawienia Konta Uzyskaj dostęp do konta służbowego, wybierz konto, a następnie przycisk Informacje i przewiń w dół, aby wyświetlić różne konfiguracje i aplikacje zastosowane do urządzenia z rozwiązania  ->    ->  MDM. 

Aby zweryfikować instalację z usługi Intune, przejdź do strony Stan instalacji aplikacji w portalu [MEM](https://endpoint.microsoft.com/#home)> Wszystkie aplikacje  ->     -> *TheNameOfYourApp*  ->  **Device install status** (Aplikacje —wszystkie aplikacje)

Zobacz więcej: [Wdrażanie aplikacji usługi Intune dla urządzenia HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Weryfikowanie przewodników usługi Dynamics 365

Istnieją tryby tworzenia i działania aplikacji Przewodniki na urządzeniach HoloLens. Przed rozpoczęciem pracy z przewodnikiem należy zakończyć jego tworzenie.

### <a name="authoring-the-guide"></a>Tworzenie przewodnika

Nie musimy robić zbyt wiele na potrzeby tej szybkiej weryfikacji. Wystarczy wybrać przewodnik przygotowany na komputerze. Musisz zakotwiczyć [przewodnik ,](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor)aby szybko zweryfikować, możesz użyć kotwicy holograficznej. Następnie należy umieścić [kroki i modele](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation).

>[!NOTE]
> Do zalogowania **się na komputerze** i tworzenia na urządzeniach HoloLens potrzebna jest rola Tworzenie. Rola Operator jest tylko do odczytu i nie ma dostępu do aplikacji na komputerze.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>Obsługa przewodnika

Gdy hologramy będą już dostępne, możesz przetestować sposób działania przewodnika. 
- Wybieranie **trybu operatora**
- Kliknij kroki swojego przewodnika.

Aby uzyskać bardziej szczegółowe wskazówki dotyczące sposobu obsługi przewodnika, zapoznaj się z tymi zasobami:

[Omówienie obsługi przewodnika w przewodniku usługi Dynamics 365](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-overview)

[Uzyskaj orientację za pomocą karty Krok jako operator w przewodnikach usługi Dynamics 365](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>Następny krok 
> [!div class="nextstepaction"]
> [Wdrożenie połączone z firmą — obsługa](hololens2-corp-connected-maintain.md)
