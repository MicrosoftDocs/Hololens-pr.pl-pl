---
title: Omówienie urządzenia HoloLens 2 połączonego z chmurą z usługą Remote Assist
description: Dowiedz się, jak zarejestrować urządzenia HoloLens 2 za pośrednictwem sieci połączonej z chmurą przy użyciu usługi Dynamics 365 Remote Assist.
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
ms.openlocfilehash: a44247b4afea747e4b75c974fcae344380909989
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923537"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Przewodnik wdrażania — urządzenie HoloLens 2 połączone z chmurą z usługą Remote Assist — omówienie

Ten przewodnik pomoże specjalistom IT w planowaniu i wdrażaniu Microsoft HoloLens 2 urządzeń z usługą Remote Assist w organizacji. Będzie to model wdrożeń weryfikacji koncepcji w organizacji w różnych przypadkach użycia urządzenia HoloLens 2. Konfiguracja jest podobna do scenariusza [A: wdrażanie na urządzeniach podłączonych do chmury.](https://docs.microsoft.com/hololens/common-scenarios#scenario-a) 

W tym przewodniku opisano sposób rejestrowania urządzeń w zarządzaniu urządzeniami, stosowania licencji zgodnie z potrzebami i sprawdzania, czy użytkownicy końcowi mogą natychmiast korzystać z usługi Remote Assist podczas konfigurowania urządzenia. W tym celu przejmiemy ważne elementy infrastruktury potrzebne do skonfigurowania i uruchomienia — osiągnięcie wdrożenia na dużą skalę za pomocą urządzenia HoloLens 2. W tym przewodniku nie będą stosowane żadne inne ograniczenia ani konfiguracje dotyczące urządzeń, jednak zachęcamy do eksplorowania tych opcji po zakończeniu.

## <a name="prerequisites"></a>Wymagania wstępne

Aby wdrożyć urządzenie HoloLens 2, należy wdrożyć następującą infrastrukturę. Jeśli nie, konfigurowanie platformy Azure i usługi Intune jest uwzględnione w tym przewodniku:

- Wi-Fi
    - Sieci są zwykle otwarte dla Internetu i usług w chmurze
- Azure Active Directory (Azure AD) Join with MDM Auto Enrollment (Wymagane są subskrypcje[usługi Azure AD P1)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
- Zarządzanie urządzeniami przenośnymi (Intune)
    - Co najmniej jedna aplikacja jest wdrażana za pośrednictwem rozwiązania MDM.
- Użytkownicy logują się przy użyciu własnego konta firmowego (Azure AD)
    - Obsługiwana jest jedna lub wielu użytkowników na urządzenie.

:::image type="content" alt-text="Scenariusz połączony z chmurą" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a>Dowiedz się więcej na temat usługi Remote Assist

Usługa Remote Assist umożliwia współpracę w zakresie konserwacji i naprawy, zdalną inspekcję, a także udostępnianie i szkolenie wiedzy. Łącząc osoby w różnych rolach i lokalizacjach, technik korzystający z usługi Remote Assist może nawiązać połączenie ze zdalnym współpracownikiem w aplikacji Microsoft Teams. Mogą łączyć filmy wideo, zrzuty ekranu i adnotacje, aby rozwiązywać problemy w czasie rzeczywistym nawet wtedy, gdy&#39;nie w tej samej lokalizacji. Zdalni współpracownicy mogą wstawiać obrazy referencyjne, schematy i inne przydatne informacje, które technik&#39;w przestrzeni fizycznej, dzięki czemu mogą odwoływać się do schematu podczas pracy na urządzeniach HoloLens bez pracy praktycznej i pracy na urządzeniach HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a>Licencjonowanie i wymagania dotyczące usługi Remote Assist

- Konto usługi Azure AD (wymagane do zakupu subskrypcji i przypisywania licencji)
- [Subskrypcja usługi Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (lub [wersja próbna usługi Remote Assist)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)
    
#### <a name="dynamics-365-remote-assist-user"></a>Użytkownik usługi Dynamics 365 Remote Assist

- Licencja usługi Remote Assist
- Łączność sieciowa

#### <a name="microsoft-teams-user"></a>Użytkownik aplikacji Microsoft Teams

- Microsoft Teams lub [Teams Freemium](https://products.office.com/microsoft-teams/free).
- Łączność sieciowa

Jeśli planujesz wdrożenie tego scenariusza między [dzierżawami,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)być może potrzebujesz licencji Information Barriers. Zapoznaj [się z tym artykułem,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) aby ustalić, czy jest wymagana licencja information barrier.

## <a name="in-this-guide-you-will"></a>Ten przewodnik zawiera informacje na temat:

Przygotować:

> [!div class="checklist"]
> - [Dowiedz się więcej na temat podstawowych informacji o infrastrukturze dla urządzeń HoloLens 2.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Dowiedz się więcej o usłudze Azure AD i skonfiguruj ją, jeśli&#39;jej nie masz.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Dowiedz się więcej na temat zarządzania tożsamościami i sposobu najlepszego skonfigurowania kont usługi Azure AD.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Dowiedz się więcej na temat zarządzania urządzeniami przenośnymi i skonfiguruj usługę Intune, jeśli&#39;jeszcze nie jest gotowa.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Dowiedz się więcej o wymaganiach dotyczących sieci usługi Remote Assist.](hololens2-cloud-connected-prepare.md#network)
> - [Opcjonalnie: sieć VPN do łączenia się z zasobami organizacji](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Skonfiguruj:

> [!div class="checklist"]
> - [Jak utworzyć użytkowników i grupy.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Jak skonfigurować automatyczne rejestrowanie w usłudze Azure AD.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Jak przypisać licencje aplikacji.](hololens2-cloud-connected-configure.md#application-licenses)

Wdrażanie:

> [!div class="checklist"]
> - [Skonfiguruj urządzenie HoloLens 2 i zweryfikuj rejestrację.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Sprawdź, czy można wykonać wywołanie funkcji Remote Assist.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Utrzymania:

> [!div class="checklist"]
> - [Jak zaktualizować usługę Remote Assist przy użyciu Microsoft Store aplikacji.](hololens2-cloud-connected-maintain.md#updates)
> - [Tworzenie planu pomocy technicznej.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Plan rozwoju.](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>Następny krok

> [!div class="nextstepaction"]
> [Wdrożenie połączone z chmurą — przygotowanie](hololens2-cloud-connected-prepare.md)

