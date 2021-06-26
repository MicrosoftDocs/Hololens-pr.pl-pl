---
title: Znane problemy dotyczące urządzenia HoloLens (1. generacja)
description: Bądź na bieżąco z naszą listą znanych problemów i obejść, które mogą mieć wpływ na klientów i deweloperów urządzenia HoloLens korzystających z aparatu Unity i środowiska Portal urządzeń z systemem Windows.
keywords: rozwiązywanie problemów, znany problem, pomoc
author: mattzmsft
ms.author: mazeller
ms.date: 6/15/2021
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
ms.openlocfilehash: 558eba8c2260b24a228e957b27927d508a077ec4
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923554"
---
# <a name="known-issues-for-hololens-1st-gen"></a>Znane problemy dotyczące urządzenia HoloLens (1. generacja)

Oto bieżąca lista znanych problemów dotyczących urządzeń HoloLens. Najpierw sprawdź tutaj, czy widzisz nietypowe zachowanie. Ta lista będzie aktualizowana w przypadku nowych problemów wykrytych lub zgłoszonych bądź gdy problemy zostaną rozwiązane w przyszłych aktualizacjach oprogramowania urządzenia HoloLens.

>[!NOTE]
> - Jeśli odkryjesz problem, który nie blokuje, zgłoś go na urządzeniu HoloLens za pośrednictwem [Centrum opinii](hololens-feedback.md).
> - Jeśli problem, który występuje, blokuje Cię, oprócz zgłaszania opinii, prosimy [o zgłoszenie do pomocy technicznej.](https://aka.ms/hlsupport)


- [Znane problemy dla wszystkich generacji urządzenia HoloLens](#known-issues-for-all-hololens-generations)
- [Znane problemy dotyczące urządzenia HoloLens (1. generacja)](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a>Znane problemy dla wszystkich generacji urządzenia HoloLens

### <a name="unity"></a>Unity

- Zobacz [Install the tools for](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) the most-to-date version of Unity recommended for HoloLens development (Instalowanie narzędzi dla najbardziej aktualnej wersji aparatu Unity zalecanej do budowania aplikacji na urządzeniach HoloLens).
- Znane problemy z urządzeniem Unity HoloLens Technical Preview są udokumentowane na [forach HoloLens Unity.](https://forum.unity3d.com/threads/known-issues.394627/)

### <a name="windows-device-portal"></a>Portal urządzeń z systemem Windows

- Funkcja podglądu na żywo w Mixed Reality przechwytywania danych może mieć opóźnienie kilku sekund.

- Na stronie Wirtualne dane wejściowe kontrolki Gest i Przewiń w sekcji Gesty wirtualne nie działają. Ich użycie nie będzie mieć żadnego efektu. Klawiatura wirtualna na stronie wirtualnych danych wejściowych działa poprawnie.

- Po włączeniu trybu dewelopera w ustawieniach może mieć kilka sekund, zanim Portal urządzeń przełącznik zostanie włączony.

### <a name="onedrive-camera-upload"></a>Przekazywanie aparatu w usłudze OneDrive

Aplikacja OneDrive dla urządzenia HoloLens nie obsługuje automatycznego przekazywania z aparatu dla kont służbowych.

Obejścia:

- Jeśli jest to możliwe dla Twojej firmy, automatyczne przekazywanie aparatów jest obsługiwane na kontach Microsoft klientów. Możesz zalogować się do konta konto Microsoft konta służbowego (aplikacja OneDrive obsługuje logowanie podwójne). Z poziomu konto Microsoft w usłudze OneDrive możesz włączyć automatyczne przekazywanie z aparatu w tle.

- Jeśli nie możesz bezpiecznie użyć konta konto Microsoft do automatycznego przekazywania zdjęć, możesz ręcznie przekazać zdjęcia do konta służbowego z aplikacji OneDrive. W tym celu upewnij się, że zalogowano się do konta służbowego w aplikacji OneDrive. Wybierz przycisk **+** i wybierz pozycję **Przekaż**. Znajdź zdjęcia lub wideo, które chcesz przekazać, przechodząc do tematu **Pictures > Camera Roll (Obrazy** i > camera Roll). Wybierz zdjęcia lub wideo, które chcesz przekazać, a następnie wybierz **przycisk** Otwórz.

## <a name="known-issues-for-hololens-1st-gen"></a>Znane problemy dotyczące urządzenia HoloLens (1. generacja)

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Nie można nawiązać połączenia i wdrożyć na urządzeniach HoloLens za pośrednictwem Visual Studio

> [!NOTE]
> Ostatnia aktualizacja: 8/8 o 17:11 — program Visual Studio opublikował program VS 2019 w wersji 16.2, który zawiera poprawkę tego problemu. Zalecamy zaktualizowanie do najnowszej wersji, aby uniknąć wystąpienia tego błędu.

Visual Studio program VS 2019 w wersji 16.2, który zawiera poprawkę tego problemu. Zalecamy zaktualizowanie do najnowszej wersji, aby uniknąć wystąpienia tego błędu.

Główna przyczyna problemu: Dotyczy to użytkowników, którzy używali programu Visual Studio 2015 lub wczesnych wersji programu Visual Studio 2017 do wdrażania i debugowania aplikacji na urządzeniach HoloLens, a następnie używali najnowszych wersji urządzenia Visual Studio 2017 lub Visual Studio 2019 z tym samym urządzeniem HoloLens. Nowsze wersje składnika Visual Studio nową wersję składnika, ale pliki ze starszej wersji są pozostawiane na urządzeniu, co powoduje niepowodzenie nowszej wersji.  Powoduje to następujący komunikat o błędzie: DEP0100: Upewnij się, że urządzenie docelowe ma włączony tryb dewelopera. Nie można uzyskać licencji dewelopera z \<ip\> powodu błędu 80004005.

#### <a name="workaround"></a>Obejście

Nasz zespół obecnie pracuje nad poprawek. W międzyczasie możesz wykonać następujące kroki, aby omiń problem i ułatwić odblokowanie wdrażania i debugowania:  

1. Otwórz program Visual Studio.

1. Wybierz **pozycję File** New Project  >  **(Plik nowego**  >  **projektu).**

1. Wybierz **pozycję Visual C#**  >  **Windows Desktop** Console App  >  **(.NET Framework)**.

1. Nadaj projektowi nazwę (na przykład "HoloLensDeploymentFix") i upewnij się, że dla struktury ustawiono co najmniej jedną .NET Framework 4.5, a następnie wybierz przycisk **OK.**

1. Kliknij prawym przyciskiem myszy węzeł **Odwołania** w Eksplorator rozwiązań dodaj następujące odwołania (wybierz **sekcję** Przeglądaj i wybierz pozycję **Przeglądaj):**

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

Podczas próby uruchomienia aplikacji i aplikacji na Microsoft Store HoloLens mogą wystąpić problemy. Ustaliliśmy, że problem występuje, gdy aktualizacje aplikacji w tle wdrażają nowszą wersję pakietów struktury w określonych sekwencjach, podczas gdy co najmniej jedna z aplikacji zależnych nadal działa. W takim przypadku automatyczna aktualizacja aplikacji dostarczała nową wersję programu .NET Native Framework (w wersji od 10.0.25531 do 10.0.27413) spowodowała, że uruchomione aplikacje nie były poprawnie aktualizowane dla wszystkich uruchomionych aplikacji, które zużywają poprzednią wersję struktury.  Przepływ aktualizacji struktury jest następujący:

1. Nowy pakiet struktury jest pobierany ze sklepu i instalowany.

1. Wszystkie aplikacje użyciu starszej struktury są "aktualizowane" w celu używania nowszej wersji.

Jeśli krok 2 zostanie przerwany przed ukończeniem, uruchomienie wszystkich aplikacji, dla których nie zarejestrowano nowszej struktury, z menu Start zakończy się niepowodzeniem.  Uważamy, że ten problem może mieć wpływ na dowolną aplikację na urządzeniach HoloLens.

Niektórzy użytkownicy zgłaszali, że zamknięcie zawieszonych aplikacji i uruchomienie innych aplikacji, takich jak Centrum opinii, Przeglądarka 3D lub Zdjęcia, rozwiązuje problem dla nich — jednak nie działa to przez 100% czasu.

Główną przyczyną tego problemu nie była sama aktualizacja, ale usterka systemu operacyjnego, która powodowała nieprawidłową obsługę aktualizacji struktury .NET Native. Z zadowoleniem ogłaszamy, że zidentyfikowano poprawkę i wydaliśmy aktualizację (system operacyjny w wersji 17763.380) zawierającą poprawkę.  

Aby sprawdzić, czy urządzenie może podjąć aktualizację:

1. Przejdź do aplikacji Ustawienia i otwórz program **Update & Security.**

1. Wybierz **pozycję Sprawdź aktualizacje.**

1. Jeśli jest dostępna aktualizacja do wersji 17763.380, zaktualizuj tę kompilację, aby otrzymać poprawkę dla błędu Zawieszanie aplikacji.

1. Po zaktualizowaniu do tej wersji systemu operacyjnego aplikacje powinny działać zgodnie z oczekiwaniami.

Ponadto, podobnie jak w przypadku każdej wersji systemu operacyjnego HoloLens, obraz FFU został opublikowany w [Centrum pobierania Microsoft.](https://aka.ms/hololensdownload/10.0.17763.380)

Jeśli nie chcesz przyjmować aktualizacji, 3/29 wydaliśmy nową wersję aplikacji platformy Microsoft Store platformy uniwersalnej systemu Windows. Po zaktualizowaniu wersji sklepu:

1. Otwórz magazyn i upewnij się, że jest ładowany.
1. Użyj gestu Blooma, aby otworzyć menu.
1. Spróbuj otworzyć wcześniej uszkodzone aplikacje.
1. Jeśli nadal nie można go uruchomić, naciśnij i przytrzymaj ikonę uszkodzonej aplikacji, a następnie wybierz pozycję Odinstaluj.
1. Zainstaluj ponownie te aplikacje ze sklepu.

Jeśli urządzenie nadal nie może ładować aplikacji, możesz załadować bezpośrednio wersję programu .NET Native Framework i środowiska uruchomieniowego za pośrednictwem Centrum pobierania, wykonać następujące czynności:

1. Pobierz ten [plik zip](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) z Centrum pobierania Microsoft. Rozpakowanie spowoduje tworzenie dwóch plików.  Microsoft .NET.Native.Runtime.1.7.appx i Microsoft .NET.Native.Framework.1.7.appx.

1. Sprawdź, czy urządzenie zostało odblokowane.  Jeśli nie zostało to jeszcze zrobione, zobacz [Using the Portal urządzeń z systemem Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) (Używanie Portal urządzeń z systemem Windows, aby uzyskać instrukcje.

1. Następnie chcesz uzyskać dostęp do Portal urządzeń z systemem Windows. Zaleca się, aby to zrobić za pośrednictwem portu USB, wpisując http://127.0.0.1:10080 je w przeglądarce.

1. Po zakończeniu Portal urządzeń z systemem Windows musimy "załadować bezpośrednio" dwa pobrane pliki. W tym celu należy przejść w dół na lewym pasku bocznym, aż do sekcji Aplikacje **i** wybrać pozycję **Aplikacje.**

1. Zostanie wyświetlony ekran podobny do poniższego.  Chcesz przejść do sekcji Install **App** (Instalowanie aplikacji) i przejść do miejsca, w którym rozpakowane zostały te dwa pliki APPX. Można to zrobić tylko jeden raz na raz, więc po wybraniu pierwszej z nich kliknij pozycję "Przejdź" w sekcji Wdrażanie. Następnie zrób to dla drugiego pliku APPX.

   ![Portal urządzeń z systemem Windows zainstalować Side-Loaded aplikacji](images/20190322-DevicePortal.png)

1. W tym momencie uważamy, że twoje aplikacje powinny zacząć ponownie działać i że możesz również przejść do sklepu Store.

1. W niektórych przypadkach konieczne jest uruchomienie dodatkowego kroku uruchamiania aplikacji Przeglądarka 3D przed uruchomieniem aplikacji, których dotyczy problem.

Dziękujemy za cierpliwość, ponieważ przeszliśmy przez proces rozwiązania tego problemu, i z niecierpliwością oczekujemy na kontynuowanie współpracy z naszą społecznością w celu utworzenia Mixed Reality doświadczenia.

### <a name="device-update"></a>Aktualizacja urządzenia

- 30 sekund po nowej aktualizacji powłoka może zniknąć jeden raz. Wykonaj gest **Blooma,** aby wznowić sesję.

### <a name="visual-studio"></a>Visual Studio

- Zobacz [Install the tools for](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) the most-to-date version of Visual Studio that is recommended for HoloLens development (Instalowanie narzędzi, aby uzyskać najnowszą wersję Visual Studio, która jest zalecana do instalowania na urządzeniach HoloLens.

- Podczas wdrażania aplikacji z Visual Studio na urządzenia HoloLens może zostać wyświetlony błąd: Nie można wykonać żądanej operacji na pliku z otwartą sekcją **mapowana przez użytkownika. (Wyjątek od HRESULT: 0x800704C8)**. Jeśli tak się stanie, spróbuj ponownie, aby wdrożenie na ogół zakończyło się pomyślnie.

### <a name="api"></a>interfejs API

- Jeśli aplikacja ustawia punkt [koncentracji uwagi](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) za użytkownikiem lub normalny tryb camera.forward, hologramy nie będą wyświetlane na Przechwytywanie rzeczywistości mieszanej lub wideo. Dopóki ta usterka nie zostanie naprawiona w systemie Windows, jeśli aplikacje aktywnie ustawią punkt koncentracji uwagi, powinny upewnić się, że płaszczyzna normalna jest ustawiona na przeciwną przód kamery (na przykład normal = -camera.forward). [](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity)

### <a name="xbox-wireless-controller"></a>Kontroler bezprzewodowy konsoli Xbox

- Przed rozpoczęciem pracy z urządzeniem HoloLens należy zaktualizować kontroler bezprzewodowy konsoli Xbox S. Przed [próbą sparowania kontrolera z](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) urządzeniem HoloLens upewnij się, że jesteś na bieżąco.

- W przypadku ponownego uruchomienia urządzenia HoloLens, gdy kontroler bezprzewodowy konsoli Xbox jest podłączony, kontroler nie zostanie automatycznie ponownie połączony z urządzeniem HoloLens. Światło przycisku Przewodnik będzie wolno migać, aż kontroler wyłączy się po 3 minutach. Aby od razu ponownie połączyć kontroler, wyłącz kontroler, przytrzymując przycisk Przewodnik, aż światło wyłączy się. Ponowne włączenie kontrolera spowoduje ponowne nawiązanie połączenia z urządzeniem HoloLens.

- Jeśli urządzenie HoloLens przejdzie w stan wstrzymania, gdy kontroler bezprzewodowy konsoli Xbox jest podłączony, wszelkie dane wejściowe na kontrolerze wybudzą urządzenie HoloLens. Możesz temu zapobiec, wyłączając kontroler po jego użyciu.

