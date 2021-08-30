---
title: Wprowadzenie do nowej Ustawienia aplikacji
description: Dowiedz się więcej o nowej Ustawienia aplikacji
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, ustawienia, s wyboru aplikacji, wolumin
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: bcde697b5887573826a3a1a61e8c3707b4d0337a
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189668"
---
# <a name="new-settings-app"></a>Nowa Ustawienia aplikacji

W Windows Holographic w wersji [21H1](hololens-release-notes.md#windows-holographic-version-21h1)wprowadzamy nową wersję Ustawienia aplikacji. Nowa aplikacja Ustawienia zawiera nowe funkcje i rozszerzone ustawienia dla usługi HoloLens 2 w następujących obszarach: Dźwięk, Power & uśpienia, Sieć & Internet, Aplikacje, Konta, Ułatwienia dostępu i inne.

> [!NOTE]
> Ponieważ nowa aplikacja Ustawienia różni się od starszej Ustawienia, wszystkie okna Ustawienia wcześniej umieszczone wokół środowiska zostaną usunięte po aktualizacji.

![Nowa Ustawienia aplikacji.](images/new-settings-app.png)

**Nowe funkcje i ustawienia**
- Ustawienia wyszukiwania: wyszukaj ustawienia ze strony głównej Ustawienia, używając słów kluczowych lub nazwy ustawienia.
- Kolorowanie > [systemu](hololens2-display.md#how-to-use-display-color-calibration)
    - Wybierz alternatywny profil kolorów dla ekranu HoloLens 2.
- Dźwięk > systemu:
  - Wejściowe i wyjściowe urządzenia audio: niezależne wybieranie wejściowych i wyjściowych urządzeń audio (na przykład nasłuchiwać dźwięku za pośrednictwem mikrofonu Bluetooth lub używać mikrofonu USB-C do wprowadzania audio).
    > [!NOTE]
    > Bluetooth nie są obsługiwane przez HoloLens 2.
  - Wolumin aplikacji: niezależnie dostosuj wolumin każdej aplikacji. Zobacz [per app volume control (Kontrola woluminu aplikacji).](holographic-home.md#per-app-volume-control)
- System > power & uśpienia: wybierz, kiedy urządzenie ma przejść w stan uśpienia po okresie braku aktywności.
- System > Baterii: ręcznie włączyć tryb oszczędzanie baterii lub ustawić próg baterii, w którym punkt oszczędzanie baterii automatycznie włączyć tryb.
- Urządzenia > USB: można domyślnie wyłączyć połączenia USB.
- Sieć & Internet:
  - Karty Ethernet USB-C będą teraz wyświetlane w sieci & Internet.
  - Ustawienia karty Ethernet USB-C są teraz dostępne, łącznie z jej adresem IP.
  - Teraz można włączyć tryb samolotowy na HoloLens 2.
- Aplikacje: możesz zresetować domyślne aplikacje używane dla typów plików i linków. Aby uzyskać więcej informacji, zobacz [S wyboru domyślnej aplikacji.](holographic-home.md#default-app-picker)
- Konta > innych użytkowników: właściciele urządzeń mogą dodawać użytkowników, uaktualniać użytkowników standardowych do właścicieli urządzeń, obniżać właścicieli urządzeń do standardowych użytkowników i usuwać użytkowników.
- Ułatwienia dostępu: zmiana rozmiaru tekstu i niektórych efektów wizualnych.

**Znane problemy**
- Wcześniej umieszczone Ustawienia zostaną usunięte (patrz uwaga powyżej).
- Nie można już zmienić nazwy urządzenia na Ustawienia aplikację. Administratorzy IT mogą zmieniać nazwy urządzeń za pomocą szablonu nazwy urządzenia rozwiązania [Windows Autopilot for HoloLens 2](hololens2-autopilot.md) lub węzła MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.
- Na stronie Ethernet przez cały czas jest przedstawiane wirtualne urządzenie Ethernet ("UsbNcm").
- Użycie baterii dla nowej Microsoft Edge może być niedokładne, ze względu na charakter aplikacji klasycznej Win32 obsługiwanej przez warstwę adaptera platformy uniwersalnej systemu Windows (nie przewiduje się wkrótce żadnej poprawki).

