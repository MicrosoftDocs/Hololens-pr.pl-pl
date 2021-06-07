---
title: Insider preview for Microsoft HoloLens
description: Dowiedz się, jak rozpocząć pracę z kompilacjami niejawnych testerów i przekazać cenną opinię na temat naszej kolejnej ważnej aktualizacji systemu operacyjnego dla urządzenia HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 8545b5f23dc81c194b68ea8b40feb83e525dfdf7
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378369"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider preview for Microsoft HoloLens

Witamy w najnowszych kompilacjach insider preview dla urządzenia HoloLens! Łatwo jest rozpocząć pracę [i przekazać](hololens-insider.md#start-receiving-insider-builds) cenną opinię na temat naszej kolejnej ważnej aktualizacji systemu operacyjnego dla urządzenia HoloLens.

## <a name="windows-insider-release-notes"></a>niejawny tester systemu Windows informacje o wersji

Z przyjemnością możemy ponownie zacząć testować nowe funkcje dla niejawnych testerów systemu Windows. Nowe kompilacje będą dostępne w kanałach Dev i Beta, aby uzyskać najnowsze aktualizacje. Będziemy nadal aktualizować tę stronę w przypadku dodawania kolejnych funkcji i aktualizacji do naszych niejawny tester systemu Windows kompilacji. Przygotuj się do pomieszania tych aktualizacji ze swoją rzeczywistością. 

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>Przekazywanie do aplikacji OneDrive dla służbowych aparatów fotograficznych

*Wprowadzono w kompilacji 20346.1402*

Dodaliśmy nową funkcję do aplikacji Ustawienia urządzenia HoloLens 2, która umożliwia klientom automatyczne przekazywanie zdjęć i wideo rzeczywistości mieszanej z folderu Pictures > Camera Roll urządzenia do odpowiedniego folderu usługi OneDrive dla służbowych. Ta funkcja rozwiązuje lukę w funkcjach w aplikacji [OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) na urządzeniach HoloLens 2, która obsługuje tylko automatyczne przekazywanie funkcji roll aparatu do osobistego konta konto Microsoft klienta (a nie konta służbowego).

**Jak to działa**

- Odwiedź stronę Settings > System > Mixed Reality Camera (Ustawienia **aparatu > Mixed Reality),** aby włączyć opcję "Przekazywanie z aparatu".
- Po ustawieniu tej  funkcji na pozycję Wł. wszystkie zdjęcia rzeczywistości mieszanej lub filmy wideo przechwycone na urządzeniu zostaną automatycznie umieszczone w kolejce do przekazania do folderu Pictures > Camera Roll na koncie służbowym usługi OneDrive.
    >[!NOTE]
    >Zdjęcia i wideo przechwycone  przed włączeniem tej funkcji nie będą kolejkowane do przekazania i nadal będą trzeba je przekazywać ręcznie.
- Na stronie Ustawienia zostanie wyświetlony komunikat o stanie z liczbą plików oczekujących na przekazanie (lub komunikatem "Usługa OneDrive jest aktualne" w przypadku przekazania wszystkich oczekujących plików).
- Jeśli martwisz się o przepustowość lub chcesz "wstrzymać" przekazywanie z dowolnej **przyczyny,** możesz przełączyć tę funkcję na pozycję Wyłączone. Tymczasowe wyłączenie tej funkcji gwarantuje, że kolejka przekazywania będzie się zwiększać w przypadku dodawania nowych plików do folderu roll aparatu, ale pliki nie zostaną przesłane do momentu ponownego włączenia tej funkcji.
- Najnowsze pliki zostaną najpierw przesłane (ostatni na w, pierwszy na zewnątrz).
- Jeśli twoje konto usługi OneDrive ma problemy (na  przykład po zmianie hasła), na stronie Ustawienia pojawi się przycisk Napraw teraz.
- Nie ma żadnego maksymalnego rozmiaru pliku, ale pamiętaj, że przekazywanie dużych plików będzie trwać dłużej (zwłaszcza jeśli przepustowość przekazywania jest ograniczona). Jeśli podczas przekazywania dużego pliku zostanie "wstrzymane" lub wyłączone przekazywanie, przekazywanie zostanie natychmiast anulowane. Przekazywanie zostanie uruchomione ponownie po ponownym włączeniu funkcji. Nie utracisz żadnych plików, ale częściowe przekazanie zostanie odrzucone.

**Znane problemy i zastrzeżenia**

- To ustawienie nie ma wbudowanego ograniczania przepustowości na podstawie bieżącego użycia przepustowości. Jeśli chcesz zmaksymalizować przepustowość w innym scenariuszu, wyłącz ustawienie ręcznie. Przekazywanie zostanie wstrzymane, ale funkcja będzie nadal monitorować nowo dodane pliki do funkcji rzutowania z aparatu. Włącz ponownie przekazywanie, gdy wszystko będzie gotowe do kontynuowania.
- Ta funkcja musi być włączona dla każdego konta użytkownika na urządzeniu i może aktywnie przekazywać pliki tylko dla użytkownika, który jest aktualnie zalogowany na urządzeniu.
- Jeśli zdjęcia lub filmy wideo są oglądane w czasie rzeczywistym na stronie Ustawienia, pamiętaj, że liczba oczekujących plików nie może ulec zmianie, dopóki bieżący plik nie zakończy przekazywania.
- Przekazywanie zostanie wstrzymane, jeśli urządzenie zostanie uśpione lub wyłączone. Aby upewnić się, że oczekujące przekazania zostaną ukończone, aktywnie używaj urządzenia do momentu, aż na stronie Ustawienia zostanie odczytany stan "OneDrive jest aktualny" lub dostosuj ustawienia usługi **Power & uśpienia.**

## <a name="start-receiving-insider-builds"></a>Rozpoczynanie odbierania kompilacji niejawnych testerów
> [!NOTE]
> Jeśli ostatnio nie była aktualizowana, uruchom ponownie urządzenie, aby zaktualizować stan i pobrać najnowszą kompilację.
> - Polecenie głosowe "Reboot device" (Uruchom ponownie urządzenie) działa dobrze. 
> - Możesz również wybrać przycisk ponownego uruchamiania w ustawieniach/Niejawny program testów systemu Windows.
>
> Wystąpiła usterka w zakańcach, która może cię napotkać, co spowoduje powrót do śledzenia.

Na urządzeniu HoloLens 2 przejdź do opcji Ustawienia Zaktualizuj &  >  **Security**  >  **Niejawny program testów systemu Windows** wybierz pozycję **Wprowadzenie.** Połącz konto użyte do zarejestrowania się jako niejawny tester systemu Windows.
Niejawny program testów systemu Windows jest teraz przenoszący do kanałów. Szybki **pierścień** stanie się kanałem **dewelopera,** pierścień Wolny stanie  się **kanał beta,** a pierścień wersji zapoznawczej zostanie kanałem wersji  **zapoznawczej.** Oto jak wygląda to mapowanie: niejawny tester systemu Windows Kanały wyjaśnienia Aby uzyskać więcej informacji, zobacz ![ ](images/WindowsInsiderChannels.png) [Introducing niejawny tester systemu Windows Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) (Wprowadzenie do kanałów internetowych) na blogach dotyczących systemu Windows.
Następnie wybierz pozycję **Aktywny rozwój systemu Windows,** wybierz, czy  chcesz otrzymywać kanał **dewelopera,** czy tworzyć kanał beta kompilacje, i przejrzyj warunki programu.
Wybierz **pozycję > uruchom ponownie teraz,** aby zakończyć. Po ponownym uruchomieniu urządzenia przejdź do tematu Ustawienia > **Update & Security > Sprawdź** aktualizacje w celu uzyskania najnowszej kompilacji.
### <a name="update-error-0x80070490-work-around"></a>Błąd aktualizacji 0x80070490 omięcie
Jeśli wystąpi błąd aktualizacji 0x80070490 podczas aktualizowania w kanale dewelopera lub wersji beta, spróbuj wykonać następujące krótkoterminowe czynności. Obejmuje to przeniesienie kanału niejawnego testera, pobranie aktualizacji, a następnie przeniesienie kanału niejawnego testera z powrotem.
#### <a name="stage-one---release-preview"></a>Etap pierwszy — wersja zapoznawcza
1.  Ustawienia, Zaktualizuj & zabezpieczeń, Niejawny program testów systemu Windows wybierz pozycję **Kanał wersji zapoznawczej.**
2.  Ustawienia, Zaktualizuj & zabezpieczeń, Windows Update, **Sprawdź aktualizacje.** Po aktualizacji przejdź do etapu 2.
#### <a name="stage-two---dev-channel"></a>Etap drugi — kanał dewelopera
1. Ustawienia, Zaktualizuj & zabezpieczeń, Niejawny program testów systemu Windows wybierz pozycję **Kanał deweloperów.**
2. Ustawienia, Zaktualizuj & zabezpieczeń, Windows Update, **Sprawdź aktualizacje.**
## <a name="ffu-download-and-flash-directions"></a>Wskazówki dotyczące pobierania i flasha z użyciem ffu
Aby przetestować przy użyciu podpisanego lotu ffu, musisz najpierw odblokować urządzenie przed flashingiem podpisanego lotu ffu.
1. Na komputerze:
    1. Pobierz ffu na komputer ze strony [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Zainstaluj program ARC (Advanced Recovery Companion) z Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. Na urządzeniu HoloLens — Flight Unlock: **otwórz** ustawienia Zaktualizuj &  >  **Security**  >  **Niejawny program testów systemu Windows** następnie zarejestruj się i uruchom ponownie urządzenie.
1. Flash FFU — teraz możesz flashowane ffu z podpisem lotu przy użyciu usługi ARC.
### <a name="provide-feedback-and-report-issues"></a>Zgłaszanie opinii i zgłaszanie problemów
Użyj aplikacji [Centrum opinii na](hololens-feedback.md) swoim urządzenia HoloLens, aby przekazać opinię i zgłosić problemy. Użycie Centrum opinii zapewnia, że wszystkie niezbędne informacje diagnostyczne są uwzględniane, aby pomóc naszym inżynierom szybko debugować i rozwiązywać problem.  Problemy z chińskiej i japońskiej wersji urządzenia HoloLens powinny być zgłaszane w ten sam sposób.
> [!NOTE]
> Pamiętaj, aby zaakceptować monit z pytaniem, czy chcesz uzyskać Centrum opinii  dostęp do folderu Dokumenty (po wyświetleniu monitu wybierz pozycję Tak).
## <a name="note-for-developers"></a>Uwaga dla deweloperów
Zachęcamy i zachęcamy do wypróbowania tworzenia aplikacji przy użyciu niejawnych kompilacji urządzenia HoloLens.  Zapoznaj się z [dokumentacją dla deweloperów urządzenia HoloLens,](https://developer.microsoft.com/windows/mixed-reality/development) aby rozpocząć pracę. Te same instrukcje działają z kompilacjami dla niejawnych testerów urządzenia HoloLens.  Możesz użyć tych samych kompilacji aparatu Unity i Visual Studio, których już używasz do kompilowania na urządzeniach HoloLens.
## <a name="stop-receiving-insider-builds"></a>Zatrzymywanie odbierania kompilacji niejawnych testerów
Jeśli nie chcesz już otrzymywać kompilacji systemu Windows Holographic dla niejawnych testerów, możesz zrezygnować [](hololens-recovery.md) z używania kompilacji produkcyjnej na urządzeniu HoloLens lub odzyskać urządzenie za pomocą zaawansowanego pomocnika odzyskiwania, aby odzyskać urządzenie do wersji systemu Windows Holographic innego niż niejawny program testów.
> [!CAUTION]
> Istnieje znany problem, w którym użytkownicy, którzy wyrejestrować się z kompilacji insider preview po ręcznej ponownej instalacji nowej kompilacji w wersji zapoznawczej, zobaczą niebieski ekran. Następnie muszą ręcznie odzyskać urządzenie. Aby uzyskać szczegółowe informacje na temat tego, czy problem może mieć wpływ, zobacz więcej informacji na temat tego [znanego problemu.](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)
Aby sprawdzić, czy na urządzeniach HoloLens jest uruchomiona kompilacja produkcyjna:
1. Przejdź do **> System > informacje** i znajdź numer kompilacji.
1. [Zobacz informacje o wersji, aby uzyskać numery kompilacji produkcyjnej.](hololens-release-notes.md)
Aby zrezygnować z kompilacji niejawnych testerów:
1. Na urządzeniach HoloLens z kompilacją produkcyjną przejdź do opcji Ustawienia > **Update & Security > Niejawny program testów systemu Windows** i wybierz pozycję Zatrzymaj kompilacje niejawnych **testerów.**
1. Postępuj zgodnie z instrukcjami, aby zrezygnować z urządzenia.
