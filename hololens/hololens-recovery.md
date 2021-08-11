---
title: Ponowne uruchamianie, resetowanie lub odzyskiwanie HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
description: How to use Advanced Recovery Companion to flash an image to HoloLens 2 (Jak używać pomocnika odzyskiwania zaawansowanego do flash HoloLens 2).
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
ms.openlocfilehash: 7d8f2f8bf6aaaeb7f6f0ddbd339d428dad9335faeb99bfca48a19e68929921ed
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662985"
---
# <a name="restart-reset-or-recover-hololens-2"></a>Ponowne uruchamianie, resetowanie lub odzyskiwanie HoloLens 2

>[!IMPORTANT]
> Przed rozpoczęciem procedury rozwiązywania problemów upewnij się, że urządzenie jest obciążane od **20 do 40%** pojemności baterii, jeśli jest to możliwe. Wskaźniki [naładowania baterii](hololens2-setup.md#lights-that-indicate-the-battery-level) znajdujące się pod przyciskiem zasilania to szybki sposób sprawdzenia pojemności baterii bez logowania się do urządzenia.

Użyj [kabla i kabla USB typu C,](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1) który jest HoloLens 2, ponieważ jest to najlepszy sposób ładowania urządzenia. Zasilacz dostarcza moc 18W (9V przy 2A). Przy użyciu dostarczonych ścianek HoloLens 2 urządzenia mogą ładować baterii do pełnej w mniej niż 65 minut, gdy urządzenie jest w stanie wstrzymania. Jeśli te akcesoria nie są dostępne, upewnij się, że dostępne akcesoria mogą obsługiwać moc co najmniej 15 W.

> [!NOTE]
> Jeśli to możliwe, unikaj używania komputera do ładowania urządzenia przez port USB, który działa wolno.

Jeśli urządzenie jest prawidłowo uruchomione, istnieją trzy sposoby sprawdzenia poziomu naładowania baterii:

- Z menu głównego interfejsu HoloLens użytkownika urządzenia.
- Wyświetl diodę LED w pobliżu przycisku zasilania (w przypadku 40-procentowego naładowania powinny być co najmniej dwie ciągłe diody LED).
    - Gdy urządzenie jest ładowane, wskaźnik naładowania baterii jest osłaniany, aby wskazać bieżący poziom naładowania.  Ostatnie światło zaniknie i będzie się pojawiać, aby wskazać aktywne opłaty.
    - Gdy urządzenie HoloLens, wskaźnik naładowania baterii wyświetla poziom naładowania baterii w pięciu przyrostach.
    - Gdy tylko jedno z pięciu światła jest wł., poziom naładowania baterii jest poniżej 20 procent.
    - Jeśli poziom naładowania baterii jest krytycznie niski i spróbujesz włączyć urządzenie, jedno światło miga przez krótki czas, a następnie wychodzie.
- Na komputerze hosta otwórz **Eksplorator plików** i poszukaj urządzenia z systemem HoloLens 2 po lewej stronie w obszarze Ten **komputer.** Kliknij prawym przyciskiem myszy urządzenie, a następnie wybierz pozycję **Właściwości.** Zostanie wyświetlone okno dialogowe z poziomem naładowania baterii.

   ![Ekran HoloLens 2 pokazuje poziom zmiany baterii](images/ResetRecovery2.png)

Jeśli urządzenie nie może uruchomić się z menu startowego, zwróć uwagę na wygląd diody LED i wyliczenie urządzenia na komputerze hosta. Następnie postępuj zgodnie z [przewodnikiem rozwiązywania problemów](hololens-troubleshooting.md). Jeśli stan urządzenia nie pasuje do żadnego ze stanów wymienionych w przewodniku rozwiązywania problemów, wykonaj procedurę resetowania na zawsze z urządzeniem podłączonym do zasilacza, a nie z komputerem hosta. [](hololens-recovery.md#hard-reset-procedure) Zaczekaj co najmniej godzinę na naliczanie opłat za urządzenie.

## <a name="reset-the-device"></a>Resetowanie urządzenia

W pewnych okolicznościach może być trzeba ręcznie zresetować urządzenie bez korzystania z programowego interfejsu użytkownika.

### <a name="standard-procedure"></a>Standardowa procedura

1. Odłącz kabel Typu C, aby odłączyć urządzenie od zasilacza lub komputera hosta.

2. Naciśnij i przytrzymaj **przycisk zasilania** przez 15 sekund. Wszystkie diody LED powinny być wyłączone.

3. Poczekaj 2–3 sekundy, a następnie naciśnij krótko **przycisk** zasilania. Diody LED w pobliżu przycisku zasilania zaczną się osłaniać, a urządzenie zacznie się uruchamiać.

4. Połączenie na komputerze hosta, a następnie otwórz Menedżer urządzeń. (Na Windows 10 naciśnij klawisz **Windows,** a następnie **klawisz X,** a następnie wybierz **Menedżer urządzeń**.) Upewnij się, że urządzenie wyliczy *Microsoft HoloLens,* jak pokazano na poniższej ilustracji:

   ![HoloLens 2 MicrosoftLensRecovery devive manager](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a>Procedura resetowania na twardym dysku

Jeśli standardowa procedura resetowania nie zadziałała, użyj procedury resetowania na czas:

1. Odłącz kabel Typu C, aby odłączyć urządzenie od zasilacza lub komputera hosta.

2. Przytrzymaj w dół **przyciski zasilania** głośności przez  +   15 sekund. Urządzenie zostanie automatycznie uruchomione ponownie.

4. Połączenie na komputerze hosta.


5. Otwórz Menedżer urządzeń (na Windows 10 naciśnij klawisz **Windows,** a następnie **klawisz X,** a następnie wybierz pozycję **Menedżer urządzeń**). Upewnij się, że urządzenie wyliczy *Microsoft HoloLens,* jak pokazano na poniższej ilustracji:

   ![HoloLens 2 MicrosoftLensRecovery device maanger 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a>Czyszczenie i reflash urządzenia

W wyjątkowych sytuacjach może być trzeba "oczyścić flash" HoloLens 2. Należy pamiętać, że czysty ukośnik nie powinien mieć wpływu na następujące problemy:
- [Wyświetlanie jednolitego koloru](hololens2-display.md)
- Rozruch z dźwięk, ale bez wyświetlania danych wyjściowych
- [Wzorzec 1-3-5-LED](hololens2-setup.md#lights-to-indicate-problems)
- [Przegrzanie](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- Awarie systemu operacyjnego (różniące się od awarii aplikacji)

Istnieją dwa sposoby reflashowania urządzenia. W obu przypadkach należy najpierw zainstalować [pakiet Advanced Recovery Companion ze sklepu Windows Store.](https://www.microsoft.com/store/productId/9P74Z35SFRS8)

>[!WARNING]
>W przypadku zmiany ukośnika urządzenia wszystkie dane osobowe, aplikacje i ustawienia, w tym informacje dotyczące resetowania modułu TPM, zostaną usunięte.

Domyślnie opcja Pomocnik odzyskiwania zaawansowanego jest ustawiona na pobieranie najnowszej [](hololens-release-notes.md#) kompilacji wydania funkcji. Przeczytaj informacje o wersji, aby dowiedzieć się więcej o najnowszej wersji funkcji. Aby uzyskać najnowszy pakiet HoloLens 2 Full Flash Update (FFU) w celu reflashowania urządzenia za pomocą narzędzia Advanced Recovery Companion, kliknij tutaj, aby pobrać najnowszy obraz z pakietu [HoloLens 2.](https://aka.ms/hololens2download) Jest to najnowsza ogólnie dostępna kompilacja.

Przed rozpoczęciem procedury reflash upewnij się, że aplikacja jest zainstalowana i uruchomiona na komputerze Windows 10 i jest gotowa do wykrywania urządzenia. Upewnij się również, HoloLens opłaty są naliczane co najmniej do 40%.

![HoloLens ekranu z 2 czystymi ukośnikiem odwrotnym](images/ARC1.png)

### <a name="normal-procedure"></a>Normalna procedura

1. Gdy urządzenie HoloLens, połącz je z komputerem Windows 10, na którym wcześniej otwarto aplikację Advanced Recovery Companion.
 
   Urządzenie zostanie wykryte automatycznie, a interfejs użytkownika aplikacji Advanced Recovery Companion rozpocznie proces aktualizacji:

   ![HoloLens ekranu początkowego czystego ukośnika odwrotnego](images/ARC2.png)

3. Wybierz urządzenie HoloLens 2 w interfejsie użytkownika aplikacji Pomocnik odzyskiwania zaawansowanego, a następnie postępuj zgodnie z instrukcjami, aby zakończyć reflash.

### <a name="manual-procedure"></a>Procedura ręczna

Jeśli urządzenie HoloLens 2 nie zostanie poprawnie skonfigurowane lub jeśli program Advanced Recovery Companion nie będzie mógł wykryć urządzenia, może być konieczne uruchomienie go w tryb odzyskiwania:

1. Odłącz kabel Typu C, aby odłączyć urządzenie od zasilacza lub komputera hosta.

2. Naciśnij i przytrzymaj **przycisk zasilania** przez 15 sekund. Wszystkie diody LED powinny zostać wyłączone.

3. Naciskając przycisk **regulacji głośności,** naciśnij i zwolnij **przycisk** zasilania, aby uruchomić urządzenie. Poczekaj 15 sekund, a następnie zwolnij **przycisk regulacji głośności.** Tylko środkowa dioda LED pięciu diod LED będzie się oświetlać.

4. Połączenie na komputerze hosta i otwórz Menedżer urządzeń. (Na Windows 10 naciśnij **klawisz Windows,** a następnie **klawisz X,** a następnie wybierz **Menedżer urządzeń**.) Upewnij się, że urządzenie wyliczy się poprawnie Microsoft HoloLens jak pokazano na poniższej ilustracji:

   ![HoloLens 2 MicrosoftLensRecovery](images/MicrosoftHoloLensRecovery.png)

   Urządzenie zostanie wykryte automatycznie, a interfejs użytkownika aplikacji Advanced Recovery Companion rozpocznie proces aktualizacji:

   ![HoloLens 2 czysty ekran reflash](images/ARC2.png)

6. Wybierz urządzenie HoloLens 2 w interfejsie użytkownika aplikacji Pomocnik odzyskiwania zaawansowanego, a następnie postępuj zgodnie z instrukcjami, aby zakończyć reflash.

## <a name="troubleshoot-advanced-recovery-companion"></a>Rozwiązywanie problemów z zaawansowaną pomocniką odzyskiwania

1. Przed próbą flashowania urządzenia upewnij się, że opłata za urządzenie jest naliczana do 40% lub więcej.

2. Sprawdź, czy urządzenie jest odblokowane.

1. Sprawdź, czy urządzenie jest podłączone bezpośrednio do komputera hosta, a nie koncentratora.

1. Jeśli urządzenie nie jest wyświetlane jako urządzenie HoloLens/HoloLens Recovery w obszarze Sterowniki uniwersalnej magistrali szeregowej, sprawdź:
    1. **Porty** jako urządzenie Typu Hs-USB
    1.   **Inne urządzenia** jako urządzenie QUSB_BULK — komputer hosta nie ma sterowników niezbędnych do wykrywania HoloLens. Kliknij prawym przyciskiem myszy i wybierz polecenie Aktualizuj sterownik i wyszukaj sterowniki w trybie online lub zaznacz pole wyboru Aktualizacje Windows [ustawienia aktualizacji.](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674) Po pobraniu sterownika usługa ARC powinna być w stanie go wykryć.
 
1. Jeśli usługa ARC nie wykryje urządzenia, upewnij się, że możesz nawiązać połączenie z urządzeniem za pośrednictwem Eksplorator plików na komputerze. Jeśli nie możesz;

    1.  Urządzenie może mieć zasady USB, które wyłączą to połączenie. Jeśli tak, spróbuj [użyć trybu ręcznego flashowania.](hololens-recovery.md#manual-procedure)
    2.  Jeśli nie ma żadnych zasad, wypróbuj inny kabel USB.

1. Sprawdź, czy na urządzeniu nie jest wyświetlany wzorzec [led 1-3-5.](hololens2-setup.md#lights-to-indicate-problems)

## <a name="download-arc-without-using-the-app-store"></a>Pobieranie usługi ARC bez korzystania ze sklepu z aplikacjami

Jeśli środowisko IT uniemożliwia korzystanie z aplikacji ze sklepu Windows Store lub ogranicza dostęp do sklepu detalicznego, administrator IT może udostępnić tę aplikację za pośrednictwem ścieżki wdrożenia "w trybie offline".

 >[!NOTE]
 > - Administratorzy IT mogą również rozpowszechniać tę aplikację za pośrednictwem System Center Configuration Manager (SCCM) lub usługi Intune.
 > - Ten przewodnik koncentruje się na pomocniku odzyskiwania zaawansowanego, ale ten proces może być również używany w przypadku innych aplikacji "w trybie offline".

Wykonaj następujące kroki, aby włączyć ścieżkę wdrażania:

1. Przejdź do [Microsoft Store dla Firm](https://businessstore.microsoft.com) i zaloguj się przy użyciu Azure Active Directory tożsamości.

1. Przejdź do **zarządzaj — Ustawienia**. Włącz wyświetlanie **aplikacji w trybie offline w** obszarze Środowisko **zakupów.**

1. Przejdź do **sklepu dla mojej grupy** i wyszukaj [**_pomocnika odzyskiwania zaawansowanego._**](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)

1. Zmień typ **licencji na** **_offline_*_, a następnie wybierz pozycję _ Zarządzaj***.

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
          > Numer wersji w tym przykładzie kodu może nie odpowiadać obecnie dostępnej wersji. Być może wybrano również inną lokalizację pobierania niż w przykładzie. W razie potrzeby wprowadzaj zmiany w poleceniu.

> [!TIP]
> Jeśli planujesz użycie pomocnika odzyskiwania zaawansowanego w celu zainstalowania ffu w trybie offline, może być przydatne pobranie obrazu flash. [**Pobierz bieżący obraz dla wersji HoloLens 2.**](https://aka.ms/hololens2download)


Inne zasoby:
- [Dystrybuowanie aplikacji w trybie offline](/microsoft-store/distribute-offline-apps) 
- [Opcje wiersza polecenia obsługi pakietu aplikacji DISM (appx lub appxbundle)](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
