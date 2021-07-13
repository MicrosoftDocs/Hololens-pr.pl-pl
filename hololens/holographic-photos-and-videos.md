---
title: Przechwytywanie, rejestrowanie i udostępnianie zdjęć i wideo rzeczywistości mieszanej
description: Dowiedz się, jak przechwytywać, rejestrować i wyświetlać zdjęcia i wideo rzeczywistości mieszanej przy użyciu HoloLens rzeczywistości mieszanej. Dowiedz się, jak udostępniać za pośrednictwem Miracast lub zebranych plików.
keywords: hololens, photo, video, capture, mrc, mixed reality capture, photos, camera, miracast, stream, livestream, demo, record
ms.assetid: 1b636ec3-6186-4fbb-81b2-71155aef0593
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 10/28/2019
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: daced6fab65f779b7bd670bf1275f99ae5311d3f
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635963"
---
# <a name="create-mixed-reality-photos-and-videos"></a>Tworzenie zdjęć i wideo rzeczywistości mieszanej

HoloLens zapewnia użytkownikom środowisko łączenia świata rzeczywistego ze światem cyfrowym.  Funkcja przechwytywania rzeczywistości mieszanej (MRC, mixed reality capture) umożliwia przechwytywanie tego doświadczenia jako zdjęcia lub wideo albo udostępnianie tego, co widzisz innym osobom w czasie rzeczywistym.

Przechwytywanie rzeczywistości mieszanej używa punktu widzenia pierwszej osoby, aby inne osoby widziały hologramów, gdy je widzisz. W przypadku punktu widzenia osoby trzeciej użyj [widoku chybnego](/windows/mixed-reality/spectator-view). Widok zdumień jest szczególnie przydatny w przypadku pokazów.

Chociaż udostępnianie filmów wideo znajomym i współpracownikom jest zabawne, filmy wideo mogą również pomóc w nauczenie innych osób korzystania z aplikacji lub komunikowania problemów z aplikacjami i doświadczeniami.

> [!NOTE]
> Jeśli nie możesz uruchomić środowisko przechwytywania rzeczywistości mieszanej, a Urządzenie HoloLens jest urządzeniem służbowym, skontaktuj się z administratorem systemu. Dostęp do aparatu można ograniczyć za pomocą zasad firmowych.

## <a name="capture-a-mixed-reality-photo"></a>Przechwytywanie zdjęcia rzeczywistości mieszanej

Istnieje kilka sposobów, aby zrobić zdjęcie rzeczywistości mieszanej na HoloLens; Możesz użyć przycisków sprzętowych, głosu lub menu Start.

### <a name="hardware-buttons-to-take-photos"></a>Przyciski sprzętowe do robić zdjęcia

Aby zrobić szybkie zdjęcie bieżącego widoku, naciśnij jednocześnie przyciski regulacji głośności w górę i w dół.  Jest to trochę tak jak HoloLens zrzutu ekranu lub ekranu wydruku.

- [Lokalizacje przycisków na HoloLens 2](hololens2-hardware.md)
- [Lokalizacje przycisków na HoloLens (1. generacja)](hololens1-hardware.md#hololens-components)

> [!NOTE]
> **Przytrzymanie przycisków regulacji głośności** i regulacji głośności przez trzy sekundy spowoduje rozpoczęcie rejestrowania wideo zamiast zrobienia zdjęcia.  Aby zatrzymać nagrywanie, naciśnij jednocześnie przyciski **regulacji głośności** **i** regulacji głośności.

### <a name="voice-commands-to-take-photos"></a>Polecenia głosowe do robić zdjęcia

W HoloLens 2, wersja 2004 (i nowsze) powiedz: "Take a picture" (Zrób zdjęcie).

Na HoloLens (1. generacji) lub HoloLens 2, wersja 1903, powiedz: "Hej, Cortana, zrób zdjęcie".

### <a name="start-menu-to-take-photos"></a>menu Start robić zdjęcia

Użyj gestu Uruchom, aby przejść do **menu Start,** a następnie wybierz **ikonę Aparat.**

Wskaż kierunek głowy w kierunku tego, co chcesz przechwycić, a następnie naciśnij [w](hololens2-basic-usage.md#touch-holograms-near-you) powietrzu, aby zrobić zdjęcie. Możesz dalej naciskać w powietrzu i przechwytywać dodatkowe zdjęcia. Wszystkie przechwycone zdjęcia zostaną zapisane na urządzeniu.

Użyj ponownie gestu Start, aby zakończyć przechwytywanie zdjęć.  

## <a name="capture-a-mixed-reality-video"></a>Przechwytywanie wideo rzeczywistości mieszanej

Istnieje kilka sposobów na nagraniu wideo rzeczywistości mieszanej na HoloLens; Możesz użyć przycisków sprzętowych, głosu lub menu Start.

### <a name="hardware-buttons-to-record-videos"></a>Przyciski sprzętowe do nagrywania wideo

Najszybszym sposobem na nagrania wideo jest  jednoczesne  naciśnięcie i przytrzymanie przycisków regulacji głośności i regulacji głośności do momentu, gdy rozpocznie się odliczanie do trzech sekund. Aby zatrzymać nagrywanie, naciśnij oba przyciski jednocześnie.

> [!NOTE]
> Szybkie naciśnięcie **przycisków regulacji głośności w** górę i regulacji głośności w tym samym czasie spowoduje zrób zdjęcie zamiast nagrywania wideo. 

### <a name="voice-to-record-videos"></a>Głos do nagrywania wideo

W HoloLens 2, wersja 2004 (i nowsze) powiedz: "Rozpocznij nagrywanie". Aby zatrzymać nagrywanie, powiedz "Stop recording" (Zatrzymaj nagrywanie).

Na HoloLens (1. generacji) lub HoloLens 2, wersja 1903, powiedz: "Hej, Cortana, rozpocznij nagrywanie". Aby zatrzymać nagrywanie, powiedz "Hej, Cortana zatrzymaj nagrywanie".

### <a name="start-menu-to-record-videos"></a>menu Start do nagrywania filmów wideo

Użyj gestu Start, aby przejść do **menu Start,** a następnie wybierz **ikonę Wideo.** Wskaż kierunek przechwytywania, a następnie naciśnij w powietrzu, [aby](hololens2-basic-usage.md#touch-holograms-near-you) rozpocząć nagrywanie. Odejmuje się trzy sekundy i rozpocznie się nagrywanie.

Aby zatrzymać nagrywanie, użyj gestu Start i wybierz wyróżnione **ikonę Wideo.** Film wideo zostanie zapisany na urządzeniu.

> [!NOTE]
> **Dotyczy tylko HoloLens (1. generacji)**  
> Ekran [Aktualizacja systemu Windows 10 z października 2018](/windows/mixed-reality/release-notes-october-2018) sposób zachowania gestu Start i przycisku Windows na HoloLens (1. generacja). Przed aktualizacją gest Start lub przycisk Windows zatrzymały nagrywanie wideo. Jednak po aktualizacji przycisk Rozpocznij gest lub przycisk Windows otwiera menu **Start** (lub **menu** szybkich akcji, jeśli znajdujesz  się w aplikacji immersyjnej), z którego można wybrać wyróżnione ikonę wideo, aby zatrzymać nagrywanie.

## <a name="share-what-you-see-in-real-time"></a>Udostępnianie tego, co widzisz w czasie rzeczywistym

W czasie rzeczywistym możesz udostępniać HoloLens w czasie rzeczywistym znajomym i współpracownikom. Dostępnych jest kilka metod:

1. Nawiązywanie połączenia z Miracast z włączoną obsługą urządzenia lub adaptera w celu obejrzenia go na ekranie TV.
1. Używanie [Windows Portal urządzeń](/windows/mixed-reality/using-the-windows-device-portal) do obserwowania na komputerze
1. Używanie aplikacji [Microsoft HoloLens do obserwowania](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) na komputerze.
1. Wdrażanie aplikacji [Microsoft Dynamics 365 Remote Assist,](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) która umożliwia pracownikom pracującym przy pierwszej linii przesyłanie strumieniowe tego, co widzą, do zdalnego eksperta. Zdalny ekspert może następnie prowadzić pracowników na pierwszej linii słownie lub przez adnotacje w ich świecie.

> [!NOTE]
> Udostępnianie tego, co widzisz za Windows Portal urządzeń lub Microsoft HoloLens aplikacji towarzyszącej, wymaga, aby HoloLens był w [trybie dewelopera.](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)

### <a name="stream-video-with-miracast"></a>Przesyłanie strumieniowe wideo za pomocą Miracast

Użyj gestu Start, aby przejść do **menu Start,** a następnie wybierz **ikonę Połączenie** menu. Z wyświetlonego selektora wybierz Miracast lub kartę sieciową, z którą chcesz nawiązać połączenie.

Aby zatrzymać udostępnianie, użyj gestu Start i wybierz wyróżniony **Połączenie** ikony. Ponieważ przesyłano strumieniowo, żadne dane nie zostaną zapisane na urządzeniu.

> [!NOTE]
> Miracast włączono obsługę HoloLens (1. generacji) począwszy [od](/windows/mixed-reality/release-notes-october-2018)Aktualizacja systemu Windows 10 z października 2018 .

### <a name="real-time-video-with-windows-device-portal"></a>Wideo w czasie rzeczywistym z Windows Portal urządzeń

Ponieważ udostępnianie za pośrednictwem Windows Portal urządzeń wymaga, aby tryb dewelopera był włączony na platformie HoloLens, postępuj zgodnie z instrukcjami w naszej dokumentacji dla deweloperów, aby skonfigurować tryb dewelopera i nawigować po [Windows Portal urządzeń](/windows/mixed-reality/using-the-windows-device-portal).

### <a name="microsoft-hololens-companion-app"></a>Microsoft HoloLens aplikacji towarzyszącej

Ponieważ udostępnianie za pośrednictwem Microsoft HoloLens aplikacji towarzyszącej wymaga, aby tryb dewelopera był włączony w HoloLens, postępuj zgodnie z instrukcjami w naszej dokumentacji dla deweloperów, aby [skonfigurować tryb dewelopera.](/windows/mixed-reality/using-the-windows-device-portal) Następnie pobierz aplikację [Microsoft HoloLens i](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) postępuj zgodnie z instrukcjami w aplikacji, aby nawiązać połączenie z HoloLens.

Po skonfigurowaniu aplikacji przy użyciu HoloLens wybierz opcję **Transmisja strumieniowa** na żywo z menu głównego aplikacji.

## <a name="view-your-mixed-reality-photos-and-videos"></a>Wyświetlanie zdjęć i wideo rzeczywistości mieszanej

Zdjęcia i filmy wideo rzeczywistości mieszanej są zapisywane w "aparacie roll" urządzenia. Zawartość tego folderu na ekranie możesz przeglądać na ekranie HoloLens za pomocą aplikacji Eksplorator plików (przejdź do folderu Obrazy > **roll aparatu).**

Możesz również wyświetlać zdjęcia i filmy wideo rzeczywistości mieszanej w aplikacji Zdjęcia, która jest wstępnie zainstalowana na HoloLens. Aby przypiąć zdjęcie na świecie, wybierz je w aplikacji Zdjęcia, a następnie wybierz pozycję **Umieść w świecie mieszanym.** Po umieszczeniu zdjęcia można je przenosić po całym świecie.

Aby wyświetlać [i/lub](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) zapisywać zdjęcia i wideo rzeczywistości mieszanej na komputerze podłączonym do usługi HoloLens, możesz użyć usługi Windows Portal urządzeń lub usługi Eksplorator plików za pośrednictwem usługi [MTP.](/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a>Użyj Eksplorator plików, aby pobrać swoje obrazy, wideo i pliki

Podobnie jak w przypadku innych urządzeń przenośnych, podłącz urządzenie HoloLens do komputera, aby Eksplorator plików uzyskać dostęp do bibliotek HoloLens (zdjęć, wideo, dokumentów) w celu łatwego przesyłania. Ta metoda jest łatwa w użyciu i nie wymaga użycia portalu urządzeń ani sieci Wi-Fi.

1. Odblokuj urządzenie.
1. Połączenie urządzenie do komputera za pośrednictwem portu USB.
1. Eksplorator plików powinien zostać otwarty na komputerze.
1. Przejdź do: ten komputer \\ *twojanazwa_pamięci_wewnętrznej\Storage\Pictures\Camera* Roll
1. Skopiuj na komputer wszystkie potrzebne pliki.

Porady:
- Jeśli nie widzisz żadnych plików, upewnij się, że logujesz się do HoloLens, aby umożliwić dostęp do danych.
- Możesz pobrać inne pliki w innych folderach, takie jak [pliki diagnostyczne,](hololens-diagnostic-logs.md#offline-diagnostics) z folderu Dokumenty.
- Z Eksplorator plików na komputerze możesz wybrać pozycję Właściwości urządzenia, aby wyświetlić Windows wersji systemu operacyjnego Holographic (wersja oprogramowania układowego), numer seryjny urządzenia i procent naładowania baterii.
- Jeśli Twoja organizacja użyła rozwiązania MDM do wyłączenia [połączenia Connectivity/AllowUSBConnection,](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) nie będzie można nawiązać połączenia z urządzeniem.

## <a name="share-your-mixed-reality-photos-and-videos"></a>Udostępnianie zdjęć i filmów wideo rzeczywistości mieszanej

Przed Windows Holographic w wersji [21H1](hololens-release-notes.md#windows-holographic-version-21h1)po przechwyceniu zdjęcia lub wideo rzeczywistości mieszanej zostanie wyświetlony podgląd. Wybierz **ikonę Udostępnij** nad podglądem, aby wyświetlić asystenta udostępniania. W tym miejscu możesz wybrać punkt końcowy, do którego chcesz udostępnić to zdjęcie lub wideo.

W Windows Holographic w wersji 21H1 po przechwyceniu zdjęcia lub wideo rzeczywistości mieszanej zostanie wyświetlony podgląd. Wybierz **ikonę Udostępnij** nad podglądem, aby wyświetlić asystenta udostępniania. W tym miejscu możesz wybrać punkt końcowy (Mail, OneDrive itp.), do którego chcesz udostępnić to zdjęcie lub wideo. Możesz również włączyć udostępnianie HoloLens pobliskim urządzeniem, przechodząc do folderu **Ustawienia -> System -> Shared Experiences**. Aby uzyskać więcej informacji, przeczytaj [temat Udostępnianie rzeczy pobliskim urządzeniem w Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).

> [!TIP] 
> Możesz również udostępniać zdjęcia i filmy wideo rzeczywistości mieszanej z OneDrive, automatycznie przesyłając zdjęcia i filmy wideo rzeczywistości mieszanej. Otwórz aplikację OneDrive na stronie HoloLens i zaloguj się przy użyciu osobistego **[konta konto Microsoft](https://account.microsoft.com)**, jeśli jeszcze tego nie zrobić. Wybierz **ikonę Ustawienia** i wybierz pozycję **Przekaż aparat.** Włącz przekazywanie z aparatu. Zdjęcia i filmy wideo rzeczywistości mieszanej będą teraz przekazywane do OneDrive przy każdym uruchomieniu aplikacji na HoloLens.

> [!NOTE]
> Przekazywanie z aparatu można włączyć OneDrive tylko wtedy, gdy zalogowano się do OneDrive przy użyciu konta konto Microsoft. W przypadku skonfigurowania HoloLens przy użyciu konta służbowego możesz dodać osobisty konto Microsoft aplikacji OneDrive, aby włączyć tę funkcję.

## <a name="limitations-of-mixed-reality-capture"></a>Ograniczenia przechwytywania rzeczywistości mieszanej

- Podczas przechwytywania rzeczywistości mieszanej szybkość klatek HoloLens do 30 Hz.
- Rozdzielczość zdjęć i wideo może ulec skróceniu, jeśli kamera do zdjęć/wideo jest już zajęta przez inną aplikację, podczas transmisji strumieniowej na żywo lub gdy zasoby systemowe są niskie.

### <a name="maximum-recording-length"></a>Maksymalna długość rejestrowania

Na HoloLens urządzeniach przed Windows Holographic w wersji 20H2 filmy wideo zarejestrowane na urządzeniu były ograniczone do maksymalnej długości pięciu minut.

Dzięki opiniom klientów zwiększyliśmy długość rejestrowania przechwytywania [rzeczywistości mieszanej.](holographic-photos-and-videos.md) Przechwytywanie rzeczywistości mieszanej domyślnie nie będzie już ograniczone do 5 minut, ale zamiast tego obliczy maksymalną długość rejestrowania na podstawie dostępnego miejsca na dysku. Urządzenie oszacowa maksymalny czas trwania rejestrowania wideo na podstawie dostępnego miejsca na dysku do 80% całkowitego miejsca na dysku.

> [!NOTE]
> W HoloLens będzie używać domyślnej długości rejestrowania wideo (5 minut), jeśli wystąpi jedna z następujących sytuacji:
> - Szacowany maksymalny czas rejestrowania jest mniejszy niż domyślne 5 minut.
> - Dostępne miejsce na dysku jest mniejsza niż 20% całkowitego miejsca na dysku.

## <a name="default-file-format-and-resolution"></a>Domyślny format i rozdzielczość pliku

### <a name="default-photo-format-and-resolution"></a>Domyślny format i rozdzielczość zdjęcia

|  Urządzenie  |  Format  |  Wewnętrzny  |  Rozwiązanie  |
|----------|----------|----------|----------|
| HoloLens 2 | [Jpeg](https://en.wikipedia.org/wiki/JPEG) | jpg | 3904 x 2196 pikseli |
| HoloLens (1. generacja) | [Jpeg](https://en.wikipedia.org/wiki/JPEG) | jpg | 1408 x 792 pikseli |

### <a name="recorded-video-format-and-resolution"></a>Format i rozdzielczość zarejestrowanego wideo

| Urządzenie | Format | Wewnętrzny | Rozwiązanie | Szybkość | Dźwięk |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | mp4 | 1920 x 1080 pikseli | 30 kl./s | 48 kHz Stereo |
| HoloLens (1. generacja) |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | mp4 | 1216 x 684 pikseli | 24 kl./s | 48 kHz Stereo |
