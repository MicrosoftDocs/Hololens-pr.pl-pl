---
title: Zarządzanie HoloLens aktualizacji
description: Dowiedz się, jak administratorzy mogą używać zarządzania urządzeniami przenośnymi do zarządzania aktualizacjami HoloLens urządzeń.
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
ms.openlocfilehash: 3afe3d2aecd64c2b4724f4805571cb3c46112875
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036498"
---
# <a name="manage-hololens-updates"></a>Zarządzanie HoloLens aktualizacji

HoloLens używa Windows Update w taki sam sposób jak inne Windows 10 urządzenia. Gdy aktualizacja będzie dostępna, zostanie ona automatycznie pobrana i zainstalowana przy następnym podłączeniu urządzenia do Internetu i połączeniu się z Internetem. W tym artykule opisano sposób zarządzania aktualizacjami w przedsiębiorstwie lub innym środowisku zarządzanym. Aby uzyskać informacje na temat zarządzania aktualizacjami poszczególnych urządzeń HoloLens, zobacz [Update HoloLens](hololens-update-hololens.md).

## <a name="manage-updates-automatically"></a>Automatyczne zarządzanie aktualizacjami

### <a name="managing-updates-by-using-windows-update-for-business"></a>Zarządzanie aktualizacjami przy użyciu Windows Update dla Firm

Windows Holographic for Business zarządzać [aktualizacjami za pomocą Windows Update for Business.](/windows/deployment/update/waas-manage-updates-wufb) Wszystkie HoloLens 2 mogą używać Windows Holographic for Business. Upewnij się, że używają Windows Holographic for Business kompilacji 10.0.18362.1042 lub nowszej. Jeśli masz HoloLens (1. generacji), musisz uaktualnić je do wersji [Windows Holographic for Business,](hololens1-upgrade-enterprise.md) aby zarządzać ich aktualizacjami.

Windows Usługa Update for Business HoloLens bezpośrednio z usługą Windows Update. Za pomocą Windows Update for Business można kontrolować wiele aspektów procesu aktualizacji, czyli to, które urządzenia mogą uzyskać aktualizacje o &mdash; każdej godzinie. Można na przykład w celu testowania wycofywał aktualizacje do podzbioru urządzeń, a następnie je później wycofywał na pozostałych urządzeniach. Można również zdefiniować różne harmonogramy aktualizacji dla różnych typów aktualizacji.

> [!NOTE]  
> W HoloLens można automatycznie zarządzać aktualizacjami funkcji (wydanymi dwa razy w roku) i aktualizacjami jakości (wydanymi co miesiąc lub zgodnie z wymaganiami, w tym krytycznymi aktualizacjami zabezpieczeń). Aby uzyskać więcej informacji na temat typów aktualizacji, zobacz [Typy aktualizacji zarządzanych przez usługę Windows Update for Business.](/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business)

Ustawienia usługi Windows Update for Business dla usługi HoloLens można skonfigurować przy użyciu zasad w rozwiązaniu mobile Zarządzanie urządzeniami (MDM), takim jak Microsoft Intune.

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>Zarządzanie Windows Update dla firm przy użyciu usługi Microsoft Intune

Aby uzyskać szczegółowe omówienie sposobu używania usługi Intune do konfigurowania usługi Windows Update dla firm, zobacz Zarządzanie Windows 10 [aktualizacjami oprogramowania w usłudze Intune.](/intune/protect/windows-update-for-business-configure) Aby uzyskać więcej informacji na temat określonych funkcji usługi Intune, które HoloLens obsługuje, zobacz Funkcje zarządzania aktualizacjami usługi [Intune, które HoloLens usługi](#intune-update-management-functions-that-hololens-supports).

> [!IMPORTANT]  
> Usługa Intune udostępnia dwa typy zasad do zarządzania aktualizacjami: *Windows 10 pierścienia aktualizacji* *i Windows 10 aktualizacji funkcji.* Typ Windows 10 aktualizacji funkcji jest obecnie w publicznej wersji zapoznawczej i nie jest obsługiwany HoloLens.
>  
> Zasady pierścienia Windows 10 do zarządzania aktualizacjami HoloLens 2.

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>Konfigurowanie zasad aktualizacji dla HoloLens 2 lub HoloLens (1. generacja)

W tej sekcji opisano zasady, których można użyć do zarządzania aktualizacjami dla HoloLens 2 lub HoloLens (1. generacji). Aby uzyskać więcej informacji na temat funkcji dostępnych dla wersji HoloLens 2, zobacz Planowanie i konfigurowanie we/wy aktualizacji dla wersji [HoloLens 2.](#plan-and-configure-update-rollouts-for-hololens-2)

[Zasady CSP — aktualizacja](/windows/client-management/mdm/policy-csp-update) definiuje zasady, które konfigurują usługę Windows Update for Business.

> [!NOTE]  
> Aby uzyskać listę określonych dostawców usług konfiguracji zasad (CSP), którzy są obsługiwani przez określone wersje programu HoloLens, zobacz [Policy CSPs supported by HoloLens devices](/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices)(Dostawcy usługi konfiguracji zasad obsługiwani przez HoloLens usługi ).

#### <a name="configure-automatic-checks-for-updates"></a>Konfigurowanie automatycznego sprawdzania aktualizacji

Zasady **Update/AllowAutoUpdate** umożliwiają zarządzanie automatycznym zachowaniem aktualizacji, takim jak skanowanie, pobieranie i instalowanie aktualizacji. Aby uzyskać więcej informacji na temat dostępnych ustawień dla tych zasad, zobacz [Update/AllowAutoUpdate](/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> W Microsoft Intune można zmienić **te** zasady za pomocą automatycznego zachowania aktualizacji. Aby uzyskać więcej informacji, zobacz [Zarządzanie Windows 10 aktualizacjami oprogramowania w usłudze Intune.](/intune/windows-update-for-business-configure)

#### <a name="configure-an-update-schedule"></a>Konfigurowanie harmonogramu aktualizacji

Aby skonfigurować sposób i czas stosowania aktualizacji, użyj następujących zasad:

- [Update/ScheduledInstallDay](/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - Wartości: **0–7**(0 = codziennie, 1 = niedziela, 7 = sobota)
  - Wartość domyślna: **0** (codziennie)
- [Update/ScheduledInstallTime](/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Wartości: 0–23 (0 = północ, 23 = 21:00)
  - Wartość domyślna: 3:00

#### <a name="configure-active-hours"></a>Konfigurowanie godzin aktywnego działania
Począwszy od Windows Holographic, w wersji [20H2](hololens-release-notes.md#windows-holographic-version-20h2) administrator IT może określić zakres godzin aktywnego HoloLens 2 urządzeń.

Aktywne godziny identyfikują okres, w którym urządzenie ma być w użyciu. Automatyczne ponowne uruchamianie po aktualizacji nastąpi poza godzinami aktywności. Określony zakres będzie liczony od godziny rozpoczęcia godzin aktywnego działania. Możesz użyć rozwiązania MDM zgodnie z opisem w tece [Konfigurowanie godzin aktywnego użytkowania za pomocą rozwiązania MDM.](/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm) Rozwiązanie MDM używa ustawień Update/ActiveHoursStart i Update/ActiveHoursEnd i Update/ActiveHoursMaxRange w programie CSP zasad do konfigurowania godzin aktywności.

-   [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend) — ta wartość określa czas zakończenia. Od rozpoczęcia jest 12-godzinny limit.
    -   Obsługiwane wartości to 0–23, gdzie 0 to 12:00, 1 to 1:00 itd.
    -   Wartość domyślna to 17 (17:00).
-   [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) — ta wartość określa maksymalną liczbę aktywnych godzin od czasu rozpoczęcia.
    -   Obsługiwane wartości to 8–18.
    -   Wartość domyślna to 18 (godziny).
-   [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart) — ta wartość określa czas rozpoczęcia. Istnieje maksymalnie 12-godzinny czas od zakończenia.
    -   Obsługiwane wartości to 0–23, gdzie 0 to 12:00, 1 to 1:00 itd.
    -   Wartość domyślna to 8 (8:00).

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a>Urządzenia z systemem Windows 10 tylko w wersji 1607

Następujące zasady aktualizacji można użyć do skonfigurowania urządzeń w celu uzyskania aktualizacji z usługi Windows Server Update Service (WSUS), a nie z Windows Update:

- [Update/AllowUpdateService](/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Update/RequireUpdateApproval](/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>Planowanie i konfigurowanie we/wy aktualizacji dla wersji HoloLens 2

HoloLens 2 obsługuje więcej funkcji automatyzacji aktualizacji niż HoloLens (1. generacja). Jest to szczególnie istotne, jeśli używasz usługi Microsoft Intune do zarządzania Windows update for Business. Te funkcje ułatwiają planowanie i wdrażanie aktualizacji w całej organizacji.

#### <a name="plan-the-update-strategy"></a>Planowanie strategii aktualizacji

Windows Aktualizacje dla firm obsługują zasady odroczenia. Po wydaniu aktualizacji przez firmę Microsoft można użyć zasad odroczenia, aby zdefiniować czas oczekiwania przed zainstalowaniem tej aktualizacji na urządzeniach. Kojarząc podzestawy urządzeń (nazywane również pierścieniami *aktualizacji)* z różnymi zasadami odroczenia, można skojarzyć strategię aktualizacji w organizacji.

Rozważmy na przykład organizację, która ma 1000 urządzeń i musi aktualizować urządzenia w pięciu falach. Organizacja może utworzyć pięć pierścieni aktualizacji, jak pokazano w poniższej tabeli.

|Group (Grupa) |Liczba urządzeń |Odroczenie (dni) |
| ---| :---: | :---: |
|Grp 1 (personel IT) |5 |0 |
|Grp 2 (wcześnie adoptatorzy) |50 |60 |
|Grp 3 (główny 1) |250 |120 |
|Grp 4 (główny 2) |300 |150 |
|Grp 5 (główny 3) |395 |180 |

Oto jak w czasie będzie się to dzieje w całej organizacji.

![Oś czasu wdrażania aktualizacji.](./images/hololens-updates-timeline.png)

#### <a name="configure-an-update-deferral-policy"></a>Konfigurowanie zasad odroczenia aktualizacji

Zasady odroczenia określają liczbę dni między datą, w której aktualizacja stanie się dostępna, a datą, w której aktualizacja jest oferowana urządzeniu.

Można skonfigurować różne odroczenia dla aktualizacji funkcji i aktualizacji jakości. W poniższej tabeli wymieniono konkretne zasady do użycia dla każdego typu oraz maksymalne odroczenie dla każdego z nich.

|Kategoria |Zasady |Maksymalne odroczenie |
| --- | --- | --- |
|Aktualizacje funkcji |DeferFeatureUpdatesPeriodInDays |365 dni |
|Aktualizacje dotyczące jakości |DeferQualityUpdatesPeriodInDays |30 dni |

#### <a name="pause-updates-via-device"></a>Wstrzymywanie aktualizacji za pośrednictwem urządzenia

Jeśli użytkownik nie ma dostępu do rozwiązania MDM, może indywidualnie wstrzymać aktualizacje do 35 dni ręcznie na urządzeniu z systemem HoloLens 2 w kompilacji Windows Holographic w wersji [2004](hololens-release-notes.md#windows-holographic-version-2004) lub nowszej. Użytkownicy mogą uzyskać dostęp do tego ustawienia, przechodząc do Ustawienia > **Update & Security > Advanced** options scroll down to Pause **updates** and select the date which they will pause updates. Gdy użytkownik osiągnie limit wstrzymania, urządzenie będzie musiało pobrać nowe aktualizacje, zanim będzie można je ponownie wstrzymać. 

Począwszy od Windows Holographic w wersji [20H2,](hololens-release-notes.md#windows-holographic-version-20h2)tą funkcją wstrzymywania aktualizacji można zarządzać dla HoloLens 2. 
- [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0 (ustawienie domyślne) — włączone
    - 1 — wyłączone

#### <a name="intune-update-management-functions-that-hololens-supports"></a>Funkcje zarządzania aktualizacjami usługi Intune, HoloLens obsługuje

Następujące funkcje zarządzania aktualizacjami usługi Intune mogą być służące do zarządzania aktualizacjami HoloLens.

- **Tworzenie** i **przypisywanie:** te funkcje dodają Windows 10 pierścienia aktualizacji do listy pierścieni aktualizacji. Aby uzyskać więcej informacji, zobacz Create and assign update rings (Tworzenie [i przypisywanie pierścieni aktualizacji).](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)

- **Wstrzymaj:** jeśli podczas wdrażania aktualizacji dotyczącej funkcji lub jakości wystąpi problem, możesz wstrzymać aktualizację na 35 dni (począwszy od określonej daty). Ta pauza uniemożliwia innym urządzeniem instalowanie aktualizacji do momentu rozwiązania lub rozwiązania problemu. Jeśli wstrzymasz aktualizację funkcji, aktualizacje dotyczące jakości będą nadal oferowane na urządzeniach, aby zapewnić ich bezpieczeństwo. Jeśli typ aktualizacji został wstrzymany, okienko omówienia tego pierścienia zawiera liczbę dni pozostałych do wznowienia typu aktualizacji. Po upływie określonego czasu wstrzymanie automatycznie wygasa, a proces aktualizacji zostaje wznowiony.

  Gdy pierścień aktualizacji jest wstrzymany, możesz wybrać jedną z następujących opcji:

  - **Rozszerz:** wydłuż okres wstrzymania dla typu aktualizacji o 35 dni.
  - **Wznów:** przywracanie aktualizacji dla tego pierścienia do aktywnej operacji. Jeśli jest to konieczne, możesz ponownie wstrzymać pierścień aktualizacji.

  > [!NOTE]  
  > Operacja **odinstalowywania** pierścieni aktualizacji nie jest obsługiwana w przypadku HoloLens 2.

### <a name="delivery-optimization-preview"></a>Optymalizacja dostarczania zapoznawcza

[Windows Holographic w wersji 21H1](hololens-release-notes.md#windows-holographic-version-21h1) włączono wczesną wersję zapoznawczą ustawień optymalizacji dostarczania w celu zmniejszenia zużycia przepustowości w przypadku pobierania z HoloLens urządzeń. Pełniejsze opisy tej funkcji wraz z zalecaną konfiguracją sieci są dostępne tutaj: Optymalizacja dostarczania [dla Windows 10 aktualizacji.](/windows/deployment/update/waas-delivery-optimization)

Następujące ustawienia są włączane w ramach powierzchni zarządzania i [można je skonfigurować z usługi Intune:](/mem/intune/configuration/delivery-optimization-settings)

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Kilka zastrzeżenia dotyczących tej oferty w wersji zapoznawczej:

- HoloLens w tej wersji zapoznawczej jest ograniczona tylko do aktualizacji systemu operacyjnego.
- Windows Holographic for Business obsługuje tylko tryby pobierania http i pobieranie z punktu [końcowego Connected Cache Microsoft;](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache) Tryby pobierania równorzędne i przypisania grup nie są obecnie obsługiwane HoloLens równorzędnych.
- HoloLens nie obsługuje optymalizacji wdrażania ani dostarczania dla Windows Server Update Services końcowych.
- Rozwiązywanie problemów będzie wymagało diagnostyki na serwerze Connected Cache lub zebrania śladu na serwerze HoloLens na HoloLens za pośrednictwem usługi **Ustawienia**  >  **Update & Security**  >   **Troubleshooting** Windows  >   **Update.**

## <a name="manually-check-for-updates"></a>Ręczne sprawdzanie aktualizacji

Chociaż HoloLens okresowo sprawdza aktualizacje systemu, mogą wystąpić okoliczności, w których chcesz ręcznie sprawdzić.

Aby ręcznie sprawdzić aktualizacje, przejdź do Ustawienia  >  **Update & Security** Check for  >  **updates**. Jeśli aplikacja Ustawienia wskazuje, że urządzenie jest aktualne, masz wszystkie aktualizacje, które są obecnie dostępne.

## <a name="manually-roll-back-an-update"></a>Ręczne wycofywanie aktualizacji

W niektórych przypadkach może być konieczne przywrócenie poprzedniej wersji HoloLens oprogramowania. Proces ten zależy od tego, czy używasz usługi HoloLens 2, czy HoloLens (1. generacja).

### <a name="revert-to-a-previous-version-hololens-2"></a>Przywróć poprzednią wersję (HoloLens 2)

Możesz wycofać aktualizacje i wrócić do poprzedniej wersji programu [](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) HoloLens 2 przy użyciu zaawansowanego pomocnika odzyskiwania, aby zresetować HoloLens do starszej wersji.

> [!NOTE]
> Przywrócenie starszej wersji powoduje usunięcie osobistych plików i ustawień.

Aby przywrócić poprzednią wersję HoloLens 2, wykonaj następujące kroki:

1. Upewnij się, że nie masz żadnych telefonów ani urządzeń Windows podłączonych do komputera.
1. Na komputerze pobierz program [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) z Microsoft Store.
1. Pobierz [najnowszą wersję HoloLens 2.](https://aka.ms/hololens2download)
1. Po zakończeniu pobierania otwórz Eksploratora plików Pliki do pobrania, kliknij prawym przyciskiem myszy skompresowany folder (.zip), który właśnie został pobrany, a następnie wybierz polecenie Wyodrębnij wszystko Wyodrębnij, aby rozwinąć  >     >   plik.
1. Użyj kabla USB-A do USB-C, aby podłączyć urządzenie HoloLens do komputera. Nawet jeśli używasz innych kabli do podłączenia urządzenia HoloLens, ten rodzaj kabla działa najlepiej.
1. Pomocnik odzyskiwania zaawansowanego automatycznie wykrywa urządzenie HoloLens odzyskiwania. Wybierz **kafelek Microsoft HoloLens** aplikacji.
1. Na następnym ekranie wybierz pozycję **Ręczne wybieranie pakietu,** a następnie otwórz wcześniej rozwinięty folder.
1. Wybierz plik instalacyjny (ffu).
1. Wybierz **pozycję Zainstaluj oprogramowanie,** a następnie postępuj zgodnie z instrukcjami.

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a>Przywróć poprzednią wersję (HoloLens (1. generacja))

Możesz wycofać aktualizacje i wrócić do poprzedniej wersji programu HoloLens (1. generacji) przy użyciu narzędzia [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) w celu zresetowania wersji HoloLens do starszej wersji.

> [!NOTE]
> Przywrócenie starszej wersji HoloLens powoduje usunięcie osobistych plików i ustawień.

Aby przywrócić poprzednią wersję HoloLens (1. generacji), wykonaj następujące kroki:

1. Upewnij się, że nie masz żadnych telefonów ani urządzeń Windows podłączonych do komputera.
1. Na komputerze pobierz narzędzie [Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379)
1. Pobierz pakiet [odzyskiwania HoloLens Anniversary Update.](https://aka.ms/hololensrecovery)
1. Po zakończeniu pobierania otwórz Eksploratora plików Pliki do pobrania, kliknij prawym przyciskiem myszy skompresowany folder (.zip), który właśnie został pobrany, a następnie wybierz pozycję Wyodrębnij wszystkie, aby rozwinąć  >     >   plik.
1. Użyj kabla mikro USB dostarczonego razem z urządzeniem HoloLens, aby podłączyć urządzenie HoloLens do komputera. Nawet jeśli używasz innych kabli do podłączania urządzenia HoloLens, ten z nich działa najlepiej.
1. Program WDRT automatycznie wykrywa HoloLens urządzenia. Wybierz **kafelek Microsoft HoloLens** aplikacji.
1. Na następnym ekranie wybierz pozycję **Ręczne wybieranie pakietu,** a następnie otwórz wcześniej rozwinięty folder.
1. Wybierz plik instalacyjny (ffu).
1. Wybierz **pozycję Zainstaluj oprogramowanie,** a następnie postępuj zgodnie z instrukcjami.

**Jeśli program WDRT nie wykryje urządzenia**

Jeśli program WDRT nie wykryje urządzenia HoloLens, spróbuj ponownie uruchomić komputer. Jeśli to nie zadziała, wybierz pozycję **Moje urządzenie** nie zostało wykryte, wybierz pozycję Microsoft HoloLens **,** a następnie postępuj zgodnie z instrukcjami.

## <a name="related-articles"></a>Pokrewne artykuły:

- [HoloLens wersji 2](hololens-release-notes.md)
- [Co to jest Windows Update dla firm?](/windows/deployment/update/waas-manage-updates-wufb)
- [Przypisywanie urządzeń do kanałów obsługi na Windows 10 aktualizacji](/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Zarządzanie aktualizacjami oprogramowania systemu Windows 10 w usłudze Intune](/mem/intune/protect/windows-update-for-business-configure)
