---
ms.openlocfilehash: d96a769b40daba0948f8f3c71a88513576c531b5
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859408"
---
# <a name="non-aad-configuration"></a>[Konfiguracja bez usługi AAD](#tab/nonaadlogon)

#### <a name="non-aad-configuration"></a>Konfiguracja bez usługi AAD

1. Utwórz pakiet aprowizowania, który:
    1. Konfiguruje ustawienia środowiska uruchomieniowego/AssignedAccess, aby zezwalać na konta gości.
    1. Opcjonalnie rejestruje urządzenie w układzie MDM (ustawienia środowiska uruchomieniowego/miejsce pracy/rejestracje), aby można było nim zarządzać później.
    1. Nie twórz konta lokalnego
2. [Zastosuj pakiet aprowizowania](../hololens-provisioning.md).

# <a name="aad-configuration"></a>[Konfiguracja usługi AAD](#tab/aadlogon)

#### <a name="aad-configuration"></a>Konfiguracja usługi AAD

Urządzenia przyłączone do usługi AAD skonfigurowane do trybu kiosku mogą zalogować się do konta gościa jednym naciśnięciem przycisku na ekranie logowania. Po zalogowaniu się do konta gościa urządzenie nie wyświetli monitu o ponowne zalogowanie, dopóki gość nie zostanie jawnie wylogowany z menu Start lub urządzenie zostanie uruchomione ponownie.

Automatyczne logowanie gościa można zarządzać za pomocą niestandardowych zasad [OMA-URI:](/mem/intune/configuration/custom-settings-windows-10)

- Wartość URI: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Zasady | Opis | Konfiguracje |
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | Umożliwia odwiedzającemu automatyczne logowanie do kiosku. | 1 (Tak), 0 (Nie, wartość domyślna). |