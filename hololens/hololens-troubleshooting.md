---
title: Rozwiązywanie problemów z urządzeniem HoloLens
description: Bądź na bieżąco z najbardziej powszechnymi rozwiązaniami problemów z urządzeniami HoloLens i technikami rozwiązywania problemów.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problemy, usterka, rozwiązywanie problemów, poprawka, pomoc, obsługa techniczna, HoloLens, emulator
ms.openlocfilehash: b69dddf04ac31b69f0b2f8759d095806189f33ab
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924625"
---
# <a name="device-troubleshooting"></a>Rozwiązywanie problemów z urządzeniami

W tym artykule opisano sposób rozwiązywania kilku typowych problemów z urządzeniem HoloLens.

>[!IMPORTANT]
> Przed rozpoczęciem procedury rozwiązywania problemów upewnij się, że urządzenie jest obciążane od **20 do 40%** pojemności baterii, jeśli jest to możliwe. Wskaźniki [naładowania baterii znajdujące](hololens2-setup.md#lights-that-indicate-the-battery-level) się pod przyciskiem zasilania to szybki sposób na sprawdzenie pojemności baterii bez logowania się do urządzenia.

<a id="list"></a>

**Znane problemy**
- [Wideo remote assist zawiesza się po 20 minutach](#remote-assist-video-freezes-after-20-minutes)
- [Automatyczne logowanie wymaga zalogowania](#auto-login-asks-for-log-in)
- [Microsoft Edge nie można uruchomić](#microsoft-edge-fails-to-launch)
- [Klawiatura nie przełącza się na znaki specjalne](#keyboard-doesnt-switch-to-special-characters)
- [Pobieranie zablokowanych plików nie pokazuje błędu](#downloading-locked-files-doesnt-error)
- [Portal urządzeń przekazywania/pobierania plików](#device-portal-file-uploaddownload-times-out)
- [Niebieski ekran po wywrzeniu z wersji zapoznawczej niejawnego programu testów na urządzeniu z flashem kompilacji niejawnego testera](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [W usłudze OneDrive obrazy nie są automatycznie przekazywać](#onedrive-doesnt-automatically-upload-pictures)

**Ogólne**
- [Urządzenie HoloLens nie odpowiada lub nie uruchamia się](#hololens-is-unresponsive-or-wont-start)
- [Błąd "Mała ilość miejsca na dysku"](#low-disk-space-error)
- [Niepowodzenie awarii](#calibration-fails)
- [Nie można się zalogować, ponieważ urządzenie HoloLens zostało wcześniej ustawione dla kogoś innego](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [Unity nie działa](#unity-isnt-working)
- [Portal urządzeń z systemem Windows nie działa prawidłowo](#windows-device-portal-isnt-working-correctly)
- [Emulator urządzenia HoloLens nie działa](#the-hololens-emulator-isnt-working)

**Dane wejściowe**
- [Polecenia głosowe nie działają](#voice-commands-arent-working)
- [Ręczne wprowadzanie danych nie działa](#hand-input-isnt-working)

**Połączenia**
- [Nie można nawiązać połączenia z siecią Wi-Fi](#cant-connect-to-wi-fi)

**Urządzenia zewnętrzne** 
- [Urządzenia Bluetooth nie są parowane](#bluetooth-devices-arent-pairing)
- [Mikrofon USB-C nie działa](#usb-c-microphone-isnt-working)
- [Urządzenia wymienione jako dostępne w ustawieniach nie działają](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Wideo remote assist zawiesza się po 20 minutach

> [!NOTE]
> Ze względu na ważność tego znanego problemu obecnie wstrzymano dostępność systemu Windows Holographic w wersji 21H1. Jeśli chcesz nadal aktualizować urządzenia do wersji 21H1, zapoznaj się z instrukcjami w naszych informacjach o wersji w [górnej części strony.](hololens-release-notes.md)

W najnowszej wersji systemu Windows Holographic w wersji [21H1](hololens-release-notes.md#windows-holographic-version-21h1)niektórzy użytkownicy usługi Remote Assist doświadczyli blokowania wideo podczas wywołań przez 20 minut. Jest to znany **problem.**

### <a name="workarounds"></a>Obejścia

#### <a name="restart-in-between-calls"></a>Uruchom ponownie między wywołaniami

Jeśli połączenia są trwać ponad 20 minut i występuje ten problem, spróbuj ponownie uruchomić urządzenie. Ponowne uruchomienie urządzenia między wywołaniami usługi Remote Assist spowoduje odświeżenie urządzenia i jego ponowne uruchomienie w dobrym stanie.

Aby szybko ponownie uruchomić urządzenie na platformie Windows Holographic, w wersji [21H1](hololens-release-notes.md#windows-holographic-version-21h1) otwórz menu Start i wybierz ikonę użytkownika, a następnie wybierz pozycję **Uruchom ponownie.**

#### <a name="revert-to-an-older-build"></a>Przywracanie starszej kompilacji

Niektórzy klienci odkryli, że po przywróceniu starszej wersji systemu operacyjnego ten problem już nie występuje. Jeśli napotkano ten problem na urządzeniach, spróbuj wykonać następujące czynności:


Obejścia:

- Jeśli jest to możliwe dla Twojej firmy, automatyczne przekazywanie z aparatu jest obsługiwane na kontach Microsoft klientów. Możesz zalogować się do konta konto Microsoft konta służbowego (aplikacja OneDrive obsługuje logowanie podwójne). Z poziomu konto Microsoft w usłudze OneDrive możesz włączyć automatyczne przekazywanie z aparatu w tle.

- Jeśli nie możesz bezpiecznie użyć konta konto Microsoft do automatycznego przekazywania zdjęć, możesz ręcznie przekazać zdjęcia na konto służbowe z aplikacji OneDrive. W tym celu upewnij się, że zalogowano się do konta służbowego w aplikacji OneDrive. Wybierz przycisk **+** i wybierz pozycję **Przekaż.** Znajdź zdjęcia lub filmy wideo, które chcesz przekazać, przechodząc do > **Camera Roll**. Wybierz zdjęcia lub wideo, które chcesz przekazać, a następnie wybierz **przycisk** Otwórz.


1. [Pobierz kompilację dla systemu Windows Holographic w wersji 20H2 — aktualizacja z maja 2021 r.](https://aka.ms/hololens2download/10.0.19041.1146)
1. Postępuj zgodnie [z instrukcjami, aby powrócić do poprzedniej wersji systemu operacyjnego](hololens-update-hololens.md#go-back-to-a-previous-version)
1. [Wstrzymaj aktualizacje systemu operacyjnego na urządzeniu ręcznie](hololens-updates.md#pause-updates-via-device) lub dla wielu urządzeń użyj odroczenia za [pośrednictwem rozwiązania MDM.](hololens-updates.md#configure-an-update-deferral-policy)

[Powrót do listy](#list)

## <a name="auto-login-asks-for-log-in"></a>Automatyczne logowanie wymaga zalogowania

Urządzenie HoloLens 2 można skonfigurować do automatycznego logowania się za pośrednictwem opcji logowania konta ustawień > i w obszarze Wymagane ustawienie wartości  ->    ->   **Nigdy.**  Niektórzy użytkownicy mogą wymagać zalogowania się na urządzeniu ponownie podczas aktualizowania urządzenia przy użyciu znacznie dużej aktualizacji, takiej jak aktualizacja funkcji. Jest to znany **problem.**

Przykład sytuacji, w których może się to zdarzyć:

- Aktualizowanie urządzenia z systemu Windows Holographic w wersji 2004 (kompilacja 19041.xxxx) do systemu Windows Holographic w wersji 21H1 (kompilacja 20346.xxxx)
- Aktualizowanie urządzenia w celu podjęcia dużej aktualizacji w tej samej kompilacji, np. Windows Holographic, wersja 2004 do systemu Windows Holographic, wersja 20H2
- Aktualizowanie urządzenia z obrazu fabrycznego do najnowszego obrazu

Nie powinno to mieć miejsca w trakcie:

- Urządzenia korzystające z comiesięcznej aktualizacji obsługi

Omiń metody:

- Metody logowania, takie jak numer PIN, hasło, irysy, uwierzytelnianie internetowe lub klucze FIDO2.
- Jeśli nie można zapamiętać numeru PIN urządzenia i inne metody uwierzytelniania są niedostępne, użytkownik może użyć [ręcznego trybu reflashingu.](hololens-recovery.md#manual-procedure)

[Powrót do listy](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge nie można uruchomić

> [!NOTE]
> Ten problem został pierwotnie utworzony z myślą o Microsoft Edge wysyłkowej. Ten problem można rozwiązać w nowej [Microsoft Edge](hololens-new-edge.md). Jeśli tak nie jest, prosimy o opinię.

Kilku klientów zgłosiło problem, który Microsoft Edge nie można uruchomić. W przypadku tych klientów problem będzie nadal występował po ponownym uruchomieniu i nie zostanie rozwiązany za pomocą aktualizacji systemu Windows ani aplikacji. Jeśli ten problem występuje i wiesz, że system [Windows](hololens-updates.md#manually-check-for-updates)jest aktualny, prosimy o zgłaszanie usterki z aplikacji [Centrum opinii](hololens-feedback.md) z następującą kategorią i podkategorią: Instalowanie i aktualizowanie usługi > Pobieranie, instalowanie i konfigurowanie Windows Update.

Nie ma znanych obejść, ponieważ do tej pory nie można było głównej przyczyny problemu. Zgłoszenie usterki za pośrednictwem Centrum opinii pomoże w naszym badaniu! Jest to znany **problem.**

[Powrót do listy](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>Klawiatura nie przełącza się na znaki specjalne

Podczas OOBE występuje problem, który występuje, gdy użytkownik wybrał konto służbowe i wprowadza hasło, próbując przełączyć się na znaki specjalne na klawiaturze, naciskając przycisk &123, nie zmienia się na znaki specjalne. Jest to znany **problem.**

Omiń:
-   Zamknij klawiaturę i otwórz ją ponownie, naciskając pole tekstowe.
-   Niepoprawnie wprowadź hasło. Gdy klawiatura zostanie ponownie wyzjęte przy następnym czasie, będzie działać zgodnie z oczekiwaniami.
- Uwierzytelnianie internetowe, zamknij klawiaturę i wybierz **pozycję Zaloguj się z innego urządzenia.**
-   Jeśli wprowadzasz tylko liczby, użytkownik może nacisnąć i przytrzymać niektóre klawisze, aby otworzyć rozwinięte menu.
-   Za pomocą klawiatury USB.

Nie ma to wpływu na:
- Użytkownicy, którzy wybiorą opcję korzystania z konta osobistego.

[Powrót do listy](#list)


## <a name="downloading-locked-files-doesnt-error"></a>Pobieranie zablokowanych plików nie kończy się błędem
> ! UWAGA Jest to znany **problem, który został** rozwiązany w niejawny tester systemu Windows kompilacji w wersji 20348.1403.


W poprzednich kompilacjach systemu Windows Holographic próba pobrania zablokowanego pliku byłaby stroną błędu HTTP. W systemie Windows Holographic aktualizacja w wersji 21H1 podczas próby pobrania zablokowanego pliku nie powoduje żadnych widocznych sytuacji — plik nie zostanie pobrana i nie wystąpi błąd. 

[Powrót do listy](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Portal urządzeń przekazywania/pobierania plików
> ! UWAGA Jest to znany **problem, który** został rozwiązany w kompilacji niejawny tester systemu Windows wersji 20348.1403. Jeśli wcześniej wyłączono połączenie SSL w ramach obejścia, zdecydowanie zalecamy jego ponowne włączenie.


Niektórzy klienci odkryli, że podczas próby przekazania lub pobrania plików operacja może się zawieszać, a następnie kończyć się lub nigdy nie kończyć. Jest to oddzielone[](#downloading-locked-files-doesnt-error) od znanego problemu "plik zablokowany" — dotyczy to systemu Windows Holographic w wersjach 2004, 20H2 i 21H1 w kompilacjach na rynku. Przyczyną problemu była usterka w obsłudze niektórych żądań Portal urządzeń przez usługę i jest ona najsuchomiej trafiona w przypadku używania protokołu https, co jest ustawieniem domyślnym. 

### <a name="workaround"></a>Obejście

To obejście, które ma zastosowanie w równym stopniu Wi-Fi i UsbNcm, polega na wyłączeniu opcji "wymagane" w obszarze "Połączenie SSL". W tym celu przejdź do Portal urządzeń **System** i wybierz stronę **Preferencje.** W sekcji **Zabezpieczenia urządzenia** znajdź opcję **Połączenie SSL** i usuń zaznaczenie pola wyboru, aby wyłączyć **opcję Wymagane.**

Następnie użytkownik powinien przejść do strony http://, a nie https:// (adres IP), a funkcje, takie jak przekazywanie i pobieranie plików, będą działać.

[Powrót do listy](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Niebieski ekran po wywrzeniu z niejawnego programu testów w wersji zapoznawczej na urządzeniu flashowym za pomocą kompilacji niejawnego programu testów

Jest to problem, który ma wpływ na użytkowników, którzy byli w kompilacji niejawnego testera w wersji zapoznawczej, przekrzywilili swoje urządzenia HoloLens 2 przy użyciu nowej kompilacji insider preview, a następnie nie są zarejestrowani w programie niejawnego programu testów. Jest to znany **problem.**

Nie ma to wpływu na:
- Użytkownicy, którzy nie są zarejestrowani w niejawny tester systemu Windows 
- Wewnętrznych:
    - Jeśli urządzenie zostało zarejestrowane od kompilacji niejawnych testerów w wersji 18362.x
    - Jeśli flashował kompilację 19041.x podpisaną przez niejawnego testera I został zarejestrowany w programie niejawnego programu testów

Pomiń: 
- Unikaj problemu 
    - Flashuj kompilację bez niejawnych testerów. Jedna z regularnych comiesięcznych aktualizacji.
    - Bądź na testach w wersji zapoznawczej
- Reflash urządzenia

    1. Ręcznie przełączyć [urządzenie HoloLens 2](hololens-recovery.md) w tryb flashowania, w pełni przez całkowite zasilanie bez połączenia. Następnie przytrzymaniu przycisku Volume up naciśnij przycisk Zasilania.
    
    1. Połącz się z komputerem i otwórz program Advanced Recovery Companion.
    
    1. Flashuj urządzenie HoloLens 2 do kompilacji domyślnej.

[Powrót do listy](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>W usłudze OneDrive obrazy nie są automatycznie przekazywać

Aplikacja OneDrive dla urządzenia HoloLens nie obsługuje automatycznego przekazywania z aparatu dla kont służbowych. Jest to znany **problem.**

Obejścia:

- Jeśli jest to możliwe dla Twojej firmy, automatyczne przekazywanie aparatów jest obsługiwane na kontach Microsoft klientów. Możesz zalogować się do konta konto Microsoft konta służbowego (aplikacja OneDrive obsługuje logowanie podwójne). Z poziomu konto Microsoft w usłudze OneDrive możesz włączyć automatyczne przekazywanie z aparatu w tle.

- Jeśli nie możesz bezpiecznie użyć konta konto Microsoft do automatycznego przekazywania zdjęć, możesz ręcznie przekazać zdjęcia do konta służbowego z aplikacji OneDrive. W tym celu upewnij się, że zalogowano się do konta służbowego w aplikacji OneDrive. Wybierz przycisk **+** i wybierz pozycję **Przekaż**. Znajdź zdjęcia lub wideo, które chcesz przekazać, przechodząc do tematu **Pictures > Camera Roll (Obrazy** i > camera Roll). Wybierz zdjęcia lub wideo, które chcesz przekazać, a następnie wybierz **przycisk** Otwórz.

[Powrót do listy](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>Urządzenie HoloLens nie odpowiada lub nie uruchamia się

Jeśli nie można uruchomić urządzenia HoloLens:

- Jeśli diody LED obok przycisku zasilania nie zaczną się osłaniać lub tylko jedna dioda LED miga, może być konieczne ładowanie urządzenia [HoloLens.](hololens2-charging.md#charging-the-device)
- Jeśli diody LED są wyświetlane po naciśnięciu przycisku zasilania, ale na ekranie nie widać niczego, wykonaj twarde [resetowanie urządzenia.](hololens-recovery.md#hard-reset-procedure)

Jeśli urządzenie HoloLens jest zamrożone lub nie odpowiada:

- Wyłącz urządzenie HoloLens, naciskając przycisk zasilania, aż wszystkie pięć diod LED wyłączy się lub na 15 sekund, jeśli diody LED nie będą odpowiadać. Aby uruchomić urządzenie HoloLens, naciśnij ponownie przycisk zasilania.

Jeśli te kroki nie działają, możesz spróbować odzyskać urządzenie [HoloLens 2](hololens-recovery.md) lub [HoloLens (1. generacja).](hololens1-recovery.md)

[Powrót do listy](#list)

## <a name="low-disk-space-error"></a>Błąd "Mała ilość miejsca na dysku"

Konieczne będzie wolne miejsce do magazynowania, wykonując jedną lub więcej z następujących czynności:

- Usuń niektóre nieużywane spacje. Przejdź do **obszaru Ustawienia**  >  **Przestrzenie** systemowe, wybierz miejsce, które nie jest już  >   **potrzebne,** a następnie wybierz pozycję Usuń .
- Usuń niektóre z umieszczonych hologramów.
- Usuń zdjęcia i filmy wideo z aplikacji Zdjęcia.
- Odinstaluj niektóre aplikacje z urządzenia HoloLens. Na liście **Wszystkie aplikacje** naciśnij i przytrzymaj aplikację, którą chcesz odinstalować, a następnie wybierz pozycję **Odinstaluj.**

[Powrót do listy](#list)

## <a name="calibration-fails"></a>Niepowodzenie awarii

Większość osób powinna pracować, ale istnieją przypadki, w których niepowodzeniem.
  
Niektóre potencjalne przyczyny niepowodzenia awarii to:

- Rozpraszanie uwagi i niesłanianie celów docelowych
- Zanieczyszczona lub zadrzewiona osłona urządzenia lub urządzenie nie jest prawidłowo pozycjonowane
- Zanieczyszczone lub porysowane okulary
- Niektóre typy obiektywów i okularów kontaktowych (kolorowe obiektywy kontaktowe, niektóre toryczne obiektywy kontaktowe, okulary blokujące ir IR, niektóre okulary przeciwsłoneczne, okulary przeciwsłoneczne lub podobne)
- Bardziej wymawiane nagie i niektóre rozszerzenia ukośników
- Zarost lub grube ramki okularów, jeśli blokują one wzrok urządzenia
- Niektóre fizjologia, warunki wzrokowe lub operacje oczu, takie jak wąskie oczy, długie ukośniki, amblyopia, nystagmus, niektóre przypadki LASIK lub inne operacje skoków oczu

Jeśli próba nie powiedzie się, spróbuj:

- Czyszczenie aplikacji do czyszczenia urządzenia
- Czyszczenie okularów
- Wypychanie wizjora urządzenia tak blisko oczu, jak to możliwe
- Przenoszenie obiektów w osłodę poza drogę (na przykład zarostu)
- Włączanie światła w pomieszczeniu lub wyprowadzanie bezpośredniego światła

Jeśli wszystkie wytyczne i ustawienia nadal nie są stosowane, można wyłączyć monit monitu w ustawieniach. Daj nam znać, klikając opinię w [Centrum opinii](hololens-feedback.md).

Zobacz również powiązane informacje dotyczące [rozwiązywania problemów z kolorem obrazu lub jasność.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Ustawienie adresu IPD nie ma zastosowania w przypadku urządzenia HoloLens 2, ponieważ pozycje oka są obliczane przez system. 

[Powrót do listy](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Nie można się zalogować, ponieważ urządzenie HoloLens zostało wcześniej ustawione dla kogoś innego

Możesz [przełożyć urządzenie w tryb **flashowania i**](hololens-recovery.md#clean-reflash-the-device) użyć narzędzia Advanced Recovery Companion w celu odzyskania urządzenia.

[Powrót do listy](#list)


## <a name="unity-isnt-working"></a>Unity nie działa

- Zobacz [Install the tools for](/windows/mixed-reality/install-the-tools) the most-to-date version of Unity recommended for HoloLens development (Instalowanie narzędzi dla najbardziej aktualnej wersji aparatu Unity zalecanej do budowania aplikacji na urządzeniach HoloLens).
- Znane problemy z urządzeniem Unity HoloLens Technical Preview zostały udokumentowane na [forach Aparatu Unity dla urządzenia HoloLens.](https://forum.unity3d.com/threads/known-issues.394627/)

[Powrót do listy](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Portal urządzeń z systemem Windows nie działa prawidłowo

- Funkcja podglądu na żywo w Mixed Reality przechwytywania danych może mieć opóźnienie kilku sekund.

- Na stronie Wirtualne dane wejściowe kontrolki Gest i Przewijanie w sekcji Gesty wirtualne nie działają. Ich użycie nie będzie mieć żadnego efektu. Klawiatura wirtualna na stronie wirtualnych danych wejściowych działa poprawnie.

- Po włączeniu trybu dewelopera w ustawieniach może mieć kilka sekund, zanim Portal urządzeń przełącznik zostanie włączony.

[Powrót do listy](#list)

## <a name="emulator"></a>Emulator
### <a name="the-hololens-emulator-isnt-working"></a>Emulator urządzenia HoloLens nie działa

Informacje o emulatorze urządzenia HoloLens znajdują się w naszej dokumentacji dla deweloperów.  Przeczytaj więcej na [temat rozwiązywania problemów z emulatorem urządzenia HoloLens.](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)


- Nie wszystkie aplikacje w Microsoft Store są zgodne z emulatorem. Na przykład w emulatorze nie można odtwarzać fragmentów Ani Younga Conkera.
- Nie można używać kamery internetowej komputera w emulatorze.
- Funkcja podglądu na żywo Portal urządzeń z systemem Windows nie działa z emulatorem. Nadal można przechwytywać Mixed Reality wideo i obrazy.

[Powrót do listy](#list)

## <a name="i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator"></a>Nie mogę znaleźć lub użyć klawiatury do wpisywania w emulatorze urządzenia HoloLens 2

*Już wkrótce*

[Powrót do listy](#list)

## <a name="voice-commands-arent-working"></a>Polecenia głosowe nie działają

Jeśli Cortana nie odpowiada na polecenia głosowe, upewnij się, że Cortana jest włączona. Na liście Wszystkie aplikacje wybierz pozycję **Ustawienia**  >  **notesu menu** Cortany, aby wprowadzić  >    >   zmiany. Aby dowiedzieć się więcej na temat tego, co możesz powiedzieć, zobacz [Używanie głosu na urządzeniach HoloLens.](hololens-cortana.md)

Na urządzeniach HoloLens (1. generacji) wbudowanej funkcji rozpoznawania mowy nie można skonfigurować. Jest ona zawsze włączona. Na urządzeniu HoloLens 2 możesz wybrać, czy włączyć funkcję rozpoznawania mowy, jak i Cortanę podczas konfigurowania urządzenia.

Jeśli urządzenie HoloLens 2 nie odpowiada na Twój głos, upewnij się, że funkcja rozpoznawania mowy jest włączona. Przejdź do menu **Start**  >  **Settings**  >  **Privacy**  >  **Speech (Ustawienia startowe)** Privacy Speech (Mowa o ochronie prywatności) i włącz rozpoznawanie **mowy.**

[Powrót do listy](#list)

## <a name="hand-input-isnt-working"></a>Ręczne wprowadzanie danych nie działa

Aby mieć pewność, że urządzenie HoloLens będzie widzieć twoje ręce, musisz zachować je w ramce gestu.  Strona Mixed Reality home udostępnia opinię, która informuje o tym, kiedy są śledzone twoje ręce.  Opinie są inne w różnych wersjach urządzenia HoloLens:
- Na urządzeniach HoloLens (1. generacja) kursor spojrzenia zmienia się z kropki na pierścień
- Na urządzeniach HoloLens 2, gdy ręka jest blisko planszy, pojawia się kursor w zasięgu ręki, a gdy plansze znajdują się dalej, pojawia się promienia ręki

Wiele aplikacji immersywnych ma wzorce wejściowe podobne do Mixed Reality Home.  Dowiedz się więcej o używaniu danych wejściowych ręcznie na [urządzeniach HoloLens (1. generacja)](hololens1-basic-usage.md#use-hololens-with-your-hands) i [HoloLens 2.](hololens2-basic-usage.md#the-hand-tracking-frame)

Należy pamiętać, że niektóre typy iniekcj nie działają w przypadku śledzenia rąk.  Częstym przykładem są czarne gumy, które zwykle absorbują światło podczerwone i nie są odbierane przez kamerę z głębokością.  Jeśli Twoja praca wiąże się z gumką, zalecamy wypróbowanie jaśniejszego koloru, takiego jak niebieski lub szary.  Innym przykładem są duże baggy nagie, które zwykle przesłaniają kształt ręki. Zalecamy używanie tak dopasowanych do formularzy, jak to tylko możliwe, aby uzyskać najlepsze wyniki.

Jeśli twoje urządzenie ma odciski palców lub smekty, użyj mikrofibry czyszczącej urządzenie HoloLens, aby wyczyścić ją.

[Powrót do listy](#list)

## <a name="cant-connect-to-wi-fi"></a>Nie można nawiązać połączenia z Wi-Fi

Oto kilka rzeczy, które należy wypróbować, jeśli nie można połączyć urządzenia HoloLens z Wi-Fi siecią:

- Upewnij się, Wi-Fi jest włączona. Aby to sprawdzić, użyj gestu Start, a następnie wybierz **pozycję**  >  **Ustawienia Sieć &amp; Internet**  >  **Wi-Fi.** Jeśli Wi-Fi jest wł., spróbuj go wyłączyć, a następnie ponownie wł.
- Umieść komputer bliżej routera lub punktu dostępu.
- Uruchom ponownie Wi-Fi, a następnie [ponownie uruchom urządzenie HoloLens.](hololens-recovery.md) Spróbuj ponownie nałączyć połączenie.
- Jeśli żadna z tych czynności nie działa, upewnij się, że router korzysta z najnowszego oprogramowania układowego. Te informacje można znaleźć w witrynie internetowej producenta.

[Powrót do listy](#list)
## <a name="bluetooth-devices-arent-pairing"></a>Urządzenia Bluetooth nie są parowane

Jeśli masz problemy z [parowaniem urządzenia Bluetooth,](hololens-connect-devices.md)spróbuj wykonać następujące czynności:

- Przejdź do **ustawień**  >  **Urządzenia** i upewnij się, że funkcja Bluetooth jest włączona. Jeśli tak, wyłącz ją i włącz ponownie.
- Upewnij się, że urządzenie Bluetooth jest w pełni obciążone lub ma świeże baterii.
- Jeśli nadal nie możesz nawiązać połączenia, [uruchom ponownie urządzenie HoloLens.](hololens-recovery.md)

[Powrót do listy](#list)

## <a name="usb-c-microphone-isnt-working"></a>Mikrofon USB-C nie działa
Należy pamiętać, że niektóre mikrofony USB-C nieprawidłowo zgłaszają się jako mikrofon i *prelegent.* Jest to problem z mikrofonem, a nie z urządzeniem HoloLens. Podczas podłączania jednego z tych mikrofonów do urządzenia HoloLens dźwięk może zostać utracony. Na szczęście istnieje prosta poprawka.  

W   ->  **ustawieniach Dźwięk** systemowy jawnie ustaw wbudowane osoby mówiące (sterownik audio funkcji  ->   **analogicznej)** jako **domyślne urządzenie**. Urządzenie HoloLens powinno zapamiętać to ustawienie, nawet jeśli mikrofon zostanie później usunięty i ponownie podłączony.

![Rozwiązywanie problemów z mikrofonami USB-C](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Urządzenia wymienione jako dostępne w ustawieniach nie działają

Urządzenie HoloLens (1. generacja) nie obsługuje profilów audio bluetooth. Urządzenia audio Bluetooth, takie jak głośniki i zestawy nagłowne, mogą być wyświetlane jako dostępne w ustawieniach urządzenia HoloLens, ale nie są obsługiwane.

Urządzenie HoloLens 2 obsługuje profil audio protokołu Bluetooth A2DP do odtwarzania stereo. Profil Bez rąk Bluetooth, który umożliwia przechwytywanie mikrofonu z urządzenia peryferyjnego Bluetooth, nie jest obsługiwany na urządzeniu HoloLens 2.

Jeśli masz problemy z używaniem urządzenia Bluetooth, upewnij się, że jest to obsługiwane urządzenie. Obsługiwane urządzenia są następujące:

- Klawiatury Bluetooth QWERTY w języku angielskim (można ich używać wszędzie tam, gdzie używasz klawiatury holograficznej).
- Myszy Bluetooth.
- Kliknięcie [urządzenia HoloLens](hololens1-clicker.md).

Z urządzeniem HoloLens można sparować inne urządzenia Bluetooth HID i AND. Może być jednak trzeba zainstalować odpowiednie aplikacje towarzyszące z Microsoft Store, aby w rzeczywistości korzystać z urządzeń.

[Powrót do listy](#list)
