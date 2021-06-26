---
title: Przewodnik wdrażania — wdrażanie urządzenia HoloLens 2 połączonego z chmurą na dużą skalę przy użyciu usługi Remote Assist — przygotowanie
description: Dowiedz się, jak przygotować się do zarejestrowania urządzeń HoloLens za pośrednictwem sieci połączonej z chmurą przy użyciu usługi Azure Active Directory i zarządzania tożsamościami.
keywords: HoloLens, zarządzanie, połączone z chmurą, Remote Assist, AAD, Azure AD, MDM, Mobile Zarządzanie urządzeniami
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 21132ed5d1e84d92a877747ac9a4c090b177ca08
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924574"
---
# <a name="prepare---cloud-connected-guide"></a>Przygotowanie — przewodnik po połączeniu z chmurą

Po zakończeniu pracy z tym artykułem skonfigurujemy usługę Azure AD i rozwiązanie MDM oraz lepiej zrozumiesz wymagania dotyczące korzystania z kont usługi Azure AD i sieci. Ta sekcja przewodnika pomoże Ci i Twojej organizacji przygotować się do wdrożenia urządzenia HoloLens 2 w chmurze i korzystania z usługi Dynamics 365 Remote Assist. Zostanie ona przejmuje ważność każdego elementu infrastruktury, a także będzie zawierać linki do przewodników, które pomogą Ci skonfigurować te elementy zgodnie z potrzebami.

## <a name="infrastructure-essentials"></a>Podstawowe informacje o infrastrukturze

W przypadku scenariuszy wdrażania osobistego i firmowego system MDM jest podstawową infrastrukturą wymaganą do wdrażania urządzeń Windows 10 Holographic zarządzania nimi. Subskrypcja usługi Azure AD Premium jest zalecana jako dostawca tożsamości i wymagana do obsługi niektórych funkcji.

### <a name="azure-active-directory"></a>Azure Active Directory

Azure AD to oparta na chmurze usługa katalogowa, która zapewnia zarządzanie tożsamościami i dostępem. Organizacje korzystające z usługi Microsoft Office 365 lub Intune już używają usługi Azure AD, która ma trzy wersje: Bezpłatna, Premium P1 i Premium P2 (zobacz [Azure Active Directory wersji).](https://azure.microsoft.com/documentation/articles/active-directory-editions) Wszystkie wersje obsługują rejestrację urządzeń w usłudze Azure AD, ale do włączenia automatycznej rejestracji w usłudze MDM, której będziemy używać w dalszej części tego przewodnika, jest wymagana wersja Premium P1.

> [!IMPORTANT]
> Bardzo ważne jest, aby mieć Azure Active Directory, ponieważ urządzenia HoloLens nie obsługują lokalnego dołączania do usługi AD. Jeśli nie&#39;jeszcze Azure Active Directory, przejdź do strony Tworzenie nowej dzierżawy w [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## <a name="identity-management"></a>Zarządzanie tożsamością

Pracownicy mogą używać tylko jednego konta do inicjowania urządzenia, tak aby&#39;konieczne było, aby twoja organizacja kontroluje, które konto jest włączone w pierwszej kolejności. Wybrane konto określi, kto kontroluje urządzenie i wpływa na możliwości zarządzania.

W tym przewodniku wybraliśmy, że dla używanej tożsamości będą używane konta usługi Azure AD lub Azure Active Directory kont. [](https://docs.microsoft.com/hololens/hololens-identity) Istnieje kilka korzyści dla kont usługi Azure AD, których chcemy użyć, takich jak:

- Pracownicy używają swojego konta usługi Azure AD do rejestrowania urządzenia w usłudze Azure AD i automatycznego rejestrowania go w organizacji&#39;rozwiązania MDM (Azure AD+MDM — wymaga Azure AD — wersja Premium).
- Konta usługi Azure AD obsługują [logowanie pojedyncze.](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) Gdy użytkownik zalogował się do usługi Remote Assist, jego tożsamość z zalogowaonego użytkownika usługi Azure AD zostanie rozpoznana, a użytkownik zostanie zalogowany do aplikacji w celu usprawnienia obsługi.
- Konta usługi Azure AD mają dodatkowe [opcje uwierzytelniania za](https://docs.microsoft.com/hololens/hololens-identity) [pośrednictwem Windows Hello dla firm](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). Oprócz logowania irysów użytkownicy mogą logować się z innego urządzenia lub używać kluczy zabezpieczeń FIDO.

### <a name="mobile-device-management"></a>Zarządzanie urządzeniami przenośnymi

Usługa Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune), część usługi Enterprise Mobility + Security, to oparty na chmurze system MDM, który zarządza urządzeniami połączonymi z dzierżawą. Podobnie jak usługa Office 365, usługa Intune używa usługi Azure AD do zarządzania tożsamościami, więc pracownicy używają tych samych poświadczeń do rejestrowania urządzeń w usłudze Intune, których używają do logowania się do usługi Office 365. Usługa Intune obsługuje również urządzenia z innymi systemami operacyjnymi, takimi jak iOS i Android, w celu zapewnienia pełnego rozwiązania MDM. Na potrzeby tego przewodnika skupimy się&#39;usłudze Intune w celu umożliwienia wdrożenia chmury na dużą skalę przy użyciu urządzenia HoloLens 2.

> [!IMPORTANT]
> Ważne jest, aby mieć aplikacje mobilne Zarządzanie urządzeniami. Jeśli nie masz&#39;, postępuj zgodnie z tym przewodnikiem i [rozpoczynanie pracy z usługą Intune.](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)

> [!NOTE]
> Wiele systemów MDM obsługuje Windows 10 i większość obsługuje scenariusze wdrażania urządzeń osobistych i firmowych. Dostawcy rozwiązań MDM, którzy obsługują Windows 10 Holographic obecnie obejmują: AirWatch, MobileIron i inni. Większość wiodących w branży dostawców rozwiązań MDM obsługuje już integrację z usługą Azure AD. Dostawców rozwiązań MDM, którzy obsługują usługę Azure AD, można znaleźć w [Azure Marketplace](https://azure.microsoft.com/marketplace/).

## <a name="network"></a>Sieć

W tej konfiguracji przewidujemy urządzenia HoloLens 2 łączące się z Internetem z dowolnej dostępnej otwartej Wi-Fi sieci. Ponieważ użytkownik może wymagać zmiany połączenia sieciowego na podstawie lokalizacji, powinien dowiedzieć się, jak połączyć urządzenia [HoloLens z siecią Wi-Fi.](https://docs.microsoft.com/hololens/hololens-network)

W przypadku usługi Dynamics 365 Remote Assist istnieją różne warunki sieciowe, w tym przepustowość, opóźnienie, zakłócenie i utrata pakietów, które mogą mieć wpływ na środowisko wywoływania wideo. Chociaż wywołania audio i wideo mogą być możliwe w środowiskach z ograniczoną przepustowością, może wystąpić pogorszenie funkcji. W przypadku korzystania z usługi Dynamics 365 Remote Assist na urządzeniach HoloLens należy pamiętać o wymaganiach dotyczących sieci:

**Minimum:** 1,5 Mb/s w górę/w dół jest wymagane w przypadku równorzędnego wywoływania wideo w jakości HD z rozdzielczością HD 1080p przy rozdzielczości 30 pikseli.

**Optymalne:** W przypadku połączeń wideo w jakości HD typu peer-to-peer o rozdzielczości HD 1080p należy spodziewać się 4–5 Mb/s w górę/w dół.

Więcej informacji:

- [Wymagania dotyczące sieci](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Zalecenia dotyczące optymalizacji sieci](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>Opcjonalnie: łączenie urządzenia HoloLens z siecią VPN

Urządzenia połączone z tym przewodnikiem będą łączyć się z siecią za pośrednictwem sieci i zewnętrznej sieci w chmurze. Być może w celu uzyskania dostępu do zasobów firmy&#39;będzie konieczne połączenie urządzeń za pośrednictwem sieci VPN. Istnieje kilka różnych sposobów łączenia urządzeń z siecią VPN, zarówno w przypadku, gdy użytkownik końcowy może nawiązać połączenie za pomocą interfejsu użytkownika urządzenia, albo urządzenia mogą być zarządzane i odbierać profil sieci VPN z narzędzia PPKG lub MDM. Sposób skonfigurowania sieci VPN nie zostanie&#39;w tym artykule, dlatego jeśli chcesz dowiedzieć się więcej o różnych protokołach sieci VPN lub sposobach zarządzania siecią VPN&#39;, zapoznaj się z tymi przewodnikami, aby uzyskać informacje na temat urządzenia [HoloLens](https://docs.microsoft.com/hololens/hololens-network#vpn) i sieci VPN.

## <a name="next-step"></a>Następny krok

> [!div class="nextstepaction"]
> [Wdrożenie połączone z chmurą — konfigurowanie](hololens2-cloud-connected-configure.md)
