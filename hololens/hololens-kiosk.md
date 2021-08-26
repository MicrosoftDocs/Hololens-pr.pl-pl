---
title: Konfigurowanie HoloLens jako kiosku
description: Dowiedz się, jak skonfigurować konfigurację kiosku i używać jej do blokowania aplikacji na HoloLens urządzeń.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: daab30a8ea5200ca145b6b0234b8bd060b8cec5f
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859224"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Konfigurowanie HoloLens jako kiosku

## <a name="what-is-kiosk-mode"></a>Co to jest tryb kiosku?

Tryb kiosku to funkcja, która pozwala kontrolować, które aplikacje są wyświetlane w menu Start, gdy użytkownik się HoloLens. Istnieją 2 obsługiwane scenariusze:

1. **Tryb kiosku z pojedynczą** aplikacją — menu Start nie jest wyświetlane, a pojedyncza aplikacja jest uruchamiana automatycznie, gdy użytkownik się pojawia. <br> *Przykładowe zastosowania:* urządzenie, na których działa tylko aplikacja Przewodniki usługi Dynamics 365.
2. **Tryb kiosku z** wieloma aplikacjami — menu Start tylko te aplikacje, które zostały określone w konfiguracji kiosku, gdy użytkownik się pojawia. Aplikację można wybrać do automatycznego uruchamiania w razie potrzeby. <br> *Przykładowe zastosowania:* urządzenie, które wyświetla tylko aplikację ze Sklepu, Centrum opinii i Ustawienia w menu Start.

    <img alt="Multi app kiosk example" src=".\images\multi-app-kiosk.jpg" width="411" height="500" />

## <a name="description-of-kiosk-mode-experience-when-a-user-signs-in"></a>Opis trybu kiosku po dopisku użytkownika

W poniższej tabeli wymieniono możliwości funkcji w różnych trybach kiosku.

| &nbsp; |Menu Start |Menu Szybkie akcje |Aparat i wideo |Miracast |Cortana |Wbudowane polecenia głosowe |
| --- | --- | --- | --- | --- | --- | --- |
|Kiosk z jedną aplikacją |Disabled |Disabled |Disabled |Disabled   |Disabled |Włączone* |
|Kiosk z wieloma aplikacjami |Enabled (Włączony) |Włączone*  |Dostępne*  |Dostępne* |Dostępne*   |Włączone*  |

Aby uzyskać więcej informacji na temat włączania wyłączonych funkcji lub sposobu interakcji poleceń głosowych z wyłączonymi funkcjami i Cortana zobacz [HoloLens AUMID dla aplikacji.](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)

## <a name="key-general-considerations-before-configuring-kiosk-mode"></a>Najważniejsze zagadnienia ogólne przed skonfigurowaniem trybu kiosku

1. Określ rodzaj konta użytkownika logując się do urządzenia Hololens w swoim środowisku — usługa HoloLens obsługuje konta usługi Azure Active Directory (AAD), konta Microsoft (MSA) i konta lokalne. Ponadto są również obsługiwane tymczasowo utworzone konta nazywane gośćmi/gośćmi (tylko w przypadku urządzeń dołączanych do usługi AAD). Aby dowiedzieć się [więcej, zobacz Manage user identity and sign-in for HoloLens (Zarządzanie](hololens-identity.md)tożsamościami użytkowników i logowaniem na HoloLens).
2. Określanie celów trybu kiosku — określa, czy wszyscy, pojedynczy użytkownicy, określeni użytkownicy, czy użytkownicy są członkami grup w ucieki.
3. W przypadku wielu trybów kiosku aplikacji określ aplikacje, które mają być wyświetlane w menu Start. Dla każdej aplikacji będzie potrzebny jej identyfikator modelu użytkownika [aplikacji (AUMID).](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)
4. Określ, czy tryb kiosku będzie stosowany do HoloLens za pośrednictwem pakietów aprowiwizowania środowiska uruchomieniowego lub serwera Zarządzanie urządzeniami (MDM).

## <a name="security-considerations"></a>Zagadnienia dotyczące bezpieczeństwa

Tryb kiosku nie powinien być traktowany jako metoda zabezpieczeń, ale jako sposób kontrolowania uruchamiania podczas logowania użytkownika. Możesz połączyć środowisko trybu kiosku z opcjami wymienionymi poniżej, jeśli istnieją określone potrzeby związane z zabezpieczeniami:

- Jeśli Ustawienia jest skonfigurowana do pokazywania w trybie kiosku i chcesz kontrolować, które strony są wyświetlane w aplikacji Ustawienia, zapoznaj się z tematem [Page Ustawienia Visibility (Widoczność stron)](settings-uri-list.md)
- Jeśli chcesz kontrolować dostęp do niektórych funkcji sprzętowych, takich jak aparat fotograficzny, Bluetooth itp. dla niektórych aplikacji itp., zapoznaj się z tematem Zasady w programie Policy CSP obsługiwanym przez program [HoloLens 2 — Windows Client Management](/windows/client-management/mdm/policies-in-policy-csp-supported-by-hololens2). Możesz zapoznać się z [naszymi wspólnymi ograniczeniami urządzeń,](hololens-common-device-restrictions.md) aby zapoznać się z pomysłami.
- Tryb kiosku nie blokuje uruchamiania innych aplikacji przez aplikację (skonfigurowaną w ramach obsługi kiosku). Jeśli chcesz całkowicie zablokować uruchamianie niektórych aplikacji/procesów w usłudze HoloLens, zobacz Use [Windows Defender Application Control on HoloLens 2 devices in Microsoft Intune - Azure](/mem/intune/configuration/custom-profile-hololens) (Używanie kontroli aplikacji usługi Windows Defender na urządzeniach z systemem HoloLens 2 w usłudze Microsoft Intune — Azure)

## <a name="key-technical-considerations-for-kiosk-mode-for-hololens"></a>Kluczowe zagadnienia techniczne dotyczące trybu kiosku dla HoloLens

Ma zastosowanie tylko wtedy, gdy planujesz używać pakietów aprowiwizowania środowiska uruchomieniowego lub samodzielnie tworzyć konfiguracje kiosku. Konfiguracja trybu kiosku używa struktury hierarchicznej opartej na formacie XML:

- Przypisany profil dostępu określa, które aplikacje są wyświetlane w menu Start w trybie kiosku. Można zdefiniować wiele profilów w tej samej strukturze XML, do których można się później odwołać.
- Konfiguracja przypisanego dostępu odwołuje się do profilu i użytkowników docelowych tego profilu, na przykład określonego użytkownika, grupy usługi AAD lub odwiedzającego itp. Można zdefiniować wiele konfiguracji w tej samej strukturze XML w zależności od złożoności scenariuszy użycia (zobacz sekcję obsługiwane scenariusze poniżej).
- Aby dowiedzieć się więcej, zapoznaj się z [tematem AssignedAccess CSP (AssignedAccess CSP).](/windows/client-management/mdm/assignedaccess-csp)

## <a name="supported-scenarios-for-kiosk-mode-based-on-identity-type"></a>Obsługiwane scenariusze dla trybu kiosku na podstawie typu tożsamości

> [!NOTE]
> Użyj kodu XML tylko wtedy, gdy nie używasz interfejsu użytkownika usługi Intune do tworzenia konfiguracji kiosku.

### <a name="for-users-who-sign-in-as-either-local-account-or-msa"></a>Dla użytkowników, którzy logują się jako konto lokalne lub konto MSA

| **Żądane środowisko kiosku** | **Zalecana konfiguracja kiosku** | **Sposoby konfigurowania**  | **Uwagi** |
| --- | --- | --- | --- |
| Każdy użytkownik, który się insektuje, otrzyma środowisko kiosku. | [Konfigurowanie profilu przypisanego globalnie dostępu dla wielu aplikacji](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune szablon niestandardowy](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Aprowizowanie środowiska uruchomieniowego — wiele aplikacji](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Dostęp przypisany globalnie wymaga [20H2 i nowszej kompilacji](hololens-release-notes.md#windows-holographic-version-20h2) |
| Konkretny użytkownik, który się do tego dodaje, otrzymuje środowisko kiosku.  | [Skonfiguruj profil dostępu przypisany do jednej lub wielu aplikacji (zgodnie z wymaganiami), określając nazwę określonego użytkownika.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account) | [Zobacz obsługiwane opcje poniżej.](#steps-in-configuring-kiosk-mode-for-hololens) | W trybie kiosku z pojedynczą aplikacją tylko konto użytkownika lokalnego lub konto MSA jest obsługiwane HoloLens. <br> W przypadku wielu trybów kiosku aplikacji tylko konto MSA lub konto usługi AAD jest obsługiwane HoloLens. |

### <a name="for-users-who-sign-in-as-aad-account"></a>Dla użytkowników, którzy logują się jako konto WAD

| **Żądane środowisko kiosku** | **Zalecana konfiguracja kiosku** | **Sposoby konfigurowania** | **Uwagi** |
| --- | --- | --- | --- |
| Każdy użytkownik, który się insektuje, otrzyma środowisko kiosku. | [Konfigurowanie profilu przypisanego globalnie dostępu dla wielu aplikacji](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune szablon niestandardowy](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Aprowizowanie środowiska uruchomieniowego — wiele aplikacji](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Dostęp przypisany globalnie wymaga [20H2 i nowszej kompilacji](hololens-release-notes.md#windows-holographic-version-20h2) |
| Każdy użytkownik, który się insygnie, otrzyma środowisko kiosku z wyjątkiem niektórych użytkowników. | [Skonfiguruj profil globalnego dostępu przypisanego do wielu aplikacji, wykluczając niektórych użytkowników (którzy muszą być właścicielami urządzeń).](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile-excluding-device-owners) | • [Microsoft Intune szablon niestandardowy](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Aprowizowanie środowiska uruchomieniowego — wiele aplikacji](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Dostęp przypisany globalnie wymaga [20H2 i nowszej kompilacji](hololens-release-notes.md#windows-holographic-version-20h2) |
| Każdy użytkownik aplikacji AAD otrzymuje oddzielne środowisko kiosku specyficzne dla tego użytkownika. | [Skonfiguruj konfigurację przypisanego dostępu dla każdego użytkownika, określając jego nazwę konta usługi AAD.](hololens-kiosk-reference.md#multiple-app-assigned-access-profiles-for-two-aad-users-or-more) | • [Microsoft Intune szablon niestandardowy](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Aprowizowanie środowiska uruchomieniowego — wiele aplikacji](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | &nbsp; |
| Użytkownicy w różnych grupach aAD mają tryb kiosku, który jest tylko dla ich grupy. | [Skonfiguruj konfigurację przypisanego dostępu dla każdej żądanej grupy usługi AAD.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-two-aad-groups-or-more) | • [Microsoft Intune szablon niestandardowy](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Aprowizowanie środowiska uruchomieniowego — wiele aplikacji](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | • Gdy użytkownik jest połączony z Internetem i HoloLens jest połączony z Internetem, jeśli zostanie on członkiem grupy usługi AAD, dla której istnieje konfiguracja kiosku, użytkownik otrzyma dostęp do kiosku dla tej grupy usługi AAD. <br> • Jeśli podczas logowania użytkownika nie ma dostępnego Internetu, użytkownik będzie HoloLens [zachowanie trybu awarii.](#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode) <br> • Jeśli dostępność Internetu nie jest gwarantowana, gdy trzeba użyć kiosku opartego na grupach usługi AAD i się do tego konta, rozważ użycie zasad [AADGroupMembershipCacheValidityInDayspolicy.](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk) |
| Użytkownicy, którzy muszą używać HoloLens do celów tymczasowych, mogą korzystać z kiosku. | [Konfigurowanie konfiguracji przypisanego dostępu dla gości](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-visitors) | • [Microsoft Intune szablon niestandardowy](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Aprowizowanie środowiska uruchomieniowego — pojedyncza aplikacja](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens) | • Tymczasowe konto użytkownika jest tworzone automatycznie HoloLens logowania i jest usuwane po wylogowania się użytkownika tymczasowego. <br> • Rozważ włączenie [zasad automatycznego logowania gościa.](#how-to-can-visitor-accounts-automatically-logon-into-kiosk-experience) |

## <a name="steps-in-configuring-kiosk-mode-for-hololens"></a>Kroki konfigurowania trybu kiosku dla HoloLens

Konfiguracje kiosku można tworzyć i stosować w następujący sposób:

1. Za pomocą interfejsu użytkownika serwera MDM, np. szablonów kiosku usługi Intune lub niestandardowych konfiguracji OMA-URI, które są następnie zdalnie stosowane do HoloLens.
2. Za pomocą pakietów aprowizowania środowiska uruchomieniowego, które są następnie bezpośrednio stosowane HoloLens.

Poniżej przedstawiono sposoby konfigurowania i wybierz kartę pasującą do procesu, który chcesz użyć.

1. [Microsoft Intune szablonu kiosku z pojedynczą aplikacją](hololens-kiosk.md?tabs=uisak#steps-in-configuring-kiosk-mode-for-hololens)
2. [Microsoft Intune szablonu kiosku z wieloma aplikacjami](hololens-kiosk.md?tabs=uimak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Microsoft Intune szablon niestandardowy](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens)
1. [Aprowizowanie środowiska uruchomieniowego — wiele aplikacji](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Aprowizowanie środowiska uruchomieniowego — pojedyncza aplikacja](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens)

[!INCLUDE[](includes/kiosk-configure-steps.md)]

## <a name="frequently-asked-questions"></a>Często zadawane pytania

### <a name="how-to-can-visitor-accounts-automatically-logon-into-kiosk-experience"></a>Jak konta gości mogą automatycznie logować się do kiosku?

W kompilacjach [Windows Holographic, wersja 21H1](hololens-release-notes.md#windows-holographic-version-21h1) i nowsza:

- Konfiguracje usługi AAD i inne niż ADD obsługują konta gościa z włączoną automatyczną obsługą trybów kiosku.

[!INCLUDE[](includes/kiosk-autologin.md)]

### <a name="is-kiosk-experience-supported-on-hololens-1st-gen"></a>Czy środowisko kiosku jest obsługiwane na urządzeniach Hololens (1. generacji)?

Tryb kiosku jest dostępny tylko wtedy, gdy urządzenie Windows Holographic for Business. Wszystkie HoloLens 2 są Windows Holographic for Business i nie ma żadnych innych wersji. Co HoloLens 2 urządzenie może uruchomić tryb kiosku.

HoloLens (1. generacji) należy uaktualnić zarówno pod względem kompilacji systemu operacyjnego, jak i wersji systemu operacyjnego. Poniżej znajduje się więcej informacji na temat aktualizowania HoloLens (1. generacji) do [Windows Holographic for Business](hololens1-upgrade-enterprise.md) wersji. Aby zaktualizować urządzenie HoloLens (1. generacji) do trybu kiosku, należy najpierw upewnić się, że na urządzeniu działa Windows 10, wersja 1803 lub nowsza. Jeśli do odzyskania urządzenia z systemem HoloLens (1. generacji) do kompilacji domyślnej zostało użyte narzędzie Windows Device Recovery Tool, lub jeśli zainstalowano najnowsze aktualizacje, urządzenie jest gotowe do skonfigurowania.

### <a name="how-to-use-device-portal-to-configure-kiosk-in-non-production-environments"></a>Jak skonfigurować kiosk w środowiskach nieprodukcji przy użyciu portalu urządzeń?

Skonfiguruj urządzenie [HoloLens do korzystania z Windows Portal urządzeń](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal). Serwer Portal urządzeń to serwer internetowy na komputerze HoloLens z którym można nawiązać połączenie z przeglądarki internetowej na komputerze.

 > [!CAUTION]
 > Po skonfigurowaniu HoloLens do korzystania z Portal urządzeń należy włączyć tryb dewelopera na urządzeniu. Tryb dewelopera na urządzeniu z Windows Holographic for Business umożliwia ładowanie aplikacji side-load. Jednak to ustawienie tworzy ryzyko, że użytkownik może instalować aplikacje, które nie zostały certyfikowane przez Microsoft Store. Administratorzy mogą zablokować możliwość włączania trybu dewelopera przy użyciu ustawienia **ApplicationManagement/AllowDeveloper Unlock** w [programie Policy CSP.](/windows/client-management/mdm/policy-configuration-service-provider) [Dowiedz się więcej o trybie dewelopera.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)

Tryb kiosku można ustawić za pośrednictwem interfejsu API REST usługi Portal urządzeń, wykonując wpis POST na adres /api/holographic/kioskmode/settings z jednym wymaganym parametrem ciągu zapytania ("kioskModeEnabled" o wartości "true" lub "false") i jednym opcjonalnym parametrem ("startupApp" z wartością nazwy pakietu). Należy pamiętać, że Portal urządzeń jest przeznaczona tylko dla deweloperów i nie powinna być włączona na urządzeniach innych niż deweloper. Interfejs API REST może ulec zmianie w przyszłych aktualizacjach/wydaniach.

## <a name="troubleshooting"></a>Rozwiązywanie problemów

### <a name="issue---no-apps-are-shown-in-start-menu-in-kiosk-mode"></a>Problem — w menu Start w trybie kiosku nie są wyświetlane żadne aplikacje?

**Objawy**

W przypadku napotkania błędów podczas stosowania trybu kiosku zostanie wyświetlone następujące zachowanie:

- Przed Windows Holographic wersja 20H2 — HoloLens będą wyświetlane wszystkie aplikacje w menu Start.
- Windows Holographic, wersja 20H2 — jeśli urządzenie ma konfigurację kiosku, która jest kombinacją przypisanego dostępu globalnego i przypisanego do członka grupy usługi AAD, w przypadku określenia niepowodzenia członkostwa w grupie usługi AAD użytkownik zobaczy menu "nic nie jest wyświetlane w menu Start".

    ![Obraz trybu kiosku wygląda teraz w przypadku awarii.](images/hololens-kiosk-failure-behavior.png )

- Począwszy od Windows Holographic w wersji [21H1,](hololens-release-notes.md#windows-holographic-version-21h1)tryb kiosku wyszukuje dostęp przypisany globalnie przed pokazaniem pustego menu Start. Środowisko kiosku powróci do globalnej konfiguracji kiosku (jeśli występuje), jeśli wystąpią błędy podczas trybu kiosku grupy usługi AAD.

**Kroki rozwiązywania problemów**

- Sprawdź, czy wartość AUMID aplikacji jest poprawnie określona i nie zawiera wersji. Przykłady [można znaleźć HoloLens AUMID](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) dla aplikacji skrzynki odbiorczej.
- Upewnij się, że aplikacja jest zainstalowana na urządzeniu dla tego użytkownika.
- Jeśli konfiguracja kiosku jest oparta na grupach usługi AAD, upewnij się, że po zaloguje się użytkownik usługi AAD istnieje łączność z Internetem. W razie potrzeby skonfiguruj zasady [MixedReality/AADGroupMembershipCacheValidityInDays,](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-aadgroupmembershipcachevalidityindays) aby działały również bez Internetu.

### <a name="issue---building-a-package-with-kiosk-mode-failed"></a>Problem — tworzenie pakietu z trybem kiosku nie powiodło się

**Objawy**

Zostanie wyświetlone okno dialogowe podobne do poniższego.

<kbd>
    <img alt="Kiosk failure to build" src="./images/kiosk-steps/kiosk-ppkg-failure.png"/>
</kbd>

**Kroki rozwiązywania problemów**

1. Kliknij hiper link pokazany w powyższym oknie dialogowym.
1. Otwórz plik ICD.log w edytorze tekstów, a jego zawartość powinna wskazywać błąd.

> [!NOTE]
> Jeśli podjęto kilka prób, sprawdź sygnatury czasowe w dzienniku. Pomoże to sprawdzić tylko bieżące problemy.

### <a name="issue--provisioning-package-built-successfully-but-failed-to-apply"></a>Problem — pakiet inicjowania obsługi administracyjnej został sbudowaną pomyślnie, ale nie można go zastosować.

**Objawy**

Błąd jest wyświetlany podczas stosowania pakietu aprowizowania na urządzeniach Hololens

**Kroki rozwiązywania problemów**

1. Przejdź do folderu, w którym Windows Configuration Designer dla pakietu aprowizowania środowiska uruchomieniowego.
1. Otwórz plik ICD.log i upewnij się, że nie ma żadnych błędów w dzienniku podczas budowania pakietu aprowizowania. Niektóre błędy nie są wyświetlane podczas kompilacji, ale są nadal rejestrowane w pliku ICD.log

### <a name="issue--multiple-app-assigned-access-to-aad-group-does-not-work"></a>Problem — dostęp przypisany do wielu aplikacji do grupy usługi AAD nie działa

**Objawy**

W przypadku logowania użytkownika w UAD urządzenie nie jest w trybie kiosku

**Kroki rozwiązywania problemów**

- Upewnij się, że w pliku XML konfiguracji przypisanego dostępu używany jest identyfikator GUID grupy usługi AAD, której członkiem jest zalogowany użytkownik, a nie identyfikator GUID użytkownika usługi AAD.
- Upewnij się, że w portalu usługi Intune użytkownik usługi AAD jest rzeczywiście wyświetlany jako członek docelowej grupy usługi AAD.
