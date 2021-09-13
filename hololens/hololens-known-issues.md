---
title: Znane problemy dotyczące HoloLens (1. generacja)
description: Bądź na bieżąco z naszą listą znanych problemów i obejść, które mogą mieć wpływ na HoloLens i deweloperów korzystających z aparatu Unity i Windows Portal urządzeń.
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
ms.openlocfilehash: 5c942bae91c7684f2c2d36aca6ace6306b5fed54
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033089"
---
# <a name="known-issues-for-hololens-1st-gen"></a>Znane problemy dotyczące HoloLens (1. generacja)

Poniżej znajduje się bieżąca lista znanych problemów dotyczących HoloLens urządzeń. Najpierw sprawdź tutaj, czy widzisz nietypowe zachowanie. Ta lista będzie aktualizowana w przypadku nowych problemów wykrytych lub zgłoszonych albo gdy problemy zostaną rozwiązane w HoloLens oprogramowania.

>[!NOTE]
> - Jeśli odkryjesz problem, który nie blokuje, zgłoś go na urządzeniu HoloLens za [pośrednictwem Centrum opinii.](hololens-feedback.md)
> - Jeśli problem, który występuje, blokuje Cię, oprócz zgłaszania opinii, prosimy [o zgłoszenie do pomocy technicznej.](https://aka.ms/hlsupport)


- [Znane problemy dla wszystkich HoloLens generacji](#known-issues-for-all-hololens-generations)
- [Znane problemy dotyczące HoloLens (1. generacja)](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a>Znane problemy dla wszystkich HoloLens generacji

### <a name="unity"></a>Unity

- Zobacz [Instalowanie narzędzi dla](/windows/mixed-reality/install-the-tools) najbardziej aktualnej wersji aparatu Unity zalecanej do HoloLens projektowania.
- Znane problemy z platformą Unity HoloLens Technical Preview są udokumentowane na [forach HoloLens Unity.](https://forum.unity3d.com/threads/known-issues.394627/)

### <a name="windows-device-portal"></a>Windows Portal urządzeń

- Funkcja Live Preview w funkcji Mixed Reality przechwytywania danych może mieć kilka sekund opóźnienia.

- Na stronie Wirtualne dane wejściowe kontrolki Gest i Przewiń w sekcji Gesty wirtualne nie działają. Ich użycie nie będzie mieć żadnego efektu. Klawiatura wirtualna na wirtualnej stronie wejściowej działa poprawnie.

- Po włączeniu trybu dewelopera w Ustawienia może mieć kilka sekund, zanim przełącznik włączy przełącznik, Portal urządzeń włączony.

### <a name="onedrive-camera-upload"></a>OneDrive przekazywania z aparatu

Aplikacja OneDrive dla aplikacji HoloLens nie obsługuje automatycznego przekazywania z aparatu dla kont służbowych.

Obejścia:

- Jeśli jest to możliwe dla Twojej firmy, automatyczne przekazywanie z aparatu jest obsługiwane na kontach Microsoft konsumentów. Możesz zalogować się do konta konto Microsoft konta służbowego (aplikacja OneDrive obsługuje logowanie podwójne). Z poziomu konto Microsoft w OneDrive można włączyć automatyczne przekazywanie z kamery w tle.

- Jeśli nie możesz bezpiecznie użyć konta konto Microsoft do automatycznego przekazywania zdjęć, możesz ręcznie przekazać zdjęcia na konto służbowe z aplikacji OneDrive aplikacji. W tym celu upewnij się, że zalogowano się do konta służbowego w OneDrive aplikacji. Wybierz przycisk **+** i wybierz pozycję **Upload**. Znajdź zdjęcia lub filmy wideo, które chcesz przekazać, przechodząc do tematu **Obrazy > aparatem.** Wybierz zdjęcia lub wideo, które chcesz przekazać, a następnie wybierz **przycisk** Otwórz.

## <a name="known-issues-for-hololens-1st-gen"></a>Znane problemy dotyczące HoloLens (1. generacja)

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Nie można nawiązać połączenia i wdrożyć HoloLens za pośrednictwem Visual Studio

> [!NOTE]
> Ostatnia aktualizacja: 8/8 o 17:11 — program Visual Studio opublikował program VS 2019 w wersji 16.2, który zawiera poprawkę do tego problemu. Zalecamy aktualizację do najnowszej wersji, aby uniknąć wystąpienia tego błędu.

Visual Studio program VS 2019 w wersji 16.2, który zawiera poprawkę tego problemu. Zalecamy aktualizację do najnowszej wersji, aby uniknąć wystąpienia tego błędu.

Główna przyczyna problemu: dotyczy to użytkowników, którzy używali programu Visual Studio 2015 lub wczesnych wersji programu Visual Studio 2017 do wdrażania i debugowania aplikacji na swoich HoloLens, a następnie używali najnowszych wersji programu Visual Studio 2017 lub Visual Studio 2019 z tym samym HoloLens. Nowsze wersje programu Visual Studio nową wersję składnika, ale pliki ze starszej wersji są pozostawiane na urządzeniu, co powoduje niepowodzenie nowszej wersji.  Powoduje to następujący komunikat o błędzie: DEP0100: Upewnij się, że urządzenie docelowe ma włączony tryb dewelopera. Nie można uzyskać licencji dewelopera z \<ip\> powodu błędu 80004005.

#### <a name="workaround"></a>Obejście

Nasz zespół obecnie pracuje nad poprawą. W międzyczasie możesz wykonać następujące kroki, aby ominąć problem i ułatwić odblokowanie wdrażania i debugowania:  

1. Otwórz program Visual Studio.

1. Wybierz **pozycję Plik**  >  **Nowy**  >  **Project**.

1. Wybierz **pozycję Visual C#**  >  **Windows Desktop** Console App  >  **(.NET Framework).**

1. Nadaj projektowi nazwę (na przykład "HoloLensDeploymentFix") i upewnij się, że dla struktury ustawiono co najmniej .NET Framework 4.5, a następnie wybierz przycisk **OK.**

1. Kliknij prawym przyciskiem myszy węzeł **Odwołania** w Eksplorator rozwiązań i dodaj następujące odwołania (wybierz **sekcję** Przeglądaj i wybierz **pozycję Przeglądaj):**

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Jeśli nie masz zainstalowanej wersji 10.0.18362.0, użyj najnowszej zainstalowanej wersji.

1. Kliknij prawym przyciskiem myszy projekt w Eksplorator rozwiązań a następnie **wybierz pozycję Dodaj** istniejący  >  **element**.

1. Przejdź do folderu C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 i zmień filtr na **Wszystkie pliki ( . \* \* )**.

1. Wybierz obie SirepClient.dll i SshClient.dll, a następnie wybierz **pozycję Dodaj.**

1. Znajdź i wybierz oba pliki w usłudze Eksplorator rozwiązań (powinny znajdować się  w dolnej części  listy plików) i zmień opcję Kopiuj do katalogu wyjściowego w oknie Właściwości na Kopiuj **zawsze**.

1. W górnej części pliku dodaj następujący kod do istniejącej listy `using` instrukcji:

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. W `static void Main(...)` programie dodaj następujący kod:

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

1. Uruchom plik wykonywalny i podaj adres IP urządzenia jako argument wiersza polecenia. (W przypadku połączenia przy użyciu portu USB możesz użyć adresu 127.0.0.1, w przeciwnym razie użyć adresu IP Wi-Fi urządzenia).  Na przykład "HoloLensDeploymentFix 127.0.0.1".

1. Gdy narzędzie zakończy działanie bez żadnych komunikatów (powinno to potrwać tylko kilka sekund), będzie można wdrażać i debugować z programu Visual Studio 2017 lub nowszej wersji.  Dalsze korzystanie z narzędzia nie jest konieczne.

W przypadku ich udostępnień będziemy dostarczać kolejne aktualizacje.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>Problemy z uruchamianiem aplikacji Microsoft Store na HoloLens

> [!NOTE]
> Ostatnia aktualizacja: 4/2 o 10:00 — problem został rozwiązany.

Mogą wystąpić problemy podczas próby uruchomienia aplikacji Microsoft Store na HoloLens. Ustaliliśmy, że problem występuje, gdy aktualizacje aplikacji w tle wdrażają nowszą wersję pakietów struktury w określonych sekwencjach, podczas gdy co najmniej jedna z aplikacji zależnych jest nadal uruchomiona. W takim przypadku automatyczna aktualizacja aplikacji dostarczała nową wersję programu .NET Native Framework (wersja od 10.0.25531 do 10.0.27413) spowodowała, że uruchomione aplikacje nie były poprawnie aktualizowane dla wszystkich uruchomionych aplikacji, które zużywają poprzednią wersję struktury.  Przepływ aktualizacji struktury jest następujący:

1. Nowy pakiet struktury jest pobierany ze sklepu i instalowany.

1. Wszystkie aplikacje korzystania ze starszej struktury są "aktualizowane" w celu korzystania z nowszej wersji.

Jeśli krok 2 zostanie przerwany przed zakończeniem, uruchomienie wszystkich aplikacji, dla których nie zarejestrowano nowszej struktury, z menu Start zakończy się niepowodzeniem.  Uważamy, że ten HoloLens może mieć wpływ na dowolną aplikację w tej aplikacji.

Niektórzy użytkownicy zgłaszali, że zamknięcie zawieszonych aplikacji i uruchomienie innych aplikacji, takich jak Centrum opinii, Przeglądarka 3D lub Photos, rozwiązuje problem — jednak nie działa to przez 100% czasu.

Główną przyczyną tego problemu nie była sama aktualizacja, ale usterka systemu operacyjnego, która powodowała niepoprawną obsługę aktualizacji struktury .NET Native. Z zadowoleniem ogłaszamy, że zidentyfikowano poprawkę i wydaliśmy aktualizację (system operacyjny w wersji 17763.380) zawierającą poprawkę.  

Aby sprawdzić, czy urządzenie może podjąć aktualizację:

1. Przejdź do aplikacji Ustawienia i otwórz **program Update & Security.**

1. Wybierz **pozycję Sprawdź aktualizacje.**

1. Jeśli dostępna jest aktualizacja do wersji 17763.380, zaktualizuj tę kompilację, aby otrzymać poprawkę dla błędu Zawieszanie aplikacji.

1. Po zaktualizowaniu do tej wersji systemu operacyjnego aplikacje powinny działać zgodnie z oczekiwaniami.

Ponadto, podobnie jak w przypadku każdego HoloLens systemu operacyjnego, obraz FFU został opublikowany w [Centrum pobierania Microsoft.](https://aka.ms/hololensdownload/10.0.17763.380)

Jeśli nie chcesz przyjmować aktualizacji, 29.03.29 wydaliśmy nową wersję aplikacji platformy uniwersalnej systemu Windows Microsoft Store platformy uniwersalnej systemu Windows. Po zaktualizowaniu wersji sklepu:

1. Otwórz magazyn i upewnij się, że jest ładowany.
1. Użyj gestu Blooma, aby otworzyć menu.
1. Spróbuj otworzyć wcześniej uszkodzone aplikacje.
1. Jeśli nadal nie można go uruchomić, naciśnij i przytrzymaj ikonę uszkodzonej aplikacji, a następnie wybierz pozycję Odinstaluj.
1. Zainstaluj ponownie te aplikacje ze sklepu.

Jeśli nadal nie można załadować aplikacji na urządzeniu, możesz załadować bezpośrednio wersję programu .NET Native Framework i środowiska uruchomieniowego za pośrednictwem Centrum pobierania, następujące kroki:

1. Pobierz ten [plik zip z](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) Centrum pobierania Microsoft. Rozpakowanie spowoduje tworzenie dwóch plików.  Microsoft .NET.Native.Runtime.1.7.appx i Microsoft .NET.Native.Framework.1.7.appx.

1. Sprawdź, czy urządzenie zostało odblokowane.  Jeśli nie zostało to jeszcze zrobione, zobacz Using the Windows Portal urządzeń (Używanie [Windows Portal urządzeń,](/windows/mixed-reality/using-the-windows-device-portal) aby uzyskać instrukcje.

1. Następnie chcesz uzyskać dostęp do Windows Portal urządzeń. Zaleca się, aby to zrobić za pośrednictwem portu USB, wpisując http://127.0.0.1:10080 polecenie w przeglądarce.

1. Po zakończeniu Windows Portal urządzeń należy "załadować bezpośrednio" dwa pobrane pliki. Aby to zrobić, musisz przejść w dół na  lewym pasku bocznym, aż do sekcji Aplikacje wybierzesz pozycję **Aplikacje.**

1. Zostanie wyświetlony ekran podobny do poniższego.  Chcesz przejść do sekcji Install App (Zainstaluj **aplikację)** i przejść do miejsca, w którym zostały rozpakowane te dwa pliki APPX. Można to zrobić tylko jeden raz na raz, więc po wybraniu pierwszej z nich kliknij pozycję "Przejdź" w sekcji Wdrażanie. Następnie zrób to dla drugiego pliku APPX.

   ![Windows Portal urządzeń zainstalować Side-Loaded aplikację.](images/20190322-DevicePortal.png)

1. W tym momencie uważamy, że twoje aplikacje powinny zacząć ponownie działać i że możesz również przejść do Sklepu.

1. W niektórych przypadkach konieczne jest uruchomienie dodatkowego kroku uruchamiania aplikacji Przeglądarka 3D przed uruchomieniem aplikacji, których dotyczy problem.

Dziękujemy za cierpliwość, ponieważ przeszliśmy przez proces rozwiązania tego problemu, i czekamy na kontynuowanie współpracy z naszą społecznością w celu utworzenia Mixed Reality doświadczenia.

### <a name="device-update"></a>Aktualizacja urządzenia

- 30 sekund po nowej aktualizacji powłoka może zniknąć jeden raz. Wykonaj gest **Blooma,** aby wznowić sesję.

### <a name="visual-studio"></a>Visual Studio

- Zobacz [Instalowanie narzędzi,](/windows/mixed-reality/install-the-tools) aby uzyskać najnowszą wersję pakietu Visual Studio zalecaną do HoloLens tworzenia aplikacji.

- Podczas wdrażania aplikacji z usługi Visual Studio do usługi HoloLens może zostać wyświetlony błąd: Nie można wykonać żądanej operacji na pliku z otwartą sekcją mapowana **przez użytkownika. (Wyjątek od HRESULT: 0x800704C8)**. Jeśli tak się stanie, spróbuj ponownie, aby wdrożenie na ogół zakończyło się pomyślnie.

### <a name="api"></a>interfejs API

- Jeśli aplikacja ustawia punkt [koncentracji uwagi](/windows/mixed-reality/focus-point-in-unity) za użytkownikiem lub normalny na camera.forward, hologramy nie będą wyświetlane na Przechwytywanie rzeczywistości mieszanej lub wideo. Dopóki ta usterka nie zostanie naprawiona [](/windows/mixed-reality/focus-point-in-unity) w Windows, jeśli aplikacje aktywnie ustawią punkt koncentracji uwagi, powinny upewnić się, że płaszczyzna normalna jest ustawiona na przeciwną kamerę do przodu (na przykład normal = -camera.forward).

### <a name="xbox-wireless-controller"></a>Kontroler sieci bezprzewodowej Xbox

- Kontroler bezprzewodowy Konsoli Xbox S musi zostać zaktualizowany, zanim będzie można go używać z HoloLens. Przed [podjęciem próby sparowania kontrolera](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) z kontrolerem upewnij się, że jesteś na bieżąco HoloLens.

- Jeśli ponownie uruchomisz urządzenie HoloLens, gdy kontroler sieci bezprzewodowej Xbox jest podłączony, kontroler nie zostanie automatycznie ponownie połączony z HoloLens. Światło przycisku Prowadnica będzie wolno migać, aż kontroler wyłączy się po 3 minutach. Aby od razu ponownie połączyć kontroler, wyłącz kontroler, przytrzymując przycisk Przewodnik do momentu wyłączenia światła. Ponowne włączenie kontrolera spowoduje ponowne nawiązanie połączenia z HoloLens.

- Jeśli urządzenie HoloLens w stanie wstrzymania, gdy kontroler sieci bezprzewodowej Xbox jest podłączony, wszelkie dane wejściowe na kontrolerze wznowią HoloLens. Można temu zapobiec, wyłączając kontroler po jego użyciu.

