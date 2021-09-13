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
ms.openlocfilehash: 6224cd5e07794d9fca3c0a406e787d1a3fd88b43
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036543"
---
# <a name="license-requirements"></a>Wymagania licencyjne

## <a name="overview"></a>Omówienie
Ta strona zawiera ogólne omówienie licencji i kont wymaganych do wdrożenia zarówno zarządzanych, jak i nieza zarządzanych urządzeń HoloLens 2 w organizacji. Zawiera on również informacje dotyczące licencjonowania usługi Dynamics 365 [Remote Assist](#dynamics-365-remote-assist) i [przewodników.](#dynamics-365-guides)

## <a name="hololens-2-license-and-account-requirements"></a>HoloLens licencji 2 i wymagań dotyczących konta

 
|       &nbsp;      | Zarządzane HoloLens | Niezamanageowane HoloLens |
|-------------------|-----------------|---------------------|
| **Przypadek użycia biznesowego** | | |
| [Wdrażanie na urządzeniach połączonych z chmurą — potwierdzenie koncepcji/wdrożenie pilotażowe](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices)  | ✔️| |
| [Wdrażanie wewnątrz sieci organizacji — wdrażanie na dużą skalę](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) | ✔️| |
| [Wdrażanie w bezpiecznym środowisku offline](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) | | ✔️ |
| **Licencje** | | |
| Azure Active Directory | ✔️ | |
| MDM (Intune<sup>1</sup> lub <sup>2)</sup> | ✔️  | |
| **Konta** |  | |
| Konto administratora usługi Azure AD | ✔️ |  |
| Konto użytkownika usługi Azure AD | ✔️ | |
| [Konto Microsoft (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts)| | ✔️ |
| [Konto lokalne](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | | ✔️ |
- <sup>1 Automatyczna</sup> [rejestracja podczas](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) początkowej konfiguracji urządzenia, która rejestruje i dołącza Azure Active Directory i umożliwia zarządzanie urządzeniem za pomocą usługi Intune.
- <sup>2</sup> [Windows Autopilot for HoloLens 2](hololens2-autopilot.md) upraszcza aprowizowanie zarówno dla administratorów IT, jak i użytkowników końcowych. Administratorzy IT mogą wstępnie skonfigurować zasady HoloLens 2, a przy pierwszym rozruchu urządzenia będą wdrażane w stanie gotowości do działania firmy bez interakcji z użytkownikiem.
- <sup>3 To</sup> konto należy [aprowizować](hololens-provisioning.md#provisioning-package-hololens-wizard) z wyprzedzeniem za pomocą Windows Configuration Designer (WCD).

> [!IMPORTANT]
> Usługi Active Directory (AD) nie można używać do zarządzania HoloLens urządzeniami.
 
> [!WARNING]
> Wielu użytkowników nie jest obsługiwanych na urządzeniu przy użyciu konta MSA lub konta lokalnego.

## <a name="dynamics-365-licensing-and-requirements"></a>Dynamics 365 Licensing and Requirements

### <a name="dynamics-365-remote-assist"></a>Dynamics 365 Remote Assist 

#### <a name="admin"></a>Administrator

- Konto usługi Azure AD (wymagane do zakupu subskrypcji i przypisywania licencji)
- [Subskrypcja usługi Remote Assist](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (lub wersja [próbna usługi Remote Assist)](/dynamics365/mixed-reality/remote-assist/try-remote-assist)
    
#### <a name="dynamics-365-remote-assist-user"></a>Użytkownik usługi Dynamics 365 Remote Assist

- Konto usługi Azure AD

- Licencja usługi Remote Assist 

  > [!NOTE]
  > Microsoft Teams jest w pakiecie z usługą Remote Assist

- Łączność sieciowa

#### <a name="microsoft-teams-user"></a>Microsoft Teams użytkownika

- Konto usługi Azure AD

- Microsoft Teams lub [Teams Freemium](https://products.office.com/microsoft-teams/free)

- Łączność sieciowa

Jeśli planujesz wdrożenie tego scenariusza między [dzierżawami,](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)może być potrzebna licencja na bariery informacyjne. Zapoznaj [się z tym artykułem,](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) aby ustalić, czy wymagana jest licencja information barrier.

### <a name="dynamics-365-guides"></a>Dynamics 365 Guides 

#### <a name="admin"></a>Administrator

1. Konto usługi Azure AD (wymagane do zakupu subskrypcji i przypisywania licencji)
2. Subskrypcja przewodników usługi Dynamics 365 [lub bezpłatna wersja próbna](/dynamics365/mixed-reality/guides/setup-step-one)

#### <a name="guides-author"></a>Tworzenie przewodników

1. Konto usługi Azure AD
1. [Licencja przewodników usługi Dynamics 365](/dynamics365/mixed-reality/guides/requirements)
1. Aplikacja Dynamics 365 Guides zainstalowana na komputerze pc lub HoloLens
1. [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (używane do wyświetlania pulpitu nawigacyjnego analizy)
1. Rola autora (do tworzenia przewodników)
1. Łączność sieciowa

#### <a name="guides-user"></a>Przewodniki dla użytkowników

1. Konto usługi Azure AD
1. [Licencja przewodników usługi Dynamics 365](/dynamics365/mixed-reality/guides/requirements)
1. Aplikacja Dynamics 365 Guides zainstalowana na komputerze HoloLens
1. Rola operatora (do testowania lub używania przewodników)
1. Łączność sieciowa
