---
title: Ponowne uruchamianie, resetowanie lub odzyskiwanie urządzenia HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: Jak za pomocą narzędzia Advanced Recovery Companion flashować obraz na urządzeniaCh HoloLens 2.
keywords: how-to, reboot, reset, recover, hard reset, soft reset, power cycle, HoloLens, shut down, arc, advanced recovery companion
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: be33eb5d06ee7d63f1f598792ff75605b0eb4424
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923639"
---
# <a name="restart-reset-or-recover-hololens-2"></a>Ponowne uruchamianie, resetowanie lub odzyskiwanie urządzenia HoloLens 2

>[!IMPORTANT]
> Przed rozpoczęciem procedury rozwiązywania problemów upewnij się, że urządzenie jest obciążane od **20 do 40%** pojemności baterii, jeśli jest to możliwe. Wskaźniki [naładowania baterii znajdujące](hololens2-setup.md#lights-that-indicate-the-battery-level) się pod przyciskiem zasilania to szybki sposób na sprawdzenie pojemności baterii bez logowania się do urządzenia.

Użyj [kabla USB typu C,](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) który jest podłączony do urządzenia HoloLens 2, ponieważ jest to najlepszy sposób ładowania urządzenia. Zasilacz dostarcza moc 18W (9V przy 2A). Korzystając z dostarczonego urządzenia HoloLens 2, urządzenie HoloLens 2 może ładować baterii do pełnej baterii w mniej niż 65 minut, gdy urządzenie jest w stanie wstrzymania. Jeśli te akcesoria nie są dostępne, upewnij się, że dostępne akcesoria mogą obsługiwać moc co najmniej 15 W.

> [!NOTE]
> Jeśli to możliwe, unikaj używania komputera do ładowania urządzenia za pośrednictwem portu USB, co działa wolno.

Jeśli urządzenie jest prawidłowo uruchomione, istnieją trzy sposoby sprawdzania poziomu naładowania baterii:

- Z menu głównego interfejsu użytkownika urządzenia HoloLens.
- Wyświetl diodę LED w pobliżu przycisku zasilania (w przypadku 40-procentowego obciążenia powinny być na przykład co najmniej dwie ciągłe diody LED).
    - Gdy urządzenie jest ładowane, wskaźnik baterii jest oświetlany, aby wskazać bieżący poziom naładowania.  Ostatnie światło będzie zanikać i zanikać, aby wskazać aktywne ładowanie.
    - Gdy urządzenie HoloLens jest wł., wskaźnik baterii wyświetla poziom naładowania baterii w pięciu przyrostach.
    - Gdy tylko jedno z pięciu światła jest w zasilania, poziom naładowania baterii jest poniżej 20 procent.
    - Jeśli poziom naładowania baterii jest krytycznie niski i spróbujesz włączyć urządzenie, jedno światło miga przez krótki czas, a następnie wychodzie.
- Na komputerze hosta otwórz **Eksplorator plików** i poszukaj urządzenia HoloLens 2 po lewej stronie w obszarze Ten **komputer.** Kliknij prawym przyciskiem myszy urządzenie, a następnie wybierz pozycję **Właściwości.** Zostanie wyświetlone okno dialogowe z poziomem naładowania baterii.

   ![Ekran właściwości urządzenia HoloLens 2 pokazuje poziom zmiany baterii](images/ResetRecovery2.png)

Jeśli urządzenie nie może uruchomić się w menu startowym, zwróć uwagę na wygląd diody LED i wyliczenie urządzenia na komputerze hosta. Następnie postępuj zgodnie z [przewodnikiem rozwiązywania problemów.](hololens-troubleshooting.md) Jeśli stan urządzenia nie pasuje do żadnego ze stanów wymienionych w przewodniku rozwiązywania problemów, wykonaj procedurę resetowania na czas z urządzeniem podłączonym do źródła zasilania, a nie z komputerem hosta. [](hololens-recovery.md#hard-reset-procedure) Zaczekaj co najmniej godzinę na obciążenie urządzenia.

## <a name="reset-the-device"></a>Resetowanie urządzenia

W pewnych okolicznościach może być trzeba ręcznie zresetować urządzenie bez korzystania z interfejsu użytkownika oprogramowania.

### <a name="standard-procedure"></a>Standardowa procedura

1. Odłącz kabel typu C, aby odłączyć urządzenie od zasilacza lub komputera hosta.

2. Naciśnij i przytrzymaj **przycisk zasilania** przez 15 sekund. Wszystkie diody LED powinny być wyłączone.

3. Poczekaj 2–3 sekundy, a następnie naciśnij krótko **przycisk** zasilania. Diody LED w pobliżu przycisku zasilania zostaną zasypne, a urządzenie zacznie się uruchamiać.

4. Podłącz urządzenie do komputera hosta, a następnie otwórz Menedżer urządzeń. (Aby Windows 10, naciśnij klawisz **systemu Windows,** a następnie **klawisz X,** a następnie wybierz **pozycję Menedżer urządzeń).** Upewnij się, że urządzenie jest prawidłowo wyliczane *Microsoft HoloLens* jak pokazano na poniższej ilustracji:

   ![HoloLens 2 MicrosoftLensRecovery devive manager](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a>Procedura resetowania na twardym dysku

Jeśli standardowa procedura resetowania nie zadziałała, użyj procedury resetowania na dysku twardym:

1. Odłącz kabel typu C, aby odłączyć urządzenie od zasilacza lub komputera hosta.

2. Przytrzymaj w dół **przyciski zasilania** głośności przez  +   15 sekund. Urządzenie zostanie automatycznie uruchomione ponownie.

4. Podłącz urządzenie do komputera hosta.

5. Otwórz Menedżer urządzeń (w Windows 10 naciśnij klawisz **systemu Windows,** a następnie **klawisz X,** a następnie wybierz pozycję **Menedżer urządzeń**). Upewnij się, że urządzenie jest prawidłowo wyliczane *Microsoft HoloLens* jak pokazano na poniższej ilustracji:

   ![Urządzenie HoloLens 2 MicrosoftKlensRecovery maanger 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a>Czyszczenie i reflash urządzenia

W wyjątkowych sytuacjach może być trzeba "oczyścić flash" urządzenia HoloLens 2. Należy pamiętać, że clean-reflash nie powinien mieć wpływu na następujące problemy:
- [Wyświetlanie jednolitego koloru](hololens2-display.md)
- Rozruch z dźwiękami, ale bez wyświetlania danych wyjściowych
- [Wzorzec 1-3-5-LED](hololens2-setup.md#lights-to-indicate-problems)
- [Przegrzanie](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- Awarie systemu operacyjnego (różniące się od awarii aplikacji)

Istnieją dwa sposoby reflash urządzenia. W obu przypadkach należy najpierw zainstalować program [Advanced Recovery Companion ze Sklepu Windows.](https://www.microsoft.com/store/productId/9P74Z35SFRS8)

>[!WARNING]
>W przypadku zmiany ukośnika urządzenia wszystkie dane osobowe, aplikacje i ustawienia zostaną usunięte, w tym informacje dotyczące resetowania modułu TPM.

Domyślnie opcja Pomocnik odzyskiwania zaawansowanego jest ustawiona na pobieranie najnowszej [](hololens-release-notes.md#) kompilacji wydania funkcji. Przeczytaj nasze informacje o wersji, aby dowiedzieć się więcej o najnowszej wersji funkcji. Aby uzyskać najnowszy pakiet Aktualizacji pełnej flash urządzenia HoloLens 2 (FFU) w celu reflashowania urządzenia za pomocą narzędzia Advanced Recovery Companion, kliknij tutaj, aby pobrać najnowszy obraz [urządzenia HoloLens 2 w miesiącu.](https://aka.ms/hololens2download) Jest to najnowsza ogólnie dostępna kompilacja.

Przed rozpoczęciem procedury reflash upewnij się, że aplikacja jest zainstalowana i uruchomiona na komputerze Windows 10 i jest gotowa do wykrywania urządzenia. Upewnij się również, że opłaty za urządzenie HoloLens są naliczane co najmniej 40%.

![Zrzut ekranu z czystym ukośnikiem holoLens 2](images/ARC1.png)

### <a name="normal-procedure"></a>Normalna procedura

1. Gdy urządzenie HoloLens jest uruchomione, połącz je z komputerem Windows 10, na którym wcześniej otwarto aplikację Advanced Recovery Companion.
 
   Urządzenie zostanie wykryte automatycznie, a interfejs użytkownika aplikacji pomocnika odzyskiwania zaawansowanego rozpocznie proces aktualizacji:

   ![Początkowy ekran czystego ukośnika HoloLens 2](images/ARC2.png)

3. Wybierz urządzenie HoloLens 2 w interfejsie użytkownika aplikacji Advanced Recovery Companion i postępuj zgodnie z instrukcjami, aby ukończyć reflash.

### <a name="manual-procedure"></a>Procedura ręczna

Jeśli urządzenie HoloLens 2 nie uruchamia się poprawnie lub jeśli program Advanced Recovery Companion nie może wykryć urządzenia, może być konieczne uruchomienie urządzenia w tryb odzyskiwania:

1. Odłącz kabel typu C, aby odłączyć urządzenie od zasilacza lub komputera hosta.

2. Naciśnij i przytrzymaj **przycisk zasilania** przez 15 sekund. Wszystkie diody LED powinny zostać wyłączone.

3. Naciskając przycisk **regulacji głośności,** naciśnij i zwolnij **przycisk** zasilania, aby uruchomić urządzenie. Poczekaj 15 sekund, a następnie zwolnij **przycisk regulacji głośności.** Tylko środkowa dioda LED pięciu diod LED będzie się oświetlać.

4. Podłącz urządzenie do komputera hosta i otwórz Menedżer urządzeń. (Aby Windows 10 naciśnij klawisz **systemu Windows,** a następnie **klawisz X,** a następnie wybierz **pozycję Menedżer urządzeń).** Upewnij się, że urządzenie jest prawidłowo wyliczane Microsoft HoloLens jak pokazano na poniższej ilustracji:

   ![HoloLens 2 MicrosoftLensRecovery](images/MicrosoftHoloLensRecovery.png)

   Urządzenie zostanie wykryte automatycznie, a interfejs użytkownika aplikacji pomocnika odzyskiwania zaawansowanego rozpocznie proces aktualizacji:

   ![Czysty ekran reflash urządzenia HoloLens 2](images/ARC2.png)

6. Wybierz urządzenie HoloLens 2 w interfejsie użytkownika aplikacji Advanced Recovery Companion, a następnie postępuj zgodnie z instrukcjami, aby ukończyć reflash.

## <a name="troubleshoot-advanced-recovery-companion"></a>Rozwiązywanie problemów z zaawansowaną pomocniką odzyskiwania

1. Przed próbą flashowania upewnij się, że opłata za urządzenie jest naliczana w wysokości co najmniej 40%.

2. Sprawdź, czy urządzenie jest odblokowane.

3. Jeśli usługa ARC nie wykryje urządzenia, upewnij się, że możesz nawiązać połączenie z urządzeniem za pośrednictwem Eksplorator plików na komputerze. Jeśli nie możesz;

    1.  Urządzenie może mieć zasady USB, które wyłączą to połączenie. Jeśli tak, spróbuj [użyć trybu ręcznego flashowania.](hololens-recovery.md#manual-procedure)
    2.  Jeśli nie ma żadnych zasad, wypróbuj inny kabel USB.

1. Sprawdź, czy na urządzeniu nie jest wyświetlany wzorzec [1–3-5-LED.](hololens2-setup.md#lights-to-indicate-problems)

## <a name="download-arc-without-using-the-app-store"></a>Pobieranie usługi ARC bez korzystania ze sklepu z aplikacjami

Jeśli środowisko IT uniemożliwia korzystanie z aplikacji ze Sklepu Windows lub ogranicza dostęp do sklepu detalicznego, administrator IT może udostępnić tę aplikację za pośrednictwem ścieżki wdrażania "w trybie offline".

 >[!NOTE]
 > - Administratorzy IT mogą również rozpowszechniać tę aplikację za pośrednictwem System Center Menedżer konfiguracji (SCCM) lub usługi Intune.
 > - Ten przewodnik koncentruje się na pomocniku odzyskiwania zaawansowanego, ale ten proces może być również używany w przypadku innych aplikacji "w trybie offline".

Wykonaj następujące kroki, aby włączyć ścieżkę wdrażania:

1. Przejdź do [Microsoft Store dla Firm](https://businessstore.microsoft.com) i zaloguj się przy użyciu Azure Active Directory tożsamości.

1. Przejdź do **zarządzaj — ustawienia**. Włącz wyświetlanie **aplikacji w trybie offline w** obszarze Środowisko **zakupów.**

1. Przejdź do **sklepu dla mojej grupy** i wyszukaj [**_pomocnika odzyskiwania zaawansowanego._**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)

1. Zmień typ **licencji na** **_offline_*_, a następnie wybierz pozycję _* Zarządzaj**.

1. W **obszarze Pobierz pakiet do użycia w trybie offline** wybierz drugi niebieski **przycisk** Pobierz. Upewnij się, że rozszerzeniem pliku *jest .appxbundle.*

    - Jeśli na tym etapie komputer stacjonarny ma dostęp do Internetu, kliknij dwukrotnie pakiet, aby zainstalować aplikację.

    - Jeśli komputer docelowy nie ma łączności z Internetem, wykonaj następujące kroki:
       1. Wybierz niezakodowana licencję, a następnie wybierz pozycję **Generuj licencję.**
       2. W **obszarze Wymagane struktury wybierz** pozycję **Pobierz**.
       3. Użyj funkcji DISM, aby zastosować pakiet z zależnością i licencją. W wierszu polecenia administratora uruchom następujące polecenie:

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > Numer wersji w tym przykładzie kodu może nie odpowiadać obecnie dostępnej wersji. Być może wybrano również inną lokalizację pobierania niż w przykładzie. W razie potrzeby należy wprowadzić zmiany w poleceniu.

> [!TIP]
> Jeśli planujesz użycie pomocnika odzyskiwania zaawansowanego w celu zainstalowania ffu w trybie offline, może być przydatne pobranie obrazu flash. [**Pobierz bieżący obraz dla urządzenia HoloLens 2.**](https://aka.ms/hololens2download)


Inne zasoby:
- [Dystrybuowanie aplikacji w trybie offline](/microsoft-store/distribute-offline-apps) 
- [Opcje wiersza polecenia obsługi pakietu aplikacji DISM (appx lub appxbundle)](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
