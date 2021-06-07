---
title: Wymagania licencyjne
description: Bądź na bieżąco ze wszystkimi wymaganiami i wytycznymi dotyczącymi licencjonowania potrzebnymi do zarządzania urządzeniami przenośnymi, urządzenia HoloLens i usługi Remote Assist.
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2f7af532d2172dcaa6514ee11dbb0d6ab5631929
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379753"
---
# <a name="license-requirements"></a>Wymagania licencyjne

## <a name="mobile-device-management-mdm-licenses-guidance"></a>Wskazówki dotyczące licencji usługi Mobile Zarządzanie urządzeniami (MDM)

Jeśli planujesz zarządzanie urządzeniami HoloLens, potrzebujesz usługi Azure AD i rozwiązania MDM. Usługi Active Director (AD) nie można używać do zarządzania urządzeniami HoloLens.
Jeśli planujesz korzystanie z rozwiązania MDM innego niż usługa Intune, [wymagana jest Azure Active Directory zarządzania urządzeniami](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) przenośnymi.
Jeśli planujesz używać usługi Intune jako rozwiązania MDM, zapoznaj się z [listą](https://docs.microsoft.com/intune/fundamentals/licenses) pakietów, które obejmują licencje usługi Intune. **Należy pamiętać, że usługa Azure AD jest uwzględniona w większości tych pakietów.**

## <a name="identify-the-licenses-needed-for-your-scenario-and-products"></a>Identyfikowanie licencji wymaganych dla scenariusza i produktów

### <a name="hololens-1st-gen-licenses-requirements"></a>Wymagania dotyczące licencji urządzenia HoloLens (1. generacji)

Może być konieczne uaktualnienie urządzenia HoloLens (1. generacji) do Windows Holographic for Business. (Zobacz Funkcje [komercyjne urządzenia HoloLens,](holoLens-commercial-features.md#feature-comparison-between-editions) aby ustalić, czy należy je uaktualnić).

 Jeśli tak, należy wykonać następujące czynności:

- Uzyskaj plik XML licencji urządzenia HoloLens Enterprise
- Zastosuj plik XML do urządzenia HoloLens. Można to zrobić za pomocą pakietu [aprowizowania](hololens-provisioning.md) lub za pośrednictwem usługi [Mobile Menedżer urządzeń](https://docs.microsoft.com/intune/configuration/holographic-upgrade)

### <a name="remote-assist-license-requirements"></a>Wymagania licencyjne usługi Remote Assist

Upewnij się, że masz wymagane licencje i urządzenie, które możesz sprawdzić w [dokumentacji](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements) wymagań.

1. [Licencja usługi Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. Możesz też wypróbować wersję [próbną usługi Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)
1. [Teams Freemium/Teams](https://products.office.com/microsoft-teams/free)
1. [Azure Active Directory licencji usługi (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

Jeśli planujesz wdrożenie tego scenariusza między **[dzierżawami,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)** może być potrzebna licencja information barriers. Zapoznaj się z [tym artykułem,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) aby ustalić, czy wymagana jest licencja Information Barrier.

### <a name="guides-license-requirements"></a>Wymagania licencyjne przewodników

Zapoznaj się ze [zaktualizowanymi wymaganiami w zakresie licencjonowania i urządzeń.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements)

1. [Azure Active Directory licencji usługi (Azure AD)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [Power BI](https://powerbi.microsoft.com/desktop/)
1. [Przewodniki](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
