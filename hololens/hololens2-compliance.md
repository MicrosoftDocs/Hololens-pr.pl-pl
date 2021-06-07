---
title: Zgodność z urządzeniem HoloLens 2 i RODO
description: Dokumentacja RODO
keywords: HoloLens, RODO, prywatność, dane osobowych
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: skerewala, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 8b795513d83c9d23f70b8dd8365e703d1fc43a51
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378431"
---
# <a name="hololens-2-privacy-statement"></a>Zasady zachowania poufności informacji dla urządzenia HoloLens 2

Jednym z podstawowych elementów RODO jest "ochrona danych przez projekt". Ta koncepcja ma zastosowanie szczególnie do urządzeń przenośnych, takich jak HoloLens 2, ze względu na przenośność, nieograniczone połączenia internetowe i otwarte kanały komunikacyjne. W związku z tym zabezpieczenia urządzenia [](https://docs.microsoft.com/hololens/security-architecture) HoloLens 2 zostały przeprojektowane w celu zapewnienia zaawansowanej, innowacyjnej ochrony prywatności i zabezpieczeń, w tym zarówno podejścia firmy Microsoft do prywatności, jak i przepisów [RODO.](https://privacy.microsoft.com/)

 >[!NOTE]
> Ten dokument nie dotyczy urządzenia HoloLens (1. generacji).

## <a name="privacy-overview"></a>Omówienie ochrony prywatności

HoloLens 2 to samodzielny komputer z systemem Windows Holographic, który uruchamia aplikacje i rozwiązania w immersywnym środowisku rzeczywistości mieszanej. Może być używany jako bezpieczne urządzenie w trybie offline lub wdrażany jako [urządzenie zarządzane w](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business) organizacji. Zapoznaj się z poniższymi linkami, aby dowiedzieć się, w jaki sposób urządzenia HoloLens 2 i firma Microsoft chronią Twoje dane:
1. [Zasady zachowania poufności informacji firmy Microsoft — HoloLens](https://privacy.microsoft.com/privacystatement) — rozwiń sekcję **Enterprise and developer** (Przedsiębiorstwo i deweloper) w menu nawigacji po lewej stronie i wybierz pozycję Enterprise and developer software and appliances (Oprogramowanie i urządzenia dla przedsiębiorstw i **deweloperów).** Przejdź do **sekcji Urządzenia HoloLens.**
2.  [Windows 10 i Usługi online](https://privacy.microsoft.com/windows10privacy)
3.  [Windows 10 & Privacy Compliance Guide](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
4.  [Prywatność i dane osobowe w usłudze Intune](https://docs.microsoft.com/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>Bezpieczeństwo sieci
Zgodnie ze wspólnymi scenariuszami wdrażania urządzenia HoloLens [2](https://docs.microsoft.com/hololens/common-scenarios)dane będą chronione przez światowej klasy zgodność platformy [Azure](https://docs.microsoft.com/azure/compliance/) wraz z integracją standardów prawnych/prawnych. Jeśli jesteś nowym użytkownikiem usług Azure AD i Dynamics 365 Remote Assist, zapoznaj się z listą kontrolną gotowości do odpowiedzialności platformy Azure i usługi [Dynamics 365](https://docs.microsoft.com/compliance/regulatory/gdpr-arc-azure-dynamics)dla RODO.

Ponadto Zapora Windows Defender zapewnia krytyczne funkcje w celu zabezpieczenia łączności urządzeń. W przypadku urządzenia HoloLens 2 zapora jest zawsze włączona i nie ma możliwości wyłączenia jej programowo ani za pośrednictwem interfejsu użytkownika. Gdy urządzenie HoloLens 2 jest wdrażane jako urządzenie zarządzane przy użyciu usługi [Intune,](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)dostępna jest większa funkcjonalność zgodności z integracją punktu końcowego z usługą [Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection) jako rozwiązaniem Mobile Threat Defense. 

Dowiedz się więcej o zabezpieczeniach i architekturze urządzenia HoloLens [2.](https://docs.microsoft.com/hololens/security-architecture)

## <a name="os-security"></a>Zabezpieczenia systemu operacyjnego
Aktualizacje są wykonywane automatycznie (domyślnie), dzięki czemu urządzenie HoloLens 2 jest zawsze aktualne z najnowszą aktualizacją systemu Windows Holographic i wszystkich zainstalowanych aplikacji. Zobacz następujące informacje, aby dowiedzieć się więcej na temat sposobu bezpiecznego zaprojektowania naszego systemu operacyjnego:
1. [Separacja i izolacja stanu](https://docs.microsoft.com/hololens/security-state-separation-isolation)
1. [System operacyjny bez uprawnień administratora](https://docs.microsoft.com/hololens/security-adminless-os)
1. [Ograniczanie użycia hasła](https://docs.microsoft.com/hololens/security-limiting-password-use)

## <a name="physical-security"></a>Zabezpieczenia fizyczne
Urządzenie HoloLens 2 ma pamięć flash chronioną przez [szyfrowanie funkcją BitLocker.](https://docs.microsoft.com/hololens/security-encryption-data-protection) Urządzenie i jego dane lokalne można flashować [](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) w trybie offline przy użyciu zaawansowanego pomocnika odzyskiwania lub zdalnie wyczyścić za pośrednictwem rozwiązania MDM, jeśli zostało ono wdrożone jako urządzenie zarządzane.

## <a name="data-protection"></a>Ochrona danych
Aktualizacje systemu Windows są uruchamiane automatycznie (domyślnie), a integracja z platformą [Azure](https://docs.microsoft.com/hololens/security-encryption-data-protection#Azure-integration) chroni dane między sobą a chmurą. 

Podczas wdrażania urządzenia HoloLens 2 na klientach zewnętrznych usługa [Dynamics 365 Remote Assist](https://docs.microsoft.com/hololens/hololens2-deployment-guide) zapewnia, że poufne dane i zasoby firmy są oddzielne i bezpieczne. 

Udostępnianie danych diagnostycznych firmie Microsoft może zostać ręcznie skonfigurowane przez rozwiązanie MDM lub przez użytkownika podczas OOBE. Dostępne są dwie opcje: Opcjonalne dane diagnostyczne i Wymagane dane diagnostyczne. Jeśli oryginalne ustawienie diagnostyczne musi zostać zmienione w późniejszym czasie w celu rozwiązywania problemów, może je zmienić użytkownik w ustawieniach **-> Privacy -> Diagnostics & Feedback** lub administrator IT (MDM), jeśli jest urządzeniem zarządzanym. Zobacz więcej informacji na [temat diagnostyki, opinii i](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)prywatności w Windows 10 .

> [!Important]
> Dzienniki diagnostyczne urządzeń zawierają dane osobowe, takie jak procesy lub aplikacje, które użytkownik uruchamia podczas typowych operacji. Jeśli wielu użytkowników współużytkuje urządzenie HoloLens (na przykład użytkownicy logują się na tym samym urządzeniu przy użyciu różnych kont usługi Microsoft Azure Active Directory (Azure AD), dzienniki diagnostyczne mogą zawierać informacje osobowe dotyczące wielu użytkowników.

 

Istnieje kilka [metod zbierania i zasad przechowywania danych w](https://docs.microsoft.com/hololens/hololens-diagnostic-logs) celu zbierania danych diagnostycznych z urządzenia HoloLens 2.  Aby uzyskać więcej informacji na temat sposobu zbierania i przetwarzania danych diagnostycznych przez firmę [Microsoft,](https://privacy.microsoft.com/privacystatement) zobacz Oświadczenie o ochronie prywatności firmy Microsoft — diagnostyka — rozwiń pozycję **Windows** w menu nawigacji po lewej stronie i wybierz pozycję **Diagnostyka.** Przejdź do sekcji **Diagnostyka.**
