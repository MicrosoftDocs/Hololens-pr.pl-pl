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
ms.openlocfilehash: a4949ab68121cb772fdb8a62411ed70868a6ccb6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924370"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider preview for Microsoft HoloLens

Witamy w najnowszych kompilacjach insider preview dla urządzenia HoloLens! Łatwo jest rozpocząć pracę [i przekazać](hololens-insider.md#start-receiving-insider-builds) cenną opinię na temat naszej kolejnej ważnej aktualizacji systemu operacyjnego dla urządzenia HoloLens.

## <a name="windows-insider-release-notes"></a>niejawny tester systemu Windows informacje o wersji

Z przyjemnością możemy ponownie zacząć testować nowe funkcje dla niejawnych testerów systemu Windows. Nowe kompilacje będą dostępne w kanałach Dev i Beta, aby uzyskać najnowsze aktualizacje. Będziemy nadal aktualizować tę stronę wraz z dodawaniem kolejnych funkcji i aktualizacji do naszych niejawny tester systemu Windows kompilacji. Przygotuj się do pomieszania tych aktualizacji ze swoją rzeczywistością. 

### <a name="csp-changes-on-hololens"></a>Zmiany WSP na urządzeniach HoloLens
 
- Wprowadzona w niejawny tester systemu Windows kompilacji, 20348.1403

#### <a name="devdetail-csp"></a>DevDetail CSP

DevDetail CSP now now also reports free storage space on HoloLens device . Powinno to być w przybliżeniu zgodne z wartością wyświetlaną na stronie Magazyn aplikacji ustawienia. Poniżej znajduje się konkretny węzeł zawierający te informacje.

- ./DevDetail/Ext/Microsoft/FreeStorage (tylko operacja GET)

#### <a name="devicestatus-csp"></a>DeviceStatus CSP

DeviceStatus CSP now also reports SSID and BSSID of Wifi network with which HoloLens is actively connected(DeviceStatus CSP now also reports SSID and BSSID of Wifi network with which HoloLens is actively connected) (DeviceStatus CSP now reports SSID and BSSID of Wifi network with which HoloLens is actively connected) (Device Poniżej przedstawiono konkretne węzły zawierające te informacje.

- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*adres mac* karty Wi-Fi /SSID
- ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*adres mac* karty Wi-Fi /BSSID

Przykład obiektu blob syncml (dla dostawców mdm) do wykonywania zapytań o identyfikatory sieci

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="fixes-and-improvements"></a>Poprawki i ulepszenia:

- Rozwiązano znany problem z Portal urządzeń w którym nie było [monitu o pobranie zablokowanych plików.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Rozwiązano [znany problem z Portal urządzeń podczas przekazywania i pobierania.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)

## <a name="start-receiving-insider-builds"></a>Rozpoczynanie odbierania kompilacji niejawnych testerów
> [!NOTE]
> Jeśli ostatnio nie zaktualizowano aplikacji, uruchom ponownie urządzenie, aby zaktualizować stan i pobrać najnowszą kompilację.
> - Polecenie głosowe "Reboot device" (Uruchom ponownie urządzenie) działa dobrze. 
> - Możesz również wybrać przycisk ponownego uruchamiania w ustawieniach/Niejawny program testów systemu Windows.
>
> Wystąpiła usterka w zakańcach, która może cię napotkać, co spowoduje powrót do śledzenia.

Na urządzeniu HoloLens 2 przejdź do opcji Ustawienia Zaktualizuj &  >  **Security**  >  **Niejawny program testów systemu Windows** wybierz pozycję **Wprowadzenie.** Połącz konto użyte do zarejestrowania się jako niejawny tester systemu Windows.
Niejawny program testów systemu Windows jest teraz przenoszący się do kanałów. Szybki **pierścień** stanie się kanałem dewelopera, pierścień Wolny stanie  się kanał beta, a pierścień wersji zapoznawczej zostanie  **kanałem wersji zapoznawczej.**   Oto jak wygląda to mapowanie: niejawny tester systemu Windows Kanały wyjaśnienia Aby uzyskać więcej informacji, zobacz ![ ](images/WindowsInsiderChannels.png) [Introducing niejawny tester systemu Windows Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) (Wprowadzenie do kanałów internetowych) na blogach dotyczących systemu Windows.
Następnie wybierz pozycję **Aktywny rozwój systemu Windows,** wybierz, czy  chcesz otrzymywać kanał **dewelopera,** czy tworzyć kanał beta kompilacje, i przejrzyj warunki programu.
Wybierz **pozycję > uruchom ponownie teraz,** aby zakończyć. Po ponownym uruchomieniu urządzenia przejdź do ustawień usługi **> Update & Security > Sprawdź** aktualizacje w celu uzyskania najnowszej kompilacji.
### <a name="update-error-0x80070490-work-around"></a>Błąd aktualizacji 0x80070490 pracy
Jeśli wystąpi błąd aktualizacji 0x80070490 podczas aktualizowania w kanale dewelopera lub wersji beta, spróbuj wykonać następujące krótkoterminowe czynności. Obejmuje to przeniesienie kanału niejawnego testera, pobranie aktualizacji, a następnie przeniesienie kanału niejawnego testera z powrotem.
#### <a name="stage-one---release-preview"></a>Etap pierwszy — wersja zapoznawcza
1.  Ustawienia, Zaktualizuj & zabezpieczeń, Niejawny program testów systemu Windows wybierz pozycję **Kanał wersji zapoznawczej.**
2.  Ustawienia, Zaktualizuj & zabezpieczeń, Windows Update, **Sprawdź aktualizacje.** Po aktualizacji przejdź do etapu 2.
#### <a name="stage-two---dev-channel"></a>Etap drugi — kanał dewelopera
1. Ustawienia, Zaktualizuj & zabezpieczeń, Niejawny program testów systemu Windows wybierz pozycję **Kanał deweloperów.**
2. Ustawienia, Zaktualizuj & zabezpieczeń, Windows Update, **Sprawdź aktualizacje.**
## <a name="ffu-download-and-flash-directions"></a>Wskazówki dotyczące pobierania i flasha ffu
Aby przetestować przy użyciu podpisanego lotu ffu, musisz najpierw odblokować urządzenie przed flashingiem podpisanego lotu ffu.
1. Na komputerze:
    1. Pobierz ffu na komputer ze strony [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Zainstaluj program ARC (Advanced Recovery Companion) z Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. Na urządzeniu HoloLens — Flight Unlock: otwórz pozycję **Ustawienia** Zaktualizuj &  >  **Security**  >  **Niejawny program testów systemu Windows** następnie zarejestruj się i uruchom ponownie urządzenie.
1. Flash FFU — teraz możesz flashowane ffu z podpisem lotu przy użyciu usługi ARC.
### <a name="provide-feedback-and-report-issues"></a>Zgłaszanie opinii i zgłaszanie problemów
Użyj aplikacji [Centrum opinii na](hololens-feedback.md) swoim urządzenia HoloLens, aby przekazać opinię i zgłosić problemy. Użycie Centrum opinii zapewnia, że wszystkie niezbędne informacje diagnostyczne są uwzględniane, aby pomóc naszym inżynierom szybko debugować i rozwiązywać problem.  Problemy z chińskiej i japońskiej wersji urządzenia HoloLens powinny być zgłaszane w ten sam sposób.
> [!NOTE]
> Pamiętaj, aby zaakceptować monit z pytaniem, Centrum opinii chcesz uzyskać dostęp  do folderu Dokumenty (po wyświetleniu monitu wybierz pozycję Tak).
## <a name="note-for-developers"></a>Uwaga dla deweloperów
Zachęcamy i zachęcamy do wypróbowania tworzenia aplikacji przy użyciu niejawnych kompilacji urządzenia HoloLens.  Zapoznaj się z [dokumentacją dla deweloperów urządzenia HoloLens,](https://developer.microsoft.com/windows/mixed-reality/development) aby rozpocząć pracę. Te same instrukcje działają z kompilacjami dla niejawnych testerów urządzenia HoloLens.  Możesz użyć tych samych kompilacji aparatu Unity i Visual Studio, których już używasz do kompilowania na urządzeniach HoloLens.
## <a name="stop-receiving-insider-builds"></a>Zatrzymywanie odbierania kompilacji niejawnych testerów
Jeśli nie chcesz już otrzymywać kompilacji systemu Windows Holographic dla niejawnych testerów, możesz zrezygnować [](hololens-recovery.md) z używania kompilacji produkcyjnej na urządzeniu HoloLens lub odzyskać urządzenie za pomocą zaawansowanego pomocnika odzyskiwania, aby odzyskać urządzenie do wersji systemu Windows Holographic innego niż niejawny program testów.
> [!CAUTION]
> Istnieje znany problem, w którym użytkownicy, którzy wyrejestrować się z kompilacji insider preview po ręcznej ponownej instalacji nowej kompilacji w wersji zapoznawczej, zobaczą niebieski ekran. Następnie muszą ręcznie odzyskać urządzenie. Aby uzyskać szczegółowe informacje na temat tego, czy problem może mieć wpływ, zobacz więcej informacji na temat tego [znanego problemu.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
Aby sprawdzić, czy na urządzeniach HoloLens jest uruchomiona kompilacja produkcyjna:
1. Przejdź do **> System > informacje** i znajdź numer kompilacji.
1. [Zobacz informacje o wersji, aby uzyskać numery kompilacji produkcyjnej.](hololens-release-notes.md)
Aby zrezygnować z kompilacji niejawnych testerów:
1. Na urządzeniach HoloLens z kompilacją produkcyjną przejdź do opcji Ustawienia > **Update & Security > Niejawny program testów systemu Windows** i wybierz pozycję Zatrzymaj kompilacje **niejawnych testerów.**
1. Postępuj zgodnie z instrukcjami, aby zrezygnować z urządzenia.
