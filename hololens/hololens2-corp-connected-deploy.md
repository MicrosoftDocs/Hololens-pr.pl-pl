---
title: Przewodnik wdrażania — połączone z HoloLens 2 przewodniki usługi Dynamics 365 — wdrażanie
description: Dowiedz się, jak skonfigurować wdrożenia urządzeń z systemem HoloLens 2 za pośrednictwem firmowej sieci połączonej za pomocą przewodników usługi Dynamics 365.
keywords: HoloLens, zarządzanie, połączenia firmowe, przewodniki usługi Dynamics 365, AAD, Azure AD, MDM, Mobile Zarządzanie urządzeniami
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
ms.openlocfilehash: 7df2b00b2d87be7b9ad4a5d84c83251ec0ebec4d
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033493"
---
# <a name="deploy---corporate-connected-guide"></a>Wdrażanie — przewodnik po połączeniu firmowym

Ważnym elementem każdego wdrożenia jest upewnienie się, że wdrożenie jest prawidłowo skonfigurowane, zanim zostanie przetestowane samodzielnie, aby zapewnić bezproblemowe środowisko użytkownika końcowego.

Ponieważ wdrażamy certyfikat usługi Wi-Fi za pośrednictwem zarządzania urządzeniami przenośnymi, musimy początkowo skonfigurować usługę HoloLens i zarejestrować urządzenia w otwartej sieci Wi-Fi lub w sieci, która nie wymaga certyfikatu. Po HoloLens OOBE i rejestracji urządzenie otrzyma wcześniej skonfigurowany certyfikat sieciowy i usługę LOB i będziemy mogli sprawdzić, czy oba urządzenia zostały odebrane przez urządzenie.

Po zakończeniu będzie można potwierdzić, że można utworzyć i obsługiwać przewodnik testowy.

## <a name="enrollment-validation"></a>Walidacja rejestracji

Teraz, gdy wszystko jest prawidłowo skonfigurowane dla usługi Azure AD i rejestracji w usłudze MDM, reszta powinna być teraz przystawką. Musisz mieć połączenie Wi-Fi i urządzenie HoloLens oraz jedno z wcześniej skonfigurowanych kont użytkowników usługi Azure AD.

Jeśli urządzenie nie znajduje się obecnie w stanie ustawień fabrycznych, teraz byłby dobry czas, aby zmienić jego [ukośnik.](/hololens/hololens-recovery#clean-reflash-the-device)

1. Gdy urządzenie będzie w stanie OOBE, musisz rozpocząć interakcję i podążać za monitami.

2. Połączenie do otwartej Wi-Fi sieci, która nie wymaga certyfikatów do dołączenia do sieci Wi-Fi. Dzięki temu urządzenie będzie w stanie pobrać certyfikat, który będzie używany na stronie Wi-Fi po wstępnej konfiguracji.

3. Monit krytyczny pojawi się po wyświetleniu monitu, **KtoTo jest właścicielem tego HoloLens?** Wybierz **pozycję My work or school owns it and** enter your Azure AD account credentials (Moja praca lub szkoła jest jego właścicielem) i wprowadź poświadczenia konta usługi Azure AD.

4. Po pomyślnym zarejestrowaniu zostanie wyświetlony monit o skonfigurowanie numeru PIN. Ten numer PIN jest unikatowy dla tego urządzenia dla tego użytkownika. Zostanie również wyświetlony monit o przeskanowania irysów, dane głosowe i ustawienia telemetrii, a na koniec dowiesz się, jak otworzyć menu Start i ukończyć OOBE.

5. Po otwarciu strony Mixed Reality Home otwórz ekran menu Start użyciu właśnie poznanych **gestów** Start.

6. Wybierz aplikację **Ustawienia** i wybierz **pozycję System**. Pierwszą informacją, którą zobaczysz, jest nazwa urządzenia, która dla urządzenia z systemem HoloLens 2 będzie hololensem, po którym następuje sześć &quot; &quot; znaków.

7. Zanotuj tę nazwę.

    ![HoloLens ekranie Ustawienia 2.](./images/hololens2-settings-about.jpg)

8. Sprawdź, czy urządzenie zostało pomyślnie przyłączone do usługi Azure AD. Istnieją dwa sposoby:

    1.  Aplikacja Ustawienia. Z **Ustawienia** pozycję **Konta Uzyskaj dostęp** do konta  ->  **służbowego.** Na tym ekranie możesz sprawdzić, czy użytkownik został pomyślnie zarejestrowany, widzisz komunikat &quot; Connected to nameofAAD&#39;s Azure AD (Połączono z nazwą)AD&#39;usłudze Azure AD. Połączone przez *yourusername@nameofAAD.onmicrosoft.com* . Pozwoli to sprawdzić, czy urządzenie jest przyłączone do organizacji&#39;usługi Azure AD.

    1. W [Azure Portal](https://portal.azure.com/#home). Przejdź do **Azure Active Directory**  ->  **Urządzenia**  ->  **Wszystkie urządzenia** i wyszukaj nazwę urządzenia. W obszarze Typ sprzężenia będzie on pokazywany jako "Dołączenia do usługi Azure AD".
        ![Sprawdź typ dołączenia w usłudze Azure AD.](./images/hololens2-devices-all-devices.png)

9. Sprawdź, czy urządzenie zostało zarejestrowane w usłudze MDM. Istnieją dwa sposoby:

    1. W **Ustawienia** pozycję Konta **Uzyskaj dostęp** do konta  ->  **służbowego.** Na tym ekranie możesz sprawdzić, czy użytkownik został pomyślnie zarejestrowany, widzisz komunikat &quot; Connected to nameofAAD&#39;s Azure AD (Połączono z nazwą)AD&#39;usłudze Azure AD. Połączone przez *yourusername@nameofAAD.onmicrosoft.com* . Z tego konta uzyskaj dostęp do konta służbowego, wybierając pozycję Połączono &quot; z nazwąAD&#39;usługi Azure AD. Połączono yourusername@nameofAAD.onmicrosoft.com &quot; się i wybierz **przycisk** Informacje.

    1. [Microsoft Endpoint Manager administracyjnego programu](https://endpoint.microsoft.com/#home). Zaloguj się i wybierz **pozycję Urządzenia, a** **następnie pozycję Wszystkie urządzenia.** W tym miejscu możesz wyszukać nazwę HoloLens,&#39;nazwę urządzenia. W usłudze Intune powinna być HoloLens twoja usługa.

        ![Weryfikowanie zarządzania przez usługę Intune w usłudze Azure AD.](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi weryfikacji certyfikatu

Do tej pory urządzenie powinno otrzymało certyfikat Wi-Fi aplikacji. Najprostszą weryfikacją, jaką można wykonać, jest próba nawiązania połączenia Wi-Fi, dla którego&#39;został otrzymany certyfikat. Otwórz aplikację **internetową Ustawienia** przejdź do sieci **&amp; Internet**  ->  **Wi-Fi** i wybierz połączenie Wi-Fi. Po na połączeniu otwórz aplikację Microsoft Edge i upewnij się, że możesz przejść do witryny internetowej.

Aby potwierdzić, że certyfikat został otrzymany na urządzeniu, możesz użyć [Menedżera certyfikatów](/hololens/certificate-manager).

## <a name="validate-lob-app-install"></a>Weryfikowanie instalacji aplikacji LOB

Aby wyświetlić postęp instalacji aplikacji zarządzanej, możesz sprawdzić, czy aplikacja została zainstalowana, lub sprawdzić jej Ustawienia. Po skonfigurowaniu aplikacji LOB jako instalacji wymaganej dla naszej grupy po zarejestrowaniu aplikacji HoloLens z użytkownikiem w przypisanej grupie aplikacja zostanie automatycznie pobrana do HoloLens.

Otwórz menu Start i wybierz pozycję **Wszystkie aplikacje**. W zależności od liczby posiadanych aplikacji może być konieczne użycie przycisków strony **w** górę **lub w dół** strony.

Aby zweryfikować instalację aplikacji na urządzeniu, możesz to zrobić za pośrednictwem konta usługi Ustawienia Uzyskaj dostęp do konta służbowego, wybierz **konto, a** następnie przycisk Informacje i przewiń w dół, aby wyświetlić różne konfiguracje i aplikacje zastosowane do urządzenia z rozwiązania  ->    ->    MDM.

Aby zweryfikować instalację z usługi Intune, przejdź do strony Stan instalacji aplikacji w portalu [MEM](https://endpoint.microsoft.com/#home)> Wszystkie aplikacje  ->     -> *TheNameOfYourApp* Device install status ( Wszystkie  ->   aplikacje).

Zobacz więcej: [Wdrażanie aplikacji usługi Intune dla HoloLens](/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Weryfikowanie przewodników usługi Dynamics 365

Istnieją tryby aplikacji Przewodniki dotyczące HoloLens, tworzenia i obsługi. Przed rozpoczęciem pracy z przewodnikiem należy zakończyć jego tworzenie.

### <a name="authoring-the-guide"></a>Tworzenie przewodnika

Nie musimy robić zbyt wiele na potrzeby tej szybkiej weryfikacji. Wystarczy wybrać przewodnik przygotowany na komputerze. Musisz zakotwiczyć [przewodnik ,](/dynamics365/mixed-reality/guides/hololens-app-anchor)aby szybko zweryfikować, możesz użyć kotwicy holograficznej. Następnie należy umieścić [kroki i modele](/dynamics365/mixed-reality/guides/hololens-app-orientation).

>[!NOTE]
> Do zalogowania **się na** komputerze i tworzenia na komputerze będzie potrzebna rola Tworzenie na HoloLens. Rola Operator jest tylko do odczytu i nie ma dostępu do aplikacji na komputerze.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>Obsługa przewodnika

Gdy hologramy będą już dostępne, możesz przetestować sposób działania przewodnika. 
- Wybieranie **trybu operatora**
- Kliknij kroki swojego przewodnika.

Aby uzyskać bardziej szczegółowe wskazówki dotyczące sposobu obsługi przewodnika, zapoznaj się z tymi zasobami:

[Omówienie obsługi przewodnika w przewodniku usługi Dynamics 365](/dynamics365/mixed-reality/guides/operator-overview)

[Uzyskaj orientację za pomocą karty Krok jako operator w przewodnikach usługi Dynamics 365](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>Następny krok 
> [!div class="nextstepaction"]
> [Wdrożenie połączone z firmą — obsługa](hololens2-corp-connected-maintain.md)
