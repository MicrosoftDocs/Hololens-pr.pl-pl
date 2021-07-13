---
title: Przewodnik wdrażania klientów zewnętrznych
description: Przewodnik wdrażania programu HoloLens 2 dla klientów zewnętrznych (na przykład z asystą zdalną)
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: medium
ms.date: 1/12/2021
ms.custom: ''
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: acf4b5d730b9a7eee2dedfad2bb3f866931d7455
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636949"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>Wdrażanie HoloLens 2 na klientach zewnętrznych przy użyciu funkcji Remote Assist

Ten przewodnik pomaga specjalistom IT w następujących celach wdrażania Microsoft HoloLens 2 urządzeń w organizacji:

1. Łączenie z chmurą HoloLens 2 urządzenia
1. Pożyczek HoloLens 2 do klientów zewnętrznych do użycia
1. Zabezpieczanie urządzeń pożyczek

Ten przewodnik zawiera ogólne zalecenia HoloLens [2](#general-deployment-recommendations-and-instructions) dotyczące wdrażania, które mają zastosowanie [](#common-concerns) do większości scenariuszy wdrażania programu HoloLens 2, i typowe problemy, które klienci mają podczas wdrażania usługi Remote Assist do użytku zewnętrznego.

## <a name="scenario-description"></a>Opis scenariusza

Na potrzeby tego dokumentu firma Contoso chce wysłać urządzenie HoloLens 2 do fabryki klienta zewnętrznego do użytku krótkoterminowego lub długoterminowego. Gdy klient potrzebuje pomocy w zakresie obsługi maszyn, zaloguje się do urządzenia z systemem HoloLens 2 przy użyciu poświadczeń dostarczonych przez firmę Contoso i użyje usługi Remote Assist, aby skontaktować się z ekspertami firmy Contoso.

Dowiedz się więcej na temat usługi Remote Assist [tutaj.](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)

### <a name="requirements-for-this-scenario"></a>Wymagania dotyczące tego scenariusza

1. [Azure AD](/azure/active-directory/fundamentals/active-directory-whatis)
1. Aplikacje Menedżer urządzeń — takie jak usługa [Intune](/mem/intune/fundamentals/free-trial-sign-up)
1. Licencja usługi Remote Assist
    1. [Kup usługę Remote Assist](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [Pomoc zdalna w wersji próbnej](/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>Typowe problemy

- [Jak zapewnić, że klienci zewnętrzni nie będą mieć możliwości komunikowania się ze sobą](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [Jak upewnić się, że klienci nie mają dostępu do zasobów firmy](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [Jak ograniczyć aplikacje](#how-to-restrict-apps)
- [Jak zarządzać hasłami](#how-to-manage-passwords)
- [Jak upewnić się, że klienci nie mają dostępu do historii czatu](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>Jak zapewnić, że klienci zewnętrzni nie będą mieć możliwości komunikowania się ze sobą

Ponieważ zdalne HoloLens do HoloLens nie są obsługiwane, klienci mogą wyszukiwać, ale nie mogą komunikować się ze sobą. Aby jeszcze bardziej ograniczyć liczbę klientów, którzy mogą wyszukiwać i wywołać  [usługę](/microsoft-365/compliance/information-barriers) , bariery informacyjne mogą ograniczać to, z kim klient może się komunikować. Inną opcją, która należy wziąć pod uwagę, jest użycie wyszukiwania [w katalogu o zakresie](/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Ponieważ logowanie pojedyncze jest włączone, ważne jest, aby wyłączyć przeglądarkę przy użyciu funkcji [**WDAC.**](/hololens/windows-defender-application-control-wdac) Jeśli klient zewnętrzny otworzy przeglądarkę i użyje wersji internetowej usługi Teams, klient będzie miał dostęp do historii połączeń/czatów.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>Jak upewnić się, że klienci nie mają dostępu do zasobów firmy

Istnieją dwie opcje, które należy wziąć pod uwagę.

Pierwszą opcją jest podejście wielowarstwowe:

1. Przypisz tylko licencje wymagane przez użytkownika. Jeśli użytkownik nie przypisze OneDrive, Outlook, SharePoint, Yammer itp., nie będzie miał dostępu do tych zasobów. Jedynymi licencjami, których potrzebują użytkownicy, są licencje usługi Remote Assist, Intune i AAD, aby rozpocząć.
1. Blokowanie aplikacji (takich jak poczta e-mail), do których klienci nie mają mieć dostępu (zobacz [Jak ograniczać aplikacje).](#how-to-restrict-apps)
1. NIE należy udostępniać nazw użytkowników ani haseł klientom. Aby zalogować się do HoloLens 2, wymagany jest adres e-mail i liczbowy numer PIN.

Drugą opcją jest utworzenie oddzielnej dzierżawy hostowania klientów (zobacz obraz 1.1).

**Obraz 1.1**

![Obraz dzierżawy usługi](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>Jak ograniczyć aplikacje

[Tryb kiosku](/hololens/hololens-kiosk) i/lub [WDAC (Windows Defender Application Control)](/hololens/windows-defender-application-control-wdac) to opcje ograniczania aplikacji.

### <a name="how-to-manage-passwords"></a>Jak zarządzać hasłami

1. Usuń wygaśnięcie hasła. Zwiększa to jednak prawdopodobieństwo naruszenia zabezpieczeń konta. Zalecenie dotyczące haseł NIST to zmienianie haseł co 30–90 dni.
1. Przedłużenie okresu ważności hasła dla HoloLens 2 urządzeń do ponad 90 dni.
1. Urządzenia powinny zostać zwrócone do firmy Contoso w celu zmiany haseł. Może to jednak powodować problemy, jeśli urządzenia powinny być w zakładzie klienta przez ponad 90 dni.  
1. W przypadku urządzeń wysyłanych do wielu klientów zresetuj hasła przed wysyłką urządzenia do klientów.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>Jak upewnić się, że klienci nie mają dostępu do historii czatu

Usługa Remote Assist wyczyści historię czatu po każdej sesji. Jednak historia czatu będzie dostępna dla użytkownika Microsoft Teams użytkownika.

> [!NOTE]
> Ponieważ logowanie pojedyncze jest włączone, ważne jest, aby wyłączyć przeglądarkę przy użyciu funkcji [**WDAC.**](/hololens/windows-defender-application-control-wdac) Jeśli klient zewnętrzny otworzy przeglądarkę i użyje wersji internetowej usługi Teams, klient będzie miał dostęp do historii połączeń/czatów.

## <a name="general-deployment-recommendations-and-instructions"></a>Ogólne instrukcje Rekomendacje wdrażania

W przypadku 2 HoloLens zalecamy:

1. Użyj [najnowszej wersji HoloLens operacyjnego jako](https://aka.ms/hololens2download) kompilacji linii bazowej.
1. Przypisywanie licencji opartych na użytkownikach lub urządzeniach:
    1. Licencje oparte na użytkownikach i urządzeniach wykonaj następujące kroki:
        1. [Utwórz grupę w UAD i dodaj członków](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) dla HoloLens/RA.
        1. [Przypisz do tej](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) grupy licencje oparte na urządzeniach lub użytkownikach.
        1. (Opcjonalnie) Grupy docelowe można kierować do zasad zarządzania urządzeniami przenośnymi.

1. Urządzenia powinny być przyłączone do [dzierżawy,](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)automatycznie rejestrowane i konfigurowane za pośrednictwem programu Auto [pilotaż.](/hololens/hololens2-autopilot)
    1. Należy pamiętać, że pierwszy użytkownik urządzenia będzie właścicielem urządzenia.
    1. Należy pamiętać, że jeśli urządzenie jest przyłączone do aplikacji AAD, użytkownik, który wykonał sprzężenia, zostanie właścicielem urządzenia.
    1. Aby uzyskać więcej informacji, zobacz [Właściciel urządzenia.](/hololens/security-adminless-os#device-owner)
1. [Zablokowanie](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) urządzenia przez dzierżawę w celu dołączenia go tylko do dzierżawy.
    1. **Link dodatkowy:** [Tenant lock CSP](/windows/client-management/mdm/tenantlockdown-csp).
1. Skonfiguruj kiosk przy użyciu przypisanego globalnie dostępu do [tego urządzenia.](/hololens/hololens-global-assigned-access-kiosk)
1. Zalecamy wyłączenie następującej (opcjonalnej) możliwości:
    1. Możliwość ustawienia urządzenia w tryb dewelopera w [tym miejscu.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. Możliwość podłączenia urządzenia HoloLens z komputerem w celu skopiowania daty [wyłączenia portu USB.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > Jeśli nie chcesz wyłączać portu USB, ale chcesz mieć możliwość zastosowania pakietu aprowizowania do urządzenia przy użyciu portu USB, postępuj zgodnie z instrukcjami [**podanymi tutaj.**](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. Używanie [funkcji WDAC](/hololens/windows-defender-application-control-wdac) do zezwalania na aplikacje lub blokowania ich na HoloLens 2.
1. Zaktualizuj usługę Remote Assist do najnowszej wersji w ramach instalacji. Dostępne są dwie opcje, aby to zrobić:
    1. Można to zrobić, przechodząc do Windows **Microsoft Store --> Remote Assist --> zaktualizuj aplikację.**
    1. [ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) — co umożliwia automatyczne aktualizacje aplikacji — jest domyślnie włączone. Urządzenie musi być podłączone do zasilania, aby otrzymywać aktualizacje.
1. [Wyłącz wszystkie strony ustawień z](/hololens/settings-uri-list) wyjątkiem ustawień sieciowych, aby umożliwić użytkownikom łączenie się z sieciami gości w lokacjach klienckich.
1. [Zarządzanie HoloLens aktualizacji](/hololens/hololens-updates)
    1. Opcja [kontrolowania aktualizacji systemu operacyjnego lub](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) zezwalania na swobodne przepływy.
1. [Typowe ograniczenia dotyczące urządzeń.](/hololens/hololens-common-device-restrictions)
