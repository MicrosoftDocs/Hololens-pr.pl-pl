---
title: Przewodnik wdrażania — wdrażanie w 2 HoloLens z chmurą na dużą skalę za pomocą usługi Remote Assist — obsługa
description: Bądź na bieżąco z naszymi poradami dotyczącymi konserwacji i obsługi HoloLens za pośrednictwem sieci połączonej z chmurą.
keywords: HoloLens, zarządzanie, połączone z chmurą, Remote Assist, AAD, Azure AD, MDM, Mobile Zarządzanie urządzeniami
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 941de296d59713c098718b16431fa793bd1b60e6
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428738"
---
# <a name="maintain---cloud-connected-guide"></a>Obsługa — przewodnik po połączeniu z chmurą

## <a name="updates"></a>Aktualizacje

Firma Microsoft zaprojektowała usługę Windows Update dla Firm, aby zapewnić administratorom IT dodatkowe funkcje zarządzania zorientowane na aktualizacje usługi Windows, takie jak możliwość wdrażania aktualizacji w grupach urządzeń i definiowania okien obsługi na potrzeby instalowania aktualizacji.

Dowiedz się, [jak zarządzać aktualizacjami](/hololens/hololens-updates) HoloLens, w tym zaplanowanych dni, zaplanowanych godzin i ustawiania aktywnych godzin na urządzeniu, aby aktualizować je poza godzinami pracy.

Usługa Remote Assist jest In-Box aplikacji i można ją aktualizować za pośrednictwem Microsoft Store aplikacji. Wszystkie aplikacje pobierane za pośrednictwem Microsoft Store można zaktualizować za pośrednictwem Microsoft Store [aplikacji](/hololens/holographic-store-apps#update-apps) ręcznie.

## <a name="support-plan"></a>Plan pomocy technicznej

Plan pomocy technicznej jest doskonałym rozwiązaniem. Przydatne jest przeszkolenie kogoś lub grupy w zakresie rozwiązywania problemów z procesem rejestracji na urządzeniach HoloLens oraz ogólnego użycia urządzenia HoloLens w organizacji. Aby umożliwić użytkownikom szybsze rozwiązanie ich problemów, sugerujemy, aby proces eskalacji był obsługiwany w sposób podobny do tego:

1. Twój personel pomocy technicznej.
2. Twój HoloLens ekspertów
3. [HoloLens Docs](/hololens/)  /  [HoloLens troubleshooting Docs (Rozwiązywanie problemów z dokumentów)](/hololens/hololens-troubleshooting)
4. [Kontakt z pomocą techniczną](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a>Plan rozwoju

Po pomyślnym zarejestrowaniu urządzenia możesz teraz przygotować się do wdrażania aplikacji biznesowych (aplikacji biznesowych) na urządzeniach. Są to aplikacje niestandardowe, które są dostosowane do&#39;organizacji.

Jeśli masz już aplikację biznesową, możesz&#39;wdrożyć aplikację za pomocą [rozwiązania MDM.](/hololens/app-deploy-intune) Jeśli chcesz&#39;inną metodę, zapoznaj się z omówieniem wdrażania aplikacji dla programu [HoloLens 2,](/hololens/app-deploy-overview) aby dowiedzieć się więcej na temat metod wdrażania aplikacji LOB na urządzeniach.

Jeśli nie&#39;tworzenia własnej aplikacji LOB lub nadal trwa proces tworzenia, zapoznaj się z naszymi dokumentami programistyczną rzeczywistości mieszanej, aby rozpocząć projektowanie i [tworzenie prototypów,](/windows/mixed-reality/design/design) lub zapoznaj się z podstawowymi pojęciami, aby rozpocząć tworzenie rzeczywistości [mieszanej.](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="device-management"></a>Zarządzanie urządzeniami 

W tym przewodniku omówienia konfigurowania usługi Mobile Zarządzanie urządzeniami (MDM) nie zastosowano jej do stosowania ograniczeń ani zasad dotyczących urządzeń. Zarządzanie urządzeniami może być używane zarówno do zezwalania na dostęp przez wypychanie certyfikatów, jak i ograniczania dostępu z różnymi ograniczeniami dotyczącymi urządzeń. 

W wielu przypadkach urządzenia mogą mieć ograniczenia łączności, takie jak Bluetooth sieci VPN, USB, a nawet wyłączenie dostępu do aparatu lub mikrofonu. Jeśli którekolwiek z tych zainteresowań Cię interesuje, zachęcamy do przeczytania naszej strony [typowych ograniczeń dotyczących urządzeń](hololens-common-device-restrictions.md).

Istnieją inne, bardziej złożone ograniczenia dotyczące urządzeń, których można użyć. Przykładowe metody:

- Ograniczanie stron, które mogą być przeglądane w aplikacji Ustawienia, przy użyciu właściwości [SettingsPageVisibility](settings-uri-list.md), dzięki czemu użytkownicy mogą uzyskać dostęp tylko do ustawień, które muszą dostosować, takich jak Wi-Fi połączenia.
- Użyj [trybu kiosku,](hololens-kiosk.md) aby ograniczyć interfejs użytkownika prezentowany użytkownikom na urządzeniu. Możesz ustawić kioski tak, aby wyświetlały pojedynczą aplikację lub wiele aplikacji przy użyciu niestandardowej strony startowej. Kioski mogą również przedstawiać różne środowisko różnym użytkownikom.  
- [Windows kontroli aplikacji (WDAC),](windows-defender-application-control-wdac.md) aby całkowicie nie uruchamiać określonych aplikacji lub procesów.

Jeśli chcesz dowiedzieć się więcej o różnych metodach zarządzania urządzeniami lub ograniczeniach dotyczących urządzeń, skorzystaj z następnego kroku i zapoznaj się z naszymi Zarządzanie urządzeniami Omówienie.

## <a name="next-step"></a>Następny krok

> [!div class="nextstepaction"]
> [Przeczytaj omówienie CSP i Zarządzanie urządzeniami CSP](hololens-csp-policy-overview.md)