---
title: Planowanie wdrożenia urządzenia HoloLens 2 w środowisku komercyjnym
description: Poznaj podstawowe potrzeby dotyczące wdrażania urządzenia HoloLens i zarządzania nim w środowiskach przedsiębiorstwa, w tym infrastruktury, usługi Azure Active Directory i zarządzania urządzeniami przenośnymi.
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
ms.openlocfilehash: 684059b1ab91860dc6af63cbd6f0927876fefb8c
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961482"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>Planowanie wdrożenia urządzenia HoloLens 2 w środowisku komercyjnym

## <a name="overview"></a>Omówienie
> [!NOTE]
> To omówienie ma na celu pomoc specjalistom IT w zrozumieniu kwestii, które należy wziąć pod uwagę podczas wdrażania 2 urządzeń w Microsoft HoloLens i zarządzania nimi w organizacji. Aby rozpocząć pracę, zobacz [Podstawowe informacje](hololens2-setup.md) dla użytkowników końcowych urządzeń.

Urządzenie HoloLens 2 działa na platformie Windows 10 Holographic która zapewnia organizacjom niezawodne, elastyczne, wbudowane technologie zarządzania urządzeniami przenośnymi i aplikacją. Windows 10 Holographic obsługuje zarządzanie całym cyklem życia urządzeń, aby zapewnić firmom kontrolę nad ich urządzeniami, danymi i aplikacjami. Urządzenie HoloLens 2 można łatwo włączyć do standardowych rozwiązań w zakresie cyklu życia, od rejestracji urządzeń, konfiguracji i zarządzania aplikacją po konserwację i wycofanie przy użyciu kompleksowego rozwiązania do zarządzania urządzeniami przenośnymi.

Poniższe kroki mogą pomóc w sposobie wdrożenia urządzenia HoloLens 2 w organizacji.

| | |
|--|--|
| ![Krok 1](images/1green.png)| <br/> **[Typowe scenariusze wdrażania:](hololens-requirements.md)** Poznaj scenariusze wdrażania i poznaj podstawowe składniki potrzebne do wdrożenia urządzeń HoloLens 2. |
| ![Krok 2](images/2green.png)| <br/> **[Przygotowanie:](#prepare)** zapoznaj się z podstawowymi elementami infrastruktury potrzebnymi dla urządzenia HoloLens 2. |
| ![Krok 3](images/3green.png) | <br/> **[Konfigurowanie:](#configure)** dowiedz się, jak skonfigurować podstawowe składniki dla wdrożenia opartego na chmurze. |
| ![Krok 4](images/4green.png) | <br/> **[Wdrażanie:](#deploy)** dowiedz się, jak wdrażać urządzenia oraz bezpiecznie i wydajnie dystrybuować aplikacje. |
| ![Krok 5](images/5green.png) | <br/> **[Obsługa:](#maintain)** dowiedz się, co jest potrzebne do prawidłowego zachowania stanu urządzeń HoloLens 2 i zapewnienia zgodności z zasadami firmowym. |

## <a name="prepare"></a>Przygotowywanie

Dowiedz się więcej o podstawowych usługach infrastruktury wymaganych do obsługi pełnego zestawu funkcji urządzenia HoloLens 2. 

| Składnik | Opis |
|-----------|------------|
| [Azure AD](hololens-identity.md) | Zapewnia zarządzanie tożsamościami i dostępem dla urządzenia HoloLens 2  |
| [Zarządzanie urządzeniami przenośnymi](hololens-mdm-configure.md)| Zarządza urządzeniami HoloLens 2 połączonymi z dzierżawą  |
| [Sieć Wi-Fi](hololens-commercial-infrastructure.md)| Wi-Fi jest dostępna, a urządzenia mogą być połączone z Internetem  |

## <a name="configure"></a>Konfigurowanie

Użyj usługi Intune i rozwiązania Autopilot jako rozwiązań o niskim poziomie dotyku do rejestrowania i konfigurowania urządzenia HoloLens 2 w dzierżawie usługi Azure AD i rozwiązaniu MDM organizacji.

| Składnik | Opis |
|-----------|------------|
| [Automatyczne rejestrowanie](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | Po początkowym zalogowaniu urządzenia automatycznie rejestrują się w usłudze Azure AD i rejestrują się w usłudze MDM  |
| [Licencje aplikacji](hololens2-cloud-connected-configure.md#application-licenses)| Można stosować do użytkowników, grup użytkowników lub grup urządzeń  |
| [Użytkownicy i grupy platformy Azure](hololens2-cloud-connected-configure.md#azure-users-and-groups) | Ułatwia przypisywanie konfiguracji i licencji dla urządzenia HoloLens 2  |

## <a name="deploy"></a>Wdróż

Rozdystrybuuj urządzenia HoloLens 2 i zweryfikuj ich konfigurację. 

| Składnik | Opis |
|-----------|------------|
| [Walidacja rejestracji](hololens2-corp-connected-deploy.md#enrollment-validation) | Sprawdzanie, czy urządzenie jest przyłączone do usługi Azure AD z ustawień lub witryny Azure Portal |
| [Walidacja certyfikatu](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | Sprawdzanie ustawień i sprawdzanie, czy zostały one poprawnie dystrybuowane |
| [Weryfikowanie instalacji aplikacji](hololens2-corp-connected-deploy.md#validate-lob-app-install) | Potwierdzanie, że aplikacja jest obecna i działa na urządzeniach HoloLens 2 |

## <a name="maintain"></a>Obsługa

Używaj Windows Update dla Firm z systemem MDM lub Microsoft Store, aby zachować swoją flotę urządzeń HoloLens 2 i aplikacji na bieżąco.

| Składnik | Opis |
|-----------|------------|
| [Aktualizowanie urządzenia HoloLens 2](hololens-updates.md) | Konfigurowanie aktualizacji zgodnie z potrzebami za pomocą aktualizacji systemu Windows dla firm |
| [Aktualizowanie aplikacji](app-deploy-overview.md) | Konfigurowanie za pośrednictwem systemu MDM lub Microsoft Store
