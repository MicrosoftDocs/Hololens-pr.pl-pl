---
title: Przewodnik wdrażania — przewodnik po HoloLens 2 z usługą Dynamics 365 — konfigurowanie
description: Dowiedz się, jak skonfigurować konfiguracje wdrażania HoloLens 2 za pośrednictwem firmowej połączonej sieci za pomocą przewodników usługi Dynamics 365.
keywords: HoloLens, zarządzanie, połączenie firmowe, przewodniki usługi Dynamics 365, AAD, Azure AD, MDM, Mobile Zarządzanie urządzeniami
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
ms.openlocfilehash: 9457acd2f53d0d3127d6c68d620b660f6e09866d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637085"
---
# <a name="configure---corporate-connected-guide"></a>Konfigurowanie — przewodnik po połączeniach firmowych

## <a name="azure-users-and-groups"></a>Użytkownicy i grupy platformy Azure

Platforma Azure i usługa Intune tego rozszerzenia używa użytkowników i grup do przypisywania konfiguracji i licencji. Aby zweryfikować ten przepływ wdrażania i sprawdzić, czy można utworzyć i obsługiwać przewodnik, musisz&#39;konto użytkownika.

Możemy utworzyć jedną grupę użytkowników specjalnie do przypisywania licencji.

Jeśli nie&#39;jeszcze dostępu do dwóch kont usługi Azure AD w grupie użytkowników, możesz użyć funkcji . Poniżej znajdują się przewodniki Szybki start dotyczące:

- [Jak utworzyć użytkownika](/mem/intune/fundamentals/quickstart-create-user)
- [Jak utworzyć grupę](/mem/intune/fundamentals/quickstart-create-group)
- [Dodawanie użytkowników do grupy —](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) dodawanie utworzonych użytkowników w celu utworzenia grupy
- [Konfigurowanie usługi Azure AD w celu umożliwienia grupie użytkowników](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) dołączania urządzeń — upewnij się, że nowa grupa użytkowników ma uprawnienia do rejestrowania urządzeń w usłudze Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>Automatyczne rejestrowanie w HoloLens 2

Aby zapewnić bezproblemowe i bezproblemowe środowisko, możesz skonfigurować funkcję Azure Active Directory Join (AADJ) i automatyczne rejestrowanie w usłudze Intune dla urządzeń z systemem HoloLens 2. Umożliwia to użytkownikom wprowadzanie poświadczeń logowania organizacji podczas OOBE oraz automatyczne rejestrowanie w usłudze Azure AD i rejestrowanie urządzenia w usłudze MDM.

Korzystając z [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), możemy wybierać usługi i nawigować po kilku stronach, dopóki nie wybierzemy opcji Pobierz Premium wersji próbnej. Możesz zauważyć, że istnieje Azure Active Directory — wersja Premium 1 i 2 — dla automatycznego rejestrowania P1 jest wystarczająca. Możemy wybrać usługę Intune, wybrać zakres użytkownika dla automatycznej rejestracji, a następnie wybrać grupę, która została wcześniej utworzona.

Aby uzyskać szczegółowe informacje i instrukcje, przeczytaj przewodnik [dotyczący włączania automatycznej rejestracji w usłudze Intune.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="corporate-wi-fi-connectivity"></a>Łączność Wi-Fi firmowa

Połączenia Wi-Fi firmowe często wymagają uwierzytelniania opartego na certyfikatach dla klientów korzystających HoloLens 2. Takie certyfikaty należy wdrożyć przy użyciu infrastruktury certyfikatów prosty protokół rejestrowania certyfikatów (SCEP) lub PKCS (Public Key Cryptography Standard) zintegrowanej z rozwiązaniem MDM. Wdrażanie profilów Wi-Fi, certyfikatów i ustawień serwera proxy przy użyciu usługi Intune zapewnia bezproblemowe środowisko dla użytkowników końcowych.
 
### <a name="deploy-certificates-and-wi-fi-profiles"></a>Wdrażanie certyfikatów i Wi-Fi profilów

Aby wdrożyć certyfikaty i profile za pośrednictwem Microsoft Endpoint Manager, wykonaj następujące kroki:

1. Utwórz profil dla każdego certyfikatu głównego i pośredniego (zobacz [Tworzenie profilów zaufanych certyfikatów).](/intune/protect/certificates-configure#create-trusted-certificate-profiles) Każdy z tych profilów musi mieć opis, który zawiera datę wygaśnięcia w formacie DD/MM/YYYY.

    > [!CAUTION]
    > **Profile certyfikatów bez daty wygaśnięcia nie zostaną wdrożone.**

2. Utwórz profil dla każdego certyfikatu SCEP lub PKCS (zobacz Tworzenie profilu certyfikatu SCEP lub Tworzenie profilu certyfikatu [PKCS).](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)Każdy z tych profilów musi mieć opis, który zawiera datę wygaśnięcia w formacie DD/MM/YYYY.

    > [!CAUTION]
    > **Profile certyfikatów bez daty wygaśnięcia nie zostaną wdrożone.**

    > [!Note]
    > Ponieważ urządzenie HoloLens 2 jest uznawane za urządzenie udostępnione, czyli wielu użytkowników na urządzenie, zaleca się wdrożenie certyfikatów urządzeń zamiast certyfikatów użytkownika na Wi-Fi uwierzytelniania, jeśli jest to możliwe.

3. Utwórz profil dla firmowej sieci Wi-Fi sieci (zobacz [Ustawienia sieci Wi-Fi](/intune/wi-fi-settings-windows)dla urządzeń Windows 10 i nowszych). W profilu Wi-Fi można wybrać opcję użycia ustawień serwera proxy w organizacji.

    Dostępne opcje:
    - **Brak**: nie są konfigurowane żadne ustawienia serwera proxy.
    - **Ręcznie skonfiguruj :** wprowadź adres IP serwera **proxy** i jego **numer portu**.
    - **Skonfiguruj automatycznie**: wprowadź adres URL wskazujący skrypt automatycznej konfiguracji serwera proxy (PAC). Na przykład wprowadź *http://proxy.contoso.com/proxy.pac* .

    Aby uzyskać więcej informacji na temat plików PAC, zobacz [Proxy Auto-Configuration (PAC) file](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (Plik automatycznej konfiguracji serwera proxy (PAC)). Zostanie otwarta witryna nienależąca do firmy Microsoft.
 
    > [!Note]
    > Zaleca się, aby profil Wi-Fi był przypisany do grup urządzeń, a nie grup użytkowników, jeśli jest to możliwe.
     
    > [!Tip]
    > Możesz również wyeksportować roboczy profil Wi-Fi z komputera Windows 10 w sieci firmowej. Ten eksport tworzy plik XML ze wszystkimi bieżącymi ustawieniami. Następnie zaimportuj ten plik do usługi Intune i użyj go jako profilu Wi-Fi dla urządzeń HoloLens 2. Zobacz [Eksportowanie i importowanie ustawień sieci Wi-Fi dla urządzeń z systemem Windows](/mem/intune/configuration/wi-fi-settings-import-windows-8-1).

1.  [Przypisz](/mem/intune/configuration/device-profile-assign) profile urządzeń do HoloLens grupy urządzeń.

2.  [Monitorowanie](/mem/intune/configuration/device-profile-monitor) profilów urządzeń w usłudze Intune.

Jeśli występują problemy z profilami usługi Wi-Fi, informacje można Wi-Fi rozwiązywanie problemów z profilami konfiguracji [urządzeń w usłudze Intune.](/troubleshoot/mem/intune/troubleshoot-wi-fi-profiles)

## <a name="troubleshooting-external-internet-access-when-corp-connected"></a>Rozwiązywanie problemów z zewnętrznym dostępem do Internetu po podłączeniu do firmy
Gdy usługi próbują nie przechodzić przez ustawiony serwer proxy, mogą próbować nawiązać połączenie za pośrednictwem zapory. Aby rozwiązać te problemy, możesz dodać listę specyficznych dla punktu końcowego reguł zapory.

Jeśli porty zapory są blokowane, włącz niektóre typowe [punkty końcowe](/hololens/hololens-offline) dla HoloLens.

Możesz również włączyć porty określone dla przewodników: adresy URL dostępne z Internetu [wymagane do połączenia](https://support.microsoft.com/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)z Microsoft Dynamics CRM Online .

## <a name="app-deployment"></a>Wdrażanie aplikacji

Wdrażanie aplikacji LOB za pośrednictwem rozwiązania MDM to metoda, która jest łatwa do skalowania i może być automatycznie wdrażana na urządzeniach po zarejestrowaniu w utworzonej grupie.

Jeśli nadal opracowujesz aplikacje lub jeszcze ich nie masz, możesz użyć przykładowej aplikacji centrum przykładów mrtk. Ta przykładowa aplikacja jest gotowa do użycia i nie wymaga użycia aparatu Unity ani Visual Studio. [Pobierz przykładową aplikację MRTK Examples](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App).

Jeśli wolisz używać własnej aplikacji lub interesuje Cię tworzenie aplikacji dla Mixed Reality, możesz zapoznać się z naszą dokumentacją Mixed Reality [dewelopera.](/windows/mixed-reality/design/design)

> [!NOTE]
> Wymagania systemowe dla HoloLens są oparte na architekturze kompilacji aplikacji. HoloLens 2 używają architektury ARM. Podczas tworzenia aplikacji w Visual Studio upewnij się, że wybrano właściwą architekturę dla urządzenia i dołączyć wszystkie wymagane zależności.

> [!IMPORTANT]
> Podczas wdrażania aplikacji LOB ważne jest również przekazanie certyfikatu do usługi Intune i przypisanie go do tej samej grupy, która jest przeznaczona do korzystania z aplikacji lub nie zostanie poprawnie zainstalowany.

### <a name="upload-and-assign-the-app"></a>Upload i przypisywanie aplikacji

1. Przejdź do centrum [administracyjnego MEM.](https://endpoint.microsoft.com/#home)

2. Wybierz **pozycję**  ->  **Wszystkie aplikacje** i wybierz **przycisk + Dodaj.**

3. Poniżej opcji Inne wybierz pozycję Aplikacja **biznesowa**. Kliknij **pozycję Wybierz**.

4. Wybierz plik pakietu aplikacji, jest to plik APPXBUNDLE. W naszym przypadku aplikacja to _MRTK Examples Hub \_ 2.4.2.0 \_ arm \_ Master.appxbundle._

5. Zostaniesz powiadomiony o brakujących zależnościach. W tym przypadku musimy przekazać plik _Microsoft.VCLibs.ARM.14.00.appx._ Wyszukaj go w **obszarze Wybierz plik**.

6. Wybierz przycisk OK.

7. Na następnym ekranie wymagane pola zostaną wypełnione automatycznie. Wybierz opcję **Dalej**.

8. W obszarze Wymagane dodaj wcześniej utworzoną grupę, aby aplikacja była wymagana dla tej grupy. Spowoduje to automatyczne pobranie aplikacji na zarejestrowane urządzenia w grupie. Wybierz opcję **Dalej**.

9. Wybierz przycisk **Utwórz**.

Dowiedz się więcej: [Przypisywanie aplikacji do grup w Microsoft Intune](/mem/intune/apps/apps-deploy#assign-an-app)

## <a name="setup-guides-application-licenses-dataverse-and-authoring"></a>Przewodniki instalacji: licencje aplikacji, daneverse i tworzenie

Aby móc korzystać z przewodników usługi Dynamics 365, należy wykonać pewne przygotowania. Istnieją trzy obszary, w których musimy się przygotować. użytkownicy, daneverse i same przewodniki.

### <a name="users-and-application-licenses"></a>Licencje użytkowników i aplikacji

Aby ktoś mógł korzystać z przewodników, musi użyć konta usługi Azure AD, które zostało wcześniej ustawione w tym przewodniku.

Musisz również przypisać licencję przewodników usługi Dynamics 365 do utworzonego użytkownika. Zrobisz to z centrum administracyjne platformy Microsoft 365 [.](https://admin.microsoft.com/AdminPortal/Home) Przypisz również licencję do podstawowego konta platformy Azure.

Postępuj [zgodnie z tym krótkim przewodnikiem](/dynamics365/mixed-reality/guides/setup-step-one#assign-the-dynamics-365-guides-license-to-user-accounts) ze zdjęciami, aby uzyskać instrukcje krok po kroku dotyczące stosowania licencji aplikacji.

### <a name="set-up-the-dataverse"></a>Konfigurowanie aplikacji Dataverse

Aby skonfigurować [środowisko produkcyjne,](/dynamics365/mixed-reality/guides/setup-step-two#set-up-a-production-environment-for-purchased-licenses-only) należy spełnić dwa wymagania wstępne. Musisz mieć rolę [**Administratora**](/power-platform/admin/database-security)  systemu i musisz mieć licencję [**usługi Power Apps**](/power-platform/admin/signup-question-and-answer) (lub licencję przewodników usługi [**Dynamics 365,**](/dynamics365/mixed-reality/guides/setup-step-one) która zawiera licencję Power Apps). Jeśli w tym przewodniku utworzono usługę Azure AD, spełniasz wymagania dotyczące roli dla administratora systemu. W poprzednim kroku przypisaliśmy również licencję przewodnika.

W tym przewodniku o [tworzeniu środowiska Microsoft Dataverse:](/dynamics365/mixed-reality/guides/setup-step-two)

1. Rozpocznij od utworzenia [centrum administracyjne platformy Power Platform](https://admin.powerplatform.microsoft.com/environments) i utworzenia nowego środowiska.
2. Podczas tworzenia **nowego środowiska** dla ustawienia **Typ** wybierz&#39;**produkcyjne.**
3. Ważne jest, aby włączyć przełącznik **Tworzenie bazy danych dla tego środowiska?**  na **tak.**
4. W  **oknie dialogowym**  Dodawanie bazy danych ustaw opcję  **Włącz aplikacje usługi Dynamics 365**  na  **wartość Tak.**

Należy zwiększyć maksymalny rozmiar plików elementów w danychverse. Zwiększenie maksymalnego rozmiaru pliku umożliwi przekazanie większych modeli 3D lub plików wideo, które będą później dostępne w przewodnikach. Postępuj zgodnie z krótkim [przewodnikiem, aby zmienić maksymalny rozmiar pliku przekazywania.](/dynamics365/mixed-reality/guides/setup-step-two#change-the-maximum-upload-file-size)

Na koniec należy zainstalować [i skonfigurować rozwiązanie](/dynamics365/mixed-reality/guides/setup-step-two#install-and-configure-the-solution). Na [centrum administracyjne platformy Power Platform](https://admin.powerplatform.microsoft.com/environments)wybierz pozycję **Zasoby** \& gt;  **Aplikacje usługi Dynamics 365,** wybierz pozycję **Przewodniki usługi Dynamics 365** na liście, a następnie wybierz pozycję **Zainstaluj.**  

Aby móc [korzystać z aplikacji,](/dynamics365/mixed-reality/guides/assign-role) musisz dodać rolę zabezpieczeń Przewodniki.

### <a name="create-a-test-guide-on-your-pc-via-authoring"></a>Tworzenie przewodnika testowego na komputerze za pośrednictwem tworzenia

Podczas tworzenia przewodników zawsze rozpoczniesz na komputerze. Tworzenie kroków, wybieranie modeli i sposób zakotwiczenia przewodnika. Następnie zawartość przewodnika zostanie umieszczana w dalszej części w trybie tworzenia na HoloLens urządzeniu. Na potrzeby tego przewodnika sugerujemy wykonanie krótkiego przewodnika testowego z minimalnymi krokami i modelami.

Jeśli chcesz rozpocząć naukę tworzenia dla przewodników, zacznij tutaj od odpowiedzialności [za tworzenie](/dynamics365/mixed-reality/guides/authoring-overview). Aby uzyskać krótkie omówienie, obejrzyj ten krótki film wideo.

<iframe width="560" height="315" src="https://www.youtube.com/embed/EC24dMlAy90" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="optional-kiosk-mode"></a>Opcjonalnie: tryb kiosku

Tryb kiosku to tryb, który umożliwia administratorowi IT skonfigurowanie interfejsu użytkownika menu Start tak, aby wyświetlał tylko jedną aplikację lub wybrane aplikacje. Kiosk można również zastosować do określonych użytkowników, grup lub na poziomie urządzenia. w niektórych przypadkach należy wykluczyć niektórych użytkowników z kiosku, aby nadal zezwalali im na dostęp do zwykłego menu Start.

Tryb kiosku ma wiele różnych zmiennych, zarówno w zakresie, jak i konfiguracjach, które można ustawić, a także metody wdrażania kiosku w HoloLens. Ze względu na wszystkie te zmienne tryb  kiosku zostanie pozostawiony jako opcjonalny dla tego przewodnika i nie zostanie ponownie poprawiony. Jeśli uważasz, że firma musi ograniczyć dostępne aplikacje do użytkowników lub chcesz dowiedzieć się więcej, możesz dowiedzieć się, jak skonfigurować usługę [HoloLens jako kiosk.](/hololens/hololens-kiosk)

## <a name="optional-wdac"></a>Opcjonalnie: WDAC

Funkcja WDAC umożliwia administratorowi IT skonfigurowanie urządzeń tak, aby blokowały uruchamianie aplikacji na urządzeniach. Różni się to od metod ograniczeń dotyczących urządzeń, takich jak tryb kiosku, w którym użytkownik jest prezentowany za pomocą interfejsu użytkownika, który ukrywa aplikacje na urządzeniu, ale nadal można go uruchomić. Podczas implementowania usługi WDAC aplikacje są nadal widoczne na liście Wszystkie aplikacje, ale ta aplikacja i procesy nie mogą być uruchomione przez użytkownika urządzenia.

Aby uzyskać więcej informacji, skorzystaj z tematu Use [WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](/mem/intune/configuration/custom-profile-hololens)(Używanie funkcji WDAC i Windows PowerShell do zezwalania na aplikacje lub blokowania ich na urządzeniach z systemem HoloLens 2 z Microsoft Intune ).

[Windows Defender Kontrola aplikacji — WDAC](/hololens/windows-defender-application-control-wdac)

## <a name="next-step"></a>Następny krok 
> [!div class="nextstepaction"]
> [Wdrożenie połączone z firmą — wdrażanie](hololens2-corp-connected-deploy.md)