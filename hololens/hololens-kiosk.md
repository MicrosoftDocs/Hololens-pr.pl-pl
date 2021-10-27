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
ms.openlocfilehash: e8f269a3793a5e61eb3eb4b88084a5e4af375ffa
ms.sourcegitcommit: 73a1555fb8b84f3d20c480282c648d8d800a6c98
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/26/2021
ms.locfileid: "130351723"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Konfigurowanie HoloLens jako kiosku

## <a name="what-is-kiosk-mode"></a>Co to jest tryb kiosku?

Tryb kiosku to funkcja, która pozwala kontrolować, które aplikacje są wyświetlane w menu Start, gdy użytkownik się HoloLens. Istnieją 2 obsługiwane scenariusze:

1. **Tryb kiosku z pojedynczą** aplikacją — menu Start nie jest wyświetlane, a pojedyncza aplikacja jest uruchamiana automatycznie, gdy użytkownik się pojawia. <br> *Przykładowe zastosowania:* urządzenie, na których działa tylko aplikacja Przewodniki usługi Dynamics 365.
2. **Tryb kiosku z** wieloma aplikacjami — menu Start tylko te aplikacje, które zostały określone w konfiguracji kiosku, gdy użytkownik się pojawia. W razie potrzeby można wybrać automatyczne uruchamianie aplikacji. <br> *Przykładowe zastosowania:* urządzenie, które wyświetla tylko aplikację ze Sklepu, Centrum opinii i Ustawienia w menu Start.

    <img alt="Multi app kiosk example" src=".\images\multi-app-kiosk.jpg" width="411" height="500" />

## <a name="description-of-kiosk-mode-experience-when-a-user-signs-in"></a>Opis trybu kiosku po dopisku użytkownika

W poniższej tabeli wymieniono możliwości funkcji w różnych trybach kiosku.

| &nbsp; |Menu Start |Menu Szybkie akcje |Aparat i wideo |Miracast |Cortana |Wbudowane polecenia głosowe |
| --- | --- | --- | --- | --- | --- | --- |
|Kiosk z jedną aplikacją |Disabled |Disabled |Disabled |Disabled   |Disabled |Włączone* |
|Kiosk z wieloma aplikacjami |Enabled (Włączony) |Włączone*  |Dostępne*  |Dostępne* |Dostępne*   |Włączone*  |

\*Aby uzyskać więcej informacji na temat włączania wyłączonych funkcji lub sposobu interakcji poleceń głosowych z wyłączonymi funkcjami i Cortana zobacz [HoloLens AUMID dla aplikacji.](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)

## <a name="key-general-considerations-before-configuring-kiosk-mode"></a>Najważniejsze zagadnienia ogólne przed skonfigurowaniem trybu kiosku

1. Określ rodzaj konta użytkownika logując się do usługi HoloLens w swoim środowisku — usługa HoloLens obsługuje konta usługi Azure Active Directory (AAD), konta Microsoft (MSA) i konta lokalne. Ponadto tymczasowo utworzone konta nazywane gośćmi/gośćmi są również obsługiwane (tylko w przypadku AAD urządzeń). Aby dowiedzieć się [więcej, zobacz Manage user identity and sign-in for HoloLens (Zarządzanie](hololens-identity.md)tożsamościami użytkowników i logowaniem na HoloLens).
2. Określ cele trybu kiosku — czy wszyscy, pojedynczy użytkownik, niektórzy użytkownicy czy użytkownicy są członkami AAD grupy itp.
3. W przypadku wielu trybów kiosku aplikacji określ aplikacje, które mają być wyświetlane w menu Start. Dla każdej aplikacji będzie potrzebny jej identyfikator modelu użytkownika [aplikacji (AUMID).](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)
4. Określ, czy tryb kiosku będzie stosowany do HoloLens za pośrednictwem pakietów aprowiwizowania środowiska uruchomieniowego lub serwera Zarządzanie urządzeniami (MDM).

## <a name="security-considerations"></a>Zagadnienia dotyczące bezpieczeństwa

Tryb kiosku nie powinien być traktowany jako metoda zabezpieczeń, ale jako sposób kontrolowania uruchamiania podczas logowania użytkownika. Możesz połączyć środowisko trybu kiosku z opcjami wymienionymi poniżej, jeśli istnieją określone potrzeby związane z zabezpieczeniami:

- Jeśli Ustawienia jest skonfigurowana do pokazywania w trybie kiosku i chcesz kontrolować, które strony są wyświetlane w aplikacji Ustawienia, zapoznaj się z tematem [Page Ustawienia Visibility](settings-uri-list.md) (Widoczność stron)
- Jeśli chcesz kontrolować dostęp do niektórych funkcji sprzętowych, takich jak aparat fotograficzny, Bluetooth itp. dla niektórych aplikacji itp., zapoznaj się z tematem Zasady w programie Policy CSP obsługiwanym przez program HoloLens 2 — [Windows Client Management.](/windows/client-management/mdm/policies-in-policy-csp-supported-by-hololens2) Aby zapoznać się z [naszymi wspólnymi ograniczeniami urządzeń,](hololens-common-device-restrictions.md) możesz zapoznać się z naszymi pomysłami.
- Tryb kiosku nie blokuje uruchamiania innych aplikacji przez aplikację (skonfigurowaną w ramach obsługi kiosku). Jeśli chcesz całkowicie zablokować uruchamianie niektórych aplikacji/procesów w usłudze HoloLens, zobacz Use [Windows Defender Application Control on HoloLens 2 devices in Microsoft Intune - Azure](/mem/intune/configuration/custom-profile-hololens) (Używanie kontroli aplikacji usługi Windows Defender na urządzeniach z systemem HoloLens 2 w usłudze Microsoft Intune — Azure)

## <a name="key-technical-considerations-for-kiosk-mode-for-hololens"></a>Kluczowe zagadnienia techniczne dotyczące trybu kiosku dla HoloLens

Ma zastosowanie tylko wtedy, gdy planujesz używać pakietów aprowiwizowania środowiska uruchomieniowego lub samodzielnie tworzyć konfiguracje kiosku. Konfiguracja trybu kiosku używa struktury hierarchicznej opartej na formacie XML:

- Przypisany profil dostępu określa, które aplikacje są wyświetlane w menu Start w trybie kiosku. Można zdefiniować wiele profilów w tej samej strukturze XML, do której można się później odwołać.
- Konfiguracja przypisanego dostępu odwołuje się do profilu i użytkowników docelowych tego profilu, na przykład określonego użytkownika lub AAD lub odwiedzającego itp. Można zdefiniować wiele konfiguracji w tej samej strukturze XML w zależności od złożoności scenariuszy użycia (zobacz sekcję obsługiwane scenariusze poniżej).
- Aby dowiedzieć się więcej, zapoznaj się z [tematem AssignedAccess CSP (AssignedAccess CSP).](/windows/client-management/mdm/assignedaccess-csp)

## <a name="supported-scenarios-for-kiosk-mode-based-on-identity-type"></a>Obsługiwane scenariusze dla trybu kiosku na podstawie typu tożsamości

Zapoznaj [się z linkami](hololens-kiosk-reference.md#kiosk-xml-code-samples) referencyjnymi, aby uzyskać przykłady na podstawie Twojego scenariusza i w razie potrzeby zaktualizuj je przed wklejonym kopiowaniem.

> [!NOTE]
> Użyj kodu XML tylko wtedy, gdy nie używasz interfejsu użytkownika usługi Intune do tworzenia konfiguracji kiosku.

### <a name="for-users-who-sign-in-as-either-local-account-or-msa"></a>Dla użytkowników, którzy logują się jako konto lokalne lub konto MSA

| **Żądane środowisko kiosku** | **Zalecana konfiguracja kiosku** | **Sposoby konfigurowania**  | **Uwagi** |
| --- | --- | --- | --- |
| Każdy użytkownik, który się insektuje, otrzyma środowisko kiosku. | [Konfigurowanie profilu globalnego przypisanego dostępu dla wielu aplikacji](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune szablon niestandardowy](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Aprowizowanie środowiska uruchomieniowego — wiele aplikacji](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Dostęp przypisany globalnie wymaga [20H2 i nowszej kompilacji](hololens-release-notes.md#windows-holographic-version-20h2) |
| Konkretny użytkownik, który się do tego dodaje, otrzymuje środowisko kiosku.  | [Skonfiguruj profil dostępu przypisany do jednej lub wielu aplikacji (zgodnie z wymaganiami), określając nazwę określonego użytkownika.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account) | [Zobacz obsługiwane opcje poniżej.](#steps-in-configuring-kiosk-mode-for-hololens) | W trybie kiosku z pojedynczą aplikacją tylko lokalne konto użytkownika lub konto MSA jest obsługiwane HoloLens. <br> W trybie kiosku z wieloma aplikacjami tylko konto MSA AAD jest obsługiwane na HoloLens. |

### <a name="for-users-who-sign-in-as-aad-account"></a>Dla użytkowników, którzy logują się jako AAD konta

| **Żądane środowisko kiosku** | **Zalecana konfiguracja kiosku** | **Sposoby konfigurowania** | **Uwagi** |
| --- | --- | --- | --- |
| Każdy użytkownik, który się insektuje, otrzyma środowisko kiosku. | [Konfigurowanie profilu globalnego przypisanego dostępu dla wielu aplikacji](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune szablon niestandardowy](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Aprowizowanie środowiska uruchomieniowego — wiele aplikacji](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Dostęp przypisany globalnie wymaga [20H2 i nowszej kompilacji](hololens-release-notes.md#windows-holographic-version-20h2) |
| Każdy użytkownik, który się insygnie, otrzyma środowisko kiosku z wyjątkiem niektórych użytkowników. | [Skonfiguruj profil globalnego dostępu przypisanego do wielu aplikacji, wykluczając niektórych użytkowników (którzy muszą być właścicielami urządzeń).](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile-excluding-device-owners) | • [Microsoft Intune szablon niestandardowy](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Aprowizowanie środowiska uruchomieniowego — wiele aplikacji](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Dostęp przypisany globalnie wymaga [20H2 i nowszej kompilacji](hololens-release-notes.md#windows-holographic-version-20h2) |
| Każdy AAD otrzymuje oddzielne środowisko kiosku specyficzne dla tego użytkownika. | [Skonfiguruj konfigurację przypisanego dostępu dla każdego użytkownika, określając jego AAD nazwę konta.](hololens-kiosk-reference.md#multiple-app-assigned-access-profiles-for-two-aad-users-or-more) | • [Microsoft Intune szablon niestandardowy](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Aprowizowanie środowiska uruchomieniowego — wiele aplikacji](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | &nbsp; |
| Użytkownicy w różnych AAD mają tryb kiosku, który jest tylko dla ich grupy. | [Skonfiguruj konfigurację przypisanego dostępu dla każdej żądanej AAD grupy.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-two-aad-groups-or-more) | • [Microsoft Intune szablon niestandardowy](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Aprowizowanie środowiska uruchomieniowego — wiele aplikacji](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | • Gdy użytkownik jest połączony z Internetem i użytkownik HoloLens zostanie odnaleziony jako członek grupy usługi AAD, dla której istnieje konfiguracja kiosku, użytkownik otrzyma dostęp do kiosku dla tej AAD grupy. <br> • Jeśli podczas logowania użytkownika nie ma dostępnego Internetu, użytkownik będzie HoloLens [zachowanie trybu awarii.](#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode) <br> • Jeśli dostępność Internetu nie jest gwarantowana, gdy trzeba użyć kiosku opartego na grupie AAD i użytkownika, rozważ użycie zasad [AADGroupMembershipCacheValidityInDayspolicy.](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk) <br> • Aby uzyskać optymalne środowisko AAD grup podczas logowania, zaleca się użycie polecenia [AADGroupMembershipCacheValidityInDayspolicy](/hololens/hololens-release-notes#cache-azure-ad-group-membership-for-offline-kiosk) |
| Użytkownicy, którzy muszą używać HoloLens do celów tymczasowych, uzyskają środowisko kiosku. | [Konfigurowanie konfiguracji przypisanego dostępu dla gości](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-visitors) | • [Microsoft Intune szablonu niestandardowego](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Aprowizowanie środowiska uruchomieniowego — pojedyncza aplikacja](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens) | • Tymczasowe konto użytkownika jest tworzone automatycznie HoloLens logowania i jest usuwane po wylogowania się użytkownika tymczasowego. <br> • Rozważ włączenie [zasad automatycznego logowania gościa.](#how-can-visitor-accounts-automatically-logon-to-kiosk-experience) |

## <a name="steps-in-configuring-kiosk-mode-for-hololens"></a>Kroki konfigurowania trybu kiosku dla HoloLens

Konfiguracje kiosku można tworzyć i stosować w następujący sposób:

1. Za pomocą interfejsu użytkownika serwera MDM, np. szablonów kiosku usługi Intune lub niestandardowych konfiguracji OMA-URI, które są następnie zdalnie stosowane do HoloLens.
2. Za pomocą pakietów aprowizowania środowiska uruchomieniowego, które są następnie bezpośrednio stosowane HoloLens.

Poniżej przedstawiono następujące sposoby konfigurowania. Wybierz kartę pasującą do procesu, który chcesz użyć.

1. [Microsoft Intune szablonu kiosku z pojedynczą aplikacją](hololens-kiosk.md?tabs=uisak#steps-in-configuring-kiosk-mode-for-hololens)
2. [Microsoft Intune szablonu kiosku z wieloma aplikacjami](hololens-kiosk.md?tabs=uimak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Microsoft Intune szablonu niestandardowego](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens)
1. [Aprowizowanie środowiska uruchomieniowego — wiele aplikacji](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Aprowizowanie środowiska uruchomieniowego — pojedyncza aplikacja](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens)

[!INCLUDE[](includes/kiosk-configure-steps.md)]

## <a name="frequently-asked-questions"></a>Często zadawane pytania

### <a name="how-can-visitor-accounts-automatically-logon-to-kiosk-experience"></a>W jaki sposób konta gości mogą automatycznie logować się do kiosku?

Na kompilacjach [Windows Holographic, wersja 21H1](hololens-release-notes.md#windows-holographic-version-21h1) i nowsza:

- AAD i inne konfiguracje obsługują konta gościa włączone automatycznie dla trybów kiosku.

[!INCLUDE[](includes/kiosk-autologin.md)]

### <a name="is-kiosk-experience-supported-on-hololens-1st-gen"></a>Czy środowisko kiosku jest obsługiwane HoloLens (1. generacji)?

Tryb kiosku jest dostępny tylko wtedy, gdy urządzenie Windows Holographic for Business. Wszystkie HoloLens 2 są Windows Holographic for Business i nie ma żadnych innych wersji. Co HoloLens 2 urządzenie może uruchomić tryb kiosku z pamięci.

HoloLens (1. generacji) należy uaktualnić zarówno pod względem kompilacji systemu operacyjnego, jak i wersji systemu operacyjnego. Poniżej znajduje się więcej informacji na temat aktualizowania HoloLens (1. generacji) [do Windows Holographic for Business](hololens1-upgrade-enterprise.md) wersji. Aby zaktualizować urządzenie HoloLens (1. generacji) w celu korzystania z trybu kiosku, należy najpierw upewnić się, że na urządzeniu działa Windows 10, wersja 1803 lub nowsza. Jeśli do odzyskania urządzenia z systemem HoloLens (pierwszej generacji) do kompilacji domyślnej zostało użyte narzędzie Windows Device Recovery Tool, lub jeśli zainstalowano najnowsze aktualizacje, urządzenie jest gotowe do skonfigurowania.

### <a name="how-to-use-device-portal-to-configure-kiosk-in-non-production-environments"></a>Jak skonfigurować kiosk w środowiskach nieprodukcji przy użyciu portalu urządzeń?

Skonfiguruj urządzenie [HoloLens do korzystania z Windows Portal urządzeń](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal). Serwer Portal urządzeń to serwer internetowy na komputerze HoloLens z którym można nawiązać połączenie z przeglądarki internetowej na komputerze.

 > [!CAUTION]
 > Po skonfigurowaniu HoloLens do korzystania z Portal urządzeń należy włączyć tryb dewelopera na urządzeniu. Tryb dewelopera na urządzeniu, na Windows Holographic for Business umożliwia ładowanie aplikacji side-load. Jednak to ustawienie tworzy ryzyko, że użytkownik może instalować aplikacje, które nie zostały certyfikowane przez Microsoft Store. Administratorzy mogą zablokować możliwość włączania trybu dewelopera przy użyciu ustawienia **ApplicationManagement/AllowDeveloper Unlock** w [programie Policy CSP.](/windows/client-management/mdm/policy-configuration-service-provider) [Dowiedz się więcej o trybie dewelopera.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)

Tryb kiosku można ustawić za pośrednictwem interfejsu API REST usługi Portal urządzeń, wykonując wpis POST na adres /api/holographic/kioskmode/settings z jednym wymaganym parametrem ciągu zapytania ("kioskModeEnabled" o wartości "true" lub "false") i jednym opcjonalnym parametrem ("startupApp" z wartością nazwy pakietu). Należy pamiętać, że Portal urządzeń jest przeznaczona tylko dla deweloperów i nie powinna być włączona na urządzeniach innych niż dewelopera. Interfejs API REST może ulec zmianie w przyszłych aktualizacjach/wydaniach.

## <a name="troubleshooting"></a>Rozwiązywanie problemów

### <a name="issue---no-apps-are-shown-in-start-menu-in-kiosk-mode"></a>Problem — w menu Start w trybie kiosku nie są wyświetlane żadne aplikacje

**Objawy**

W przypadku napotkania błędów podczas stosowania trybu kiosku zostanie wyświetlone następujące zachowanie:

- Przed Windows Holographic wersja 20H2 — HoloLens będą wyświetlane wszystkie aplikacje w menu Start.
- Windows Holographic, wersja 20H2 — jeśli urządzenie ma konfigurację kiosku, która jest kombinacją przypisanego dostępu globalnego i dostępu przypisanego do członka grupy AAD, w przypadku określenia niepowodzenia członkostwa w grupie usługi AAD użytkownik zobaczy menu "nic nie jest wyświetlane w menu Start".

    ![Obraz trybu kiosku wygląda teraz w przypadku awarii.](images/hololens-kiosk-failure-behavior.png )

- Począwszy od Windows Holographic w wersji [21H1,](hololens-release-notes.md#windows-holographic-version-21h1)tryb kiosku wyszukuje dostęp przypisany globalnie przed pokazaniem pustego menu Start. Środowisko kiosku powróci do globalnej konfiguracji kiosku (jeśli występuje), jeśli wystąpią błędy podczas AAD trybu kiosku grupy.

**Kroki rozwiązywania problemów**

- Sprawdź, czy wartość AUMID aplikacji jest poprawnie określona i nie zawiera wersji. Przykłady [można znaleźć HoloLens AUMID](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) dla aplikacji skrzynki odbiorczej.
- Upewnij się, że aplikacja jest zainstalowana na urządzeniu dla tego użytkownika.
- Jeśli konfiguracja kiosku jest oparta na AAD, upewnij się, że połączenie z Internetem jest obecne AAD użytkownikiem. W razie potrzeby skonfiguruj [zasady MixedReality/AADGroupMembershipCacheValidityInDays,](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-aadgroupmembershipcachevalidityindays) aby ta funkcja również działała bez Internetu.

Jeśli kod XML został użyty do utworzenia konfiguracji przypisanego dostępu (za pośrednictwem inicjowania obsługi środowiska uruchomieniowego lub niestandardowego kodu URI OMA usługi Intune), upewnij się, że kod XML jest dobrze uformowany, otwierając go w dowolnej przeglądarce internetowej lub edytorze XML. Zapoznaj się z [przykładami kodu XML kiosku,](hololens-kiosk-reference.md#kiosk-xml-code-samples) aby uzyskać dobrze utworzone i prawidłowe szablony.

### <a name="issue---building-a-package-with-kiosk-mode-failed"></a>Problem — Tworzenie pakietu z trybem kiosku nie powiodło się

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

Podczas stosowania pakietu aprowizowania na urządzeniach Hololens jest wyświetlany błąd

**Kroki rozwiązywania problemów**

1. Przejdź do folderu, w którym Windows Configuration Designer dla pakietu aprowizowania środowiska uruchomieniowego.
1. Otwórz plik ICD.log i upewnij się, że nie ma żadnych błędów w dzienniku podczas tworzenia pakietu aprowizowania. Niektóre błędy nie są wyświetlane podczas kompilacji, ale są nadal rejestrowane w pliku ICD.log

### <a name="issue--multiple-app-assigned-access-to-aad-group-does-not-work"></a>Problem — dostęp przypisany do wielu aplikacji AAD grupy nie działa

**Objawy**

Na AAD logowania użytkownika urządzenie nie jest w oczekiwanym trybie kiosku.

**Kroki rozwiązywania problemów**

- Upewnij się, że w pliku XML konfiguracji przypisanego dostępu używany jest identyfikator GUID AAD grupy, której członkiem jest zalogowany użytkownik, a nie identyfikator GUID AAD użytkownika.
- Upewnij się, że w portalu usługi Intune AAD użytkownik jest rzeczywiście wyświetlany jako członek docelowej AAD grupy.
- Upewnij się, że urządzenie jest wyświetlane jako zgodne tylko w przypadku usługi Intune. Aby uzyskać więcej [informacji, zapoznaj](/mem/intune/protect/device-compliance-get-started) się z informacjami na temat zgodności urządzeń.
