---
title: Wymagania licencyjne
description: Bądź na bieżąco ze wszystkimi wymaganiami i wytycznymi dotyczącymi licencjonowania, które są potrzebne do zarządzania urządzeniami przenośnymi, HoloLens i usługi Remote Assist.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens 2
ms.openlocfilehash: d0d8aa648df7901dec8636942e43aa549e626d7e
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635895"
---
# <a name="license-requirements"></a>Wymagania licencyjne

## <a name="hololens-2-device-managed"></a>HoloLens 2 (zarządzane)

[Konto usługi Azure AD](https://docs.microsoft.com/azure/active-directory/)

> [!IMPORTANT]
> Usługi Active Directory (AD) nie można używać do zarządzania HoloLens urządzeniami.

[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) lub innego rozwiązania MDM.
- [Windows Autopilot for HoloLens 2](hololens2-autopilot.md)— upraszcza aprowizowanie zarówno dla administratorów IT, jak i użytkowników końcowych. Administratorzy IT mogą wstępnie skonfigurować zasady HoloLens 2, a przy pierwszym rozruchu urządzenia zostaną wdrożone w stanie gotowości do działania firmy bez interakcji użytkownika końcowego. 

  > [!NOTE]
  > Windows Funkcja Autopilot wymaga [](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) skonfigurowania [platformy Azure P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) i automatycznego rejestrowania w celu wdrożenia przepływu rozwiązania Autopilot z niskim poziomem dotyku i wdrażania urządzeń. 

### <a name="business-use-case"></a>Przypadek użycia biznesowego: 

- [Scenariusz wdrażania A](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) — wdrożenie weryfikacji koncepcji lub wdrożenia pilotażowego.

- [Scenariusz wdrażania B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) — wdrażanie na dużą skalę.

## <a name="hololens-2-device-only-non-managed"></a>HoloLens 2 Tylko urządzenie (nieza zarządzane)

W przypadku korzystania z konta Microsoft (MSA) lub konta lokalnego nie są wymagane żadne dodatkowe licencje dla tych kont.

[Konto lokalne](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts)

- To konto należy [aprowizować](hololens-provisioning.md#provisioning-package-hololens-wizard) z wyprzedzeniem za pomocą Windows Configuration Designer (WCD).

[Konto Microsoft (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts)

> [!WARNING]
> Wielu użytkowników nie jest obsługiwanych na urządzeniu przy użyciu jednego z tych kont.

### <a name="business-use-case"></a>Przypadek użycia biznesowego: 

- [Scenariusz wdrażania C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) — wdrożenie w trybie offline lub bezpieczne.
 
## <a name="dynamics-365-licensing-and-requirements"></a>Dynamics 365 Licensing and Requirements

### <a name="dynamics-365-remote-assist"></a>Dynamics 365 Remote Assist 

#### <a name="admin"></a>Administrator

- Konto usługi Azure AD (wymagane do zakupu subskrypcji i przypisywania licencji)
- [Subskrypcja usługi Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (lub wersja [próbna usługi Remote Assist)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)
    
#### <a name="dynamics-365-remote-assist-user"></a>Użytkownik usługi Dynamics 365 Remote Assist

- Konto usługi Azure AD

- Licencja usługi Remote Assist 

  > [!NOTE]
  > Microsoft Teams jest w pakiecie z usługą Remote Assist

- Łączność sieciowa

#### <a name="microsoft-teams-user"></a>Microsoft Teams użytkownika

- Konto usługi Azure AD

- Microsoft Teams lub [Teams Freemium.](https://products.office.com/microsoft-teams/free)

- Łączność sieciowa

Jeśli planujesz wdrożenie tego scenariusza między [dzierżawami,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)może być potrzebna licencja na bariery informacyjne. Zapoznaj [się z tym artykułem,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) aby ustalić, czy wymagana jest licencja information barrier.

### <a name="dynamics-365-guides"></a>Dynamics 365 Guides 

#### <a name="admin"></a>Administrator

- Konto usługi Azure AD (wymagane do zakupu subskrypcji i przypisywania licencji)
- Subskrypcja przewodników usługi Dynamics 365 [lub bezpłatna wersja próbna](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one)

#### <a name="guides-author"></a>Tworzenie przewodników

1. Konto usługi Azure AD
1. [Licencja przewodników usługi Dynamics 365](/dynamics365/mixed-reality/guides/requirements)
1. Aplikacja Dynamics 365 Guides zainstalowana na komputerze pc lub HoloLens
1. [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (używane do wyświetlania pulpitu nawigacyjnego analizy)
1. Rola autora (do tworzenia przewodników)
1. Łączność sieciowa

#### <a name="guides-user"></a>Przewodniki użytkownika

1. Konto usługi Azure AD
1. [Licencja przewodników usługi Dynamics 365](/dynamics365/mixed-reality/guides/requirements)
1. Aplikacja Dynamics 365 Guides zainstalowana na HoloLens
1. Rola operatora (do testowania lub używania przewodników)
1. Łączność sieciowa
