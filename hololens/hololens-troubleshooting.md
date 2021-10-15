---
title: HoloLens Rozwiązywanie problemów z urządzeniami
description: Bądź na bieżąco z najpopularniejszymi rozwiązaniami, które HoloLens problemów z urządzeniami i technikami rozwiązywania problemów.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2021
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: ranjibb
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problemy, usterka, rozwiązywanie problemów, poprawka, pomoc, pomoc, HoloLens, emulator
ms.openlocfilehash: 5c79e119352146ac249ef02ab888141391c9cea1
ms.sourcegitcommit: 19d1abb7589cebf14ba45e830f49224f7b4fcfe9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/15/2021
ms.locfileid: "130034199"
---
# <a name="device-troubleshooting"></a>Rozwiązywanie problemów z urządzeniami

W tym artykule opisano sposób rozwiązywania kilku typowych HoloLens problemów.

>[!IMPORTANT]
> Przed rozpoczęciem procedury rozwiązywania problemów upewnij się, że urządzenie jest obciążane od **20 do 40%** pojemności baterii, jeśli jest to możliwe. Wskaźniki [naładowania baterii](hololens2-setup.md#lights-that-indicate-the-battery-level) znajdujące się pod przyciskiem zasilania to szybki sposób sprawdzenia pojemności baterii bez logowania się do urządzenia.

<a id="list"></a>

**Znane problemy**
- [Za każdym razem, gdy zasilanie spada do 18%, urządzenie nagle wyłącza się automatycznie](#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)
- [OneDrive Aplikacja platformy uniwersalnej systemu Windows nie działa dla użytkowników usługi Azure AD](#onedrive-uwp-app-doesnt-work-for-azure-ad-users)
- [Dlaczego widzę informacje 0x80180014 funkcji Autopilot?](#why-do-i-see-0x80180014-during-autopilot)
- [Microsoft Store kod błędu 0x80131500](#microsoft-store-error-code-0x80131500)
- [Microsoft Edge nie można uruchomić mikrofonu](#microsoft-edge-fails-to-start-the-microphone)
- [**Naprawiono** — wideo remote assist zawiesza się po 20 minutach](#remote-assist-video-freezes-after-20-minutes)
- [Automatyczne logowanie prosi o zalogowanie](#auto-login-asks-for-log-in)
- [Microsoft Edge nie można uruchomić](#microsoft-edge-fails-to-launch)
- [Klawiatura nie przełącza się na znaki specjalne](#keyboard-doesnt-switch-to-special-characters)
- [**Naprawiono** — pobieranie zablokowanych plików nie wyświetla błędu](#downloading-locked-files-doesnt-error)
- [**Naprawiono** — Portal urządzeń przekazywania/pobierania pliku jest przekierowywyny czas](#device-portal-file-uploaddownload-times-out)
- [Niebieski ekran po wywrzeniu z niejawnego programu testów w wersji zapoznawczej na urządzeniu flashowym za pomocą kompilacji niejawnego programu testów](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive nie przekaże automatycznie obrazów](#onedrive-doesnt-automatically-upload-pictures)

**Ogólne**
- [HoloLens nie odpowiada lub nie można uruchomić](#hololens-is-unresponsive-or-wont-start)
- [Błąd "Mała ilość miejsca na dysku"](#low-disk-space-error)
- [Niepowodzenie awarii](#calibration-fails)
- [Nie można się zalogować, ponieważ mój HoloLens wcześniej został ustawiony dla kogoś innego](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
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
- [Urządzenia wymienione jako dostępne Ustawienia nie działają](#devices-listed-as-available-in-settings-dont-work)

## <a name="every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically"></a>Za każdym razem, gdy zasilanie spada do 18%, urządzenie nagle wyłącza się automatycznie

Istnieje znany problem, który oznacza, że gdy urządzenie osiągnie poziom naładowania baterii 18%, zostanie nieoczekiwanie zamknięte. Jest to problem z oprogramowaniem, a nie ze sprzętem ani z bateriią, dlatego nie należy wymieniać w tym celu urządzeń. Jeśli nie masz pewności, czy problem pasuje do tej usterki, zobacz:

1. Upewnij się, że na urządzeniach włączono opcjonalną diagnostykę
1. Odtprodukuj problem
1. Przesyłanie [Centrum opinii](hololens-feedback.md) problemu
1. Udostępnianie adresu URL problemu z opinią
1. [Kontakt z pomocą techniczną](https://aka.ms/hololenssupport)

[Powrót do listy](#list)

## <a name="onedrive-uwp-app-doesnt-work-for-azure-ad-users"></a>OneDrive Aplikacja platformy uniwersalnej systemu Windows nie działa dla użytkowników usługi Azure AD

Jeśli używasz aplikacji OneDrive for Business przy użyciu konta usługi Azure AD, być może wystąpił błąd podczas logowania się do skrzynki odbiorczej OneDrive aplikacji. Nie można zalogować się do aplikacji OneDrive nie ma wpływu na automatyczne przekazywanie obrazów i wideo przechwyconych przez aplikację Aparatu. Nadal można zapisywać pliki i uzyskiwać do nich dostęp z OneDrive dla Firm magazynu w chmurze. Zespół OneDrive i HoloLens pracuje nad problemem.

### <a name="workarounds"></a>Obejścia

Wymaganie wstępne: klienci mogą Microsoft Edge, a system operacyjny urządzenia zostanie Windows kompilacji Holographic, 21H1 lub nowszej.

Jeśli ten problem występuje, spróbuj wykonać jedną z następujących czynności:

- Użytkownicy mogą bezpośrednio uzyskać OneDrive do aplikacji Microsoft Edge i korzystać z plików w witrynie internetowej z przeglądarki.
- Użytkownicy mogą zainstalować aplikację OneDrive PWA, aby HoloLens, pobierając ją z Microsoft Edge. Umożliwi to użytkownikom wyświetlanie plików na urządzeniu i zarządzanie nimi ponownie. Przeczytaj te instrukcje [dotyczące instalowania aplikacji OneDrive PWA na komputerze HoloLens.](holographic-store-apps.md#install-microsoft-onedrive-pwa-app)

[Powrót do listy](#list)

## <a name="why-do-i-see-0x80180014-during-autopilot"></a>Dlaczego widzę informacje 0x80180014 funkcji Autopilot?

Ten błąd występuje zwykle podczas resetowania urządzenia i ponownego używania przepływów, w których urządzenie HoloLens co najmniej raz za pośrednictwem rozwiązania Autopilot. Aby rozwiązać ten problem, usuń urządzenie z Microsoft Intune [i](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode) zresetuj je ponownie, aby ukończyć przepływ rozwiązania Autopilot.

Aby uzyskać więcej informacji, zapoznaj się z [krokami rozwiązywania problemów na stronie rozwiązania Autopilot.](hololens2-autopilot.md#why-do-i-see-0x80180014-during-autopilot)

## <a name="microsoft-store-error-code-0x80131500"></a>Microsoft Store kod błędu 0x80131500

Niektórzy użytkownicy mogą mieć Microsoft Store, że nie działają zgodnie z oczekiwaniami, i zobaczą kod błędu 0x80131500. Jest to problem spowodowany tym, że region ustawiony na stronie HoloLens jest niedostępny w aplikacji Microsoft Store na HoloLens. Jeśli wystąpi błąd z kodem 0x80131500, aby obejść ten problem:

1. Ustaw Ustawienia > Time & Language > Region > Country or region (Kraj lub region) na jedną z następujących czynności:
    - Stany Zjednoczone, Japonia, Chiny, Niemcy, Kanada, Zjednoczone Królestwo, Irlandia, Francja, Australia, Nowa Zelandia.
1. Uruchom ponownie aplikację ze Sklepu.
1. Aby zmiana odzwierciedliła zmianę dla całego urządzenia, konieczne będzie jego ponowne uruchomienie.

Zespół HoloLens pracuje nad dodaniem obsługi kolejnych regionów.

Zobacz [tutaj, aby uzyskać informacje o krajach, w HoloLens 2.](hololens2-purchase.md)

## <a name="microsoft-edge-fails-to-start-the-microphone"></a>Microsoft Edge nie można uruchomić mikrofonu

Jeśli użytkownicy używający Microsoft Edge mikrofonu mogą nie uruchomić się, w związku z tym interakcja z usługą Edge w aplikacji HoloLens nie będzie HoloLens. Ten znany problem jest związany z wersją aplikacji Microsoft Edge, nie przekłań urządzenia do starszej wersji, ponieważ nie rozwiąże to tego problemu.

### <a name="who-is-affected"></a>KtoTo problem?

Użytkownicy, którzy mają Microsoft Edge wersji 93, 94 lub 95.
Możesz sprawdzić, którą wersję aplikacji Microsoft Edge masz, używając aplikacji Microsoft Store, a następnie wybrać przycisk "Zobacz więcej" reprezentowany przez przycisk **...** i wybrać pozycję Pliki do pobrania i **aktualizacje.**

### <a name="work-around"></a>Pomiń

Bieżąca poprawka jest w wersji 96, która jest dostępna dla użytkowników zarejestrowanych w usłudze Microsoft Edge Insiders. Różni się to od rejestrowania urządzenia jako Windows Insider. Przeczytaj te instrukcje, aby uzyskać szczegółowe [informacje na temat rejestrowania w niejawnym programie edge.](hololens-new-edge.md#microsoft-edge-insider-channels)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Wideo remote assist zawiesza się po 20 minutach

> [!NOTE]
> Istnieje nowsza wersja usługi Remote Assist, która zawiera poprawkę dla tego problemu. Zaktualizuj [usługę Remote Assist](holographic-store-apps.md#update-apps) do najnowszej wersji, aby uniknąć tego problemu.

> [!NOTE]
> Ze względu na ważność tego znanego problemu tymczasowo wstrzymano dostępność systemu Windows Holographic w wersji 21H1. Kompilacja 21H1 jest teraz ponownie dostępna, więc urządzenia mogą zostać ponownie zaktualizowane do najnowszej kompilacji 21H1.

W najnowszej wersji systemu Windows Holographic w wersji [21H1](hololens-release-notes.md#windows-holographic-version-21h1)niektórzy użytkownicy usługi Remote Assist doświadczyli zamarzania wideo podczas wywołań przez ponad 20 minut. Jest to znany **problem.**

### <a name="workarounds"></a>Obejścia

Jeśli nie możesz zaktualizować usługi Remote Assist do nowszej kompilacji, spróbuj wykonać poniższe czynności.

#### <a name="restart-in-between-calls"></a>Uruchom ponownie między wywołaniami

Jeśli połączenia trwają ponad 20 minut i występuje ten problem, spróbuj ponownie uruchomić urządzenie. Ponowne uruchomienie urządzenia między wywołaniami usługi Remote Assist spowoduje odświeżenie urządzenia i jego ponowne uruchomienie w dobrym stanie.

Aby szybko ponownie uruchomić urządzenie na platformie Windows Holographic, w wersji [21H1](hololens-release-notes.md#windows-holographic-version-21h1) otwórz menu Start i wybierz ikonę użytkownika, a następnie wybierz pozycję **Uruchom ponownie.**

[Powrót do listy](#list)

## <a name="auto-login-asks-for-log-in"></a>Automatyczne logowanie prosi o zalogowanie

Urządzenie HoloLens 2 można skonfigurować do automatycznego logowania się za pośrednictwem opcji logowania kont usługi **Ustawienia —**> i w obszarze Wymagane ustawienie wartości  ->    ->    **Nigdy.** Niektórzy użytkownicy mogą wymagać zalogowania się na urządzeniu ponownie podczas aktualizowania urządzenia przy użyciu znacznie dużej aktualizacji, takiej jak aktualizacja funkcji. Jest to znany **problem.**

Przykład sytuacji, w których może się to zdarzyć:

- Aktualizowanie urządzenia z systemu Windows Holographic w wersji 2004 (kompilacja 19041.xxxx) do wersji Windows Holographic w wersji 21H1 (kompilacja 20346.xxxx)
- Aktualizowanie urządzenia w celu podjęcia dużej aktualizacji w tej samej kompilacji, np. Windows Holographic, wersja 2004 do wersji Windows Holographic, wersja 20H2
- Aktualizowanie urządzenia z obrazu fabryki do najnowszego obrazu

Nie powinno to mieć miejsca w trakcie:

- Urządzenia korzystające z comiesięcznej aktualizacji obsługi

Pomiń metody:

- Metody logowania, takie jak numer PIN, hasło, irys, uwierzytelnianie internetowe lub klucze FIDO2.
- Jeśli nie można zapamiętać numeru PIN urządzenia i inne metody uwierzytelniania są niedostępne, użytkownik może użyć trybu [ręcznego reflashingu.](hololens-recovery.md#manual-flashing-mode-procedure)

[Powrót do listy](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge nie można uruchomić

> [!NOTE]
> Ten problem został pierwotnie utworzony z myślą o wersji wysyłkowej Microsoft Edge o tym. Ten problem można rozwiązać w nowej [Microsoft Edge](hololens-new-edge.md). Jeśli tak nie jest, prosimy o opinię.

Kilku klientów zgłosiło problem, który Microsoft Edge nie można uruchomić. W przypadku tych klientów problem będzie nadal występował po ponownym uruchomieniu i nie zostanie rozwiązany Windows aktualizacji aplikacji. Jeśli ten problem występuje i Windows jest [aktualny,](hololens-updates.md#manually-check-for-updates)prosimy o zgłaszanie usterki z aplikacji Centrum opinii z następującą kategorią i podkategorią: Instalowanie i aktualizowanie programu > Pobieranie, instalowanie i konfigurowanie usługi [Windows](hololens-feedback.md) Update.

Nie ma znanych obejść, ponieważ do tej pory nie można było uzyskać głównej przyczyny problemu. Zgłoszenie usterki za pośrednictwem Centrum opinii pomoże w naszym badaniu! Jest to znany **problem.**

[Powrót do listy](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>Klawiatura nie przełącza się na znaki specjalne

Podczas OOBE występuje problem, który występuje, gdy użytkownik wybrał konto służbowe i wprowadza hasło, próbując przełączyć się na znaki specjalne na klawiaturze, naciskając przycisk &123, nie zmienia się na znaki specjalne. Jest to znany **problem.**

Work-arounds::

- Zamknij klawiaturę i otwórz ją ponownie, naciskając pole tekstowe.
- Niepoprawnie wprowadź hasło. Gdy klawiatura zostanie ponownie wyzowana przy następnym czasie, będzie ona działać zgodnie z oczekiwaniami.
- Uwierzytelnianie internetowe, zamknij klawiaturę i wybierz **pozycję Zaloguj się z innego urządzenia.**
- Jeśli wprowadzasz tylko liczby, użytkownik może nacisnąć i przytrzymać niektóre klawisze, aby otworzyć rozwinięte menu.
- Za pomocą klawiatury USB.

Nie ma to wpływu na:

- Użytkownicy, którzy zdecydują się używać konta osobistego.

[Powrót do listy](#list)

## <a name="downloading-locked-files-doesnt-error"></a>Pobieranie zablokowanych plików nie kończy się błędem

> [!NOTE]
> Jest to znany **problem, który** został rozwiązany na [platformie Windows Holographic w wersji 21H1 — aktualizacja z lipca 2021 r.](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update).

W poprzednich kompilacjach Windows Holographic próba pobrania zablokowanego pliku byłaby stroną błędu HTTP. W aktualizacji Windows Holographic w wersji 21H1 próba pobrania zablokowanego pliku nie powoduje nic widocznego — plik nie zostanie pobrana i nie wystąpi błąd.

[Powrót do listy](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Portal urządzeń przekazywania/pobierania plików przesłoniło
> [!NOTE]
> Jest to znany **problem, który** został rozwiązany na [platformie Windows Holographic w wersji 21H1 — aktualizacja z lipca 2021 r.](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update). Jeśli wcześniej wyłączono połączenie SSL w ramach obejścia, zdecydowanie zalecamy jego ponowne włączenie.

Niektórzy klienci odkryli, że podczas próby przekazania lub pobrania plików operacja może się zawieszać, a następnie kończyć się lub nigdy nie kończyć. Jest to niezależne[](#downloading-locked-files-doesnt-error) od znanego problemu "plik zablokowany" — ma to wpływ na kompilacje systemu Windows Holographic w wersjach 2004, 20H2 i 21H1 na rynku. Przyczyną problemu jest usterka w obsłudze niektórych żądań Portal urządzeń przez usługę , która jest najczęściej występuje w przypadku używania protokołu HTTPS, co jest ustawieniem domyślnym.

### <a name="workaround"></a>Obejście

To obejście, które ma zastosowanie w równym stopniu Wi-Fi i UsbNcm, polega na wyłączeniu opcji "wymagane" w obszarze "Połączenie SSL". W tym celu przejdź do Portal urządzeń **System** i wybierz **stronę Preferencje.** W sekcji **Zabezpieczenia urządzenia** znajdź opcję **Połączenie SSL** i usuń zaznaczenie pola wyboru, aby wyłączyć **opcję Wymagane.**

Użytkownik powinien następnie przejść do strony http://, a nie https:// (adres IP), a funkcje, takie jak przekazywanie i pobieranie plików, będą działać.

[Powrót do listy](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Niebieski ekran po wywrzeniu z niejawnego programu testów w wersji zapoznawczej na urządzeniu flashowym za pomocą kompilacji niejawnego programu testów

Jest to problem, który ma wpływ na użytkowników, którzy byli w kompilacji niejawnego programu testów w wersji zapoznawczej, przeszli do wersji HoloLens 2 przy użyciu nowej kompilacji niejawnego programu testów w wersji zapoznawczej, a następnie nie są zarejestrowani w programie niejawnego testera. Jest to znany **problem.**

Nie ma to wpływu na:

- Użytkownicy, którzy nie są zarejestrowani w programie Windows Insider
- Wewnętrznych:
    - Jeśli urządzenie zostało zarejestrowane od kompilacji niejawnych testerów w wersji 18362.x
    - Jeśli flashował kompilację 19041.x podpisaną przez niejawnego testera I pozostał zarejestrowany w programie niejawnego testera

Pomiń:

- Unikanie problemu
    - Flashuj kompilację bez niejawnych testerów. Jedna z regularnych comiesięcznych aktualizacji.
    - Bądź na testach w wersji zapoznawczej
- Reflash urządzenia

    1. Umieść urządzenie [HoloLens 2 w trybie flashowania](hololens-recovery.md) ręcznie, w pełni przez całkowite zasilanie bez połączenia. Następnie przytrzymując pozycję Volume up (Wolumin w górę), naciśnij przycisk Power (Zasilanie).

    1. Połączenie na komputer i otwórz program Advanced Recovery Companion.

    1. Flashuj HoloLens 2 do domyślnej kompilacji.

[Powrót do listy](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive nie przekaże automatycznie obrazów

Aplikacja OneDrive dla HoloLens nie obsługuje automatycznego przekazywania z aparatu dla kont służbowych. Jest to znany **problem.**

Obejścia:

- Jeśli jest to możliwe dla Twojej firmy, automatyczne przekazywanie aparatów jest obsługiwane na kontach Microsoft klientów. Możesz zalogować się do konta konto Microsoft konta służbowego (aplikacja OneDrive obsługuje logowanie podwójne). Z poziomu konto Microsoft w OneDrive można włączyć automatyczne przekazywanie z kamery w tle.

- Jeśli nie możesz bezpiecznie użyć konta konto Microsoft do automatycznego przekazywania zdjęć, możesz ręcznie przekazać zdjęcia na konto służbowe z OneDrive aplikacji. W tym celu upewnij się, że zalogowano się do konta służbowego w OneDrive aplikacji. Wybierz przycisk **+** i wybierz pozycję **Upload**. Znajdź zdjęcia lub wideo, które chcesz przekazać, przechodząc do tematu **Obrazy > Camera Roll**. Wybierz zdjęcia lub wideo, które chcesz przekazać, a następnie wybierz **przycisk** Otwórz.

[Powrót do listy](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens nie odpowiada lub nie można uruchomić

Jeśli twój HoloLens nie zostanie uruchomić:

- Jeśli diody LED obok przycisku zasilania nie zaczną się migać lub tylko jedna dioda LED miga, może być konieczne [HoloLens.](hololens2-charging.md#charging-the-device)
- Jeśli diody LED są wyświetlane po naciśnięciu przycisku zasilania, ale na ekranie nie widać niczego, wykonaj twarde [resetowanie urządzenia.](hololens-recovery.md#hard-restart-procedure)

Jeśli twoja HoloLens jest zamrożona lub nie odpowiada:

- Wyłącz urządzenie HoloLens naciskając przycisk zasilania, aż wszystkie pięć diod LED wyłączy się lub na 15 sekund, jeśli diody LED nie będą odpowiadać. Aby uruchomić HoloLens, ponownie naciśnij przycisk zasilania.

Jeśli te kroki nie działają, możesz spróbować odzyskać urządzenie [z systemem HoloLens 2](hololens-recovery.md) lub HoloLens [(1. generacji).](hololens1-recovery.md)

[Powrót do listy](#list)

## <a name="low-disk-space-error"></a>Błąd "Mała ilość miejsca na dysku"

Konieczne będzie wolne miejsce do magazynowania, wykonując jedną lub więcej z następujących czynności:

- Usuń niektóre nieużywane spacje. Przejdź do **Ustawienia**  >  **System**  >  **Spaces,** wybierz miejsce, które nie jest już **potrzebne,** a następnie wybierz pozycję Usuń .
- Usuń niektóre z umieszczonych hologramów.
- Usuń zdjęcia i filmy wideo z aplikacji Zdjęcia.
- Odinstaluj niektóre aplikacje z HoloLens. Na liście **Wszystkie aplikacje** naciśnij i przytrzymaj aplikację, którą chcesz odinstalować, a następnie wybierz pozycję **Odinstaluj.**

[Powrót do listy](#list)

## <a name="calibration-fails"></a>Niepowodzenie awarii

Większość osób powinna pracować, ale istnieją przypadki, w których niepowodzeniem.
  
Niektóre potencjalne przyczyny niepowodzenia awarii to:

- Rozpraszanie uwagi i niesąsiadowanie po celach docelowych
- Zanieczyszczona lub zadrzewiona osłona urządzenia lub urządzenie nie jest prawidłowo pozycjonowane
- Zanieczyszczone lub porysowane okulary
- Niektóre typy obiektywów i okularów kontaktowych (kolorowe obiektywy kontaktowe, niektóre toryczne obiektywy kontaktowe, okulary blokujące ir IR, niektóre okulary przeciwsłoneczne, okulary przeciwsłoneczne lub podobne)
- Bardziej wymawiane nagie i niektóre rozszerzenia ukośników
- Zarost lub grube ramki okularów, jeśli blokują one wzrok urządzenia
- Niektóre fizjologia, warunki wzrokowe lub operacje oczu, takie jak wąskie oczy, długie ukośniki, amblyopia, nystagmus, niektóre przypadki LASIK lub inne operacje skoków oczu

Jeśli próba nie powiedzie się, spróbuj:

- Czyszczenie aplikacji do czyszczenia urządzenia
- Czyszczenie okularów
- Wypychanie wizjonera urządzenia tak blisko oczu, jak to możliwe
- Przenoszenie obiektów w osłodę poza drogę (na przykład zarostu)
- Włączanie światła w pomieszczeniu lub wyprowadzanie bezpośredniego światła

Jeśli wszystkie wytyczne są nadal nieudane, można wyłączyć monit o monit o Ustawienia. Daj nam znać, klikając opinię w [Centrum opinii](hololens-feedback.md).

Zobacz również powiązane informacje dotyczące [rozwiązywania problemów z kolorem obrazu lub jasność.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Ustawienie adresu IPD nie ma zastosowania HoloLens 2, ponieważ pozycje oka są obliczane przez system. 

[Powrót do listy](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Nie można się zalogować, ponieważ HoloLens wcześniej została ustawiona dla kogoś innego

Możesz [przełożyć urządzenie w tryb **flashowania i**](hololens-recovery.md#clean-reflash-the-device) użyć narzędzia Advanced Recovery Companion w celu odzyskania urządzenia.

[Powrót do listy](#list)


## <a name="unity-isnt-working"></a>Unity nie działa

- Zobacz [Instalowanie narzędzi dla](/windows/mixed-reality/install-the-tools) najbardziej aktualnej wersji aparatu Unity zalecanej do HoloLens projektowania.
- Znane problemy z platformą Unity HoloLens Technical Preview są udokumentowane na [forach HoloLens Unity.](https://forum.unity3d.com/threads/known-issues.394627/)

[Powrót do listy](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows Portal urządzeń nie działa prawidłowo

- Funkcja podglądu na żywo w Mixed Reality przechwytywania danych może mieć opóźnienie kilku sekund.

- Na stronie Wirtualne dane wejściowe kontrolki Gest i Przewiń w sekcji Gesty wirtualne nie działają. Ich użycie nie będzie mieć żadnego efektu. Klawiatura wirtualna na stronie wirtualnych danych wejściowych działa poprawnie.

- Po włączeniu trybu dewelopera w Ustawienia Portal urządzeń może mieć kilka sekund, zanim przełącznik zostanie włączony.

[Powrót do listy](#list)

## <a name="the-hololens-emulator-isnt-working"></a>HoloLens Emulator nie działa

Informacje o emulatorze HoloLens znajdują się w naszej dokumentacji dla deweloperów.  Przeczytaj więcej na [temat rozwiązywania problemów z HoloLens emulatorem.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)


- Nie wszystkie aplikacje w Microsoft Store są zgodne z emulatorem. Na przykład w emulatorze nie można odtwarzać fragmentów Ani Younga Conkera.
- Nie można używać kamery internetowej komputera w Emulator.
- Funkcja podglądu na żywo Windows Portal urządzeń nie działa z emulatorem. Nadal można przechwytywać Mixed Reality wideo i obrazy.

[Powrót do listy](#list)

## <a name="voice-commands-arent-working"></a>Polecenia głosowe nie działają

Jeśli Cortana nie odpowiada na polecenia głosowe, upewnij się, że Cortana włączona. Na liście Wszystkie aplikacje wybierz pozycję **Cortana**  >  **Menu**  >  **Ustawienia,**  >   aby wprowadzić zmiany. Aby dowiedzieć się więcej na temat tego, co możesz powiedzieć, zobacz Używanie głosu [z HoloLens](hololens-cortana.md).

Na HoloLens (1. generacji) wbudowanej funkcji rozpoznawania mowy nie można skonfigurować. Jest ona zawsze włączona. Na HoloLens 2 możesz wybrać, czy włączyć zarówno rozpoznawanie mowy, jak i Cortana podczas konfigurowania urządzenia.

Jeśli urządzenie HoloLens 2 nie odpowiada na Twój głos, upewnij się, że funkcja rozpoznawania mowy jest włączona. Przejdź do **tematu**  >  **Start Ustawienia**  >  **privacy**  >  **speech** i włącz rozpoznawanie **mowy.**

[Powrót do listy](#list)

## <a name="hand-input-isnt-working"></a>Ręczne wprowadzanie danych nie działa

Aby upewnić się HoloLens, że twoje ręce będą widać, musisz zachować je w ramce gestu.  Strona Mixed Reality Home udostępnia opinię, która informuje o tym, kiedy są śledzone twoje ręce.  Opinie są inne w różnych wersjach HoloLens:

- Na HoloLens (1. generacja) kursor spojrzenia zmienia się z kropki na pierścień
- Na HoloLens 2, gdy ręka jest blisko planszy, pojawia się kursor w zasięgu ręki, a promienia ręki, gdy plansze są dalej

Wiele aplikacji immersywnych ma wzorce wejściowe podobne do Mixed Reality Home.  Dowiedz się więcej na temat korzystania z danych wejściowych HoloLens [(1. generacja)](hololens1-basic-usage.md#use-hololens-with-your-hands) [i HoloLens 2.](hololens2-basic-usage.md#the-hand-tracking-frame)

Należy pamiętać, że niektóre typy iniekcj nie działają w przypadku śledzenia rąk.  Powszechnym przykładem są czarne gumy, które zwykle absorbują światło podczerwone i nie są odbierane przez kamerę z głębokością.  Jeśli Twoja praca wiąże się z gumką, zalecamy wypróbowanie jaśniejszego koloru, takiego jak niebieski lub szary.  Innym przykładem są duże baggy nagie, które zwykle przesłaniają kształt ręki. Zalecamy używanie tak dopasowanych do formularzy, jak to tylko możliwe, aby uzyskać najlepsze wyniki.

Jeśli twoje urządzenie ma odciski palców lub smekty, użyj mikrofibry czyszczącej, która została HoloLens, aby wyczyścić ją.

[Powrót do listy](#list)

## <a name="cant-connect-to-wi-fi"></a>Nie można nawiązać połączenia z Wi-Fi

Oto kilka rzeczy, które należy wypróbować, jeśli nie można połączyć sieci HoloLens z Wi-Fi siecią:

- Upewnij się, Wi-Fi jest włączona. Aby to sprawdzić, użyj gestu Start, a następnie wybierz **Ustawienia**  >  **Sieci &amp;**  >  **Wi-Fi.** Jeśli Wi-Fi jest wł., spróbuj wyłączyć ją, a następnie ponownie wł.
- Umieść komputer bliżej routera lub punktu dostępu.
- Uruchom ponownie Wi-Fi, a następnie [uruchom ponownie HoloLens](hololens-recovery.md). Spróbuj ponownie nawiązać połączenie.
- Jeśli żadna z tych czynności nie działa, upewnij się, że router korzysta z najnowszego oprogramowania układowego. Te informacje można znaleźć w witrynie internetowej producenta.

[Powrót do listy](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth urządzenia nie są parowane

Jeśli masz problemy z [parowaniem urządzenia Bluetooth,](hololens-connect-devices.md)spróbuj wykonać następujące czynności:

- Przejdź do **Ustawienia**  >  **Urządzenia** i upewnij się, że Bluetooth włączona. Jeśli tak, wyłącz ją i włącz ponownie.
- Upewnij się, że urządzenie Bluetooth jest w pełni obciążone lub ma świeże baterii.
- Jeśli nadal nie możesz nawiązać połączenia, [uruchom ponownie HoloLens](hololens-recovery.md).

[Powrót do listy](#list)

## <a name="usb-c-microphone-isnt-working"></a>Mikrofon USB-C nie działa

Należy pamiętać, że niektóre mikrofony USB-C nieprawidłowo zgłaszają się jako mikrofon i *prelegent.* Jest to problem z mikrofonem, a nie z HoloLens. Podczas podłączania jednego z tych mikrofonów do HoloLens, dźwięk może zostać utracony. Na szczęście istnieje prosta poprawka.  

W **Ustawienia**  ->  **System**  ->  **Sound** jawnie ustaw wbudowane osoby mówiące **(sterownik audio** funkcji analogicznej) jako domyślne urządzenie . HoloLens zapamiętać to ustawienie, nawet jeśli mikrofon zostanie później usunięty i ponownie nawiązyny połączenie.

![Rozwiązywanie problemów z mikrofonami USB-C.](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Urządzenia wymienione jako dostępne Ustawienia nie działają

HoloLens (1. generacji) nie obsługuje profilów Bluetooth audio. Bluetooth audio, takie jak głośniki i zestawy nagłowne, mogą być wyświetlane jako dostępne w HoloLens, ale nie są obsługiwane.

HoloLens 2 obsługuje profil audio Bluetooth A2DP do odtwarzania stereo. Profil Bluetooth Hands Free, który umożliwia przechwytywanie mikrofonu z urządzenia peryferyjnego Bluetooth nie jest obsługiwany na urządzeniach HoloLens 2.

Jeśli masz problemy z używaniem urządzenia Bluetooth, upewnij się, że jest to obsługiwane urządzenie. Obsługiwane urządzenia są następujące:

- Język angielski QWERTY Bluetooth klawiatury (można ich używać wszędzie tam, gdzie używasz klawiatury holograficznej).
- Bluetooth myszy.
- Kliknij [HoloLens kliknij przycisk](hololens1-clicker.md).

Inne urządzenia HID Bluetooth MOŻNA sparować z urządzeniami z systemem HoloLens. Może być jednak trzeba zainstalować odpowiednie aplikacje towarzyszące z Microsoft Store, aby faktycznie korzystać z urządzeń.

[Powrót do listy](#list)
