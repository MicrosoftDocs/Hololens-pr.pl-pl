---
title: Połączenie do Bluetooth i USB-C
description: Wprowadzenie do nawiązywania połączenia Bluetooth urządzeniami i akcesoriami USB-C z urządzeń HoloLens rzeczywistości mieszanej.
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
ms.openlocfilehash: 5fed56d7a0beeda0a0d96eddc63aaee872f3e52d
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639101"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Połączenie do Bluetooth i USB-C

## <a name="pair-bluetooth-devices"></a>Parowanie Bluetooth urządzeń

HoloLens 2 obsługuje następujące klasy Bluetooth urządzeń:

- [HID:](/windows-hardware/drivers/hid/)
    - Mysz
    - Klawiatura
- Urządzenia wyjściowe audio (A2DP)

HoloLens 2 obsługuje następujące interfejsy BLUETOOTH API:
- Serwer [](/windows/uwp/devices-sensors/gatt-server) i klient [ZOI](/windows/uwp/devices-sensors/gatt-client)
- [RFCOMM](/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> Może być trzeba zainstalować odpowiednie aplikacje towarzyszące z Microsoft Store, aby w rzeczywistości korzystać z urządzeń HID i THE.

HoloLens (1. generacji) obsługuje następujące klasy urządzeń Bluetooth:

- Mysz
- Klawiatura
- [HoloLens (1. generacja)](hololens1-clicker.md)

> [!NOTE]
> Inne typy urządzeń Bluetooth, takie jak głośników, zestawy nagłowne, smartfony i konsoli do gier, mogą być wyświetlane jako dostępne w HoloLens ustawieniach. Jednak te urządzenia nie są obsługiwane na urządzeniach HoloLens (1. generacji). Aby uzyskać więcej informacji, zobacz HoloLens Ustawienia listę urządzeń [jako dostępnych, ale urządzenia nie działają.](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work)

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Parowanie klawiatury Bluetooth myszy lub klawiatury

1. Włącz klawiaturę lub mysz, aby było możliwe do odnajdywania. Aby dowiedzieć się, jak sprawić, aby urządzenie było wykrywalne, poszukaj informacji na urządzeniu (lub w jego dokumentacji) lub odwiedź witrynę internetową producenta.

1. Użyj gestu Blooma (HoloLens (1. generacja)) lub gestu uruchamiania (HoloLens 2), aby przejść do opcji **Start**, a następnie wybierz pozycję **Ustawienia**.

1. Wybierz **pozycję** Urządzenia i upewnij się, Bluetooth jest wł.  

1. Gdy zobaczysz nazwę urządzenia, wybierz pozycję **Sparuj,** a następnie postępuj zgodnie z instrukcjami.

## <a name="disable-bluetooth"></a>Wyłącz Bluetooth

Ta procedura wyłącza składniki RF przycisku radiowego Bluetooth i wyłącza wszystkie Bluetooth na Microsoft HoloLens.

1. Użyj gestu Blooma (HoloLens (1. generacja)) lub gestu uruchamiania (HoloLens 2), aby przejść do strony Start **,** a następnie wybrać pozycję Ustawienia  >  **Urządzenia.**

1. Przenieś przełącznik suwaka dla **Bluetooth** w **położenie** Wyłączone.

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: Połączenie USB-C

HoloLens 2 obsługuje następujące klasy urządzeń USB-C:

- Urządzenia pamięci masowej (takie jak dyski miniatur)
- Karty Ethernet (w tym karty Ethernet i ładowanie)
- Adaptery usb-C-to-3.5mm do cyfrowych audio
- Cyfrowe zestawy audio USB-C (w tym adaptery nagłowne i ładowanie)
- Zewnętrzne mikrofony USB-C ([Windows Holographic, wersja 21H1](hololens-release-notes.md#windows-holographic-version-21h1) lub nowsza)
- Mysz przewodowa
- Klawiatura przewodowa
- Koncentratory z kombinacją pd (ładowanie za pomocą portu USB A i pd)


> [!NOTE]
> W odpowiedzi na opinie klientów włączyliśmy ograniczoną obsługę łączności komórkowej bezpośrednio z siecią HoloLens za pośrednictwem portu USB-C. Zobacz [Połączenie do sieci komórkowej i 5G,](hololens-cellular.md) aby uzyskać więcej informacji.

### <a name="usb-c-external-microphone-support"></a>Obsługa zewnętrznego mikrofonu USB-C

> [!IMPORTANT]
> Podłączanie **mikrofonu USB nie ustawi go** automatycznie jako urządzenia wejściowego . Podczas podłączania zestawu słuchawki USB-C użytkownicy zauważą, że dźwięk telefonu komórkowego zostanie automatycznie przekierowany do słuchawki, ale system operacyjny HoloLens ustawia priorytet wewnętrznej macierzy mikrofonu nad każdym innym urządzeniem wejściowym. **Aby użyć mikrofonu USB-C, wykonaj poniższe kroki.**

> [!NOTE]
> Nie można używać mikrofonów zewnętrznych w kompilacjach wcześniejszych niż Windows Holographic w wersji [21H1](hololens-release-notes.md#windows-holographic-version-21h1) lub wyższej. 

Użytkownicy mogą wybierać zewnętrzne mikrofony podłączone do dysku USB C przy użyciu **panelu Ustawień** dźwięku. Mikrofony USB-C mogą służyć do wywoływania, nagrywania itp.

Otwórz aplikację **Ustawienia** wybierz **pozycję Dźwięk**  >  **systemowy.**

![Dźwięk Ustawienia](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Aby używać mikrofonów zewnętrznych z **usługą Remote Assist,** użytkownicy będą musieli kliknąć hiperlink "Zarządzanie urządzeniami dźwiękowymi".
>
> Następnie użyj listy rozwijanej, aby ustawić zewnętrzny mikrofon jako **domyślny lub** domyślny **dla komunikacji.** Wybranie **opcji** Domyślne oznacza, że zewnętrzny mikrofon będzie używany wszędzie.
>
> Wybranie **opcji Domyślna** komunikacja oznacza, że mikrofon zewnętrzny będzie używany w uchęce Zdalnej pomocy i innych aplikacjach komunikacyjnych, ale macierz mikrofonu HoloLens nadal może być używana do innych zadań.

![Zarządzanie urządzeniami dźwiękowymi](images/usbc-mic-2.png)

<br>

![Ustawianie domyślnego mikrofonu](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>A co z Bluetooth mikrofonu?

Niestety, Bluetooth mikrofony nadal nie są obecnie obsługiwane w HoloLens 2.

### <a name="usb-c-hubs"></a>Koncentratory USB-C

Niektórzy użytkownicy mogą wymagać połączenia wielu urządzeń jednocześnie. W przypadku użytkowników, którzy chcą używać mikrofonu [USB-C](#usb-c-external-microphone-support) wraz z innym połączonym urządzeniem, koncentratory USB-C mogą być dopasowane do potrzeb klienta. Firma Microsoft nie przetestowała tych urządzeń ani nie może zalecać żadnych konkretnych marek.

**Wymagania dotyczące koncentratora USB-C i podłączonych urządzeń:**

- Podłączone urządzenia nie mogą wymagać zainstalowania sterownika.
- Całkowity pobór mocy wszystkich połączonych urządzeń musi być poniżej 4,5 Watów.

## <a name="connect-to-miracast"></a>Połączenie do Miracast

Aby użyć Miracast, wykonaj następujące kroki:

1. Wykonaj jedną z następujących czynności:  

   - Otwórz menu **Start** i wybierz **ikonę Wyświetl.**
   - Powiedz "Połączenie", gdy spojrzysz na menu **Start.**  

1. Na wyświetlonej liście urządzeń wybierz dostępne urządzenie.

1. Ukończ parowanie, aby rozpocząć rzutowanie.
