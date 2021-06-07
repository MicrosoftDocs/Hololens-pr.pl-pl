---
title: Wprowadzenie do nowej aplikacji Ustawienia
description: Dowiedz się więcej o nowej aplikacji Ustawienia
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, ustawienia, s wyboru aplikacji, wolumin
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: bf1a2080c15346843b9ea9b2d0dc93154e185107
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379818"
---
# <a name="new-settings-app"></a>Nowa aplikacja Ustawienia

W [systemie Windows Holographic w wersji 21H1](hololens-release-notes.md#windows-holographic-version-21h1)wprowadzamy nową wersję aplikacji Ustawienia. Nowa aplikacja Ustawienia zawiera nowe funkcje i rozszerzone ustawienia dla urządzenia HoloLens 2 w następujących obszarach: Dźwięk, Power & uśpienia, Sieć & Internet, Aplikacje, Konta, Ułatwienia dostępu i inne.

> [!NOTE]
> Ponieważ nowa aplikacja Ustawienia różni się od starszej aplikacji Ustawienia, wszystkie okna ustawień umieszczone wcześniej w środowisku zostaną usunięte po aktualizacji.

![Strona główna nowej aplikacji Ustawienia](images/new-settings-app.png)

**Nowe funkcje i ustawienia**
- Wyszukiwanie ustawień: wyszukaj ustawienia na stronie głównej Ustawienia przy użyciu słów kluczowych lub nazwy ustawienia.
- Kolor > [systemu](hololens2-display.md#how-to-use-display-color-calibration)
    - Wybierz alternatywny profil kolorów dla ekranu urządzenia HoloLens 2.
- Dźwięk > systemowego:
  - Wejściowe i wyjściowe urządzenia audio: niezależne wybieranie wejściowych i wyjściowych urządzeń audio (na przykład nasłuchiwać dźwięku za pośrednictwem słuchawki Bluetooth lub używać mikrofonu USB-C do wprowadzania audio).
    > [!NOTE]
    > Mikrofony Bluetooth nie są obsługiwane przez urządzenie HoloLens 2.
  - Wolumin aplikacji: niezależnie dostosuj wolumin każdej aplikacji. Zobacz [per app volume control (Kontrola woluminu aplikacji).](holographic-home.md#per-app-volume-control)
- System > zasilania & uśpienia: wybierz, kiedy urządzenie ma przejść w stan uśpienia po okresie braku aktywności.
- System > Baterii: ręcznie włączyć tryb oszczędzanie baterii lub ustawić próg baterii, w którym punkt oszczędzanie baterii automatycznie włączyć tryb.
- Urządzenia > USB: można domyślnie wyłączyć połączenia USB.
- Sieć & Internet:
  - Karty Ethernet USB-C będą teraz wyświetlane w sieci & Internet.
  - Ustawienia karty Ethernet USB-C są teraz dostępne, w tym jej adres IP.
  - Teraz można włączyć tryb samolotowy na urządzeniach HoloLens 2.
- Aplikacje: możesz zresetować domyślne aplikacje używane dla typów plików i linków. Aby uzyskać więcej informacji, zobacz [S wyboru domyślnej aplikacji.](holographic-home.md#default-app-picker)
- Konta > innych użytkowników: właściciele urządzeń mogą dodawać użytkowników, uaktualniać użytkowników standardowych do właścicieli urządzeń, obniżać właścicieli urządzeń do użytkowników standardowych i usuwać użytkowników.
- Ułatwienia dostępu: zmiana rozmiaru tekstu i niektórych efektów wizualnych.

**Znane problemy**
- Wcześniej umieszczone okna Ustawienia zostaną usunięte (patrz uwaga powyżej).
- Nie można już zmienić nazwy urządzenia za pomocą aplikacji Ustawienia. Administratorzy IT mogą zmieniać nazwy urządzeń przy użyciu szablonu [nazwy urządzenia Windows Autopilot for HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) lub węzła MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.
- Na stronie Ethernet przez cały czas jest przedstawiane wirtualne urządzenie Ethernet ("UsbNcm").
- Użycie baterii dla nowej Microsoft Edge może nie być dokładne, ze względu na charakter aplikacji klasycznej Win32 obsługiwanej przez warstwę adaptera platformy uniwersalnej systemu Windows (nie przewiduje się wkrótce żadnej poprawki).

