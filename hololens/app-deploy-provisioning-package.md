---
title: Pakiet aprowizowania
description: Dowiedz się więcej o pakowaniu, aprowizowaniu, wdrażaniu i wdrażaniu aplikacji dla przedsiębiorstw HoloLens urządzeń.
keywords: aplikacja, wdrażanie aplikacji, wdrażanie aplikacji dla przedsiębiorstw, aprowizowanie
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
ms.openlocfilehash: d071f4326a35a9ea61e2069618da7107bb808f04
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033078"
---
# <a name="provisioning-package"></a>Pakiet aprowizowania

Pakietów aprowizowania można używać do przygotowywania i konfigurowania urządzeń w środowisku bez dostępu do zarządzania punktami końcowymi. Można je również wdrożyć na urządzeniu niezależnie od tożsamości użytkownika, stanu rejestracji, podczas procesu OOBE (Out of Box Experience) lub przez zastosowanie pakietu aprowizowania podczas [instalacji.](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)

## <a name="provisioning-packages-considerations"></a>Zagadnienia dotyczące pakietów aprowizowania

* Aplikacje niepublicznie dostępne
* Tylko ładowanie boczne USB
* Brak automatycznej aktualizacji (wymaga aktualizacji ręcznych za pośrednictwem PPKG)

Aplikacje zainstalowane za pośrednictwem pakietu aprowizowania muszą być podpisane przy użyciu certyfikatu w magazynie komputera lokalnego. Pakiety aprowizowania mogą instalować certyfikaty tylko w magazynie urządzenia (komputera lokalnego). W związku z tym aplikację i certyfikat można zainstalować za pośrednictwem tego samego pakietu aprowizowania. Jeśli wdrażasz certyfikat z rozwiązania MDM lub instalujesz go za pośrednictwem Menedżera [certyfikatów,](certificate-manager.md)upewnij się, że certyfikat został wdrożony w magazynie komputera lokalnego w celu podpisywania zainstalowanych w ten sposób aplikacji.

Aby poznać podstawy tworzenia pakietu aprowizowania dla urządzeń HoloLens, odwiedź [stronę HoloLens Provisioning](/hololens/hololens-provisioning). Aby wdrożyć aplikację, musisz rozpocząć od zaawansowanej aprowrowi.

> [!NOTE]
> HoloLens (1. generacji) ma ograniczoną obsługę instalowania aplikacji **(UniversalAppInstall**) przy użyciu pakietu aprowizowania. HoloLens (1. generacji) obsługują tylko instalowanie aplikacji za pośrednictwem ppkg tylko podczas OOBE i tylko w przypadku instalacji kontekstu użytkownika.

## <a name="setup"></a>Konfigurowanie

W [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) należy wykonać następujące cztery kroki.

1. Ustaw pozycję ApplicationManagement/AllowAllTrustedApps na wartość "Yes". Zobacz: [ApplicationManagement/AllowAllTrustedApps.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)

2. Przejdź do **aplikacji UniversalAppInstall**  >  **UserContextApp** i wprowadź **wartość PackageFamilyName.** Zobacz [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall).

   Możesz użyć Portal urządzeń na urządzeniu, na które masz już zainstalowaną aplikację. Odwiedź stronę Aplikacje i spójrz na wiersz PackageRelativeID , wszystkie informacje przed "!" Jest to **nazwa PackageFamilyName.**

3. Zobaczysz, że masz nową sekcję **ApplicationFile**. Użyj tego obszaru, aby przekazać pakiet appx.

4. W zależności od tego, czy zakupiono aplikację lub sbudowaliśmy własną aplikację LOB, konieczne będzie przekazanie pliku licencji lub certyfikatu zabezpieczeń.

    - W przypadku pliku licencji przejdź do strony **UniversalAppInstall**  >  **UserContextAppLicence** i wprowadź identyfikator produktu licencji. Zostanie utworzona nowa sekcja <b>LicenseProductID:</b><i>yourlicenseproductid,</i> wybierz tę nową sekcję i przejdź do lokalizacji licencji i przekaż ją.
        - Zobacz [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).
    - W przypadku pliku zabezpieczeń przejdź do **opcji Certyfikaty** i wybierz certyfikat do zainstalowania razem z pakietem appx.

Pamiętaj, aby zapisać projekt w bezpiecznej lokalizacji. Następnie **wyeksportuj** go jako **pakiet aprowizowania.**  

Zobacz też: [Stosowanie pakietu aprowizowania do HoloLens](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).
