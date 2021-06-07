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
ms.openlocfilehash: 43fbcc3a841f6c3f15006f285188e55d22f10599
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378247"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Przewodnik wdrażania — urządzenie HoloLens 2 połączone z chmurą ze zdalną asystą — omówienie

Ten przewodnik pomaga specjalistom IT w planowaniu i wdrażaniu urządzeń z systemem Microsoft HoloLens 2 w organizacji w ogólnym celu, aby chmura tych urządzeń była połączona z twoją organizacją przy użyciu usługi Dynamics 365 Remote Assist gotowej do użycia. Należy pamiętać, że będzie to model wdrożeń weryfikacji koncepcji w organizacji w różnych przypadkach użycia urządzenia HoloLens 2.

W tym przewodniku opisano sposób rejestrowania urządzeń w zarządzaniu urządzeniami, stosowania licencji zgodnie z potrzebami i sprawdzania, czy użytkownicy końcowi mogą natychmiast korzystać z usługi Remote Assist podczas konfigurowania urządzenia. W tym celu przejmiemy ważne elementy infrastruktury potrzebne do skonfigurowania i uruchomienia — osiągnięcie wdrożenia na dużą skalę za pomocą urządzenia HoloLens 2.

[![Scenariusz połączony z chmurą ](./images/deployment-guides-revised-scenario-a.png)](./images/deployment-guides-revised-scenario-a.png#lightbox)
## <a name="in-this-guide"></a>W tym przewodniku

Celem tego przewodnika jest skonfigurowanie usługi Remote Assist w organizacji na urządzeniach HoloLens. Zostaną pokrytą koniecznością niezbędną do osiągnięcia tego celu. Aby można było skupić się na tym celu, niektóre przygotowania i konfiguracje zostaną wstępnie wybrane w celu zoptymalizowania pod kątem tego wdrożenia lub zmniejszenia ilości elementów wymaganych do skonfigurowania. Będziesz mieć informacje o tych wyborach i będziesz w stanie dostosować wdrożenie do swoich potrzeb biznesowych.

Jest to konfiguracja podobna do scenariusza [A:](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)wdrażanie na urządzeniach z połączeniami w chmurze, co jest dobrą opcją dla wielu wdrożeń weryfikacji koncepcji, które obejmują:

- Wi-Fi są zwykle w pełni otwarte dla Internetu i usług w chmurze
- Dołączanie do usługi Azure AD z automatyczną rejestracją w usłudze MDM — zarządzane przez rozwiązanie MDM (Intune)
- Użytkownicy logują się przy użyciu własnego konta firmowego (Azure AD)
  - Obsługiwanych jest jeden lub wielu użytkowników na urządzenie
- Różne poziomy konfiguracji blokady urządzeń są stosowane na podstawie konkretnych przypadków użycia, od całkowitego otwarcia do kiosku z jedną aplikacją



W tym przewodniku nie będą stosowane żadne inne ograniczenia ani konfiguracje urządzeń, jednak zachęcamy do eksplorowania tych opcji po zakończeniu.

## <a name="learn-about-remote-assist"></a>Dowiedz się więcej o pomocy zdalnej

Usługa Remote Assist umożliwia wspólną konserwację i naprawę, zdalną inspekcję, a także udostępnianie i szkolenie wiedzy. Łącząc osoby w różnych rolach i lokalizacjach, technik korzystający z usługi Remote Assist może nawiązać połączenie ze zdalnym współpracownikiem w aplikacji Microsoft Teams. Mogą one łączyć wideo, zrzuty ekranu i adnotacje, aby rozwiązywać problemy w czasie rzeczywistym, nawet&#39;nie w tej samej lokalizacji. Zdalni współpracownicy mogą wstawiać obrazy referencyjne, schematy i inne przydatne informacje, które technik&#39;w fizycznej przestrzeni, dzięki czemu mogą odwoływać się do schematu podczas pracy z orzełami i bez rąk na urządzeniach HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a>Ten przewodnik zawiera informacje na temat:

Przygotować:

> [!div class="checklist"]
> - [Dowiedz się więcej na temat podstawowych informacji o infrastrukturze dla urządzeń HoloLens 2.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Dowiedz się więcej o usłudze Azure AD i skonfiguruj ją, jeśli&#39;jej nie masz.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Dowiedz się więcej na temat zarządzania tożsamościami i sposobu najlepszego skonfigurowania kont usługi Azure AD.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Dowiedz się więcej na temat zarządzania urządzeniami przenośnymi i skonfiguruj usługę Intune, jeśli&#39;jeszcze nie jest gotowa.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Dowiedz się więcej o wymaganiach dotyczących sieci usługi Remote Assist.](hololens2-cloud-connected-prepare.md#network)
> - [Opcjonalnie: sieć VPN do łączenia się z zasobami organizacji](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Skonfiguruj:

> [!div class="checklist"]
> - [Jak utworzyć użytkowników i grupy.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Jak skonfigurować automatyczne rejestrowanie w usłudze Azure AD.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Jak przypisać licencje aplikacji.](hololens2-cloud-connected-configure.md#application-licenses)

Wdrażanie:

> [!div class="checklist"]
> - [Skonfiguruj urządzenie HoloLens 2 i zweryfikuj rejestrację.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Zweryfikuj, czy można wykonać wywołanie funkcji Remote Assist.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Utrzymania:

> [!div class="checklist"]
> - [Jak zaktualizować usługę Remote Assist przy użyciu Microsoft Store aplikacji.](hololens2-cloud-connected-maintain.md#updates)
> - [Tworzenie planu pomocy technicznej.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Plan rozwoju.](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>Następny krok

> [!div class="nextstepaction"]
> [Wdrożenie połączone z chmurą — przygotowanie](hololens2-cloud-connected-prepare.md)

