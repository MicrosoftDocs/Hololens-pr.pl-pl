---
title: Przewodnik wdrażania — przewodnik po HoloLens 2 z usługą Dynamics 365 — obsługa
description: Dowiedz się, jak utrzymywać HoloLens 2 za pośrednictwem firmowej połączonej sieci przy użyciu przewodników usługi Dynamics 365.
keywords: HoloLens, zarządzanie, połączenie firmowe, przewodniki usługi Dynamics 365, AAD, Azure AD, MDM, Mobile Zarządzanie urządzeniami
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
ms.openlocfilehash: 2649e370e98747562591c031b8ae262674c831e071f4ef228557dda66d2dc768
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660270"
---
# <a name="maintain---corporate-connected-guide"></a>Obsługa — przewodnik po połączeniach firmowych

## <a name="update-hololens"></a>Aktualizowanie HoloLens

Firma Microsoft zaprojektowała usługę Windows Update dla Firm, aby zapewnić administratorom IT dodatkowe funkcje zarządzania zorientowane na aktualizacje usługi Windows, takie jak możliwość wdrażania aktualizacji w grupach urządzeń i definiowania okien obsługi na potrzeby instalowania aktualizacji.

Jedną z popularnych metod zarządzania aktualizacjami jest odroczenie funkcji o 30 dni. Dzięki temu administratorzy mogą aktualizować i wyświetlać nowe funkcje w wersji zapoznawczej, uzyskując wiedzę z pierwszej ręki i informując personel pomocy technicznej o wszelkich nowych zmianach.

Dowiedz się, [jak zarządzać aktualizacjami](/hololens/hololens-updates)HoloLens, w tym zaplanowanymi dniami, zaplanowaną godziną i ustawianiem aktywnych godzin na urządzeniu, aby aktualizować je poza godzinami pracy.

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Jak zaktualizować przewodniki usługi Dynamics 365 (i inne aplikacje ze sklepu)

Przewodniki usługi Dynamics 365 to In-Box, które można aktualizować za pośrednictwem Microsoft Store aplikacji. Wszystkie aplikacje pobierane za pośrednictwem Microsoft Store można zaktualizować za pośrednictwem Microsoft Store [aplikacji](/hololens/holographic-store-apps#update-apps) ręcznie.

## <a name="how-to-update-lob-apps"></a>Jak aktualizować aplikacje LOB

Aplikacje LOB można aktualizować w taki sam sposób, jak zostały dodane do usługi Intune. Aplikacje można zaktualizować w usłudze Intune, przesyłając nową aplikację o wyższym numerze wersji do istniejącej konfiguracji aplikacji. Gdy urządzenie zostanie zsynchronizowane z usługą Intune, zauważy, że istnieje nowsza wersja aplikacji, a nowsza aplikacja zostanie pobrana i zastąpi starą.

1. Aby przekazać nowszą aplikację, przejdź do portalu [MEM](https://endpoint.microsoft.com/#home)  ->  **Apps** -> Wszystkie **aplikacje**  ->  *TheNameOfYourApp*  ->  **Properties.**
2. Obok opcji Informacje o aplikacji wybierz pozycję **Edytuj.**
3. Dla wartości Wybierz &quot; plik do zaktualizowania &quot; wybierz swój plik.
4. W tym miejscu użyj menu kontekstowego, aby otworzyć Eksploratora plików i przekazać nowszą wersję aplikacji LOB. Upewnij się, że zależności są dołączane zgodnie z potrzebami.

Zobacz więcej: [Wdrażanie aplikacji usługi Intune dla HoloLens](/hololens/app-deploy-intune)

## <a name="development-plan"></a>Plan rozwoju

Po pomyślnym zarejestrowaniu urządzenia możesz teraz przygotować się do wdrożenia większej liczby aplikacji LOB na urządzeniach. W tym przewodniku używamy przykładowej aplikacji, ale bardziej prawdopodobne jest, że będziesz chcieć używać aplikacji niestandardowych sbudowaną na potrzeby twojej organizacji.

Jeśli masz już aplikację LOB, możesz wdrożyć aplikację za pośrednictwem [rozwiązania MDM.](/hololens/app-deploy-intune) Jeśli wolisz inną metodę, zapoznaj się z omówieniem wdrażania aplikacji dla usługi [HoloLens 2,](/hololens/app-deploy-overview) aby dowiedzieć się więcej na temat metod wdrażania aplikacji LOB na urządzeniach.

Jeśli nie masz jeszcze czasu na utworzenie własnej aplikacji LOB lub nadal jesteś w trakcie tworzenia, zapoznaj się z naszymi dokumentami programistyczną rzeczywistości mieszanej, aby rozpocząć projektowanie i [tworzenie prototypów,](/windows/mixed-reality/design/design) lub poznaj podstawowe pojęcia, aby rozpocząć tworzenie rzeczywistości [mieszanej.](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="support-plan"></a>Plan pomocy technicznej

Plan pomocy technicznej jest doskonałym rozwiązaniem. Przydatne jest przeszkolenie kogoś lub grupy w zakresie rozwiązywania problemów z procesem rejestracji na urządzeniach HoloLens, a także ogólnego użycia urządzenia HoloLens w organizacji. Aby umożliwić użytkownikom szybsze rozwiązanie ich problemów, sugerujemy, aby proces eskalacji był obsługiwany w sposób podobny do tego:

1. Pomoc techniczna.
2. Twój HoloLens ekspertów
3. [HoloLens Docs](/hololens/)  /  [HoloLens troubleshooting Docs (Rozwiązywanie problemów z dokumentów)](/hololens/hololens-troubleshooting)
4. [Kontakt z pomocą techniczną](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>Zarządzanie urządzeniami

W tym przewodniku omówienia konfigurowania usługi Mobile Zarządzanie urządzeniami (MDM) i używanego do konfigurowania niektórych konfiguracji urządzeń i stosowania ustawień w celu umożliwienia dostępu w zakresie certyfikatów Wi-Fi i serwera proxy. Jednak rozwiązania MDM można również używać do stosowania ograniczeń urządzenia za pośrednictwem CSP i zasad.

W wielu przypadkach urządzenia mogą mieć ograniczenia łączności, takie jak Bluetooth sieci VPN, USB, a nawet wyłączenie dostępu do aparatu lub mikrofonu. Jeśli którekolwiek z tych zainteresowań Cię interesuje, zachęcamy do przeczytania naszej strony [typowych ograniczeń dotyczących urządzeń](/hololens/hololens-common-device-restrictions).

Istnieją inne, bardziej złożone ograniczenia dotyczące urządzeń, których można użyć. Przykładowe metody:

- Ograniczanie stron, które można wyświetlać w aplikacji Ustawienia, przy użyciu właściwości [SettingsPageVisibility](/hololens/settings-uri-list), dzięki czemu użytkownicy mogą uzyskać dostęp tylko do ustawień, które muszą dostosować, takich jak Wi-Fi połączenia.
- Użyj [trybu kiosku,](/hololens/hololens-kiosk) aby ograniczyć interfejs użytkownika prezentowany użytkownikom na urządzeniu. Możesz ustawić kioski tak, aby wyświetlały pojedynczą aplikację lub wiele aplikacji przy użyciu niestandardowej strony startowej. Kioski mogą również przedstawiać różne środowisko różnym użytkownikom.
- [Windows kontroli aplikacji (WDAC),](/hololens/windows-defender-application-control-wdac) aby całkowicie nie uruchamiać określonych aplikacji lub procesów.

Jeśli chcesz dowiedzieć się więcej o dodatkowych metodach zarządzania urządzeniami lub ograniczeniach dotyczących urządzeń, skorzystaj z następnego kroku i przeczytaj nasz [Zarządzanie urządzeniami Omówienie.](/hololens/hololens-csp-policy-overview)





