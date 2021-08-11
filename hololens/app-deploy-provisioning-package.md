---
title: Pakiet aprowizowania
description: Dowiedz się więcej na temat pakowania, aprowizowania, wdrażania i wdrażania aplikacji dla przedsiębiorstw HoloLens urządzeń.
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
ms.openlocfilehash: 2cb497d850ff7ba2de66f69e8ec53e6dd36b773cc13d01b038def8d539e3b0c1
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665220"
---
# <a name="provisioning-package"></a>Pakiet aprowizowania

Pakiety aprowizowania mogą służyć do przygotowywania i konfigurowania urządzeń w środowisku bez dostępu do zarządzania punktami końcowymi. Można je również wdrożyć na urządzeniu niezależnie od tożsamości użytkownika, stanu rejestracji, podczas procesu OOBE (Out of Box Experience) lub przez zastosowanie pakietu aprowizowania podczas [instalacji.](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)

## <a name="provisioning-packages-considerations"></a>Zagadnienia dotyczące aprowowania pakietów:

* Aplikacje niepublicznie dostępne
* Tylko ładowanie boczne USB
* Brak automatycznej aktualizacji (wymaga aktualizacji ręcznych za pośrednictwem PPKG)

Aplikacje zainstalowane za pośrednictwem pakietu aprowizowania muszą być podpisane przy użyciu certyfikatu w magazynie komputera lokalnego. Pakiety aprowizowania mogą instalować certyfikaty tylko w magazynie urządzenia (komputera lokalnego), w związku z tym aplikacja i certyfikat mogą być instalowane za pośrednictwem tego samego pakietu aprowizowania. Jeśli wdrażasz certyfikat z rozwiązania MDM lub instalujesz go za pośrednictwem Menedżera [certyfikatów,](certificate-manager.md)pamiętaj o wdrożeniu certyfikatu w magazynie komputera lokalnego w celu podpisywania zainstalowanych w ten sposób aplikacji.

Aby poznać podstawy tworzenia pakietu aprowizowania dla urządzeń HoloLens, odwiedź stronę [HoloLens Provisioning](/hololens/hololens-provisioning). Aby wdrożyć aplikację, musisz rozpocząć od zaawansowanej aprowiwizowania.

> [!NOTE]
> HoloLens (1. generacji) ma ograniczoną obsługę instalowania aplikacji **(UniversalAppInstall**) przy użyciu pakietu aprowizowania. HoloLens (1. generacji) obsługują instalowanie aplikacji tylko za pośrednictwem ppkg tylko podczas instalacji OOBE i tylko w kontekście użytkownika.

## <a name="setup"></a>Konfigurowanie

W [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) należy wykonać następujące cztery kroki.

1. Ustaw pozycję ApplicationManagement/AllowAllTrustedApps na wartość "Yes". Zobacz: [ApplicationManagement/AllowAllTrustedApps.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)

2. Przejdź do **pola UniversalAppInstall**  >  **UserContextAppLicense i** wprowadź wartość **PackageFamilyName.** Zobacz [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall). Zobacz też: [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).

   Możesz użyć Portal urządzeń na urządzeniu, na które już zainstalowano aplikację. Odwiedź stronę Aplikacje i spójrz na wiersz PackageRelativeID, wszystkie informacje przed "!" To twoja **nazwa_pakietu_pakietu.**

3. Zobaczysz, że masz nową sekcję **ApplicationFile**. Użyj tego obszaru, aby przekazać pakiet appx.

4. W zależności od tego, czy zakupiono aplikację lub sbudowaliśmy własną aplikację LOB, konieczne będzie przekazanie pliku licencji lub certyfikatu zabezpieczeń.

    - W przypadku pliku licencji: przejdź do **pozycji UniversalAppInstall**  >  **UserContextAppLicence** i przejdź do lokalizacji licencji i przekaż ją.
    - W przypadku pliku zabezpieczeń przejdź do **opcji Certyfikaty** i wybierz certyfikat do zainstalowania wraz z pakietem appx.

Pamiętaj, aby zapisać projekt w bezpiecznej lokalizacji. Następnie **wyeksportuj** go jako **pakiet aprowizowania.**  

Zobacz też: [Stosowanie pakietu aprowizowania do HoloLens](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).
