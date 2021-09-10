---
title: HoloLens Rozwiązywanie problemów z urządzeniami
description: Bądź na bieżąco z najpopularniejszymi rozwiązaniami, które HoloLens problemów z urządzeniami i technik rozwiązywania problemów.
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
ms.openlocfilehash: 6ac86acf85e8e4fc1b97473732ea358d3d612d12
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427927"
---
# <a name="device-troubleshooting"></a>Rozwiązywanie problemów z urządzeniami

W tym artykule opisano sposób rozwiązywania kilku typowych HoloLens problemów.

>[!IMPORTANT]
> Przed rozpoczęciem procedury rozwiązywania problemów upewnij się, że urządzenie jest obciążane od **20 do 40%** pojemności baterii, jeśli jest to możliwe. Wskaźniki [naładowania baterii znajdujące](hololens2-setup.md#lights-that-indicate-the-battery-level) się pod przyciskiem zasilania to szybki sposób na sprawdzenie pojemności baterii bez logowania się do urządzenia.

<a id="list"></a>

**Znane problemy**
- [Wideo remote assist zawiesza się po 20 minutach](#remote-assist-video-freezes-after-20-minutes)
- [Automatyczne logowanie prosi o zalogowanie](#auto-login-asks-for-log-in)
- [Microsoft Edge nie można uruchomić](#microsoft-edge-fails-to-launch)
- [Klawiatura nie przełącza się na znaki specjalne](#keyboard-doesnt-switch-to-special-characters)
- [Pobieranie zablokowanych plików nie pokazuje błędu](#downloading-locked-files-doesnt-error)
- [Portal urządzeń umyka czas przekazywania/pobierania pliku](#device-portal-file-uploaddownload-times-out)
- [Niebieski ekran po wywrzeniu z wersji zapoznawczej niejawnego programu testów na urządzeniu z flashem kompilacji niejawnego testera](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive nie przekaże automatycznie obrazów](#onedrive-doesnt-automatically-upload-pictures)

**Ogólne**
- [HoloLens nie odpowiada lub nie można uruchomić](#hololens-is-unresponsive-or-wont-start)
- [Błąd "Mała ilość miejsca na dysku"](#low-disk-space-error)
- [Niepowodzenie awarii](#calibration-fails)
- [Nie można się zalogować, ponieważ moja HoloLens wcześniej została ustawiona dla kogoś innego](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [Unity nie działa](#unity-isnt-working)
- [Windows Portal urządzeń nie działa prawidłowo](#windows-device-portal-isnt-working-correctly)
- [HoloLens Emulator nie działa](#the-hololens-emulator-isnt-working)

**Dane wejściowe**
- [Polecenia głosowe nie działają](#voice-commands-arent-working)
- [Ręczne wprowadzanie danych nie działa](#hand-input-isnt-working)

**Połączenia**
- [Nie można nawiązać połączenia z siecią Wi-Fi](#cant-connect-to-wi-fi)

**Urządzenia zewnętrzne** 
- [Bluetooth urządzenia nie są parowane](#bluetooth-devices-arent-pairing)
- [Mikrofon USB-C nie działa](#usb-c-microphone-isnt-working)
- [Urządzenia wymienione jako dostępne w Ustawienia nie działają](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Wideo remote assist zawiesza się po 20 minutach

> [!NOTE]
> Istnieje nowsza wersja usługi Remote Assist, która zawiera poprawkę dla tego problemu. Zaktualizuj [usługę Remote Assist](holographic-store-apps.md#update-apps) do najnowszej wersji, aby uniknąć tego problemu.

> [!NOTE]
> Ze względu na ważność tego znanego problemu tymczasowo wstrzymano dostępność systemu Windows Holographic w wersji 21H1. Kompilacja 21H1 jest teraz ponownie dostępna, więc urządzenia mogą zostać ponownie zaktualizowane do najnowszej kompilacji 21H1.

W najnowszej wersji systemu Windows Holographic w wersji [21H1](hololens-release-notes.md#windows-holographic-version-21h1)niektórzy użytkownicy usługi Remote Assist doświadczyli blokowania wideo podczas połączeń przez 20 minut. Jest to znany **problem.**

### <a name="workarounds"></a>Obejścia

Jeśli nie możesz zaktualizować usługi Remote Assist do nowszej kompilacji, spróbuj wykonać następujące czynności.

#### <a name="restart-in-between-calls"></a>Uruchom ponownie między wywołaniami

Jeśli połączenia są trwające ponad 20 minut i występuje ten problem, spróbuj ponownie uruchomić urządzenie. Ponowne uruchomienie urządzenia między wywołaniami usługi Remote Assist spowoduje odświeżenie urządzenia i jego ponowne uruchomienie w dobrym stanie.

Aby szybko ponownie uruchomić urządzenie na Windows Holographic, w wersji [21H1](hololens-release-notes.md#windows-holographic-version-21h1) otwórz menu Start i wybierz ikonę użytkownika, a następnie wybierz pozycję **Uruchom ponownie.**

[Powrót do listy](#list)

## <a name="auto-login-asks-for-log-in"></a>Automatyczne logowanie prosi o zalogowanie

Urządzenie HoloLens 2 można skonfigurować do automatycznego logowania się za pośrednictwem opcji logowania kont usługi **Ustawienia >** i w obszarze Wymagane ustawienie wartości  ->    ->   Nigdy.   Niektórzy użytkownicy mogą wymagać zalogowania się na urządzeniu ponownie podczas aktualizowania urządzenia przy użyciu znacznie dużej aktualizacji, takiej jak aktualizacja funkcji. Jest to znany **problem.**

Przykład sytuacji, w których może się to zdarzyć:

- Aktualizowanie urządzenia z systemu Windows Holographic w wersji 2004 (kompilacja 19041.xxxx) do wersji Windows Holographic, wersja 21H1 (kompilacja 20346.xxxx)
- Aktualizowanie urządzenia w celu podjęcia dużej aktualizacji w tej samej kompilacji, np. Windows Holographic, wersja 2004 do wersji Windows Holographic, wersja 20H2
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

Kilku klientów zgłosiło problem, który Microsoft Edge nie można uruchomić. W przypadku tych klientów problem będzie nadal występował po ponownym uruchomieniu i nie zostanie rozwiązany Windows aktualizacji aplikacji. Jeśli ten problem występuje i potwierdzono, że program [Windows](hololens-updates.md#manually-check-for-updates)jest aktualny, prosimy o zgłaszanie usterki z aplikacji Centrum opinii z następującą kategorią i podkategorią: Instalowanie i aktualizowanie usługi > Pobieranie, instalowanie i konfigurowanie usługi [Windows](hololens-feedback.md) Update.

Nie ma znanych obejść, ponieważ do tej pory nie można było głównej przyczyny problemu. Zgłoszenie usterki za pośrednictwem Centrum opinii pomoże w naszym badaniu! Jest to znany **problem.**

[Powrót do listy](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>Klawiatura nie przełącza się na znaki specjalne

Podczas OOBE występuje problem, który występuje, gdy użytkownik wybrał konto służbowe i wprowadza hasło, próbując przełączyć się na znaki specjalne na klawiaturze, naciskając przycisk &123, nie zmienia się na znaki specjalne. Jest to znany **problem.**

Omiń:

- Zamknij klawiaturę i otwórz ją ponownie, naciskając pole tekstowe.
- Niepoprawnie wprowadź hasło. Po następnym wznowione klawiatury będzie działać zgodnie z oczekiwaniami.
- Uwierzytelnianie internetowe, zamknij klawiaturę i wybierz **pozycję Zaloguj się z innego urządzenia.**
- Jeśli wprowadzasz tylko liczby, użytkownik może nacisnąć i przytrzymać niektóre klawisze, aby otworzyć rozwinięte menu.
- Za pomocą klawiatury USB.

Nie ma to wpływu na:

- Użytkownicy, którzy wybiorą opcję korzystania z konta osobistego.

[Powrót do listy](#list)

## <a name="downloading-locked-files-doesnt-error"></a>Pobieranie zablokowanych plików nie kończy się błędem

> [!NOTE]
> Jest to znany **problem, który** został rozwiązany na [platformie Windows Holographic w wersji 21H1 — aktualizacja z lipca 2021 r.](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update).

W poprzednich kompilacjach Windows Holographic próba pobrania zablokowanego pliku byłaby stroną błędu HTTP. Na platformie Windows Holographic aktualizacja w wersji 21H1, próba pobrania zablokowanego pliku powoduje, że nic nie dzieje się widoczne — plik nie zostanie pobrana i nie wystąpi błąd.

[Powrót do listy](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Portal urządzeń umyka czas przekazywania/pobierania pliku
> [!NOTE]
> Jest to znany **problem, który** został rozwiązany na [platformie Windows Holographic w wersji 21H1 — aktualizacja z lipca 2021 r.](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update). Jeśli wcześniej wyłączono połączenie SSL w ramach obejścia, zdecydowanie zalecamy jego ponowne włączenie.

Niektórzy klienci odkryli, że podczas próby przekazania lub pobrania plików operacja może się zawieszać, a następnie kończyć się lub nigdy nie kończyć. Jest to oddzielone[](#downloading-locked-files-doesnt-error) od znanego problemu "plik zablokowany" — dotyczy Windows Holographic w wersjach 2004, 20H2 i 21H1 w kompilacjach na rynku. Problem jest główny spowodowany usterką w obsłudze niektórych żądań przez Portal urządzeń i jest najbardziej stale trafiony w przypadku korzystania z protokołu https, co jest ustawieniem domyślnym.

### <a name="workaround"></a>Obejście

To obejście, które ma zastosowanie w równym stopniu Wi-Fi i UsbNcm, polega na wyłączeniu opcji "wymagane" w obszarze "Połączenie SSL". W tym celu przejdź do **Portal urządzeń, System** i wybierz **stronę Preferencje.** W sekcji **Zabezpieczenia urządzenia znajdź** opcję Połączenie **SSL** i usuń zaznaczenie pola wyboru, aby wyłączyć **opcję Wymagane.**

Użytkownik powinien następnie przejść do strony http://, a nie https:// (adres IP), a funkcje, takie jak przekazywanie i pobieranie plików, będą działać.

[Powrót do listy](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Niebieski ekran po wywrzeniu z niejawnego programu testów w wersji zapoznawczej na urządzeniu flashowym za pomocą kompilacji niejawnego programu testów

Jest to problem, który ma wpływ na użytkowników, którzy byli w kompilacji niejawnego programu testów w wersji zapoznawczej, przeszli do wersji HoloLens 2 przy użyciu nowej kompilacji niejawnego programu testów w wersji zapoznawczej, a następnie nie są zarejestrowani w programie niejawnego programu testów. Jest to znany **problem.**

Nie ma to wpływu na:
- Użytkownicy, którzy nie są zarejestrowani w programie Windows Insider 
- Wewnętrznych:
    - Jeśli urządzenie zostało zarejestrowane od kompilacji niejawnych testerów w wersji 18362.x
    - Jeśli flashował kompilację 19041.x podpisaną przez niejawnego testera I pozostał zarejestrowany w programie dla niejawnych testerów

Pomiń: 
- Unikaj problemu 
    - Flashuj kompilację bez niejawnych testerów. Jedna z regularnych comiesięcznych aktualizacji.
    - Bądź na testach w wersji zapoznawczej
- Reflash urządzenia

    1. Umieść urządzenie [HoloLens 2 w trybie](hololens-recovery.md) flashowania ręcznie, w pełni przez całkowite zasilanie bez połączenia. Następnie przytrzymaniu przycisku Volume up naciśnij przycisk Zasilania.
    
    1. Połączenie na komputer i otwórz program Advanced Recovery Companion.
    
    1. Flashuj HoloLens 2 do domyślnej kompilacji.

[Powrót do listy](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive nie przekaże automatycznie obrazów

Aplikacja OneDrive dla HoloLens nie obsługuje automatycznego przekazywania z aparatu dla kont służbowych. Jest to znany **problem.**

Obejścia:

- Jeśli jest to możliwe dla Twojej firmy, automatyczne przekazywanie aparatów jest obsługiwane na kontach Microsoft użytkowników. Możesz zalogować się do konta konto Microsoft konta służbowego (aplikacja OneDrive obsługuje logowanie podwójne). Z poziomu konto Microsoft w OneDrive można włączyć automatyczne przekazywanie z kamery w tle.

- Jeśli nie możesz bezpiecznie użyć konta konto Microsoft do automatycznego przekazywania zdjęć, możesz ręcznie przekazać zdjęcia na konto służbowe z aplikacji OneDrive aplikacji. W tym celu upewnij się, że zalogowano się do konta służbowego w OneDrive aplikacji. Wybierz przycisk **+** i wybierz pozycję **Upload**. Znajdź zdjęcia lub wideo, które chcesz przekazać, przechodząc do tematu **Obrazy > Camera Roll**. Wybierz zdjęcia lub wideo, które chcesz przekazać, a następnie wybierz **przycisk** Otwórz.

[Powrót do listy](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens nie odpowiada lub nie można uruchomić

Jeśli twój HoloLens nie zostanie uruchomić:

- Jeśli diody LED obok przycisku zasilania nie zaczną się migać lub tylko jedna dioda LED miga, może być konieczne [HoloLens.](hololens2-charging.md#charging-the-device)
- Jeśli diody LED są wyświetlane po naciśnięciu przycisku zasilania, ale na ekranie nie widać niczego, wykonaj twarde [resetowanie urządzenia.](hololens-recovery.md#hard-reset-procedure)

Jeśli urządzenie HoloLens zamrożone lub nie odpowiada:

- Wyłącz urządzenie HoloLens naciskając przycisk zasilania, aż wszystkie pięć diod LED wyłączy się lub na 15 sekund, jeśli diody LED nie będą odpowiadać. Aby uruchomić HoloLens, ponownie naciśnij przycisk zasilania.

Jeśli te kroki nie działają, możesz spróbować odzyskać urządzenie z systemem [HoloLens 2](hololens-recovery.md) lub HoloLens [(1. generacji).](hololens1-recovery.md)

[Powrót do listy](#list)

## <a name="low-disk-space-error"></a>Błąd "Mała ilość miejsca na dysku"

Konieczne będzie wolne miejsce do magazynowania, wykonując jedną lub więcej z następujących czynności:

- Usuń niektóre nieużywane spacje. Przejdź do **Ustawienia**  >  **System**  >  **Spaces,** wybierz miejsce, które nie jest już **potrzebne,** a następnie wybierz pozycję Usuń .
- Usuń niektóre z umieszczonych hologramów.
- Usuń zdjęcia i filmy wideo z aplikacji Zdjęcia.
- Odinstaluj niektóre aplikacje z HoloLens. Na liście **Wszystkie aplikacje** naciśnij i przytrzymaj aplikację, którą chcesz odinstalować, a następnie wybierz pozycję **Odinstaluj.**

[Powrót do listy](#list)

## <a name="calibration-fails"></a>Niepowodzenie awarii

Większość osób powinna pracować, ale zdarzają się przypadki, w których nie powiedzie się to.
  
Niektóre potencjalne przyczyny niepowodzenia awarii to:

- Rozpraszanie uwagi i nie podążanie za celami
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

Jeśli wszystkie wytyczne zostały przestrzegane, a pochylisz się nad wszystkimi wytycznymi, możesz wyłączyć monit o monit o Ustawienia. Daj nam znać, klikając opinię w [Centrum opinii](hololens-feedback.md).

Zobacz również powiązane informacje dotyczące [rozwiązywania problemów z kolorem obrazu lub jasność.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Ustawienie wartości IPD nie ma zastosowania HoloLens 2, ponieważ pozycje oka są obliczane przez system. 

[Powrót do listy](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Nie można się zalogować, ponieważ mój HoloLens wcześniej został ustawiony dla kogoś innego

Możesz [przełożyć urządzenie w tryb **flashowania i**](hololens-recovery.md#clean-reflash-the-device) użyć narzędzia Advanced Recovery Companion w celu odzyskania urządzenia.

[Powrót do listy](#list)


## <a name="unity-isnt-working"></a>Unity nie działa

- Zobacz [Install the tools for](/windows/mixed-reality/install-the-tools) the most-to-date version of Unity recommended for HoloLens development (Instalowanie narzędzi dla najbardziej aktualnej wersji aparatu Unity zalecanej do HoloLens projektowania).
- Znane problemy z platformą Unity HoloLens Technical Preview są udokumentowane na [forach HoloLens Unity.](https://forum.unity3d.com/threads/known-issues.394627/)

[Powrót do listy](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows Portal urządzeń nie działa prawidłowo

- Funkcja podglądu na żywo w Mixed Reality przechwytywania danych może mieć opóźnienie kilku sekund.

- Na stronie Wirtualne dane wejściowe kontrolki Gest i Przewijanie w sekcji Gesty wirtualne nie działają. Ich użycie nie będzie mieć żadnego efektu. Klawiatura wirtualna na stronie wirtualnych danych wejściowych działa poprawnie.

- Po włączeniu trybu dewelopera w Ustawienia może mieć kilka sekund, zanim Portal urządzeń przełącznik zostanie włączony.

[Powrót do listy](#list)

## <a name="the-hololens-emulator-isnt-working"></a>HoloLens Emulator nie działa

Informacje o emulatorze HoloLens znajdują się w naszej dokumentacji dla deweloperów.  Przeczytaj więcej na [temat rozwiązywania problemów z HoloLens emulatorem.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)


- Nie wszystkie aplikacje w Microsoft Store są zgodne z emulatorem. Na przykład w emulatorze nie można odtwarzać fragmentów Ani Younga Conkera.
- Nie można używać kamery internetowej komputera w Emulator.
- Funkcja podglądu na żywo Windows Portal urządzeń nie działa z emulatorem. Nadal można przechwytywać Mixed Reality wideo i obrazy.

[Powrót do listy](#list)

## <a name="voice-commands-arent-working"></a>Polecenia głosowe nie działają

Jeśli Cortana nie odpowiada na polecenia głosowe, upewnij się, że Cortana włączona. Na liście Wszystkie aplikacje wybierz **pozycję** Cortana  >  **Menu**  >  **Ustawienia,** aby wprowadzić  >   zmiany. Aby dowiedzieć się więcej na temat tego, co możesz powiedzieć, zobacz Używanie głosu [z HoloLens](hololens-cortana.md).

Na HoloLens (1. generacji) wbudowanej funkcji rozpoznawania mowy nie można skonfigurować. Jest ona zawsze włączona. Na HoloLens 2 możesz wybrać, czy włączyć zarówno rozpoznawanie mowy, jak i Cortana podczas konfigurowania urządzenia.

Jeśli urządzenie HoloLens 2 nie odpowiada na Twój głos, upewnij się, że funkcja rozpoznawania mowy jest włączona. Przejdź do **tematu Start**  >  **Ustawienia**  >  **Privacy**  >  **Speech** i włącz **rozpoznawanie mowy.**

[Powrót do listy](#list)

## <a name="hand-input-isnt-working"></a>Ręczne wprowadzanie danych nie działa

Aby upewnić się HoloLens widać ręce, należy zachować je w ramce gestu.  Strona Mixed Reality Home udostępnia opinie, które pozwalają dowiedzieć się, kiedy ręce są śledzone.  Opinie są różne w różnych wersjach HoloLens:
- Na HoloLens (1. generacji) kursor spojrzenia zmienia się z kropki na pierścień
- Na HoloLens 2, gdy ręka jest blisko planszy, pojawia się kursor w zasięgu ręki, a promienia ręki, gdy plansze są dalej

Wiele aplikacji immersywnych ma wzorce wejściowe podobne do Mixed Reality Home.  Dowiedz się więcej o używaniu danych wejściowych ręcznie [HoloLens (1. generacji)](hololens1-basic-usage.md#use-hololens-with-your-hands) [i HoloLens 2.](hololens2-basic-usage.md#the-hand-tracking-frame)

Należy pamiętać, że niektóre typy iniekcj nie działają w przypadku śledzenia rąk.  Częstym przykładem są czarne gumy, które zwykle absorbują światło podczerwone i nie są odbierane przez kamerę z głębokością.  Jeśli Twoja praca wiąże się z gumką, zalecamy wypróbowanie jaśniejszego koloru, takiego jak niebieski lub szary.  Innym przykładem są duże baggy nagie, które zwykle przesłaniają kształt ręki. Zalecamy używanie tak dopasowanych do formularzy, jak to tylko możliwe, aby uzyskać najlepsze wyniki.

Jeśli twoja wizjer ma odciski palców lub smekty, użyj mikrofibry czyszczącej, która została HoloLens, aby wyczyścić ją.

[Powrót do listy](#list)

## <a name="cant-connect-to-wi-fi"></a>Nie można nawiązać połączenia z Wi-Fi

Oto kilka rzeczy, które należy wypróbować, jeśli nie można połączyć sieci HoloLens z Wi-Fi siecią:

- Upewnij się, Wi-Fi jest włączona. Aby to sprawdzić, użyj gestu Start, a następnie wybierz **pozycję Ustawienia**  >  **Network &amp; Internet**  >  **Wi-Fi.** Jeśli Wi-Fi jest wł., spróbuj go wyłączyć, a następnie ponownie wł.
- Umieść komputer bliżej routera lub punktu dostępu.
- Uruchom ponownie Wi-Fi, a następnie [uruchom ponownie HoloLens](hololens-recovery.md). Spróbuj ponownie nałączyć połączenie.
- Jeśli żadna z tych czynności nie działa, upewnij się, że router korzysta z najnowszego oprogramowania układowego. Te informacje można znaleźć w witrynie internetowej producenta.

[Powrót do listy](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth urządzenia nie są parowane

Jeśli masz problemy z [parą urządzenia Bluetooth,](hololens-connect-devices.md)spróbuj wykonać następujące czynności:

- Przejdź do **Ustawienia**  >  **Urządzenia** i upewnij się, Bluetooth jest włączona. Jeśli tak, wyłącz ją i włącz ponownie.
- Upewnij się, że urządzenie Bluetooth jest w pełni obciążone lub ma świeże baterii.
- Jeśli nadal nie możesz nawiązać połączenia, [uruchom ponownie HoloLens](hololens-recovery.md).

[Powrót do listy](#list)

## <a name="usb-c-microphone-isnt-working"></a>Mikrofon USB-C nie działa
Należy pamiętać, że niektóre mikrofony USB-C nieprawidłowo zgłaszają się jako mikrofon i *prelegent.* Jest to problem z mikrofonem, a nie z HoloLens. Podczas podłączania jednego z tych mikrofonów do HoloLens, dźwięk może zostać utracony. Na szczęście istnieje prosta poprawka.  

W **Ustawienia**  ->  **System**  ->  **Sound** jawnie ustaw wbudowane osoby mówiące **(sterownik audio** funkcji analogicznej) jako domyślne urządzenie . HoloLens zapamiętać to ustawienie, nawet jeśli mikrofon zostanie później usunięty i ponownie podłączony.

![Rozwiązywanie problemów z mikrofonami USB-C.](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Urządzenia wymienione jako dostępne w Ustawienia nie działają

HoloLens (1. generacja) nie obsługuje profilów Bluetooth audio. Bluetooth audio, takie jak głośników i zestawy nagłowne, mogą być wyświetlane jako dostępne HoloLens ustawieniach, ale nie są obsługiwane.

HoloLens 2 obsługuje Bluetooth audio A2DP do odtwarzania stereo. Profil Bluetooth Hands Free, który umożliwia przechwytywanie mikrofonu z urządzenia peryferyjnego Bluetooth nie jest obsługiwany na HoloLens 2.

Jeśli masz problemy z używaniem urządzenia Bluetooth, upewnij się, że jest to obsługiwane urządzenie. Obsługiwane urządzenia są następujące:

- QWERTY w języku angielskim Bluetooth klawiatury (można ich używać wszędzie tam, gdzie używasz klawiatury holograficznej).
- Bluetooth myszy.
- Kliknij [HoloLens .](hololens1-clicker.md)

Inne urządzenia HID Bluetooth MOŻNA sparować z urządzeniami HID HoloLens. Może być jednak trzeba zainstalować odpowiednie aplikacje towarzyszące z Microsoft Store, aby w rzeczywistości korzystać z urządzeń.

[Powrót do listy](#list)
