---
title: Widoczność ustawień strony
description: Bądź na bieżąco z naszą listą obsługiwanych interfejsów URI dla elementów PageVisibilityList i Guide on HoloLens mixed reality devices (Lista obsługiwanych przez usługę PageVisibilityList i przewodnik na urządzeniach z rzeczywistością mieszaną HoloLens).
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens, hololens 2, przypisany dostęp, kiosk, strona ustawień
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d28994d911532a940d82756aa45609571ee80ac3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924336"
---
# <a name="page-settings-visibility"></a>Widoczność ustawień strony

Jedną z funkcji, które można zarządzać na urządzeniach HoloLens, jest użycie zasad [Settings/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) w celu ograniczenia stron widocznych w aplikacji Ustawienia. PageVisibilityList to zasady, które umożliwiają administratorom IT uniemożliwić widoczność lub dostępność określonych stron w aplikacji Ustawienia systemowe lub zrobić to dla wszystkich stron z wyjątkiem określonych.

> [!NOTE]
> Ta funkcja jest dostępna tylko w systemie Windows Holographic w wersji [20H2](hololens-release-notes.md#windows-holographic-version-20h2) lub wyższej dla urządzeń HoloLens 2. Upewnij się, że urządzenia, dla których zamierzasz używać tej funkcji, zostały zaktualizowane.

Poniższy przykład ilustruje zasady, które zezwalają na dostęp tylko do stron about i Bluetooth, które mają odpowiednio URI "ms-settings:network-wifi" i "ms-settings:bluetooth":
- `showonly:network-wifi;network-proxy;bluetooth`

Aby to ustawić za pośrednictwem pakietu aprowizowania:

1. Podczas tworzenia pakietu w projektancie konfiguracji systemu Windows przejdź do opcji **> ustawienia > PageVisibilityList**
1. Wprowadź ciąg: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Wyeksportuj pakiet aprowizowania.
1. Zastosuj pakiet do urządzenia.
Aby uzyskać szczegółowe informacje na temat tworzenia i stosowania pakietu aprowizowania, odwiedź [tę stronę.](hololens-provisioning.md)

Można to zrobić za pośrednictwem usługi Intune przy użyciu OMA-URI:

1. Utwórz zasady **niestandardowe.**
1. Podczas ustawiania wartości OMA-URI użyj ciągu: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. Podczas wybierania danych wybierz **pozycję** Ciąg
1. Podczas wpisywania wartości użyj: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Pamiętaj, aby przypisać niestandardową konfigurację urządzenia do grupy, w która ma się znaleźć urządzenie.

Aby uzyskać więcej informacji na temat grup i konfiguracji urządzeń usługi Intune, zobacz Konfiguracja urządzenia [HoloLens MDM.](hololens-mdm-configure.md)

Niezależnie od wybranej metody urządzenie powinno teraz otrzymywać zmiany, a użytkownikom zostanie przedstawiona następująca aplikacja Ustawienia.

![Zrzut ekranu przedstawiający modyfikację godzin aktywnego działania w aplikacji Ustawienia](images/hololens-page-visibility-list.jpg)

Aby skonfigurować strony aplikacji Ustawienia do pokazywania lub ukrywania własnych wybranych stron, zobacz Ustawienia URI dostępne na urządzeniach HoloLens.

## <a name="settings-uris"></a>Ustawienia URI

Urządzenia HoloLens i Windows 10 mają różne strony w aplikacji Ustawienia. Na tej stronie znajdziesz tylko ustawienia, które istnieją na urządzeniach HoloLens.

### <a name="accounts"></a>Konta
| Strona Ustawienia           | URI                                            |
|-------------------------|------------------------------------------------|
| Dostęp do zasobów służbowych | `ms-settings:workplace`                         |
| Rejestracja irysów       | `ms-settings:signinoptions-launchirisenrollment` |
| Opcje logowania         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a>Apps
| Strona Ustawienia | URI                          |
|---------------|------------------------------|
| Funkcje &<sup>2</sup>     | `ms-settings:appsfeatures` <br> |
| Funkcje & aplikacji > opcje zaawansowane <sup>2</sup>     | `ms-settings::appsfeatures-app` <br> |
| Funkcje & aplikacji > Offline Maps <sup>2</sup>     | `ms-settings:maps-maps` <br> |
| Aplikacje & funkcje > Mapy offline > Pobieranie map <sup>2</sup>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a>Urządzenia
| Strona Ustawienia | URI                          |
|---------------|------------------------------|
| Bluetooth     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| Mysz <sup>2</sup>      | `ms-settings:mouse` <br>  |
| USB <sup>2</sup>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a>Prywatność
| Strona Ustawienia            | URI                                             |
|--------------------------|-------------------------------------------------|
| Informacje o koncie             | `ms-settings:privacy-accountinfo`              |
| Diagnostyka aplikacji        | `ms-settings:privacy-appdiagnostics`              |
| Aplikacje w tle        | `ms-settings:privacy-backgroundapps`              |
| Kalendarz                 | `ms-settings:privacy-calendar`                    |
| Historia połączeń             | `ms-settings:privacy-callhistory`                 |
| Aparat fotograficzny                   | `ms-settings:privacy-webcam`                      |
| Kontakty                 | `ms-settings:privacy-contacts`                    |
| Opinia & diagnostyki | `ms-settings:privacy-feedback`                    |
| Dokumenty                | `ms-settings:privacy-documents`                   |
| E-mail                    | `ms-settings:privacy-email`                       |
| System plików              | `ms-settings:privacy-broadfilesystemaccess`       |
| Ogólne <sup>2</sup>             | `ms-settings:privacy-general`       |
| Personalizacja & pisma odręcznego <sup>2</sup>             | `ms-settings:privacy-speechtyping`       |
| Lokalizacja                 | `ms-settings:privacy-location`                    |
| Obsługa wiadomości                | `ms-settings:privacy-messaging`                   |
| Mikrofon               | `ms-settings:privacy-microphone`                  |
| Ruch <sup>2</sup>               | `ms-settings:privacy-motion`                  |
| Powiadomienia            | `ms-settings:privacy-notifications`               |
| Inne urządzenia            | `ms-settings:privacy-customdevices`               |
| Obrazy                 | `ms-settings:privacy-pictures`                    |
| Radia                   | `ms-settings:privacy-radios`                      |
| Zrzut ekranu przedstawiający <sup>obramowanie 2</sup>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| Zrzuty ekranu i aplikacje <sup>2</sup>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| Mowa                   | `ms-settings:privacy-speech`                      |
| Zadania                    | `ms-settings:privacy-tasks`                       |
| Ruchy użytkowników           | `ms-settings:privacy-backgroundspatialperception` |
| Filmy wideo                   | `ms-settings:privacy-videos`                      |
| Aktywacja głosowa       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a>Sieć i Internet
| Strona Ustawienia | URI                              |
|---------------|----------------------------------|
| Tryb <sup>samolotowy 2</sup> | `ms-settings:network-airplanemode`        |
| Serwer proxy | `ms-settings:network-proxy`        |
| VPN   | `ms-settings:network-vpn`          |
| Wi-Fi  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a>System
| Strona Ustawienia      | URI                                |
|--------------------|------------------------------------|
| Bateria <sup>2</sup>           | `ms-settings:batterysaver`<br>|
| Bateria <sup>2</sup>           | `ms-settings:batterysaver-settings`<br>|
| Kolory             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| Hologramy <sup>2</sup>  |  `ms-settings:holograms`  |
| Przekłoń <sup>2</sup> |  `ms-settings:calibration` |
| Powiadomienia & akcje  | `ms-settings:notifications`          |
| Udostępnione doświadczenia | `ms-settings:crossdevice` 
| Dźwięk <sup>2</sup>           | `ms-settings:sound`<br>|
| Dźwięk > aplikacji i preferencja urządzenia <sup>2</sup>           | `ms-settings:apps-volume`<br>|
| Zarządzanie > dźwięku <sup>2</sup>           | `ms-settings:sound-devices`<br>|
| Storage            | `ms-settings:storagesense`           |
| Konfigurowanie > magazynu Czujnik pamięci <sup>2</sup>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a>Język & czasu
| Strona Ustawienia | URI                                           |
|---------------|-----------------------------------------------|
| Data & <sup>2</sup> | `ms-settings:dateandtime`                  |
| Klawiatura <sup>2</sup> | `ms-settings:keyboard`                  |
| Język <sup>2</sup> | `ms-settings:language`                  |
| Język <sup>2</sup> | `ms-settings:regionlanguage-languageoptions`                  |
| Język      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| Region (Region)        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a>Aktualizowanie & zabezpieczeń
| Strona Ustawienia                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Opcje zaawansowane                    | `ms-settings:windowsupdate-options`         |
| Resetowanie & odzyskiwania <sup>2</sup>      | `ms-settings:reset`         |
| Niejawny program testów systemu Windows               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| Windows Update                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup>1</sup>`ms-settings:windowsupdate-options`<br><sup>1</sup>`ms-settings:windowsupdate-restartoptions` |
| Windows Update — sprawdzanie, czy są dostępne aktualizacje | `ms-settings:windowsupdate-action`          |


- <sup>1</sup> — w przypadku wersji wcześniejszych niż Windows Holographic, wersja 21H1,  następujące dwa interfejsy URI w rzeczywistości nie przejdą do stron Opcje zaawansowane **ani** Opcje. Będą blokować lub wyświetlać tylko główną Windows Update internetową.
  -  ms-settings:windowsupdate-options
  -  ms-settings:windowsupdate-restartoptions

- <sup>2 —</sup> dostępne w systemie Windows Holographic 21H1 lub wyższym.


Aby uzyskać pełną listę Windows 10 URI ustawień uruchamiania, zapoznaj się z [dokumentacją ustawień uruchamiania.](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)
