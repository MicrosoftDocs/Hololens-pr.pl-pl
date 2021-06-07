---
title: Zarządzanie urządzeniami HoloLens przy użyciu Endpoint Manager Intune firmy Microsoft
description: Dowiedz się, jak za pomocą rozwiązania MDM skonfigurować zasady i zasady dotyczące programu CSP oraz zarządzać urządzeniami rzeczywistości mieszanej HoloLens na dużą skalę przy użyciu usługi Intune.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/9/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ce288afdcb112c17ffde75078d641f3637a8448c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378358"
---
# <a name="using-microsofts-endpoint-manager-intune-to-manage-hololens-devices"></a>Zarządzanie urządzeniami HoloLens przy użyciu Endpoint Manager Intune firmy Microsoft

Istnieje wiele różnych ustawień, które można zarządzać za pośrednictwem zarządzania urządzeniami przenośnymi. Urządzenia usługi Intune można grupować razem, a konfiguracje można wdrażać w tych grupach użytkowników lub urządzeń. Aplikacje można również wdrażać i zarządzać nimi, konfigurować urządzenia w celu nawiązywania połączenia z siecią, a także konfigurować aktualizacje w żądanym czasie i w wymaganym pierścieniu aktualizacji. 

## <a name="how-to-manage-via-intune"></a>Jak zarządzać za pomocą usługi Intune

### <a name="device-categories-and-groups"></a>Kategorie i grupy urządzeń
Za pomocą usługi Intune można tworzyć kategorie urządzeń, aby automatycznie dodawać urządzenia do grup na podstawie tworzyć kategorie, takie jak inżynieria, opieka medyczna, deweloperzy i tak dalej. Koncepcja ta ma na celu ułatwienie zarządzania urządzeniami z systemem Windows Holographic for Business.
Dowiedz się więcej: [Kategoryzowanie urządzeń do grup](https://docs.microsoft.com/mem/intune/enrollment/device-group-mapping)

### <a name="device-configuration-profiles"></a>Profile konfiguracji urządzeń
Usługa Intune obejmuje ustawienia i funkcje, które można włączać lub wyłączać na różnych urządzeniach w organizacji. Te ustawienia i funkcje są zarządzane przy użyciu profilów. Na przykład możesz utworzyć profil włączający Cortanę lub używający usługi Microsoft Defender Smart Screen na urządzeniach z systemem Windows Holographic for Business.
W profilach możesz użyć identyfikatora URI OMA, aby dostosować wybrane ustawienia, utworzyć ograniczenia urządzeń i skonfigurować wirtualną sieć prywatną (VPN) oraz sieć Wi-Fi.
[Wprowadzenie do profilów konfiguracji](https://docs.microsoft.com/mem/intune/configuration/device-profiles)i omówienie [profilu.](https://docs.microsoft.com/mem/intune/configuration/device-profile-create)

## <a name="examples-of-what-can-be-managed-and-configured"></a>Przykłady tego, co można zarządzać i konfigurować

Zarządzanie urządzeniami przenośnymi zapewnia szeroką gamę elementów, które można wybrać. 

### <a name="wi-fi"></a>Wi-Fi
Profil [Ustawienia sieci Wi-Fi](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure) przypisuje ustawienia sieci bezprzewodowej do użytkowników i urządzeń. Po przypisaniu profilu Wi-Fi użytkownicy uzyskają dostęp do konta Wi-Fi bez konieczności konfigurowania go samodzielnie.
Dowiedz się więcej [o konfigurowaniu sieci dla urządzenia HoloLens](hololens-commercial-infrastructure.md)

### <a name="certificates"></a>Certyfikaty
Certyfikaty pomagają zwiększyć bezpieczeństwo, zapewniając uwierzytelnianie konta, uwierzytelnianie Wi-Fi, szyfrowanie sieci VPN i szyfrowanie SSL zawartości internetowej. Mimo że administratorzy mogą ręcznie zarządzać certyfikatami na urządzeniach za pomocą pakietów aprowizacji, najlepszym rozwiązaniem jest użycie systemu MDM do zarządzania tymi certyfikatami przez cały cykl ich życia — od rejestracji po odnawianie i odwoływanie. System MDM może automatycznie wdrożyć te certyfikaty w magazynach certyfikatów urządzeń po zarejestrowaniu urządzenia (o ile system MDM obsługuje standard prosty protokół rejestrowania certyfikatów (SCEP) lub standardy kryptografii klucza publicznego #12 (PKCS #12)). Rozwiązanie MDM może również wysyłać zapytania o zarejestrowane certyfikaty klienta i usuwać je lub wyzwalać nowe żądanie rejestracji przed wygaśnięciem bieżącego certyfikatu. 

### <a name="proxy"></a>Serwer proxy
Większość firmowych sieci intranetowych korzysta z serwera proxy do zarządzania ruchem wewnętrznym. Na urządzeniach HoloLens 2 można skonfigurować serwer proxy dla połączeń ethernet i Wi-Fi sieci. Te ustawienia nie dotyczą połączeń sieci VPN. Aby uzyskać więcej informacji na temat ustawień serwera proxy dla Windows 10, [zobacz NetworkProxy CSP ( NetworkProxy CSP).](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)

### <a name="vpn"></a>VPN
Organizacje często używają sieci VPN do kontrolowania dostępu do aplikacji i zasobów w intranecie firmy. Urządzenie HoloLens 2 obsługuje połączenia SSL sieci VPN, które wymagają wtyczki do pobrania z serwera Microsoft Store i są specyficzne dla wybranego dostawcy sieci VPN. 
- Przeczytaj więcej na temat [sieci VPN na urządzeniach HoloLens.](hololens-network.md#vpn)
- Aby uzyskać więcej informacji na temat profilów sieci VPN, zobacz [VPNv2 CSP](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).

### <a name="deploy-and-manage-apps"></a>Wdrażanie aplikacji i zarządzanie nimi
Przy użyciu usługi Intune możesz dodawać aplikacje do urządzeń z systemem Windows Holographic for Business. Rozwiązanie MDM umożliwia twórcom i administratorom IT prywatną automatyczną instalację (wypychanie) własnych aplikacji biznesowych lub kupowanie aplikacji za pośrednictwem sklepu dla grupy użytkowników. Istnieje wiele sposobów wdrażania aplikacji, w tym:
-   [Intune i Portal firmy]( app-deploy-intune.md)
-   [Sklep Microsoft dla Firm]( app-deploy-store-business.md)

Dowiedz się więcej o zarządzaniu aplikacją za pośrednictwem usługi Intune.
-   [Dodawanie aplikacji do usługi Intune](https://docs.microsoft.com/mem/intune/apps/apps-add)
-   [Dodawanie aplikacji ze sklepu Microsoft Store](https://docs.microsoft.com/mem/intune/apps/store-apps-windows)
-   [Dodawanie utworzonej aplikacji](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
- [Przypisywanie aplikacji do grup](https://docs.microsoft.com/mem/intune/apps/apps-deploy)

### <a name="software-updates"></a>Aktualizacje oprogramowania
Usługa Intune obejmuje funkcję zwaną strefami aktualizacji dla urządzeń z systemem Windows 10. Te strefy aktualizacji obejmują grupę ustawień, które określają sposób instalacji aktualizacji. Na przykład możesz utworzyć okno obsługi, aby zainstalować aktualizacje lub wybrać opcję ponownego uruchomienia po zainstalowaniu aktualizacji. Strefę aktualizacji można zastosować do wielu urządzeń z systemem Windows Holographic for Business.
Dowiedz się więcej na temat zarządzania [aktualizacjami urządzenia HoloLens](hololens-updates.md) i [zarządzania aktualizacjami oprogramowania za pośrednictwem usługi Intune.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)

### <a name="configure-kiosk-mode"></a>Konfigurowanie trybu kiosku
Za pomocą udostępnionych funkcji lub funkcji komputera gościa usługi Intune możesz skonfigurować urządzenia z systemem Windows Holographic for Business, aby były uruchamiane jako kiosk. Na tych urządzeniach może działać jedna aplikacja (tryb kiosku z jedną aplikacją) lub wiele aplikacji (tryb kiosku z wieloma aplikacjami). Tryb kiosku to interfejs użytkownika do kontrolowania tożsamości, które domyślnie mają dostęp do których aplikacji.
Dowiedz się, [jak skonfigurować urządzenie HoloLens jako kiosk]( hololens-kiosk.md)

