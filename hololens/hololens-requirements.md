---
title: Typowe scenariusze wdrażania
description: Dowiedz się więcej na temat wdrażania i zarządzania HoloLens w środowiskach przedsiębiorstw, w tym infrastruktury, Azure Active Directory i zarządzania urządzeniami przenośnymi.
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
ms.openlocfilehash: 72b9e61c52d6f4f08cf5a29baf7b01c29fae7489
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635470"
---
# <a name="common-deployment-scenarios"></a>Typowe scenariusze wdrażania

## <a name="overview"></a>Omówienie

Ta strona zawiera ogólne omówienie architektury dla trzech typowych scenariuszy wdrażania i zarządzania Microsoft HoloLens 2 urządzeń w przedsiębiorstwie.

Często sposób zarządzania urządzeniami i uzyskiwania dostępu do zasobów organizacji jest w dużej mierze określany przez już używane czynniki. Na podstawie istniejącej infrastruktury zachęcamy do przejrzenia wspólnego stylu zarządzania urządzeniami (MDM) w następujących scenariuszach, a następnie przeczytania tematu Planowanie [wdrożeń programu HoloLens 2](hololens-core-components.md) w środowisku komercyjnym w celu określenia, który scenariusz odpowiada Twoim potrzebom. Dostępne są również trzy odpowiednie przewodniki do użycia podczas wdrażania.


 1. [Przewodnik wdrażania środowiska połączonego z chmurą](hololens2-cloud-connected-overview.md)
     1. [Przewodnik wdrażania środowiska połączonego z chmurą (klientów zewnętrznych)](hololens2-deployment-guide.md)
 1. [Przewodnik wdrażania sieci firmowej](hololens2-corp-connected-overview.md)
 1. [Przewodnik wdrażania bezpiecznego środowiska w trybie offline](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Scenariusz A: wdrażanie na urządzeniach połączonych z chmurą

Ten scenariusz jest porównywalny z wdrażaniem zarządzanych urządzeń przenośnych w firmie. HoloLens 2 jest wdrażany głównie w środowiskach zewnętrznych niż sieć firmowa. Zasoby firmowe nie są dostępne lub mogą być ograniczone za pośrednictwem sieci VPN. 
 * Podstawowe typowe konfiguracje
   * Wi-Fi są zwykle w pełni otwarte dla Internetu i usług w chmurze.
   * Azure AD Join with Mobile Zarządzanie urządzeniami (MDM) Auto Enrollment--MDM (Intune) Managed (Azure AD Join with Mobile Zarządzanie urządzeniami (MDM) Auto Enrollment--MDM (Intune) Managed (Azure AD Join with Mobile Zarządzanie urządzeniami (MDM) Auto Enrollment--MDM (Intune) Managed
   * Użytkownicy logują się przy użyciu własnego konta firmowego (Azure AD)
     * Obsługiwani są pojedynczy lub wielu użytkowników na urządzenie
   * Różne poziomy konfiguracji blokady urządzeń są stosowane na podstawie konkretnych przypadków użycia, od w pełni otwartego do kiosku z pojedynczą aplikacją.
   * Co najmniej jedna aplikacja jest wdrażana za pośrednictwem rozwiązania MDM

* Typowe wyzwania
   * Określenie, które konfiguracje zarządzania urządzeniami przenośnymi mają być stosowane HoloLens 2 na podstawie wymagań scenariusza.

[![Diagram scenariusza ](images/deployment-guides-revised-scenario-a.png) A](images/deployment-guides-revised-scenario-a.png#lightbox)

Odpowiedni przewodnik po chmurze obejmuje sposób rejestrowania usługi HoloLens 2 w usłudze zarządzania urządzeniami, stosowania licencji zgodnie z potrzebami i sprawdzania, czy użytkownicy końcowi mogą natychmiast korzystać z usługi Remote Assist podczas konfigurowania urządzenia. Przewodnik Klienci zewnętrzni umożliwia wdrażanie urządzeń w lokacji zdalnej do krótkoterminowego lub długoterminowego użytku zewnętrznego.

> [!div class="nextstepaction"]
> [Przewodnik wdrażania środowiska połączonego z chmurą](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [Przewodnik wdrażania środowiska połączonego z chmurą (klientów zewnętrznych)](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Scenariusz B: wdrażanie wewnątrz sieci organizacji

Ten scenariusz jest identyczny z klasycznym wdrożeniem dla większości Windows 10 komputerów. HoloLens 2 jest wdrażany do użytku głównie w sieci firmowej z dostępem do wewnętrznych zasobów firmy. Usługi internetowe i w chmurze mogą być ograniczone. 

 * Podstawowe typowe konfiguracje
   * Wi-Fi to wewnętrzna sieć firmowa z dostępem do zasobów wewnętrznych i ograniczonym dostępem do Internetu lub usług w chmurze.
   * Azure AD Join with MDM Auto Enrollment
   * Zarządzanie urządzeniami przenośnymi (Intune)
   * Użytkownicy logują się przy użyciu własnego konta firmowego (Azure AD)
     * Obsługiwani są pojedynczy lub wielu użytkowników na urządzenie
   * Różne poziomy konfiguracji blokady urządzeń są stosowane na podstawie konkretnych przypadków użycia, od w pełni otwartego do kiosku z pojedynczą aplikacją.
   * Co najmniej jedna aplikacja jest wdrażana za pośrednictwem rozwiązania MDM

 * Typowe wyzwania
   * HoloLens 2 nie obsługuje dołączania do lokalnej usługi AD ani programu SCCM. Tylko dołączanie do usługi Azure AD za pomocą rozwiązania MDM. Obecnie wiele firm nadal wdraża komputery z systemem Windows 10 w tym scenariuszu jako lokalne urządzenia przyłączone do usługi AD, zarządzane przez usługę System Center Configuration Manager (SCCM) i mogą nie mieć wdrożonej/skonfigurowanej infrastruktury do zarządzania wewnętrznymi urządzeniami Windows 10 za pośrednictwem rozwiązań MDM opartych na chmurze.
   * Ponieważ HoloLens 2 to pierwsze urządzenie w chmurze, w dużym stopniu opiera się ono na usługach połączonych z Internetem i w chmurze na temat uwierzytelniania użytkowników, aktualizacji systemu operacyjnego, zarządzania urządzeniami przenośnymi i tak dalej. Podczas nawiązywania połączenia z siecią firmową najprawdopodobniej trzeba będzie dostosować reguły serwera proxy/zapory, aby umożliwić dostęp dla programu HoloLens 2 i aplikacji, które na nim działają.
   * Łączność Wi-Fi zwykle wymaga certyfikatów w celu uwierzytelnienia urządzenia lub użytkownika w sieci. Skonfigurowanie wymaganej infrastruktury lub ustawień do wdrażania certyfikatów na urządzeniach Windows 10 za pośrednictwem zarządzania urządzeniami przenośnymi może być trudne.

[![Diagram scenariusza B1 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagram scenariusza B2 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

Odpowiedni przewodnik po sieci firmowej zawiera instrukcji na temat rejestrowania usługi HoloLens 2 w istniejącym zarządzaniu urządzeniami, stosowania licencji zgodnie z potrzebami i sprawdzania, czy użytkownicy końcowi mogą korzystać z przewodnika usługi Dynamics 365, a także używania niestandardowych aplikacji biznesowych po skonfigurowaniu urządzenia.

> [!div class="nextstepaction"]
> [Przewodnik wdrażania sieci firmowej](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Scenariusz C: wdrażanie w bezpiecznym środowisku offline

Jest to typowe wdrożenie dla wysoce bezpiecznych lub poufnych lokalizacji. HoloLens 2 jest wdrażany do użytku głównie w trybie offline bez dostępu do sieci ani Internetu. 
 * Podstawowe typowe konfiguracje
   * Wi-Fi łączność jest wyłączona. Sieć Ethernet za pośrednictwem portu USB może być włączona dla łączności z siecią LAN, jeśli jest to konieczne.
   * Nie zarządzana.
   * Konto użytkownika lokalnego do logowania urządzenia.
     * HoloLens 2 obsługuje tylko jedno konto lokalne.
   * Różne poziomy konfiguracji blokady urządzeń są stosowane za pośrednictwem pakietów aprowiwizowania na podstawie określonych przypadków użycia. Te konfiguracje są zwykle ograniczone ze względu na wymagania dotyczące bezpiecznego środowiska.
   * Co najmniej jedna aplikacja jest wdrażana za pośrednictwem pakietu aprowizowania

 * Typowe wyzwania
   * Istnieje ograniczony zestaw konfiguracji dostępnych za pośrednictwem pakietów aprowizowania
   * Nie można używać usług w chmurze, co ogranicza liczbę HoloLens 2.
   * Wyższe koszty administracyjne, ponieważ te urządzenia muszą być konfigurowane, konfigurowane i aktualizowane ręcznie.

[![Bezpieczny diagram trybu offline 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

Odpowiedni bezpieczny przewodnik w trybie offline zawiera instrukcje stosowania przykładowego pakietu aprowizowania, który zablokuje pakiet HoloLens 2 do użycia w bezpiecznych środowiskach.

> [!div class="nextstepaction"]
> [Przewodnik wdrażania bezpiecznego środowiska w trybie offline](hololens-common-scenarios-offline-secure.md)


