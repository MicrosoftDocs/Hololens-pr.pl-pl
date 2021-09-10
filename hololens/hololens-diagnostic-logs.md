---
title: Zbieranie i używanie informacji diagnostycznych z HoloLens urządzeń
description: Dowiedz się, jak zbierać, używać i zachowywać informacje diagnostyczne z HoloLens urządzeń.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/15/2020
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
ms.custom:
- CI 115131
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: medium
keywords: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 082a263bdd7eba694c13124abf40763644c83dfa
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428685"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>Zbieranie i używanie informacji diagnostycznych z HoloLens urządzeń

HoloLens użytkownicy i administratorzy mogą wybierać spośród czterech różnych metod zbierania informacji diagnostycznych z HoloLens:

- Centrum opinii aplikacji
- DiagnosticLog CSP
- Ustawienia aplikacji
- Diagnostyka w trybie offline

> [!IMPORTANT]  
> Dzienniki diagnostyczne urządzeń zawierają dane osobowe, takie jak procesy lub aplikacje, które użytkownik uruchamia podczas typowych operacji. Jeśli wielu użytkowników współużytkuje urządzenie z systemem HoloLens (na przykład użytkownicy logują się na tym samym urządzeniu przy użyciu różnych kont usługi Microsoft Azure Active Directory (Azure AD), dzienniki diagnostyczne mogą zawierać informacje osobowe dotyczące wielu użytkowników. Aby uzyskać więcej informacji, zobacz [Zasady zachowania poufności informacji firmy Microsoft.](https://privacy.microsoft.com/privacystatement)

W poniższej tabeli porównano różne metody zbierania. Nazwy metod są linkami do bardziej szczegółowych informacji w sekcjach, które są zgodne z tabelą.

|Metoda |Wymagania wstępne |Lokalizacje danych |Dostęp do danych i ich użycie |Przechowywanie danych |
| --- | --- | --- | --- | --- |
|[Centrum opinii](#feedback-hub) |Połączenie sieciowe i internetowe<br /><br />Centrum opinii aplikacji<br /><br />Uprawnienie do przekazywania plików do chmury firmy Microsoft |Chmura firmy Microsoft<br /><br />HoloLens (opcjonalnie) |Użytkownik żąda pomocy, akceptuje warunki użytkowania i przesyła dane<br /><br />Pracownicy firmy Microsoft mogą wyświetlać dane zgodnie z warunkami użytkowania |Dane w chmurze są przechowywane przez okres zdefiniowany przez zasady ochrony prywatności nowej generacji (NGP). Następnie dane są usuwane automatycznie.<br /><br />Dane na urządzeniu mogą zostać usunięte w dowolnym momencie przez użytkownika, który ma **uprawnienia właściciela urządzenia** lub **administratora.** |
|[Ustawienia Rozwiązywania](#settings-troubleshooter) |Ustawienia aplikacji |Urządzenie HoloLens<br /><br />Połączony komputer (opcjonalnie) |Użytkownik przechowuje dane i tylko ten użytkownik uzyskuje dostęp do danych (chyba że użytkownik udostępnia te dane in inowi użytkownikowi). |Dane są przechowywane na urządzeniu do momentu usunięcia ich przez użytkownika.* |
|[DiagnosticLog CSP](#diagnosticlog-csp) |Połączenie sieciowe<br /><br />Środowisko MDM obsługujące program DiagnosticLog CSP |Administrator konfiguruje lokalizacje magazynu |W środowisku zarządzanym użytkownik niejawnie wyraża zgodę na dostęp administratora do danych.<br /><br />Administrator konfiguruje role dostępu i uprawnienia. | Dane są przechowywane w magazynie w chmurze, a administrator konfiguruje zasady przechowywania. |
|[Diagnostyka w trybie offline](#offline-diagnostics) |Konfiguracja urządzenia:<ul><li>Włączone i połączone z komputerem</li><li>Przyciski zasilania i regulacji głośności działają</li></ul> |Urządzenie HoloLens<br /><br />Połączony komputer |Użytkownik przechowuje dane i tylko ten użytkownik uzyskuje dostęp do danych (chyba że użytkownik udostępnia te dane in inowi użytkownikowi). |Dane są przechowywane na urządzeniu do momentu usunięcia ich przez użytkownika. |

* Użytkownik końcowy jest odpowiedzialny za odpowiedzialne udostępnianie dzienników innej osobie. Te pliki są przydatne głównie podczas kontaktowania się z działem obsługi klienta i pomocą techniczną.  

## <a name="feedback-hub"></a>Centrum opinii

Użytkownik HoloLens może używać aplikacji klasycznej Microsoft Centrum opinii do wysyłania informacji diagnostycznych do Pomoc techniczna Microsoft. Aby uzyskać szczegółowe informacje i pełne instrukcje, zobacz [Temat Daj nam swoją opinię.](hololens-feedback.md)  

> [!NOTE]  
> **Użytkownicy komercyjni lub przedsiębiorstwa:** Jeśli używasz aplikacji Centrum opinii do zgłaszania problemu związanego z zarządzaniem urządzeniami przenośnymi, aprowizą lub innym aspektem zarządzania urządzeniami, zmień kategorię aplikacji na **kategorię Enterprise Management**  >  **Device**.

>[!IMPORTANT]
> Aby zapewnić najlepsze możliwe dane do rozwiązywania problemów, zdecydowanie zalecamy ustawienie opcji Telemetria urządzenia na **wartość Opcjonalne.** Tę wartość można ustawić podczas korzystania z out-of-box-experience (OOBE) lub przy **użyciu Ustawienia** aplikacji. Aby to zrobić przy użyciu Ustawienia, wybierz pozycję Uruchom > Ustawienia > prywatność > **diagnostyki aplikacji >.**
### <a name="prerequisites"></a>Wymagania wstępne

- Urządzenie jest połączone z siecią.
- Aplikacja Centrum opinii jest dostępna na komputerze stacjonarnym użytkownika, a użytkownik może przekazywać pliki do chmury firmy Microsoft.

### <a name="data-locations-access-and-retention"></a>Lokalizacje danych, dostęp i przechowywanie

Wyrażając zgodę na warunki użytkowania usługi Centrum opinii, użytkownik jawnie wyraża zgodę na przechowywanie i używanie danych (zgodnie z definicją w tej umowie).

W Centrum opinii użytkownik może przechowywać informacje diagnostyczne w dwóch miejscach:

- **Chmura firmy Microsoft.** Dane, które użytkownik przekaże za pomocą aplikacji Centrum opinii, są przechowywane przez liczbę dni, która jest zgodna z wymaganiami dotyczącymi ochrony prywatności nowej generacji (NGP). Pracownicy firmy Microsoft mogą używać przeglądarki zgodnej z NGP, aby uzyskać dostęp do informacji w tym okresie.

   > [!NOTE]  
   > Te wymagania dotyczą danych we wszystkich Centrum opinii kategorii.

- **Urządzenie HoloLens .** Podczas tworzenia raportu w Centrum opinii użytkownik może wybrać pozycję Zapisz lokalną kopię diagnostyki i załączników utworzonych podczas **zgłaszania opinii.** Jeśli użytkownik wybierze tę opcję, Centrum opinii przechowuje kopię informacji diagnostycznych na urządzeniu HoloLens danych. Te informacje pozostają dostępne dla użytkownika (lub każdego, kto używa tego konta do logowania się do HoloLens). Aby usunąć te informacje, użytkownik musi  mieć uprawnienia **właściciela urządzenia** lub administratora na urządzeniu. Użytkownik, który ma odpowiednie uprawnienia, może zalogować się do witryny Centrum opinii, wybrać Ustawienia Wyświetlić dzienniki  >  **diagnostyczne** i usunąć informacje.

## <a name="settings-troubleshooter"></a>Ustawienia Rozwiązywania

Użytkownik HoloLens może używać aplikacji **Ustawienia** na urządzeniu do rozwiązywania problemów i zbierania informacji diagnostycznych. W tym celu wykonaj następujące kroki:

1. Otwórz aplikację Ustawienia i wybierz **stronę & rozwiązywanie problemów z**  >  **zabezpieczeniami.**
1. Wybierz odpowiedni obszar, a następnie wybierz pozycję **Uruchom.**
1. Odtwórz problem.
1. Po odtworzeniu problemu wróć do Ustawienia a następnie wybierz pozycję **Zatrzymaj**.

Użytkownik może również skonfigurować zachowanie diagnostyki rezerwowej z **Ustawienia** aplikacji. Przejdź do **strony Privacy -> Troubleshooting (Prywatność** i > rozwiązywania problemów), aby skonfigurować to ustawienie.
> [!NOTE]
> Jeśli dla urządzenia skonfigurowano zasady zarządzania urządzeniami przenośnymi, użytkownik nie będzie mógł przesłonić tego zachowania.

### <a name="os-update-troubleshooter"></a>Narzędzie do rozwiązywania problemów z aktualizacjami systemu operacyjnego
W kompilacjach [Windows Holographic, wersja 21H1](hololens-release-notes.md#windows-holographic-version-21h1) i nowsza:
- Oprócz poprzednich funkcji rozwiązywania problemów w aplikacji Ustawienia dodano nowe narzędzie do rozwiązywania problemów wraz z dodaniem nowej aplikacji Ustawienia aktualizacji systemu operacyjnego. Przejdź do **Ustawienia -> Update & Security -> Troubleshoot -> Windows Update** (Rozwiązywanie problemów z > Windows Update) i wybierz pozycję **Start .** Dzięki temu można zbierać ślady podczas odtwarzania problemu z aktualizacjami systemu operacyjnego, aby pomóc w lepszym rozwiązywaniu problemów z chmurze lub pomocą techniczną.
### <a name="prerequisites"></a>Wymagania wstępne

- Aplikacja **Ustawienia** jest zainstalowana na urządzeniu i jest dostępna dla użytkownika.

### <a name="data-locations-access-and-retention"></a>Lokalizacje danych, dostęp i przechowywanie

Ponieważ użytkownik uruchamia zbieranie danych, niejawnie wyraża zgodę na przechowywanie informacji diagnostycznych. Tylko użytkownik lub każda osoba, której użytkownik udostępnia dane, może uzyskać dostęp do danych.

Informacje diagnostyczne są przechowywane na urządzeniu. Jeśli urządzenie jest podłączone do komputera użytkownika, informacje znajdują się również na komputerze w następującym pliku:

> Ten komputer \\ \<*HoloLens device name*> \\ wewnętrzny Storage \\ \\ śledzenia \<*ddmmyyhhmmss*> dokumentów etl

> [!NOTE]  
> W tej ścieżce pliku i nazwie reprezentuje nazwę urządzenia HoloLens oraz datę i czas \<*HoloLens device name*> \<*ddmmyyhhmmss*> utworzenia pliku.

Informacje diagnostyczne pozostają w tych lokalizacjach do momentu usunięcia ich przez użytkownika.

## <a name="diagnosticlog-csp"></a>DiagnosticLog CSP

W środowisku usługi Mobile Zarządzanie urządzeniami (MDM) administrator IT może użyć dostawcy usług konfiguracji [DiagnosticLog (CSP)](/windows/client-management/mdm/diagnosticlog-csp) do skonfigurowania ustawień diagnostycznych na zarejestrowanych urządzeniach HoloLens urządzeniach. Administrator IT może skonfigurować te ustawienia w celu zbierania dzienników z zarejestrowanych urządzeń.

Zobacz więcej:
- [Zbieranie danych diagnostycznych z Windows urządzenia](/mem/intune/remote-actions/collect-diagnostics)
- [Publiczna wersja zapoznawcza usługi Intune — Windows 10 diagnostyki urządzenia](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>Wymagania wstępne

- Urządzenie jest połączone z siecią.
- Urządzenie jest zarejestrowane w środowisku MDM, które obsługuje program DiagnosticLog CSP.

### <a name="data-locations-access-and-retention"></a>Lokalizacje danych, dostęp i przechowywanie

Ponieważ urządzenie jest częścią środowiska zarządzanego, użytkownik niejawnie wyraża zgodę na dostęp administracyjny do informacji diagnostycznych.

Administrator IT używa usługi CSP DiagnosticLog do konfigurowania zasad przechowywania, przechowywania i dostępu do danych, w tym zasad, które określają następujące kwestie:

- Infrastruktura chmury, która przechowuje informacje diagnostyczne.
- Okres przechowywania informacji diagnostycznych.
- Uprawnienia kontrolują dostęp do informacji diagnostycznych.

## <a name="offline-diagnostics"></a>Diagnostyka w trybie offline
W sytuacjach, gdy urządzenie nie może zbierać danych diagnostycznych za pośrednictwem usługi Centrum opinii lub narzędzia Ustawienia Troubleshooter, możesz zbierać diagnostykę ręcznie. Jednym ze scenariuszy, w którym jest to konieczne, jest sytuacja, w której urządzenie nie może nawiązać połączenia z usługą Wi-Fi lub nie można uzyskać dostępu do innych metod wymienionych powyżej. Diagnostyka zbiera zrzuty awaryjne i dzienniki z urządzenia, które pomagają inżynierowi pomocy technicznej firmy Microsoft wyizolować problemy.

Działa to, gdy urządzenie jest Eksplorator plików po podłączeniu go do komputera za pośrednictwem kabla USB.

> [!NOTE]
> Generowanie diagnostyki offline i zarządzanie nimi jest kontrolowane w różny sposób w zależności od wersji systemu operacyjnego. Wcześniej był on kontrolowany przez ustawienie telemetrii, ale jest teraz bezpośrednio kontrolowany za pośrednictwem zasad zarządzania urządzeniami przenośnymi. W przypadku wyłączenia za pomocą ustawienia lub zasad zarządzania urządzeniami przenośnymi dzienniki diagnostyczne nie mogą być zbierane przy użyciu tego mechanizmu.

Zachowanie przed [Windows Holographic, wersja 20H2:](hololens-release-notes.md#windows-holographic-version-20h2)
 - Diagnostyka w trybie offline jest włączona tylko wtedy, gdy użytkownik przechodzi przez tryb OOBE lub [wartość zasad System\AllowTelemetry](/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) jest ustawiona na Wartość pełna (wartość domyślna to Podstawowa na HoloLens). 
- Aby wyłączyć diagnostykę w trybie offline, przejdź **do Ustawienia Zasady >** aplikacji i wybierz pozycję Podstawowe **w** danych **diagnostycznych.** W przypadku kompilacji, w których diagnostyka offline zależy od ustawienia telemetrii, ma to wpływ tylko na to, czy są zbierane jakiekolwiek dzienniki. Nie ma to wpływu na to, jakie pliki są zbierane.
- Jeśli urządzenie jest zablokowane, dzienniki nie będą wyświetlane.

W [kompilacjach Windows Holographic, wersja 20H2](hololens-release-notes.md#windows-holographic-version-20h2) lub nowsza:
- Po włączeniu diagnostyki rezerwowej będą kontrolowane przez określone zasady MDM z odpowiednim ustawieniem [MixedReality/FallbackDiagnostics](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)
- Jeśli urządzenie jest zablokowane, dzienniki nie będą wyświetlane.

Obejrzyj ten film wideo, aby dowiedzieć się więcej.

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

Wykonaj następujące kroki, aby zebrać dane diagnostyczne:
1.  Połączenie podłącz urządzenie do komputera za pomocą kabla USB.
2.  W Eksplorator plików na komputerze przejdź do folderu **"Ten komputer \<hololens-device> \Wewnętrzny Storage".**
3.  Jeśli folder **Storage** nie jest pokazywany, urządzenie oczekuje na zalogowanie się użytkownika. Zaloguj się lub zamów zasilanie urządzenia, przytrzymując przycisk POWER na 10 sekund.
4.  Naciśnij i natychmiast zwolnij **przyciski Power + Volume Down.**
5.  Poczekaj chwilę, aż urządzenie przygotuje archiwa zip. (Plik tymczasowy o nazwie HololensDiagnostics.temp może stać się widoczny podczas generowania archiwów zip przez urządzenie. Nie należy uzyskać dostępu do tego pliku ani go zapisać. Po zakończeniu procesu zostanie on zastąpiony archiwami zip.
6.  Odśwież Eksploratora plików i przejdź do folderu **"\Documents".**
7.  Skopiuj diagnostyczne pliki ZIP i udostępnij je zespołowi pomocy technicznej firmy Microsoft.

> [!NOTE]
> Niektóre pliki ZIP diagnostyki mogą zawierać dane osobowe.
