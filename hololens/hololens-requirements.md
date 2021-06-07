---
title: Konfigurowanie urządzenia HoloLens w środowisku komercyjnym
description: Dowiedz się więcej na temat wdrażania urządzenia HoloLens i zarządzania nim w środowiskach przedsiębiorstwa, w tym w infrastrukturze, usłudze Azure Active Directory i zarządzaniu urządzeniami przenośnymi.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
ms.reviewer: aboeger
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: e6aebfca076294de34068cd075d954220d7f4686
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378350"
---
# <a name="hololens-2-enterprise-deployment-and-management"></a>Wdrażanie urządzenia HoloLens 2 w przedsiębiorstwie i zarządzanie nimi

To omówienie ma pomóc specjalistom IT zrozumieć zagadnienia dotyczące wdrażania i zarządzania Microsoft HoloLens 2 urządzeniami w przedsiębiorstwie.

Urządzenie HoloLens 2 działa na platformie Windows 10 Holographic która zapewnia organizacjom niezawodne, elastyczne, wbudowane technologie zarządzania urządzeniami przenośnymi i aplikacją. Windows 10 Holographic obsługuje zarządzanie całym cyklem życia urządzeń, aby zapewnić firmom kontrolę nad ich urządzeniami, danymi i aplikacjami. Urządzenie HoloLens 2 można łatwo włączyć do standardowych rozwiązań w zakresie cyklu życia, od rejestracji urządzeń, konfiguracji i zarządzania aplikacją po konserwację i wycofanie przy użyciu kompleksowego rozwiązania do zarządzania urządzeniami przenośnymi.

## <a name="prepare"></a>Przygotowywanie

Podczas przygotowywania do wdrożenia urządzenia HoloLens 2 w korporacyjnym środowisku przedsiębiorstwa należy zapoznać się z kilkoma zagadnieniami, które należy rozważyć, aby rozpocząć planowanie wdrożeń na dużą skalę urządzenia HoloLens 2.

### <a name="infrastructure-essentials"></a>Podstawowe informacje o infrastrukturze

W przypadku urządzenia HoloLens 2 w scenariuszu wdrażania w przedsiębiorstwie istnieją pewne podstawowe usługi infrastruktury wymagane do obsługi pełnego zestawu funkcji. Urządzenie HoloLens 2 zostało zbudowane z myślą o Zarządzanie urządzeniami [Modern Mobile](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) na platformie do wdrażania i zarządzania. Podstawowym sposobem osiągnięcia tego celu jest dołączenie do usługi Azure AD i zarządzanie urządzeniami przenośnymi w coraz większej liczby pracowników mobilnych. Poniższe tematy zawierają krótkie omówienie każdego składnika infrastruktury, który należy wziąć pod uwagę podczas planowania wdrożenia urządzenia HoloLens 2.

### <a name="azure-active-directory"></a>Azure Active Directory
Azure AD to oparta na chmurze usługa katalogowa, która zapewnia zarządzanie tożsamościami i dostępem. Można ją zintegrować z istniejącymi katalogami lokalnymi, aby utworzyć rozwiązanie tożsamości hybrydowej. Organizacje używające usługi Microsoft Office 365 lub Intune już używają usługi Azure AD, która ma trzy wersje: Bezpłatna, Premium P1 i Premium P2 (zobacz [Azure Active Directory wersji](https://azure.microsoft.com/documentation/articles/active-directory-editions/)). Wszystkie wersje obsługują rejestrację urządzeń w usłudze Azure AD, ale do włączenia automatycznej rejestracji w usłudze MDM jest wymagana wersja Premium P1. Urządzenie HoloLens 2 wymaga Azure Active Directory Join, aby włączyć większość funkcji i funkcji na poziomie przedsiębiorstwa.

> [!NOTE]
> Lokalne dołączanie do usługi Active Directory nie jest obsługiwane na urządzeniach HoloLens 2.

### <a name="mobile-device-management"></a>Zarządzanie urządzeniami przenośnymi
Urządzenie HoloLens 2 zostało zaprojektowane specjalnie do zarządzania przez systemy Mobile Zarządzanie urządzeniami (MDM) w środowisku przedsiębiorstwa. Microsoft [Intune](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune), część usługi Enterprise Mobility + Security, to oparty na chmurze system MDM, który zarządza urządzeniami w przedsiębiorstwie. Podobnie jak usługa Office 365, usługa Intune używa usługi Azure AD do zarządzania tożsamościami, więc pracownicy używają tych samych poświadczeń do rejestrowania urządzeń w usłudze Intune, których używają do logowania się do usługi Office 365. Wiele systemów MDM obsługuje Windows 10 a większość obsługuje scenariusze wdrażania urządzeń osobistych i firmowych. Systemy MDM mogą również zarządzać wdrożeniami i aktualizacjami aplikacji dla urządzenia HoloLens 2. Inni dostawcy rozwiązań MDM, którzy obecnie obsługują urządzenie HoloLens 2, to: AirWatch, MobileIron i inni. Wszyscy dostawcy systemów MDM mają równy dostęp do dostawców usług konfiguracji zarządzania urządzeniami (CSP) firmy Windows 10, co daje organizacjom IT swobodę wyboru systemu najlepiej dopasowanego do ich wymagań w zakresie zarządzania, niezależnie od tego, czy jest Microsoft Intune czy też produkt MDM innej firmy.

> [!NOTE]
> Tradycyjne lokalne systemy zarządzania komputerami, takie System Center Menedżer konfiguracji, nie są obsługiwane na urządzeniach HoloLens 2.

### <a name="windows-update-for-business"></a>Windows Update dla firm
Firma Microsoft zaprojektowała Windows Update dla Firm, aby zapewnić administratorom IT dodatkowe funkcje zarządzania zorientowane na funkcje Windows Update, takie jak możliwość wdrażania aktualizacji w grupach urządzeń i definiowania okien obsługi w celu instalowania aktualizacji. Zobacz dokumentację [aktualizacji urządzenia HoloLens,](https://docs.microsoft.com/hololens/hololens-updates) aby uzyskać szczegółowe informacje na temat zarządzania aktualizacjami urządzenia HoloLens 2.

### <a name="certificates"></a>Certyfikaty
Urządzenie HoloLens 2 obsługuje wdrażanie certyfikatów za pośrednictwem rozwiązania MDM, jeśli środowisko wymaga certyfikatów na Wi-Fi firmy Corp lub dostępu do innych zasobów. Niektóre konfiguracje infrastruktury MDM mogą być wymagane do włączenia wdrożeń certyfikatów na urządzeniach HoloLens 2. Przeczytaj o tym, jak [przygotować certyfikaty i profile sieciowe dla urządzenia HoloLens 2.](https://docs.microsoft.com/hololens/hololens-certificates-network) Jeśli używasz usługi Intune, zapoznaj się ze [szczegółami konfiguracji certyfikacji.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)

## <a name="configure"></a>Konfigurowanie

Administratorzy mdm mogą definiować i implementować ustawienia zasad na dowolnym urządzeniu firmowym zarejestrowanym w systemie MDM. Ustawienia konfiguracji, których użyjemy, różnią się w zależności od scenariusza wdrażania. W Windows 10 dostawcy usług konfiguracji (CSP) to interfejs do odczytywania, konfigurowania, modyfikowania lub usuwania ustawień konfiguracji na urządzeniu. Te ustawienia są mapowe na klucze lub pliki rejestru. Aby uzyskać więcej informacji Windows 10 zarządzania urządzeniami CSP dla urządzenia HoloLens 2, zobacz pełną listę adresów CSP obsługiwanych na [urządzeniach HoloLens.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)

Urządzenie HoloLens 2 obsługuje również ustawianie ograniczonego zestawu konfiguracji CSP za pomocą niestandardowych pakietów aprowizowania. Pakiety aprowizowania są zwykle używane w przypadku urządzeń innych niż zarządzane przez rozwiązanie MDM i wymagają ręcznego zastosowania do każdego urządzenia. Aby uzyskać szczegółowe informacje na temat tworzenia niestandardowych pakietów aprowizowania, zobacz dokumentację aprowizowania urządzenia [HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning)

> [!NOTE]
> Urządzenie HoloLens 2 obsługuje [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot), zapewniając łatwy i prosty proces zarządzania konfiguracją urządzeń Windows 10 firmowych.

### <a name="identity-management"></a>Zarządzanie tożsamością

Pracownicy mogą używać tylko jednego konta do zainicjowania urządzenia, aby&#39;konieczne, aby organizacja kontroluje najpierw, które konto jest włączone. Wybrane konto określi, kto kontroluje urządzenie i wpływa na możliwości zarządzania. Urządzenie HoloLens 2 obsługuje 3 typy kont: konto użytkownika lokalnego, osobiste konto Microsoft i Azure Active Directory konta. Zdecydowanie zaleca się korzystanie z Azure Active Directory rozwiązania do zarządzania tożsamościami w przedsiębiorstwie, ponieważ umożliwi to korzystanie z pełnych możliwości na urządzeniach HoloLens 2. Zapoznaj się z [tożsamością urządzenia HoloLens,](https://docs.microsoft.com/hololens/hololens-identity) aby uzyskać więcej informacji na temat tożsamości dla urządzenia HoloLens 2.

### <a name="network-and-connectivity"></a>Sieć i łączność

Ponieważ urządzenie HoloLens 2 jest pierwszym urządzeniem w chmurze, dostęp sieciowy do zasobów online jest wymagany do uzyskania pełnej funkcjonalności i możliwości. W przypadku wdrażania urządzeń HoloLens 2 z łącznością z firmową siecią intranet może być konieczne zaktualizowanie reguł serwera proxy/zapory w celu umożliwienia dostępu do usług HoloLens 2 w chmurze. Aby uzyskać więcej informacji, zobacz listę typowych punktów końcowych dla systemu operacyjnego [HoloLens 2.](https://docs.microsoft.com/hololens/hololens-offline) Aby aplikacje lub inne usługi w chmurze działały pomyślnie na urządzeniach HoloLens 2, może być wymagany dostęp do dodatkowych punktów końcowych.

Niektóre typowe usługi urządzenia HoloLens 2 wymagające dodatkowego dostępu do punktu końcowego są następujące:

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [Przewodniki D365](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [Zdalna pomoc dla usługi D365 (infrastruktura usługi O365 Teams)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### <a name="certificate-deployment"></a>Wdrażanie certyfikatu

Jeśli certyfikaty są wymagane w celu uzyskania dostępu do sieci Wi-Fi firmowych lub innych usług w organizacji, urządzenie HoloLens 2 obsługuje wdrażanie certyfikatów użytkowników i urządzeń za pośrednictwem rozwiązania MDM. Uwaga: Rozwiązanie MDM może wymagać dodatkowej konfiguracji infrastruktury w celu wdrożenia certyfikatów na Windows 10 urządzeń.

### <a name="security-review"></a>Przegląd zabezpieczeń

Większość działów IT przedsiębiorstwa będzie wymagać oceny i przeglądu nowych urządzeń wdrażanych w firmowej sieci przedsiębiorstwa. Jeśli Twoja organizacja potrzebuje przeglądu zabezpieczeń urządzenia HoloLens 2, możesz znaleźć więcej szczegółów, aby uzyskać pomoc w uzyskiwaniu [zatwierdzeń zabezpieczeń.](https://docs.microsoft.com/hololens/security-overview)

### <a name="common-hololens-2-device-settings"></a>Typowe ustawienia urządzenia HoloLens 2

Podczas wdrażania urządzeń HoloLens 2 w korporacyjnym środowisku firmy istnieje kilka typowych konfiguracji urządzeń, które można uwzględnić podczas planowania wdrożenia urządzenia HoloLens 2. Ta lista wyróżnia konfiguracje i ustawienia, które są dość typowe i nie obejmują pełnej listy dostępnych opcji:

| Ustawienie urządzenia | Krótki opis.                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [Ograniczenia sprzętowe](hololens-requirements.md#hardware-restrictions)               | Ograniczenia sprzętowe zmniejszają łączność i pomagają w ochronie danych.                        |
| [Profile sieci Wi-Fi](hololens-requirements.md#wi-fi-profiles)               | Skonfiguruj Wi-Fi użytkowników bez interwencji użytkownika ani interakcji.                              |
| [Certyfikaty](hololens-requirements.md#certificates-1)               | Podaj uwierzytelnianie konta i/Wi-Fi, szyfrowanie sieci VPN i szyfrowanie SSL zawartości internetowej. |
| [Proxy](hololens-requirements.md#proxy)              | Zarządzanie ruchem wewnętrznym.                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | Kontroluj dostęp do aplikacji i zasobów w intranecie firmy.                               |
| [Tryb kiosku](hololens-requirements.md#kiosk-mode) | Ogranicza aplikacje, które są prezentowane użytkownikom za pośrednictwem interfejsu użytkownika. |

#### <a name="hardware-restrictions"></a>Ograniczenia sprzętowe

Urządzenie HoloLens 2 korzysta z najnowocześniejszej technologii, która obejmuje popularne funkcje sprzętowe, takie jak kamery, mikrofony, głośniki, interfejsy USB, interfejsy Bluetooth i sieć Wi-Fi. Aby kontrolować dostępność tych funkcji, można użyć ograniczeń sprzętowych.

Poniżej wymieniono najczęściej używane ustawienia zarządzania urządzeniami przenośnymi, które obsługuje urządzenie HoloLens 2 w celu skonfigurowania ograniczeń sprzętowych. Niektóre z tych ograniczeń sprzętowych zapewniają łączność i pomagają w ochronie danych.

- [**Zezwalaj na sieć Wi-Fi:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Czy użytkownicy mogą włączać i używać przycisku radiowego Wi-Fi na swoich urządzeniach
- [**Zezwalaj na połączenie USB:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Czy połączenie USB jest włączone (nie&#39;ładowania USB)
- [**Zezwalaj na połączenia Bluetooth:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Czy użytkownicy mogą włączać i używać przycisku radiowego Bluetooth na swoich urządzeniach

Dowiedz się więcej o innych [typowych ograniczeniach dotyczących urządzeń.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

#### <a name="wi-fi-profiles"></a>Profile sieci Wi-Fi

Większość firmowych Wi-Fi wymaga certyfikatów i innych złożonych informacji w celu ograniczenia i zabezpieczenia dostępu użytkowników. Te zaawansowane Wi-Fi są trudne do skonfigurowania dla typowych użytkowników, ale systemy MDM mogą w pełni skonfigurować te profile Wi-Fi bez interwencji użytkownika. W systemie MDM Wi-Fi wiele profilów zarządzania urządzeniami przenośnymi.

Aby uzyskać więcej informacji na Wi-Fi ustawień sieci Windows 10, zobacz [Ustawienia sieci Wi-Fi profilu przedsiębiorstwa.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)

#### <a name="certificates"></a>Certyfikaty

Certyfikaty pomagają zwiększyć bezpieczeństwo, zapewniając uwierzytelnianie konta, Wi-Fi uwierzytelnianie, szyfrowanie sieci VPN i szyfrowanie SSL zawartości internetowej. Mimo że administratorzy mogą zarządzać certyfikatami na urządzeniach ręcznie za pomocą pakietów aprowizacji&#39;, najlepszym rozwiązaniem jest użycie systemu MDM do zarządzania tymi certyfikatami przez cały cykl ich życia — od rejestracji po odnawianie i odwoływanie. System MDM może automatycznie wdrożyć te certyfikaty na urządzeniach&#39; magazynach certyfikatów po zarejestrowaniu urządzenia (o ile system MDM obsługuje standard prosty protokół rejestrowania certyfikatów (SCEP) lub public Key Cryptography Standards #12 (PKCS #12)). Rozwiązanie MDM może również wysyłać zapytania o zarejestrowane certyfikaty klienta i usuwać je lub wyzwalać nowe żądanie rejestracji przed wygaśnięciem bieżącego certyfikatu.

Przeczytaj więcej na temat przygotowywania [certyfikatów i profilów sieciowych dla urządzenia HoloLens 2.](https://docs.microsoft.com/hololens/hololens-certificates-network)

#### <a name="proxy"></a>Serwer proxy

Większość firmowych sieci intranet korzysta z serwera proxy do zarządzania ruchem wewnętrznym. Za pomocą urządzenia HoloLens 2 można skonfigurować serwer proxy dla połączeń ethernet i Wi-Fi sieciowych. Te ustawienia nie dotyczą połączeń sieci VPN.

Aby uzyskać więcej informacji na temat ustawień serwera proxy dla Windows 10, zobacz [NetworkProxy CSP ( NetworkProxy CSP).](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)

#### <a name="vpn"></a>VPN

Organizacje często używają sieci VPN do kontrolowania dostępu do aplikacji i zasobów w&#39;sieci intranet. Urządzenie HoloLens 2 obsługuje połączenia SSL sieci VPN, które wymagają wtyczki do pobrania z Microsoft Store i są specyficzne dla wybranego dostawcy sieci VPN.

Aby uzyskać więcej informacji na temat profilów sieci VPN, zobacz VPNv2 CSP (Dostawca usług [kryptograficznych VPNv2)](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx)

#### <a name="kiosk-mode"></a>Tryb kiosku

Urządzenie HoloLens 2 można skonfigurować tak, aby działało jako urządzenie o stałym przeznaniu, nazywane również kioskiem, przez skonfigurowanie urządzenia do uruchamiania w trybie kiosku. Tryb kiosku ogranicza aplikacje (lub użytkowników), które są dostępne na urządzeniu. Tryb kiosku to wygodna funkcja, za pomocą których można przeznaczyć urządzenie HoloLens 2 na aplikacje biznesowe lub użyć urządzenia HoloLens 2 w pokazie aplikacji.

Aby uzyskać więcej informacji na temat konfigurowania urządzenia HoloLens 2 w trybie kiosku, zobacz [Setup HoloLens as a Kiosk (Konfigurowanie urządzenia HoloLens jako kiosku)](https://docs.microsoft.com/hololens/hololens-kiosk)

## <a name="deploy"></a>Wdróż

### <a name="mdm-device-enrollment"></a>Rejestracja urządzeń MDM

W przypadku wdrożeń przedsiębiorstwa [](https://docs.microsoft.com/hololens/hololens-enroll-mdm) zaleca się rejestrowanie urządzeń w usłudze MDM jako urządzeń firmowych tylko przy użyciu dołączania do usługi Azure AD i automatycznej rejestracji w usłudze MDM (Azure AD+MDM). Wymaga to Azure AD — wersja Premium automatycznego rejestrowania kilku dostawców rozwiązań MDM, w tym usługi Intune.

Dowiedz się więcej o samodzielnej metodzie rejestracji rozwiązania [Autopilot.](https://docs.microsoft.com/hololens/hololens2-autopilot)

### <a name="application-deployment"></a>Wdrażanie aplikacji

Produktywność użytkowników na urządzeniach przenośnych jest często napędzana przez aplikacje.

Windows 10 umożliwia tworzenie aplikacji, które bezproblemowo działają na wielu urządzeniach, przy użyciu platformy platforma uniwersalna systemu Windows (UWP) dla aplikacji systemu Windows.

Istnieje wiele sposobów wdrażania aplikacji na urządzeniach HoloLens 2. Aplikacje można wdrażać bezpośrednio za pośrednictwem rozwiązania MDM, Microsoft Store dla Firm lub ładowane bezpośrednio za pośrednictwem pakietu aprowizowania. Aby uzyskać więcej [informacji, zapoznaj](https://docs.microsoft.com/hololens/app-deploy-overview) się z dokumentacją wdrażania aplikacji.

> [!NOTE]
> Urządzenie HoloLens 2 obsługuje tylko uruchamianie aplikacji ARM64 platformy UWP.

## <a name="maintain"></a>Obsługa

W środowiskach IT przedsiębiorstwa potrzeba zapewnienia bezpieczeństwa i kontroli kosztów musi być zrównoważona w stosunku do potrzeby zapewnienia użytkownikom najnowszych technologii. Ze względu na to, że cyberataki stały się codziennymi zdarzeniami, ważne jest, aby prawidłowo utrzymywać stan Windows 10 urządzeń. It needs to control configuration settings, keeping them from drifting out of compliance, as enforce which devices can access internal applications. Urządzenie HoloLens 2 zapewnia możliwości zarządzania operacjami mobilnymi niezbędne do zapewnienia zgodności urządzeń z zasadami firmowymi.

### <a name="os-servicing-options"></a>Opcje obsługi systemu operacyjnego

**Usprawniony proces aktualizacji**

Firma Microsoft usprawniła cykl projektowania i wydań produktów systemu Windows, dzięki czemu nowe funkcje, środowiska i funkcje, których wymaga rynek, mogą być dostarczane szybciej niż kiedykolwiek wcześniej. Firma Microsoft planuje dostarczać dwie aktualizacje funkcji na rok (okres 12 miesięcy). **Aktualizacje funkcji** ustanawiają Current Branch cb i mają skojarzoną wersję.

Firma Microsoft będzie również dostarczać i instalować aktualizacje w celu zapewnienia bezpieczeństwa i stabilności bezpośrednio na urządzeniach HoloLens 2. Te **aktualizacje dotyczące jakości** wydane pod kontrolą firmy Microsoft za pośrednictwem Windows Update są dostępne co miesiąc. Urządzenie HoloLens 2 zużywa aktualizacje dotyczące funkcji i jakości w ramach tego samego standardowego procesu aktualizacji.

Klienci w przedsiębiorstwach mogą zarządzać procesem i środowiskom aktualizacji na urządzeniach HoloLens 2 przy użyciu systemu MDM. W większości przypadków zasady zarządzania procesem aktualizacji będą stosowane zarówno do aktualizacji funkcji, jak i jakości. Więcej szczegółów dotyczących [konfigurowania funkcji MDM dla aktualizacji urządzenia HoloLens.](https://docs.microsoft.com/hololens/hololens-updates)

### <a name="managing-applications"></a>Zarządzanie aplikacjami

Administratorzy IT mogą kontrolować, które aplikacje mogą być instalowane na urządzeniach HoloLens 2 i jak powinny być one aktualne.

Urządzenie HoloLens 2 obsługuje Windows Defender [Application Control (WDAC),](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)co umożliwia administratorom tworzenie, zezwalanie lub zezwalanie na listy aplikacji z Microsoft Store. Ta funkcja rozszerza się również na aplikacje wbudowane. Możliwość zezwalania na aplikacje lub blokowania ich pomaga zapewnić, że ludzie używają swoich urządzeń do swoich celów. Jednak nie zawsze jest to łatwe podejście do znalezienia równowagi między tym, czego potrzebują pracownicy lub których żądają, a problemami z zabezpieczeniami. Tworzenie list zezwalania lub blokowania wymaga również nadążania za zmieniającym się poziomem aplikacji w Microsoft Store.

Aby uzyskać więcej informacji, zobacz [Application Control CSP (Program CSP kontroli aplikacji).](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp)

### <a name="retire"></a>Wycofaj

Wycofanie urządzenia jest ostatnią fazą cyklu życia urządzenia. Ważne&#39;&#39;, aby urządzenia zastępowane przez nowsze modele były bezpiecznie wycopywowane, ponieważ nie chcesz, aby żadne dane firmowe pozostały na odrzuconych urządzeniach, co mogłoby naruszyć poufność danych. It also needs a way to odpowiednio support users who need to wipe devices that are lost orstolen.

Urządzenie HoloLens 2 obsługuje 3 metody czyszowania urządzenia

**Czyszczenie fabryki mdm:** Resetuje urządzenie HoloLens 2 z powrotem do obrazu fabrycznego za pomocą polecenia MDM zainicjowanego przez administratora. Wymazuje wszystkie przechowywane dane na urządzeniu.

**Resetowanie urządzenia z poziomu ustawień:** Użytkownicy końcowi mogą ręcznie zresetować urządzenie HoloLens 2 w aplikacji Ustawienia na urządzeniu. Wymazuje wszystkie przechowywane dane na urządzeniu.

**Zaawansowana pomocnika odzyskiwania (ARC):** Na komputerze z uruchomionym narzędziem ARC użytkownik lub administrator może flashować urządzenie HoloLens 2 podłączone do komputera za pośrednictwem kabla USB. Wymazuje wszystkie przechowywane dane na urządzeniu.

> [!div class="nextstepaction"]
> [Typowe scenariusze wdrażania](common-scenarios.md)
