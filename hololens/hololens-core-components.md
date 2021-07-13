---
title: Planowanie HoloLens 2 w środowisku komercyjnym
description: Poznaj podstawowe potrzeby dotyczące wdrażania aplikacji i zarządzania nimi HoloLens środowiskach przedsiębiorstwa, w tym infrastruktury, usługi Azure Active Directory i zarządzania urządzeniami przenośnymi.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 2fb58345f623a0b70c1fda10b9fb550de70f4c6d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635793"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>Planowanie HoloLens 2 w środowisku komercyjnym

## <a name="overview"></a>Omówienie
> [!NOTE]
> To omówienie ma pomóc specjalistom IT zrozumieć zagadnienia dotyczące wdrażania i zarządzania Microsoft HoloLens 2 urządzeń w organizacji. Aby uzyskać informacje o użytkownikach końcowych urządzeń, zobacz [Get your HoloLens 2 ready to use](hololens2-setup.md) to get started (Przygotuj urządzenie do użycia w celu rozpoczęcia pracy).

HoloLens 2 działa na platformie Windows 10 Holographic która zapewnia organizacjom niezawodne, elastyczne, wbudowane technologie zarządzania urządzeniami przenośnymi i aplikacją. Windows 10 Holographic obsługuje zarządzanie całym cyklem życia urządzeń, aby zapewnić firmom kontrolę nad ich urządzeniami, danymi i aplikacjami. Usługę HoloLens 2 można łatwo włączyć do standardowych rozwiązań w zakresie cyklu życia, od rejestracji urządzeń, konfiguracji i zarządzania aplikacją po konserwację i wycofanie przy użyciu kompleksowego rozwiązania do zarządzania urządzeniami przenośnymi.

Poniższe kroki i wideo mogą pomóc w sposobie wdrożenia HoloLens 2 w organizacji.

| | |
|--|--|
| ![Krok 1](images/1green.png)| <br/> **[Typowe scenariusze wdrażania:](hololens-requirements.md)** Poznaj scenariusze wdrażania i poznaj podstawowe składniki potrzebne do wdrożenia HoloLens 2 urządzeń. |
| ![Krok 2](images/2green.png)| <br/> **[Przygotowanie:](#prepare)** zapoznaj się z podstawowymi elementami infrastruktury wymaganymi HoloLens 2. |
| ![Krok 3](images/3green.png) | <br/> **[Konfigurowanie:](#configure)** dowiedz się, jak skonfigurować podstawowe składniki dla wdrożenia opartego na chmurze. |
| ![Krok 4](images/4green.png) | <br/> **[Wdrażanie:](#deploy)** dowiedz się, jak wdrażać urządzenia oraz bezpiecznie i wydajnie dystrybuować aplikacje. |
| ![Krok 5](images/5green.png) | <br/> **[Obsługa:](#maintain)** dowiedz się, co jest potrzebne do prawidłowego utrzymania stanu urządzeń z systemem HoloLens 2 i zapewnienia zgodności z zasadami firmowym. |

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a>Przygotowywanie

Dowiedz się więcej o podstawowych usługach infrastruktury wymaganych do obsługi pełnego zestawu HoloLens 2. 

| Składnik | Opis |
|-----------|------------|
| [Azure AD](hololens-identity.md) | Zapewnia zarządzanie tożsamościami i dostępem dla HoloLens 2  |
| [Zarządzanie urządzeniami przenośnymi](hololens-mdm-configure.md)| Zarządza 2 HoloLens połączonymi z dzierżawą  |
| [Sieć Wi-Fi](hololens-commercial-infrastructure.md)| Wi-Fi jest dostępna, a urządzenia mogą być połączone z Internetem  |

## <a name="configure"></a>Konfigurowanie

Użyj usługi Intune i rozwiązania Autopilot jako rozwiązań o niskim poziomie dotyku do rejestrowania i konfigurowania HoloLens 2 w dzierżawie usługi Azure AD i rozwiązaniu MDM organizacji.

| Składnik | Opis |
|-----------|------------|
| [Automatyczne rejestrowanie](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | Po początkowym zalogowaniu urządzenia automatycznie rejestrują się w usłudze Azure AD i rejestrują się w usłudze MDM  |
| [Licencje aplikacji](hololens2-cloud-connected-configure.md#application-licenses)| Można stosować do użytkowników, grup użytkowników lub grup urządzeń  |
| [Użytkownicy i grupy platformy Azure](hololens2-cloud-connected-configure.md#azure-users-and-groups) | Ułatwia przypisywanie konfiguracji i licencji dla HoloLens 2  |

## <a name="deploy"></a>Wdróż

Rozdystrybuuj HoloLens 2 urządzenia i zweryfikuj ich konfigurację. 

| Składnik | Opis |
|-----------|------------|
| [Walidacja rejestracji](hololens2-corp-connected-deploy.md#enrollment-validation) | Sprawdzanie, czy urządzenie jest przyłączone do usługi Azure AD z Ustawienia lub witryny Azure Portal |
| [Walidacja certyfikatu](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | Sprawdzanie ustawień i sprawdzanie, czy zostały one poprawnie dystrybuowane |
| [Weryfikowanie instalacji aplikacji](hololens2-corp-connected-deploy.md#validate-lob-app-install) | Potwierdzanie, że aplikacja jest obecna i działa na komputerze HoloLens 2 |

## <a name="maintain"></a>Obsługa

Użyj Windows Update for Business wraz z systemem MDM lub Microsoft Store, aby zachować swoją flotę HoloLens 2 i aplikacji.

| Składnik | Opis |
|-----------|------------|
| [Aktualizacja HoloLens 2](hololens-updates.md) | Konfigurowanie aktualizacji zgodnie z potrzebami za pomocą Windows Updates for Business |
| [Aktualizowanie aplikacji](app-deploy-overview.md) | Konfigurowanie za pośrednictwem systemu MDM lub Microsoft Store
