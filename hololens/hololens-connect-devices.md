---
title: Połączenie do Bluetooth i usb-C
description: Rozpoczynanie nawiązywania połączenia z Bluetooth i urządzeniami USB-C oraz akcesoriami z urządzeń HoloLens rzeczywistości mieszanej.
ms.assetid: 01af0848-3b36-4c13-b797-f38ad3977e30
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 03/11/2020
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: d9c8b813ba54edbcfef8d1a32e641dad39a7f193
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036024"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Połączenie do Bluetooth i usb-C

## <a name="pair-bluetooth-devices"></a>Parowanie Bluetooth urządzeń

HoloLens 2 obsługuje następujące klasy urządzeń Bluetooth urządzeń:

- [HID:](/windows-hardware/drivers/hid/)
    - Mysz
    - Klawiatura
- Urządzenia wyjściowe audio (A2DP)

HoloLens 2 obsługuje następujące interfejsy BLUETOOTH API:
- Serwer [](/windows/uwp/devices-sensors/gatt-server) i [klient](/windows/uwp/devices-sensors/gatt-client) DNS
- [RFCOMM](/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> Może być trzeba zainstalować odpowiednie aplikacje towarzyszące z Microsoft Store, aby w rzeczywistości używać urządzeń HID iINSTALOWAĆ.

HoloLens (1. generacji) obsługuje następujące klasy urządzeń Bluetooth:

- Mysz
- Klawiatura
- [HoloLens (1. generacja)](hololens1-clicker.md)

> [!NOTE]
> Inne typy urządzeń Bluetooth, takie jak głośniki, zestawy nagłowne, smartfony i konsoli do gier, mogą być wyświetlane jako dostępne w HoloLens ustawień. Jednak te urządzenia nie są obsługiwane na urządzeniach HoloLens (1. generacji). Aby uzyskać więcej informacji, [zobacz HoloLens Ustawienia lista urządzeń jako dostępnych, ale urządzenia nie działają.](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work)

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Parowanie Bluetooth klawiatury lub myszy

1. Włącz klawiaturę lub mysz, aby było możliwe do odnajdywania. Aby dowiedzieć się, jak sprawić, aby urządzenie było wykrywalne, poszukaj informacji na urządzeniu (lub w jego dokumentacji) lub odwiedź witrynę internetową producenta.

1. Użyj gestu Blooma (HoloLens (1. generacja)) lub gestu uruchamiania (HoloLens 2), aby przejść do opcji **Start**, a następnie wybierz **pozycję Ustawienia**.

1. Wybierz **pozycję** Urządzenia i upewnij się, Bluetooth jest wł.  

1. Po wyświetleniu nazwy urządzenia wybierz pozycję **Sparuj**, a następnie postępuj zgodnie z instrukcjami.

## <a name="disable-bluetooth"></a>Wyłącz Bluetooth

Ta procedura wyłącza składniki RF przycisku radiowego Bluetooth i wyłącza wszystkie Bluetooth na Microsoft HoloLens.

1. Użyj gestu Blooma (HoloLens (1. generacja)) lub gestu uruchamiania (HoloLens 2), aby przejść do opcji **Start**, a następnie wybierz pozycję Ustawienia  >  **Urządzenia.**

1. Przesuń przełącznik suwaka dla **Bluetooth** do **pozycji** Wyłączone.

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: Połączenie USB-C

HoloLens 2 obsługuje następujące klasy urządzeń USB-C:

- Urządzenia pamięci masowej (takie jak dyski kciuka)
- Karty Ethernet (w tym ethernet i ładowanie)
- Adaptery audio usb-C-do-3,5 mm
- Cyfrowe zestawy nagłowne USB-C (w tym adaptery zestawów nagłownych i ładowanie)
- Zewnętrzne mikrofony USB-C ([Windows Holographic, wersja 21H1](hololens-release-notes.md#windows-holographic-version-21h1) lub nowsza)
- Mysz przewodowa
- Klawiatura przewodowa
- Koncentratory PD z kombinacją (ładowanie za pomocą portu USB A i PD)


> [!NOTE]
> W odpowiedzi na opinie klientów włączyliśmy ograniczoną obsługę łączności komórkowej związanej bezpośrednio z siecią HoloLens za pośrednictwem portu USB-C. Aby uzyskać Połączenie, zobacz Połączenie do sieci komórkowej i [sieci 5G.](hololens-cellular.md)

### <a name="usb-c-external-microphone-support"></a>Obsługa mikrofonu zewnętrznego USB-C

> [!IMPORTANT]
> Podłączanie **mikrofonu USB nie spowoduje automatycznego ustawienia go jako urządzenia wejściowego.** Podczas podłączania zestawu mikrofonów USB C użytkownicy będą obserwowali, że dźwięk telefonu komórkowego zostanie automatycznie przekierowany do mikrofonu, ale system operacyjny HoloLens określa priorytet wewnętrznej macierzy mikrofonu nad każdym innym urządzeniem wejściowym. **Aby użyć mikrofonu USB-C, wykonaj poniższe kroki.**

> [!NOTE]
> Nie można używać zewnętrznych mikrofonów w kompilacjach przed Windows Holographic w wersji [21H1](hololens-release-notes.md#windows-holographic-version-21h1) lub wyższej. 

Użytkownicy mogą wybierać zewnętrzne mikrofony podłączone do portu USB C przy użyciu **panelu Ustawień** dźwięku. Mikrofony USB-C mogą służyć do wywoływania, nagrywania itp.

Otwórz aplikację **Ustawienia** i wybierz **pozycję Dźwięk**  >  **systemowy.**

![Dźwięk Ustawienia.](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Aby używać mikrofonów zewnętrznych z **usługą Remote Assist,** użytkownicy muszą kliknąć hiperlink "Zarządzanie urządzeniami dźwiękowymi".
>
> Następnie użyj listy rozwijanej, aby ustawić zewnętrzny mikrofon jako **Domyślny lub** Domyślny **dla komunikacji.** Wybranie **opcji Domyślne** oznacza, że zewnętrzny mikrofon będzie używany wszędzie.
>
> Wybranie **opcji Domyślna** komunikacja oznacza, że zewnętrzny mikrofon będzie używany w uciece zdalnej pomocy i innych aplikacjach komunikacyjnych, ale HoloLens macierz mikrofonu może być nadal używana do innych zadań.

![Zarządzanie urządzeniami dźwiękowymi.](images/usbc-mic-2.png)

<br>

![Ustaw wartość domyślną mikrofonu.](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Co z obsługą Bluetooth mikrofonu?

Niestety, Bluetooth mikrofony nadal nie są obecnie obsługiwane na HoloLens 2.

### <a name="usb-c-hubs"></a>Koncentratory USB-C

Niektórzy użytkownicy mogą wymagać połączenia wielu urządzeń jednocześnie. W przypadku użytkowników, którzy chcą używać mikrofonu [USB-C](#usb-c-external-microphone-support) wraz z innym połączonym urządzeniem, koncentratory USB-C mogą być dopasowane do potrzeb klienta. Firma Microsoft nie przetestowała tych urządzeń ani nie możemy zalecić żadnych określonych marek.

**Wymagania dotyczące koncentratora USB-C i podłączonych urządzeń:**

- Podłączone urządzenia nie mogą wymagać zainstalowania sterownika.
- Łączny pobór mocy wszystkich podłączonych urządzeń musi być poniżej 4,5 Watów.

## <a name="connect-to-miracast"></a>Połączenie do Miracast

Aby użyć Miracast, wykonaj następujące kroki:

1. Wykonaj jedną z następujących czynności:  

   - Otwórz menu **Start** i wybierz **ikonę Wyświetl.**
   - Powiedz "Połączenie" podczas spojrzenia na menu **Start.**  

1. Na wyświetlonej liście urządzeń wybierz dostępne urządzenie.

1. Ukończ parowanie, aby rozpocząć rzutowanie.
