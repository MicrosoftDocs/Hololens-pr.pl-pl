---
title: Przewodnik wdrażania — przewodniki dotyczące HoloLens 2 połączone z usługą Dynamics 365 — przygotowanie
description: Dowiedz się, jak przygotować się do rejestracji HoloLens 2 urządzeń za pośrednictwem firmowej sieci połączonej za pomocą przewodników usługi Dynamics 365.
keywords: HoloLens, zarządzanie, połączenia firmowe, przewodniki usługi Dynamics 365, AAD, Azure AD, MDM, Mobile Zarządzanie urządzeniami
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
ms.openlocfilehash: 5d8fc2eb0a8dafaae0e1b222b7451877975cf90b
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190212"
---
# <a name="prepare---corporate-connected-guide"></a>Przygotowanie — przewodnik po połączeniu firmowym
## <a name="infrastructure-essentials"></a>Podstawowe informacje o infrastrukturze
Zarówno w przypadku scenariuszy wdrażania osobistego, jak i firmowego system zarządzania urządzeniami przenośnymi (MDM, Mobile Zarządzanie urządzeniami) jest podstawową infrastrukturą wymaganą do wdrażania urządzeń Windows 10 i zarządzania nimi, szczególnie w wersji HoloLens 2. Subskrypcja [Azure AD — wersja Premium jest](/azure/active-directory/fundamentals/active-directory-get-started-premium) zalecana jako dostawca tożsamości i wymagana **do** obsługi niektórych funkcji.

> [!NOTE]
> Mimo że HoloLens 2 jest wdrażany i zarządzany jak urządzenie przenośne, jest on zwykle używany jako urządzenie udostępnione wielu użytkownikom.

## <a name="azure-active-directory"></a>Azure Active Directory
Azure AD to oparta na chmurze usługa katalogowa, która zapewnia zarządzanie tożsamościami i dostępem. Organizacje używające usługi Microsoft Office 365 lub Intune już używają usługi Azure AD, która ma trzy wersje: Bezpłatna, Premium P1 i Premium P2 (zobacz [Azure Active Directory wersje).](https://azure.microsoft.com/documentation/articles/active-directory-editions) Wszystkie wersje obsługują rejestrację urządzeń w usłudze Azure AD, ale Premium P1 jest wymagana do włączenia automatycznej rejestracji w usłudze MDM, której będziemy używać w dalszej części tego przewodnika.
> [!Important]
> Bardzo ważne jest, aby usługa Azure AD była HoloLens, które nie obsługują dołączania do lokalnej usługi AD. Jeśli nie masz jeszcze usługi Azure AD, postępuj zgodnie z instrukcjami, aby rozpocząć pracę i utworzyć nową dzierżawę w [usłudze Azure Active Directory](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## <a name="identity-management"></a>Zarządzanie tożsamością
W tym przewodniku używana [tożsamość](/hololens/hololens-identity) będzie kontami usługi Azure AD. Istnieje kilka korzyści dla kont usługi Azure AD, takich jak:

- Pracownicy rejestrują urządzenie w usłudze Azure AD za pomocą konta usługi Azure AD i mogą automatycznie rejestrować je w rozwiązaniu MDM organizacji (Azure AD+MDM — wymaga subskrypcji [Azure AD — wersja Premium ).](/azure/active-directory/fundamentals/active-directory-get-started-premium)
- Konta usługi Azure AD mają dodatkowe [opcje uwierzytelniania za](/hololens/hololens-identity) [pośrednictwem Windows Hello for Business.](/windows/security/identity-protection/hello-for-business/hello-identity-verification) Oprócz logowania irysów użytkownicy mogą logować się z innego urządzenia lub używać kluczy zabezpieczeń FIDO.

> [!WARNING] 
> Pracownicy mogą używać tylko jednego konta do zainicjowania urządzenia, dlatego konieczne jest, aby organizacja kontroluje, które **konto jest włączone w pierwszej kolejności.** Wybrane konto określi, kto kontroluje urządzenie i wpływa na możliwości zarządzania.

## <a name="mobile-device-management"></a>Zarządzanie urządzeniami przenośnymi
Microsoft Intune, część usługi Enterprise Mobility + Security, to oparty na chmurze system MDM, który zarządza urządzeniami połączonymi z dzierżawą. Podobnie Office 365 usługa Intune używa usługi Azure AD do zarządzania tożsamościami, więc pracownicy używają tych samych poświadczeń do rejestrowania urządzeń w usłudze Intune, których używają do logowania się do Office 365. Usługa Intune obsługuje również urządzenia z innymi systemami operacyjnymi, takimi jak iOS i Android, w celu zapewnienia pełnego rozwiązania MDM. Na potrzeby tego przewodnika skupimy się na używaniu usługi Intune do włączania wdrożenia w sieci wewnętrznej przy użyciu usługi HoloLens 2.
> [!Important] 
> Ważne jest, aby mieć usługę Mobile Zarządzanie urządzeniami. Jeśli jeszcze jej nie masz, postępuj zgodnie z tym przewodnikiem i tematem Rozpoczynanie pracy z usługą Intune.

> [!Important]
> Aby można było korzystać z przewodników, wymagane jest konto usługi Azure AD.

> [!Note] 
> Wiele systemów MDM obsługuje Windows 10 a większość obsługuje scenariusze wdrażania urządzeń osobistych i firmowych. Dostawcy rozwiązań MDM, którzy obsługują Windows 10 Holographic to: AirWatch, MobileIron i inni. Większość wiodących w branży dostawców rozwiązań MDM obsługuje już integrację z usługą Azure AD. Najbardziej aktualną listę dostawców rozwiązań MDM, którzy obsługują usługę Azure AD, można znaleźć w [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/apps/category/azure-active-directory-apps).

## <a name="network-access"></a>Dostęp sieciowy 
Dynamics 365 Guides to aplikacja oparta na chmurze. Jeśli administrator sieci ma listę zatwierdzeń, może być konieczne dodanie adresów IP i/lub punktów końcowych, które są wymagane do nawiązania połączenia z serwerami usługi Dynamics 365. [Dowiedz się więcej o odblokowywaniu adresów IP i adresów URL.](/power-platform/admin/online-requirements#ip-addresses-and-urls)

## <a name="certificates"></a>Certyfikaty
Certyfikaty pomagają zwiększyć bezpieczeństwo, zapewniając uwierzytelnianie konta, uwierzytelnianie Wi-Fi, szyfrowanie sieci VPN i szyfrowanie SSL zawartości internetowej. Mimo że administratorzy mogą zarządzać certyfikatami na urządzeniach ręcznie za pomocą pakietów aprowizacji, najlepszym rozwiązaniem jest użycie systemu MDM do zarządzania tymi certyfikatami przez cały cykl ich życia — od rejestracji po odnawianie i odwoływanie. 

System MDM może automatycznie wdrożyć te certyfikaty w magazynach certyfikatów urządzeń po ich zarejestrowaniu (o ile system MDM obsługuje standard **prosty protokół rejestrowania certyfikatów (SCEP)** lub **Public Key Cryptography Standards #12 (PKCS #12)**). [Dowiedz się więcej o typach certyfikatów i profilach, których używasz z Microsoft Intune](/mem/intune/protect/certificates-configure). Rozwiązanie MDM może również wysyłać zapytania o zarejestrowane certyfikaty klienta i usuwać je lub wyzwalać nowe żądanie rejestracji przed wygaśnięciem bieżącego certyfikatu.

Jeśli twoje systemy MDM są już skonfigurowane dla certyfikatów, odwołuj się do dokumentacji Prepare [certificates and network profiles for HoloLens 2](/hololens/hololens-certificates-network) (Przygotowanie certyfikatów i profilów sieciowych dla programu HoloLens 2), aby rozpocząć wdrażanie certyfikatów i profilów dla urządzeń z systemem HoloLens 2.

## <a name="scep"></a>SCEP

Następujące usługi są wymagane do wdrożenia SCEP, z wyjątkiem serwera serwer proxy aplikacji Web.

- [Urząd certyfikacji](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj125375(v=ws.11))
- [Rola serwera usługi NDES](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11))
- [Łącznik usługi Microsoft Intune](/mem/intune/protect/certificates-scep-configure#install-the-microsoft-intune-connector)

Należy również opublikować adres URL usługi NDES poza siecią firmową przy użyciu serwera proxy aplikacji usługi [Azure AD lub serwera Dostęp w sieci Web proxy.](/azure/active-directory/manage-apps/application-proxy-add-on-premises-application) Możesz również użyć innego wybranego zwrotnego serwera proxy.

![Przepływ danych SCEP.](./images/hololens2-scep-info-flow.png)

Jeśli Twoja sieć nie obsługuje jeszcze SCEP lub nie masz pewności, czy sieć została prawidłowo skonfigurowana pod adres SCEP przy użyciu usługi Intune, odwołuj się do konfigurowania infrastruktury do obsługi SCEP w usłudze [Intune.](/mem/intune/protect/certificates-scep-configure)

Jeśli twoja infrastruktura już obsługuje profil [](/mem/intune/protect/certificates-profile-scep) SCEP, musisz utworzyć profil dla każdego certyfikatu SCEP, który będzie HoloLens 2. [](/mem/configmgr/protect/deploy-use/create-certificate-profiles) Jeśli masz problemy z profilem SCEP, użyj narzędzia Troubleshoot [use of SCEP certificate profiles to provision certificates with Microsoft Intune](/troubleshoot/mem/intune/troubleshoot-scep-certificate-profiles).

## <a name="pkcs"></a>PKCS
Usługa Intune obsługuje również korzystanie z certyfikatów pary kluczy prywatnych i publicznych (PKCS). Aby [uzyskać więcej informacji,](/mem/intune/protect/certificates-pfx-configure) skorzystaj z Microsoft Intune certyfikatów kluczy prywatnych i publicznych w programie .

## <a name="proxy"></a>Serwer proxy
Większość firmowych sieci intranetowych korzysta z serwera proxy do zarządzania ruchem zewnętrznym. Za HoloLens 2 można skonfigurować serwer proxy dla połączeń ethernet, Wi-Fi sieci VPN.

Istnieje kilka różnych typów serwera proxy i sposobów konfigurowania serwera proxy. Na potrzeby tego przewodnika wybieramy serwer **proxy sieci Wi-Fi,** ustawiamy go za pośrednictwem adresu URL PAC i wdrażamy za pośrednictwem rozwiązania MDM. Jest to związane z zaletami automatycznego wdrażania za pośrednictwem zarządzania urządzeniami przenośnymi, aktualizowania pliku PAC zamiast używania konfiguracji serwer:port, a na koniec używania serwera proxy usługi Wi-Fi do konfigurowania serwera proxy do stosowania tylko do jednego połączenia Wi-Fi, co pozwala nadal używać urządzeń w przypadku połączenia w innej lokalizacji.

Aby uzyskać więcej informacji na temat ustawień serwera proxy dla serwera Windows 10, zobacz Create a Wi-Fi profile for devices in Microsoft Intune - Azure (Tworzenie profilu Wi-Fi dla urządzeń w [usłudze Microsoft Intune — Azure).](/mem/intune/configuration/wi-fi-settings-configure)

## <a name="line-of-business-apps"></a>Aplikacje biznesowe 
Chociaż za pośrednictwem usługi Microsoft Store można zainstalować kilka aplikacji, prawdopodobnie masz własną aplikację niestandardową utworzoną specjalnie do użycia w rzeczywistości mieszanej. Te aplikacje niestandardowe dystrybuowane w całej organizacji dla Twojej firmy są nazywane aplikacjami biznesowymi (LOB).
  
Istnieje wiele sposobów wdrażania aplikacji na HoloLens 2 urządzeniach. Aplikacje można wdrażać bezpośrednio za pośrednictwem rozwiązania MDM, Microsoft Store dla Firm (MSfB) lub ładować bezpośrednio za pośrednictwem pakietu aprowizowania. Na potrzeby tego przewodnika będziemy wdrażać aplikacje za pośrednictwem rozwiązania MDM, korzystając z wymaganej instalacji aplikacji. Umożliwi to automatyczne pobranie aplikacji LOB na urządzenia HoloLens po zakończeniu rejestracji.

Dla osób, które nie mają własnych aplikacji LOB, udostępnimy przykładową aplikację do testowania tego przepływu wdrażania. Ta aplikacja będzie aplikacją [mrTK Examples](https://aka.ms/HoloLensDocs-Sample-MRTK-Examples-App) i została już wstępnie sprebugowana i spakowana w celu przetestowania weryfikacji koncepcji.

Więcej szczegółów dotyczących wdrażania aplikacji można znaleźć na stronie [Zarządzanie aplikacją: Omówienie.](/hololens/app-deploy-overview)

> [!NOTE]
> HoloLens 2 obsługuje uruchamianie tylko aplikacji ARM64 platformy UWP.

## <a name="guides-playbook"></a>Podręcznik przewodników
Przewodniki wykorzystują środowisko Microsoft Dataverse jako magazyn danych dla aplikacji Przewodniki. Ważne jest, aby zrozumieć, jak środowisko Dataverse współdziała z aplikacjami przewodników i twoją dzierżawą. W tym przewodniku nie opisano sposobu zarządzania obiektem dataverse, ale zapoznaj się z podstawowymi pojęciami wdrażania przewodników usługi [Dynamics 365 — Dynamics 365 Mixed Reality](/dynamics365/mixed-reality/guides/admin-deployment-playbook).

## <a name="next-step"></a>Następny krok 
> [!div class="nextstepaction"]
> [Wdrożenie połączone z firmą — konfigurowanie](hololens2-corp-connected-configure.md)