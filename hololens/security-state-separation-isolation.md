---
title: Separacja i izolacja stanu
description: Dowiedz się więcej o rozdzielaniu stanu, izolacji, podpisywaniu kodu i aplikacjach defender na urządzeniu HoloLens rzeczywistości mieszanej 2.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, State separation, State separation and isolation, hololens 2, hololens2 security, security overview, security architecture, architecture, hololens 2 architecture
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 0487ea49c706c753f4dfca7da7daa499d1715e9f
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036583"
---
# <a name="state-separation-and-isolation"></a>Separacja i izolacja stanu

Separacja i izolacja stanu chroni krytyczne części systemu operacyjnego Hololens 2 przed zmianą — na przykład te, które są wymagane do uruchomienia systemu operacyjnego w stanie zaufanym. Dzięki technologii izolacji niezaufane aplikacje są przenoszone do izolowanego środowiska piaskownicy, aby upewnić się, że nie wpływają one na zabezpieczenia systemu.

## <a name="state-separation"></a>Separacja stanu

Separacja stanu w HoloLens 2 znacznie zwiększa bezpieczeństwo i użyteczność (aktualizowanie) i pomaga chronić dane aplikacji.  Separacja stanu działa w następujący sposób:
  * Podstawowy system operacyjny jest przechowywany w podstawowym woluminie systemu operacyjnego (zaufany lub zweryfikowany system operacyjny firmy Microsoft aktualizujący system operacyjny).
  * Części systemu operacyjnego, które mogą być zmieniane w czasie działania (na przykład sterowniki i konfiguracje do pobrania), używają dalszej separacji stanu do partycjonowania danych i przechowywania ich w bezpiecznych, oddzielnych lokalizacjach przechowywania.
  * Z każdą bezpieczną lokalizacją magazynu są skojarzone odrębne zasady zabezpieczeń, które oferują zróżnicowane korzyści w zakresie zabezpieczeń, zgodnie z informacjami w poniższej sekcji.

## <a name="state-separation-benefits"></a>Korzyści z separacji stanu

  * Zabezpieczenia: Separacja stanu w programie HoloLens 2 znacznie zwiększa integralność platformy, odporność na złośliwe oprogramowanie i ochronę danych użytkowników. Rozdzielenie niealterowalnej części systemu operacyjnego i zabezpieczenie jej tylko do odczytu lub integralności sprawia, że oddzielenie stanu bardzo utrudnia trwałość złośliwego oprogramowania po zimnym ponownym rozruchu. 
  * Aktualizacje: w HoloLens 2, gdy podstawowy system operacyjny jest niemodyfikowalny i został dokładnie oddzielony od pozostałych danych na urządzeniu, aktualizacje stają się proste i niezawodne.  Ponadto separacja stanu określa podstawowe możliwości znacznie szybszych aktualizacji, co umożliwia zastąpienie systemu operacyjnego w jednym kroku (jednostce niepodzielnej).
  * Resetowanie urządzenia: HoloLens 2 powoduje wyczyszczenie danych wygenerowanych przez użytkownika i danych aplikacji użytkownika na urządzeniu — w tym wewnętrznych i zewnętrznych lokalizacji przechowywania. Zachowuje bieżące aplikacje systemu operacyjnego i aplikacje krytyczne dla zabezpieczeń oraz bieżące aplikacje dostosowane przez firmę Microsoft i OEM (wstępnie zainstalowane). Te wstępnie zainstalowane aplikacje można ponownie wypełnić na urządzeniu po zakończeniu resetowania

### <a name="state-separation-states"></a>Stany separacji stanów

Separacja stanu zapewnia, że system operacyjny może zostać zmieniony tylko przez składniki zaufanych urządzeń firmy Microsoft i tylko stan wysokiej wartości może być utrwalany po ponownym uruchomieniu; inny stan systemu istnieje tylko przez czas trwania sesji rozruchu i jest odrzucany po ponownym uruchomieniu. Oddzielenie stanu szybko przywraca urządzenie do stanu fabrycznego. Windows Holographic for Business można podzielić na następujące odrębne kategorie:
  * Podstawowy system operacyjny — stan nietrwale
  * Dane systemu operacyjnego — stan, który można zmienić 
  * Dane użytkownika — stan, który można zmienić

Każdy z tych HoloLens 2 stany operacyjne opisano w poniższej sekcji.

#### <a name="core-operating-system"></a>Podstawowy system operacyjny

Stan niezmienny składa się z plików wykonywalnych i danych, które są niezmienne i mogą być zmieniane przez firmę Microsoft tylko podczas instalacji aktualizacji. Podczas takiej aktualizacji podstawowego systemu operacyjnego jest włączony nowy obraz zawierający najnowszy żądany stan operacyjny.
Stan nietrwale jest oznaczony jako tylko do odczytu (lub w inny sposób chroniony przez integralność), zapobiegając trwałości złośliwego oprogramowania z podwyższonym poziomem uprawnień. Następujące pliki wykonywalne i dane są chronione w stanie niezmiennym:
  * Windows Sterowniki skrzynki odbiorczej holograficznej
  * Pliki binarne systemu operacyjnego
  * Windows skrzynki odbiorczej
  * Ustawienia Windows holograficzne przechowywane w gałęzi Windows registry hive (HKLM)
    * Przykład: HKLM przechowuje informacje o konfiguracji dla aplikacji zainstalowanych na maszynie. Przechowuje również informacje dotyczące wykrywania sprzętu i odpowiednich sterowników.
Dzięki ochronie w stanie niezmiennym (integralność i ochrona tylko do odczytu) gwarantujemy, że podstawowy system operacyjny zawsze jest w stanie zaufanym. Ponadto po zresetowaniu urządzenia możemy upewnić się, że jest on uruchamiany tylko ze składnikami, które znajdują się w tej sekcji niezmiennej. 

#### <a name="operating-system-data"></a>Dane systemu operacyjnego 

Należy pamiętać, że pliki wykonywalne i dane, które można zmieniać w czasie wykonywania (i które nie są krytyczne dla funkcji systemu operacyjnego), mogą być odrzucane i tworzone ponownie, gdy dane są uszkodzone lub naruszone. Stan o wysokiej wartości, który można zmienić, jest funkcjonalnie wymagany do utrwalania przez system operacyjny lub oczekiwany podczas zamykania systemu operacyjnego i/lub ponownego uruchamiania przez obsługiwane Windows systemów operacyjnych i urządzeń. Przykłady modyfikowalnego stanu o wysokiej wartości to:
  * Skonfigurowane przez administratora IT globalne ustawienia urządzeń, takie jak wyłączenie lokalizacji dla wszystkich użytkowników.
  * Połączenie sieciowe Wi-Fi uzyskuje dostęp do sieci zapamiętyowanych przez urządzenie danych i skojarzonych haseł połączeń.
  * Zrzuty awaryjne, w tym ustawienia, dzienniki.
  * Sterowniki pobrane na żądanie dla nowo odnalezionych urządzeń.
Stan o wysokiej wartości, który można zmienić na HoloLens 2, znajduje się w lokalizacji zabezpieczeń danych systemu operacyjnego jako plik zapisany na dysku lub w utrwalonej gałęzi rejestru.

#### <a name="user-data"></a>Dane użytkowników

Ostatnia kategoria stanu reprezentuje dane użytkownika wytwarzanych lub utrwalane przez aplikacje platformy UWP lub system operacyjny. Wszystkie znane foldery użytkownika, takie jak Pliki do pobrania, Dokumenty, Wideo, profile użytkowników HKEY_CURRENT_USER gałęzi, również są przechowywane w tej lokalizacji. Tych danych nie można wyodrębnić bez odpowiednich poświadczeń; Aby dowiedzieć się więcej na temat sposobu ochrony danych, zobacz [Szyfrowanie i ochrona danych.](security-encryption-data-protection.md)

##  <a name="isolation"></a>Izolacja

Aby osiągnąć tę równowagę, HoloLens 2 ma podstawowy system operacyjny, który jest używany do podstawowych funkcji, takich jak rozruch, kontrola sprzętu, logowanie itp. W podstawowym systemie operacyjnym działają tylko dwa zestawy aplikacji — wstępnie zainstalowane aplikacje i aplikacje platformy uniwersalnej systemu Windows.

## <a name="code-signing"></a>Podpisywanie kodu

Cyfrowo podpisywanie kodu umożliwia uwierzytelnianie, że pliki wykonywalne i skrypty nie zostały zmodyfikowane, ponieważ zostały podpisane przez zaufane źródło, co zapewnia autentyczność i integralność. Urzędy, które HoloLens zaufania 2 domyślnie są firmy Microsoft i Microsoft Store. Administratorzy IT mogą dodawać nowe certyfikaty do urządzenia za pośrednictwem firm CSP [ClientCertificateInstall](/windows/client-management/mdm/clientcertificateinstall-csp) i [RootCATrustedCertificates.](/windows/client-management/mdm/rootcacertificates-csp) Mogą również używać zasad [AllowAllTrustedApps,](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) aby ufać dodatkowym aplikacjom ładowanych sideload lub [aplikacjom biznesowym.](/intune/apps/lob-apps-windows) Certyfikaty znajdują się w magazynie certyfikatów komputera lokalnego, który jest przechowywany w HKLM/głównego w przypadku korzystania z "urządzenia" lub w HKCU w przypadku korzystania z "użytkownika".

## <a name="defender-protections"></a>Zabezpieczenia usługi Defender
HoloLens 2 używa usługi firmy Microsoft, aby zapewnić użytkownikom zaawansowany poziom zabezpieczeń:

* [Filtr Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) jest automatycznie włączany na urządzeniach Windows Holographic przez system operacyjny i chroni przed wyłudzaniem informacji i złośliwym oprogramowaniem, a także pobieraniem potencjalnie złośliwych plików w przeglądarce Edge. Użytkownik nie może go wyłączyć, ale można go wyłączyć za pomocą zasad.

* [Zapora Defender](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) blokuje przepływ nieautoryzowanego ruchu sieciowego do i z urządzenia. Jest ona domyślnie włączona i nie może być konfigurowalna przez klienta za pomocą lokalnych akcji lub zasad. 

* [Windows Defender Application Control:](/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview)HoloLens 2 obsługuje funkcję WDAC, która umożliwia administratorowi IT wypychanie zasad sterowania aplikacji na urządzenie. Więcej informacji można znaleźć na stronie Korzystanie z funkcji [WDAC na urządzeniach HoloLens 2 z usługą MSFT Intune.](/mem/intune/configuration/custom-profile-hololens) 

Administratorzy IT mogą zarządzać zachowaniem filtru SmartScreen za pomocą [filtru AllowSmartScreen](/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) i zachowania przeglądarki za [pomocą tych zasad.](/windows/client-management/mdm/policy-csps-supported-by-hololens2) 

