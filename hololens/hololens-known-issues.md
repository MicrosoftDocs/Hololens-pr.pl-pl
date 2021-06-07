---
title: Znane problemy dotyczące urządzenia HoloLens
description: Bądź na bieżąco z naszą listą znanych problemów i obejść, które mogą mieć wpływ na klientów i deweloperów urządzenia HoloLens korzystających z aparatu Unity i Portal urządzeń z systemem Windows.
keywords: rozwiązywanie problemów, znany problem, pomoc
author: mattzmsft
ms.author: mazeller
ms.date: 11/30/2020
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
- HoloLens 2
ms.openlocfilehash: bc1d399a07a6a0622c953178cad7be1b8a018fdb
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378360"
---
# <a name="known-issues-for-hololens"></a>Znane problemy dotyczące urządzenia HoloLens

Oto bieżąca lista znanych problemów z urządzeniami HoloLens. Najpierw sprawdź tutaj, czy widzisz nietypowe zachowanie. Ta lista będzie aktualizowana w przypadku nowych problemów wykrytych lub zgłoszonych bądź gdy problemy zostaną rozwiązane w przyszłych aktualizacjach oprogramowania HoloLens.

>[!NOTE]
> - Jeśli odkryjesz problem, który nie blokuje, zgłoś go na urządzeniu HoloLens za pośrednictwem [Centrum opinii](hololens-feedback.md).
> - Jeśli problem, który występuje, blokuje Cię, oprócz zgłaszania opinii, prosimy [o zgłoszenie do pomocy technicznej.](https://aka.ms/hlsupport)

- [Znane problemy dla wszystkich generacji urządzenia HoloLens](#known-issues-for-all-hololens-generations)
- [Znane problemy dotyczące urządzeń HoloLens 2](#known-issues-for-hololens-2-devices)
- [Znane problemy dotyczące urządzenia HoloLens (1. generacji)](#known-issues-for-hololens-1st-gen)
- [Znane problemy dotyczące emulatora urządzenia HoloLens](#known-issues-for-hololens-emulator)

## <a name="known-issues-for-all-hololens-generations"></a>Znane problemy dla wszystkich generacji urządzenia HoloLens

### <a name="unity"></a>Unity

- Zobacz [Install the tools for](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) the most-to-date version of Unity recommended for HoloLens development (Instalowanie narzędzi dla najbardziej aktualnej wersji aparatu Unity zalecanej do instalowania na urządzeniach HoloLens).
- Znane problemy z urządzeniem Unity HoloLens Technical Preview zostały udokumentowane na [forach aparatu Unity dla urządzenia HoloLens.](https://forum.unity3d.com/threads/known-issues.394627/)

### <a name="windows-device-portal"></a>Portal urządzeń z systemem Windows

- Funkcja podglądu na żywo w Mixed Reality przechwytywania danych może mieć kilka sekund opóźnienia.

- Na stronie Wirtualne dane wejściowe kontrolki Gest i Przewiń w sekcji Gesty wirtualne nie działają. Ich użycie nie będzie mieć żadnego efektu. Klawiatura wirtualna na wirtualnej stronie wejściowej działa poprawnie.

- Po włączeniu trybu dewelopera w ustawieniach może mieć kilka sekund, zanim przełącznik włączy Portal urządzeń włączony.

### <a name="onedrive-camera-upload"></a>Przekazywanie aparatu w usłudze OneDrive

Aplikacja OneDrive dla urządzenia HoloLens nie obsługuje automatycznego przekazywania z aparatu dla kont służbowych.

Obejścia:

- Jeśli jest to możliwe dla Twojej firmy, automatyczne przekazywanie z aparatu jest obsługiwane na kontach Microsoft konsumentów. Możesz zalogować się do konta konto Microsoft konta służbowego (aplikacja OneDrive obsługuje logowanie podwójne). Z poziomu konto Microsoft w usłudze OneDrive możesz włączyć automatyczne przekazywanie z aparatu w tle.

- Jeśli nie możesz bezpiecznie użyć konta konto Microsoft do automatycznego przekazywania zdjęć, możesz ręcznie przekazać zdjęcia na konto służbowe z aplikacji OneDrive. W tym celu upewnij się, że zalogowano się do konta służbowego w aplikacji OneDrive. Wybierz przycisk **+** i wybierz pozycję **Przekaż.** Znajdź zdjęcia lub filmy wideo, które chcesz przekazać, przechodząc do > **Camera Roll**. Wybierz zdjęcia lub wideo, które chcesz przekazać, a następnie wybierz **przycisk** Otwórz.

## <a name="known-issues-for-hololens-2-devices"></a>Znane problemy dotyczące urządzeń HoloLens 2

### <a name="device-using-auto-login-asks-for-log-in"></a>Urządzenie korzystające z automatycznego logowania prosi o zalogowanie

Urządzenie HoloLens 2 można skonfigurować do automatycznego logowania się za pośrednictwem opcji logowania konta ustawień > i w obszarze Wymagane ustawienie wartości  ->    ->   **Nigdy.**  Niektórzy użytkownicy mogą być zobowiązani do zalogowania się na urządzeniu ponownie podczas aktualizowania urządzenia przy użyciu znacznie dużej aktualizacji, takiej jak aktualizacja funkcji.

Przykład sytuacji, w których może się to zdarzyć:

- Aktualizowanie urządzenia z systemu Windows Holographic w wersji 2004 (kompilacja 19041.xxxx) do systemu Windows Holographic w wersji 21H1 (kompilacja 20346.xxxx)
- Aktualizowanie urządzenia w celu podjęcia dużej aktualizacji w tej samej kompilacji, np. Windows Holographic, wersja 2004 do systemu Windows Holographic, wersja 20H2
- Aktualizowanie urządzenia z obrazu fabrycznego do najnowszego obrazu

Nie powinno to mieć miejsca w trakcie:

- Urządzenia korzystające z comiesięcznej aktualizacji obsługi

Omiń metody:

- Metody logowania, takie jak numer PIN, hasło, irysy, uwierzytelnianie internetowe lub klucze FIDO2.
- Jeśli nie można zapamiętać numeru PIN urządzenia i inne metody uwierzytelniania są niedostępne, użytkownik może użyć [ręcznego trybu reflashingu.](hololens-recovery.md#manual-procedure)

### <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge nie można uruchomić

> [!NOTE]
> Ten problem został pierwotnie utworzony z myślą o wersji wysyłkowej Microsoft Edge o tym. Ten problem można rozwiązać w nowej [Microsoft Edge](hololens-new-edge.md). Jeśli tak nie jest, prosimy o opinię.

Kilku klientów zgłosiło problem, który Microsoft Edge nie można uruchomić. W przypadku tych klientów problem będzie nadal występował po ponownym uruchomieniu i nie zostanie rozwiązany za pomocą aktualizacji systemu Windows ani aplikacji. Jeśli ten problem występuje i wiesz, że system [Windows](hololens-updates.md#manually-check-for-updates)jest aktualny, prosimy o zgłaszanie usterki z aplikacji [Centrum opinii](hololens-feedback.md) z następującą kategorią i podkategorią: Instalowanie i aktualizowanie usługi > Pobieranie, instalowanie i konfigurowanie Windows Update.

Nie ma znanych obejść, ponieważ do tej pory nie można było głównej przyczyny problemu. Zgłoszenie usterki za pośrednictwem Centrum opinii pomoże w naszym badaniu!

### <a name="keyboard-does-not-switch-to-special-characters"></a>Klawiatura nie przełącza się na znaki specjalne

Podczas OOBE występuje problem, który występuje, gdy użytkownik wybrał konto służbowe i wprowadza hasło, próbując przełączyć się na znaki specjalne na klawiaturze, naciskając przycisk &123, nie zmienia się na znaki specjalne.

Omiń:
-   Zamknij klawiaturę i otwórz ją ponownie, naciskając pole tekstowe.
-   Niepoprawnie wprowadź hasło. Gdy klawiatura zostanie ponownie wyzjęte przy następnym czasie, będzie działać zgodnie z oczekiwaniami.
- Uwierzytelnianie internetowe, zamknij klawiaturę i wybierz **pozycję Zaloguj się z innego urządzenia.**
-   Jeśli wprowadzasz tylko liczby, użytkownik może nacisnąć i przytrzymać niektóre klawisze, aby otworzyć rozwinięte menu.
-   Za pomocą klawiatury USB.

Nie ma to wpływu na:
- Użytkownicy, którzy wybiorą opcję korzystania z konta osobistego.

### <a name="blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-an-insider-build"></a>Niebieski ekran jest wyświetlany po wywrzeniu kompilacji niejawnego programu testów w wersji zapoznawczej na urządzeniu z reflashed za pomocą kompilacji niejawnego testera

Jest to problem, który ma wpływ na użytkowników, którzy byli w kompilacji w wersji zapoznawczej niejawnego testera, przekrzywilili swoje urządzenia HoloLens 2 przy użyciu nowej kompilacji insider preview, a następnie nie zakodują się w programie Insider.

Nie ma to wpływu na:
- Użytkownicy, którzy nie są zarejestrowani w niejawny tester systemu Windows 
- Wewnętrznych:
    - Jeśli urządzenie zostało zarejestrowane od kompilacji niejawnych testerów w wersji 18362.x
    - Jeśli program flashował kompilację 19041.x podpisaną przez niejawnego testera i pozostał zarejestrowany w programie insider

Pomiń: 
- Unikanie problemu 
    - Flashuj kompilację nie niejawnego testera. Jedna z regularnych comiesięcznych aktualizacji.
    - Stay on Insider Preview
- Reflash urządzenia

    1. Ręcznie przełączyć [urządzenie HoloLens 2](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) w tryb flashowania, w pełni włączyć zasilanie, ale nie nawiązać połączenia. Następnie przy przytrzymaniu przycisku Regulacji głośności naciśnij przycisk Zasilania.
    
    1. Połącz się z komputerem i otwórz program Advanced Recovery Companion.
    
    1. Flashuj urządzenie HoloLens 2 do kompilacji domyślnej.

## <a name="known-issues-for-hololens-1st-gen"></a>Znane problemy dotyczące urządzenia HoloLens (1. generacji)

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Nie można nawiązać połączenia i wdrożyć na urządzeniach HoloLens za pośrednictwem Visual Studio

> [!NOTE]
> Ostatnia aktualizacja: 8/8 o 17:11 — program Visual Studio opublikował program VS 2019 w wersji 16.2, który zawiera poprawkę do tego problemu. Zalecamy aktualizację do najnowszej wersji, aby uniknąć wystąpienia tego błędu.

Visual Studio program VS 2019 w wersji 16.2, który zawiera poprawkę tego problemu. Zalecamy aktualizację do najnowszej wersji, aby uniknąć wystąpienia tego błędu.

Główna przyczyna problemu: Dotyczy to użytkowników, którzy używali programu Visual Studio 2015 lub wczesnej wersji programu Visual Studio 2017 do wdrażania i debugowania aplikacji na urządzeniach HoloLens, a następnie używali najnowszych wersji programu Visual Studio 2017 lub Visual Studio 2019 z tym samym urządzeniem HoloLens. Nowsze wersje programu Visual Studio nową wersję składnika, ale pliki ze starszej wersji są pozostawiane na urządzeniu, co powoduje niepowodzenie nowszej wersji.  Powoduje to następujący komunikat o błędzie: DEP0100: Upewnij się, że urządzenie docelowe ma włączony tryb dewelopera. Nie można uzyskać licencji dewelopera z \<ip\> powodu błędu 80004005.

#### <a name="workaround"></a>Obejście

Nasz zespół obecnie pracuje nad poprawek. W międzyczasie możesz wykonać następujące kroki, aby ominąć problem i ułatwić odblokowanie wdrażania i debugowania:  

1. Otwórz program Visual Studio.

1. Wybierz **pozycję File** New Project  >  **(Plik nowego**  >  **projektu).**

1. Wybierz **pozycję Visual C#**  >  **Windows Desktop** Console App  >  **(.NET Framework)**.

1. Nadaj projektowi nazwę (na przykład "HoloLensDeploymentFix") i upewnij się, że dla struktury ustawiono co najmniej jedną .NET Framework 4.5, a następnie wybierz przycisk **OK.**

1. Kliknij prawym przyciskiem myszy węzeł **Odwołania** w Eksplorator rozwiązań i dodaj następujące odwołania (wybierz **sekcję** Przeglądaj i wybierz pozycję **Przeglądaj):**

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Jeśli nie masz zainstalowanej wersji 10.0.18362.0, użyj najnowszej posiadanej wersji. 

1. Kliknij prawym przyciskiem myszy projekt na stronie Eksplorator rozwiązań wybierz **pozycję Dodaj**  >  **istniejący element**.

1. Przejdź do katalogu C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 i zmień filtr na **Wszystkie pliki ( . \* \* )**.

1. Wybierz obie SirepClient.dll i SshClient.dll, a następnie wybierz **pozycję Dodaj.**

1. Znajdź i wybierz oba pliki w Eksplorator rozwiązań (powinny znajdować się u dołu  listy plików),  a następnie zmień opcję Kopiuj do katalogu wyjściowego w oknie Właściwości na Kopiuj **zawsze**.

1. W górnej części pliku dodaj następujący kod do istniejącej listy `using` instrukcji :

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. W `static void Main(...)` dodatku dodaj następujący kod:

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. Wybierz **pozycję Build** Build Solution  >  **(Skompilowanie rozwiązania kompilacji).**

1. Otwórz okno wiersza polecenia i otwórz folder cd do folderu zawierającego skompilowany plik .exe (na przykład C:\MyProjects\HoloLensDeploymentFix\bin\Debug).

1. Uruchom plik wykonywalny i podaj adres IP urządzenia jako argument wiersza polecenia. (W przypadku połączenia przy użyciu portu USB możesz użyć adresu 127.0.0.1. W przeciwnym razie użyj adresu IP Wi-Fi urządzenia).  Na przykład "HoloLensDeploymentFix 127.0.0.1".

1. Po zakończeniu działania narzędzia bez żadnych komunikatów (powinno to potrwać tylko kilka sekund), będzie można wdrażać i debugować z programu Visual Studio 2017 lub nowszego.  Dalsze korzystanie z narzędzia nie jest konieczne.

Będziemy dostarczać dalsze aktualizacje, gdy staną się dostępne.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>Problemy z uruchamianiem aplikacji Microsoft Store na urządzeniach HoloLens

> [!NOTE]
> Ostatnia aktualizacja: 4/2 o 10:00 — problem rozwiązany.

Podczas próby uruchomienia aplikacji i aplikacji na Microsoft Store HoloLens mogą wystąpić problemy. Ustaliliśmy, że problem występuje, gdy aktualizacje aplikacji w tle wdrażają nowszą wersję pakietów struktury w określonych sekwencjach, podczas gdy co najmniej jedna z aplikacji zależnych nadal działa. W takim przypadku automatyczna aktualizacja aplikacji dostarczała nową wersję programu .NET Native Framework (od 10.0.25531 do 10.0.27413) spowodowała, że uruchomione aplikacje nie były poprawnie aktualizowane dla wszystkich uruchomionych aplikacji, które zużywają poprzednią wersję struktury.  Przepływ aktualizacji struktury jest następujący:

1. Nowy pakiet struktury jest pobierany ze sklepu i instalowany.

1. Wszystkie aplikacje użyciu starszej struktury są "aktualizowane" w celu używania nowszej wersji.

Jeśli krok 2 zostanie przerwany przed ukończeniem, uruchomienie wszystkich aplikacji, dla których nie zarejestrowano nowszej struktury, z menu Start zakończy się niepowodzeniem.  Uważamy, że ten problem może mieć wpływ na dowolną aplikację na urządzeniach HoloLens.

Niektórzy użytkownicy zgłaszali, że zamknięcie zawieszonych aplikacji i uruchomienie innych aplikacji, takich jak Centrum opinii, Przeglądarka 3D lub Zdjęcia, rozwiązuje problem dla nich — jednak nie działa to przez 100% czasu.

Główną przyczyną tego problemu nie była sama aktualizacja, ale usterka systemu operacyjnego, która powodowała nieprawidłową obsługę aktualizacji struktury .NET Native. Z zadowoleniem ogłaszamy, że zidentyfikowano poprawkę i wydaliśmy aktualizację (system operacyjny w wersji 17763.380) zawierającą poprawkę.  

Aby sprawdzić, czy urządzenie może podjąć aktualizację:

1. Przejdź do aplikacji Ustawienia i otwórz program **Update & Security.**

1. Wybierz **pozycję Sprawdź aktualizacje.**

1. Jeśli jest dostępna aktualizacja do wersji 17763.380, zaktualizuj tę kompilację, aby otrzymać poprawkę dla błędu zawieszania się aplikacji.

1. Po zaktualizowaniu do tej wersji systemu operacyjnego aplikacje powinny działać zgodnie z oczekiwaniami.

Ponadto, podobnie jak w przypadku każdej wersji systemu operacyjnego HoloLens, obraz FFU został opublikowany w [Centrum pobierania Microsoft.](https://aka.ms/hololensdownload/10.0.17763.380)

Jeśli nie chcesz przyjmować aktualizacji, 3/29 wydaliśmy nową wersję aplikacji platformy Microsoft Store platformy uniwersalnej systemu Windows. Po zaktualizowaniu wersji sklepu:

1. Otwórz magazyn i upewnij się, że jest ładowany.
1. Użyj gestu Blooma, aby otworzyć menu.
1. Spróbuj otworzyć wcześniej uszkodzone aplikacje.
1. Jeśli nadal nie można go uruchomić, naciśnij i przytrzymaj ikonę uszkodzonej aplikacji, a następnie wybierz pozycję Odinstaluj.
1. Zainstaluj ponownie te aplikacje ze sklepu.

Jeśli urządzenie nadal nie może ładować aplikacji, możesz załadować bezpośrednio wersję programu .NET Native Framework i środowiska uruchomieniowego za pośrednictwem Centrum pobierania, wykonać następujące czynności:

1. Pobierz ten [plik zip](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) z Centrum pobierania Microsoft. Rozpakowanie spowoduje skomplikowanie dwóch plików.  Microsoft .NET.Native.Runtime.1.7.appx i Microsoft .NET.Native.Framework.1.7.appx.

1. Sprawdź, czy twoje urządzenie zostało odblokowane.  Jeśli nie zostało to jeszcze zrobione, zobacz [Using the Portal urządzeń z systemem Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) (Używanie Portal urządzeń z systemem Windows, aby uzyskać instrukcje.

1. Następnie chcesz uzyskać dostęp do Portal urządzeń z systemem Windows. Zaleca się, aby to zrobić za pośrednictwem portu USB, wpisując http://127.0.0.1:10080 je w przeglądarce.

1. Po zakończeniu Portal urządzeń z systemem Windows musimy "załadować bezpośrednio" dwa pobrane pliki. W tym celu należy przejść w dół na lewym pasku bocznym, aż do sekcji Aplikacje **i** wybrać pozycję **Aplikacje.**

1. Zostanie wyświetlony ekran podobny do poniższego.  Chcesz przejść do sekcji Instalowanie  aplikacji i przejść do miejsca, w którym zostały rozpakowane te dwa pliki APPX. Można to zrobić tylko jeden raz na raz, więc po wybraniu pierwszej z nich kliknij pozycję "Przejdź" w sekcji Wdrażanie. Następnie zrób to dla drugiego pliku APPX.

   ![Portal urządzeń z systemem Windows zainstalować Side-Loaded aplikacji](images/20190322-DevicePortal.png)
   
1. W tym momencie uważamy, że twoje aplikacje powinny zacząć ponownie działać i że możesz również przejść do Sklepu.

1. W niektórych przypadkach konieczne jest uruchomienie dodatkowego kroku uruchamiania aplikacji Przeglądarka 3D przed uruchomieniem aplikacji, których dotyczy problem. 

Dziękujemy za cierpliwość, ponieważ przeszliśmy przez proces rozwiązania tego problemu, i czekamy na kontynuowanie współpracy z naszą społecznością w celu utworzenia Mixed Reality doświadczenia.

### <a name="device-update"></a>Aktualizacja urządzenia

- 30 sekund po nowej aktualizacji powłoka może zniknąć jeden raz. Wykonaj gest **Blooma,** aby wznowić sesję.

### <a name="visual-studio"></a>Visual Studio

- Zobacz [Instalowanie narzędzi,](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) aby uzyskać najnowszą wersję pakietu Visual Studio zalecaną do tworzenia aplikacji na urządzeniach HoloLens.

- Podczas wdrażania aplikacji z usługi Visual Studio na urządzenie HoloLens może zostać wyświetlony błąd: Nie można wykonać żądanej operacji na pliku z otwartą sekcją **zamaponą przez użytkownika. (Wyjątek od HRESULT: 0x800704C8)**. Jeśli tak się stanie, spróbuj ponownie, aby wdrożenie na ogół zakończyło się pomyślnie.

### <a name="api"></a>interfejs API

- Jeśli aplikacja ustawia punkt [koncentracji uwagi](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) za użytkownikiem lub normalny na camera.forward, hologramy nie będą wyświetlane na Przechwytywanie rzeczywistości mieszanej lub wideo. Dopóki ta usterka nie zostanie naprawiona w systemie Windows, jeśli aplikacje aktywnie ustawiają punkt koncentracji uwagi, powinny upewnić się, że płaszczyzna normalna jest ustawiona na przeciwną kamerę do przodu (na przykład normal = -camera.forward). [](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity)

### <a name="xbox-wireless-controller"></a>Kontroler sieci bezprzewodowej Xbox

- Kontroler bezprzewodowy Konsoli Xbox S musi zostać zaktualizowany, aby można go było używać z urządzeniem HoloLens. Przed [próbą sparowania kontrolera z](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) urządzeniem HoloLens upewnij się, że jesteś na bieżąco.

- Jeśli ponownie uruchomisz urządzenie HoloLens, gdy kontroler sieci bezprzewodowej Xbox jest podłączony, kontroler nie zostanie automatycznie ponownie połączony z urządzeniem HoloLens. Światło przycisku Prowadnica będzie wolno migać, aż kontroler wyłączy się po 3 minutach. Aby od razu ponownie połączyć kontroler, wyłącz kontroler, przytrzymując przycisk Przewodnik do momentu wyłączenia światła. Ponowne włączenie kontrolera spowoduje ponowne nawiązanie połączenia z urządzeniem HoloLens.

- Jeśli urządzenie HoloLens przejdzie w stan wstrzymania, gdy kontroler bezprzewodowy konsoli Xbox jest podłączony, wszelkie dane wejściowe na kontrolerze wybudzą urządzenie HoloLens. Można temu zapobiec, wyłączając kontroler po jego użyciu.

## <a name="known-issues-for-hololens-emulator"></a>Znane problemy dotyczące emulatora urządzenia HoloLens

- Nie wszystkie aplikacje w Microsoft Store są zgodne z emulatorem. Na przykład w emulatorze nie można odtwarzać fragmentów Ani Younga Conkera.
- Nie można używać kamery internetowej komputera w emulatorze.
- Funkcja podglądu na żywo Portal urządzeń z systemem Windows nie działa z emulatorem. Nadal można przechwytywać Mixed Reality wideo i obrazy.
