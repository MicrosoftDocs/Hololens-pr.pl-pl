---
title: Windows Autopilot dla urządzenia HoloLens 2
description: Dowiedz się, jak skonfigurować i rozwiązać problem z rozwiązaniem Autopilot na urządzeniach HoloLens 2.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/13/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Autopilota
manager: jarrettr
ms.openlocfilehash: 9625f3fd1cd6a928f6bd20ba809c750c625143cf
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379787"
---
# <a name="windows-autopilot-for-hololens-2"></a>Windows Autopilot dla urządzenia HoloLens 2

Począwszy od systemu Windows Holographic w wersji 2004, [](https://docs.microsoft.com/mem/autopilot/self-deploying) urządzenie HoloLens 2 obsługuje tryb samodzielnego wdrażania urządzenia Windows Autopilot z systemem Microsoft Intune (rozwiązania MDM innych firm nie są obsługiwane). Administratorzy mogą skonfigurować środowisko out-of-box experience (OOBE) w programie Microsoft Endpoint Manager i umożliwić użytkownikom końcowych przygotowywanie urządzeń do użytku biznesowego przy niewielkiej interakcji lub bez interakcji. Zmniejsza to narzut na zarządzanie zapasami, koszty praktycznego przygotowywania urządzeń i rozmów z pomocą techniczną od pracowników podczas procesu konfiguracji. Dowiedz się więcej z [Windows Autopilot](https://docs.microsoft.com/mem/autopilot/windows-autopilot) dokumentacji.

Podobnie jak w przypadku urządzeń Surface, zaleca się, aby klienci współpracowali z firmą Microsoft [Dostawca rozwiązań w chmurze](https://partner.microsoft.com/cloud-solution-provider) (odsprzedawcą lub dystrybutorem), aby zarejestrować urządzenia w usłudze Autopilot za pośrednictwem Partner Center. Inne metody rejestracji urządzeń są [](https://docs.microsoft.com/mem/autopilot/add-devices) opisane w dokumentacji dodawania urządzeń, chociaż korzystanie z partnerów handlowych firmy Microsoft zapewnia najbardziej efektywną, end-to-end ścieżkę.

> [!NOTE]
> Od 20.11.2020 r. konfiguracja rozwiązania Autopilot dla urządzenia HoloLens na platformie Microsoft Endpoint Manager przechodzi do publicznej **wersji zapoznawczej.** Klienci nie muszą już rejestrować się w prywatnej wersji zapoznawczej, a wszyscy dzierżawcy będą mogli skonfigurować funkcję Autopilot w centrum administracyjnym MEM.

Gdy użytkownik uruchamia proces samodzielnego wdrażania rozwiązania Autopilot, rozwiązanie Autopilot kończy następujące kroki:

1. Dołącz urządzenie do usługi Azure Active Directory (Azure AD). Pamiętaj, że rozwiązanie Autopilot dla urządzenia HoloLens nie obsługuje dołączania do usługi Active Directory ani dołączania hybrydowego do usługi Azure AD.

1. Użyj usługi Azure AD, aby zarejestrować urządzenie w usłudze Microsoft Endpoint Manager (lub innej usłudze MDM).

1. Pobieranie i stosowanie zasad, certyfikatów, profilów sieciowych i aplikacji dla urządzeń docelowych.

1. Aprowizuj urządzenie.

1. Przedstawianie użytkownikowi ekranu logowania.

## <a name="configuring-autopilot-for-hololens-2"></a>Konfigurowanie rozwiązania Autopilot dla urządzenia HoloLens 2

Wykonaj poniższe kroki, aby skonfigurować środowisko:

1. [Zapoznaj się z wymaganiami Windows Autopilot dla urządzenia HoloLens 2.](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [Włączanie automatycznej rejestracji mdm](#2-enable-automatic-mdm-enrollment)

1. [Rejestrowanie urządzeń w Windows Autopilot.](#3-register-devices-in-windows-autopilot)

1. [Utwórz grupę urządzeń.](#4-create-a-device-group)

1. [Utwórz profil wdrożenia.](#5-create-a-deployment-profile)

1. [Sprawdź konfigurację strony ze stanem rejestracji.](#6-verify-the-esp-configuration)

1. [Sprawdź stan profilu urządzeń HoloLens.](#7-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. Przegląd wymagań dotyczących Windows Autopilot dla urządzenia HoloLens 2

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>Zapoznaj się z następującymi sekcjami artykułu Windows Autopilot wymagań:

- [Wymagania dotyczące sieci](https://docs.microsoft.com/mem/autopilot/networking-requirements)  
- [Wymagania dotyczące licencjonowania](https://docs.microsoft.com/mem/autopilot/licensing-requirements)  
- [Wymagania dotyczące konfiguracji](https://docs.microsoft.com/mem/autopilot/configuration-requirements)

**Zapoznaj się z [sekcją](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)"Wymagania" artykułu Windows Autopilot Self-Deploying trybie pracy.** Środowisko musi spełniać te wymagania, a także standardowe wymagania Windows Autopilot wymagań. Nie musisz przeglądać sekcji "Krok po kroku" i "Walidacja" artykułu. Procedury w dalszej części tego artykułu zawierają odpowiednie kroki specyficzne dla urządzenia HoloLens.

Aby uzyskać informacje na temat rejestrowania urządzeń i konfigurowania profilów, zobacz [2. Rejestrowanie urządzeń w Windows Autopilot](#3-register-devices-in-windows-autopilot) i [4. Utwórz profil wdrożenia w](#5-create-a-deployment-profile) tym artykule. Aby skonfigurować profile trybu samodzielnego wdrażania rozwiązania Autopilot i zarządzać nimi, upewnij się, że masz dostęp do usługi [Microsoft Endpoint Manager administracyjnego.](https://endpoint.microsoft.com)

#### <a name="review-hololens-os-requirements"></a>Zapoznaj się z wymaganiami systemu operacyjnego HoloLens:

- Urządzenia muszą być w systemie Windows Holographic w wersji [2004](hololens-release-notes.md#windows-holographic-version-2004) (kompilacja 19041.1103) lub nowszej. Aby potwierdzić wersję kompilacji na urządzeniu lub ponownie flashować do najnowszej wersji systemu operacyjnego, użyj narzędzia [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) i instrukcji ponownego [flashuj nasze urządzenie.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device) Należy pamiętać, że urządzenia dostarczane do końca września 2020 r. mają wstępnie zainstalowany system Windows Holographic w wersji 1903. Skontaktuj się z odsprzedawcą, aby upewnić się, że urządzenia gotowe do rozwiązania Autopilot są wysyłane do Ciebie.

- System Windows Holographic w wersji 2004 obsługuje tylko połączenie rozwiązania Autopilot za pośrednictwem sieci Ethernet. Przed włączeniem urządzenia HoloLens upewnij się, że urządzenie HoloLens jest podłączone do sieci Ethernet przy użyciu adaptera "USB-C to **Ethernet".** Podczas rozruchu urządzenia nie jest wymagana żadna interakcja użytkownika. Jeśli planujesz użycie rozwiązania Autopilot na wielu urządzeniach HoloLens, zalecamy zaplanowanie infrastruktury adaptera. Nie zalecamy koncentratorów USB, ponieważ często wymagają one zainstalowania dodatkowych sterowników innych firm, które nie są obsługiwane na urządzeniach HoloLens.

- [System Windows Holographic w wersji 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (kompilacja 19041.1128) lub nowszej obsługuje funkcję Autopilot za pośrednictwem sieci Wi-Fi, chociaż nadal można używać kart Ethernet. W przypadku urządzeń połączonych za pośrednictwem sieci Wi-Fi użytkownik musi tylko:

     - Przejdź przez scenę z ploterami
     - Wybieranie języka i ustawieniach regionalnych
     - Uruchamianie z okiem
     - Nawiązywanie połączenia sieciowego

- System Windows Holographic w wersji 20H2 obsługuje rozwiązania [Tenantlockdown CSP i Autopilot,](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)które blokuje urządzenie do dzierżawy i zapewniają, że urządzenie pozostanie powiązane z dzierżawą w razie przypadkowego lub zamierzonego zresetowania lub wyczyszczenia danych.  

- Upewnij się, że urządzenia nie są jeszcze członkami usługi Azure AD i nie są zarejestrowane w usłudze Intune (ani w innym systemie MDM). Proces samodzielnego wdrażania rozwiązania Autopilot kończy te kroki. Aby upewnić się, że wszystkie informacje dotyczące urządzenia  są czyszczone, sprawdź strony Urządzenia w portalach usługi Azure AD i Intune. Pamiętaj, że funkcja "Konwertuj wszystkie urządzenia docelowe na funkcję Autopilot" nie jest obecnie obsługiwana na urządzeniu HoloLens.  

### <a name="2-enable-automatic-mdm-enrollment"></a>2. Włącz automatyczną rejestrację mdm:

Aby rozwiązanie Autopilot zakończyło się powodzeniem, należy włączyć automatyczne rejestrowanie mdm w Azure Portal. Umożliwi to rejestrowanie urządzenia bez użytkownika.

W [Azure Portal](https://portal.azure.com/#home) wybierz **pozycję Azure Active Directory** Mobility  ->  **(MDM i MAM)**  ->  **Microsoft Intune**. Następnie skonfiguruj **zakres użytkownika rozwiązania MDM,** a następnie wybierz pozycję **Wszystkie.**

Zapoznaj się z następującym krótkim przewodnikiem na temat włączania automatycznego rejestrowania w u [rozwiązaniach MDM](https://docs.microsoft.com/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) lub przewodnikiem Szybki [start](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment) dotyczący automatycznego rejestrowania, aby uzyskać jeszcze więcej informacji na temat konfiguracja.

### <a name="3-register-devices-in-windows-autopilot"></a>3. Rejestrowanie urządzeń w Windows Autopilot

Urządzenia muszą zostać zarejestrowane w u Windows Autopilot przed pierwszą konfiguracją. Aby uzyskać dokumentację MEM dotyczącą rejestracji urządzeń, zobacz [Adding devices to Autopilot (Dodawanie urządzeń do rozwiązania Autopilot).](https://docs.microsoft.com/mem/autopilot/add-devices)  

Istnieją trzy podstawowe sposoby rejestrowania urządzeń HoloLens:

 - **Odsprzedawca może zarejestrować urządzenia w Partner Center podczas zamawiania.**

   > [!NOTE]  
   > Jest to zalecana ścieżka dodawania urządzeń do usługi Autopilot. [Dowiedz się więcej](https://docs.microsoft.com/mem/autopilot/partner-registration).  

 - **Wniosek [o pomoc techniczną możesz przesłać](hololens2-autopilot-registration-support.md) bezpośrednio do firmy Microsoft.**
 - Pobierz skrót sprzętu (znany również jako identyfikator sprzętu) i zarejestruj urządzenie ręcznie w **centrum administracyjnym MEM.**

#### <a name="obtain-hardware-hash"></a>Uzyskiwanie skrótu sprzętu
Istnieją dwa sposoby pobierania skrótu sprzętu.
1. Wniosek [o pomoc techniczną możesz przesłać](hololens2-autopilot-registration-support.md) bezpośrednio do firmy Microsoft.
2. Można go pobrać z urządzenia. Urządzenie rejestruje skrót sprzętu w pliku CSV podczas procesu OOBE lub później, gdy właściciel urządzenia uruchamia proces zbierania dzienników diagnostycznych (opisany w poniższej procedurze). Zazwyczaj właściciel urządzenia jest pierwszym użytkownikiem, który loguje się do urządzenia.
     > [!WARNING]
     > W kompilacjach wcześniejszych niż 20H2, jeśli przeszliśmy przez tryb OOBE i ustawiono telemetrię Na wymagane, nie można zebrać skrótu sprzętu dla rozwiązania Autopilot za pomocą tej metody. W celu zebrania skrótu sprzętu za pomocą tej metody ustaw opcję telemetrii na Wartość pełna za pośrednictwem aplikacji Ustawienia i wybierz pozycję Prywatność —> diagnostyki.

    1. Uruchom urządzenie HoloLens 2.

    1. Na urządzeniu naciśnij jednocześnie przyciski **Power i** **Volume Down,** a następnie zwolnij je. Urządzenie zbiera dzienniki diagnostyczne i skrót sprzętu i zapisuje je w zestawie plików .zip danych.

   1. Aby uzyskać szczegółowe informacje i instruktażowy film wideo na temat wstępnego sformułowania tego tematu, przeczytaj informacje na temat diagnostyki [w trybie offline.](hololens-diagnostic-logs.md#offline-diagnostics)

    1. Podłącz urządzenie do komputera za pomocą kabla USB-C.

    1. Na komputerze otwórz Eksplorator plików. Otwórz **program This PC Internal Storage \\ \<*HoloLens device name*> \\ \\ Documents** i znajdź AutopilotDiagnostics.zip magazynu.  

       > [!NOTE]  
       > Plik .zip może nie być natychmiast dostępny. Jeśli plik nie jest jeszcze gotowy, w folderze Documents może zostać wyświetlony plik HoloLensDiagnostics.temp. Aby zaktualizować listę plików, odśwież okno.
    
    1. Wyodrębnij zawartość AutopilotDiagnostics.zip pliku.

    1. W wyodrębnianych plikach znajdź plik CSV z prefiksem nazwy pliku "DeviceHash". Skopiuj ten plik na dysk na komputerze, na którym będzie można później uzyskać do niego dostęp.  

       > [!IMPORTANT]  
       > Dane w pliku CSV powinny mieć następujący format nagłówka i wiersza:
       > ```
       > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
       >```

#### <a name="register-device-through-mem"></a>Rejestrowanie urządzenia za pośrednictwem MEM

1. W [centrum administracyjnym Endpoint Manager](https://endpoint.microsoft.com) Microsoft wybierz pozycję Urządzenia Rejestracja systemu Windows w systemie Windows, a następnie wybierz pozycję Urządzenia  >    >     >  **Importuj** w **obszarze Windows Autopilot Deployment Program.**

1. W **obszarze Windows Autopilot urządzenia** wybierz plik CSV DeviceHash, wybierz pozycję **Otwórz,** a następnie wybierz pozycję **Importuj.**  

   > [!div class="mx-imgBorder"]
   > ![Za pomocą polecenia Importuj zaimportuj skrót sprzętu.](./images/hololens-ap-hash-import.png)

1. Po zakończeniu importowania wybierz pozycję **Urządzenia** Rejestracja urządzeń  >  **z** systemem Windows  >    >  **Synchronizacja** urządzeń z systemem  >  **Windows.** Proces może potrwać kilka minut, w zależności od tego, ile urządzeń jest synchronizowanych. Aby wyświetlić zarejestrowane urządzenie, wybierz pozycję **Odśwież.**  

   > [!div class="mx-imgBorder"]
   > ![Użyj poleceń Synchronizuj i Odśwież, aby wyświetlić listę urządzeń.](./images/hololens-ap-devices-sync.png)  

### <a name="4-create-a-device-group"></a>4. Tworzenie grupy urządzeń

1. W [centrum administracyjnym Endpoint Manager Microsoft wybierz](https://endpoint.microsoft.com)pozycję Grupy **Nowa**  >  **grupa.**

1. W **polu Typ grupy** wybierz pozycję **Zabezpieczenia**, a następnie wprowadź nazwę i opis grupy.

1. W **przypadku opcji Typ** członkostwa wybierz pozycję **Przypisane** lub **Urządzenie dynamiczne.**

1. Wykonaj jedną z następujących czynności:  

   - Jeśli w poprzednim **kroku wybrano** **opcję** Przypisane dla typu członkostwa, wybierz pozycję **Członkowie**, a następnie dodaj urządzenia rozwiązania Autopilot do grupy. Urządzenia rozwiązania Autopilot, które nie zostały jeszcze zarejestrowane, są wyświetlane przy użyciu numeru seryjnego urządzenia jako nazwy urządzenia.
   - Jeśli w poprzednim  **kroku** jako typ członkostwa wybrano pozycję Urządzenia dynamiczne,  wybierz pozycję Dynamiczne **elementy** członkowskie urządzenia, a następnie wprowadź kod w regułę zaawansowaną, która będzie wyglądać następująco:
     - Aby utworzyć grupę obejmującą wszystkie urządzenia rozwiązania Autopilot, wpisz: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Pole tagu grupy usługi Intune jest mapowanie na atrybut **OrderID** na urządzeniach usługi Azure AD. Jeśli chcesz utworzyć grupę, która zawiera wszystkie urządzenia rozwiązania Autopilot z określonym tagiem grupy (OrderID urządzenia usługi Azure AD), musisz wpisać: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - Jeśli chcesz utworzyć grupę, która zawiera wszystkie urządzenia rozwiązania Autopilot, które mają określony identyfikator zamówienia zakupu, wpisz: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > Te reguły mają na celu atrybuty, które są unikatowe dla urządzeń rozwiązania Autopilot.
1. Wybierz **pozycję Zapisz,** a następnie wybierz **pozycję Utwórz.**

### <a name="5-create-a-deployment-profile"></a>5. Tworzenie profilu wdrożenia

1. W [centrum administracyjnym Endpoint Manager](https://endpoint.microsoft.com)Microsoft wybierz pozycję Urządzenia Rejestracja w systemie Windows Windows Autopilot wdrożenia  >    >    >  **Utwórz**  >  **profil**  >  **Urządzenia HoloLens.**
   ![Lista rozwijana Tworzenie profilu zawiera element HoloLens.](./images/hololens-ap-enrollment-profiles.png)

1. Wprowadź nazwę i opis profilu, a następnie wybierz pozycję **Dalej.**  
   Powinna zostać wyświetlona lista z urządzeniem **HoloLens**. Jeśli ta opcja nie istnieje, użyj jednej z opcji [opinii,](hololens2-autopilot.md#feedback-and-support-for-autopilot) aby się z nami skontaktować.

   > [!div class="mx-imgBorder"]
   > ![Dodawanie nazwy i opisu profilu](./images/hololens-ap-profile-name.png)

1. Na stronie **Środowisko out-of-box experience (OOBE)** większość ustawień jest wstępnie skonfigurowana w celu usprawnienia procesu OOBE na czas tej oceny. Opcjonalnie można skonfigurować następujące ustawienia:  

   - **Język (region):** wybierz język dla OOBE. Zalecamy wybranie języka z listy obsługiwanych języków [dla urządzenia HoloLens 2.](hololens2-language-support.md)
   - **Automatycznie skonfiguruj klawiaturę:** aby upewnić się, że klawiatura jest taka jak wybrany język, wybierz pozycję **Tak.**
   - Zastosuj szablon nazwy **urządzenia:** aby automatycznie ustawić nazwę  urządzenia podczas OOBE, wybierz  pozycję Tak, a następnie wprowadź frazę szablonu i symbole zastępcze w sekcji Wprowadź nazwę. Na przykład wprowadź prefiks i symbol zastępczy dla czterocyfrowej liczby `%RAND:4%` &mdash; losowej.
     > [!NOTE]  
     > Jeśli korzystasz z szablonu nazwy urządzenia, proces OOBE ponownie uruchamia urządzenie jeszcze raz po naliłączeniu nazwy urządzenia do usługi Azure AD. To ponowne uruchomienie umożliwia włączenie nowej nazwy.  

   > [!div class="mx-imgBorder"]
   > ![Konfigurowanie ustawień OOBE](./images/hololens-ap-profile-oobe.png)

1. Po skonfigurowaniu ustawień wybierz pozycję **Dalej.**
1. Na stronie **Tagi zakresu** opcjonalnie dodaj tagi zakresu, które chcesz zastosować do tego profilu. Więcej informacji na temat tagów zakresu można znaleźć w artykule [Używanie kontroli dostępu opartej na rolach (RBAC) i tagów zakresu w rozproszonej infrastrukturze informatycznej](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md). Po zakończeniu wybierz przycisk **Dalej**.
1. Na stronie **Przypisania wybierz** pozycję Wybrane **grupy** w celu **przypisania do**.
1. W **obszarze WYBRANE GRUPY** wybierz pozycję + Wybierz grupy do **dołączyć**.
1. Na liście **Wybierz grupy do dołączyć** wybierz grupę urządzeń utworzoną dla urządzeń HoloLens rozwiązania Autopilot, a następnie wybierz pozycję **Dalej.**  
  
   Jeśli chcesz wykluczyć jakiekolwiek grupy, wybierz pozycję Wybierz **grupy** do wykluczenia i wybierz grupy, które chcesz wykluczyć.

   > [!div class="mx-imgBorder"]
   > ![Przypisywanie grupy urządzeń do profilu.](./images/hololens-ap-profile-assign-devicegroup.png)

1. Na stronie **Przeglądanie + tworzenie** przejrzyj ustawienia, a następnie wybierz pozycję **Utwórz,** aby utworzyć profil.  

   > [!div class="mx-imgBorder"]
   > ![Przeglądanie i tworzenie](./images/hololens-ap-profile-summ.png)

### <a name="6-verify-the-esp-configuration"></a>6. Weryfikowanie konfiguracji esp

Strona ze stanem rejestracji wyświetla stan kompletnego procesu konfiguracji urządzenia, który jest uruchamiany, gdy użytkownik zarządzany przez rozwiązanie MDM po raz pierwszy logowania się do urządzenia. Upewnij się, że konfiguracja esp przypomina następującą, i sprawdź, czy przypisania są poprawne.  

> [!div class="mx-imgBorder"]
> ![Konfiguracja esp](./images/hololens-ap-profile-settings.png)

### <a name="7-verify-the-profile-status-of-the-hololens-devices"></a>7. Sprawdzanie stanu profilu urządzeń HoloLens

1. W centrum administracyjnym Endpoint Manager Microsoft wybierz pozycję **Urządzenia Urządzenia z**  >  **rejestracją systemu Windows** Urządzenia z systemem  >  **Windows.**  >  

1. Sprawdź, czy na liście znajdują się urządzenia HoloLens oraz czy ich stan profilu **to Przypisane.**  

   > [!NOTE]  
   > Przypisanie profilu do urządzenia może potrwać kilka minut.  

   > [!div class="mx-imgBorder"]
   > ![Przypisania urządzeń i profilów.](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>Windows Autopilot dla urządzenia HoloLens 2

Po zakończeniu powyższych instrukcji użytkownicy urządzenia HoloLens 2 przejdą przez następujące środowisko, aby aprowizować swoje urządzenia HoloLens:  

1. Środowisko rozwiązania Autopilot wymaga dostępu do Internetu. Aby zapewnić dostęp do Internetu, użyj jednej z następujących opcji:

    - Połącz urządzenie z siecią Wi-Fi OOBE, a następnie pozwól, aby automatycznie wykrywało środowisko rozwiązania Autopilot. Jest to jedyny czas, gdy trzeba będzie korzystać z funkcji OOBE, dopóki środowisko rozwiązania Autopilot nie zostanie ukończone samodzielnie. Pamiętaj, że domyślnie urządzenie HoloLens 2 czeka 10 sekund na wykrycie rozwiązania Autopilot po wykryciu Internetu. Jeśli w ciągu 10 sekund nie zostanie wykryty żaden profil rozwiązania Autopilot, program OOBE przedstawi eula. Jeśli napotkasz ten scenariusz, uruchom ponownie urządzenie, aby można było spróbować wykryć funkcję Autopilot. Należy również pamiętać, że funkcja OOBE może czekać na funkcję Autopilot przez czas nieokreślony tylko wtedy, gdy na urządzeniu są ustawione zasady TenantLockdown.

    - Podłącz urządzenie za pomocą sieci Ethernet przy użyciu adapterów "USB-C do Ethernet" w celu przewodowego połączenia z Internetem i pozwól urządzeniu HoloLens 2 automatycznie korzystać z rozwiązania Autopilot.

    - Podłącz urządzenie za pomocą adapterów "USB-C do sieci Wi-Fi" w celu bezprzewodowego połączenia z Internetem i pozwól urządzeniu HoloLens 2 automatycznie ukończyć środowisko rozwiązania Autopilot.

        > [!IMPORTANT]  
       > Urządzenia próbujące korzystać z Wi-Fi w trybie OOBE dla rozwiązania Autopilot muszą być na platformie Windows Holographic w wersji [20H2.](hololens-release-notes.md#windows-holographic-version-20h2)
       >
       > W przypadku urządzeń korzystających z kart Ethernet należy podłączyć urządzenie do sieci przed rozpoczęciem korzystania z technologii OOBE (Out-of-the-Box-Experience). Urządzenie określa, czy aprowizuje jako urządzenie rozwiązania Autopilot na pierwszym ekranie OOBE. Jeśli urządzenie nie może nawiązać połączenia z siecią lub jeśli nie chcesz aprowizować urządzenia jako urządzenia rozwiązania Autopilot, nie możesz później zmienić aprow na aprowizowanie rozwiązania Autopilot. Zamiast tego należy uruchomić tę procedurę od początku, aby aprowizować urządzenie jako urządzenie rozwiązania Autopilot.

1. Urządzenie powinno automatycznie uruchomić OOBE. Nie należy wchodzić w interakcje z OOBE. Zamiast tego usiądź, wrócisz i zrelaksuj. Pozwól, aby urządzenie HoloLens 2 wykryło łączność sieciową i zezwoliło na automatyczne ukończenie procesu OOBE. Urządzenie może zostać uruchomione ponownie podczas OOBE. Ekrany OOBE powinny wyglądać następująco.

   ![OOBE krok 1 ](./images/autopilot-welcome.jpg)
    ![ OOBE krok 2 ](./images/autopilot-step-complete.jpg)
    ![ OOBE krok 3](./images/autopilot-device-setup.jpg)

1. Na końcu OOBE możesz zalogować się na urządzeniu przy użyciu swojej nazwy użytkownika i hasła.

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP and Autopilot

Urządzenia HoloLens 2 obsługują program TenantLockdown CSP od systemu Windows Holographic w wersji 20H2. Ten program CSP utrzymuje urządzenia w dzierżawie organizacji, blokując je dla tej dzierżawy nawet za pośrednictwem resetowania urządzenia lub reflashu.

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) Zasady CSP umożliwiają wiązanie urządzenia HoloLens 2 z rejestracją MDM tylko przy użyciu rozwiązania Autopilot. Gdy węzeł RequireNetworkInOOBE w programie TenantLockdown CSP zostanie ustawiony na wartość true lub false (początkowo ustawioną) na urządzeniu HoloLens 2, ta wartość pozostanie na urządzeniu pomimo ponownego flashowania, aktualizacji systemu operacyjnego itp.

Gdy węzeł RequireNetworkInOOBE dostawcy CSP TenantLockdown zostanie ustawiony na wartość true na urządzeniach HoloLens 2, system OOBE czeka przez czas nieokreślony na pomyślne pobranie i zastosowanie profilu rozwiązania Autopilot po napięciu sieciowym.

Gdy węzeł RequireNetworkInOOBE dla dzierżawcy TenantLockdown zostanie ustawiony na wartość true na urządzeniach HoloLens 2, następujące operacje są niedozwolone w OOBE:

- Tworzenie użytkownika lokalnego przy użyciu aprowizowania środowiska uruchomieniowego 
- Wykonywanie operacji dołączania do usługi Azure AD za pośrednictwem aprowizowania środowiska uruchomieniowego 
- Wybieranie, kto jest właścicielem urządzenia w środowisko OOBE 

#### <a name="how-to-set-this-using-intune"></a>Jak ustawić tę wartość przy użyciu usługi Intune? 
1. Utwórz niestandardowy profil konfiguracji urządzenia OMA URI i określ wartość true dla węzła RequireNetworkInOOBE, jak pokazano poniżej.
Wartość OMA-URI powinna być ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Ustawianie blokady czasowej za pośrednictwem OMA-URI](images/hololens-tenant-lockdown.png)

1. Utwórz grupę i przypisz profil konfiguracji urządzenia do tej grupy urządzeń.

1. Dokonaj synchronizacji urządzenia HoloLens 2 w grupie utworzonej w poprzednim kroku i wyzwolij synchronizację.  

Sprawdź w portalu usługi Intune, czy konfiguracja urządzenia została pomyślnie zastosowana. Po pomyślnym zastosowaniem tej konfiguracji urządzenia na urządzeniu HoloLens 2 efekty ustawienia TenantLockdown będą aktywne.

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>Jak zdezsetować usługę TenantLockdown z usługi RequireNetworkInOOBE na urządzeniach HoloLens 2 przy użyciu usługi Intune?

1. Usuń urządzenie HoloLens 2 z grupy urządzeń, do której wcześniej przypisano utworzoną wcześniej konfigurację urządzenia.

1. Utwórz niestandardowy profil konfiguracji urządzenia oparty na interfejsie OMA URI i określ wartość false dla wartości RequireNetworkInOOBE, jak pokazano poniżej.
Wartość OMA-URI powinna być ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![Zrzut ekranu przedstawiający ustawianie wartości false dla ustawienia RequireNetworkInOOBE za pośrednictwem adresu URI OMA w usłudze Intune](images/hololens-tenant-lockdown-false.png)

1. Utwórz grupę i przypisz profil konfiguracji urządzenia do tej grupy urządzeń. 

1. Dokonaj synchronizacji urządzenia HoloLens 2 w grupie utworzonej w poprzednim kroku i wyzwolij synchronizację.

Sprawdź w portalu usługi Intune, czy konfiguracja urządzenia została pomyślnie zastosowana. Po pomyślnym zastosowaniem tej konfiguracji urządzenia na urządzeniu HoloLens 2 efekty ustawienia TenantLockdown będą nieaktywne.

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>Co się stanie podczas OOBE, jeśli profil rozwiązania Autopilot zostanie nieprzypisane na urządzeniach HoloLens po tym, jak ustawienie TenantLockdown miało wartość true? 
OOBE będzie czekać przez czas nieokreślony na pobranie profilu rozwiązania Autopilot i zostanie wyświetlone następujące okno dialogowe. Aby usunąć skutki ustawienia TenantLockdown, urządzenie musi najpierw zostać zarejestrowane w pierwotnej dzierżawie przy użyciu rozwiązania Autopilot, a opcja RequireNetworkInOOBE musi zostać cofnięciem ustawienia zgodnie z opisem w poprzednim kroku przed usunięciem ograniczeń wprowadzonych przez usługę TenantLockdown CSP.

![Widok na urządzeniu dla sytuacji, gdy zasady są wymuszane na urządzeniu.](images/hololens-autopilot-lockdown.png)

## <a name="known-issues--limitations"></a>Znane problemy & ograniczenia

- Badamy problem, który powoduje, że instalacja aplikacji opartej na kontekście urządzenia skonfigurowana w programie MEM nie ma zastosowania do urządzenia HoloLens. [Dowiedz się więcej na temat instalacji kontekstu urządzenia i kontekstu użytkownika.](https://docs.microsoft.com/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- Podczas konfigurowania rozwiązania Autopilot za pośrednictwem sieci Wi-Fi może wystąpić wystąpienie, w którym profil rozwiązania Autopilot nie zostanie pobrany po pierwszym nawiązaniu połączenia internetowego. W takim przypadku zostanie przedstawiona umowa licencyjna użytkownika oprogramowania (EULA), a użytkownik będzie mieć możliwość kontynuowania pracy z konfiguracją bez rozwiązania Autopilot. Aby ponowić próbę skonfigurowania rozwiązania Autopilot, umieść urządzenie w stanie uśpienia, a następnie uruchom je, lub uruchom ponownie urządzenie i spróbuj ponownie.
- Funkcja "Konwertuj wszystkie urządzenia docelowe do rozwiązania Autopilot" nie jest obecnie obsługiwana na urządzeniu HoloLens.  

### <a name="troubleshooting"></a>Rozwiązywanie problemów

Następujące artykuły mogą być przydatnym zasobem, który pozwala uzyskać więcej informacji i rozwiązywać problemy z rozwiązaniem Autopilot, należy jednak pamiętać, że te artykuły są oparte na programie Windows 10 Desktop i nie wszystkie informacje mogą dotyczyć urządzenia HoloLens:

- [Windows Autopilot — znane problemy](https://docs.microsoft.com/mem/autopilot/known-issues)
- [Rozwiązywanie problemów dotyczących rejestrowania urządzeń z systemem Windows w usłudze Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot — konflikty zasad](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a>Opinie i pomoc techniczna dla rozwiązania Autopilot

Aby przekazać opinię lub zgłosić problemy, użyj jednej z następujących metod:

- Aby uzyskać pomoc techniczną w zakresie rejestracji urządzeń, skontaktuj się z odsprzedawcą lub dystrybutorem.
- W przypadku ogólnych zapytań pomocy technicznej dotyczących Windows Autopilot problemów, takich jak przypisania profilów, tworzenie grup lub kontrolki portalu MEM, skontaktuj się z pomocą techniczną [firmy Microsoft Endpoint Manager technicznej](https://docs.microsoft.com/mem/get-support)  
- Jeśli urządzenie jest zarejestrowane w usłudze Autopilot, a profil jest przypisany w [](https://docs.microsoft.com/hololens/) portalu MEM, skontaktuj się z pomocą techniczną urządzenia HoloLens (zobacz kartę "Pomoc techniczna"). Otwórz bilet pomocy technicznej i, jeśli ma to zastosowanie, dołącz zrzuty ekranu i dzienniki, przechwytując dzienniki diagnostyczne w trybie [offline](hololens-diagnostic-logs.md#offline-diagnostics) podczas procesu OOBE (out-of-box-experience).
- Aby zgłosić problem z urządzenia, użyj aplikacji Centrum opinii na urządzeniu HoloLens. W Centrum opinii wybierz **kategorię Enterprise Management**  >  **Device.**
- Aby przekazać ogólną opinię na temat rozwiązania Autopilot dla urządzenia HoloLens, możesz przesłać tę [ankietę](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)
