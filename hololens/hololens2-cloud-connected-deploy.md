---
title: Przewodnik wdrażania — wdrażanie urządzenia HoloLens 2 połączonego z chmurą na dużą skalę przy użyciu usługi Remote Assist — wdrażanie
description: Dowiedz się, jak zweryfikować rejestrację i usługę Remote Assist dla urządzeń HoloLens za pośrednictwem sieci połączonej z chmurą.
keywords: HoloLens, zarządzanie, połączone z chmurą, Remote Assist, AAD, Azure AD, MDM, Mobile Zarządzanie urządzeniami
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 4183bde30673f5147683e16b4d625f73b063c529
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378407"
---
# <a name="deploy---cloud-connected-guide"></a>Wdrażanie — przewodnik po chmurze

Teraz, po skonfigurowaniu wszystkich ustawień, wszystko powinno być gotowe do dystrybucji urządzeń. Teraz jednak należy najpierw zweryfikować konfigurację. Najpierw należy zweryfikować proces dołączania do usługi Azure AD i rejestracji w usłudze MDM, a następnie sprawdzić, czy można umieścić wywołanie funkcji Remote Assist.

## <a name="enrollment-validation"></a>Walidacja rejestracji

Teraz, gdy wszystko jest prawidłowo skonfigurowane dla usługi Azure AD i rejestracji w usłudze MDM, reszta powinna być teraz przystawką. Konieczne&#39;będzie połączenie Wi-Fi i urządzenie HoloLens, a także jedno z wcześniej skonfigurowanych kont użytkowników usługi AAD.

Jeśli urządzenie nie&#39;obecnie w stanie ustawień fabrycznych, byłby to dobry czas na [reflashowanie urządzenia.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)

1. Gdy urządzenie będzie w stanie OOBE,&#39;będzie konieczne rozpoczęcie interakcji i korzystanie z monitów. 
1. Monit krytyczny pojawi się po wyświetleniu monitu **Kto jest właścicielem tego urządzenia HoloLens?** Wybierz **pozycję My work or school owns it and** enter your Azure AD account credentials (Moja praca lub szkoła jest jego właścicielem) i wprowadź poświadczenia konta usługi Azure AD.
1. Po pomyślnym zarejestrowaniu&#39;zostanie wyświetlony monit o skonfigurowanie numeru PIN. Ten numer PIN jest unikatowy dla tego urządzenia dla tego użytkownika. Zostanie również wyświetlony monit o przeskanowania irysów, dane głosowe i ustawienia telemetrii. Na koniec dowiesz się&#39;jak otworzyć menu Start i ukończyć OOBE.
1. Po otwarciu strony Mixed Reality Home otwórz menu Start przy użyciu właśnie poznanych **gestów** Start.
1. Wybierz aplikację **Ustawienia** i wybierz pozycję **System.** Pierwszymi informacjami, które&#39;, jest nazwa urządzenia, które dla urządzenia HoloLens 2 będzie hololensem, a po nim sześć &quot; &quot; znaków.
1. Zanotuj tę nazwę.

![Ustawienia urządzenia HoloLens 2 — informacje](./images/hololens2-settings-about.jpg)

7. Możesz sprawdzić, czy urządzenie zostało pomyślnie zarejestrowane w usłudze Azure AD w aplikacji Ustawienia. W **menu Ustawienia** wybierz pozycję Konta **Uzyskaj** dostęp do konta  ->  **służbowego.** Na tym ekranie możesz sprawdzić, czy użytkownik został pomyślnie zarejestrowany, widząc komunikat Połączono z &quot; _nazwąAD_&#39;usługi Azure AD. Połączono _za pomocą_ @ _nazwy_użytkownikaofAAD_.onmicrosoft.com &quot; .


Aby sprawdzić, czy urządzenie jest przyłączone do usługi Azure AD, możemy sprawdzić Azure Active Directory w witrynie [Azure Portal](https://portal.azure.com/#home)Azure Active Directory Wszystkie urządzenia i wyszukać  ->    ->    ->  nazwę urządzenia. Możesz&#39;, że urządzenie jest częścią Azure Active Directory.


![Azure Active Directory — urządzenie](./images/aad-enrollment.png)

Następnie musisz&#39;w centrum administracyjnym usługi [Microsoft Endpoint Manager.](https://endpoint.microsoft.com/#home) Zaloguj się i wybierz **pozycję Urządzenia, a** **następnie pozycję Wszystkie urządzenia.** W tym miejscu możesz wyszukać nazwę&#39;HoloLens. Urządzenie HoloLens powinno być wyświetlane na liście w usłudze Intune.

![Intune — urządzenie](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Walidacja wywołań usługi Remote Assist

Po&#39;, że urządzenie jest zarejestrowane zarówno w usłudze AAD, jak i w usłudze MDM,&#39;czas na przetestowanie wywołania usługi Remote Assist. Na potrzeby tej weryfikacji&#39;urządzenie HoloLens i komputer Windows 10, a także drugie konto użytkownika usługi Azure AD dla komputera.

W tym kroku walidacji przyjęto założenie, że ostatni krok weryfikacji został ukończony, a urządzenie zostało zarejestrowane, a użytkownik usługi Azure AD jest na urządzeniu.


1. Jeśli na komputerze nie masz jeszcze zainstalowanej aplikacji Microsoft Teams, możesz [pobrać aplikację Teams tutaj.](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)
2. Zaloguj się do aplikacji Teams przy użyciu drugiego konta użytkownika usługi Azure AD niż konto aktualnie zalogowane na urządzenie HoloLens. Po zalogowaniu się na komputerze możesz rozpocząć odbieranie połączenia.
3. Odblokuj urządzenie HoloLens i zaloguj się.
4. Aby uruchomić aplikację Remote Assist, otwórz **menu Start i** wybierz pozycję Remote **Assist.** Usługa Remote Assist nie tylko jest pakowana jako aplikacja skrzynki odbiorczej, ale przypięta do urządzenia HoloLens 2&#39;menu Start. Jeśli nie widzisz&#39;przypiętą do menu Start, a następnie  otwórz listę Wszystkie aplikacje, aby ją znaleźć.
5. Po zalogowaniu się usługa Remote Assist powinna zidentyfikować użytkownika urządzenia za pośrednictwem logowania jednokrotnego [i](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) zalogować się do aplikacji.
6. W aplikacji wybierz pozycję **Wyszukaj** i wyszukaj drugiego użytkownika na komputerze. Wybierz użytkownika, aby rozpocząć wywołanie.
7. Na komputerze odpowiedz na połączenie.

Gratulacje, udało&#39;pomyślnie nałączono połączenie i masz połączenie zdalnej pomocy. Pamiętaj, aby wypróbować określone funkcje zdalnej pomocy, takie jak korzystanie z:

- [Adnotacje z cytami](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Udostępnianie pliku i widoku w rzeczywistości mieszanej](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Uzyskiwanie pomocy w innej aplikacji dla urządzenia HoloLens](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>Następny krok

> [!div class="nextstepaction"]
> [Wdrożenie połączone z chmurą — obsługa](hololens2-cloud-connected-maintain.md)