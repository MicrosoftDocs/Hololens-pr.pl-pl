---
title: Insider Preview for Microsoft HoloLens
description: Dowiedz się, jak rozpocząć pracę z kompilacjami niejawnych testerów i przekazać cenną opinię na temat naszej następnej ważnej aktualizacji systemu operacyjnego na HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 10/19/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 382c979138068ab1d9682ee4e84831accc9e4553
ms.sourcegitcommit: 73a1555fb8b84f3d20c480282c648d8d800a6c98
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/26/2021
ms.locfileid: "130351659"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview for Microsoft HoloLens

Witamy w najnowszych kompilacjach insider preview dla HoloLens! Łatwo jest rozpocząć pracę [i przekazać](hololens-insider.md#start-receiving-insider-builds) cenną opinię na temat naszej następnej ważnej aktualizacji systemu operacyjnego na HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Informacje o wersji dla niejawnych testerów

Co nowego i na horyzontach dla HoloLens? Zapoznaj się z tymi nowymi aktualizacjami, które wkrótce HoloLens!

### <a name="colorblind-mode"></a>Tryb bezbłędny

Dodano kompilację insidera 20348.1463

Tryb Colorblind jest przydatną świetną funkcją, która sprawia, że HoloLens bardziej dostępne. Nowy tryb colorblind można znaleźć w aplikacji Ustawienia w **obszarze** Ustawienia  ->  **Ułatwienia dostępu**  ->  **Color.** Dostępnych jest kilka nowych filtrów. Oto przykład wizualizacji niektórych dostępnych filtrów.

| Wyłączone | Skala szarości | Tritanopia |
|-----|-----------|------------|
| ![Wyłączanie filtrowania kolorów](images/colorblind-off.png)   | ![Filtr kolorów w skali szarej](images/colorblind-greyscale.png)         | ![Tritanopia filtru kolorów](images/colorblind-tritanopia.png)          |

### <a name="fixes-and-improvements"></a>Poprawki i ulepszenia

- Rozwiązano znany problem, który dotyczył sytuacji, w której za każdym razem, gdy zasilanie spada do [18%,](hololens-troubleshooting.md#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)urządzenie nagle wyłącza się automatycznie.
- Ulepszenia dotyczące przenoszenia trybu platformy podczas wykrywania kierunku w dół.
- Rozwiązano problem z oknami dialogowymi aktualizacji.
- Zaktualizowano skrzynkę odbiorczą Microsoft Edge wersji przeglądarki.
- Rozwiązano problem, który występował, gdy przełączanie opcjonalnych danych diagnostycznych nie utrwaliło wybranego ustawienia na stronie ustawień telemetrii po ponownym uruchomieniu.
- Rozwiązano problem, który oznaczał, że kody QR nie były rozpoznawane, gdy były obracane pod kątem 45 stopni względem urządzenia.

## <a name="start-receiving-insider-builds"></a>Rozpoczynanie odbierania kompilacji niejawnych testerów

> [!NOTE]
> Jeśli ostatnio nie była aktualizowana, uruchom ponownie urządzenie, aby zaktualizować stan i pobrać najnowszą kompilację.
>
> - Polecenie głosowe "Reboot device" (Uruchom ponownie urządzenie) działa dobrze.
> - Możesz również wybrać przycisk ponownego uruchamiania w Ustawienia/Windows niejawny program testów.
>
> Wystąpiła usterka w załocie, która może cię napotkać, co pozwoli ci wrócić do śledzenia.

Na urządzeniu HoloLens 2 przejdź do usługi **Ustawienia**  >  **Update & Security**  >  **Windows niejawny program testów** i wybierz **pozycję Wprowadzenie.** Połącz konto, które było używane do zarejestrowania się jako Windows Insider.

> [!NOTE]
> Aby zarejestrować urządzenie w kompilacjach niejawnych testerów, należy włączyć opcjonalną telemetrię. Jeśli jeszcze tego nie zrobiono, otwórz aplikację Ustawienia wybierz pozycję Diagnostyka prywatności i  ->  **&, a** następnie wybierz pozycję Opcjonalne **dane diagnostyczne.**

Windows niejawny program testów jest teraz przenoszący się do kanałów. Szybki **pierścień** stanie się kanałem **dewelopera,** pierścień Wolny stanie  się **kanał beta,** a pierścień wersji zapoznawczej będzie  **kanałem wersji zapoznawczej.** Oto jak wygląda to mapowanie:

![Windows Wyjaśnienie kanałów niejawnych testerów.](images/WindowsInsiderChannels.png)

Aby uzyskać więcej informacji, zobacz Introducing Windows Insider Channels (Wprowadzenie [do kanałów niejawnych testerów)](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) na Windows Blogi.
Następnie wybierz **pozycję Active development of Windows**, wybierz, czy chcesz otrzymywać kanał **dewelopera,** czy kanał beta kompilacje, i przejrzyj warunki programu. 
Wybierz **pozycję Potwierdź> uruchom ponownie teraz,** aby zakończyć. Po ponownym uruchomieniu urządzenia przejdź do Ustawienia > **Update & Security > Sprawdź** aktualizacje, aby pobrać najnowszą kompilację.

### <a name="update-error-0x80070490-work-around"></a>Błąd aktualizacji 0x80070490 pracy

Jeśli wystąpi błąd aktualizacji 0x80070490 podczas aktualizowania w kanale dewelopera lub wersji beta, spróbuj wykonać poniższe krótkoterminowe czynności. Obejmuje to przeniesienie kanału niejawnego testera, pobranie aktualizacji, a następnie przeniesienie kanału niejawnego testera z powrotem.

#### <a name="stage-one---release-preview"></a>Etap pierwszy — wersja zapoznawcza

1. Ustawienia, Zaktualizuj zabezpieczenia &, Windows niejawny program testów wybierz pozycję **Kanał wersji zapoznawczej.**

2. Ustawienia, Update & Security, Windows Update, **Check for updates**. Po aktualizacji przejdź do etapu 2.

#### <a name="stage-two---dev-channel"></a>Etap drugi — kanał dewelopera

1. Ustawienia, Zaktualizuj & Zabezpieczeń, Windows niejawny program testów pozycję **Kanał deweloperów.**

2. Ustawienia, Update & Security, Windows Update, **Check for updates**.

## <a name="ffu-download-and-flash-directions"></a>Wskazówki dotyczące pobierania i flasha z użyciem ffu

Aby przetestować przy użyciu podpisanego lotu ffu, musisz najpierw odblokować urządzenie przed flashingiem podpisanego lotu ffu.

1. Na komputerze:
    1. Pobierz ffu na komputer ze strony [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .

    1. Zainstaluj program ARC (Advanced Recovery Companion) z Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. Na HoloLens — Flight Unlock: **otwórz** Ustawienia Update & Security Windows niejawny program testów następnie zarejestruj  >    >   się i uruchom ponownie urządzenie.

1. Flash FFU — teraz możesz flashowane ffu z podpisem lotu przy użyciu usługi ARC.

### <a name="provide-feedback-and-report-issues"></a>Zgłaszanie opinii i zgłaszanie problemów

Użyj aplikacji [Centrum opinii aplikacji na](hololens-feedback.md) swoim HoloLens, aby przekazać opinię i zgłosić problemy. Użycie Centrum opinii gwarantuje, że wszystkie niezbędne informacje diagnostyczne będą uwzględniane, aby pomóc naszym inżynierom szybko debugować i rozwiązywać problem.  Problemy z chińskim i japońskim wersją HoloLens powinny być zgłaszane w ten sam sposób.

> [!NOTE]
> Pamiętaj, aby zaakceptować monit z pytaniem, czy chcesz Centrum opinii dostępu  do folderu Dokumenty (po wyświetleniu monitu wybierz pozycję Tak).

## <a name="note-for-developers"></a>Uwaga dla deweloperów

Zachęcamy i zachęcamy do wypróbowania tworzenia aplikacji przy użyciu kompilacji niejawnych testerów HoloLens.  Zapoznaj się z [dokumentacją HoloLens Developer,](https://developer.microsoft.com/windows/mixed-reality/development) aby rozpocząć pracę. Te same instrukcje działają z kompilacjami niejawnych testerów HoloLens.  Możesz użyć tych samych kompilacji aparatu Unity i Visual Studio, których już używasz do HoloLens tworzenia aplikacji.

## <a name="stop-receiving-insider-builds"></a>Zatrzymywanie odbierania kompilacji niejawnych testerów

Jeśli nie chcesz już otrzymywać kompilacji systemu Windows Holographic dla niejawnych testerów, możesz zrezygnować z używania kompilacji produkcyjnej na platformie HoloLens lub odzyskać urządzenie za pomocą narzędzia Advanced Recovery Companion, aby odzyskać urządzenie do wersji systemu Windows Holographic innego niż niejawny program testów. [](hololens-recovery.md)

> [!CAUTION]
> Istnieje znany problem, w którym użytkownicy, którzy wyrejestrować się z kompilacji insider preview po ręcznej ponownej instalacji nowej kompilacji w wersji zapoznawczej, zobaczą niebieski ekran. Następnie muszą ręcznie odzyskać urządzenie. Aby uzyskać szczegółowe informacje na temat tego, czy problem może mieć wpływ, zobacz więcej informacji na temat tego [znanego problemu.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Aby sprawdzić, czy HoloLens jest uruchomiona kompilacja produkcyjna:

1. Przejdź do **Ustawienia > System > informacje** i znajdź numer kompilacji.

1. [Zobacz informacje o wersji, aby uzyskać numery kompilacji produkcyjnej.](hololens-release-notes.md)

Aby zrezygnować z kompilacji niejawnych testerów:

1. W przypadku HoloLens kompilacji produkcyjnej przejdź do usługi **Ustawienia > Update & Security > Windows niejawny program testów** i wybierz pozycję Zatrzymaj kompilacje niejawnych **testerów.**

1. Postępuj zgodnie z instrukcjami, aby zrezygnować z urządzenia.
