---
title: Pakiet aprowizowania
description: Dowiedz się więcej na temat pakowania, aprowizowania, wdrażania i wdrażania aplikacji przedsiębiorstwa dla urządzeń HoloLens.
keywords: app, app deployment, enterprise app deployment, provisioning
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378323"
---
# <a name="provisioning-package"></a>Pakiet aprowizowania

Pakiety aprowizowania mogą służyć do przygotowywania i konfigurowania urządzeń w środowisku bez dostępu do zarządzania punktami końcowymi. Można je również wdrożyć na urządzeniu niezależnie od tożsamości użytkownika, stanu rejestracji, podczas procesu OOBE (Out of Box Experience) lub przez zastosowanie pakietu aprowizowania podczas [instalacji.](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)

## <a name="provisioning-packages-considerations"></a>Zagadnienia dotyczące pakietów aprowiwizowania:

* Aplikacje niepublicznie dostępne
* Tylko ładowanie boczne USB
* Brak automatycznej aktualizacji (wymaga aktualizacji ręcznych za pośrednictwem PPKG)

Aplikacje zainstalowane za pośrednictwem pakietu aprowizowania muszą być podpisane przy użyciu certyfikatu w magazynie komputera lokalnego. Pakiety aprowizowania mogą instalować certyfikaty tylko w magazynie urządzenia (komputera lokalnego), w związku z tym aplikacja i certyfikat mogą być instalowane za pośrednictwem tego samego pakietu aprowizowania. Jeśli wdrażasz certyfikat z rozwiązania MDM lub instalujesz go za pośrednictwem Menedżera [certyfikatów,](certificate-manager.md)pamiętaj o wdrożeniu certyfikatu w magazynie komputera lokalnego w celu podpisywania zainstalowanych w ten sposób aplikacji.

Aby poznać podstawy tworzenia pakietu aprowizowania dla urządzeń HoloLens, odwiedź stronę [aprowizowania urządzenia HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning) Aby wdrożyć aplikację, musisz rozpocząć od zaawansowanej aprowiwizowania.

> [!NOTE]
> Urządzenie HoloLens (1. generacja) ma ograniczoną obsługę instalowania aplikacji **(UniversalAppInstall**) przy użyciu pakietu aprowizowania. Urządzenia HoloLens (1. generacji) obsługują instalowanie aplikacji za pośrednictwem ppkg tylko podczas instalacji OOBE i tylko w przypadku instalacji w kontekście użytkownika.

## <a name="setup"></a>Konfigurowanie

W [programie Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) należy wykonać następujące cztery kroki.

1. Ustaw pozycję ApplicationManagement/AllowAllTrustedApps na wartość "Yes". Zobacz: [ApplicationManagement/AllowAllTrustedApps.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)

2. Przejdź do **pola UniversalAppInstall**  >  **UserContextAppLicense i wprowadź** wartość **PackageFamilyName.** Zobacz [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall). Zobacz też: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).

   Możesz użyć Portal urządzeń na urządzeniu, na które już zainstalowano aplikację. Odwiedź stronę Aplikacje i spójrz na wiersz PackageRelativeID, wszystkie informacje przed "!" To twoja **nazwa_pakietu_pakietu.**

3. Zobaczysz, że masz nową sekcję **ApplicationFile**. Użyj tego obszaru, aby przekazać pakiet appx.

4. W zależności od tego, czy zakupiono aplikację lub sbudowaliśmy własną aplikację LOB, konieczne będzie przekazanie pliku licencji lub certyfikatu zabezpieczeń.

    - W przypadku pliku licencji: przejdź do **pozycji UniversalAppInstall**  >  **UserContextAppLicence** i przejdź do lokalizacji licencji i przekaż ją.
    - W przypadku pliku zabezpieczeń przejdź do **opcji Certyfikaty** i wybierz certyfikat do zainstalowania wraz z pakietem appx.

Pamiętaj, aby zapisać projekt w bezpiecznej lokalizacji. Następnie **wyeksportuj** go jako **pakiet aprowizowania.**  

Zobacz też: [Stosowanie pakietu aprowizowania na urządzeniach HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)
