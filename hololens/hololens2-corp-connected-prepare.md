---
title: Przewodnik wdrażania — urządzenie HoloLens 2 połączone z firmą z usługą Dynamics 365 — przygotowanie
description: Dowiedz się, jak przygotować się do rejestracji urządzeń HoloLens 2 za pośrednictwem firmowej sieci połączonej za pomocą przewodników usługi Dynamics 365.
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
ms.openlocfilehash: 2ab24aeac371b8d4a17d6121c3adf317cac7daf1
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378343"
---
# <a name="prepare---corporate-connected-guide"></a>Przygotowanie — przewodnik po połączeniu firmowym
## <a name="infrastructure-essentials"></a>Podstawowe informacje o infrastrukturze
Zarówno w scenariuszach wdrażania osobistego, jak i firmowego system mobile Zarządzanie urządzeniami (MDM) jest podstawową infrastrukturą wymaganą do wdrażania urządzeń Windows 10 i zarządzania nimi, szczególnie holoLens 2. Subskrypcja [Azure AD — wersja Premium jest](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium) zalecana jako dostawca tożsamości i wymagana do obsługi niektórych funkcji. 

> [!NOTE]
> Chociaż urządzenie HoloLens 2 jest wdrażane i zarządzane jak urządzenie przenośne, jest ono zwykle używane jako urządzenie udostępnione wielu użytkownikom.

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD to oparta na chmurze usługa katalogowa, która zapewnia zarządzanie tożsamościami i dostępem. Organizacje korzystające z usługi Microsoft Office 365 lub Intune już używają usługi Azure AD, która ma trzy wersje: Bezpłatna, Premium P1 i Premium P2 (zobacz [Azure Active Directory wersji](https://azure.microsoft.com/documentation/articles/active-directory-editions)). Wszystkie wersje obsługują rejestrację urządzeń w usłudze Azure AD, ale do włączenia automatycznej rejestracji w usłudze MDM, której będziemy używać w dalszej części tego przewodnika, jest wymagana wersja Premium P1.
> [!Important]
> Bardzo ważne jest, aby mieć usługę Azure AD, ponieważ urządzenia HoloLens nie obsługują lokalnego dołączania do usługi AD. Jeśli nie masz jeszcze usługi Azure AD, postępuj zgodnie z instrukcjami, aby rozpocząć pracę i utworzyć nową dzierżawę w [usłudze Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## <a name="identity-management"></a>Zarządzanie tożsamością
W tym przewodniku używana [tożsamość](https://docs.microsoft.com/hololens/hololens-identity) będzie kontami usługi Azure AD. Istnieje kilka korzyści dla kont usługi Azure AD, takich jak:
- Pracownicy używają konta usługi Azure AD do rejestrowania urządzenia w usłudze Azure AD i mogą automatycznie rejestrować je w rozwiązaniu MDM organizacji (Azure AD+MDM — wymaga Azure AD — wersja Premium [subskrypcji).](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-get-started-premium)
- Konta usługi Azure AD mają dodatkowe [opcje uwierzytelniania za](https://docs.microsoft.com/hololens/hololens-identity) [pośrednictwem Windows Hello dla firm](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). Oprócz logowania irysów użytkownicy mogą logować się z innego urządzenia lub używać kluczy zabezpieczeń FIDO.

> [!WARNING] 
> Pracownicy mogą używać tylko jednego konta do inicjowania urządzenia, więc konieczne jest, aby twoja organizacja kontroluje, które konto **jest włączone w pierwszej kolejności.** Wybrane konto określi, kto kontroluje urządzenie i wpływa na możliwości zarządzania.

## <a name="mobile-device-management"></a>Zarządzanie urządzeniami przenośnymi
Microsoft Intune, część Enterprise Mobility + Security, to oparty na chmurze system MDM, który zarządza urządzeniami połączonymi z dzierżawą. Podobnie jak usługa Office 365, usługa Intune używa usługi Azure AD do zarządzania tożsamościami, więc pracownicy używają tych samych poświadczeń do rejestrowania urządzeń w usłudze Intune, których używają do logowania się do usługi Office 365. Usługa Intune obsługuje również urządzenia z innymi systemami operacyjnymi, takimi jak iOS i Android, w celu zapewnienia pełnego rozwiązania MDM. Na potrzeby tego przewodnika skupimy się na używaniu usługi Intune do włączania wdrożenia w sieci wewnętrznej przy użyciu urządzenia HoloLens 2.
> [!Important] 
> Ważne jest, aby mieć aplikacje mobilne Zarządzanie urządzeniami. Jeśli jeszcze go nie masz, postępuj zgodnie z tym przewodnikiem i wprowadzeniem do usługi Intune.

> [!Important]
> Aby można było korzystać z przewodników, wymagane jest konto usługi Azure AD.

> [!Note] 
> Wiele systemów MDM obsługuje Windows 10 i większość scenariuszy wdrażania urządzeń osobistych i firmowych. Dostawcy rozwiązań MDM, którzy obsługują Windows 10 Holographic to między innymi AirWatch, MobileIron. Większość wiodących w branży dostawców rozwiązań MDM obsługuje już integrację z usługą Azure AD. Najbardziej aktualną listę dostawców rozwiązań MDM, którzy obsługują usługę Azure AD, można znaleźć w [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps).

## <a name="network-access"></a>Dostęp sieciowy 
Dynamics 365 Guides to aplikacja oparta na chmurze. Jeśli administrator sieci ma listę zatwierdzeń, może być konieczne dodanie adresów IP i/lub punktów końcowych, które są wymagane do nawiązania połączenia z serwerami usługi Dynamics 365. [Dowiedz się więcej o odblokowywaniu adresów IP i adresów URL.](https://docs.microsoft.com/power-platform/admin/online-requirements#ip-addresses-and-urls)

## <a name="certificates"></a>Certyfikaty
Certyfikaty pomagają zwiększyć bezpieczeństwo, zapewniając uwierzytelnianie konta, Wi-Fi uwierzytelnianie, szyfrowanie sieci VPN i szyfrowanie SSL zawartości internetowej. Mimo że administratorzy mogą zarządzać certyfikatami na urządzeniach ręcznie za pomocą pakietów aprowizacji, najlepszym rozwiązaniem jest użycie systemu MDM do zarządzania tymi certyfikatami w całym ich cyklu życia — od rejestracji po odnawianie i odwoływanie. 

System MDM może automatycznie wdrożyć te certyfikaty w magazynach certyfikatów urządzeń po ich zarejestrowaniu (o ile system MDM obsługuje standard **kryptograficzny prosty protokół rejestrowania certyfikatów (SCEP)** lub public **key cryptography Standards #12 (PKCS #12).** [Dowiedz się więcej o typach certyfikatów i profilach, których używasz z Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/certificates-configure). Rozwiązanie MDM może również wysyłać zapytania o zarejestrowane certyfikaty klienta i usuwać je lub wyzwalać nowe żądanie rejestracji przed wygaśnięciem bieżącego certyfikatu.
 
Jeśli twoje systemy MDM zostały już skonfigurowane pod celu skonfigurowania certyfikatów, odwołuj się do dokumentacji Prepare [certificates and network profiles for HoloLens 2](https://docs.microsoft.com/hololens/hololens-certificates-network) (Przygotowywanie certyfikatów i profilów sieciowych dla urządzenia HoloLens 2), aby rozpocząć wdrażanie certyfikatów i profilów dla urządzeń HoloLens 2.

## <a name="scep"></a>SCEP

Następujące usługi są wymagane do wdrożenia SCEP, z wyjątkiem serwera web serwer proxy aplikacji Server.
- [Urząd certyfikacji](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [Rola serwera usługi NDES](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Łącznik usługi Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

Należy również opublikować adres URL usługi NDES poza siecią firmową przy użyciu serwera proxy aplikacji usługi [Azure AD lub serwera Dostęp w sieci Web proxy.](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-add-on-premises-application) Możesz również użyć innego wybranego zwrotnego serwera proxy.

![Przepływ danych SCEP](./images/hololens2-scep-info-flow.png)

Jeśli twoja sieć nie obsługuje jeszcze SCEP lub nie masz pewności, czy sieć została prawidłowo skonfigurowana do obsługi SCEP za pomocą usługi Intune, odwołuj się do konfigurowania infrastruktury do obsługi SCEP przy użyciu usługi [Intune.](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure)

Jeśli Twoja infrastruktura obsługuje już SCEP, [](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-certificate-profiles) musisz utworzyć profil dla każdego certyfikatu SCEP, który będzie używać urządzenia HoloLens 2. [](https://docs.microsoft.com/mem/intune/protect/certificates-profile-scep) Jeśli masz problemy z profilem SCEP, użyj narzędzia Troubleshoot [use of SCEP certificate profiles to provision certificates with Microsoft Intune](https://docs.microsoft.com/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles).

## <a name="pkcs"></a>PKCS
Usługa Intune obsługuje również korzystanie z certyfikatów par kluczy prywatnych i publicznych (PKCS). Aby [uzyskać więcej informacji,](https://docs.microsoft.com/mem/intune/protect/certificates-pfx-configure) skorzystaj z informacji na temat używania certyfikatów Microsoft Intune klucza prywatnego i publicznego w programie .

## <a name="proxy"></a>Serwer proxy
Większość firmowych sieci intranet korzysta z serwera proxy do zarządzania ruchem zewnętrznym. Za pomocą urządzenia HoloLens 2 można skonfigurować serwer proxy dla połączeń Ethernet, Wi-Fi i VPN.

Istnieje kilka różnych typów serwera proxy i sposobów konfigurowania serwera proxy. Na potrzeby tego przewodnika wybieramy serwer **proxy sieci Wi-Fi,** ustawiamy go za pomocą adresu URL PAC i wdrażamy za pośrednictwem rozwiązania MDM. Jest to związane z zaletami automatycznego wdrażania za pośrednictwem rozwiązania MDM, możliwością aktualizowania pliku PAC zamiast używania konfiguracji serwer:port, a na koniec z użyciem serwera proxy usługi Wi-Fi w celu skonfigurowania serwera proxy do stosowania tylko do pojedynczego połączenia Wi-Fi, dzięki czemu urządzenia mogą być nadal używane, jeśli są połączone w innej lokalizacji. 


Aby uzyskać więcej informacji na temat ustawień serwera proxy dla Windows 10, zobacz Tworzenie profilu Wi-Fi dla urządzeń w [usłudze Microsoft Intune — Azure.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure)

## <a name="line-of-business-apps"></a>Aplikacje biznesowe 
Chociaż kilka aplikacji można zainstalować za pośrednictwem Microsoft Store, prawdopodobnie masz własną aplikację niestandardową utworzoną specjalnie do użycia w rzeczywistości mieszanej. Te aplikacje niestandardowe dystrybuowane w całej organizacji dla Twojej firmy są nazywane aplikacjami biznesowymi (LOB).
  
Istnieje wiele sposobów wdrażania aplikacji na urządzeniach HoloLens 2. Aplikacje można wdrażać bezpośrednio za pośrednictwem rozwiązania MDM, Microsoft Store dla Firm (MSfB) lub ładować bezpośrednio za pośrednictwem pakietu aprowiwizowania. Na potrzeby tego przewodnika będziemy wdrażać aplikacje za pośrednictwem rozwiązania MDM, korzystając z wymaganej instalacji aplikacji. Umożliwi to automatyczne pobranie aplikacji LOB na urządzenia HoloLens po zakończeniu rejestracji.

Dla osób, które nie mają własnych aplikacji LOB, udostępnimy przykładową aplikację do testowania tego przepływu wdrażania. Ta aplikacja będzie aplikacją [przykładów zestawu mrtk](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) i została już wstępnie sprebugowana i spakowana w celu przetestowania weryfikacji koncepcji.
 
Więcej szczegółów dotyczących wdrażania aplikacji można znaleźć na stronie [Zarządzanie aplikacją: Omówienie.](https://docs.microsoft.com/hololens/app-deploy-overview)

> [!NOTE]
> Urządzenie HoloLens 2 obsługuje tylko uruchamianie aplikacji ARM64 platformy UWP.

## <a name="guides-playbook"></a>Podręcznik przewodników
Przewodniki wykorzystują środowisko Microsoft Dataverse jako magazyn danych dla aplikacji Przewodniki. Ważne jest, aby zrozumieć, jak środowisko Dataverse współdziała z aplikacjami przewodników i dzierżawą. W tym przewodniku nie opisano sposobu zarządzania obiektem dataverse, ale zapoznaj się z podstawowymi pojęciami wdrażania przewodników usługi [Dynamics 365 — Dynamics 365 Mixed Reality.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/admin-deployment-playbook)

## <a name="next-step"></a>Następny krok 
> [!div class="nextstepaction"]
> [Wdrożenie połączone z firmą — konfigurowanie](hololens2-corp-connected-configure.md)