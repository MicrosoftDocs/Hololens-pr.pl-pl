---
title: Przewodnik wdrażania — połączone z HoloLens 2 z usługą Dynamics 365 — przewodniki — omówienie
description: Dowiedz się, jak zarejestrować HoloLens 2 urządzenia za pomocą przewodników usługi Dynamics 365 za pośrednictwem firmowej sieci połączonej.
keywords: HoloLens, zarządzanie, połączenia firmowe, przewodniki usługi Dynamics 365, AAD, Azure AD, MDM, Mobile Zarządzanie urządzeniami
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 541c1080d7f5fe9491d6cb11179ea98b160f687c
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190178"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>Przewodnik wdrażania — przewodniki dotyczące HoloLens 2 z usługą Dynamics 365 — omówienie

Ten przewodnik pomoże specjalistom IT w planowaniu i wdrażaniu urządzeń Microsoft HoloLens 2 za pomocą przewodników usługi Dynamics 365 (przewodników) w organizacji. Ten przewodnik jest doskonały dla wdrożeń pilotażowych i produkcyjnych i jest podobny do scenariusza B: wdrażanie wewnątrz [sieci organizacji.](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) Po przetestowaniu weryfikacji koncepcji skorzystaj z tego przewodnika, aby przejść dalej dzięki integracji HoloLens z twoją organizacją.

W tym przewodniku opisano sposób rejestrowania urządzeń w istniejącym zarządzaniu urządzeniami, stosowania licencji zgodnie z potrzebami i sprawdzania, czy użytkownicy końcowi mogą korzystać z przewodnika usługi Dynamics 365, a także jak korzystać z niestandardowych aplikacji biznesowych po skonfigurowaniu urządzenia. 

## <a name="prerequisites"></a>Wymagania wstępne

Powinna być już w tym miejscu następująca infrastruktura:
- Wi-Fi
    - Wewnętrzna sieć firmowa z dostępem do zasobów wewnętrznych i ograniczonym dostępem do Internetu lub usług w chmurze
    - Uwierzytelnianie certyfikatu opartego na urządzeniach.
- Azure Active Directory (Azure AD) Join with MDM Auto Enrollment (Wymagane są subskrypcje[usługi Azure AD P1)](/azure/active-directory/fundamentals/active-directory-whatis)
- Zarządzanie urządzeniami przenośnymi (Intune)
    - Co najmniej jedna aplikacja jest wdrażana za pośrednictwem rozwiązania MDM.
- Sieć 
    - Certyfikaty (SCEP lub PKCS)
    - Konfiguracja serwera proxy
- Użytkownicy logują się przy użyciu własnego konta firmowego (Azure AD)
    - Obsługiwana jest jedna lub wielu użytkowników na urządzenie.
- Różne poziomy konfiguracji blokady urządzenia stosowanych na podstawie konkretnych przypadków użycia, od w pełni otwartego do kiosku z jedną aplikacją.

## <a name="guides-licensing-and-requirements"></a>[Licencjonowanie przewodników i wymagania](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- Konto usługi Azure AD
- Dynamics 365 Prowadzi aplikacje na komputerach pc i HoloLens
- Subskrypcja przewodników usługi Dynamics 365
    - Microsoft Dataverse (dołączone)
    - Power Apps (dołączone)
- Power BI Desktop
- Łączność sieciowa

[![Diagram sieciowy połączony z firmami, etap 1. ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagram sieci połączony z firmami, etap 2. ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

## <a name="in-this-guide-you-will"></a>Ten przewodnik zawiera informacje na temat:
### <a name="prepare"></a>Przygotowywanie
> [!div class="checklist"]
>- [Poznaj podstawowe informacje o infrastrukturze dla HoloLens 2 urządzeń.](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [Dowiedz się więcej o usłudze Azure AD i skonfiguruj ją, jeśli jej nie masz.](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [Dowiedz się więcej na temat zarządzania tożsamościami i sposobu najlepszego skonfigurowania kont usługi Azure AD.](hololens2-corp-connected-prepare.md#identity-management)
>- [Dowiedz się więcej o usłudze MDM i skonfiguruj usługę Intune, jeśli jeszcze jej nie masz.](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [Zapoznaj się z siecią Wi-Fi opartą na certyfikatach.](hololens2-corp-connected-prepare.md#certificates)
>- [Zapoznaj się z serwerem proxy.](hololens2-corp-connected-prepare.md#proxy)
>- [Dowiedz się, jak używać aplikacji biznesowych.](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [Dowiedz się więcej na temat sposobu korzystania z przewodników w organizacji.](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>Konfigurowanie
> [!div class="checklist"]
>- [Jak tworzyć użytkowników i grupy.](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [Jak skonfigurować rejestrację automatyczną.](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [Jak skonfigurować certyfikaty Wi-Fi profilów dla firmowej Wi-Fi łączności.](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [Upload i przypisywanie pakietów aplikacji biznesowych.](hololens2-corp-connected-configure.md#app-deployment)
>- [Konfigurowanie przewodników usługi Dynamics 365.](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [Jak skonfigurować tryb kiosku (opcjonalnie).](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [Jak skonfigurować usługę WDAC (opcjonalnie).](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>Wdróż
> [!div class="checklist"]
>-  [Zweryfikuj rejestrację za pośrednictwem urządzenia i rozwiązania MDM.](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [Zweryfikuj Wi-Fi certyfikatów.](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [Zweryfikuj instalację aplikacji LOB.](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [Zweryfikuj przewodniki za pośrednictwem tworzenia i obsługi.](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>Obsługa
> [!div class="checklist"]
>- [Zaktualizuj HoloLens 2.](hololens2-corp-connected-maintain.md#update-hololens)
>- [Jak aktualizować przewodniki (aplikacje ze sklepu).](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [Jak aktualizować aplikacje LOB.](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [Plan rozwoju.](hololens2-corp-connected-maintain.md#development-plan) 
>- [Tworzenie planu pomocy technicznej.](hololens2-corp-connected-maintain.md#support-plan)
>- [Opcje zarządzania urządzeniami.](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>Następny krok 
> [!div class="nextstepaction"]
> [Wdrożenie połączone z firmą — przygotowanie](hololens2-corp-connected-prepare.md)
