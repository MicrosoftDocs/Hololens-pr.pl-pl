---
title: Separacja i izolacja stanu
description: Dowiedz się więcej o rozdzielaniu stanu, izolacji, podpisywaniu kodu i aplikacjach defender na urządzeniu HoloLens 2 rzeczywistości mieszanej.
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
ms.openlocfilehash: 60d6d7c0e281395957ce9158144a5f3d60927682
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379778"
---
# <a name="state-separation-and-isolation"></a>Separacja i izolacja stanu

Separacja i izolacja stanu chroni krytyczne części systemu operacyjnego Hololens 2 przed zmianami, takimi jak te, które są wymagane do uruchomienia systemu operacyjnego w stanie zaufanym. Dzięki technologii izolacji niezaufane aplikacje są przenoszone do izolowanego środowiska piaskownicy w celu zapewnienia, że nie wpływają one na zabezpieczenia systemu.

## <a name="state-separation"></a>Separacja stanu

Separacja stanu na urządzeniach HoloLens 2 znacznie zwiększa bezpieczeństwo i użyteczność (aktualizowanie) i pomaga chronić dane aplikacji.  Separacja stanu działa w następujący sposób:
  * Podstawowy system operacyjny jest przechowywany w woluminie podstawowego systemu operacyjnego (zaufany lub zweryfikowany system operacyjny firmy Microsoft aktualizujący system operacyjny).
  * Części systemu operacyjnego, które można zmienić w czasie działania (na przykład sterowniki i konfiguracje do pobrania), używają dalszej separacji stanu do partycjonowania danych i przechowywania ich w bezpiecznych, oddzielnych lokalizacjach przechowywania.
  * Z każdą bezpieczną lokalizacją magazynu są skojarzone odrębne zasady zabezpieczeń, które oferują różne korzyści w zakresie zabezpieczeń, zgodnie z informacjami w poniższej sekcji.

## <a name="state-separation-benefits"></a>Korzyści z separacji stanu

  * Zabezpieczenia: Funkcja separacji stanu na urządzeniach HoloLens 2 znacznie poprawia integralność platformy, odporność na złośliwe oprogramowanie i ochronę danych użytkowników. Rozdzielenie niealterowalnej części systemu operacyjnego i zabezpieczenie jej przed tylko do odczytu lub integralnością sprawia, że ponowne uruchomienie złośliwego oprogramowania jest niezwykle trudne. 
  * Aktualizacje: w przypadku urządzenia HoloLens 2, gdy podstawowy system operacyjny jest niemodyfikowalny i został dokładnie oddzielony od pozostałych danych na urządzeniu, aktualizacje stają się proste i niezawodne.  Ponadto separacja stanu określa podstawowe wymagania dotyczące znacznie szybszych aktualizacji, co pozwala na zastąpienie systemu operacyjnego w jednym kroku (jednostce niepodzielnej).
  * Resetowanie urządzenia: resetowanie urządzenia HoloLens 2 powoduje wyczyszczenie danych wygenerowanych przez użytkownika i danych aplikacji użytkownika na urządzeniu — w tym wewnętrznych i zewnętrznych lokalizacji przechowywania. Zachowuje bieżące aplikacje systemu operacyjnego i aplikacje krytyczne dla zabezpieczeń oraz bieżące aplikacje dostosowane przez firmę Microsoft i producentów OEM (wstępnie zainstalowane). Te wstępnie zainstalowane aplikacje można ponownie wypełnić na urządzeniu po zakończeniu resetowania

### <a name="state-separation-states"></a>Stany separacji stanów

Separacja stanu zapewnia, że system operacyjny może zostać zmieniony tylko przez składniki zaufanego urządzenia firmy Microsoft i tylko stan wysokiej wartości może zostać utrwalony po ponownym uruchomieniu. inny stan systemu istnieje tylko przez czas trwania sesji rozruchu i jest odrzucany po ponownym uruchomieniu. Separacja stanu szybko przywraca urządzenie do stanu fabrycznego. Windows Holographic for Business można podzielić na następujące odrębne kategorie:
  * Podstawowy system operacyjny — stan nietrwale
  * Dane systemu operacyjnego — stan, który można zmienić 
  * Dane użytkownika — stan, który można zmienić

Każdy z tych stanów operacyjnych urządzenia HoloLens 2 został opisany w poniższej sekcji.

#### <a name="core-operating-system"></a>Podstawowy system operacyjny

Stan niezmienny składa się z plików wykonywalnych i danych, które są nietrwale i mogą być zmieniane przez firmę Microsoft tylko podczas instalacji aktualizacji. Podczas takiej aktualizacji podstawowego systemu operacyjnego jest włączany nowy obraz zawierający najnowszy żądany stan operacyjny.
Stan nietrwale jest oznaczony jako tylko do odczytu (lub w inny sposób chroniony przez integralność), zapobiegając trwałości złośliwego oprogramowania z podwyższonym poziomem uprawnień. Następujące pliki wykonywalne i dane są chronione w stanie niezmiennym:
  * Sterowniki skrzynki odbiorczej systemu Windows Holographic
  * Pliki binarne systemu operacyjnego
  * Sterowniki skrzynki odbiorczej systemu Windows
  * Statyczne ustawienia systemu Windows Holographic przechowywane w gałęzi rejestru systemu Windows (HKLM)
    * Przykład: HKLM przechowuje informacje o konfiguracji dla aplikacji zainstalowanych na maszynie. Ponadto przechowuje informacje w celu wykrywania sprzętu i odpowiednich sterowników.
Dzięki ochronie tych danych w stanie niezmiennym (integralności i tylko do odczytu) gwarantujemy, że podstawowy system operacyjny zawsze będzie w stanie zaufanym. Ponadto po zresetowaniu urządzenia możemy upewnić się, że jest on uruchamiany tylko ze składnikami, które znajdują się w tej sekcji niezmiennej. 

#### <a name="operating-system-data"></a>Dane systemu operacyjnego 

Należy pamiętać, że pliki wykonywalne i dane, które można zmieniać w czasie wykonywania (i które nie są krytyczne dla funkcji systemu operacyjnego), mogą być odrzucane i tworzone ponownie, gdy dane są uszkodzone lub naruszone. Stan o wysokiej wartości, który można zmienić, jest funkcjonalnie wymagany do utrwalania przez system operacyjny lub oczekiwany podczas zamykania systemu operacyjnego i/lub po ponownym uruchomieniu przez obsługiwane scenariusze systemu operacyjnego Windows i urządzeń. Przykłady modyfikowalnego stanu wysokiej wartości to:
  * Skonfigurowane przez administratora IT globalne ustawienia urządzeń, takie jak wyłączenie lokalizacji dla wszystkich użytkowników.
  * Połączenie sieciowe sieci Wi-Fi uzyskuje dostęp do sieci zapamiętyowanych przez urządzenie danych i skojarzonych haseł połączeń.
  * Zrzuty awaryjne, w tym ustawienia, dzienniki.
  * Sterowniki pobrane na żądanie dla nowo odnalezionych urządzeń.
Stan o wysokiej wartości, który można zmienić na urządzeniach HoloLens 2, znajduje się w lokalizacji zabezpieczeń danych systemu operacyjnego jako zapisany plik na dysku lub w utrwalonej gałęzi rejestru.

#### <a name="user-data"></a>Dane użytkowników

Ostatnia kategoria stanu reprezentuje dane użytkownika, które zostały utrwalone przez aplikacje platformy UWP lub system operacyjny. Wszystkie znane foldery użytkowników, takie jak Pliki do pobrania, Dokumenty, Wideo, profile użytkowników i HKEY_CURRENT_USER hive, również są przechowywane w tej lokalizacji. Tych danych nie można wyodrębnić bez odpowiednich poświadczeń; Aby dowiedzieć się więcej na temat ochrony danych, zobacz [Szyfrowanie i ochrona danych.](security-encryption-data-protection.md)

##  <a name="isolation"></a>Izolacja

Aby osiągnąć tę równowagę, urządzenie HoloLens 2 ma podstawowy system operacyjny, który jest używany do podstawowych funkcji, takich jak rozruch, sterowanie sprzętem, logowanie itp. W podstawowym systemie operacyjnym działają tylko dwa zestawy aplikacji — wstępnie zainstalowane aplikacje i aplikacje platformy UWP.

## <a name="code-signing"></a>Podpisywanie kodu

Cyfrowo podpisywanie kodu umożliwia tworzenie plików wykonywalnych i skryptów, które nie zostały zmodyfikowane, ponieważ zostały podpisane przez zaufane źródło, co zapewnia autentyczność i integralność. Domyślnymi urzędami zaufanymi dla urządzenia HoloLens 2 są firma Microsoft i Microsoft Store. Administratorzy IT mogą dodawać nowe certyfikaty do urządzenia za pośrednictwem serwerów CSP [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) i [RootCATrustedCertificates.](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) Mogą również użyć zasad [AllowAllTrustedApps,](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) aby ufać dodatkowym aplikacjom ładowanych sideload lub [biznesowym.](https://docs.microsoft.com/intune/apps/lob-apps-windows) Certyfikaty znajdują się w magazynie certyfikatów komputera lokalnego, który jest przechowywany w HKLM/głównego w przypadku korzystania z "urządzenia" lub w HKCU, jeśli za pomocą "użytkownika".

## <a name="defender-protections"></a>Zabezpieczenia usługi Defender
Urządzenie HoloLens 2 usługi firmy Microsoft, aby zapewnić użytkownikom zaawansowany poziom zabezpieczeń:

* [Filtr Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) jest automatycznie włączany na urządzeniach z systemem Windows Holographic przez system operacyjny i chroni przed wyłudzeniem informacji i złośliwym oprogramowaniem, a także pobieraniem potencjalnie złośliwych plików w przeglądarce Edge. Użytkownik nie może go wyłączyć, ale można go wyłączyć za pomocą zasad.

* [Zapora Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) blokuje nieautoryzowany ruch sieciowy do i z urządzenia. Jest ona domyślnie włączona i nie można jej konfigurować przez klienta za pomocą lokalnych akcji lub zasad. 

* [Windows Defender Application Control:](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview)urządzenie HoloLens 2 obsługuje funkcję WDAC, która umożliwia administratorowi IT wypychanie zasad sterowania aplikacją na urządzenie. Więcej informacji można znaleźć na stronie [Use WDAC on HoloLens 2 devices with MSFT Intune (Używanie funkcji WDAC na urządzeniach HoloLens 2 z usługą MSFT Intune).](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens) 

Administratorzy IT mogą zarządzać zachowaniem filtru SmartScreen za pomocą [filtru AllowSmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) i zachowania przeglądarki za [pomocą tych zasad.](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2) 

