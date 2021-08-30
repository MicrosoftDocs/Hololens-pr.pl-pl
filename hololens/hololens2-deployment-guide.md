---
title: Wdrażanie połączonych z chmurą HoloLens 2 na klientach zewnętrznych
description: Przewodnik wdrażania dla HoloLens 2 dla klientów zewnętrznych (na przykład z pomocą zdalną)
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/6/2021
ms.custom: ''
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: d5cd9c380e0d276f0a8aa9efac14cf44885446e5
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190331"
---
# <a name="deploy-cloud-connected-hololens-2-to-external-clients"></a>Wdrażanie połączonych z chmurą HoloLens 2 na klientach zewnętrznych

Ten przewodnik stanowi uzupełnienie przewodnika wdrażania [połączonego z chmurą.](hololens2-cloud-connected-overview.md) Jest on używany w sytuacjach, w których organizacja chce wysyłać HoloLens 2 urządzenia do obiektu klienta zewnętrznego w celu krótko- lub długoterminowego użycia. Klient zewnętrzny zaloguje się do urządzenia HoloLens 2 przy użyciu poświadczeń dostarczonych przez organizację i użyje usługi [Remote Assist,](/dynamics365/mixed-reality/remote-assist/ra-overview) aby skontaktować się z ekspertami. Ten przewodnik zawiera ogólne [HoloLens 2](#general-deployment-recommendations) zalecenia dotyczące wdrażania, które mają zastosowanie [](#common-external-client-deployment-concerns) do większości scenariuszy wdrażania programu HoloLens 2 zewnętrznych i typowe problemy, które klienci mają podczas wdrażania usługi Remote Assist do użytku zewnętrznego. 

## <a name="prerequisites"></a>Wymagania wstępne

W przewodniku wdrażania połączonym z chmurą należy wdrożyć następującą infrastrukturę, aby wdrożyć HoloLens 2 zewnętrznie. [](hololens2-cloud-connected-overview.md)

- Dołączanie do usługi Azure AD z automatyczną rejestracją w usłudze MDM — zarządzane przez rozwiązanie MDM (Intune)
- Użytkownicy logują się przy użyciu własnego konta firmowego (Azure AD)
    - Obsługiwanych jest jeden lub wielu użytkowników na urządzenie.

### <a name="remote-assist-licensing-and-requirements"></a>Licencjonowanie i wymagania dotyczące usługi Remote Assist

- Konto usługi Azure AD (wymagane do zakupu subskrypcji i przypisywania licencji)
- [Subskrypcja usługi Remote Assist](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (lub wersja [próbna usługi Remote Assist)](/dynamics365/mixed-reality/remote-assist/try-remote-assist)

Zobacz [Więcej informacji na temat usługi Remote Assist.](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)

### <a name="dynamics-365-remote-assist-user"></a>Użytkownik usługi Dynamics 365 Remote Assist

- Licencja usługi Remote Assist
- Łączność sieciowa

### <a name="microsoft-teams-user"></a>Microsoft Teams użytkownika

- Microsoft Teams lub [Teams Freemium](https://products.office.com/microsoft-teams/free)
- Łączność sieciowa

## <a name="general-deployment-recommendations"></a>Ogólne zalecenia dotyczące wdrażania

Zalecamy następujące kroki w przypadku wdrożenia HoloLens 2:

1. Użyj [najnowszej HoloLens systemu operacyjnego jako](https://aka.ms/hololens2download) kompilacji linii bazowej.
1. Przypisz licencje oparte na użytkownikach lub urządzeniach, korzystając z poniższych instrukcji:
    1. [Utwórz grupę W UAD i dodaj członków](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) dla HoloLens/RA.
    1. [Przypisz do tej](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) grupy licencje oparte na urządzeniach lub użytkownikach.
    1. (Opcjonalnie) Grupy docelowe zasad [zarządzania urządzeniami przenośnymi (MDM).](hololens-enroll-mdm.md)

1. Dołączanie urządzeń usługi AAD do dzierżawy, [automatyczne rejestrowanie](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)i konfigurowanie za pomocą rozwiązania [Autopilot.](/hololens/hololens2-autopilot) Aby uzyskać więcej informacji, zobacz [właściciel urządzenia](/hololens/security-adminless-os#device-owner).
    1. Pierwszy użytkownik na urządzeniu będzie właścicielem urządzenia.
    1. Jeśli urządzenie jest przyłączone do aplikacji AAD, użytkownik, który wykonał dołączenie, jest właścicielem urządzenia.
    
1. [Zablokowanie](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) urządzenia przez dzierżawę, aby można było do niego dołączyć tylko dzierżawca.
    1. Zobacz też [tenant lock CSP (CSP ) (Blok dzierżawy CSP).](/windows/client-management/mdm/tenantlockdown-csp)

1. [Skonfiguruj tryb kiosku przy użyciu dostępu przypisanego globalnie.](/hololens/hololens-global-assigned-access-kiosk)

1. Wyłącz następujące (opcjonalne) możliwości:
    1. Możliwość ustawienia urządzenia w tryb dewelopera w [tym miejscu.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. Możliwość podłączenia urządzenia HoloLens z komputerem w celu skopiowania daty [wyłącz port USB.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > Jeśli nie chcesz wyłączać portu USB, ale chcesz mieć możliwość zastosowania pakietu aprowizowania do urządzenia przy użyciu portu USB, postępuj zgodnie z instrukcjami dotyczącymi sposobu zezwalania na instalację [pakietu aprowizowania.](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. Użyj [Windows Defender Application Control (WDAC),](/hololens/windows-defender-application-control-wdac) aby zezwalać na aplikacje lub blokować je na urządzeniu HoloLens 2.
1. Zaktualizuj usługę Remote Assist do najnowszej wersji w ramach instalacji. Rozważ następujące dwie opcje:
    1. Przejdź do Windows **Microsoft Store --> Remote Assist --> i Zaktualizuj aplikację.**
    1. [ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) — co umożliwia automatyczne aktualizacje aplikacji — jest domyślnie włączone. Urządzenie musi być podłączone do zasilania, aby otrzymywać aktualizacje.
1. [Wyłącz wszystkie strony ustawień z](/hololens/settings-uri-list) wyjątkiem ustawień sieciowych, aby umożliwić użytkownikom łączenie się z sieciami gości w lokacjach klienckich.
1. [Zarządzanie HoloLens aktualizacjami](/hololens/hololens-updates)
    1. Opcja [kontrolowania aktualizacji systemu operacyjnego](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) lub zezwalania na swobodne przepływy.
1. Ustaw [typowe ograniczenia dotyczące urządzeń.](/hololens/hololens-common-device-restrictions)

Teraz klienci zewnętrzni są gotowi do korzystania z HoloLens 2.

## <a name="common-external-client-deployment-concerns"></a>Typowe problemy z wdrażaniem klientów zewnętrznych

- [Zapewnienie, że klienci nie mogą komunikować się ze sobą](#ensure-that-external-clients-cant-communicate-with-one-another)
- [Zapewnianie, że klienci nie mogą uzyskać dostępu do zasobów firmy](#ensure-that-clients-wont-have-access-to-company-resources)
- [Ukrywanie lub ograniczanie aplikacji](#hidden-or-restricted-apps)
- [Zarządzanie hasłami klientów](#password-management-for-your-clients) 
- [Zapewnianie, że klienci nie mogą uzyskać dostępu do historii czatu](#ensure-that-clients-wont-have-access-to-chat-history)

### <a name="ensure-that-external-clients-cant-communicate-with-one-another"></a>Upewnij się, że klienci zewnętrzni nie mogą komunikować się ze sobą

Zdalne HoloLens do HoloLens nie są obsługiwane. Klienci mogą wyszukiwać, ale nie mogą komunikować się ze sobą. [Bariery informacyjne w Microsoft 365](/microsoft-365/compliance/information-barriers) mogą dodatkowo ograniczać możliwości wyszukiwania i wywołania klienta. Inną opcją jest użycie [Microsoft Teams wyszukiwania w katalogu o zakresie .](/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Ponieważ logowanie pojedyncze jest włączone, ważne jest, aby wyłączyć przeglądarkę przy użyciu Windows Defender [Application Control (WDAC).](/hololens/windows-defender-application-control-wdac) Jeśli klient zewnętrzny otworzy przeglądarkę i użyje wersji internetowej usługi Teams, klient będzie miał dostęp do historii czatu.

### <a name="ensure-that-clients-wont-have-access-to-company-resources"></a>Upewnij się, że klienci nie będą mieć dostępu do zasobów firmy

Istnieją dwie opcje, które należy wziąć pod uwagę.

Pierwszą opcją jest podejście wielowarstwowe:

1. Przypisz tylko licencje wymagane przez użytkownika. Jeśli nie przypiszesz kont OneDrive, Outlook, SharePoint, Yammer itp., użytkownik nie będzie miał dostępu do tych zasobów. Jedyną licencją, która będzie potrzebna użytkownikom, są licencje usługi Remote Assist, Intune i AAD, aby rozpocząć.
1. Blokuj aplikacje (takie jak poczta e-mail), do których klienci nie mają mieć dostępu (zobacz Aplikacje [są ukryte lub ograniczone).](#apps are hidden or restricted)
1. Nie udostępniaj klientom nazw użytkowników ani haseł. Aby zalogować się do HoloLens 2, wymagana jest wiadomość e-mail i numeryczny numer PIN.

Drugą opcją jest utworzenie oddzielnej dzierżawy hostowania klientów (zobacz obraz 1.1).

**Obraz 1.1**

![Obraz dzierżawy usługi.](./images/hololens-service-tenant-image.png)

### <a name="hidden-or-restricted-apps"></a>Aplikacje ukryte lub z ograniczeniami

[Tryb kiosku](/hololens/hololens-kiosk) [i/lub Windows Defender Application Control (WDAC)](/hololens/windows-efender-application-control-wdac) to opcje ukrywania i/lub ograniczania aplikacji.

### <a name="password-management-for-your-clients"></a>Zarządzanie hasłami dla klientów

1. Usuń wygaśnięcie hasła. Jednak ta opcja może zwiększyć prawdopodobieństwo naruszenia zabezpieczeń konta. Zalecenie dotyczące haseł NIST to zmienianie haseł co 30–90 dni.
1. Przedłużenie okresu ważności hasła dla HoloLens 2 urządzeń do ponad 90 dni.
1. Urządzenia powinny zostać zwrócone do organizacji w celu zmiany haseł. Jednak ta opcja może powodować problemy, jeśli urządzenia powinny być w zakładzie klienta przez ponad 90 dni.  
1. W przypadku urządzeń wysyłanych do wielu klientów zresetuj hasła przed wysyłką urządzenia do klientów.

### <a name="ensure-that-clients-wont-have-access-to-chat-history"></a>Upewnij się, że klienci nie będą mieć dostępu do historii czatu

Funkcja Remote Assist wyczyści historię czatu po każdej sesji. Jednak historia czatu będzie dostępna dla Microsoft Teams użytkowników.

> [!NOTE]
> Ponieważ logowanie pojedyncze jest włączone, ważne jest, aby wyłączyć przeglądarkę przy użyciu Windows Defender [Application Control (WDAC).](/hololens/windows-defender-application-control-wdac)  Jeśli klient zewnętrzny otworzy przeglądarkę i użyje wersji internetowej usługi Teams, klient będzie miał dostęp do historii połączeń/czatów.
