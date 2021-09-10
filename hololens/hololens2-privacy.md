---
title: HoloLens 2 Prywatność i ochrona danych
description: Dokumentacja dotycząca ochrony prywatności
keywords: HoloLens, RODO, prywatność, dane osobowe, ochrona danych
author: golish
ms.author: marcingo
ms.reviewer: sekerawa, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 74f74645a3fc1282f48cb7ce0f6f722979c91b04
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427542"
---
# <a name="hololens-2-privacy-and-data-protection"></a>HoloLens 2 Prywatność i ochrona danych

Jednym z podstawowych elementów RODO jest "ochrona danych przez projekt". Ta koncepcja ma zastosowanie szczególnie do urządzeń przenośnych, takich jak HoloLens 2, ze względu na przenośność, nieograniczone połączenia internetowe i otwarte kanały komunikacyjne. W związku z tym zabezpieczenia usługi [](/hololens/security-architecture) HoloLens 2 zostały przeprojektowane w celu zapewnienia zaawansowanej, innowacyjnej ochrony prywatności i zabezpieczeń, w tym zarówno podejścia firmy Microsoft do prywatności, jak i przepisów [RODO.](https://privacy.microsoft.com/)

 >[!NOTE]
> Ten dokument nie dotyczy HoloLens (1. generacji).

## <a name="privacy-overview"></a>Omówienie ochrony prywatności

HoloLens 2 to samodzielny komputer Windows z systemem Windows Holographic, który uruchamia aplikacje i rozwiązania w immersywnym środowisku rzeczywistości mieszanej. Może służyć jako bezpieczne urządzenie w trybie offline lub wdrażane jako urządzenie [zarządzane w](/mem/intune/fundamentals/windows-holographic-for-business) organizacji. Zapoznaj się z poniższymi linkami, aby dowiedzieć się, jak HoloLens 2 i firma Microsoft chroni Twoje dane:

1. [Zasady zachowania poufności informacji firmy Microsoft — HoloLens](https://privacy.microsoft.com/privacystatement) — **rozwiń** sekcję Enterprise i dewelopera w menu nawigacji po lewej stronie, a następnie wybierz pozycję Enterprise oprogramowania i urządzeń **dla deweloperów.** Przejdź do **sekcji HoloLens.**
2. [Windows 10 i Usługi online](https://privacy.microsoft.com/windows10privacy)
3. [Windows 10 & privacy compliance Guide (Przewodnik zgodności z zasadami zachowania poufności informacji)](/windows/privacy/windows-10-and-privacy-compliance)
4. [Prywatność i dane osobowe w usłudze Intune](/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>Bezpieczeństwo sieci
Zgodnie z HoloLens 2 [common deployment scenarios](/hololens/common-scenarios)(Typowe scenariusze wdrażania) dane będą chronione przez światowej klasy zgodność platformy [Azure](/azure/compliance/) wraz z integracją standardów prawnych/prawnych. Jeśli jesteś nowym użytkownikiem usług Azure AD i Dynamics 365 Remote Assist, zapoznaj się z listą kontrolną gotowości do odpowiedzialności platformy Azure i usługi [Dynamics 365](/compliance/regulatory/gdpr-arc-azure-dynamics)dla RODO.

Ponadto zapora Windows Defender zapewnia krytyczne funkcje w celu zabezpieczenia łączności urządzeń. W HoloLens 2 zapora jest zawsze włączona i nie ma możliwości wyłączenia jej programowo ani za pośrednictwem interfejsu użytkownika. Gdy urządzenie HoloLens 2 jest wdrażane jako urządzenie zarządzane przy użyciu usługi [Intune,](/mem/intune/protect/device-compliance-get-started)dostępna jest większa funkcjonalność zgodności z integracją punktu końcowego z usługą [Microsoft Intune](/mem/intune/protect/advanced-threat-protection) jako rozwiązaniem Mobile Threat Defense.

Dowiedz się więcej o zabezpieczeniach i architekturze HoloLens [2.](/hololens/security-architecture)

## <a name="os-security"></a>Zabezpieczenia systemu operacyjnego
Aktualizacje są wykonywane automatycznie (domyślnie), dzięki czemu HoloLens 2 jest zawsze aktualne z najnowszą Windows holograficzną i zainstalowanymi aplikacjami. Zobacz następujące informacje, aby dowiedzieć się więcej na temat sposobu bezpiecznego zaprojektowania naszego systemu operacyjnego:

1. [Separacja i izolacja stanu](/hololens/security-state-separation-isolation)
1. [System operacyjny bez uprawnień administratora](/hololens/security-adminless-os)
1. [Ograniczanie użycia hasła](/hololens/security-limiting-password-use)

## <a name="physical-security"></a>Zabezpieczenia fizyczne
HoloLens 2 ma pamięć flash chronioną przez [szyfrowanie funkcją BitLocker.](/hololens/security-encryption-data-protection) Urządzenie i jego dane lokalne mogą być [](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) flashowane w trybie offline przy użyciu zaawansowanego pomocnika odzyskiwania lub zdalnie czyszowane za pośrednictwem rozwiązania MDM, jeśli zostało wdrożone jako urządzenie zarządzane.

## <a name="data-protection"></a>Ochrona danych
Windows są uruchamiane automatycznie (domyślnie), a integracja z platformą [Azure](/hololens/security-encryption-data-protection#Azure-integration) chroni dane pomiędzy sobą a chmurą.

Podczas wdrażania HoloLens 2 na klientach zewnętrznych usługa [Dynamics 365 Remote Assist](/hololens/hololens2-deployment-guide) zapewnia, że poufne dane i zasoby firmy są zarówno oddzielne, jak i bezpieczne.

Udostępnianie danych diagnostycznych firmie Microsoft może zostać ręcznie skonfigurowane przez rozwiązanie MDM lub przez użytkownika podczas OOBE. Dostępne są dwie opcje: Opcjonalne dane diagnostyczne i Wymagane dane diagnostyczne. Jeśli oryginalne ustawienie diagnostyczne musi zostać zmienione w późniejszym czasie w celu rozwiązywania problemów, może je zmienić użytkownik w diagnostyce Ustawienia **-> Privacy -> Diagnostics & Feedback** lub administrator IT (MDM), jeśli jest urządzeniem zarządzanym. Zobacz więcej informacji na [temat diagnostyki, opinii i](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)prywatności w Windows 10 .

> [!Important]
> Dzienniki diagnostyczne urządzeń zawierają dane osobowe, takie jak procesy lub aplikacje, które użytkownik uruchamia podczas typowych operacji. Jeśli wielu użytkowników współużytkuje urządzenie z systemem HoloLens (na przykład użytkownicy logują się na tym samym urządzeniu przy użyciu różnych kont usługi Microsoft Azure Active Directory (Azure AD), dzienniki diagnostyczne mogą zawierać informacje osobowe dotyczące wielu użytkowników.

Istnieje kilka [metod zbierania i zasad przechowywania danych w](/hololens/hololens-diagnostic-logs) celu zbierania danych diagnostycznych z HoloLens 2.  Aby uzyskać więcej informacji na temat sposobu zbierania i przetwarzania danych diagnostycznych przez firmę [Microsoft,](https://privacy.microsoft.com/privacystatement) zobacz Oświadczenie o ochronie prywatności firmy Microsoft — diagnostyka — rozwiń Windows **w** menu nawigacji po lewej stronie i wybierz pozycję **Diagnostyka.** Przejdź do sekcji **Diagnostyka.**
