---
title: Typowe scenariusze wdrażania
description: Dowiedz się więcej o wdrażaniu aplikacji i HoloLens w środowiskach przedsiębiorstw, w tym w infrastrukturze, Azure Active Directory i zarządzaniu urządzeniami przenośnymi.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bgener
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 4b8975d8eb362212eaf91966f4efa0bc22236327
ms.sourcegitcommit: 3f21b692be2f1b7f9c382f2b735b4c10339d4a78
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2021
ms.locfileid: "127934072"
---
# <a name="common-deployment-scenarios"></a>Typowe scenariusze wdrażania

## <a name="overview"></a>Omówienie

Ustalenie, jak wdrożyć nowe urządzenie, może być problem, gdy spróbujesz go po raz pierwszy. W tym miejscu udostępniamy różne sposoby wdrażania 2 urządzeń w organizacji Microsoft HoloLens zarządzania nimi.

Potrzebujesz rozwiązań wdrażanych na dużą skalę. Chcemy Cię tam zabrać. Najpierw omówmy kroki wdrażania urządzeń, w związku z tym hologramów, w celu osiągnięcia wartości dla docelowego scenariusza rzeczywistości mieszanej. Bez względu na to, czy używasz pomocy zdalnej usługi D365, przewodników, czy utworzonej aplikacji z obsługą usługi rzeczywistości mieszanej platformy Azure, nasze typowe scenariusze wdrażania będą kierować Twoją podróżą.

Możesz być twórcą decyzji biznesowych, specjalistą IT lub zespołem ds. innowacji, który chce HoloLens w organizacji. Podczas tworzenia od weryfikacji koncepcji do wdrożenia skalowanego nasze przewodniki wdrażania mają sens HoloLens infrastruktury IT — niezależnie od tego, jak duże i małe. Najczęściej spotykane są następujące scenariusze wdrażania:

| Scenariusz |Użycie | Kwestie kluczowe |
|---------|---------|---------|
| [Scenariusz A: Urządzenia połączone z chmurą](hololens2-cloud-connected-overview.md) | Po pierwszym rozpoczęciu wdrażania możesz zacząć od małej ilości danych i wdrożyć jedno urządzenie połączone z chmurą, aby zobaczyć podstawowy proces. | Urządzenia będą połączone z usługami w chmurze i publicznym Internetem. Jest to najbardziej odpowiednie w przypadku przypadków użycia klienta, usług terenowych i weryfikacji koncepcji.|
| [Scenariusz B: sieć organizacji](hololens2-corp-connected-overview.md) | Podczas wdrażania w środowisku produkcyjnym na dużą skalę może być konieczne zintegrowanie z siecią organizacji. | Urządzenia będą połączone z firmową siecią Wi-Fi. Jest to najbardziej odpowiednie dla użytkowników wewnętrznych lub w środowisku firmowym.|
| [Scenariusz C: Bezpieczne środowisko w trybie offline](hololens-common-scenarios-offline-secure.md) | Niektóre procesy o znaczeniu krytycznym lub niektóre zasady firmowe mogą wymagać użycia środowisk w trybie offline. | Urządzenia będą połączone z wysoce restrykcyjną siecią lub będą urządzeniami wyłącznie w trybie offline. Jest to najbardziej odpowiednie dla środowisk o wysokim stopniu bezpieczeństwa lub ograniczeń łączności z Internetem w obszarach zdalnych. |

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Scenariusz A: wdrażanie na urządzeniach połączonych z chmurą

Ten scenariusz jest porównywalny z wdrażaniem zarządzanych urządzeń przenośnych w firmie. HoloLens 2 jest wdrażany głównie w środowiskach zewnątrz sieci firmowej. Zasoby firmowe nie są dostępne lub mogą być ograniczone za pośrednictwem sieci VPN.

[![Scenariusz Diagram.](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

### <a name="when-to-use"></a>Kiedy stosować

Rozważ ten model wdrażania dla:

* Wdrażanie weryfikacji koncepcji, pilotażowych i usług terenowych
* Wdrażanie [zdalnej pomocy](hololens2-options-remote-assist.md)

### <a name="basic-common-configurations"></a>Podstawowe typowe konfiguracje

* Wi-Fi są zwykle w pełni otwarte dla Internetu i usług w chmurze
* Azure AD Join with Mobile Zarządzanie urządzeniami (MDM) Auto Enrollment--MDM (Intune) Managed
* Użytkownicy logują się przy użyciu własnego konta firmowego (Azure AD)
  * Obsługiwanych jest jeden lub wielu użytkowników na urządzenie
* Różne poziomy konfiguracji blokady urządzeń są stosowane na podstawie konkretnych przypadków użycia, od pełnego otwarcia do kiosku z jedną aplikacją.
* Co najmniej jedna aplikacja jest wdrażana za pośrednictwem rozwiązania MDM

### <a name="common-challenges"></a>Typowe wyzwania

* Określanie, które konfiguracje zarządzania urządzeniami przenośnymi mają być stosowane do HoloLens 2 na podstawie wymagań scenariusza

W odpowiednim przewodniku po chmurze opisano sposób rejestrowania usługi HoloLens 2 w usłudze zarządzania urządzeniami, stosowania licencji zgodnie z potrzebami i sprawdzania, czy użytkownicy końcowi mogą natychmiast korzystać z usługi Remote Assist podczas konfigurowania urządzenia.

> [!div class="nextstepaction"]
> [Przewodnik wdrażania połączony z chmurą](hololens2-cloud-connected-overview.md)

Przewodnik Klienci zewnętrzni umożliwia wdrażanie urządzeń w lokacji zdalnej do krótkoterminowego lub długoterminowego użytku zewnętrznego.

> [!div class="nextstepaction"]
> [Przewodnik wdrażania połączonych z chmurą (klientów zewnętrznych)](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Scenariusz B: wdrażanie w sieci organizacji

Ten scenariusz jest identyczny z klasycznym wdrożeniem dla większości Windows 10 komputerów. HoloLens 2 jest wdrażany do użytku głównie w sieci firmowej z dostępem do wewnętrznych zasobów firmy. Usługi internetowe i w chmurze mogą być ograniczone. 

[![Diagram scenariusza B1.](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagram scenariusza B2.](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

### <a name="when-to-use"></a>Kiedy stosować

Rozważ ten model wdrażania dla:

* Użytkownicy wewnętrzni
* Wdrażanie na dużą skalę (pilotażowe i produkcyjne) w środowisku firmowym

### <a name="basic-common-configurations"></a>Podstawowe typowe konfiguracje

* Wi-Fi to wewnętrzna sieć firmowa z dostępem do zasobów wewnętrznych i ograniczonym dostępem do Internetu lub usług w chmurze.
* Dołączanie do usługi Azure AD z automatyczną rejestracją w usłudze MDM
* Zarządzanie urządzeniami przenośnymi (Intune)
* Użytkownicy logują się przy użyciu własnego konta firmowego (Azure AD)
  * Obsługiwanych jest jeden lub wielu użytkowników na urządzenie
* Różne poziomy konfiguracji blokady urządzeń są stosowane na podstawie konkretnych przypadków użycia, od pełnego otwarcia do kiosku z jedną aplikacją.
* Co najmniej jedna aplikacja jest wdrażana za pośrednictwem rozwiązania MDM

### <a name="common-challenges"></a>Typowe wyzwania

* HoloLens 2 nie obsługuje lokalnego dołączania do usługi AD ani System Center Configuration Manager (SCCM). Tylko dołączanie do usługi Azure AD za pomocą rozwiązania MDM. Obecnie wiele firm nadal wdraża komputery z systemem Windows 10 w tym scenariuszu jako lokalne urządzenia przyłączone do usługi AD, zarządzane przez program SCCM i mogą nie mieć wdrożonej/skonfigurowanej infrastruktury do zarządzania wewnętrznymi urządzeniami Windows 10 za pośrednictwem rozwiązań MDM opartych na chmurze.
* Ponieważ HoloLens 2 jest urządzeniem w chmurze, w dużym stopniu opiera się na usługach połączonych z Internetem i w chmurze na temat uwierzytelniania użytkowników, aktualizacji systemu operacyjnego, zarządzania urządzeniami przenośnymi i tak dalej. Podczas nawiązywania połączenia z siecią firmową reguły serwera proxy/zapory najprawdopodobniej trzeba będzie dostosować, aby umożliwić dostęp do serwera HoloLens 2 i aplikacji, które na nim działają.
* Połączenia Wi-Fi zwykle wymagają certyfikatów w celu uwierzytelnienia urządzenia lub użytkownika w sieci. Skonfigurowanie wymaganej infrastruktury lub ustawień do wdrażania certyfikatów na urządzeniach Windows 10 mdm może być trudne.

W odpowiednim przewodniku po połączeniu firmowym poinstruuje się, jak zarejestrować usługę HoloLens 2 w istniejącym zarządzaniu urządzeniami, zastosować licencje zgodnie z potrzebami i zweryfikować, czy użytkownicy końcowi mogą korzystać z przewodnika usługi Dynamics 365, a także jak korzystać z niestandardowych aplikacji biznesowych po skonfigurowaniu urządzenia.

> [!div class="nextstepaction"]
> [Przewodnik wdrażania po połączeniu firmowym](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Scenariusz C: wdrażanie w bezpiecznym środowisku offline

Jest to typowe wdrożenie dla wysoce bezpiecznych lub poufnych lokalizacji. HoloLens 2 jest wdrażany głównie w trybie offline bez dostępu do sieci ani Internetu.

[![Bezpieczny diagram 1 w trybie offline.](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

### <a name="when-to-use"></a>Kiedy stosować

Rozważ ten model wdrażania dla:

* Wysoce bezpieczne środowiska, w których dane muszą być przechowywane w domu
* "Środowisko", w którym publiczna będzie używać urządzeń
* Problem z łącznością z Internetem w obszarze zdalnym

### <a name="basic-common-configurations"></a>Podstawowe typowe konfiguracje

* Wi-Fi łączność jest wyłączona. W razie potrzeby można włączyć łączność z siecią LAN za pośrednictwem portu ETHERNET za pośrednictwem portu USB
* Nie zarządzana
* Konto użytkownika lokalnego do logowania urządzenia
  * HoloLens 2 obsługuje tylko jedno konto lokalne
* Różne poziomy konfiguracji blokady urządzeń są stosowane za pośrednictwem pakietów aprowiwizowania na podstawie określonych przypadków użycia. Te konfiguracje są zwykle ograniczone ze względu na wymagania dotyczące bezpiecznego środowiska
* Co najmniej jedna aplikacja jest wdrażana za pośrednictwem pakietu aprowizowania

### <a name="common-challenges"></a>Typowe wyzwania

* Istnieje ograniczony zestaw konfiguracji dostępny za pośrednictwem pakietów aprowizowania
* Nie można używać usług w chmurze, co ogranicza możliwości HoloLens 2.
* Wyższe koszty administracyjne, ponieważ te urządzenia muszą być konfigurowane, konfigurowane i aktualizowane ręcznie.

Odpowiedni bezpieczny przewodnik w trybie offline zawiera instrukcje stosowania przykładowego pakietu aprowizowania, który zablokuje pakiet HoloLens 2 do użycia w bezpiecznych środowiskach.

> [!div class="nextstepaction"]
> [Przewodnik wdrażania bezpiecznego środowiska w trybie offline](hololens-common-scenarios-offline-secure.md)
