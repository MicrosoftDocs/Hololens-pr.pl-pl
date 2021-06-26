---
title: Zarządzanie aktualizacjami urządzenia HoloLens
description: Dowiedz się, jak administratorzy mogą zarządzać aktualizacjami urządzeń HoloLens za pomocą zarządzania urządzeniami przenośnymi.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 10/13/2020
ms.reviewer: jarrettr
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: faa6bb2b095d69c3538063b1c042c5ce5e215d33
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924081"
---
# <a name="manage-hololens-updates"></a>Zarządzanie aktualizacjami urządzenia HoloLens

Urządzenie HoloLens używa Windows Update w taki sam sposób jak inne Windows 10 urządzenia. Gdy aktualizacja jest dostępna, jest ona automatycznie pobierana i instalowana przy następnym podłączeniu urządzenia do Sieci i połączeniu z Internetem. W tym artykule opisano sposób zarządzania aktualizacjami w przedsiębiorstwie lub innym środowisku zarządzanym. Aby uzyskać informacje na temat zarządzania aktualizacjami poszczególnych urządzeń HoloLens, zobacz [Aktualizowanie urządzenia HoloLens.](hololens-update-hololens.md)

## <a name="manage-updates-automatically"></a>Automatyczne zarządzanie aktualizacjami

### <a name="managing-updates-by-using-windows-update-for-business"></a>Zarządzanie aktualizacjami przy użyciu Windows Update dla Firm

Windows Holographic for Business można [używać](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) Windows Update dla Firm do zarządzania aktualizacjami. Wszystkie urządzenia HoloLens 2 mogą używać Windows Holographic for Business. Upewnij się, że używają Windows Holographic for Business kompilacji 10.0.18362.1042 lub nowszej. Jeśli masz urządzenia HoloLens (1. generacji), [](hololens1-upgrade-enterprise.md) musisz uaktualnić je do Windows Holographic for Business, aby zarządzać ich aktualizacjami.

Windows Update dla Firm łączy urządzenia HoloLens bezpośrednio z Windows Update service. Za pomocą Windows Update dla Firm można kontrolować wiele aspektów procesu aktualizacji, czyli to, które urządzenia mogą uzyskać &mdash; aktualizacje o jakim czasie. Można na przykład w celu testowania wycofywał aktualizacje do podzestawu urządzeń, a następnie później wycofywał aktualizacje na pozostałych urządzeniach. Można również zdefiniować różne harmonogramy aktualizacji dla różnych typów aktualizacji.

> [!NOTE]  
> W przypadku urządzeń HoloLens można automatycznie zarządzać aktualizacjami funkcji (wydanymi dwa razy w roku) i aktualizacjami jakości (wydanymi co miesiąc lub zgodnie z wymaganiami, w tym krytycznymi aktualizacjami zabezpieczeń). Aby uzyskać więcej informacji na temat typów aktualizacji, zobacz [Typy aktualizacji zarządzanych przez usługę Windows Update dla Firm](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).

Ustawienia konfiguracji Windows Update dla Firm urządzenia HoloLens można skonfigurować przy użyciu zasad w rozwiązaniu mobile Zarządzanie urządzeniami (MDM), takim jak Microsoft Intune.

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>Zarządzanie Windows Update dla Firm przy użyciu Microsoft Intune

Aby uzyskać szczegółowe omówienie sposobu używania usługi Intune do konfigurowania Windows Update dla Firm, zobacz Zarządzanie Windows 10 [aktualizacjami oprogramowania w usłudze Intune.](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure) Aby uzyskać więcej informacji na temat określonych funkcji usługi Intune, które obsługuje urządzenie HoloLens, zobacz Funkcje zarządzania aktualizacjami usługi [Intune, które obsługują urządzenie HoloLens.](#intune-update-management-functions-that-hololens-supports)

> [!IMPORTANT]  
> Usługa Intune udostępnia dwa typy zasad do zarządzania aktualizacjami: *Windows 10 pierścienia* aktualizacji *i Windows 10 aktualizacji funkcji.* Typ Windows 10 aktualizacji funkcji jest obecnie w publicznej wersji zapoznawczej i nie jest obsługiwany w przypadku urządzenia HoloLens.
>  
> Zasady pierścienia Windows 10 do zarządzania aktualizacjami urządzenia HoloLens 2.

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>Konfigurowanie zasad aktualizacji dla urządzenia HoloLens 2 lub HoloLens (1. generacji)

W tej sekcji opisano zasady, których można użyć do zarządzania aktualizacjami dla urządzenia HoloLens 2 lub HoloLens (1. generacji). Aby uzyskać więcej informacji na temat funkcji dostępnych dla urządzenia HoloLens 2, zobacz Planowanie i konfigurowanie we/wy aktualizacji dla urządzenia [HoloLens 2.](#plan-and-configure-update-rollouts-for-hololens-2)

[Zasady CSP — aktualizacja](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) definiuje zasady, które konfigurują Windows Update dla Firm.

> [!NOTE]  
> Aby uzyskać listę określonych dostawców usług konfiguracji zasad (CSP), którzy są obsługiwani przez określone wersje urządzenia HoloLens, zobacz [Policy CSPs supported by HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices)(Dostawcy usługi konfiguracji zasad obsługiwani przez urządzenia HoloLens).

#### <a name="configure-automatic-checks-for-updates"></a>Konfigurowanie automatycznego sprawdzania aktualizacji

Zasady **Update/AllowAutoUpdate** umożliwiają zarządzanie automatycznym zachowaniem aktualizacji, takim jak skanowanie, pobieranie i instalowanie aktualizacji. Aby uzyskać więcej informacji na temat dostępnych ustawień dla tych zasad, zobacz [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> W Microsoft Intune można użyć automatycznego **zachowania aktualizacji,** aby zmienić te zasady. Aby uzyskać więcej informacji, zobacz [Zarządzanie Windows 10 aktualizacjami oprogramowania w usłudze Intune.](https://docs.microsoft.com/intune/windows-update-for-business-configure)

#### <a name="configure-an-update-schedule"></a>Konfigurowanie harmonogramu aktualizacji

Aby skonfigurować sposób i czas stosowania aktualizacji, użyj następujących zasad:

- [Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - Wartości: **0–7**(0 = codziennie, 1 = niedziela, 7 = sobota)
  - Wartość domyślna: **0** (codziennie)
- [Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Wartości: 0–23 (0 = północ, 23 = 21:00)
  - Wartość domyślna: 3:00

#### <a name="configure-active-hours"></a>Konfigurowanie godzin aktywnego działania
Począwszy od [systemu Windows Holographic, w wersji 20H2](hololens-release-notes.md#windows-holographic-version-20h2) administrator IT może określić zakres godzin aktywnego działania dla urządzeń HoloLens 2.

Aktywne godziny identyfikują okres, w którym urządzenie ma być w użyciu. Automatyczne ponowne uruchamianie po aktualizacji nastąpi poza godzinami aktywności. Określony zakres będzie liczony od godziny rozpoczęcia godzin aktywnego działania. Możesz użyć rozwiązania MDM zgodnie z opisem w tece [Konfigurowanie godzin aktywnego użytkowania za pomocą rozwiązania MDM.](https://docs.microsoft.com/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm) Rozwiązanie MDM używa ustawień Update/ActiveHoursStart i Update/ActiveHoursEnd i Update/ActiveHoursMaxRange w programie CSP zasad do konfigurowania godzin aktywności.

-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend) — ta wartość określa czas zakończenia. Od rozpoczęcia jest 12-godzinny limit.
    -   Obsługiwane wartości to 0–23, gdzie 0 to 12:00, 1 to 1:00 itd.
    -   Wartość domyślna to 17 (17:00).
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) — ta wartość określa maksymalną liczbę aktywnych godzin od czasu rozpoczęcia.
    -   Obsługiwane wartości to 8–18.
    -   Wartość domyślna to 18 (godziny).
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart) — ta wartość określa czas rozpoczęcia. Istnieje maksymalnie 12-godzinny czas od zakończenia.
    -   Obsługiwane wartości to 0–23, gdzie 0 to 12:00, 1 to 1:00 itd.
    -   Wartość domyślna to 8 (8:00).

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a>Urządzenia z systemem Windows 10 tylko w wersji 1607

Następujące zasady aktualizacji można użyć do skonfigurowania urządzeń w celu uzyskania aktualizacji z usługi Windows Server Update Service (WSUS), a nie z Windows Update:

- [Update/AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>Planowanie i konfigurowanie aktualizacji dla urządzenia HoloLens 2

Urządzenie HoloLens 2 obsługuje więcej funkcji automatyzacji aktualizacji niż urządzenia HoloLens (1. generacja). Jest to szczególnie istotne, jeśli używasz Microsoft Intune do zarządzania Windows Update dla Firm zasadami. Te funkcje ułatwiają planowanie i wdrażanie aktualizacji w całej organizacji.

#### <a name="plan-the-update-strategy"></a>Planowanie strategii aktualizacji

Usługa Windows Updates dla firm obsługuje zasady odroczenia. Po wydaniu aktualizacji przez firmę Microsoft można użyć zasad odroczenia, aby zdefiniować czas oczekiwania przed zainstalowaniem tej aktualizacji na urządzeniach. Kojarząc podzestawy urządzeń (nazywane również pierścieniami *aktualizacji)* z różnymi zasadami odroczenia, można skojarzyć strategię aktualizacji dla organizacji.

Rozważmy na przykład organizację, która ma 1000 urządzeń i musi aktualizować urządzenia w pięciu falach. Organizacja może utworzyć pięć pierścieni aktualizacji, jak pokazano w poniższej tabeli.

|Group (Grupa) |Liczba urządzeń |Odroczenie (dni) |
| ---| :---: | :---: |
|Grp 1 (personel IT) |5 |0 |
|Grp 2 (wcześnie adoptatorzy) |50 |60 |
|Grp 3 (główny 1) |250 |120 |
|Grp 4 (główny 2) |300 |150 |
|Grp 5 (główny 3) |395 |180 |

Oto jak w czasie będzie się to dzieje w całej organizacji.

![Oś czasu wdrażania aktualizacji](./images/hololens-updates-timeline.png)

#### <a name="configure-an-update-deferral-policy"></a>Konfigurowanie zasad odroczenia aktualizacji

Zasady odroczenia określają liczbę dni między datą, w której aktualizacja stanie się dostępna, a datą, w której aktualizacja jest oferowana urządzeniu.

Można skonfigurować różne odroczenia dla aktualizacji funkcji i aktualizacji jakości. W poniższej tabeli wymieniono konkretne zasady do użycia dla każdego typu oraz maksymalne odroczenie dla każdego z nich.

|Kategoria |Zasady |Maksymalne odroczenie |
| --- | --- | --- |
|Aktualizacje funkcji |DeferFeatureUpdatesPeriodInDays |365 dni |
|Aktualizacje dotyczące jakości |DeferQualityUpdatesPeriodInDays |30 dni |

#### <a name="pause-updates-via-device"></a>Wstrzymywanie aktualizacji za pośrednictwem urządzenia

Jeśli użytkownik nie ma dostępu do rozwiązania MDM, może indywidualnie wstrzymać aktualizacje do 35 dni ręcznie na urządzeniu HoloLens 2 w kompilacji Systemu Windows Holographic w wersji [2004](hololens-release-notes.md#windows-holographic-version-2004) lub nowszej. Użytkownicy mogą uzyskać dostęp do tego ustawienia, przechodząc do opcji Ustawienia > Update &  Security **> Advanced,** przewiń w dół do opcji Wstrzymaj aktualizacje i wybierz datę, do której wstrzymają aktualizacje. Gdy użytkownik osiągnie limit wstrzymania, urządzenie będzie musiało pobrać nowe aktualizacje, zanim będzie można je ponownie wstrzymać. 

Począwszy od [systemu Windows Holographic w wersji 20H2,](hololens-release-notes.md#windows-holographic-version-20h2)tą funkcją aktualizacji pauzy można zarządzać dla urządzeń HoloLens 2. 
- [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0 (ustawienie domyślne) — włączone
    - 1 — wyłączone

#### <a name="intune-update-management-functions-that-hololens-supports"></a>Funkcje zarządzania aktualizacjami usługi Intune, które obsługuje urządzenie HoloLens

Do zarządzania aktualizacjami dla urządzenia HoloLens można użyć następujących funkcji zarządzania aktualizacjami usługi Intune.

- **Tworzenie** i **przypisywanie:** te funkcje dodają Windows 10 aktualizacji do listy pierścieni aktualizacji. Aby uzyskać więcej informacji, zobacz Create and assign update rings (Tworzenie [i przypisywanie pierścieni aktualizacji).](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)

- **Wstrzymaj:** jeśli podczas wdrażania aktualizacji dotyczącej funkcji lub jakości wystąpi problem, możesz wstrzymać aktualizację na 35 dni (począwszy od określonej daty). Ta pauza uniemożliwia innym urządzeniem instalowanie aktualizacji do momentu rozwiązania lub rozwiązania problemu. Jeśli wstrzymasz aktualizację funkcji, aktualizacje dotyczące jakości będą nadal oferowane na urządzeniach, aby zapewnić ich bezpieczeństwo. Jeśli typ aktualizacji został wstrzymany, okienko omówienia tego pierścienia zawiera liczbę dni pozostałych do wznowienia typu aktualizacji. Po upływie określonego czasu wstrzymanie automatycznie wygasa, a proces aktualizacji zostaje wznowiony.

  Gdy pierścień aktualizacji jest wstrzymany, możesz wybrać jedną z następujących opcji:

  - **Rozszerz:** wydłuż okres wstrzymania dla typu aktualizacji o 35 dni.
  - **Wznów:** przywracanie aktualizacji dla tego pierścienia do aktywnej operacji. Jeśli jest to konieczne, możesz ponownie wstrzymać pierścień aktualizacji.

  > [!NOTE]  
  > Operacja **odinstalowywania** pierścieni aktualizacji nie jest obsługiwana w przypadku urządzeń HoloLens 2.

### <a name="delivery-optimization-preview"></a>Optymalizacja dostarczania zapoznawcza

[System Windows Holographic w wersji 21H1](hololens-release-notes.md#windows-holographic-version-21h1) włączono wczesną wersję zapoznawczą ustawień optymalizacji dostarczania w celu zmniejszenia zużycia przepustowości w przypadku pobierania z wielu urządzeń HoloLens. Pełniejsze opisy tej funkcji wraz z zalecaną konfiguracją sieci są dostępne tutaj: Optymalizacja dostarczania [do Windows 10 aktualizacji.](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)

Następujące ustawienia są włączane w ramach powierzchni zarządzania i [można je skonfigurować z usługi Intune:](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings)

- [DOCacheHost](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Kilka zastrzeżenia dotyczących tej oferty w wersji zapoznawczej:

- Obsługa urządzenia HoloLens w tej wersji zapoznawczej jest ograniczona tylko do aktualizacji systemu operacyjnego.
- Windows Holographic for Business obsługuje tylko tryby pobierania i pobierania http z punktu [końcowego usługi Microsoft Connected Cache ;](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) Tryby pobierania elementów równorzędnych i przypisania grup nie są obecnie obsługiwane w przypadku urządzeń HoloLens.
- Urządzenie HoloLens nie obsługuje optymalizacji wdrażania ani dostarczania dla Windows Server Update Services końcowych.
- Rozwiązywanie problemów będzie wymagało diagnostyki na serwerze Connected Cache lub zebrania śladu na urządzeniach HoloLens na urządzeniach HoloLens za pośrednictwem narzędzia Do rozwiązywania problemów z & Update  >  **Windows Update**  >     >   .

## <a name="manually-check-for-updates"></a>Ręczne sprawdzanie aktualizacji

Chociaż urządzenie HoloLens okresowo sprawdza aktualizacje systemu, mogą wystąpić okoliczności, w których chcesz ręcznie sprawdzić.

Aby ręcznie sprawdzić aktualizacje, przejdź do strony **Ustawienia**  >  **& sprawdzanie** zabezpieczeń  >  **aktualizacji.** Jeśli aplikacja Ustawienia wskazuje, że urządzenie jest aktualne, masz wszystkie aktualizacje, które są obecnie dostępne.

## <a name="manually-roll-back-an-update"></a>Ręczne wycofywanie aktualizacji

W niektórych przypadkach może być konieczne przywrócenie poprzedniej wersji oprogramowania HoloLens. Proces ten zależy od tego, czy używasz urządzenia HoloLens 2, czy HoloLens (1. generacji).

### <a name="revert-to-a-previous-version-hololens-2"></a>Przywracanie do poprzedniej wersji (HoloLens 2)

Możesz wycofać aktualizacje i wrócić do poprzedniej wersji urządzenia HoloLens 2, korzystając z narzędzia [Advanced Recovery Companion,](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) aby zresetować urządzenie HoloLens do starszej wersji.

> [!NOTE]
> Przywrócenie starszej wersji powoduje usunięcie osobistych plików i ustawień.

Aby przywrócić poprzednią wersję urządzenia HoloLens 2, wykonaj następujące kroki:

1. Upewnij się, że nie masz telefonów ani urządzeń z systemem Windows podłączonych do komputera.
1. Na komputerze pobierz program [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) z Microsoft Store.
1. Pobierz [najnowszą wersję urządzenia HoloLens 2.](https://aka.ms/hololens2download)
1. Po zakończeniu pobierania otwórz Eksploratora plików Pliki do pobrania, kliknij prawym przyciskiem myszy skompresowany folder (.zip), który właśnie został pobrany, a następnie wybierz pozycję Wyodrębnij wszystkie wyodrębnij, aby rozwinąć  >     >   plik.
1. Podłącz urządzenie HoloLens do komputera za pomocą kabla USB-A do USB-C. Nawet jeśli do podłączenia urządzenia HoloLens używasz innych kabli, ten rodzaj kabla działa najlepiej.
1. Pomocnik odzyskiwania zaawansowanego automatycznie wykrywa urządzenie HoloLens. Wybierz **kafelek Microsoft HoloLens** aplikacji.
1. Na następnym ekranie wybierz pozycję **Ręczne wybieranie pakietu,** a następnie otwórz wcześniej rozwinięty folder.
1. Wybierz plik instalacyjny (ffu).
1. Wybierz **pozycję Zainstaluj oprogramowanie,** a następnie postępuj zgodnie z instrukcjami.

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a>Przywróć poprzednią wersję (HoloLens (1. generacja))

Możesz wycofać aktualizacje i wrócić do poprzedniej wersji urządzenia HoloLens (1. generacji) przy użyciu narzędzia do odzyskiwania urządzeń z systemem [Windows (WDRT)](https://support.microsoft.com/help/12379) w celu zresetowania urządzenia HoloLens do starszej wersji.

> [!NOTE]
> Przywrócenie wcześniejszej wersji urządzenia HoloLens powoduje usunięcie osobistych plików i ustawień.

Aby przywrócić poprzednią wersję urządzenia HoloLens (1. generacja), wykonaj następujące kroki:

1. Upewnij się, że nie masz żadnych telefonów ani urządzeń z systemem Windows podłączonych do komputera.
1. Na komputerze pobierz narzędzie [Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379)
1. Pobierz pakiet [odzyskiwania rocznicowej aktualizacji urządzenia HoloLens.](https://aka.ms/hololensrecovery)
1. Po zakończeniu pobierania otwórz Eksploratora plików Pliki do pobrania, kliknij prawym przyciskiem myszy skompresowany folder (.zip), który właśnie został pobrany, a następnie wybierz pozycję Wyodrębnij wszystkie, aby rozwinąć  >     >   plik.
1. Użyj kabla mikro USB dostarczonego razem z urządzeniem HoloLens, aby podłączyć urządzenie HoloLens do komputera. Nawet jeśli do podłączania urządzenia HoloLens używasz innych kabli, ten kabel działa najlepiej.
1. WDRT automatycznie wykrywa urządzenie HoloLens. Wybierz **kafelek Microsoft HoloLens** aplikacji.
1. Na następnym ekranie wybierz pozycję **Ręczne wybieranie pakietu,** a następnie otwórz wcześniej rozwinięty folder.
1. Wybierz plik instalacyjny (ffu).
1. Wybierz **pozycję Zainstaluj oprogramowanie,** a następnie postępuj zgodnie z instrukcjami.

**Jeśli program WDRT nie wykryje urządzenia**

Jeśli program WDRT nie wykryje urządzenia HoloLens, spróbuj ponownie uruchomić komputer. Jeśli to nie zadziała, wybierz pozycję **Moje urządzenie** nie zostało wykryte, wybierz pozycję **Microsoft HoloLens**, a następnie postępuj zgodnie z instrukcjami.

## <a name="related-articles"></a>Pokrewne artykuły:

- [Informacje o wersji urządzenia HoloLens 2](https://docs.microsoft.com/hololens/hololens-release-notes)
- [Co to jest Windows Update dla Firm?](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [Przypisywanie urządzeń do kanałów obsługi na Windows 10 aktualizacji](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Zarządzanie aktualizacjami oprogramowania systemu Windows 10 w usłudze Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
