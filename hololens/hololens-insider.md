---
title: Niejawna wersja zapoznawcza dla Microsoft HoloLens
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
ms.date: 10/12/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 080eb5949bc80d1ce922d57f099c375668f5633f
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924359"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Niejawna wersja zapoznawcza dla Microsoft HoloLens

Witamy w najnowszych kompilacjach insider preview dla HoloLens! Łatwo jest rozpocząć pracę [i przekazać](hololens-insider.md#start-receiving-insider-builds) cenną opinię na temat naszej następnej ważnej aktualizacji systemu operacyjnego na HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Informacje o wersji dla niejawnych testerów

Cieszymy się, że wszystkie nasze ostatnie funkcje niejawnych testerów zostały publicznie dostępne. Jeśli chcesz przeczytać o nich, zapoznaj się ze stroną informacji [o wersji](hololens-release-notes.md)

## <a name="start-receiving-insider-builds"></a>Rozpoczynanie otrzymywania kompilacji niejawnych testerów

> [!NOTE]
> Jeśli ostatnio nie zaktualizowano, uruchom ponownie urządzenie, aby zaktualizować stan i pobrać najnowszą kompilację.
>
> - Polecenie głosowe "Reboot device" (Uruchom ponownie urządzenie) działa dobrze.
> - Możesz również wybrać przycisk ponownego uruchamiania w Ustawienia/Windows niejawny program testów.
>
> Na zadurze wystąpiła usterka, która może spowodować powrót na tory.

Na urządzeniu HoloLens 2 przejdź do Ustawienia  >  **Update & Security**  >  **Windows niejawny program testów** i wybierz **pozycję Wprowadzenie.** Połącz konto użyte do zarejestrowania się jako Windows Insider.

> [!NOTE]
> Aby zarejestrować urządzenie w kompilacjach niejawnych testerów, należy włączyć opcjonalną telemetrię. Jeśli jeszcze tego nie zrobiono, otwórz aplikację Ustawienia wybierz pozycję Diagnostyka prywatności, aby &  ->  **opinii, a** następnie wybierz pozycję Opcjonalne dane **diagnostyczne.**

Windows niejawny tester jest teraz przenoszący się do kanałów. Szybki **pierścień** stanie się kanałem **dewelopera,** pierścień wolny stanie  się kanał beta **,** a pierścień wersji zapoznawczej stanie się kanałem wersji  **zapoznawczej.** Oto jak wygląda to mapowanie:

![Windows Wyjaśnienie kanałów niejawnych testerów.](images/WindowsInsiderChannels.png)

Aby uzyskać więcej informacji, zobacz Introducing Windows Insider Channels (Wprowadzenie do [kanałów niejawnych testerów)](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) Windows Blogi.
Następnie wybierz pozycję **Aktywne opracowywanie** Windows, wybierz, czy chcesz otrzymywać kanał **dewelopera,** czy kanał beta **kompilacje,** i przejrzyj warunki programu.
Wybierz **pozycję Potwierdź > uruchom ponownie teraz,** aby zakończyć. Po ponownym uruchomieniu urządzenia przejdź do tematu **Ustawienia > Update & Security > Check for updates** to get the latest build (Sprawdzanie aktualizacji w celu uzyskania najnowszej kompilacji).

### <a name="update-error-0x80070490-work-around"></a>Błąd aktualizacji 0x80070490 omięcie

Jeśli wystąpi błąd aktualizacji 0x80070490 podczas aktualizowania w kanale dewelopera lub wersji beta, spróbuj wykonać następujące krótkoterminowe czynności. Obejmuje to przeniesienie kanału dla niejawnych testerów, pobranie aktualizacji, a następnie przeniesienie kanału niejawnego testera z powrotem.

#### <a name="stage-one---release-preview"></a>Etap pierwszy — wersja zapoznawcza

1. Ustawienia, Zaktualizuj zabezpieczenia &, Windows niejawny program testów wybierz **pozycję Kanał wersji zapoznawczej wersji zapoznawczej.**

2. Ustawienia, Update & Security, Windows Update, Check **for updates**. Po aktualizacji przejdź do etapu 2.

#### <a name="stage-two---dev-channel"></a>Etap drugi — kanał dewelopera

1. Ustawienia zaktualizuj zabezpieczenia usługi &, Windows niejawny program testów pozycję Kanał **deweloperów.**

2. Ustawienia, Update & Security, Windows Update, Check **for updates**.

## <a name="ffu-download-and-flash-directions"></a>Wskazówki dotyczące pobierania i flasha ffu

Aby przetestować przy użyciu ffu z podpisem lotu, musisz najpierw odblokować urządzenie podczas lotu przed flashowanie locie podpisanego ffu.

1. Na komputerze:
    1. Pobierz ffu na komputer ze strony [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .

    1. Zainstaluj program ARC (pomocnik odzyskiwania zaawansowanego) z Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. Na HoloLens — Flight Unlock: **otwórz** Ustawienia  >  **Update & Security**  >  **Windows niejawny program testów** następnie zarejestruj się i uruchom ponownie urządzenie.

1. Flash FFU — teraz możesz flashowane ffu z podpisem lotu przy użyciu usługi ARC.

### <a name="provide-feedback-and-report-issues"></a>Opinie i zgłaszanie problemów

Użyj aplikacji [Centrum opinii aplikacji na](hololens-feedback.md) swoim HoloLens, aby przekazać opinię i zgłosić problemy. Użycie Centrum opinii zapewnia, że wszystkie niezbędne informacje diagnostyczne są uwzględniane, aby pomóc naszym inżynierom szybko debugować i rozwiązywać problem.  Problemy z chińskim i japońskim wersją HoloLens powinny być zgłaszane w ten sam sposób.

> [!NOTE]
> Pamiętaj, aby zaakceptować monit z pytaniem, czy chcesz Centrum opinii dostępu  do folderu Dokumenty (po wyświetleniu monitu wybierz pozycję Tak).

## <a name="note-for-developers"></a>Uwaga dla deweloperów

Zachęcamy i zachęcamy do wypróbowania tworzenia aplikacji przy użyciu kompilacji niejawnych testerów HoloLens.  Zapoznaj się z [HoloLens dla deweloperów,](https://developer.microsoft.com/windows/mixed-reality/development) aby rozpocząć pracę. Te same instrukcje działają z kompilacjami niejawnych testerów HoloLens.  Możesz użyć tych samych kompilacji aparatu Unity i Visual Studio, których już używasz do HoloLens kompilowania.

## <a name="stop-receiving-insider-builds"></a>Zatrzymywanie otrzymywania kompilacji niejawnych testerów

Jeśli nie chcesz już otrzymywać kompilacji systemu Windows Holographic dla niejawnych testerów, możesz zrezygnować z [](hololens-recovery.md) uruchamiania kompilacji produkcyjnej na platformie HoloLens lub odzyskać urządzenie przy użyciu zaawansowanego pomocnika odzyskiwania, aby odzyskać urządzenie do wersji systemu Windows Holographic innego niż niejawny program.

> [!CAUTION]
> Istnieje znany problem, w którym użytkownicy, którzy nie rejestrują się w kompilacjach insider preview po ręcznej ponownej instalacji nowej kompilacji w wersji zapoznawczej, będą mieli niebieski ekran. Następnie muszą ręcznie odzyskać urządzenie. Aby uzyskać szczegółowe informacje na temat tego problemu, zobacz więcej informacji na temat tego [znanego problemu.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Aby sprawdzić, czy HoloLens kompilacji produkcyjnej:

1. Przejdź do **Ustawienia > System > informacje** i znajdź numer kompilacji.

1. [Zobacz informacje o wersji dla numerów kompilacji produkcyjnych.](hololens-release-notes.md)

Aby zrezygnować z kompilacji niejawnych testerów:

1. Na stronie HoloLens kompilacji produkcyjnej przejdź do usługi **Ustawienia > Update & Security > Windows niejawny program testów** i wybierz pozycję Zatrzymaj kompilacje niejawnych **testerów.**

1. Postępuj zgodnie z instrukcjami, aby zrezygnować z urządzenia.
