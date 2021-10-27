---
title: Windows Autopilot dla urządzenia HoloLens 2
description: Dowiedz się, jak skonfigurować i rozwiązać problem z rozwiązaniem Autopilot na HoloLens 2.
author: qianw211
ms.author: v-qianwen
ms.date: 10/11/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Autopilota
manager: sekerawa
ms.openlocfilehash: 5ca7ad762e0fdbe448788926e7a6492cb7f2523d
ms.sourcegitcommit: 73a1555fb8b84f3d20c480282c648d8d800a6c98
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/26/2021
ms.locfileid: "130351706"
---
# <a name="windows-autopilot-for-hololens-2"></a>Windows Autopilot dla urządzenia HoloLens 2

## <a name="overview"></a>Omówienie

W przypadku wdrażania na dużą skalę zalecamy rozpoczęcie pracy z rozwiązaniem Windows Autopilot. Jest ona uznawana za "mały dotyk", ponieważ znacznie upraszcza konfigurowanie HoloLens dla it i użytkowników końcowych. 

Na wysokim poziomie administrator IT zazwyczaj tworzy konfiguracje gotowe do użycia w firmie i rejestruje 2 urządzenia HoloLens portalach MDM. Gdy urządzenia z systemem HoloLens 2 są włączane przy użyciu gotowego do użycia środowisko OOBE (out-of-box experience) i łączą się z Internetem, konfiguracje gotowe do użycia w firmie dla zarejestrowanych urządzeń z systemem HoloLens 2 są automatycznie pobierane i stosowane, aby przygotować urządzenia do pracy bez żadnej interwencji użytkownika.

Aby uzyskać więcej informacji, zobacz Omówienie rozwiązania [Windows Autopilot | Microsoft Docs](/mem/autopilot/windows-autopilot) artykułu.

## <a name="supported-autopilot-scenario-on-hololens-2"></a>Obsługiwany scenariusz rozwiązania Autopilot w HoloLens 2

> [!NOTE]
> Konfiguracja rozwiązania Autopilot dla HoloLens w Microsoft Endpoint Manager przechodzi z publicznej **wersji zapoznawczej** do **wersji ogólnie dostępnej.** Wszyscy dzierżawcy będą mogli skonfigurować funkcję Autopilot w centrum administracyjnym MEM.

Począwszy od Windows Holographic w wersji 2004, system HoloLens 2 obsługuje tryb samodzielnego wdrażania rozwiązania Windows [Autopilot](/mem/autopilot/self-deploying) z programem Microsoft Intune (rozwiązania MDM innych firm nie są obsługiwane). Ta konfiguracja zmniejsza narzut na zarządzanie zapasami, koszty praktycznego przygotowywania urządzeń i rozmów z pomocą techniczną od pracowników podczas procesu konfiguracji. Więcej informacji można znaleźć w [dokumentacji Windows Autopilot.](/mem/autopilot/windows-autopilot)

Podobnie jak w przypadku urządzeń Surface, zaleca się, aby klienci współpracowali z firmą Microsoft [Dostawca rozwiązań w chmurze](https://partner.microsoft.com/cloud-solution-provider) (odsprzedawcą lub dystrybutorem), aby zarejestrować urządzenia w usłudze Autopilot za pośrednictwem Partner Center.

Gdy użytkownik uruchamia proces samodzielnego wdrażania rozwiązania Autopilot, rozwiązanie Autopilot kończy następujące kroki:

1. Dołącz urządzenie do usługi Azure Active Directory (Azure AD). Rozwiązanie Autopilot HoloLens nie obsługuje dołączania do usługi Active Directory ani dołączania hybrydowego do usługi Azure AD.

1. Użyj usługi Azure AD, aby zarejestrować urządzenie w Microsoft Endpoint Manager (lub innej usłudze MDM).

1. Pobieranie i stosowanie zasad, certyfikatów, profilów sieciowych i aplikacji dla urządzeń docelowych.

1. Przedstawianie użytkownikowi ekranu logowania.

## <a name="configuring-autopilot-for-hololens-2"></a>Konfigurowanie rozwiązania Autopilot dla HoloLens 2

Wykonaj poniższe kroki, aby skonfigurować środowisko:

1. [Przejrzyj wymagania dotyczące rozwiązania Windows Autopilot dla HoloLens 2.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Włączanie automatycznej rejestracji mdm](#2-enable-automatic-mdm-enrollment)

1. (Tylko w przypadku usługi Intune) [Upewnij się, że rejestracja mdm nie jest zablokowana dla Windows urządzeń.](/mem/intune/enrollment/enrollment-restrictions-set)

1. [Rejestrowanie urządzeń w programie Windows Autopilot.](#4-register-devices-in-windows-autopilot)

1. [Utwórz grupę urządzeń.](#5-create-a-device-group)

1. [Utwórz profil rozwiązania Autopilot i przypisz go do grupy urządzeń.](#6-create-autopilot-profile-and-assign-it-to-the-device-group)

1. [Utwórz konfigurację strony ze stanem rejestracji i przypisz ją do grupy urządzeń.](#7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group)

1. [Sprawdź stan profilu HoloLens urządzeń.](#8-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. Przegląd wymagań dotyczących rozwiązania Windows Autopilot dla HoloLens 2

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>Zapoznaj się z następującymi sekcjami artykułu Windows wymagań rozwiązania Autopilot:

- [Wymagania dotyczące sieci](/mem/autopilot/networking-requirements)  
- [Wymagania dotyczące licencjonowania](/mem/autopilot/licensing-requirements)  
- [Wymagania dotyczące konfiguracji](/mem/autopilot/configuration-requirements)

**Zapoznaj się z [sekcją "Wymagania"](/windows/deployment/windows-autopilot/self-deploying#requirements)artykułu Windows trybie Self-Deploying Autopilot.** Środowisko musi spełniać te wymagania i standardowe wymagania Windows rozwiązania Autopilot. Nie musisz przeglądać sekcji "Krok po kroku" i "Walidacja" artykułu. Procedury w dalszej części tego artykułu zawierają odpowiednie kroki, które są specyficzne dla HoloLens.

Upewnij się, że urządzenia nie są jeszcze członkami usługi Azure AD i nie są zarejestrowane w usłudze Intune (ani w innym systemie MDM). Proces samodzielnego wdrażania rozwiązania Autopilot kończy te kroki. Aby upewnić się, że wszystkie informacje dotyczące urządzenia  są czyszczone, sprawdź strony Urządzenia w portalach usługi Azure AD i Intune. Konwertowanie wszystkich urządzeń docelowych na funkcję Autopilot nie HoloLens obecnie obsługiwane.

#### <a name="review-hololens-os-requirements"></a>Przejrzyj HoloLens systemu operacyjnego:

Aby potwierdzić wersję kompilacji na urządzeniu lub odtworzyć ukośnik do najnowszego systemu operacyjnego, użyj narzędzia [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=2&activetab=pivot:overviewtab) i naszych instrukcji [reflash urządzenia.](hololens-recovery.md) Urządzenia dostarczane do końca września 2020 r. mają Windows systemu Holographic w wersji 1903. Skontaktuj się ze sprzedawcą, aby upewnić się, że urządzenia gotowe do rozwiązania Autopilot są dostarczane do Ciebie.

 Minimalna wersja systemu operacyjnego | Obsługiwana funkcja | Uwagi
 ------ | ------ | ------  
 [Windows Holographic, wersja 2004](hololens-release-notes.md#windows-holographic-version-2004) (kompilacja 19041.1103) lub nowsza | 1. Scenariusz samodzielnego wdrażania rozwiązania Autopilot w HoloLens 2. | Pobieranie profilu rozwiązania Autopilot jest obsługiwane tylko za pośrednictwem sieci Ethernet. Przed włączeniem HoloLens upewnij się, że urządzenie jest połączone z siecią Ethernet przy użyciu adaptera "USB-C to **Ethernet".**  Jeśli planujesz użycie rozwiązania Autopilot na wielu urządzeniach HoloLens, zalecamy zaplanowanie infrastruktury adaptera. Nie zalecamy koncentratorów USB, ponieważ często wymagają one zainstalowania sterowników innych firm, które nie są obsługiwane HoloLens.
 [Windows Holographic, wersja 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (kompilacja 19041.1128) lub nowsza | 1. Pobieranie profilu rozwiązania Autopilot za pośrednictwem sieci Wi-Fi. <br> 2. [Blokada dzierżawy CSP i rozwiązania Autopilot](#tenant-lockdown-csp-and-autopilot) w celu blokowania urządzeń z określoną dzierżawą rozwiązania Autopilot. | W razie potrzeby można nadal używać kart Ethernet. W przypadku urządzeń połączonych za pośrednictwem sieci Wi-Fi użytkownik musi tylko: <ul> <li> Przejdź przez scenę z ploterami. </li> <li> Wybierz język i ustawienia lokalne. </li> <li> Uruchamianie z okiem. </li> <li> Pomyślnie nawiązyj połączenie z żądaną siecią Wi-Fi. </li> </ul>

### <a name="2-enable-automatic-mdm-enrollment"></a>2. Włącz automatyczną rejestrację mdm:

Aby rozwiązanie Autopilot zakończyło się pomyślnie, należy włączyć automatyczne rejestrowanie mdm w Azure Portal. Umożliwi to rejestrowanie urządzenia bez użytkownika.

Zapoznaj się z następującym krótkim przewodnikiem na temat włączania automatycznego rejestrowania w u [rozwiązaniach MDM](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) lub przewodnikiem Szybki [start](/mem/intune/enrollment/quickstart-setup-auto-enrollment) dotyczący automatycznego rejestrowania, aby uzyskać jeszcze więcej informacji na temat konfiguracja.

### <a name="3-ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>3. Upewnij się, że rejestracja mdm nie jest blokowana dla Windows urządzeń.

Aby funkcja Autopilot zakończyła się powodzeniem, musisz upewnić się, że twoje urządzenia HoloLens mogą być rejestrowane. Ponieważ HoloLens jest uznawana za Windows, nie trzeba będzie mieć żadnych ograniczeń rejestracji, które mogłyby zablokować wdrożenie. [Przejrzyj tę listę ograniczeń i](/mem/intune/enrollment/enrollment-restrictions-set) upewnij się, że będziesz mieć możliwość rejestrowania urządzeń.

### <a name="4-register-devices-in-windows-autopilot"></a>4. Rejestrowanie urządzeń w programie Windows Autopilot

Urządzenia muszą zostać zarejestrowane w programie Windows Autopilot przed pierwszą konfiguracją.

Istnieją trzy podstawowe sposoby rejestrowania HoloLens urządzeń:

 - **Odsprzedawca może zarejestrować urządzenia w Partner Center podczas zamawiania.**

   > [!NOTE]  
   > Jest to zalecana ścieżka dodawania urządzeń do usługi Autopilot. [Dowiedz się więcej](/mem/autopilot/partner-registration).  

 - **Wniosek [o pomoc techniczną możesz przesłać](hololens2-autopilot-registration-support.md) bezpośrednio do firmy Microsoft.**
 - Pobierz skrót sprzętu (znany również jako identyfikator sprzętu) i zarejestruj urządzenie **ręcznie w centrum administracyjnym MEM.**

#### <a name="obtain-hardware-hash"></a>Uzyskiwanie skrótu sprzętu

Skrót sprzętu można pobrać z urządzenia. Urządzenie rejestruje skrót sprzętu w pliku CSV podczas procesu OOBE lub później, gdy właściciel urządzenia uruchamia proces zbierania dzienników diagnostycznych (opisany w poniższej procedurze). Zazwyczaj właściciel urządzenia jest pierwszym użytkownikiem, który loguje się do urządzenia.

> [!WARNING]
> W kompilacjach wcześniejszych niż 20H2, jeśli przeszliśmy przez tryb OOBE i ustawiono telemetrię Na wymagane, nie można zebrać skrótu sprzętu dla rozwiązania Autopilot za pomocą tej metody. W celu zebrania skrótu sprzętu za pomocą tej metody ustaw opcję telemetrii na Wartość pełna za pośrednictwem aplikacji Ustawienia, a następnie wybierz pozycję **Diagnostyka**  >  **prywatności.**

1. Uruchom urządzenie HoloLens 2.

1. Na urządzeniu naciśnij jednocześnie przyciski **Power** i **Volume Down,** a następnie zwolnij je. Urządzenie zbiera dzienniki diagnostyczne i skrót sprzętu i zapisuje je w zestawie .zip plików.

1. Aby uzyskać szczegółowe informacje i instruktażowy film wideo na temat wykonywania tej czynności, przeczytaj o [diagnostyce trybu offline.](hololens-diagnostic-logs.md#offline-diagnostics)

1. Podłącz urządzenie do komputera za pomocą kabla USB-C.

1. Na komputerze otwórz Eksplorator plików. Otwórz <b>pozycję \\ Ten komputer</b>HoloLens nazwę urządzenia < *Wewnętrzne* Storage > <b> \\ \\ Dokumenty</b>i znajdź AutopilotDiagnostics.zip plik.  

   > [!NOTE]  
   > Plik .zip może nie być natychmiast dostępny. Jeśli plik nie jest jeszcze gotowy, w folderze Documents może zostać wyświetlony plik HoloLensDiagnostics.temp. Aby zaktualizować listę plików, odśwież okno.

1. Wyodrębnij zawartość AutopilotDiagnostics.zip pliku.

1. W wyodrębnianych plikach znajdź plik CSV z prefiksem nazwy pliku "DeviceHash". Skopiuj ten plik na dysk na komputerze, na którym można uzyskać do niego dostęp później.  

   > [!IMPORTANT]  
   > Dane w pliku CSV powinny mieć następujący format nagłówka i wiersza:
   >
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

#### <a name="register-device-through-mem"></a>Rejestrowanie urządzenia za pośrednictwem MEM

1. W [Microsoft Endpoint Manager administracyjnym](https://endpoint.microsoft.com)wybierz pozycję Urządzenia Windows Windows rejestracji, a następnie wybierz pozycję Urządzenia  >    >     >  **Importuj** **w obszarze Windows Autopilot Deployment Program**.

1. W **obszarze Windows rozwiązania Autopilot** wybierz plik CSV DeviceHash, wybierz pozycję **Otwórz,** a następnie wybierz pozycję **Importuj**.  

   > [!div class="mx-imgBorder"]
   > ![Zaimportuj skrót sprzętu za pomocą polecenia Import.](./images/hololens-ap-hash-import.png)

1. Po zakończeniu importowania wybierz pozycję **Urządzenia** Windows  >    >  **Windows urządzenia**  >  **Synchronizuj**  >  urządzenia. Ukończenie tego procesu może potrwać kilka minut, w zależności od tego, ile urządzeń jest synchronizowanych. Aby wyświetlić zarejestrowane urządzenie, wybierz pozycję **Odśwież.**  

   > [!div class="mx-imgBorder"]
   > ![Użyj poleceń Synchronizuj i Odśwież, aby wyświetlić listę urządzeń.](./images/hololens-ap-devices-sync.png)  

### <a name="5-create-a-device-group"></a>5. Tworzenie grupy urządzeń

1. W [Microsoft Endpoint Manager administracyjnym wybierz](https://endpoint.microsoft.com)pozycję Grupy **Nowa**  >  **grupa.**

1. W **polu Typ grupy** wybierz pozycję **Zabezpieczenia,** a następnie wprowadź nazwę i opis grupy.

1. W **przypadku opcji Typ** członkostwa wybierz pozycję **Przypisane** lub **Urządzenie dynamiczne.**

1. Wykonaj jedną z następujących czynności:  

   - Jeśli w poprzednim **kroku wybrano** **pozycję** Przypisane dla typu członkostwa, wybierz pozycję **Członkowie,** a następnie dodaj urządzenia rozwiązania Autopilot do grupy. Urządzenia rozwiązania Autopilot, które nie zostały jeszcze zarejestrowane, są wyświetlane przy użyciu numeru seryjnego urządzenia jako nazwy urządzenia.
   - Jeśli w poprzednim  **kroku** jako typ członkostwa wybrano pozycję Urządzenia dynamiczne,  wybierz pozycję Dynamiczne elementy członkowskie **urządzenia,** a następnie wprowadź kod w opcji Reguła zaawansowana, który będzie podobny do następującego:
     - Aby utworzyć grupę obejmującą wszystkie urządzenia rozwiązania Autopilot, wpisz: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Pole tagu grupy usługi Intune jest mapowanie na atrybut **OrderID** na urządzeniach usługi Azure AD. Jeśli chcesz utworzyć grupę, która zawiera wszystkie urządzenia rozwiązania Autopilot z określonym tagiem grupy (OrderID urządzenia usługi Azure AD), musisz wpisać: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Jeśli chcesz utworzyć grupę, która zawiera wszystkie urządzenia rozwiązania Autopilot o określonym identyfikatorze zamówienia zakupu, wpisz: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Te reguły są atrybutami unikatowymi dla urządzeń rozwiązania Autopilot.
1. Wybierz **pozycję Zapisz,** a następnie wybierz **pozycję Utwórz.**

### <a name="6-create-autopilot-profile-and-assign-it-to-the-device-group"></a>6. Tworzenie profilu rozwiązania Autopilot i przypisywanie go do grupy urządzeń

1. W [Microsoft Endpoint Manager administracyjnym](https://endpoint.microsoft.com)wybierz **pozycję** Urządzenia Windows Windows rejestracji Windows wdrażania rozwiązania  >    >    >  **Autopilot** Utwórz  >  **profil**  >  **HoloLens**.
   ![Lista rozwijana Tworzenie profilu zawiera HoloLens elementu.](./images/hololens-ap-enrollment-profiles.png)

1. Wprowadź nazwę i opis profilu, a następnie wybierz pozycję **Dalej.**  
   Powinna zostać wyświetlona lista, która zawiera **HoloLens**. Jeśli ta opcja nie jest obecna, użyj jednej z opcji [opinii,](hololens2-autopilot.md#feedback-and-support-for-autopilot) aby się z nami skontaktować.

   > [!div class="mx-imgBorder"]
   > ![Dodaj nazwę i opis profilu.](./images/hololens-ap-profile-name.png)

1. Na stronie **Środowisko OOBE (Out-of-box experience)** większość ustawień jest wstępnie skonfigurowana w celu usprawnienia procesu OOBE na czas tej oceny. Opcjonalnie można skonfigurować następujące ustawienia:  

   - **Język (region):** wybierz język dla OOBE. Zalecamy wybranie języka z listy obsługiwanych języków dla wersji [HoloLens 2.](hololens2-language-support.md)
   - **Automatycznie konfiguruj klawiaturę:** aby upewnić się, że klawiatura jest taka, jak w wybranym języku, wybierz pozycję **Tak.**
   - Zastosuj szablon nazwy **urządzenia:** aby automatycznie ustawić nazwę  urządzenia podczas OOBE, wybierz  pozycję Tak, a następnie wprowadź frazę szablonu i symbole zastępcze w sekcji Wprowadź nazwę. Na przykład wprowadź prefiks i symbol zastępczy czterocyfrowej liczby `%RAND:4%` &mdash; losowej.
     > [!NOTE]  
     > Jeśli używasz szablonu nazwy urządzenia, proces OOBE ponownie uruchamia urządzenie jeden raz po nadaniem nazwy urządzenia i przed dołączeniu urządzenia do usługi Azure AD. To ponowne uruchomienie powoduje, że nowa nazwa będzie obowiązywać.  

   > [!div class="mx-imgBorder"]
   > ![Konfigurowanie ustawień OOBE.](./images/hololens-ap-profile-oobe.png)

1. Po skonfigurowaniu ustawień wybierz pozycję **Dalej.**
1. Na stronie **Tagi zakresu** opcjonalnie dodaj tagi zakresu, które chcesz zastosować do tego profilu. Więcej informacji na temat tagów zakresu można znaleźć w artykule [Używanie kontroli dostępu opartej na rolach (RBAC) i tagów zakresu w rozproszonej infrastrukturze informatycznej](/mem/intune/fundamentals/scope-tags.md). Po zakończeniu wybierz przycisk **Dalej**.
1. Na stronie **Przypisania wybierz** pozycję **Wybrane grupy** dla opcji **Przypisz do**.
1. W **obszarze WYBRANE GRUPY** wybierz pozycję + Wybierz grupy do **dołączyć**.
1. Na liście Wybierz grupy do **dołączyć** wybierz grupę urządzeń utworzoną dla rozwiązania Autopilot HoloLens urządzeń, a następnie wybierz pozycję **Dalej.**  
  
   Jeśli chcesz wykluczyć wszystkie grupy, wybierz pozycję Wybierz **grupy** do wykluczenia i wybierz grupy, które chcesz wykluczyć.

   > [!div class="mx-imgBorder"]
   > ![Przypisywanie grupy urządzeń do profilu.](./images/hololens-ap-profile-assign-devicegroup.png)

1. Na stronie **Przeglądanie + tworzenie** przejrzyj ustawienia, a następnie wybierz pozycję **Utwórz,** aby utworzyć profil.  

   > [!div class="mx-imgBorder"]
   > ![Przeglądanie i tworzenie.](./images/hololens-ap-profile-summ.png)

### <a name="7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group"></a>7. Tworzenie konfiguracji strony ze stanem rejestracji i przypisywanie jej do grupy urządzeń

Strona ze stanem rejestracji (ESP) wyświetla stan kompletnego procesu konfiguracji urządzenia, który jest uruchamiany, gdy użytkownik zarządzany przez rozwiązanie MDM po raz pierwszy logowania się na urządzeniu. Upewnij się, że konfiguracja esp jest podobna do poniższej, i sprawdź, czy przypisania są poprawne.  

> [!div class="mx-imgBorder"]
> ![Konfiguracja esp.](./images/hololens-ap-profile-settings.png)

Aby uzyskać więcej informacji na temat strony ze stanem rejestracji, zobacz Konfigurowanie strony ze [stanem rejestracji — Microsoft Intune | Microsoft Docs](/mem/intune/enrollment/windows-enrollment-status)

### <a name="8-verify-the-profile-status-of-the-hololens-devices"></a>8. Sprawdź stan profilu HoloLens urządzeniach

1. W Microsoft Endpoint Manager administracyjnym wybierz **pozycję** Urządzenia Windows  >    >  **Windows**  >  **urządzenia.**

1. Sprawdź, HoloLens urządzenia są wyświetlane na liście i czy ich stan profilu to **Przypisane.**  

   > [!NOTE]  
   > Przypisanie profilu do urządzenia może potrwać kilka minut.  

   > [!div class="mx-imgBorder"]
   > ![Przypisania urządzeń i profilów.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Windows Środowisko użytkownika rozwiązania Autopilot HoloLens 2

Po ukończeniu powyższych instrukcji użytkownicy HoloLens 2 przejdą przez następujące środowisko, aby aprowizować swoje HoloLens urządzeń:  

1. Środowisko rozwiązania Autopilot wymaga dostępu do Internetu. Aby zapewnić dostęp do Internetu, użyj jednej z następujących opcji:

    - Połączenie urządzenie do sieci Wi-Fi w trybie OOBE, a następnie pozwól, aby automatycznie wykrywało środowisko rozwiązania Autopilot. Jest to jedyny czas, gdy trzeba będzie korzystać z rozwiązania OOBE, dopóki środowisko rozwiązania Autopilot nie zostanie ukończone samodzielnie.

    - Połączenie urządzenie z siecią Ethernet przy użyciu adapterów "USB-C–Ethernet" do łączności przewodowej z Internetem i HoloLens automatycznie ukończyć środowisko rozwiązania Autopilot.

    - Połączenie urządzenia z adapterami "USB-C do Wi-Fi" na bezprzewodowe połączenie z Internetem i pozwól na automatyczne HoloLens 2 pełne środowisko rozwiązania Autopilot.

        > [!IMPORTANT]  
       > Urządzenia próbujące korzystać z sieci Wi-Fi w trybie OOBE dla rozwiązania Autopilot muszą być na Windows Holographic w wersji [20H2.](hololens-release-notes.md#windows-holographic-version-20h2)
       >
       > W przypadku urządzeń korzystających z kart Ethernet należy podłączyć urządzenie do sieci przed rozpoczęciem korzystania z technologii OOBE (Out-of-the-Box-Experience). Urządzenie określa, czy aprowizuje jako urządzenie rozwiązania Autopilot na pierwszym ekranie OOBE. Jeśli urządzenie nie może nawiązać połączenia z siecią lub jeśli nie chcesz aprowizować urządzenia jako urządzenia rozwiązania Autopilot, nie możesz zmienić aprowowania rozwiązania Autopilot na później. Zamiast tego należy uruchomić tę procedurę od początku, aby aprowizować urządzenie jako urządzenie rozwiązania Autopilot.

1. Urządzenie powinno automatycznie uruchomić OOBE. Nie należy wchodzić w interakcje z OOBE.

    > [!IMPORTANT]
    > Nie wchodź w interakcję z trybem OOBE ani nie naciskaj przycisku zasilania, aby wprowadzić system w stan wstrzymania/zamknięcia, gdy funkcja Autopilot jest w toku. Może to spowodować, że przepływ rozwiązania Autopilot nie zostanie ukończony.

   Pozwól HoloLens 2 wykryć łączność sieciową i zezwolić na automatyczne ukończenie procesu OOBE. Urządzenie może zostać uruchomione ponownie podczas OOBE. Ekrany OOBE powinny wyglądać następująco.

   ![OOBE krok 1. ](./images/autopilot-welcome.jpg)
    ![ OOBE , krok 2. ](./images/autopilot-step-complete.jpg)
    ![ OOBE , krok 3.](./images/autopilot-device-setup.jpg)

1. Po zakończeniu korzystania z technologii OOBE możesz zalogować się na urządzeniu przy użyciu swojej nazwy użytkownika i hasła.

   <img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenant-lockdown-csp-and-autopilot"></a>Blokada dzierżawy — CSP i Autopilot

HoloLens 2 obsługują usługę TenantLockdown CSP od Windows Holographic w wersji 20H2. Ten program CSP utrzymuje urządzenia w dzierżawie organizacji, blokując je do tej dzierżawy nawet za pomocą resetowania urządzenia lub reflash.

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) Zasady CSP umożliwiają HoloLens 2 z rejestracją MDM tylko przy użyciu rozwiązania Autopilot. Gdy węzeł RequireNetworkInOOBE w programie TenantLockdown CSP zostanie ustawiony na wartość true lub false (początkowo ustawioną) na HoloLens 2, ta wartość pozostanie na urządzeniu pomimo reflashingu, aktualizacji systemu operacyjnego itp.

Gdy węzeł RequireNetworkInOOBE dostawcy CSP TenantLockdown zostanie ustawiony na wartość true w wersji HoloLens 2, obiekt OOBE czeka przez czas nieokreślony na pomyślne pobranie i zastosowanie profilu rozwiązania Autopilot po napięciu sieciowym.

Gdy w węźle RequireNetworkInOOBE dla węzła RequireNetworkInOOBE dla węzła TenantLockdown zostanie ustawiona wartość true na HoloLens 2, następujące operacje są niedozwolone w OOBE:

- Tworzenie użytkownika lokalnego przy użyciu aprowizowania środowiska uruchomieniowego
- Wykonywanie operacji dołączania do usługi Azure AD za pośrednictwem aprowizowania środowiska uruchomieniowego
- Wybieranie, kto jest właścicielem urządzenia w środowisko OOBE

#### <a name="how-to-set-this-using-intune"></a>Jak to ustawić przy użyciu usługi Intune?

1. Utwórz niestandardowy profil konfiguracji urządzenia OMA URI i określ wartość true dla węzła RequireNetworkInOOBE, jak pokazano poniżej.
Wartość OMA-URI powinna mieć wartość ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Ustawianie blokady czasowej za pośrednictwem OMA-URI.](images/hololens-tenant-lockdown.png)

1. Utwórz grupę i przypisz profil konfiguracji urządzenia do tej grupy urządzeń.

1. Dokonaj synchronizacji HoloLens 2 urządzenia w grupie utworzonej w poprzednim kroku i wyzwolij synchronizację.  

Sprawdź w portalu usługi Intune, czy konfiguracja urządzenia została pomyślnie zastosowana. Gdy ta konfiguracja urządzenia zostanie pomyślnie stosowana na urządzeniu HoloLens 2, efekty ustawienia TenantLockdown będą aktywne.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Jak zdezsetować usługę RequireNetworkInOOBE w usłudze HoloLens 2 przy użyciu usługi Intune?

1. Usuń HoloLens 2 z grupy urządzeń, do której wcześniej przypisano utworzoną powyżej konfigurację urządzenia.

1. Utwórz niestandardowy profil konfiguracji urządzenia oparty na URI OMA i określ wartość false dla wartości RequireNetworkInOOBE, jak pokazano poniżej.
Wartość OMA-URI powinna być ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Zrzut ekranu przedstawiający ustawianie wartości false dla ustawienia RequireNetworkInOOBE za pośrednictwem adresu URI OMA w usłudze Intune.](images/hololens-tenant-lockdown-false.png)

1. Utwórz grupę i przypisz profil konfiguracji urządzenia do tej grupy urządzeń.

1. Przek HoloLens 2 urządzenia w grupie utworzonej w poprzednim kroku i wyzwolij synchronizację.

Sprawdź w portalu usługi Intune, czy konfiguracja urządzenia została pomyślnie zastosowana. Gdy ta konfiguracja urządzenia zostanie pomyślnie stosowana na urządzeniu HoloLens 2, skutki ustawienia TenantLockdown będą nieaktywne.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Co się stanie podczas OOBE, jeśli profil rozwiązania Autopilot zostanie nieprzypisane w HoloLens po tym, jak ustawienie TenantLockdown miało wartość true?

OOBE będzie czekać przez czas nieokreślony na pobranie profilu rozwiązania Autopilot i zostanie wyświetlone następujące okno dialogowe. Aby usunąć skutki ustawienia TenantLockdown, urządzenie musi najpierw zostać zarejestrowane w pierwotnej dzierżawie przy użyciu rozwiązania Autopilot, a opcja RequireNetworkInOOBE musi zostać nieskonsorowana zgodnie z opisem w poprzednim kroku przed usunięciem ograniczeń wprowadzonych przez program TenantLockdown CSP.

![Widok na urządzeniu dla sytuacji, gdy zasady są wymuszane na urządzeniu.](images/hololens-autopilot-lockdown.png)

## <a name="troubleshooting"></a>Rozwiązywanie problemów

### <a name="issue---mdm-enrollment-fails-with-error-0x80180014-error-code-during-autopilot"></a>Problem — rejestracja w ramach rozwiązania MDM kończy się niepowodzeniem z 0x80180014 błędu podczas pracy z rozwiązaniem Autopilot.

 **Objawy**
 
Jest to błąd wyświetlany podczas procesu rozwiązania Autopilot na urządzeniu. Ten problem występuje tylko wtedy, HoloLens urządzenie wykonało następujące czynności:

1. Funkcja Autopilot została już co najmniej raz przejęła przez program Autopilot.
1. Jest teraz resetowany i ponownie używany dla rozwiązania Autopilot.

Środowisko rozwiązania Autopilot nie powiedzie się z określonym błędem.

![HoloLens Kod błędu rozwiązania Autopilot](images/autopilot-0x80180014-failure.jpg)

**Kroki rozwiązywania problemów**

1. Wykonaj kroki opisane w [te tematach Troubleshoot Autopilot device import and enrollment (Rozwiązywanie](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode) problemów z importowaniem i rejestrowaniem urządzeń rozwiązania Autopilot), aby usunąć urządzenie z usługi Intune. (Administrator usługi Intune będzie musiał wykonać to zadanie)
1. Po zakończeniu kroku 1 uruchom ponownie urządzenie i zaloguj się.
1. Przejdź do **Ustawienia**  ->  **aktualizacji & resetowania zabezpieczeń &**  ->  **i** wybierz pozycję **Wprowadzenie.**
    1. Jeśli występują problemy z krokami 2 & 3, zapoznaj się z alternatywami resetowania urządzenia na stronie [Resetowanie/ukośnik HoloLens](hololens-recovery.md).

Następnie należy pomyślnie zarejestrować program AutoPilot.

### <a name="issue---autopilot-experience-did-not-start-even-though-the-autopilot-profile-is-assigned-in-intune"></a>Problem — środowisko rozwiązania Autopilot nie uruchamia się, mimo że profil rozwiązania Autopilot jest przypisany w usłudze Intune.

**Objawy**

Domyślnie funkcja HoloLens 2 czeka 15 sekund na wykrycie rozwiązania Autopilot po wykryciu Internetu. Jeśli w ciągu 15 sekund nie zostanie wykryty żaden profil rozwiązania Autopilot, oznacza to, że funkcja Autopilot nie została poprawnie odnaleziona, a zostanie wyświetlony strona eula.

**Kroki rozwiązywania problemów**

1. Najpierw sprawdź, czy profil rozwiązania Autopilot jest wyświetlany jako przypisany w portalu MDM, np. w usłudze Intune. 
1. Uruchom ponownie urządzenie i spróbuj ponownie. Aby uzyskać więcej informacji, zobacz [Znane problemy i ograniczenia.](hololens2-autopilot.md#troubleshooting)

### <a name="helpful-resources"></a>Przydatne zasoby

Następujące artykuły mogą być przydatne, jeśli chcesz dowiedzieć się więcej i rozwiązać problemy z rozwiązaniem Autopilot, jednak te artykuły są oparte na programie Windows 10 Desktop i nie wszystkie informacje mogą mieć zastosowanie do HoloLens:

- [Windows Autopilot — znane problemy](/mem/autopilot/known-issues)
- [Rozwiązywanie problemów dotyczących rejestrowania urządzeń z systemem Windows w usłudze Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot — konflikty zasad](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Opinie i pomoc techniczna dla rozwiązania Autopilot

Aby przekazać opinię lub zgłosić problemy, użyj jednej z następujących metod:

- Aby uzyskać pomoc techniczną w zakresie rejestracji urządzeń, skontaktuj się z odsprzedawcą lub dystrybutorem.
- W przypadku ogólnych zapytań pomocy technicznej dotyczących rozwiązania Windows Autopilot lub problemów, takich jak przypisania profilów, tworzenie grup lub kontrolki portalu MEM, skontaktuj się z Microsoft Endpoint Manager [pomocy technicznej](/mem/get-support)  
- Jeśli urządzenie jest zarejestrowane w usłudze Autopilot, a profil jest przypisany w portalu MEM, skontaktuj się z działem pomocy technicznej HoloLens [(zobacz](/hololens/) kartę "Pomoc techniczna"). Otwórz bilet pomocy technicznej i, jeśli ma to zastosowanie, dołącz zrzuty ekranu i dzienniki, przechwytując dzienniki diagnostyczne w trybie [offline](hololens-diagnostic-logs.md#offline-diagnostics) podczas procesu OOBE (out-of-box-experience).
- Aby zgłosić problem z urządzenia, użyj aplikacji Centrum opinii na HoloLens. W Centrum opinii wybierz **kategorię Enterprise**  >  **Zarządzanie** urządzeniami.
- Aby przekazać ogólną opinię na temat rozwiązania Autopilot HoloLens, możesz przesłać tę [ankietę](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)

## <a name="delete-autopilot-devices"></a>Usuwanie urządzeń rozwiązania Autopilot

Możesz nie chcieć już używać urządzenia do korzystania z rozwiązania Autopilot lub rejestrować urządzenia w innej dzierżawie. Jeśli chcesz to zrobić, przeczytaj, jak usunąć urządzenia [rozwiązania Autopilot.](/mem/autopilot/add-devices#delete-autopilot-devices)
