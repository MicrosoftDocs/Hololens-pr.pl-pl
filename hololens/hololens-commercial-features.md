---
title: Funkcje komercyjne
description: Dowiedz się więcej Microsoft HoloLens Commercial Suite funkcji, które ułatwiają firmom zarządzanie urządzeniami HoloLens.
author: scooley
ms.author: scooley
ms.date: 08/26/2019
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
audience: ITPro
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: HoloLens, komercyjne, funkcje, mdm, zarządzanie urządzeniami przenośnymi, tryb kiosku
ms.openlocfilehash: 3682a2633477d68f61dba8a674846857947a3d15
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379673"
---
# <a name="commercial-features"></a>Funkcje komercyjne

Urządzenie HoloLens zawiera funkcje, które ułatwiają firmom zarządzanie urządzeniami HoloLens.

Każde urządzenie HoloLens 2 ma dostępne funkcje komercyjne.

Urządzenie HoloLens (1. generacja) ma dwie opcje licencjonowania: licencję dewelopera i licencję komercyjną. Aby odblokować możliwości komercyjne urządzenia HoloLens, uaktualnij licencję dewelopera do licencji komercyjnej. Aby kupić Microsoft HoloLens Commercial Suite, skontaktuj się z lokalnym konto Microsoft lokalnym.

>[!VIDEO https://www.youtube.com/embed/tNd0e2CiAkE]

## <a name="key-commercial-features"></a>Kluczowe funkcje komercyjne

- **Tryb kiosku.** Urządzenia HoloLens można używać w pokazach lub pokazach w trybie kiosku, aby ograniczyć liczbę aplikacji, które można uruchamiać.

  ![W trybie kiosku urządzenie HoloLens jest uruchamiane bezpośrednio w wybranej aplikacji.](images/201608-kioskmode-400px.png)

- **Urządzenia Zarządzanie urządzeniami (MDM) dla urządzenia HoloLens.** Dział IT może zarządzać jednocześnie wieloma urządzeniami HoloLens przy użyciu rozwiązań takich jak Microsoft Intune. Możesz zarządzać ustawieniami, wybierać aplikacje do zainstalowania i ustawiać konfiguracje zabezpieczeń dostosowane do potrzeb organizacji.

  ![Urządzenia Zarządzanie urządzeniami na urządzeniu HoloLens zapewniają zarządzanie urządzeniami klasy korporacyjnej na wielu urządzeniach.](images/201608-enterprisemanagement-400px.png)

- **Windows Update dla Firm.** Windows Update dla Firm zapewnia kontrolowane aktualizacje systemu operacyjnego dla urządzeń i obsługę kanału obsługi długoterminowej.
- **Bezpieczeństwo danych.** Szyfrowanie danych funkcją BitLocker jest włączone na urządzeniu HoloLens w celu zapewnienia tego samego poziomu ochrony co inne urządzenie z systemem Windows.
- **Dostęp z pracy.** Każda osoba w organizacji może zdalnie połączyć się z siecią firmową za pośrednictwem wirtualnej sieci prywatnej (VPN) na urządzeniach HoloLens. Urządzenie HoloLens może również uzyskać Wi-Fi sieci, które wymagają poświadczeń.
- **Microsoft Store dla Firm.** Dział IT może również skonfigurować prywatny sklep przedsiębiorstwa zawierający tylko aplikacje firmowe do określonego użycia urządzenia HoloLens. Bezpieczna dystrybucja oprogramowania przedsiębiorstwa do wybranej grupy użytkowników przedsiębiorstwa.

## <a name="feature-comparison-between-editions"></a>Porównanie funkcji między wersjami

|Funkcje |HoloLens (1. generacja) Development Edition |HoloLens (1. generacja) Commercial Suite |HoloLens 2 |
|---|:---:|:---:|:---:|
|szyfrowanie urządzeń (BitLocker) | |✔️ |✔️ |
|Wirtualna sieć prywatna (VPN) | |✔️ |✔️ |
|[Tryb kiosku](hololens-kiosk.md) | |✔️ |✔️ |
|**Zarządzanie i wdrażanie** | | | |
|Mobile Zarządzanie urządzeniami (MDM) | |✔️ |✔️ |
|Możliwość blokowania wywłaszania | |✔️ |✔️ |
|Dostęp do aplikacji firmowych opartych Wi-Fi certyfikatami | |✔️ |✔️ |
|Microsoft Store (konsument) |Produkty konsumenckie |Filtrowanie przy użyciu rozwiązania MDM |Filtrowanie przy użyciu rozwiązania MDM |
|[Portal sklepu dla firm](https://docs.microsoft.com/microsoft-store/working-with-line-of-business-apps) | |✔️ |✔️ |
|**Zabezpieczenia i tożsamość** | | | |
|Logowanie się przy użyciu Azure Active Directory (Azure AD) |✔️ |✔️ |✔️ |
|Zaloguj się przy użyciu konta Microsoft (MSA) |✔️ |✔️ |✔️ |
|Poświadczenia nowej generacji z odblokowywanie kodem PIN |✔️ |✔️ |✔️ |
|[Bezpieczny rozruch](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot) |✔️ |✔️ |✔️ |
|**Obsługa i pomoc techniczna** | | | |
|Automatyczne aktualizacje systemu po ich przybyciu |✔️ |✔️ |✔️ |
|[Windows Update dla firm](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) | |✔️ |✔️ |
|Long-Term Servicing Channel (LTSC) | |✔️ |✔️ |

## <a name="enabling-commercial-features"></a>Włączanie funkcji komercyjnych

Administrator IT w organizacji może skonfigurować funkcje komercyjne, takie jak Microsoft Store dla Firm, tryb kiosku i dostęp Wi-Fi przedsiębiorstwa. Dokumentacja [Microsoft HoloLens](index.yml) zawiera instrukcje krok po kroku dotyczące rejestrowania urządzeń i instalowania aplikacji z Microsoft Store dla Firm.

## <a name="see-also"></a>Zobacz też

- [Microsoft HoloLens](index.yml)
- [Tryb kiosku](hololens-kiosk.md)
- [CSP obsługiwani na urządzeniach HoloLens](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)
- [Microsoft Store dla firm i aplikacji biznesowych](https://blogs.technet.microsoft.com/sbucci/2016/04/13/windows-store-for-business-and-line-of-business-applications/)
- [Praca z aplikacjami biznesowymi](/microsoft-store/working-with-line-of-business-apps)
