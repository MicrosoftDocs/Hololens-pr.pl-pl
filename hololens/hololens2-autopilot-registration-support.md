---
title: Windows Autopilot rejestracji dla urządzenia HoloLens 2
description: Dowiedz się, jak uzyskać pomoc techniczną dla rozwiązania Autopilot na urządzeniach HoloLens 2.
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
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379817"
---
# <a name="hololens-2-registration-support-for-autopilot"></a>Obsługa rejestracji urządzenia HoloLens 2 dla rozwiązania Autopilot

Klienci i dostawcy rozwiązań w chmurze firmy Microsoft mogą teraz rejestrować urządzenia HoloLens 2, bezpośrednio przesyłając żądania do Pomoc techniczna Microsoft. Na tej stronie przedstawiono wymagania dotyczące następujących obsługiwanych scenariuszy rejestracji rozwiązania Autopilot:

- **Rejestracja rozwiązania Autopilot urządzenia HoloLens 2.** Przesyła żądanie zarejestrowania urządzeń HoloLens 2 w Windows Autopilot.
- **Żądanie skrótu sprzętu urządzenia HoloLens 2**. Przesyła żądanie do Pomoc techniczna Microsoft w celu zapewnienia skrótów sprzętu, których klienci lub CSP mogą używać do samodzielnego rejestrowania urządzeń za pośrednictwem usługi Microsoft Intune lub microsoft Partner Center.
- **Deregistracja rozwiązania Autopilot dla urządzenia HoloLens 2**. Przesyła żądanie usunięcia urządzeń z Windows Autopilot, zwykle używane w scenariuszach zakończenia cyklu życia urządzenia.

W poniższej tabeli przedstawiono szczegółowe informacje, które należy zebrać przed *przesłaniem* żądań rejestracji do Pomoc techniczna Microsoft.

| Wymagane informacje | Opis | Rejestracja rozwiązania Autopilot  | Żądanie skrótu sprzętu | Wyrejestrowanie rozwiązania Autopilot |
------------|-------------------------------|--------------------------------------------------|------------------------------|--------------------------------|
|  Azure Active Directory dzierżawy    |    Identyfikator Azure Active Directory dzierżawy to unikatowy identyfikator globalny (GUID), który różni się od nazwy organizacji lub domeny.    Aby znaleźć identyfikator dzierżawy, zaloguj się do [witryny Azure Portal.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)    |     ✔️                         |                              |                         ✔️                        |
|  Azure Active Directory nazwa domeny    |   Nazwa domeny najwyższego poziomu; na przykład contoso.com.    |     ✔️                         |                              |                         ✔️                        |
|  Dowód własności    |   Zweryfikuj dowód własności, przesyłając oryginalny rachunek lub fakturę w formacie PDF. Zrzuty ekranu nie są akceptowane. Na rachunku sprzedaży lub fakturze muszą znajdować się następujące informacje: Numery seryjne urządzeń. Nazwa firmy.     |     ✔️                         |              ✔️                |                         ✔️                        |
|  Numery seryjne urządzeń    |   Przekaż plik programu Excel w formacie CSV z każdym numerem seryjnym urządzenia w nowym wierszu.     |     ✔️                         |              ✔️                |                         ✔️                        |

## <a name="submit-support-requests"></a>Przesyłanie żądań pomocy technicznej

> [!div class="nextstepaction"]
> [Przesyłanie obsługi rejestracji rozwiązania Autopilot dla urządzenia HoloLens 2](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
