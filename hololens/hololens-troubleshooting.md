---
title: HoloLens Rozwiązywanie problemów z urządzeniami
description: Bądź na bieżąco z najpopularniejszymi rozwiązaniami, które HoloLens problemów z urządzeniami i technikami rozwiązywania problemów.
author: evmill
ms.author: v-evmill
ms.date: 10/7/2021
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: ranjibb
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problemy, usterka, rozwiązywanie problemów, poprawka, pomoc, pomoc, HoloLens, emulator
ms.openlocfilehash: ceb6f2670b15f46d17a0cb36f6602ae3d4e3ec1d
ms.sourcegitcommit: 8a3f925d2bda13c095b35f14d80afdd876aa859c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/12/2021
ms.locfileid: "129800542"
---
# <a name="device-troubleshooting"></a>Rozwiązywanie problemów z urządzeniami

W tym artykule opisano sposób rozwiązywania kilku typowych HoloLens problemów.

>[!IMPORTANT]
> Przed rozpoczęciem procedury rozwiązywania problemów upewnij się, że urządzenie jest obciążane od **20 do 40%** pojemności baterii, jeśli jest to możliwe. Wskaźniki [naładowania baterii](hololens2-setup.md#lights-that-indicate-the-battery-level) znajdujące się pod przyciskiem zasilania to szybki sposób sprawdzenia pojemności baterii bez logowania się do urządzenia.

<a id="list"></a>

**Znane problemy**
- [Za każdym razem, gdy zasilanie spada do 18%, urządzenie nagle wyłącza się automatycznie](#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)
- [OneDrive Aplikacja platformy uniwersalnej systemu Windows nie działa dla użytkowników usługi Azure AD](#onedrive-uwp-app-doesnt-work-for-azure-ad-users)
- [Wideo remote assist zawiesza się po 20 minutach](#remote-assist-video-freezes-after-20-minutes)
- [Automatyczne logowanie prosi o zalogowanie](#auto-login-asks-for-log-in)
- [Microsoft Edge nie można uruchomić](#microsoft-edge-fails-to-launch)
- [Klawiatura nie przełącza się na znaki specjalne](#keyboard-doesnt-switch-to-special-characters)
- [Pobieranie zablokowanych plików nie wyświetla błędu](#downloading-locked-files-doesnt-error)
- [Portal urządzeń przekazywania/pobierania plików przesłoniło](#device-portal-file-uploaddownload-times-out)
- [Niebieski ekran po wywrzeniu z niejawnego programu testów w wersji zapoznawczej na urządzeniu flashowym za pomocą kompilacji niejawnego testera](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
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
- [Urządzenia wymienione jako dostępne w Ustawienia nie działają](#devices-listed-as-available-in-settings-dont-work)

## <a name="every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically"></a>Za każdym razem, gdy zasilanie spada do 18%, urządzenie nagle wyłącza się automatycznie

Istnieje znany problem, który występuje, gdy urządzenie osiągnie poziom baterii 18%, zostanie nieoczekiwanie zamknięte. Jest to problem z oprogramowaniem, a nie ze sprzętem ani z bateriią, dlatego nie wymieniaj w tym celu urządzeń. Jeśli nie masz pewności, czy problem pasuje do tej usterki, zobacz:

1. Upewnij się, że na urządzeniach włączono opcjonalną diagnostykę
1. Odtprodukuj problem
1. Przesyłanie [Centrum opinii](hololens-feedback.md) problemu
1. Udostępnianie adresu URL problemu z opinią
1. [Kontakt z pomocą techniczną](https://aka.ms/hololenssupport)

[Powrót do listy](#list)

## <a name="onedrive-uwp-app-doesnt-work-for-azure-ad-users"></a>OneDrive Aplikacja platformy uniwersalnej systemu Windows nie działa dla użytkowników usługi Azure AD

Jeśli używasz aplikacji OneDrive for Business przy użyciu konta usługi Azure AD, być może wystąpił błąd podczas logowania się do OneDrive odbiorczej. Nie można zalogować się do aplikacji OneDrive nie ma wpływu na automatyczne przekazywanie obrazów i wideo przechwyconych przez aplikację Aparatu. Nadal można zapisywać pliki i uzyskiwać do nich dostęp z OneDrive dla Firm magazynu w chmurze. Zespół OneDrive i HoloLens pracuje nad problemem.

### <a name="workarounds"></a>Obejścia

Wymaganie wstępne: klienci mogą korzystać Microsoft Edge i system operacyjny urządzenia jest Windows kompilacji Holographic, 21H1 lub nowszej.

Jeśli ten problem występuje, spróbuj wykonać jedną z następujących czynności:

- Użytkownicy mogą bezpośrednio uzyskać dostęp OneDrive do aplikacji Microsoft Edge i wchodzić w interakcje ze swoimi plikami w witrynie internetowej z przeglądarki.
- Użytkownicy mogą zainstalować aplikację OneDrive PWA, aby HoloLens, pobierając ją z Microsoft Edge. Umożliwi to użytkownikom wyświetlanie plików na urządzeniu i zarządzanie nimi ponownie. Przeczytaj i postępuj zgodnie z [tymi instrukcjami dotyczącymi instalowania OneDrive PWA aplikacji na HoloLens.](holographic-store-apps.md#install-microsoft-onedrive-pwa-app)

[Powrót do listy](#list)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Wideo remote assist zawiesza się po 20 minutach

> [!NOTE]
> Istnieje nowsza wersja usługi Remote Assist, która zawiera poprawkę dla tego problemu. Zaktualizuj [usługę Remote Assist](holographic-store-apps.md#update-apps) do najnowszej wersji, aby uniknąć tego problemu.

> [!NOTE]
> Ze względu na ważność tego znanego problemu tymczasowo wstrzymano dostępność systemu Windows Holographic w wersji 21H1. Kompilacja 21H1 jest teraz ponownie dostępna, więc urządzenia mogą zostać ponownie zaktualizowane do najnowszej kompilacji 21H1.

W najnowszej wersji systemu Windows Holographic w wersji [21H1](hololens-release-notes.md#windows-holographic-version-21h1)niektórzy użytkownicy usługi Remote Assist doświadczyli zamarzania wideo podczas wywołań przez ponad 20 minut. Jest to znany **problem.**

### <a name="workarounds"></a>Obejścia

Jeśli nie możesz zaktualizować usługi Remote Assist do nowszej kompilacji, spróbuj wykonać poniższe czynności.

#### <a name="restart-in-between-calls"></a>Uruchom ponownie między wywołaniami

Jeśli połączenia będą trwać ponad 20 minut i występuje ten problem, spróbuj ponownie uruchomić urządzenie. Ponowne uruchomienie urządzenia między wywołaniami usługi Remote Assist spowoduje odświeżenie urządzenia i ponowne jego ponowne uruchomienie.

Aby szybko ponownie uruchomić urządzenie na Windows Holographic, w wersji [21H1](hololens-release-notes.md#windows-holographic-version-21h1) otwórz menu Start i wybierz ikonę użytkownika, a następnie wybierz pozycję **Uruchom ponownie.**

[Powrót do listy](#list)

## <a name="auto-login-asks-for-log-in"></a>Automatyczne logowanie prosi o zalogowanie

Urządzenie HoloLens 2 można skonfigurować do automatycznego logowania się za pośrednictwem opcji logowania kont usługi **Ustawienia —**> i w obszarze Wymagane ustawienie wartości  ->    ->   Nigdy.   Niektórzy użytkownicy mogą wymagać zalogowania się na urządzeniu ponownie podczas aktualizowania urządzenia przy użyciu znacznie dużej aktualizacji, takiej jak aktualizacja funkcji. Jest to znany **problem.**

Przykład sytuacji, w których może się to zdarzyć:

- Aktualizowanie urządzenia z systemu Windows Holographic w wersji 2004 (kompilacja 19041.xxxx) do wersji Windows Holographic, wersja 21H1 (kompilacja 20346.xxxx)
- Aktualizowanie urządzenia w celu podjęcia dużej aktualizacji w tej samej kompilacji, np. Windows Holographic, wersja 2004 do wersji Windows Holographic, wersja 20H2
- Aktualizowanie urządzenia z obrazu fabryki do najnowszego obrazu

Nie powinno to mieć miejsca w trakcie:

- Urządzenia korzystające z comiesięcznej aktualizacji obsługi

Pomiń metody:

- Metody logowania, takie jak numer PIN, hasło, irys, uwierzytelnianie internetowe lub klucze FIDO2.
- Jeśli nie można zapamiętać numeru PIN urządzenia, a inne metody uwierzytelniania są niedostępne, użytkownik może użyć [trybu ręcznego reflashingu.](hololens-recovery.md#manual-procedure)

[Powrót do listy](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge nie można uruchomić

> [!NOTE]
> Ten problem został pierwotnie utworzony z myślą o wersji wysyłkowej Microsoft Edge o tym. Ten problem można rozwiązać w nowej [Microsoft Edge](hololens-new-edge.md). Jeśli tak nie jest, prosimy o opinię.

Kilku klientów zgłosiło problem, który Microsoft Edge nie można uruchomić. W przypadku tych klientów problem będzie nadal występował po ponownym uruchomieniu i nie zostanie rozwiązany Windows aktualizacji aplikacji. Jeśli ten problem występuje i Windows jest [aktualny,](hololens-updates.md#manually-check-for-updates)prosimy o zgłaszanie usterki z aplikacji Centrum opinii z następującą kategorią i podkategorią: Instalowanie i aktualizowanie programu > Pobieranie, instalowanie i konfigurowanie usługi [Windows](hololens-feedback.md) Update.

Nie ma znanych obejść, ponieważ do tej pory nie można było uzyskać głównej przyczyny problemu. Zgłoszenie usterki za pośrednictwem Centrum opinii pomoże w naszym badaniu! Jest to znany **problem.**

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
> Jest to znany **problem, który** został rozwiązany w Windows Holographic w wersji [21H1 — aktualizacja z lipca 2021 r.](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update).

W poprzednich kompilacjach Windows Holographic próba pobrania zablokowanego pliku byłaby stroną błędu HTTP. Na platformie Windows Holographic aktualizacja w wersji 21H1, próba pobrania zablokowanego pliku powoduje, że nic nie dzieje się widoczne — plik nie zostanie pobrana i nie wystąpi błąd.

[Powrót do listy](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Portal urządzeń umyka czas przekazywania/pobierania pliku
> [!NOTE]
> Jest to znany **problem, który** został rozwiązany w Windows Holographic w wersji [21H1 — aktualizacja z lipca 2021 r.](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update). Jeśli wcześniej wyłączono połączenie SSL w ramach obejścia problemu, zdecydowanie zalecamy jego ponowne włączenie.

Niektórzy klienci odkryli, że podczas próby przekazania lub pobrania plików operacja może się zawieszać, a następnie kończyć się lub nigdy nie kończyć. Jest to oddzielone[](#downloading-locked-files-doesnt-error) od znanego problemu "plik zablokowany" — dotyczy Windows Holographic w wersjach 2004, 20H2 i 21H1 w kompilacjach na rynku. Problem jest główny spowodowany usterką w obsłudze niektórych żądań przez Portal urządzeń i jest najczęściej trafiony w przypadku używania protokołu https, co jest ustawieniem domyślnym.

### <a name="workaround"></a>Obejście

To obejście, które ma zastosowanie w Wi-Fi i UsbNcm, polega na wyłączeniu opcji "wymagane" w obszarze "Połączenie SSL". W tym celu przejdź do Portal urządzeń **System** i wybierz stronę **Preferencje.** W sekcji **Zabezpieczenia urządzenia znajdź** opcję Połączenie **SSL** i usuń zaznaczenie pola wyboru, aby wyłączyć **opcję Wymagane.**

Następnie użytkownik powinien przejść do strony http://, a https:// (adres IP), a funkcje, takie jak przekazywanie i pobieranie plików, będą działać.

[Powrót do listy](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Niebieski ekran po wywrzeniu z wersji zapoznawczej niejawnego programu testów na urządzeniu z flashem kompilacji niejawnego testera

Jest to problem, który ma wpływ na użytkowników, którzy byli w kompilacji wersji zapoznawczej niejawnego testera, przekrzywilili swój program HoloLens 2 przy użyciu nowej kompilacji niejawnego programu w wersji zapoznawczej, a następnie nie są zarejestrowani w programie niejawnego testera. Jest to znany **problem.**

Nie ma to wpływu na:

- Użytkownicy, którzy nie są zarejestrowani w programie Windows Insider
- Wewnętrznych:
    - Jeśli urządzenie zostało zarejestrowane od kompilacji niejawnych testerów w wersji 18362.x
    - Jeśli flashował kompilację 19041.x podpisaną przez niejawnego testera I pozostał zarejestrowany w programie insider

Pomiń:

- Unikanie problemu
    - Flashuj kompilację nie niejawnego testera. Jedna z regularnych comiesięcznych aktualizacji.
    - Stay on Insider Preview
- Reflash urządzenia

    1. Ręcznie umieść [HoloLens 2](hololens-recovery.md) w trybie flashowania, w pełni przez całkowite zasilanie bez połączenia. Następnie przy przytrzymaniu przycisku Volume up naciśnij przycisk Zasilania.

    1. Połączenie na komputer i otwórz program Advanced Recovery Companion.

    1. Flashuj HoloLens 2 do domyślnej kompilacji.

[Powrót do listy](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive nie przekaże automatycznie obrazów

Aplikacja OneDrive dla aplikacji HoloLens nie obsługuje automatycznego przekazywania z aparatu dla kont służbowych. Jest to znany **problem.**

Obejścia:

- Jeśli jest to możliwe dla Twojej firmy, automatyczne przekazywanie z aparatu jest obsługiwane na kontach Microsoft konsumentów. Możesz zalogować się do konta konto Microsoft konta służbowego (aplikacja OneDrive obsługuje logowanie podwójne). W profilu konto Microsoft w OneDrive można włączyć automatyczne przekazywanie z aparatu w tle.

- Jeśli nie możesz bezpiecznie użyć konta konto Microsoft do automatycznego przekazywania zdjęć, możesz ręcznie przekazać zdjęcia na konto służbowe z aplikacji OneDrive aplikacji. W tym celu upewnij się, że zalogowano się do konta służbowego w OneDrive aplikacji. Wybierz przycisk **+** i wybierz pozycję **Upload**. Znajdź zdjęcia lub filmy wideo, które chcesz przekazać, przechodząc do > **Camera Roll**. Wybierz zdjęcia lub wideo, które chcesz przekazać, a następnie wybierz **przycisk** Otwórz.

[Powrót do listy](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens nie odpowiada lub nie można uruchomić

Jeśli nie HoloLens się uruchomić:

- Jeśli diody LED obok przycisku zasilania nie zaczną się oświetlać lub tylko jedna dioda LED miga krótko, może być konieczne [HoloLens.](hololens2-charging.md#charging-the-device)
- Jeśli dioda LED zabłyśnie po naciśnięciu przycisku zasilania, ale nie widzisz niczego na ekranach, wykonaj twarde [resetowanie urządzenia.](hololens-recovery.md#hard-reset-procedure)

Jeśli twój HoloLens jest zamrożony lub nie odpowiada:

- Wyłącz zasilanie HoloLens naciskając przycisk zasilania, aż wszystkie pięć diod LED wyłączy się lub przez 15 sekund, jeśli diody LED nie będą odpowiadać. Aby uruchomić HoloLens, naciśnij ponownie przycisk zasilania.

Jeśli te kroki nie działają, możesz spróbować odzyskać urządzenie [HoloLens 2](hololens-recovery.md) lub HoloLens [(1. generacji).](hololens1-recovery.md)

[Powrót do listy](#list)

## <a name="low-disk-space-error"></a>Błąd "Mała ilość miejsca na dysku"

Konieczne będzie wolne miejsce do magazynowania, wykonując co najmniej jedną z następujących czynności:

- Usuń niektóre nieużywane spacje. Przejdź do **Ustawienia**  >  **System**  >  **Spaces,** wybierz miejsce, które nie jest już **potrzebne,** a następnie wybierz pozycję Usuń .
- Usuń niektóre z umieszczonych hologramów.
- Usuń zdjęcia i filmy wideo z aplikacji Zdjęcia.
- Odinstaluj niektóre aplikacje z HoloLens. Na liście **Wszystkie aplikacje** naciśnij i przytrzymaj aplikację, którą chcesz odinstalować, a następnie wybierz pozycję **Odinstaluj.**

[Powrót do listy](#list)

## <a name="calibration-fails"></a>Niepowodzenie awarii

Większość osób powinna pracować, ale istnieją przypadki, w których nie powiodło się to.
  
Niektóre potencjalne przyczyny niepowodzenia awarii to:

- Rozpraszanie uwagi i niesąsiadowanie po docelowych celach
- Zanieczyszczona lub porysowana osłona urządzenia lub urządzenie nie jest prawidłowo pozycjonowane
- Zanieczyszczone lub porysowane okulary
- Niektóre typy obiektywów i okularów kontaktowych (kolorowe obiektywy kontaktowe, niektóre torysowe obiektywy kontaktowe, okulary blokujące ireń, niektóre okulary przeciwsłoneczne, okulary przeciwsłoneczne lub podobne)
- Bardziej wymawiane nagie i niektóre rozszerzenia ukośników
- Zarost lub grube ramki okularów, jeśli blokują one wzrok urządzenia
- Niektóre fizjologia, warunki oczu lub operacje oczu, takie jak wąskie oczy, długie ukośniki, amblyopia, nystagmus, niektóre przypadki lasik lub inne operacje oczu

Jeśli próba nie powiedzie się, spróbuj:

- Czyszczenie urządzenia
- Czyszczenie okularów
- Wypychanie wizjora urządzenia tak blisko oczu, jak to możliwe
- Przenoszenie obiektów w ośledla poza drogę (takich jak zarost)
- Włączanie światła w pomieszczeniu lub wyprowadzanie się z bezpośredniego światła

Jeśli wszystkie wytyczne i zalecenia nadal nie są stosowane, można wyłączyć monit o Ustawienia. Daj nam znać, składając opinię na stronie [Centrum opinii.](hololens-feedback.md)

Zobacz również powiązane informacje dotyczące [rozwiązywania problemów z kolorem obrazu lub jasność.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Ustawienie adresu IPD nie ma zastosowania HoloLens 2, ponieważ pozycje oka są obliczane przez system. 

[Powrót do listy](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Nie można się zalogować, ponieważ moja HoloLens wcześniej została ustawiona dla kogoś innego

Urządzenie można [przesłonić w tryb **flashowania i**](hololens-recovery.md#clean-reflash-the-device) użyć narzędzia Advanced Recovery Companion w celu odzyskania urządzenia.

[Powrót do listy](#list)


## <a name="unity-isnt-working"></a>Unity nie działa

- Zobacz [Install the tools for](/windows/mixed-reality/install-the-tools) the most-to-date version of Unity recommended for HoloLens development (Instalowanie narzędzi dla najbardziej aktualnej wersji aparatu Unity zalecanej do HoloLens aplikacji).
- Znane problemy z programem Unity HoloLens Technical Preview są udokumentowane na [forach HoloLens Unity.](https://forum.unity3d.com/threads/known-issues.394627/)

[Powrót do listy](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows Portal urządzeń nie działa prawidłowo

- Funkcja podglądu na żywo w Mixed Reality przechwytywania danych może mieć opóźnienie kilku sekund.

- Na stronie Wirtualne dane wejściowe kontrolki Gest i Przewijanie w sekcji Gesty wirtualne nie działają. Ich użycie nie będzie mieć żadnego efektu. Klawiatura wirtualna na stronie wirtualnych danych wejściowych działa poprawnie.

- Po włączeniu trybu dewelopera w Ustawienia Portal urządzeń może mieć kilka sekund, zanim przełącznik zostanie włączony.

[Powrót do listy](#list)

## <a name="the-hololens-emulator-isnt-working"></a>HoloLens Emulator nie działa

Informacje o emulatorze HoloLens znajdują się w naszej dokumentacji dla deweloperów.  Przeczytaj więcej na [temat rozwiązywania problemów z HoloLens emulatorem.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)


- Nie wszystkie aplikacje w Microsoft Store są zgodne z emulatorem. Na przykład w emulatorze nie można odtwarzać fragmentów Ani Younga Conkera.
- Nie można używać kamery internetowej komputera w Emulator.
- Funkcja podglądu na żywo Windows Portal urządzeń nie działa z emulatorem. Nadal można przechwytywać Mixed Reality wideo i obrazy.

[Powrót do listy](#list)

## <a name="voice-commands-arent-working"></a>Polecenia głosowe nie działają

Jeśli Cortana nie odpowiada na polecenia głosowe, upewnij się, że Cortana włączona. Na liście Wszystkie aplikacje wybierz **pozycję** Cortana  >  **Menu**  >  **Ustawienia,** aby wprowadzić  >   zmiany. Aby dowiedzieć się więcej na temat tego, co możesz powiedzieć, zobacz Używanie głosu [z HoloLens](hololens-cortana.md).

Na HoloLens (1. generacji) wbudowanej funkcji rozpoznawania mowy nie można skonfigurować. Jest ona zawsze włączona. Na HoloLens 2 możesz wybrać, czy podczas konfigurowania urządzenia włączyć zarówno rozpoznawanie mowy, jak i Cortana mowę.

Jeśli urządzenie HoloLens 2 nie odpowiada na Twój głos, upewnij się, że funkcja rozpoznawania mowy jest włączona. Przejdź do **tematu**  >  **Start Ustawienia**  >  **Privacy**  >  **Speech** i włącz rozpoznawanie **mowy.**

[Powrót do listy](#list)

## <a name="hand-input-isnt-working"></a>Ręczne wprowadzanie danych nie działa

Aby upewnić się HoloLens widać ręce, należy zachować je w ramce gestu.  Strona Mixed Reality Home udostępnia opinię, która informuje o tym, kiedy są śledzone twoje ręce.  Opinie są inne w różnych wersjach HoloLens:

- Na HoloLens (1. generacja) kursor spojrzenia zmienia się z kropki na pierścień
- Na HoloLens 2, gdy ręka jest blisko planszy, pojawia się kursor w zasięgu ręki, a promienia ręki, gdy plansze są dalej

Wiele aplikacji immersywnych ma wzorce wejściowe podobne do Mixed Reality Home.  Dowiedz się więcej na temat korzystania z danych wejściowych HoloLens [(1. generacja)](hololens1-basic-usage.md#use-hololens-with-your-hands) i HoloLens [2.](hololens2-basic-usage.md#the-hand-tracking-frame)

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

W **Ustawienia**  ->  **System**  ->  **Sound** jawnie ustaw wbudowane osoby mówiące **(sterownik audio** funkcji analogicznej) jako domyślne urządzenie . HoloLens zapamiętać to ustawienie, nawet jeśli mikrofon zostanie później usunięty i ponownie podłączony.

![Rozwiązywanie problemów z mikrofonami USB-C.](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Urządzenia wymienione jako dostępne w Ustawienia nie działają

HoloLens (1. generacja) nie obsługuje Bluetooth audio. Bluetooth audio, takie jak głośników i zestawy nagłowne, mogą być wyświetlane jako dostępne HoloLens ustawieniach, ale nie są obsługiwane.

HoloLens 2 obsługuje Bluetooth audio A2DP do odtwarzania stereo. Profil Bluetooth Hands Free, który umożliwia przechwytywanie mikrofonu z urządzenia peryferyjnego Bluetooth nie jest obsługiwany na HoloLens 2.

Jeśli masz problemy z używaniem urządzenia Bluetooth, upewnij się, że jest to obsługiwane urządzenie. Obsługiwane urządzenia są następujące:

- Język angielski QWERTY Bluetooth klawiatury (można ich używać wszędzie tam, gdzie używasz klawiatury holograficznej).
- Bluetooth myszy.
- Kliknij [HoloLens .](hololens1-clicker.md)

Inne urządzenia HID Bluetooth MOŻNA sparować z urządzeniami HID HoloLens. Może być jednak trzeba zainstalować odpowiednie aplikacje towarzyszące z Microsoft Store, aby w rzeczywistości korzystać z urządzeń.

[Powrót do listy](#list)
