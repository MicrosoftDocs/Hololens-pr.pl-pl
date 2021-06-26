---
title: Planowanie wdrożenia urządzenia HoloLens 2 w środowisku komercyjnym
description: Dowiedz się więcej na temat wdrażania urządzenia HoloLens i zarządzania nim w środowiskach przedsiębiorstwa, w tym w infrastrukturze, Azure Active Directory i zarządzaniu urządzeniami przenośnymi.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bogenera
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 2a0933bb754043934621a22ffa7764c9c88d93da
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924608"
---
# <a name="common-deployment-scenarios"></a>Typowe scenariusze wdrażania

## <a name="overview"></a>Omówienie

Ta strona zawiera ogólne omówienie architektury dla trzech typowych scenariuszy wdrażania i zarządzania Microsoft HoloLens 2 urządzeń w przedsiębiorstwie.

Często sposób zarządzania urządzeniami i uzyskiwania dostępu do zasobów organizacji jest w dużej mierze określany przez już używane czynniki. Na podstawie istniejącej infrastruktury zachęcamy do przejrzenia wspólnego stylu zarządzania urządzeniami (MDM) w następujących scenariuszach, a następnie przeczytania tematu Planowanie wdrożeń urządzenia [HoloLens 2](hololens-core-components.md) w środowisku komercyjnym, aby określić, który scenariusz odpowiada Twoim potrzebom. Dostępne są również trzy odpowiednie przewodniki do użycia podczas wdrażania.


 1. [Przewodnik wdrażania środowiska połączonego z chmurą](hololens2-cloud-connected-overview.md)
     1. [Przewodnik wdrażania środowiska połączonego z chmurą (klientów zewnętrznych)](hololens2-deployment-guide.md)
 1. [Przewodnik wdrażania sieci firmowej](hololens2-corp-connected-overview.md)
 1. [Przewodnik wdrażania bezpiecznego środowiska w trybie offline](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Scenariusz A: wdrażanie na urządzeniach połączonych z chmurą

Ten scenariusz jest porównywalny z wdrażaniem zarządzanych urządzeń przenośnych w firmie. Urządzenie HoloLens 2 jest wdrażane głównie w środowiskach zewnątrz sieci firmowej. Zasoby firmowe nie są dostępne lub mogą być ograniczone za pośrednictwem sieci VPN. 
 * Podstawowe typowe konfiguracje
   * Wi-Fi są zwykle w pełni otwarte dla Internetu i usług w chmurze.
   * Azure AD Join with Mobile Zarządzanie urządzeniami (MDM) Auto Enrollment--MDM (Intune) Managed
   * Użytkownicy logują się przy użyciu własnego konta firmowego (Azure AD)
     * Obsługiwanych jest jeden lub wielu użytkowników na urządzenie
   * Różne poziomy konfiguracji blokady urządzeń są stosowane w zależności od konkretnych przypadków użycia, od pełnego otwarcia do kiosku z jedną aplikacją.
   * Co najmniej jedna aplikacja jest wdrażana za pośrednictwem rozwiązania MDM

* Typowe wyzwania
   * Określanie, które konfiguracje zarządzania urządzeniami przenośnymi mają być stosowane do urządzenia HoloLens 2, na podstawie wymagań scenariusza.

[![Diagram scenariusza ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

W odpowiednim przewodniku po chmurze opisano sposób rejestrowania urządzenia HoloLens 2 w usłudze zarządzania urządzeniami, stosowania licencji zgodnie z potrzebami i sprawdzania, czy użytkownicy końcowi mogą natychmiast korzystać z usługi Remote Assist podczas konfigurowania urządzenia. Przewodnik Klienci zewnętrzni umożliwia wdrażanie urządzeń w lokacji zdalnej do krótkoterminowego lub długoterminowego użytku zewnętrznego.

> [!div class="nextstepaction"]
> [Przewodnik wdrażania środowiska połączonego z chmurą](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [Przewodnik wdrażania środowiska połączonego z chmurą (klientów zewnętrznych)](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Scenariusz B: wdrażanie w sieci organizacji

Ten scenariusz jest identyczny z klasycznym wdrożeniem dla większości Windows 10 komputerów. Urządzenie HoloLens 2 jest wdrażane do użytku głównie w sieci firmowej z dostępem do wewnętrznych zasobów firmy. Usługi internetowe i w chmurze mogą być ograniczone. 

 * Podstawowe typowe konfiguracje
   * Wi-Fi to wewnętrzna sieć firmowa z dostępem do zasobów wewnętrznych i ograniczonym dostępem do Internetu lub usług w chmurze.
   * Dołączanie do usługi Azure AD z automatyczną rejestracją w usłudze MDM
   * Zarządzanie urządzeniami przenośnymi (Intune)
   * Użytkownicy logują się przy użyciu własnego konta firmowego (Azure AD)
     * Obsługiwanych jest jeden lub wielu użytkowników na urządzenie
   * Różne poziomy konfiguracji blokady urządzeń są stosowane w zależności od konkretnych przypadków użycia, od pełnego otwarcia do kiosku z jedną aplikacją.
   * Co najmniej jedna aplikacja jest wdrażana za pośrednictwem rozwiązania MDM

 * Typowe wyzwania
   * Urządzenie HoloLens 2 nie obsługuje lokalnego dołączania do usługi AD ani programu SCCM. Tylko dołączanie do usługi Azure AD za pomocą rozwiązania MDM. Obecnie wiele firm nadal wdraża komputery z systemem Windows 10 jako lokalne urządzenia przyłączone do usługi AD, zarządzane przez usługę System Center Menedżer konfiguracji (SCCM) i mogą nie mieć wdrożonej/skonfigurowanej infrastruktury do zarządzania wewnętrznymi urządzeniami Windows 10 za pośrednictwem rozwiązań MDM opartych na chmurze.
   * Urządzenie HoloLens 2 jest pierwszym urządzeniem w chmurze, dlatego w dużym stopniu opiera się na usługach połączonych z Internetem i w chmurze na temat uwierzytelniania użytkowników, aktualizacji systemu operacyjnego, zarządzania urządzeniami przenośnymi i tak dalej. Podczas nawiązywania połączenia z siecią firmową reguły serwera proxy/zapory najprawdopodobniej trzeba będzie dostosować, aby umożliwić dostęp do urządzenia HoloLens 2 i aplikacji, które na nim działają.
   * Połączenia Wi-Fi zwykle wymagają certyfikatów w celu uwierzytelnienia urządzenia lub użytkownika w sieci. Skonfigurowanie wymaganej infrastruktury lub ustawień do wdrażania certyfikatów na Windows 10 za pośrednictwem zarządzania urządzeniami przenośnymi może być trudne.

[![Diagram scenariusza B1 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagram scenariusza B2 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

Odpowiedni przewodnik po sieci firmowej zawiera wskazówki dotyczące rejestrowania urządzenia HoloLens 2 w istniejącym zarządzaniu urządzeniami, stosowania licencji zgodnie z potrzebami i sprawdzania, czy użytkownicy końcowi mogą korzystać z przewodnika usługi Dynamics 365, a także używania niestandardowych aplikacji biznesowych po skonfigurowaniu urządzenia.

> [!div class="nextstepaction"]
> [Przewodnik wdrażania sieci firmowej](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Scenariusz C: wdrażanie w bezpiecznym środowisku offline

Jest to typowe wdrożenie dla wysoce bezpiecznych lub poufnych lokalizacji. Urządzenie HoloLens 2 jest wdrażane do użytku głównie w trybie offline bez dostępu do sieci ani Internetu. 
 * Podstawowe typowe konfiguracje
   * Wi-Fi jest wyłączona. W razie potrzeby można włączyć łączność z siecią LAN za pośrednictwem portu ETHERNET za pośrednictwem portu USB.
   * Nie zarządzana.
   * Konto użytkownika lokalnego do logowania urządzenia.
     * Urządzenie HoloLens 2 obsługuje tylko jedno konto lokalne.
   * Różne poziomy konfiguracji blokady urządzeń są stosowane za pośrednictwem pakietów aprowiwizowania na podstawie określonych przypadków użycia. Te konfiguracje są zwykle ograniczone ze względu na wymagania dotyczące bezpiecznego środowiska.
   * Co najmniej jedna aplikacja jest wdrażana za pośrednictwem pakietu aprowizowania

 * Typowe wyzwania
   * Istnieje ograniczony zestaw konfiguracji dostępny za pośrednictwem pakietów aprowizowania
   * Nie można używać usług w chmurze, co ogranicza możliwości urządzenia HoloLens 2.
   * Wyższe koszty administracyjne, ponieważ te urządzenia muszą być konfigurowane, konfigurowane i aktualizowane ręcznie.

[![Bezpieczny diagram trybu offline 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

Odpowiedni bezpieczny przewodnik w trybie offline zawiera instrukcje stosowania przykładowego pakietu aprowizowania, który zablokuje urządzenie HoloLens 2 do użycia w bezpiecznych środowiskach.

> [!div class="nextstepaction"]
> [Przewodnik wdrażania bezpiecznego środowiska w trybie offline](hololens-common-scenarios-offline-secure.md)


