---
title: Wytyczne dotyczące infrastruktury dla urządzenia HoloLens
description: Zapoznaj się z wytycznymi dotyczącymi infrastruktury dla urządzeń HoloLens, w tym z obsługą sieci bezprzewodowej, pomocą zdalną i zarządzaniem urządzeniami przenośnymi.
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
ms.openlocfilehash: 4eb55bec56e53de9195ac87e0491eefd91992f3d
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379677"
---
# <a name="configure-your-network-for-hololens"></a>Konfigurowanie sieci dla urządzenia HoloLens

Ta część dokumentu będzie wymagać następujących osób:

1. Administrator sieci z uprawnieniami do zmieniania serwera proxy/zapory
2. Azure Active Directory administratora
3. Administrator Menedżer urządzeń urządzeń przenośnych

## <a name="infrastructure-requirements"></a>Wymagania dotyczące infrastruktury

HoloLens to podstawowe urządzenie przenośne z systemem Windows zintegrowane z platformą Azure.  Działa najlepiej w środowiskach komercyjnych z dostępnością sieci bezprzewodowej (Wi-Fi) i dostępem do usługi firmy Microsoft.

Krytyczne usługi w chmurze obejmują:

- Azure active directory (Azure AD)
- Windows Update (WU)

Klienci komercyjni będą potrzebować infrastruktury zarządzania mobilnością w przedsiębiorstwie (EMM) lub zarządzania urządzeniami przenośnymi (MDM) do zarządzania urządzeniami HoloLens na dużą skalę.  W tym przewodniku [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) jako przykład, chociaż każdy dostawca z pełną obsługą usługi Microsoft Policy może obsługiwać urządzenia HoloLens.  Zapytaj dostawcę zarządzania urządzeniami przenośnymi, czy obsługuje urządzenia HoloLens 2.

Urządzenie HoloLens obsługuje ograniczony zestaw odłączonych od chmury rozwiązań.

### <a name="wireless-network-eap-support"></a>Obsługa protokołu EAP sieci bezprzewodowej

- PEAP-MS-CHAPv2
- PEAP-TLS
- TLS
- TTLS-CHAP
- TTLS-CHAPv2
- TTLS-MS-CHAPv2
- TTLS-PAP
- TTLS-TLS

### <a name="hololens-specific-network-requirements"></a>Wymagania dotyczące sieci specyficzne dla urządzenia HoloLens

Upewnij się, [że ta lista](hololens-offline.md) punktów końcowych jest dozwolona w zaporze sieciowej. Umożliwi to poprawne działanie urządzenia HoloLens.

### <a name="remote-assist-specific-network-requirements"></a>Wymagania dotyczące sieci z określoną usługą Remote Assist

1. Zalecana przepustowość dla optymalnej wydajności usługi Remote Assist to 1,5 Mb/s. Aby uzyskać [dodatkowe informacje, zobacz](https://docs.microsoft.com/MicrosoftTeams/prepare-network) szczegółowe wymagania dotyczące sieci.
**(Pamiętaj, że jeśli nie masz szybkości sieci co najmniej 1,5 Mb/s, usługa Remote Assist nadal będzie działać. Jednak jakość może ulec zaochłoce).**
1. Upewnij się, że te porty i adresy URL są dozwolone w zaporze sieciowej, aby umożliwić działanie aplikacji Microsoft Teams. Bądź na bieżąco z [najnowszą listą portów.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

- Dowiedz się więcej o określonych [wymaganiach dotyczących sieci dla usługi Remote Assist.](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements) 
- Dowiedz się więcej na temat [przygotowywania sieci organizacji do pracy z usługą Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)

### <a name="guides-specific-network-requirements"></a>Przewodniki z określonymi wymaganiami sieciowymi

Przewodniki wymagają tylko dostępu do sieci w celu pobrania i używania aplikacji.

## <a name="azure-active-directory-guidance"></a>Azure Active Directory wskazówki

> [!NOTE]
> Ten krok jest niezbędny tylko wtedy, gdy firma planuje zarządzanie urządzeniem HoloLens.

1. Upewnij się, że masz licencję usługi Azure AD.
Aby uzyskać dodatkowe informacje, zobacz [HoloLens Licenses Requirements](hololens-licenses-requirements.md) (Wymagania dotyczące licencji urządzenia HoloLens).

1. Jeśli planujesz korzystanie z automatycznego rejestrowania, musisz skonfigurować [rejestrację w usłudze Azure AD.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)

1. Upewnij się, że użytkownicy Twojej firmy znajdują się w Azure Active Directory (Azure AD).
Zapoznaj się z [poniższymi instrukcjami](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory) dotyczącymi dodawania użytkowników.

1. Zalecamy, aby użytkownicy, którzy potrzebują podobnych licencji, dodali się do tej samej grupy.
    1. [Tworzenie grupy](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [Dodawanie użytkowników do grup](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. Upewnij się, że użytkownicy (lub grupa użytkowników) firmy mają przypisane niezbędne licencje.
Jeśli musisz przypisać licencje, postępuj zgodnie z tymi [instrukcjami](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).

1. Ten krok należy wykonać tylko wtedy, gdy oczekuje się, że użytkownicy będą rejestrować swoje urządzenia HoloLens/Mobile na Ciebie (dostępne są trzy opcje) Te kroki zapewniają, że użytkownicy w firmie (lub grupa użytkowników) mogą dodawać urządzenia.
    1. **Opcja 1.** Nadaj wszystkim użytkownikom uprawnienia do dołączania urządzeń do usługi Azure AD.
**Zaloguj się do Azure Portal jako administrator**  >  **Azure Active Directory**  >  **Urządzenia**  >  **Ustawienia urządzenia**  >
 **Ustaw dla ustawienia Użytkownicy mogą dołączać urządzenia do usługi Azure AD wartość *Wszystkie***

    1. **Opcja 2.** Nadaj wybranym użytkownikom/grupom uprawnienia do dołączania urządzeń do usługi Azure AD Zaloguj się do usługi Azure Portal jako **administrator** Azure Active Directory Devices Device Settings Set Users may join devices to Azure AD to Selected Image that  >    >  shows Configuration of Azure AD  >    >
 **** 
 ![ Joined Devices](images/azure-ad-image.png)

    1. **Opcja 3.** Możesz zablokować wszystkim użytkownikom możliwość dołączania swoich urządzeń do domeny. Oznacza to, że wszystkie urządzenia muszą zostać zarejestrowane ręcznie.

## <a name="mobile-device-manager-guidance"></a>Wskazówki dotyczące Menedżer urządzeń mobilnych

### <a name="ongoing-device-management"></a>Bieżące zarządzanie urządzeniami

> [!NOTE]
> Ten krok jest niezbędny tylko wtedy, gdy firma planuje zarządzanie urządzeniem HoloLens.

Bieżące zarządzanie urządzeniami będzie zależeć od infrastruktury zarządzania urządzeniami przenośnymi.  Większość z tych funkcji ma tę samą ogólną funkcjonalność, ale interfejs użytkownika może się znacznie różnić.

1. [Dostawcy CSP (dostawcy usług konfiguracji)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) umożliwiają tworzenie i wdrażanie ustawień zarządzania dla urządzeń w sieci. Zobacz listę [CSP urządzenia HoloLens,](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) aby uzyskać informacje.

1. [Zasady zgodności](https://docs.microsoft.com/intune/device-compliance-get-started) to reguły i ustawienia, które urządzenia muszą spełniać, aby zapewnić zgodność w infrastrukturze firmowej. Użyj tych zasad z dostępem warunkowym, aby zablokować dostęp do zasobów firmy dla niezgodnych urządzeń. Na przykład możesz utworzyć zasady wymagające włączenia funkcji Bitlocker.

1. [Utwórz zasady zgodności.](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows)

1. Dostęp warunkowy zezwala na dostęp urządzeń przenośnych i aplikacji mobilnych do zasobów firmy lub odmówi go. Przydatne mogą być dwa dokumenty: [Planowanie wdrożenia urzędu certyfikacji](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) i najlepsze [rozwiązania.](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices)

1. [W tym artykule](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) omówienia narzędzi do zarządzania usługi Intune dla urządzenia HoloLens.

1. [Tworzenie profilu urządzenia](https://docs.microsoft.com/intune/configuration/device-profile-create)

### <a name="manage-updates"></a>Zarządzanie aktualizacjami

Usługa Intune zawiera funkcję o nazwie Pierścienie aktualizacji dla urządzeń Windows 10, w tym HoloLens 2 i HoloLens v1 (z platformą Holographic for Business). Pierścienie aktualizacji obejmują grupę ustawień, które określają, jak i kiedy są instalowane aktualizacje.

Na przykład możesz utworzyć okno obsługi, aby zainstalować aktualizacje lub wybrać opcję ponownego uruchomienia po zainstalowaniu aktualizacji.  Możesz również wstrzymać aktualizacje na czas nieokreślony do momentu, aż wszystko będzie gotowe do aktualizacji.

Przeczytaj więcej na [temat konfigurowania pierścieni aktualizacji za pomocą usługi Intune.](https://docs.microsoft.com/intune/windows-update-for-business-configure)

### <a name="application-management"></a>Zarządzanie aplikacjami

Zarządzanie aplikacjami dla urządzenia HoloLens za pośrednictwem:

1. Sklepie Microsoft  
  Ten Microsoft Store to najlepszy sposób rozpowszechniania i zużywania aplikacji na urządzeniach HoloLens.  W sklepie jest już dostępny doskonały zestaw podstawowych aplikacji dla urządzenia HoloLens. Możesz też [opublikować własny zestaw](https://docs.microsoft.com/windows/uwp/publish/).  
  Wszystkie aplikacje w sklepie są publicznie dostępne dla wszystkich, ale jeśli nie jest to akceptowalne, należy wyewidencjonować Microsoft Store dla Firm.  

1. [Sklep Microsoft dla Firm](https://docs.microsoft.com/microsoft-store/)  
  Microsoft Store dla Firm i Edukacja to magazyn niestandardowy dla środowiska firmowego.  Umożliwia ona korzystanie z aplikacji Microsoft Store wbudowanych w Windows 10 i HoloLens w celu znalezienia, uzyskania i rozpowszechniania aplikacji dla organizacji oraz zarządzania nimi.  Umożliwia również wdrażanie aplikacji specyficznych dla środowiska komercyjnego, ale nie dla świata.

1. Wdrażanie aplikacji i zarządzanie nimi za pośrednictwem usługi Intune lub innego rozwiązania do zarządzania urządzeniami przenośnymi  
  Większość rozwiązań do zarządzania urządzeniami przenośnymi, w tym usługa Intune, umożliwia wdrażanie aplikacji biznesowych bezpośrednio na zestawie zarejestrowanych urządzeń.  Zobacz ten artykuł, aby [zainstalować aplikację usługi Intune.](https://docs.microsoft.com/intune/apps-deploy)

1. _nie jest zalecane_ Portal urządzeń  
  Aplikacje można również instalować na urządzeniach HoloLens bezpośrednio przy użyciu Portal urządzeń z systemem Windows.  Nie jest to zalecane, ponieważ aby można było korzystać z portalu urządzeń, należy włączyć tryb dewelopera.

Przeczytaj więcej na [temat instalowania aplikacji na urządzeniach HoloLens.](https://docs.microsoft.com/hololens/hololens-install-apps)

### <a name="certificates"></a>Certyfikaty

Certyfikaty można rozpowszechniać za pośrednictwem dostawcy rozwiązania MDM. Jeśli firma wymaga certyfikatów, usługa Intune obsługuje certyfikaty PKCS, PFX i SCEP. Ważne jest, aby zrozumieć, który certyfikat jest odpowiedni dla Twojej firmy. Zapoznaj się z [dokumentacją konfiguracji certyfikatów,](https://docs.microsoft.com/intune/protect/certificates-configure) aby ustalić, który certyfikat jest dla Ciebie najlepszy. Jeśli zamierzasz używać certyfikatów do uwierzytelniania urządzenia HoloLens, plik PFX lub SCEP może być dla Ciebie odpowiedni.

Zapoznaj się z poniższymi krokami korzystania z [SCEP.](https://docs.microsoft.com/intune/protect/certificates-profile-scep)

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a>Jak uaktualnić do pakietu Holographics for Business Commercial Suite

> [!NOTE]
> System Windows Holographics for Business (pakiet komercyjny) jest przeznaczony tylko dla urządzeń HoloLens 1. generacji. Profil nie zostanie zastosowany do urządzeń HoloLens 2.

Wskazówki dotyczące uaktualniania do pakietu komercyjnego można znaleźć w dokumentacji [uaktualnienia holograficznego.](https://docs.microsoft.com/intune/configuration/holographic-upgrade)

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a>Jak skonfigurować tryb kiosku przy użyciu Microsoft Intune

1. Zsynchronizuj Microsoft Store z usługą Intune (zobacz następujące [instrukcje).](https://docs.microsoft.com/intune/apps/windows-store-for-business)

1. Sprawdzanie ustawień aplikacji
    1. Zaloguj się do konta Microsoft Store Business
    1. **Zarządzanie > produktami i usługami > Apps and Software > Wybierz aplikację, którą chcesz zsynchronizować z dostępnością w prywatnym sklepie >, > wybierz pozycję "Wszyscy" lub "Określone grupy"**
        >[!NOTE]
        >Jeśli nie widzisz chcieć aplikacji, musisz "pobrać" aplikację, wyszukując aplikację w sklepie. Kliknij pasek "Wyszukaj" w prawym górnym rogu, > wpisz nazwę aplikacji, > kliknij aplikację, a następnie > **pozycję "Pobierz".**
    1. Jeśli nie widzisz aplikacji w usłudze **Intune > Client Apps > Apps,** być może trzeba będzie ponownie [zsynchronizować](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps) aplikacje.

1. [Tworzenie profilu urządzenia dla trybu kiosku](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> Różnych użytkowników można skonfigurować tak, aby mieli różne środowisko trybu kiosku, używając "Azure AD" jako "typu logowania użytkownika". Jednak ta opcja jest dostępna tylko w trybie kiosku z wieloma aplikacjami. Tryb kiosku z wieloma aplikacjami będzie działać tylko z jedną aplikacją, a także z wieloma aplikacjami.

![Obraz, który pokazuje konfigurację trybu kiosku w usłudze Intune](images/aad-kioskmode.png)

W przypadku innych usług MDM zapoznaj się z dokumentacją dostawcy, aby uzyskać instrukcje. Zapoznaj się z instrukcjami dotyczącymi kiosku urządzenia [HoloLens,](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) jeśli chcesz skonfigurować kiosk w usłudze MDM przy użyciu ustawienia niestandardowego i pełnej konfiguracji XML.

## <a name="certificates-and-authentication"></a>Certyfikaty i uwierzytelnianie

Certyfikaty można wdrażać za pośrednictwem rozwiązania MDM (zobacz sekcję "certyfikaty" w [sekcji MDM](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)). Certyfikaty można również wdrażać na urządzeniach HoloLens za pośrednictwem aprowowania pakietów. Aby uzyskać dodatkowe informacje, zobacz [HoloLens Provisioning (Aprowizowanie](hololens-provisioning.md) urządzenia HoloLens).

### <a name="additional-intune-quick-links"></a>Dodatkowe szybkie linki do usługi Intune

1. [Tworzenie profilów:](https://docs.microsoft.com/intune/configuration/device-profile-create) Profile umożliwiają dodawanie i konfigurowanie ustawień, które będą wypychane do urządzeń w organizacji.

