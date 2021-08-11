---
title: Przewodnik wdrażania — wdrażanie w 2 HoloLens z chmurą na dużą skalę za pomocą usługi Remote Assist — wdrażanie
description: Dowiedz się, jak zweryfikować rejestrację i usługę Remote Assist HoloLens urządzeniach za pośrednictwem sieci połączonej z chmurą.
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
ms.openlocfilehash: 593dc65ab97eaae65591a5239cd0a978750eac9fa538364ba6bbc7ef0a2a08a4
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660504"
---
# <a name="deploy---cloud-connected-guide"></a>Wdrażanie — przewodnik po chmurze

Teraz, gdy wszystko jest skonfigurowane, powinno być gotowe do dystrybucji urządzeń. Teraz jednak należy najpierw zweryfikować konfigurację. Najpierw należy zweryfikować proces dołączania do usługi Azure AD i rejestracji w usłudze MDM, a następnie sprawdzić, czy można umieścić wywołanie funkcji Remote Assist.

## <a name="enrollment-validation"></a>Walidacja rejestracji

Teraz, gdy wszystko jest prawidłowo skonfigurowane dla usługi Azure AD i rejestracji w usłudze MDM, reszta powinna być teraz przystawką. Konieczne&#39;połączenie Wi-Fi urządzeniem HoloLens, a także jedno z wcześniej skonfigurowanych kont użytkowników usługi AAD.

Jeśli urządzenie nie&#39;obecnie w stanie ustawień fabrycznych, teraz będzie to dobry czas na [reflashowanie urządzenia.](/hololens/hololens-recovery#clean-reflash-the-device)

1. Gdy urządzenie jest w stanie OOBE,&#39;należy rozpocząć interakcję i zgodnie z monitami. 
1. Monit krytyczny będzie wyświetlany po wyświetleniu monitu, **KtoTo jest właścicielem tego HoloLens?** Wybierz **pozycję My work or school owns it and** enter your Azure AD account credentials (Moja praca lub szkoła jest jego właścicielem) i wprowadź poświadczenia konta usługi Azure AD.
1. Po pomyślnym zarejestrowaniu&#39;zostanie wyświetlony monit o skonfigurowanie numeru PIN. Ten numer PIN jest unikatowy dla tego urządzenia dla tego użytkownika. Zostanie również wyświetlony monit o skanowanie irysów, dane głosowe i ustawienia telemetrii,&#39;będzie można dowiedzieć się, jak otworzyć menu Start i ukończyć OOBE.
1. Po otwarciu strony Mixed Reality Home otwórz menu Start przy użyciu właśnie poznanych **gestów** Start.
1. Wybierz aplikację **Ustawienia** i wybierz pozycję **System.** Pierwszą informacją, którą&#39;, będzie nazwa urządzenia, a w przypadku urządzenia z systemem HoloLens 2 będzie hololens, po którym następuje ciąg sześciu &quot; &quot; znaków.
1. Zanotuj tę nazwę.

![HoloLens 2 Ustawienia — informacje](./images/hololens2-settings-about.jpg)

7. Możesz sprawdzić, czy urządzenie zostało pomyślnie zarejestrowane w usłudze Azure AD w Ustawienia aplikacji. Z **Ustawienia** pozycję **Konta Uzyskaj dostęp** do konta  ->  **służbowego.** Na tym ekranie możesz sprawdzić, czy użytkownik został pomyślnie zarejestrowany, zobacz &quot; Connected to _nameofAAD_&#39;s Azure AD (Połączono z&#39;usługą Azure AD). Połączono _za pomocą nazwy_ @ _użytkownikanazwa_użytkownikanazwaAD_.onmicrosoft.com &quot; .


Aby sprawdzić, czy urządzenie jest przyłączone do usługi Azure AD, możemy sprawdzić Azure Active Directory w witrynie [Azure Portal](https://portal.azure.com/#home)Azure Active Directory Urządzenia Wszystkie urządzenia i wyszukać  ->    ->    ->  nazwę urządzenia. Możesz&#39;, że urządzenie jest częścią Azure Active Directory.


![Azure Active Directory — urządzenie](./images/aad-enrollment.png)

Następnie musisz&#39;się do centrum [administracyjnego Microsoft Endpoint Manager usługi](https://endpoint.microsoft.com/#home). Zaloguj się i wybierz **pozycję Urządzenia, a** **następnie pozycję Wszystkie urządzenia.** W tym miejscu możesz przeszukać HoloLens,&#39;nazwę urządzenia. Powinny być one wyświetlane na liście HoloLens usłudze Intune.

![Intune — urządzenie](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Walidacja wywołań zdalnej pomocy

Po&#39;, że urządzenie jest zarejestrowane zarówno w usłudze AAD, jak i w usłudze MDM,&#39;czas na przetestowanie wywołania usługi Remote Assist. Na potrzeby tej weryfikacji&#39;musi mieć urządzenie HoloLens i komputer Windows 10, a także drugie konto użytkownika usługi Azure AD dla tego komputera.

W tym kroku walidacji przyjęto założenie, że ostatni krok weryfikacji został wcześniej ukończony, a urządzenie zostało zarejestrowane, a użytkownik usługi Azure AD znajduje się na urządzeniu.


1. Jeśli nie masz jeszcze zainstalowanego Microsoft Teams komputerze, możesz pobrać go [Teams tutaj.](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)
2. Zaloguj się Teams przy użyciu drugiego konta użytkownika usługi Azure AD niż konto aktualnie zalogowane do HoloLens. Po zalogowaniu się na komputerze możesz rozpocząć odbieranie połączenia.
3. Odblokuj swój HoloLens i zaloguj się.
4. Aby uruchomić aplikację Remote Assist, otwórz **menu Start i** wybierz pozycję Remote **Assist.** Usługa Remote Assist nie tylko jest dołączana jako aplikacja skrzynki odbiorczej, ale HoloLens 2&#39;menu Start. Jeśli nie widzisz&#39;przypiętą do menu Start, a następnie otwórz listę **Wszystkie aplikacje,** aby ją znaleźć.
5. Po uruchamianiu usługi Remote Assist powinna ona identyfikować użytkownika urządzenia za pośrednictwem logowania [jednokrotnego](/azure/active-directory/manage-apps/what-is-single-sign-on) i logować się do aplikacji.
6. W aplikacji wybierz pozycję **Wyszukaj** i wyszukaj drugiego użytkownika na komputerze. Wybierz użytkownika, aby rozpocząć połączenie.
7. Na komputerze odpowiedz na połączenie.

Gratulacje, udało&#39;pomyślnie nałączono połączenie i masz połączenie zdalnej pomocy. Pamiętaj, aby wypróbować określone funkcje zdalnej pomocy, takie jak użycie:

- [Adnotacje z cytami](/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Udostępnianie pliku i widoku w rzeczywistości mieszanej](/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Uzyskiwanie pomocy w innej HoloLens aplikacji](/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>Następny krok

> [!div class="nextstepaction"]
> [Wdrażanie połączone z chmurą — obsługa](hololens2-cloud-connected-maintain.md)