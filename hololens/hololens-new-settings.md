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
ms.openlocfilehash: e6da84c180ef596b63b6d41229bd094354ab1221
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640172"
---
# <a name="new-settings-app"></a>Nowa Ustawienia aplikacji

W Windows Holographic w wersji [21H1](hololens-release-notes.md#windows-holographic-version-21h1)wprowadzamy nową wersję Ustawienia aplikacji. Nowa aplikacja Ustawienia obejmuje nowe funkcje i rozszerzone ustawienia dla usługi HoloLens 2 w następujących obszarach: dźwięk, uśpienie usługi Power &, Internet sieci &, aplikacje, konta, Ułatwienia dostępu i inne.

> [!NOTE]
> Ponieważ nowa Ustawienia aplikacji różni się od starszej Ustawienia, wszystkie okna Ustawienia wcześniej umieszczone wokół środowiska zostaną usunięte po aktualizacji.

![Strona główna Ustawienia nowej aplikacji](images/new-settings-app.png)

**Nowe funkcje i ustawienia**
- Ustawienia wyszukiwania: wyszukaj ustawienia na stronie Ustawienia głównej przy użyciu słów kluczowych lub nazwy ustawienia.
- Kolorowanie > [systemowego](hololens2-display.md#how-to-use-display-color-calibration)
    - Wybierz alternatywny profil kolorów dla ekranu HoloLens 2.
- Dźwięk > systemowego:
  - Wejściowe i wyjściowe urządzenia audio: niezależne wybieranie wejściowych i wyjściowych urządzeń audio (na przykład nasłuchiwać dźwięku za pośrednictwem mikrofonu Bluetooth lub używać mikrofonu USB-C do wprowadzania audio).
    > [!NOTE]
    > Bluetooth mikrofony nie są obsługiwane przez HoloLens 2.
  - Wolumin aplikacji: niezależnie dostosuj wolumin każdej aplikacji. Zobacz [sterowanie głośnością aplikacji.](holographic-home.md#per-app-volume-control)
- System > Power & uśpienia: wybierz, kiedy urządzenie ma przejść w stan uśpienia po okresie braku aktywności.
- System > Battery: ręcznie włącz tryb oszczędzanie baterii lub ustaw próg naładowania baterii, w którym oszczędzanie baterii jest automatycznie włączany.
- Urządzenia > USB: można domyślnie wyłączyć połączenia USB.
- Sieć & Internet:
  - Karty Ethernet USB-C będą teraz wyświetlane w sieci & Internet.
  - Dostępne są teraz ustawienia karty Ethernet USB-C, w tym jej adres IP.
  - Teraz możesz włączyć tryb samolotowy na HoloLens 2.
- Aplikacje: możesz zresetować domyślne aplikacje używane dla typów plików i linków. Aby uzyskać więcej informacji, zobacz [S wyboru domyślnej aplikacji.](holographic-home.md#default-app-picker)
- Konta > innych użytkowników: właściciele urządzeń mogą dodawać użytkowników, uaktualniać użytkowników standardowych do właścicieli urządzeń, obniżanie poziomu właścicieli urządzeń do użytkowników standardowych i usuwanie użytkowników.
- Ułatwienia dostępu: zmiana rozmiaru tekstu i niektórych efektów wizualnych.

**Znane problemy**
- Wcześniej umieszczone Ustawienia zostaną usunięte (patrz uwaga powyżej).
- Nie można już zmienić nazwy urządzenia na Ustawienia aplikacji. Administratorzy IT mogą zmieniać nazwy urządzeń za pomocą szablonu nazwy urządzenia Windows [Autopilot for HoloLens 2](hololens2-autopilot.md) lub węzła MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.
- Na stronie Ethernet przez cały czas jest wyświetlane wirtualne urządzenie Ethernet ("UsbNcm").
- Użycie baterii dla nowej Microsoft Edge może być niedokładne ze względu na jej charakter jako aplikacja komputerowa Win32 obsługiwana przez warstwę karty platformy uniwersalnej systemu Windows (nie przewiduje się wkrótce żadnej poprawki).

