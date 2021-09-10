---
title: Windows Obsługa rejestracji rozwiązania Autopilot dla HoloLens 2
description: Dowiedz się, jak uzyskać pomoc techniczną dla rozwiązania Autopilot na HoloLens 2.
author: joyjaz
ms.author: v-jjaswinski
ms.date: 5/20/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Autopilota
manager: ylempidakis
ms.openlocfilehash: cdd2ab68905d5cc82b1c5ccc50640112e857f2f4
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427984"
---
# <a name="hololens-2-registration-support-for-autopilot"></a>HoloLens 2 — pomoc techniczna dla rozwiązania Autopilot

Klienci i dostawcy rozwiązań w chmurze firmy Microsoft (CSP) mogą teraz zarejestrować 2 HoloLens, bezpośrednio przesyłając żądania do Pomoc techniczna Microsoft. Na tej stronie przedstawiono wymagania dotyczące następujących obsługiwanych scenariuszy rejestracji rozwiązania Autopilot:

- **HoloLens 2 Rejestracja rozwiązania Device Autopilot.** Przesyła żądanie zarejestrowania 2 HoloLens w Windows Autopilot.
- **HoloLens 2 żądanie skrótu sprzętu urządzenia.** Przesyła żądanie do Pomoc techniczna Microsoft w celu zapewnienia skrótów sprzętu, których klienci lub CSP mogą używać do samodzielnego rejestrowania urządzeń za pośrednictwem usługi Microsoft Intune lub microsoft Partner Center.
- **HoloLens 2 Device Autopilot Deregistration (Deregistracja rozwiązania Device Autopilot).** Przesyła żądanie usunięcia urządzeń z rozwiązania Windows Autopilot, zwykle używane w scenariuszach zakończenia cyklu życia urządzenia.

W poniższej tabeli przedstawiono szczegółowe informacje, które należy zebrać przed *przesłaniem* żądań rejestracji do Pomoc techniczna Microsoft.

| Wymagane informacje | Opis | Rejestracja rozwiązania Autopilot  | Żądanie skrótu sprzętu | Wyrejestrowanie rozwiązania Autopilot |
------------|-------------------------------|--------------------------------------------------|------------------------------|--------------------------------|
|  Azure Active Directory Identyfikator dzierżawy    |    Identyfikator Azure Active Directory dzierżawy to unikatowy identyfikator globalny (GUID), który różni się od nazwy organizacji lub domeny.    Aby znaleźć identyfikator dzierżawy, zaloguj się do [witryny Azure Portal.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)    |     ✔️                         |                              |                         ✔️                        |
|  Azure Active Directory Nazwa domeny    |   Nazwa domeny najwyższego poziomu; na przykład contoso.com.    |     ✔️                         |                              |                         ✔️                        |
|  Dowód własności    |   Zweryfikuj dowód własności, przesyłając oryginalny rachunek lub fakturę w formacie PDF. Zrzuty ekranu nie są akceptowane. Na rachunku sprzedaży lub fakturze muszą znajdować się następujące informacje: Numery seryjne urządzeń. Nazwa firmy.     |     ✔️                         |              ✔️                |                         ✔️                        |
|  Numery seryjne urządzeń    |   Upload Excel w formacie CSV z każdym numerem seryjnym urządzenia w nowym wierszu.     |     ✔️                         |              ✔️                |                         ✔️                        |

## <a name="submit-support-requests"></a>Przesyłanie żądań pomocy technicznej

> [!div class="nextstepaction"]
> [Przesyłanie obsługi rejestracji rozwiązania Autopilot dla HoloLens 2](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
