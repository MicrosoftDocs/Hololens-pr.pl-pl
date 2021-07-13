---
title: Enterprise Rejestrowanie urządzeń HoloLens w środowisku z ograniczeniami adresów MAC Wi-Fi MAC
description: Adres MAC sieci na urządzeniach z HoloLens 2
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 7938a433921a096913986f5eccff953fd17f1534
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639441"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>Enterprise Rejestrowanie urządzeń HoloLens w środowisku z ograniczeniami adresów MAC Wi-Fi MAC

W tym dokumencie opisano wspólny scenariusz zidentyfikowany w środowiskach klientów, w których adres Wi-Fi jest ograniczony przez adresy MAC lub certyfikaty są wymagane do dołączenia do sieci bezprzewodowych.

## <a name="example-scenario"></a>Przykładowy scenariusz

Wielu klientów w bezpiecznych środowiskach ma ograniczenia dotyczące sieci bezprzewodowych lub przewodowych, które umożliwią pomyślne łączenie się tylko zatwierdzonym urządzeniem (na podstawie adresów MAC). Można to wymusić za pomocą filtrowania adresów MAC w punkcie dostępu bezprzewodowego lub na serwerze DHCP. Ponadto niektóre sieci bezprzewodowe mogą być chronione przy użyciu protokołu PEAP, który wymaga, aby certyfikat był stosowany do urządzenia przed uwierzytelnienia w sieci bezprzewodowej.

W tym scenariuszu dwa kluczowe wymagania mogą powodować opóźnienia lub wymagać ręcznej interwencji podczas dołączania HoloLens urządzeń do sieci:

- Aby urządzenie pomyślnie dołączyło do sieci bezprzewodowej, należy do urządzenia zastosować certyfikat PEAP sieci bezprzewodowej.
- Adres MAC adaptera HoloLens Wi-Fi musi być zarejestrowany.

Podstawowe wyzwania związane z powyższymi wymaganiami to:

1. Adres MAC można obecnie zidentyfikować tylko z aplikacji Ustawienia na urządzeniu lub z usługi Intune po pomyślnej rejestracji.

2. Bez adresu MAC urządzenie nie może dołączyć do sieci Wi-Fi, aby rozpocząć rejestrację.

3. Ręczne obejścia tych problemów wymagają, aby technik współdziałał z urządzeniem.

## <a name="solutions"></a>Rozwiązania

Istnieje wiele sposobów na poprawienie tej sytuacji, w zależności od infrastruktury dostępnej w środowisku.

| Rozwiązanie | Korzyści | Wymagania |
| --- | --- | --- |
| Pakiet aprowizowania z adapterem Ethernet | Ulepsza środowisko OOBE i umożliwia szybsze środowisko techników. | HoloLens zgodny adapter USB-C Hub + Ethernet, a technik nadal będzie musiał wchodzić w interakcję z urządzeniem na potrzeby przechwytywania MAC i finalizacji OOBE |
| Funkcja Autopilot z rejestracją w usłudze Intune za pośrednictwem sieci Ethernet | Jest to jednoetapowe połączenie i rejestracja urządzenia w środowisku klienta. Przechwytywanie danych MAC można ukończyć bez konieczności interakcji z urządzeniem | Usługa Intune włączona dla dzierżawy usługi AAD klienta i HoloLens adaptera Ethernet USB-C |
| Automatyczne raportowanie adresów MAC | Gdy urządzenia są zarejestrowane w dzierżawie usługi Intune, skrypt może zgłosić adres MAC technikowi. | Polecenia cmdlet programu PowerShell w usłudze Intune |

## <a name="provisioning-package-with-ethernet-adaptor"></a>Pakiet aprowizowania z adapterem Ethernet

> [!NOTE] 
> Jeśli sieć przewodowa podlega również ograniczeniom adresów MAC, adres MAC adaptera USB-C Hub + Ethernet również musi być wstępnie zatwierdzony. Należy zachować ostrożność przy użyciu tej karty, ponieważ umożliwi to dostęp do sieci z innych urządzeń.

### <a name="requirements"></a>Wymagania

- Port sieci przewodowej z dostępem do sieci klienta
- HoloLens Zgodny koncentrator USB-C z adapterem Ethernet — odpowiednia powinna być każda karta, która nie wymaga dodatkowych sterowników ani instalacji aplikacji.
- Pakiet aprowizowania zawierający:
  - Zawierający informacje o sieci bezprzewodowej i certyfikat
  - Opcjonalnie zawierające informacje o rejestracji dla usługi Azure AD organizacji
  - Zawiera wszystkie inne wymagane ustawienia aprowowania

### <a name="process"></a>Proces

Proces może się różnić w zależności od poziomu oprogramowania urządzenia. Jeśli urządzenie ma aktualizację [z maja 2004](hololens-release-notes.md#windows-holographic-version-2004)r., wykonaj poniższe kroki.

1. Umieść pakiet aprowizowania na katalogu głównym dysku USB i podłącz go do koncentratora.
2. Połączenie Kabel Ethernet do adaptera Koncentrator + Ethernet.
3. Połączenie Koncentrator USB-C do HoloLens urządzenia.
4. Włącz HoloLens i umieść je na urządzeniu.
5. Naciśnij przycisk **Volume Down (Dół woluminu) i Power (Zasilanie),** aby zastosować pakiet aprowizowania.
6. Technik może teraz postępować zgodnie z ustawieniami OOBE, a po zakończeniu otwórz aplikację Ustawienia, aby pobrać adres MAC urządzenia.

Jeśli urządzenie ma kompilację systemu operacyjnego przed aktualizacją z [maja 2004](hololens-release-notes.md#windows-holographic-version-2004)r., wykonaj poniższe kroki.

1. Włącz urządzenie HoloLens podłącz urządzenie do komputera.
2. Urządzenie powinno być wyświetlane na komputerze jako urządzenie do przechowywania plików.
3. Kopiowanie pakietu aprowizowania na urządzenie
4. Połączenie Kabel Ethernet do koncentratora.
5. Połączenie Koncentrator USB-C do HoloLens urządzenia.
6. Umieść na HoloLens
7. Naciśnij przycisk **Volume Down (Dół woluminu) i Power (Zasilanie),** aby zastosować pakiet aprowizowania.
8. Technik może teraz postępować zgodnie z ustawieniami OOBE, a po zakończeniu otwórz aplikację Ustawienia, aby pobrać adres MAC urządzenia.

### <a name="benefits"></a>Korzyści

Pozwoli to na "dotknięcie pojedynczego dotyku" urządzenia w celu zastosowania poprawnego pakietu aprowizowania i zebrania adresu MAC urządzenia. [Pakiety aprowizowania można tworzyć zgodnie ze wskazówkami tutaj.](hololens-provisioning.md)

## <a name="autopilot-with-intune-enrollment"></a>Funkcja Autopilot z rejestracją w usłudze Intune

### <a name="requirements"></a>Wymagania

- Port sieci przewodowej z dostępem do sieci klienta
- HoloLens z systemem Windows Holographic 2004
- HoloLens Zgodny adapter Ethernet USB-C
- Konfigurowanie i włączanie usługi Intune dla dzierżawy klienta
- Urządzenie zarejestrowane na potrzeby rozwiązania Autopilot i zaimportowane do dzierżawy klienta
- Zasady usługi Intune zdefiniowane dla urządzenia:
   - Zawierający informacje o sieci bezprzewodowej i certyfikat
   - Zawiera wszystkie inne wymagane ustawienia aprowowania

Umożliwi to klientowi z zaawansowanymi wymaganiami sieciowymi zarejestrowanie urządzeń w praktycznej, skalowalnej podejściu

Wymagane będą dodatkowe wymagania wstępne, jak podano poniżej:
1. [Włącz dzierżawę dla wersji zapoznawczej rozwiązania Autopilot.](hololens2-autopilot.md)
1. Utwórz zasady HoloLens, aby zastąpić pakiet aprowizowania w usłudze Intune.
1. Utwórz zasady HoloLens Intune.
1. Przypisz urządzenia do odpowiedniej grupy.

### <a name="process"></a>Proces

1. Połączenie do adaptera i podłącz go do portu USB-C na urządzeniu HoloLens 2.

2. Włącz HoloLens.

3. Urządzenie powinno automatycznie łączyć się z Internetem podczas OOBE za pośrednictwem adaptera Ethernet. Powinna ona wykrywać konfigurację rozwiązania Autopilot i automatycznie rejestrować się w usłudze Azure AD i Intune.

4. Urządzenie zastosuje wymagane certyfikaty usługi Wi-Fi i inną konfigurację zgodnie z potrzebami za pośrednictwem usługi Intune.

5. Po zakończeniu technik może załadować portal usługi Intune (Endpoint Manager) i przejść do strony właściwości urządzenia na stronie Strona główna **-> Devices -> DeviceName -> Hardware**.

6. Adres Wi-Fi MAC będzie widoczny w portalu usługi Intune.

   ![Adres MAC za pośrednictwem usługi Intune](images/mac-address-intune.jpg)

7. Technik doda ten adres MAC jako dozwolone urządzenie.

### <a name="benefits"></a>Korzyści

Umożliwi to technikowi "odebranie" środowiska wdrażania z urządzeniem, które będzie możliwe z urządzenia do zarejestrowania w usłudze Azure AD i Intune bez konieczności noszenia urządzenia lub ręcznej interakcji ze środowiskiem HoloLens intune.

## <a name="reporting-of-mac-addresses-to-the-technician"></a>Raportowanie adresów MAC technikowi

### <a name="requirements"></a>Wymagania

- Autoryzacja usługi "Intune Graph PowerShell" względem dzierżawy klienta
- Instalacja programu PowerShell Graph Intune na maszynie techników.
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Dostęp do odczytu do elementów "Urządzenia zarządzane" usługi Intune. (Operator pomocy technicznej lub powyższy albo rola niestandardowa)

Obecnie nie ma "prostego" sposobu wyzwalania polecenia automatyzacji na podstawie rejestracji nowego urządzenia w usłudze Intune. W związku z tym to polecenie zapewni technikowi prosty sposób pobierania adresu MAC bez konieczności logowania się do portalu i ręcznego pobierania go.

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

Spowoduje to zwrócenie nazwy i adresu MAC wszystkich urządzeń HoloLens zarejestrowanych w ciągu ostatnich 30 dni.

![Adres MAC za pośrednictwem programu PowerShell](images/mac-address-powershell.jpg)

### <a name="process"></a>Proces

Po zakończeniu rejestracji w usłudze Intune technik uruchamia powyższy skrypt, aby pobrać adres MAC.
