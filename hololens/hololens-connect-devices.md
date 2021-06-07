---
title: Nawiązywanie połączenia z urządzeniami Bluetooth i USB-C
description: Rozpoczynanie nawiązywania połączenia z urządzeniami Bluetooth i USB-C oraz akcesoriami z urządzeń HoloLens rzeczywistości mieszanej.
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
ms.openlocfilehash: ffae65a6e1c096242ae7a28c488896c65df1c62d
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379763"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Nawiązywanie połączenia z urządzeniami Bluetooth i USB-C

## <a name="pair-bluetooth-devices"></a>Parowanie urządzeń Bluetooth

Urządzenie HoloLens 2 obsługuje następujące klasy urządzeń Bluetooth:

- [HID:](https://docs.microsoft.com/windows-hardware/drivers/hid/)
    - Mysz
    - Klawiatura
- Urządzenia wyjściowe audio (A2DP)

Urządzenie HoloLens 2 obsługuje następujące interfejsy API bluetooth:
- Serwer [](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) i klient [ZOI](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client)
- [RFCOMM](https://docs.microsoft.com/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> Może być trzeba zainstalować odpowiednie aplikacje towarzyszące z Microsoft Store, aby w rzeczywistości korzystać z urządzeń HID i THE.

Urządzenie HoloLens (1. generacji) obsługuje następujące klasy urządzeń Bluetooth:

- Mysz
- Klawiatura
- [Kliknięcie urządzenia HoloLens (1. generacji)](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> Inne typy urządzeń Bluetooth, takie jak głośniky, zestawy nagłowne, smartfony i konsoli do gier, mogą być wyświetlane jako dostępne w ustawieniach urządzenia HoloLens. Jednak te urządzenia nie są obsługiwane na urządzeniu HoloLens (1. generacji). Aby uzyskać więcej informacji, zobacz [Ustawienia urządzenia HoloLens zawiera](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)listę urządzeń jako dostępnych, ale urządzenia nie działają.

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Parowanie klawiatury lub myszy Bluetooth

1. Włącz klawiaturę lub mysz, aby było możliwe do odnajdywania. Aby dowiedzieć się, jak sprawić, aby urządzenie było wykrywalne, poszukaj informacji na urządzeniu (lub w jego dokumentacji) lub odwiedź witrynę internetową producenta.

1. Użyj gestu Blooma (HoloLens (1. generacja)) lub gestu uruchamiania (HoloLens 2), aby przejść do menu **Start,** a następnie wybrać pozycję **Ustawienia**.

1. Wybierz **pozycję Urządzenia** i upewnij się, że połączenie Bluetooth jest wł.  

1. Gdy zobaczysz nazwę urządzenia, wybierz pozycję **Sparuj,** a następnie postępuj zgodnie z instrukcjami.

## <a name="disable-bluetooth"></a>Wyłącz funkcję Bluetooth

Ta procedura powoduje wyłączenie składników RF przycisku radiowego Bluetooth i wyłączenie wszystkich funkcji Bluetooth na Microsoft HoloLens.

1. Użyj gestu Blooma (HoloLens (1. generacja)) lub gestu uruchamiania (HoloLens 2), aby przejść do menu **Start,** a następnie wybrać pozycję  >  **Ustawienia Urządzenia.**

1. Przesuń przełącznik suwaka dla **połączenia Bluetooth** do **pozycji** Wyłączone.

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: łączenie urządzeń USB-C

Urządzenie HoloLens 2 obsługuje następujące klasy urządzeń USB-C:

- Urządzenia pamięci masowej (takie jak dyski miniatur)
- Karty Ethernet (w tym karty Ethernet i ładowanie)
- Adaptery usb-C-to-3.5mm do cyfrowych audio
- Cyfrowe zestawy audio USB-C (w tym adaptery nagłowne i ładowanie)
- Zewnętrzne mikrofony USB-C[(system Windows Holographic, wersja 21H1](hololens-release-notes.md#windows-holographic-version-21h1) lub nowsza)
- Mysz przewodowa
- Klawiatura przewodowa
- Koncentratory z kombinacją pd (ładowanie za pomocą portu USB A i pd)


> [!NOTE]
> W odpowiedzi na opinie klientów włączyliśmy ograniczoną obsługę łączności komórkowej bezpośrednio z urządzeniem HoloLens za pośrednictwem portu USB-C. Aby uzyskać więcej informacji, zobacz [Connect to Cellular and 5G (Łączenie](hololens-cellular.md) z siecią komórkową i 5G).

### <a name="usb-c-external-microphone-support"></a>Obsługa zewnętrznego mikrofonu USB-C

> [!IMPORTANT]
> Podłączanie **mikrofonu USB nie ustawi go** automatycznie jako urządzenia wejściowego . Podczas podłączania zestawu słuchawki USB-C użytkownicy zauważą, że dźwięk telefonu komórkowego zostanie automatycznie przekierowany do słuchawki, ale system operacyjny HoloLens określa priorytet wewnętrznej macierzy mikrofonów nad innym urządzeniem wejściowym. **Aby użyć mikrofonu USB-C, wykonaj poniższe kroki.**

> [!NOTE]
> Nie można używać mikrofonów zewnętrznych w kompilacjach wcześniejszych niż Windows Holographic w wersji [21H1](hololens-release-notes.md#windows-holographic-version-21h1) lub wyższej. 

Użytkownicy mogą wybierać zewnętrzne mikrofony podłączone do dysku USB C przy użyciu **panelu Ustawień** dźwięku. Mikrofony USB-C mogą służyć do wywoływania, nagrywania itp.

Otwórz aplikację **Ustawienia** i wybierz **pozycję Dźwięk**  >  **systemowy.**

![Ustawienia dźwięku](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Aby używać mikrofonów zewnętrznych z **usługą Remote Assist,** użytkownicy będą musieli kliknąć hiperlink "Zarządzanie urządzeniami dźwiękowymi".
>
> Następnie użyj listy rozwijanej, aby ustawić zewnętrzny mikrofon jako **domyślny lub** domyślny **dla komunikacji.** Wybranie **opcji** Domyślne oznacza, że zewnętrzny mikrofon będzie używany wszędzie.
>
> Wybranie **opcji Domyślna** komunikacja oznacza, że zewnętrzny mikrofon będzie używany w uchęce Remote Assist i innych aplikacjach komunikacyjnych, ale macierz mikrofonu HoloLens może być nadal używana do innych zadań.

![Zarządzanie urządzeniami dźwiękowymi](images/usbc-mic-2.png)

<br>

![Ustawianie domyślnego mikrofonu](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>A co z obsługą mikrofonu Bluetooth?

Niestety mikrofony Bluetooth nadal nie są obecnie obsługiwane na urządzeniu HoloLens 2.

#### <a name="troubleshooting-usb-c-microphones"></a>Rozwiązywanie problemów z mikrofonami USB-C

Należy pamiętać, że niektóre mikrofony USB-C nieprawidłowo zgłaszają się jako mikrofon i *prelegent.* Jest to problem z mikrofonem, a nie z urządzeniem HoloLens. Podczas podłączania jednego z tych mikrofonów do urządzenia HoloLens dźwięk może zostać utracony. Na szczęście istnieje prosta poprawka.  

W   ->  **ustawieniach Dźwięk** systemowy jawnie ustaw wbudowane osoby mówiące (sterownik audio funkcji analogicznej) jako domyślne  ->   **urządzenie**.  Urządzenie HoloLens powinno zapamiętać to ustawienie, nawet jeśli mikrofon zostanie później usunięty i ponownie podłączony.

![Rozwiązywanie problemów z mikrofonami USB-C](images/usbc-mic-4.png)
### <a name="usb-c-hubs"></a>Koncentratory USB-C

Niektórzy użytkownicy mogą wymagać połączenia wielu urządzeń jednocześnie. W przypadku użytkowników, którzy chcą używać mikrofonu [USB-C](#usb-c-external-microphone-support) wraz z innym połączonym urządzeniem, koncentratory USB-C mogą być dopasowane do potrzeb klienta. Firma Microsoft nie przetestowała tych urządzeń ani nie może zalecać żadnych konkretnych marek.

**Wymagania dotyczące koncentratora USB-C i podłączonych urządzeń:**

- Podłączone urządzenia nie mogą wymagać zainstalowania sterownika.
- Całkowity pobór mocy wszystkich połączonych urządzeń musi być poniżej 4,5 Watów.

## <a name="connect-to-miracast"></a>Nawiązywanie połączenia z miracastem

Aby użyć funkcji Miracast, wykonaj następujące kroki:

1. Wykonaj jedną z następujących czynności:  

   - Otwórz menu **Start** i wybierz **ikonę Wyświetl.**
   - Powiedz "Połącz", gdy spojrzysz na menu **Start.**  

1. Na wyświetlonej liście urządzeń wybierz dostępne urządzenie.

1. Ukończ parowanie, aby rozpocząć rzutowanie.
