---
title: Wytyczne dotyczące infrastruktury dla HoloLens
description: Poznaj wytyczne dotyczące infrastruktury dla urządzeń HoloLens, w tym obsługę sieci bezprzewodowej, pomoc zdalną i zarządzanie urządzeniami przenośnymi.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e3f87c524ce0f8af05ec8c92877d46facd962fb4
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639288"
---
# <a name="configure-your-network-for-hololens"></a>Konfigurowanie sieci na HoloLens

Ta część dokumentu będzie wymagać następujących osób:

1. Administrator sieci z uprawnieniami do zmieniania serwera proxy/zapory
2. Azure Active Directory Admin
3. Administrator Menedżer urządzeń urządzeń przenośnych

## <a name="infrastructure-requirements"></a>Wymagania dotyczące infrastruktury

HoloLens to podstawowe urządzenie przenośne zintegrowane Windows platformą Azure.  Najlepiej sprawdza się w środowiskach komercyjnych z dostępnością sieci bezprzewodowej (Wi-Fi) i dostępem do usługi firmy Microsoft.

Krytyczne usługi w chmurze obejmują:

- Azure active directory (Azure AD)
- Windows Aktualizacja (WU)

Klienci komercyjni będą potrzebować infrastruktury zarządzania mobilnością w przedsiębiorstwie (EMM) lub zarządzania urządzeniami przenośnymi (MDM) w celu zarządzania HoloLens urządzeniami przenośnymi na dużą skalę.  W tym [przewodniku Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) jako przykład, chociaż każdy dostawca z pełną obsługą zasad firmy Microsoft może obsługiwać HoloLens.  Zapytaj dostawcę zarządzania urządzeniami przenośnymi, czy obsługuje HoloLens 2.

HoloLens obsługuje ograniczony zestaw odłączonych od chmury możliwości.

### <a name="wireless-network-eap-support"></a>Obsługa protokołu EAP sieci bezprzewodowej

- PEAP-MS-CHAPv2
- PEAP-TLS
- TLS
- TTLS-CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS-TLS

### <a name="hololens-specific-network-requirements"></a>HoloLens Określone wymagania dotyczące sieci

Upewnij się, [że ta lista](hololens-offline.md) punktów końcowych jest dozwolona w zaporze sieciowej. Umożliwi to prawidłowe HoloLens funkcji.

### <a name="remote-assist-specific-network-requirements"></a>Wymagania dotyczące sieci z określoną usługą Remote Assist

1. Zalecana przepustowość dla optymalnej wydajności usługi Remote Assist to 1,5 Mb/s. Aby uzyskać [dodatkowe informacje, zobacz](/MicrosoftTeams/prepare-network) szczegółowe wymagania dotyczące sieci.
**(Pamiętaj, że jeśli nie masz szybkości sieci co najmniej 1,5 Mb/s, usługa Remote Assist nadal będzie działać. Jednak jakość może ulec zaochłoce).**
1. Upewnij się, że te porty i adresy URL są dozwolone w zaporze sieciowej, aby umożliwić Microsoft Teams funkcji. Bądź na bieżąco z [najnowszą listą portów.](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

- Dowiedz się więcej o określonych [wymaganiach dotyczących sieci dla usługi Remote Assist.](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements) 
- Dowiedz się więcej o [tym, jak przygotować sieć organizacji do](/MicrosoftTeams/prepare-network) Microsoft Teams

### <a name="guides-specific-network-requirements"></a>Przewodniki z określonymi wymaganiami sieciowymi

Przewodniki wymagają tylko dostępu do sieci w celu pobrania i używania aplikacji.

## <a name="azure-active-directory-guidance"></a>Azure Active Directory Wskazówki

> [!NOTE]
> Ten krok jest niezbędny tylko wtedy, gdy firma planuje zarządzanie HoloLens.

1. Upewnij się, że masz licencję usługi Azure AD.
Aby [uzyskać dodatkowe HoloLens, zapoznaj się](hololens-licenses-requirements.md) z wymaganiami licencyjnymi.

1. Jeśli planujesz korzystanie z automatycznego rejestrowania, musisz skonfigurować [rejestrację w usłudze Azure AD.](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)

1. Upewnij się, że użytkownicy Twojej firmy znajdują się w Azure Active Directory (Azure AD).
Zapoznaj się z [poniższymi instrukcjami](/azure/active-directory/fundamentals/add-users-azure-active-directory) dotyczącymi dodawania użytkowników.

1. Zalecamy, aby użytkownicy, którzy potrzebują podobnych licencji, dodali się do tej samej grupy.
    1. [Tworzenie grupy](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [Dodawanie użytkowników do grup](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. Upewnij się, że użytkownicy (lub grupa użytkowników) firmy mają przypisane niezbędne licencje.
Jeśli musisz przypisać licencje, postępuj zgodnie z tymi [instrukcjami](/azure/active-directory/fundamentals/license-users-groups).

1. Ten krok należy wykonać tylko wtedy, gdy użytkownicy mają zarejestrować swoje urządzenie HoloLens/urządzenie przenośne (dostępne są trzy opcje) Te kroki zapewniają, że użytkownicy w firmie (lub grupa użytkowników) mogą dodawać urządzenia.
    1. **Opcja 1.** Nadaj wszystkim użytkownikom uprawnienia do dołączania urządzeń do usługi Azure AD.
**Zaloguj się do Azure Portal jako administrator**  >  **Azure Active Directory**  >  **Urządzenia**  >  **Ustawienia Ustawienia**  >
 **Ustaw dla ustawienia Użytkownicy mogą dołączać urządzenia do usługi Azure AD wartość *Wszystkie***

    1. **Opcja 2.** Nadaj wybranym użytkownikom/grupom uprawnienia do dołączania urządzeń do usługi Azure AD Zaloguj się do usługi **Azure Portal** jako administrator urządzenia Azure Active Directory  >    >  **Urządzenia**  >  **Ustawienia**  >
 **** 
 ![ Ustaw, że użytkownicy mogą dołączać urządzenia do usługi Azure AD do wybranego obrazu wyświetlającego konfigurację urządzeń przyłączone do usługi Azure AD](images/azure-ad-image.png)

    1. **Opcja 3.** Możesz zablokować wszystkim użytkownikom możliwość dołączania swoich urządzeń do domeny. Oznacza to, że wszystkie urządzenia muszą zostać zarejestrowane ręcznie.

## <a name="mobile-device-manager-guidance"></a>Wskazówki dotyczące Menedżer urządzeń mobilnych

### <a name="ongoing-device-management"></a>Bieżące zarządzanie urządzeniami

> [!NOTE]
> Ten krok jest niezbędny tylko wtedy, gdy firma planuje zarządzanie HoloLens.

Bieżące zarządzanie urządzeniami będzie zależeć od infrastruktury zarządzania urządzeniami przenośnymi.  Większość z tych funkcji ma tę samą ogólną funkcjonalność, ale interfejs użytkownika może się znacznie różnić.

1. [Dostawcy CSP (dostawcy usług konfiguracji)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) umożliwiają tworzenie i wdrażanie ustawień zarządzania dla urządzeń w sieci. Zapoznaj się [z listą HoloLens CSP,](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) aby uzyskać informacje.

1. [Zasady zgodności](/intune/device-compliance-get-started) to reguły i ustawienia, które urządzenia muszą spełniać, aby zapewnić zgodność w infrastrukturze firmowej. Użyj tych zasad z dostępem warunkowym, aby zablokować dostęp do zasobów firmy dla niezgodnych urządzeń. Na przykład możesz utworzyć zasady wymagające włączenia funkcji Bitlocker.

1. [Utwórz zasady zgodności.](/intune/protect/compliance-policy-create-windows)

1. Dostęp warunkowy zezwala na dostęp urządzeń przenośnych i aplikacji mobilnych do zasobów firmy lub odmówi go. Przydatne mogą być dwa dokumenty: [Planowanie wdrożenia urzędu certyfikacji](/azure/active-directory/conditional-access/plan-conditional-access) i najlepsze [rozwiązania.](/azure/active-directory/conditional-access/best-practices)

1. [W tym](/intune/fundamentals/windows-holographic-for-business) artykule omówienia narzędzi do zarządzania usługą Intune dla HoloLens.

1. [Tworzenie profilu urządzenia](/intune/configuration/device-profile-create)

### <a name="manage-updates"></a>Zarządzanie aktualizacjami

Usługa Intune zawiera funkcję o nazwie Pierścienie aktualizacji dla urządzeń Windows 10, w tym HoloLens 2 i HoloLens v1 (z platformą Holographic for Business). Pierścienie aktualizacji obejmują grupę ustawień, które określają, jak i kiedy są instalowane aktualizacje.

Na przykład możesz utworzyć okno obsługi, aby zainstalować aktualizacje lub wybrać opcję ponownego uruchomienia po zainstalowaniu aktualizacji.  Możesz również wstrzymać aktualizacje na czas nieokreślony do momentu, aż wszystko będzie gotowe do aktualizacji.

Przeczytaj więcej na [temat konfigurowania pierścieni aktualizacji za pomocą usługi Intune.](/intune/windows-update-for-business-configure)

### <a name="application-management"></a>Zarządzanie aplikacjami

Zarządzanie HoloLens aplikacjami za pomocą:

1. Sklepie Microsoft  
  Ten Microsoft Store to najlepszy sposób rozpowszechniania i zużywania aplikacji na HoloLens.  Istnieje doskonały zestaw podstawowych aplikacji HoloLens już dostępnych w sklepie lub możesz [opublikować własny.](/windows/uwp/publish/)  
  Wszystkie aplikacje w sklepie są publicznie dostępne dla wszystkich, ale jeśli nie jest to akceptowalne, należy wyewidencjonować Microsoft Store dla Firm.  

1. [Sklep Microsoft dla Firm](/microsoft-store/)  
  Microsoft Store dla Firm education to magazyn niestandardowy dla środowiska firmowego.  Umożliwia ona korzystanie z Microsoft Store wbudowanych Windows 10 i HoloLens do znajdowanie, pozyskiwanie i rozpowszechnianie aplikacji dla organizacji oraz zarządzanie nimi.  Umożliwia również wdrażanie aplikacji specyficznych dla środowiska komercyjnego, ale nie dla świata.

1. Wdrażanie aplikacji i zarządzanie nimi za pośrednictwem usługi Intune lub innego rozwiązania do zarządzania urządzeniami przenośnymi  
  Większość rozwiązań do zarządzania urządzeniami przenośnymi, w tym usługa Intune, umożliwia wdrażanie aplikacji biznesowych bezpośrednio na zestawie zarejestrowanych urządzeń.  Zobacz ten artykuł, aby [zainstalować aplikację usługi Intune.](/intune/apps-deploy)

1. _nie jest zalecane_ Portal urządzeń  
  Aplikacje można również instalować na HoloLens bezpośrednio przy użyciu Windows Portal urządzeń.  Nie jest to zalecane, ponieważ aby można było korzystać z portalu urządzeń, należy włączyć tryb dewelopera.

Przeczytaj więcej na [temat instalowania aplikacji na HoloLens](hololens-install-apps.md).

### <a name="certificates"></a>Certyfikaty

Certyfikaty można rozpowszechniać za pośrednictwem dostawcy rozwiązania MDM. Jeśli firma wymaga certyfikatów, usługa Intune obsługuje certyfikaty PKCS, PFX i SCEP. Ważne jest, aby zrozumieć, który certyfikat jest odpowiedni dla Twojej firmy. Zapoznaj się z [dokumentacją konfiguracji certyfikatów,](/intune/protect/certificates-configure) aby ustalić, który certyfikat jest dla Ciebie najlepszy. Jeśli zamierzasz używać certyfikatów do uwierzytelniania HoloLens, plik PFX lub SCEP może być odpowiedni dla Ciebie.

Zapoznaj się z poniższymi krokami korzystania z [SCEP.](/intune/protect/certificates-profile-scep)

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a>Jak uaktualnić do pakietu Holographics for Business Commercial Suite

> [!NOTE]
> Windows Holographics for Business (pakiet komercyjny) jest przeznaczony tylko dla HoloLens pierwszej generacji. Profil nie zostanie zastosowany do urządzeń HoloLens 2.

Wskazówki dotyczące uaktualniania do pakietu komercyjnego można znaleźć w dokumentacji [uaktualnienia holograficznego.](/intune/configuration/holographic-upgrade)

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a>Jak skonfigurować tryb kiosku przy użyciu Microsoft Intune

1. Synchronizacja Microsoft Store z usługą Intune (zobacz następujące [instrukcje).](/intune/apps/windows-store-for-business)

1. Sprawdzanie ustawień aplikacji
    1. Zaloguj się do konta Microsoft Store Business
    1. **Zarządzanie > Produktami i usługami > Apps and Software > Wybierz aplikację, którą chcesz zsynchronizować > dostępność sklepu prywatnego > wybierz pozycję "Wszyscy" lub "Określone grupy"**
        >[!NOTE]
        >Jeśli nie widzisz chętnych aplikacji, musisz "pobrać" aplikację, wyszukując aplikację w sklepie. **Kliknij pasek "Wyszukaj"** w prawym górnym rogu, > wpisz nazwę aplikacji, > kliknij aplikację, > wybierz pozycję "Pobierz".
    1. Jeśli nie widzisz aplikacji w usłudze **Intune > Client Apps > Apps,** może być ponownie trzeba [zsynchronizować](/intune/apps/windows-store-for-business#synchronize-apps) aplikacje.

1. [Tworzenie profilu urządzenia dla trybu kiosku](/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> Różnych użytkowników można skonfigurować tak, aby mieli różne środowisko trybu kiosku, używając "Azure AD" jako "typu logowania użytkownika". Jednak ta opcja jest dostępna tylko w trybie kiosku z wieloma aplikacjami. Tryb kiosku z wieloma aplikacjami będzie działać tylko z jedną aplikacją, a także z wieloma aplikacjami.

![Obraz z konfiguracją trybu kiosku w usłudze Intune](images/aad-kioskmode.png)

W przypadku innych usług MDM zapoznaj się z dokumentacją dostawcy, aby uzyskać instrukcje. Zapoznaj się z [HoloLens kiosku,](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) jeśli chcesz użyć ustawienia niestandardowego i pełnej konfiguracji XML w celu skonfigurowania kiosku w usłudze MDM.

## <a name="certificates-and-authentication"></a>Certyfikaty i uwierzytelnianie

Certyfikaty można wdrażać za pośrednictwem rozwiązania MDM (zobacz sekcję "certyfikaty" w [sekcji MDM).](hololens-commercial-infrastructure.md#mobile-device-manager-guidance) Certyfikaty można również wdrażać na HoloLens przez aprowizowanie pakietów. Aby uzyskać dodatkowe informacje, zobacz [HoloLens Provisioning](hololens-provisioning.md) (Aprowizowanie).

### <a name="additional-intune-quick-links"></a>Dodatkowe szybkie linki do usługi Intune

1. [Tworzenie profilów:](/intune/configuration/device-profile-create) Profile umożliwiają dodawanie i konfigurowanie ustawień, które będą wypychane do urządzeń w organizacji.

