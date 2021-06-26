---
title: Ponowne uruchamianie, resetowanie lub odzyskiwanie urządzenia HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: Jak używać narzędzia do odzyskiwania urządzeń z systemem Windows do flashowania obrazu na urządzeniu HoloLens 1. generacji.
keywords: how-to, reboot, reset, recover, hard reset, soft reset, power cycle, HoloLens, shut down, wdrt, windows device recovery tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 5963be84a5fbb186c77965d9bbf112713fea8242
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923520"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>Ponowne uruchamianie, resetowanie lub odzyskiwanie urządzenia HoloLens (1. generacja)

Jeśli występują problemy z urządzeniem HoloLens, możesz spróbować ponownie uruchomić lub zresetować urządzenie, a nawet zmienić jego ukośnik przy użyciu funkcji odzyskiwania urządzenia. Ten artykuł przeprowadzi Cię przez zalecane kroki odzyskiwania w kolejności.

Jeśli chcesz odzyskać urządzenie HoloLens 2, zobacz [Recovering a HoloLens 2](hololens-recovery.md)(Odzyskiwanie urządzenia HoloLens 2), ponieważ ten proces się różni.

> [!NOTE]
> Ten artykuł koncentruje się na urządzeniu HoloLens i oprogramowaniu. Jeśli Twoje hologramy nie wyglądają dobrze, zobacz Zagadnienia dotyczące środowiska **[HoloLens,](hololens-environment-considerations.md)** aby uzyskać informacje o czynnikach, które poprawiają jakość hologramów.

## <a name="restart"></a>Uruchom ponownie

### <a name="do-a-safe-restart-by-using-cortana"></a>Wykonaj bezpieczne ponowne uruchomienie przy użyciu Cortany

Najbezpieczniejszym sposobem ponownego uruchomienia urządzenia HoloLens jest użycie Cortany, która zazwyczaj jest pierwszą rzeczą, którą należy wypróbować, gdy wystąpi problem z urządzeniem HoloLens.

> [!NOTE] 
> Cortana nie jest dostępna na wszystkich urządzeniach.
> - Cortana jest dostępna na wszystkich urządzeniach HoloLens (1. generacji). 
> - Cortana jest dostępna na urządzeniach HoloLens 2 w kompilacjach przed aktualizacją systemu Windows Holograpic w wersji 2004.

1. Włącz urządzenie HoloLens.
1. Upewnij się, że użytkownik jest zalogowany i urządzenie nie czeka na odblokowanie hasła.
2. Powiedz "Hey Cortana, reboot" (Hej, Cortana, uruchom ponownie) lub "Hey Cortana, restart" (Hej, Cortana, uruchom ponownie).
3. Cortana odpowie i wyświetli monit o potwierdzenie. Zaczekaj na odtwarzanie dźwięku po pytaniu, a następnie powiedz "Yes" (Tak). Urządzenie zostanie uruchomione ponownie.

### <a name="use-the-power-button-to-do-a-safe-restart"></a>Używanie przycisku zasilania w celu bezpiecznego ponownego uruchomienia

Jeśli nadal nie możesz ponownie uruchomić urządzenia, spróbuj uruchomić je ponownie przy użyciu **przycisku** zasilania:

1. Naciśnij i przytrzymaj **przycisk zasilania** przez 5 sekund. Po upływie 1 sekundy wszystkie pięć diod LED będzie się obracać, a następnie wolno wyłączać jedną po drugiej od prawej do lewej. Po 5 sekundach wszystkie diody LED będą wyłączone, co oznacza pomyślne zamknięcie.
      
   > [!IMPORTANT]
   > Zatrzymaj naciskanie przycisku natychmiast po wyłączeniu wszystkich diod LED.
1. Poczekaj 1 minutę na zakończenie zamykania. Zamknięcie może być nadal w toku nawet po wyłączeniu ekranów.
2. Włącz ponownie urządzenie, naciskając i przytrzymując **przycisk zasilania** przez 1 sekundę.

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>Wykonaj bezpieczne ponowne uruchomienie przy użyciu Portal urządzeń z systemem Windows

> [!NOTE]
> W tym procesie urządzenie HoloLens należy skonfigurować jako urządzenie dewelopera. Dowiedz się więcej na [Portal urządzeń z systemem Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).

Jeśli poprzednia procedura nie zadziałała, spróbuj ponownie uruchomić urządzenie przy [użyciu](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)Portal urządzeń z systemem Windows . W prawym górnym rogu znajdź opcję ponownego uruchomienia lub zamknięcia urządzenia.

### <a name="do-an-unsafe-forced-restart"></a>Wykonaj niebezpieczne wymuszone ponowne uruchomienie

Jeśli poprzednie metody nie uruchomiły ponownie urządzenia HoloLens, wymusz ponowne uruchomienie. Ta metoda jest odpowiednikiem usuwania i ponownego instalowania baterii. Jest to niebezpieczne, ponieważ może pozostawić urządzenie w stanie uszkodzenia. W takim przypadku musisz flashować urządzenie HoloLens.  

> [!WARNING]
> Jest to potencjalnie szkodliwy sposób i należy go używać tylko wtedy, gdy wcześniej przywołyne metody nie zadziałały.

1. Naciśnij i przytrzymaj **przycisk zasilania** przez co najmniej 10 sekund.
   - Można przytrzymać przycisk dłużej niż przez 10 sekund.
   - Można bezpiecznie ignorować wszelkie działania diody LED.
1. Zwolnij przycisk i poczekaj 2–3 sekundy.
1. Naciśnij i przytrzymaj **przycisk zasilania** przez 1 sekundę.
1. Jeśli nadal występują problemy,  naciskaj przycisk zasilania przez 4 sekundy, aż wszystkie wskaźniki baterii znikną i ekran przestanie wyświetlać hologramy. Poczekaj 1 minutę, a następnie ponownie naciśnij **przycisk** zasilania, aby włączyć urządzenie.

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>Wstecz do poprzedniej wersji — HoloLens (1. generacja)

W niektórych przypadkach może być konieczne powrót do poprzedniej wersji oprogramowania HoloLens. Możesz to zrobić przy użyciu narzędzia do odzyskiwania urządzeń z systemem Windows, aby zresetować urządzenie HoloLens do starszej wersji.

> [!NOTE]
> Powrót do wcześniejszej wersji powoduje usunięcie osobistych plików i ustawień.

Aby wrócić do poprzedniej wersji urządzenia HoloLens 1, wykonaj następujące kroki:

1. Upewnij się, że nie masz żadnych telefonów ani urządzeń z systemem Windows podłączonych do komputera.
1. Na komputerze pobierz narzędzie [Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379)
1. Pobierz pakiet [odzyskiwania rocznicowej aktualizacji urządzenia HoloLens.](https://aka.ms/hololensrecovery)
1. Po zakończeniu pobierania otwórz **Eksploratora**  >  **plików — pliki do pobrania.** Kliknij prawym przyciskiem myszy właśnie pobrany folder ze zmapowanych danych, a następnie wybierz polecenie **Wyodrębnij wszystkie** wyodrębnij,  >   aby go rozpakować.
1. Podłącz urządzenie HoloLens do komputera przy użyciu kabla micro-USB, który jest do niego podłączony. (Nawet jeśli używasz innych kabli do podłączania urządzenia HoloLens, ten z nich działa najlepiej).
1. Program WDRT automatycznie wykryje urządzenie HoloLens. Wybierz **kafelek Microsoft HoloLens** aplikacji.
1. Na następnym ekranie wybierz opcję **Ręczne wybieranie** pakietu i wybierz plik instalacyjny zawarty w folderze rozpakowanym w kroku 4. (Poszukaj pliku z rozszerzeniem ffu).
1. Wybierz **pozycję Zainstaluj oprogramowanie** i postępuj zgodnie z instrukcjami.

> [!NOTE]
> Jeśli program WDRT nie wykryje urządzenia HoloLens, spróbuj ponownie uruchomić komputer. Jeśli to nie zadziała, wybierz pozycję Moje urządzenie nie zostało **wykryte,** wybierz pozycję Microsoft HoloLens **,** a następnie postępuj zgodnie z instrukcjami.

## <a name="reset-to-factory-settings"></a>Resetowanie do ustawień fabrycznych

> [!NOTE]
> Do zresetowania baterii jest potrzebne co najmniej 40-procentowe obciążenie.

Jeśli problem z urządzeniem HoloLens nadal występuje, spróbuj zresetować go do stanu fabrycznego. Ten krok zachowuje zainstalowaną wersję oprogramowania Windows Holographic i zwraca wszystkie inne dane do ustawień fabrycznych.

>[!WARNING]
> Zresetowanie urządzenia spowoduje usunięcie wszystkich danych osobowych, aplikacji i ustawień, w tym informacji o resetowaniu modułu TPM. Zresetowanie spowoduje zainstalowanie tylko najnowszej zainstalowanej wersji systemu Windows Holographic. Musisz ponownie wykonać wszystkie kroki inicjowania (skalibrować, połączyć się z siecią Wi-Fi, utworzyć konto użytkownika, pobrać aplikacje itd.).

1. Otwórz aplikację Ustawienia, a następnie wybierz pozycję **Zaktualizuj**  >  **odzyskiwanie.**
1. Wybierz opcję **Resetuj urządzenie** i przeczytaj komunikat potwierdzający.
1. Potwierdź zresetowanie. Urządzenie zostanie uruchomione ponownie i wyświetli zestaw wirowania koła zębatego oraz pasek postępu.
1. Poczekaj około 30 minut na ukończenie tego procesu. Gdy wszystko będzie gotowe, urządzenie zostanie uruchomione ponownie w gotowej do pracy.

## <a name="reinstall-the-operating-system"></a>Ponowne instalowanie systemu operacyjnego

Jeśli po ponownym uruchomieniu i zresetowaniu urządzenia nadal występuje problem, możesz ponownie zainstalować system operacyjny i oprogramowanie układowe HoloLens za pomocą narzędzia do odzyskiwania na komputerze.  

Dane, których urządzenie HoloLens potrzebuje do zresetowania, są spakowane w pełnej aktualizacji flash (FFU), która jest podobna do pliku ISO, WIM lub VHD. [Dowiedz się więcej o formatach plików obrazów FFU.](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

Nowy system operacyjny można zainstalować na urządzeniu HoloLens (1. generacji) przy użyciu narzędzia do odzyskiwania urządzeń z systemem Windows. Przed użyciem tego narzędzia sprawdź, czy ponowne uruchomienie lub zresetowanie urządzenia HoloLens rozwiąże problem.

Proces odzyskiwania może trochę potrwać. Gdy wszystko będzie gotowe, zostanie zainstalowana najnowsza wersja oprogramowania Windows Holographic.

Aby korzystać z tego narzędzia, potrzebny jest komputer z systemem Windows 10 lub nowszym z co najmniej 4 GB wolnego miejsca. Nie można uruchomić tego narzędzia na maszynie wirtualnej.

### <a name="recover-your-hololens"></a>Odzyskiwanie urządzenia HoloLens

1. Pobierz i zainstaluj narzędzie [do odzyskiwania urządzeń z systemem Windows](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) na komputerze.
1. Podłącz urządzenie HoloLens (1. generacji) do komputera za pomocą kabla Micro USB, który jest podłączony do urządzenia HoloLens.
1. Otwórz narzędzie do odzyskiwania urządzeń z systemem Windows i postępuj zgodnie z instrukcjami.

Jeśli urządzenie HoloLens (1. generacja) nie zostanie wykryte automatycznie, wybierz pozycję **Moje urządzenie nie zostało wykryte.** Następnie postępuj zgodnie z instrukcjami, aby przełożyć urządzenie w tryb odzyskiwania.

### <a name="manual-flashing-mode"></a>Tryb ręcznego flashowania

Jeśli urządzenie nie zostanie wykryte, wykonaj następujące kroki, aby przesłonić je w tryb flashowania:

1. Odłącz urządzenie od dowolnego źródła zasilania.
1. Jeśli urządzenie jest wł.  i przytrzymaj przycisk zasilania, aż zostanie całkowicie wyłączone.
2. Przytrzymaj przycisk **regulacji głośności** i naciśnij krótko **przycisk** zasilania. Urządzenie powinno uruchamiać się i wyświetlać tylko środkową diodę LED.
3. Podłącz urządzenie do komputera.
4. Otwórz narzędzie do odzyskiwania urządzeń z systemem Windows.
5. Wybierz **pozycję Moje urządzenie nie zostało wykryte,** a następnie pozycję **HoloLens.** 
6. Postępuj zgodnie z instrukcjami, aby odzyskać urządzenie.
