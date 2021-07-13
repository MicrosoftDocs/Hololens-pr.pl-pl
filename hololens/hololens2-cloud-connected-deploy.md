---
title: Przewodnik wdrażania — wdrożenie w 2 HoloLens połączone z chmurą na dużą skalę za pomocą usługi Remote Assist — wdrażanie
description: Dowiedz się, jak zweryfikować rejestrację i usługę Remote Assist HoloLens urządzeń za pośrednictwem sieci połączonej z chmurą.
keywords: HoloLens, zarządzanie, połączone z chmurą, remote assist, AAD, Azure AD, MDM, Mobile Zarządzanie urządzeniami
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
ms.openlocfilehash: b0597806d58d7bf16fe6f6c766af3f9662fca7e6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635181"
---
# <a name="deploy---cloud-connected-guide"></a>Wdrażanie — przewodnik po chmurze

Teraz, po skonfigurowaniu wszystkich ustawień, wszystko powinno być gotowe do dystrybucji urządzeń. Teraz jednak należy najpierw zweryfikować konfigurację. Najpierw należy zweryfikować proces dołączania do usługi Azure AD i rejestracji w usłudze MDM, a następnie sprawdzić, czy można umieścić wywołanie funkcji Remote Assist.

## <a name="enrollment-validation"></a>Walidacja rejestracji

Teraz, gdy wszystko jest prawidłowo skonfigurowane dla usługi Azure AD i rejestracji w usłudze MDM, reszta powinna być teraz przystawką. Konieczne&#39;połączenie Wi-Fi i urządzenie HoloLens, a także jedno z wcześniej skonfigurowanych kont użytkowników usługi AAD.

Jeśli urządzenie nie&#39;obecnie w stanie ustawień fabrycznych, byłby to dobry czas na [reflashowanie urządzenia.](/hololens/hololens-recovery#clean-reflash-the-device)

1. Gdy urządzenie będzie w stanie OOBE,&#39;będzie konieczne rozpoczęcie interakcji i korzystanie z monitów. 
1. Monit krytyczny będzie wyświetlany po wyświetleniu monitu, **KtoTo jest właścicielem tego HoloLens?** Wybierz **pozycję My work or school owns it and** enter your Azure AD account credentials (Moja praca lub szkoła jest jego właścicielem) i wprowadź poświadczenia konta usługi Azure AD.
1. Po pomyślnym zarejestrowaniu&#39;zostanie wyświetlony monit o skonfigurowanie numeru PIN. Ten numer PIN jest unikatowy dla tego urządzenia dla tego użytkownika. Zostanie również wyświetlony monit o przeskanowania irysów, dane głosowe i ustawienia telemetrii. Na koniec dowiesz się&#39;jak otworzyć menu Start i ukończyć OOBE.
1. Po otwarciu strony Mixed Reality Home otwórz menu Start przy użyciu właśnie poznanych **gestów** Start.
1. Wybierz aplikację **Ustawienia** i wybierz pozycję **System.** Pierwszą informacją, którą&#39;, jest nazwa urządzenia, która dla urządzenia HoloLens 2 będzie hololensem, a po nim sześć &quot; &quot; znaków.
1. Zanotuj tę nazwę.

![HoloLens 2 Ustawienia — informacje](./images/hololens2-settings-about.jpg)

7. Możesz sprawdzić, czy urządzenie zostało pomyślnie zarejestrowane w usłudze Azure AD w Ustawienia aplikacji. W **Ustawienia** pozycję **Konta Uzyskaj dostęp** do konta  ->  **służbowego.** Na tym ekranie możesz sprawdzić, czy użytkownik został pomyślnie zarejestrowany, widząc komunikat Połączono z &quot; _nazwąAD_&#39;usługi Azure AD. Połączono _za pomocą_ @ _nazwy_użytkownikaofAAD_.onmicrosoft.com &quot; .


Aby sprawdzić, czy urządzenie jest przyłączone do usługi Azure AD, możemy sprawdzić Azure Active Directory w witrynie [Azure Portal](https://portal.azure.com/#home)Azure Active Directory Wszystkie urządzenia i wyszukać  ->    ->    ->  nazwę urządzenia. Możesz&#39;, że urządzenie jest częścią Azure Active Directory.


![Azure Active Directory — urządzenie](./images/aad-enrollment.png)

Następnie&#39;zalogować się do centrum [Microsoft Endpoint Manager administracyjnego.](https://endpoint.microsoft.com/#home) Zaloguj się i wybierz **pozycję Urządzenia, a** **następnie pozycję Wszystkie urządzenia.** W tym miejscu możesz wyszukać HoloLens nazwę&#39;użytkownika. Powinny być one wyświetlane na liście HoloLens usłudze Intune.

![Intune — urządzenie](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Walidacja wywołań usługi Remote Assist

Po&#39;, że urządzenie jest zarejestrowane zarówno w usłudze AAD, jak i w usłudze MDM,&#39;czas na przetestowanie wywołania usługi Remote Assist. W celu weryfikacji&#39;musisz mieć urządzenie HoloLens i komputer Windows 10, a także drugie konto użytkownika usługi Azure AD dla tego komputera.

W tym kroku walidacji przyjęto założenie, że ostatni krok weryfikacji został ukończony, a urządzenie zostało zarejestrowane, a użytkownik usługi Azure AD jest na urządzeniu.


1. Jeśli nie masz jeszcze zainstalowanego Microsoft Teams komputerze, możesz pobrać aplikację [Teams tutaj.](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)
2. Zaloguj się Teams przy użyciu drugiego konta użytkownika usługi Azure AD niż konto aktualnie HoloLens. Po zalogowaniu się na komputerze możesz rozpocząć odbieranie połączenia.
3. Odblokuj swój HoloLens i zaloguj się.
4. Aby uruchomić aplikację Remote Assist, otwórz **menu Start i** wybierz pozycję Remote **Assist.** Usługa Remote Assist nie tylko jest pakowana jako aplikacja skrzynki odbiorczej, ale przypięta do HoloLens 2&#39;menu Start. Jeśli nie widzisz&#39;przypiętą do menu Start, a następnie  otwórz listę Wszystkie aplikacje, aby ją znaleźć.
5. Po zalogowaniu się usługa Remote Assist powinna zidentyfikować użytkownika urządzenia za pośrednictwem logowania jednokrotnego [i](/azure/active-directory/manage-apps/what-is-single-sign-on) zalogować się do aplikacji.
6. W aplikacji wybierz pozycję **Wyszukaj** i wyszukaj drugiego użytkownika na komputerze. Wybierz użytkownika, aby rozpocząć wywołanie.
7. Na komputerze odpowiedz na połączenie.

Gratulacje, udało&#39;pomyślnie nałączono połączenie i masz połączenie zdalnej pomocy. Pamiętaj, aby wypróbować określone funkcje zdalnej pomocy, takie jak korzystanie z:

- [Adnotacje z cytami](/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Udostępnianie pliku i widoku w rzeczywistości mieszanej](/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Uzyskiwanie pomocy w innej HoloLens aplikacji](/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>Następny krok

> [!div class="nextstepaction"]
> [Wdrożenie połączone z chmurą — obsługa](hololens2-cloud-connected-maintain.md)