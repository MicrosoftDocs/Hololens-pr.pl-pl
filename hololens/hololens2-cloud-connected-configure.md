---
title: Przewodnik wdrażania — wdrażanie w HoloLens z chmurą na dużą skalę za pomocą usługi Remote Assist — konfigurowanie
description: Dowiedz się, jak skonfigurować konfiguracje w celu rejestrowania urządzeń HoloLens za pośrednictwem sieci połączonej z chmurą na dużą skalę za pomocą usługi Remote Assist.
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
ms.openlocfilehash: eb96f1cdc799551297c0373268e8cc8f35c6bd06
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033547"
---
# <a name="configure---cloud-connected-guide"></a>Konfigurowanie — przewodnik po połączeniu z chmurą

W tej sekcji przewodnika dowiesz się,&#39;jak skonfigurować rejestrację automatyczną dla dzierżawy i jak stosować licencje dla usługi Intune i usługi Remote Assist.

## <a name="azure-users-and-groups"></a>Użytkownicy i grupy platformy Azure

Platforma Azure i usługa Intune tego rozszerzenia używa użytkowników i grup do przypisywania konfiguracji i licencji. W celu sprawdzania poprawności tego przepływu wdrażania i możliwości wywołania funkcji Remote Assist z jednego użytkownika do innego&#39;będą potrzebne dwa konta użytkowników.

Możemy utworzyć jedną grupę użytkowników na potrzeby przypisywania licencji. Możemy dołączyć obu użytkowników do tej samej grupy i zastosować do niej licencję usługi Intune i usługi Remote Assist.

Jeśli nie&#39;jeszcze dostępu do dwóch kont usługi Azure AD w grupie użytkowników, możesz użyć funkcji . Poniżej znajdują się przewodniki Szybki start dotyczące:

- [Jak utworzyć użytkownika](/mem/intune/fundamentals/quickstart-create-user)
- [Jak utworzyć grupę](/mem/intune/fundamentals/quickstart-create-group)
- [Dodawanie użytkowników do grupy —](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) dodawanie utworzonych użytkowników w celu utworzenia grupy
- [Konfigurowanie usługi Azure AD w celu umożliwienia grupie użytkowników](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) dołączania urządzeń — upewnij się, że nowa grupa użytkowników ma uprawnienia do rejestrowania urządzeń w usłudze Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>Automatyczne rejestrowanie w HoloLens 2

Aby zapewnić bezproblemowe i bezproblemowe środowisko, można skonfigurować dołączanie do usługi Azure Active Directory (AADJ) i automatyczne rejestrowanie w usłudze Intune dla urządzeń z systemem HoloLens 2. Umożliwi to użytkownikom wprowadzanie poświadczeń logowania organizacji podczas OOBE oraz automatyczne rejestrowanie w usłudze Azure AD i rejestrowanie urządzenia w usłudze MDM.

Korzystając z [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), możemy wybierać usługi i nawigować po kilku stronach, dopóki nie wybierzemy opcji Pobierz Premium wersji próbnej. Możesz zauważyć, że istnieje Azure Active Directory — wersja Premium 1 i 2, dla automatycznego rejestrowania P1 jest wystarczająca. Możemy wybrać usługę Intune, wybrać zakres użytkownika dla automatycznej rejestracji, a następnie wybrać grupę, która została wcześniej utworzona.

Aby uzyskać szczegółowe informacje i instrukcje, przeczytaj przewodnik [dotyczący włączania automatycznej rejestracji w usłudze Intune.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="application-licenses"></a>Licencje aplikacji

Licencja aplikacji umożliwia użytkownikowi zainstalowanie aplikacji zakupionych przez firmę lub uaktualnienie bezpłatnej wersji próbnej do pełnej wersji aplikacji. Licencje aplikacji można stosować do użytkowników, grup użytkowników lub grup urządzeń. Aby&#39;funkcji Remote Assist, użytkownicy w organizacji muszą mieć licencje na usługę Remote Assist. Na potrzeby tego przewodnika przypiszemy licencje usługi Remote Assist do grupy użytkowników utworzonej powyżej w grupie [Użytkownicy i grupy platformy Azure.](hololens2-cloud-connected-configure.md#azure-users-and-groups)

Wymagania dotyczące licencji mogą się różnić w zależności od tego, czy użytkownik będzie wołać remote assist z urządzenia, czy będzie współpracownikiem zdalnym z Microsoft Teams. Domyślnie pola wyboru Remote Assist i Teams są oznaczone. Na potrzeby tego przewodnika sugerujemy pozostawienie zaznaczonego pola domyślnego.

1. Dowiedz się więcej o różnych [wymaganiach dotyczących licencjonowania i produktu dla poszczególnych ról.](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role) Istnieje kilka różnych typów licencji usługi Remote Assist, dlatego upewnij się, że są one odpowiednie dla Twoich potrzeb.
2. Musisz&#39;[licencję](/dynamics365/mixed-reality/remote-assist/buy-remote-assist).
3. [Zastosuj licencje do](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) grupy.

## <a name="next-step"></a>Następny krok

> [!div class="nextstepaction"]
> [Wdrożenie połączone z chmurą — wdrażanie](hololens2-cloud-connected-deploy.md)