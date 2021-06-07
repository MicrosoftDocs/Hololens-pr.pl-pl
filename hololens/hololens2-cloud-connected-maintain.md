---
title: Przewodnik wdrażania — wdrażanie urządzenia HoloLens 2 połączonego z chmurą na dużą skalę przy użyciu funkcji Remote Assist — konserwacja
description: Bądź na bieżąco z naszymi poradami dotyczącymi konserwacji i obsługi urządzeń HoloLens za pośrednictwem sieci połączonej z chmurą.
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
ms.openlocfilehash: bc34c4e41c5a6cee8f3f9a0a97407ee38d419bbc
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378405"
---
# <a name="maintain---cloud-connected-guide"></a>Obsługa — przewodnik po chmurze

## <a name="updates"></a>Aktualizacje

Firma Microsoft zaprojektowała Windows Update dla Firm, aby zapewnić administratorom IT dodatkowe funkcje zarządzania zorientowane na funkcje Windows Update, takie jak możliwość wdrażania aktualizacji w grupach urządzeń i definiowania okien obsługi w celu instalowania aktualizacji.

Dowiedz się, jak zarządzać aktualizacjami urządzenia [HoloLens,](https://docs.microsoft.com/hololens/hololens-updates) w tym zaplanowanymi dniami, zaplanowanym czasem i ustawianiem aktywnych godzin na urządzeniu, aby było ono aktualizowane poza godzinami pracy.

Usługa Remote Assist jest In-Box aplikacji i można ją aktualizować za pośrednictwem Microsoft Store aplikacji. W przypadku wszystkich aplikacji pobranych za pośrednictwem Microsoft Store można je zaktualizować za pośrednictwem Microsoft Store [ręcznie.](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps)

## <a name="support-plan"></a>Plan pomocy technicznej

Plan pomocy technicznej jest doskonałym rozwiązaniem. Przydatne jest wytrenowanie kogoś lub grupy na temat rozwiązywania problemów z procesem rejestracji na urządzeniach HoloLens, a także ogólnego użycia urządzenia HoloLens w organizacji. Aby umożliwić użytkownikom szybsze rozwiązanie ich problemów, sugerujemy, aby proces eskalacji był obsługiwany w podobny sposób jak w tej kolejności:

1. Pomoc techniczna.
2. Zespół ekspertów ds. urządzenia HoloLens
3. [HoloLens Docs](https://docs.microsoft.com/hololens/)  /  [Dokumenty dotyczące rozwiązywania problemów z urządzeniem HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [Kontakt z pomocą techniczną](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a>Plan rozwoju

Po pomyślnym zarejestrowaniu urządzenia możesz teraz przygotować się do wdrożenia aplikacji biznesowych (aplikacji biznesowych) na urządzeniach. Są to aplikacje niestandardowe, które są dostosowane do potrzeb&#39;organizacji.

Jeśli masz już aplikację biznesową, możesz&#39;ponownie wdrożyć aplikację za pomocą [rozwiązania MDM.](https://docs.microsoft.com/hololens/app-deploy-intune) Jeśli w&#39;wolisz inną metodę, zapoznaj się z omówieniem wdrażania aplikacji dla urządzenia [HoloLens 2,](https://docs.microsoft.com/hololens/app-deploy-overview) aby dowiedzieć się więcej na temat metod wdrażania aplikacji LOB na urządzeniach.

Jeśli nie&#39;tworzenia własnej aplikacji LOB lub nadal trwa proces jej tworzenia, zapoznaj się z naszymi dokumentami programistyczną rzeczywistości mieszanej, aby rozpocząć projektowanie i [tworzenie prototypów,](https://docs.microsoft.com/windows/mixed-reality/design/design) lub poznasz podstawowe pojęcia, aby rozpocząć tworzenie rzeczywistości [mieszanej.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)

## <a name="device-management"></a>Zarządzanie urządzeniami 

Chociaż ten przewodnik dotyczył konfigurowania usługi Mobile Zarządzanie urządzeniami (MDM), nie został on zastosowany do stosowania ograniczeń dotyczących urządzeń ani stosowania zasad do urządzeń. Zarządzanie urządzeniami może służyć zarówno do zezwalania na dostęp przez wypychanie certyfikatów, jak i ograniczania dostępu z różnymi ograniczeniami dotyczącymi urządzeń. 

W wielu przypadkach urządzenia mogą mieć ograniczenia łączności, takie jak Bluetooth, VPN, USB, a nawet wyłączenie dostępu do aparatu lub mikrofonu. Jeśli którekolwiek z tych zainteresowań Cię interesuje, zachęcamy do przeczytania naszej strony [typowych ograniczeń dotyczących urządzeń](hololens-common-device-restrictions.md).

Istnieją inne, bardziej złożone ograniczenia dotyczące urządzeń, których można użyć. Przykładowe metody:

- Ograniczanie stron, które można wyświetlać w aplikacji Ustawienia, za pomocą właściwości [SettingsPageVisibility](settings-uri-list.md), dzięki czemu użytkownicy mogą uzyskać dostęp tylko do ustawień, które muszą dostosować, takich jak Wi-Fi połączenia.
- Użyj [trybu kiosku,](hololens-kiosk.md) aby ograniczyć interfejs użytkownika prezentowany użytkownikom na urządzeniu. Możesz ustawić kioski tak, aby wyświetlały pojedynczą aplikację, lub wiele aplikacji z niestandardową stroną startową. Kioski mogą również prezentować różne środowisko różnym użytkownikom.  
- [Kontrola aplikacji systemu Windows (WDAC, Windows Application Control),](windows-defender-application-control-wdac.md) aby całkowicie nie uruchamiać określonych aplikacji lub procesów.

Jeśli chcesz dowiedzieć się więcej na temat różnych metod zarządzania urządzeniami lub ograniczeń dotyczących urządzeń, zapoznaj się z następnym krokiem i zapoznaj się z Zarządzanie urządzeniami Omówienie.

## <a name="next-step"></a>Następny krok

> [!div class="nextstepaction"]
> [Przeczytaj omówienie CSP i Zarządzanie urządzeniami CSP](hololens-csp-policy-overview.md)