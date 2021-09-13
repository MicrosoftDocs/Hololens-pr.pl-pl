---
title: Przewodnik wdrażania — wdrażanie w 2 HoloLens z chmurą na dużą skalę przy użyciu usługi Remote Assist — przygotowanie
description: Dowiedz się, jak przygotować się do rejestracji urządzeń HoloLens za pośrednictwem sieci połączonej z chmurą przy użyciu usługi Azure Active Directory i zarządzania tożsamościami.
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
ms.openlocfilehash: 21fffdc24f8682bc44779e1cebe8cd6eacb59619
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033511"
---
# <a name="prepare---cloud-connected-guide"></a>Przygotowanie — przewodnik po połączeniu z chmurą

Po zakończeniu pracy z tym artykułem skonfigurujemy usługę Azure AD i rozwiązanie MDM oraz lepiej zrozumiesz wymagania dotyczące korzystania z kont usługi Azure AD i sieci. Ta sekcja przewodnika pomoże Ci i Twojej organizacji przygotować się do wdrożenia usługi HoloLens 2 w chmurze i korzystania z usługi Dynamics 365 Remote Assist. Zostanie ona przejmuje ważność każdego elementu infrastruktury, a także będzie zawierać linki do przewodników, które pomogą Ci skonfigurować te elementy zgodnie z potrzebami.

## <a name="infrastructure-essentials"></a>Podstawowe informacje o infrastrukturze

W przypadku scenariuszy wdrażania osobistego i firmowego system MDM jest podstawową infrastrukturą wymaganą do wdrażania urządzeń Windows 10 Holographic zarządzania nimi. Subskrypcja usługi Azure AD Premium jest zalecana jako dostawca tożsamości i wymagana do obsługi niektórych funkcji.

### <a name="azure-active-directory"></a>Azure Active Directory

Azure AD to oparta na chmurze usługa katalogowa, która zapewnia zarządzanie tożsamościami i dostępem. Organizacje używające usługi Microsoft Office 365 lub Intune już używają usługi Azure AD, która ma trzy wersje: Bezpłatna, Premium P1 i Premium P2 (zobacz Azure Active Directory [wersje).](https://azure.microsoft.com/documentation/articles/active-directory-editions) Wszystkie wersje obsługują rejestrację urządzeń w usłudze Azure AD, ale Premium P1 jest wymagana do włączenia automatycznej rejestracji w usłudze MDM, której będziemy używać w dalszej części tego przewodnika.

> [!IMPORTANT]
> Bardzo ważne jest, aby mieć Azure Active Directory, HoloLens urządzenia nie obsługują lokalnego dołączania do usługi AD. Jeśli nie&#39;jeszcze skonfigurować Azure Active Directory, przejdź do strony Tworzenie nowej [dzierżawy](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)w Azure Active Directory .

## <a name="identity-management"></a>Zarządzanie tożsamością

Pracownicy mogą używać tylko jednego konta do inicjowania urządzenia, tak aby&#39;niezbędne do tego, aby twoja organizacja kontroluje, które konto jest włączone w pierwszej kolejności. Wybrane konto określi, kto kontroluje urządzenie i wpływa na możliwości zarządzania.

W tym przewodniku wybraliśmy, że dla używanej tożsamości będą używane konta usługi Azure AD, Azure Active Directory kont. [](/hololens/hololens-identity) Istnieje kilka korzyści dla kont usługi Azure AD, których chcemy użyć, takich jak:

- Pracownicy używają swojego konta usługi Azure AD do rejestrowania urządzenia w usłudze Azure AD i automatycznego rejestrowania go w organizacji&#39;rozwiązania MDM (Azure AD+MDM — wymaga Azure AD — wersja Premium).
- Konta usługi Azure AD obsługują [logowanie pojedyncze.](/azure/active-directory/manage-apps/what-is-single-sign-on) Gdy użytkownik zalogował się do usługi Remote Assist, jego tożsamość z zalogowaonego użytkownika usługi Azure AD zostanie rozpoznana, a użytkownik zostanie zalogowany do aplikacji w celu usprawnienia obsługi.
- Konta usługi Azure AD mają dodatkowe [opcje uwierzytelniania za](/hololens/hololens-identity) [pośrednictwem Windows Hello for Business.](/windows/security/identity-protection/hello-for-business/hello-identity-verification) Oprócz logowania irysów użytkownicy mogą logować się z innego urządzenia lub używać kluczy zabezpieczeń FIDO.

### <a name="mobile-device-management"></a>Zarządzanie urządzeniami przenośnymi

Usługa Microsoft [Intune](/mem/intune/fundamentals/what-is-intune), część usługi Enterprise Mobility + Security, to oparty na chmurze system MDM, który zarządza urządzeniami połączonymi z dzierżawą. Podobnie jak Office 365 usługa Intune używa usługi Azure AD do zarządzania tożsamościami, więc pracownicy używają tych samych poświadczeń do rejestrowania urządzeń w usłudze Intune, których używają do logowania się do Office 365. Usługa Intune obsługuje również urządzenia z innymi systemami operacyjnymi, takimi jak iOS i Android, w celu zapewnienia pełnego rozwiązania MDM. Na potrzeby tego przewodnika skupimy się&#39;usłudze Intune w celu umożliwienia wdrożenia chmury na dużą skalę przy HoloLens 2.

> [!IMPORTANT]
> Ważne jest, aby mieć aplikacje mobilne Zarządzanie urządzeniami. Jeśli nie masz&#39;, postępuj zgodnie z tym przewodnikiem i [rozpoczynanie pracy z usługą Intune.](/mem/intune/fundamentals/free-trial-sign-up)

> [!NOTE]
> Wiele systemów MDM obsługuje Windows 10 i większość scenariuszy wdrażania urządzeń osobistych i firmowych. Dostawcy rozwiązań MDM, którzy obsługują Windows 10 Holographic obecnie obejmują: AirWatch, MobileIron i inni. Większość wiodących w branży dostawców rozwiązań MDM obsługuje już integrację z usługą Azure AD. Dostawców rozwiązań MDM, którzy obsługują usługę Azure AD, można znaleźć w [Azure Marketplace](https://azure.microsoft.com/marketplace/).

## <a name="network"></a>Sieć

W tej konfiguracji przewidujemy, że HoloLens 2 urządzenia łączące się z Internetem z dowolnej dostępnej otwartej Wi-Fi sieci. Ponieważ użytkownik może wymagać zmiany połączenia sieciowego na podstawie lokalizacji, powinien dowiedzieć się, jak połączyć urządzenia HoloLens [z siecią Wi-Fi.](/hololens/hololens-network)

W przypadku usługi Dynamics 365 Remote Assist istnieją różne warunki sieciowe, w tym przepustowość, opóźnienie, zakłócenie i utrata pakietów, które mogą mieć wpływ na środowisko wywoływania wideo. Chociaż wywołania audio i wideo mogą być możliwe w środowiskach z ograniczoną przepustowością, może wystąpić obniżenie jakości funkcji. W przypadku korzystania z usługi Dynamics 365 Remote Assist HoloLens poniżej o wymaganiach dotyczących sieci, które należy mieć na uwadze:

**Minimum:** 1,5 Mb/s w górę/w dół jest wymagane dla równorzędnego wywoływania wideo w jakości HD z rozdzielczością HD 1080p przy rozdzielczości 30 pikseli.

**Optymalne:** W przypadku połączeń wideo w jakości HD typu peer-to-peer o rozdzielczości HD 1080p należy spodziewać się 4–5 Mb/s w górę/w dół.

Więcej informacji:

- [Wymagania dotyczące sieci](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Zalecenia dotyczące optymalizacji sieci](/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>Opcjonalnie: Połączenie połączenie HoloLens siecią VPN

Urządzenia połączone z tym przewodnikiem będą łączyć się z siecią za pośrednictwem sieci i zewnętrznej sieci w chmurze. Być może w celu uzyskania dostępu do zasobów firmy&#39;będzie konieczne połączenie urządzeń za pośrednictwem sieci VPN. Istnieje kilka różnych sposobów łączenia urządzeń z siecią VPN, zarówno w przypadku, gdy użytkownik końcowy może nawiązać połączenie za pośrednictwem interfejsu użytkownika urządzenia, albo urządzenia mogą być zarządzane i odbierać profil sieci VPN z narzędzia PPKG lub MDM. Sposób skonfigurowania sieci VPN nie zostanie&#39;w tym artykule, dlatego jeśli chcesz dowiedzieć się więcej o różnych protokołach sieci VPN lub sposobach zarządzania siecią VPN&#39;, zapoznaj się z tymi przewodnikami, aby uzyskać informacje na temat sieci HoloLens i [VPN.](/hololens/hololens-network#vpn)

## <a name="next-step"></a>Następny krok

> [!div class="nextstepaction"]
> [Wdrożenie połączone z chmurą — konfigurowanie](hololens2-cloud-connected-configure.md)
