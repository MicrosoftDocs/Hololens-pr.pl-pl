---
title: HoloLens 2 możliwości i rozwiązania
description: Dowiedz się więcej o Microsoft HoloLens komercyjnych, które ułatwiają firmom zarządzanie HoloLens urządzeniami.
author: joyjaz
ms.author: v-jjaswinski
ms.date: 06/28/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
audience: ITPro
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: skerewa
appliesto:
- HoloLens 2
keywords: HoloLens 2, commercial, features, mdm, mobile device management, kiosk mode, applications, identity, Bitlocker, iris, Windows Hello, Azure-powered, Autopilot, mixed reality, WDAC
ms.openlocfilehash: 88a75224909fd64e387cfb5677056e2ae5d62e4b3518aa758f22ec66a86a8355
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665349"
---
# <a name="hololens-2-capabilities-and-solutions"></a>HoloLens 2 możliwości i rozwiązania

## <a name="what-can-hololens-2-do-for-you"></a>Co może HoloLens 2?

Współpraca bez granic i precyzyjne działanie w celu zwiększenia produktywności pracowników dzięki aplikacjom rzeczywistości mieszanej na HoloLens 2. Nie wykonuj dłużej i niechętnych rąk dzięki wbudowanym poleceńom głosowemu, śledzeniu wzroku i zakotwiczeniu świata w celu ciągłego skoncentrowania się na bezpiecznym wypełnianiu zadań bez błędów. Połączenie współpracownikami w czasie rzeczywistym i współpracować ze sobą na obszernej kanwie holograficznej nakładanej w środowisku fizycznym, aby szybko rozwiązywać problemy w miejscu pracy. Od razu poszukaj zwrotu z inwestycji dzięki niezawodnemu ekosystemowi aplikacji, które są obsługiwane z zabezpieczeniami, niezawodnością i skalowalnością firmy Microsoft.  

[!INCLUDE [solutions](includes/hlsolutions.md)]

## <a name="hololens-2-capabilities"></a>HoloLens 2

Co sprawia, że HoloLens 2 są tak zaawansowane?

| Cecha | Opis |
|---------|-------------|
| Zakotwiczenie świata | Kotwicone hologramy pozostają dokładnie na miejscu. HoloLens 2 rozumie obszar roboczy. W związku z tym zawartość cyfrowa jest utrwalana w czasie — zakotwiczona w obiektach lub powierzchniach, w których pracujesz. |
| Śledzenie rąk | Dotyk, osłanianie i przenoszenie hologramów w sposób naturalny. HoloLens 2 dostosowuje się do twoich rąk, aby uzyskać nowe zadowolenie z interakcji. |
| Śledzenie wzroku | Korzystaj z nowego poziomu kontekstu i zrozumienia przez ludzi. HoloLens 2 rozumie dokładnie, gdzie się znajdujesz, dzięki czemu może zrozumieć Twoją intencję i dostosować hologramy do twoich oczu w czasie rzeczywistym. |
| Włączony głos | Wbudowane polecenia głosowe umożliwiają szybkie nawigowanie po HoloLens 2, gdy ręce są zajęte zadaniem. |
| Ergonomiczne | HoloLens 2 jest lekki (3,28kg), który zawiera system dopasowania numerów do obsługi rozszerzonego użycia. |
| Duże fov | Rozwiń kanwę holograficzną z dużymi ekranami w polu widzenia o wysokiej rozdzielczości. |
| Swobodne | Poruszaj się swobodnie bez kabli ani zewnętrznych pakietów, aby rozpocząć pracę. |
| Obsługiwane przez platformę Azure | Przesyłaj strumieniowo zawartość 3D o wysokiej jakości, która może być zakotwiczona w lokalizacji i/lub obiekcie, który utrzymuje się między użytkownikami za pomocą usług rzeczywistości mieszanej platformy Azure.
| Przechwytywanie rzeczywistości mieszanej | Udokumentuj środowisko jako zdjęcie lub film wideo, aby udostępnić go innym osobom w czasie rzeczywistym. |
| Windows Hello for Business | Uwierzytelnianie biometryczne oparte na irysach umożliwia szybkie i bezpieczne przepływ pracy. |
| Windows Autopilot | Skonfiguruj i skonfiguruj wstępnie usługi dla HoloLens 2, aby były gotowe do użycia od razu po instalacji w rozproszonych działach. |
| Aktualizacje systemu operacyjnego | Zapewnij bezpieczeństwo dzięki comiesięcznych aktualizacjach obsługi oraz skorzystaj z nowych funkcji zwiększających produktywność i możliwości zarządzania w co dwa roczne wersje. |
| Łatwe zarządzanie urządzeniami | Zarządzanie wieloma HoloLens 2 jednocześnie przy użyciu rozwiązań, takich jak Microsoft Intune, VMware Workspace One, MobileIron i wiele innych. |
| Działanie w środowiskach podlegających regulacjom | HoloLens 2 ma obszerną ofertę urządzeń, która obsługuje środowiska ściśle podlegających regulacjom, w tym środowiska wyznaczone do klas ISO 5.0 i UL, klasa I, dział 2. |


## <a name="managing-hololens-2-in-your-organization"></a>Zarządzanie HoloLens 2 w organizacji
HoloLens 2 zawiera funkcje, które ułatwiają organizacjom zarządzanie urządzeniami HoloLens urządzeniami. Niektóre funkcje są dołączone do urządzenia, a inne mogą być włączane przez usługę [](hololens-provisioning.md) [Mobile Zarządzanie urządzeniami (MDM)](hololens-mdm-configure.md) dla usługi HoloLens lub za pośrednictwem pakietów aprowizowania przy użyciu programu Windows [Configuration Designer.](app-deploy-provisioning-package.md#setup)

| Chcę... | Rozwiązanie | Opis |  
|---------| ------------|------------|
Zarządzanie logowaniem użytkowników końcowych | [**Tożsamość**](hololens-identity.md) | HoloLens 2 obsługuje kilka rodzajów tożsamości użytkowników — Azure Active Directory (AAD), konto Microsoft (MSA) i konta lokalne.  |
| Szyfrowanie danych użytkownika | [**Bezpieczeństwo danych**](security-encryption-data-protection.md) | Szyfrowanie danych funkcją BitLocker jest włączone na HoloLens 2 w celu zapewnienia tego samego poziomu zabezpieczeń co inne Windows urządzenia. | 
Zarządzanie urządzeniami Hololens w mojej organizacji | [**Zarządzanie urządzeniami przenośnymi**](hololens-mdm-configure.md) | Zarządzaj ustawieniami, wybierz aplikacje do zainstalowania i ustawienia konfiguracji zabezpieczeń dostosowanych do potrzeb twojej organizacji na wielu HoloLens 2 z centralnej lokalizacji. | 
|Minimalizowanie czasu instalacji dla nowych użytkowników i urządzeń | [**Autopilota**](hololens2-autopilot.md) | Skonfiguruj środowisko out-of-box experience (OOBE) w programie Microsoft Endpoint Manager, aby umożliwić użytkownikom końcowego przygotowanie urządzeń do użycia w firmie bez interakcji lub z niewielkimi interakcjami. |  
| Kontrolowanie aktualizacji systemu operacyjnego dla urządzeń | [**Windows Update dla firm**](hololens-updates.md#managing-updates-by-using-windows-update-for-business) | Windows Aktualizacja dla firm zapewnia kontrolowane aktualizacje systemu operacyjnego dla urządzeń i obsługę kanału obsługi długoterminowej. |  
| Zezwalaj na pobranie określonych aplikacji i aplikacji LOB |[**Zarządzanie aplikacją**](app-deploy-overview.md) | Wybierz sposób dystrybucji i kontrolowania aplikacji dla wybranych grup HoloLens 2 użytkowników. | 
| Pokazywanie lub ukrywanie określonych aplikacji w menu Start |[**Tryb kiosku**](hololens-kiosk.md) | Skonfiguruj HoloLens 2, aby działały jako urządzenie o stałym celu do użycia w pokazach aplikacji lub dedykowanych aplikacjach biznesowych. 
| Zabezpieczanie środowiska przez blokowanie aplikacji | [**WDAC**](windows-defender-application-control-wdac.md) | Windows Defender Kontrola aplikacji (WDAC) blokuje aplikacje i procesy przed ich uruchomiono przez użytkownika urządzenia.
| Zarządzanie zabezpieczeniami urządzeń przy użyciu reguł dla aplikacji i procesów | [**Zasady (CSP)**](hololens-csp-policy-overview.md) | Administratorzy IT mogą definiować i implementować ustawienia zasad przy użyciu istniejącej listy obsługiwanych zasad CSP na HoloLens 2. |  
| Zarządzanie tym, jak urządzenie łączy się z Internetem | [**Sieć i łączność**](hololens-certificates-network.md) | Użyj uwierzytelniania opartego na certyfikatach, aby uzyskać dostęp do sieci Wi-Fi, sieci VPN lub zasobów wewnętrznych. | 
| Udostępnianie urządzenia wielu użytkownikom | [**Automatycznie dostosowywany ekran**](hololens-calibration.md#auto-eye-position-support) | HoloLens ekrany z 2 ekranami są automatycznie dostosowywane za pomocą funkcji Automatycznego rozsyłania oka (AEP, Auto Eye Position), eliminując konieczność ręcznego uruchamiania procesu redugowania, gdy urządzenie jest współużytkowane [przez użytkowników.](hololens-multiple-users.md) |

Dowiedz się więcej [o wymaganiach dotyczących](hololens-licenses-requirements.md) licencjonowania dla powyższych rozwiązań.

## <a name="next-steps"></a>Następne kroki
> [!div class="nextstepaction"]
> [Eksplorowanie HoloLens 2](hololens2-options.md)

> [!div class="nextstepaction"]
>[Planowanie HoloLens 2](hololens-requirements.md) 
