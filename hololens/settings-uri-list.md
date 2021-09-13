---
title: Widoczność Ustawienia strony
description: Bądź na bieżąco z naszą listą obsługiwanych adresów URI dla elementów PageVisibilityList i Guide on HoloLens rzeczywistości mieszanej.
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
ms.openlocfilehash: 92040019b093c5ef63d74f095dcb3809112ae7a0
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036578"
---
# <a name="page-settings-visibility"></a>Widoczność Ustawienia strony

Jedną z funkcji, które można zarządzać HoloLens, jest użycie zasad [Ustawienia/PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) w celu ograniczenia stron widocznych w Ustawienia aplikacji. PageVisibilityList to zasady, które umożliwiają administratorom IT uniemożliwić widoczność lub dostępność określonych stron w aplikacji System Ustawienia lub na ich użycie dla wszystkich stron z wyjątkiem określonych.

> [!NOTE]
> Ta funkcja jest dostępna tylko w Windows Holographic w wersji [20H2](hololens-release-notes.md#windows-holographic-version-20h2) lub wyższej dla urządzeń HoloLens 2. Upewnij się, że urządzenia, dla których zamierzasz używać tej funkcji, zostały zaktualizowane.


## <a name="examples"></a>Przykłady
Strony są identyfikowane za pomocą skróconej wersji opublikowanych identyfikatora URI, czyli identyfikatora URI minus prefiks "ms-settings:".

Poniższy przykład ilustruje zasady, które zezwalają na dostęp tylko do stron about i Bluetooth, które mają odpowiednio URI "sieć-Wi-Fi" i "bluetooth":
- `showonly:network-wifi;network-proxy;bluetooth`

Poniższy przykład ilustruje zasady, które ukrywałyby stronę Resetowanie systemu operacyjnego:
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a>Wdrażanie tych zasad za pośrednictwem usługi Intune

Są to wartości konfiguracji, które zostaną dostarczone do usługi Intune:

- **Nazwa:** Preferowana przez administratora nazwa wyświetlana profilu.
- **OMA-URI:** W pełni kwalifikowany URI strony ustawienia, w tym jej [zakres](/windows/client-management/mdm/policy-configuration-service-provider). Te przykłady na tej stronie są przy użyciu `./Device` zakresu.
- **Wartość:** Wartość ciągu wskazująca, czy ukrywać lub *wyświetlać tylko* określone strony. Możliwe wartości to `hide:<pagename>` i `showonly:<pagename>` . 
 
Wiele stron można określić, oddzielając je średnikami, a listę typowych stron można znaleźć poniżej.

1. Utwórz zasady **niestandardowe.**
1. Podczas ustawiania wartości **OMA-URI** wprowadź w pełni ograniczony adres URI. Na przykład: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. Podczas wybierania danych wybierz **pozycję** Ciąg
1. Podczas określania **wartości skorzystaj** z powyższych wskazówek. Na przykład: **`showonly:network-wifi;network-proxy;bluetooth`** lub **`hide:reset`** 
> [!IMPORTANT]
> Pamiętaj, aby przypisać niestandardową konfigurację urządzenia do grupy, w która ma się znaleźć urządzenie. Jeśli ten krok nie zostanie wykonany, zasady zostaną wypchnięci, ale nie zostaną zastosowane.

Zobacz [HoloLens mdm,](hololens-mdm-configure.md) aby uzyskać więcej informacji na temat grup i konfiguracji urządzeń usługi Intune.


## <a name="deploying-this-policy-via-a-provisioning-package"></a>Wdrażanie tych zasad za pośrednictwem pakietu aprowizowania

Są to wartości konfiguracji, które zostaną określone w programie Windows Configuration Designer:

**Wartość:** Wartość ciągu wskazująca, czy ukrywać lub *wyświetlać tylko* określone strony. Możliwe wartości to `hide:<pagename>` i `showonly:<pagename>` . Wiele stron można określić, oddzielając je średnikami, a listę typowych stron można znaleźć poniżej.


1. Podczas tworzenia pakietu w programie Windows Configuration Designer przejdź do > Ustawienia > **PageVisibilityList**
1. Wprowadź ciąg: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Wyeksportuj pakiet aprowizowania.
1. Zastosuj pakiet do urządzenia.
Aby uzyskać szczegółowe informacje na temat tworzenia i stosowania pakietu aprowizowania, odwiedź [HoloLens aprowizowania.](hololens-provisioning.md)


Niezależnie od wybranej metody urządzenie powinno teraz otrzymywać zmiany, a użytkownikom zostaną przedstawione następujące Ustawienia App.

![Zrzut ekranu przedstawiający modyfikację godzin aktywnego Ustawienia aplikacji.](images/hololens-page-visibility-list.jpg)

Aby skonfigurować Ustawienia aplikacji do pokazywania lub ukrywania własnych wybranych stron, przyjrzyj się Ustawienia URI dostępnym na HoloLens.

## <a name="settings-uris"></a>Ustawienia Identyfikatory uri

HoloLens i Windows 10 mają różne strony w aplikacji Ustawienia aplikacji. Na tej stronie znajdziesz tylko ustawienia, które istnieją w HoloLens.

### <a name="accounts"></a>Konta
| Strona Ustawienia           | URI                                            |
|-------------------------|------------------------------------------------|
| Dostęp do zasobów służbowych | `workplace`                         |
| Rejestracja irysów       | `signinoptions-launchirisenrollment` |
| Opcje logowania         | ` signinoptions `                   |

### <a name="apps"></a>Apps
| Strona Ustawienia | URI                          |
|---------------|------------------------------|
| Funkcje & <sup>2</sup>     | `appsfeatures` <br> |
| Funkcje & aplikacji > opcje zaawansowane <sup>2</sup>     | `appsfeatures-app` <br> |
| Funkcje & aplikacji > offline Mapy <sup>2</sup>     | `maps-maps` <br> |
| Aplikacje & funkcje > offline Mapy > Pobierz mapy <sup>2</sup>     | `maps-downloadmaps` <br> |

### <a name="devices"></a>Urządzenia
| Strona Ustawienia | URI                          |
|---------------|------------------------------|
| Bluetooth     | `bluetooth` <br> `connecteddevices` |
| Mysz <sup>2</sup>      | `mouse` <br>  |
| USB <sup>2</sup>      | `usb` <br>  |

### <a name="privacy"></a>Prywatność
| Strona Ustawienia            | URI                                             |
|--------------------------|-------------------------------------------------|
| Informacje o koncie             | `privacy-accountinfo`              |
| Diagnostyka aplikacji        | `privacy-appdiagnostics`              |
| Aplikacje w tle        | `privacy-backgroundapps`              |
| Kalendarz                 | `privacy-calendar`                    |
| Historia połączeń             | `privacy-callhistory`                 |
| Aparat fotograficzny                   | `privacy-webcam`                      |
| Kontakty                 | `privacy-contacts`                    |
| Opinia & diagnostyki | `privacy-feedback`                    |
| Dokumenty                | `privacy-documents`                   |
| E-mail                    | `privacy-email`                       |
| System plików              | `privacy-broadfilesystemaccess`       |
| Ogólne <sup>2</sup>             | `privacy-general`       |
| Personalizacja & pisma odręcznego <sup>2</sup>             | `privacy-speechtyping`       |
| Lokalizacja                 | `privacy-location`                    |
| Obsługa komunikatów                | `privacy-messaging`                   |
| Mikrofon               | `privacy-microphone`                  |
| Ruch <sup>2</sup>               | `privacy-motion`                  |
| Powiadomienia            | `privacy-notifications`               |
| Inne urządzenia            | `privacy-customdevices`               |
| Obrazy                 | `privacy-pictures`                    |
| Radia                   | `privacy-radios`                      |
| Zrzut ekranu <sup>obramowania 2</sup>             | `privacy-graphicsCaptureWithoutBorder`       |
| Zrzuty ekranu i aplikacje <sup>2</sup>             | `privacy-graphicsCaptureProgrammatic`       |
| Mowa                   | `privacy-speech`                      |
| Zadania                    | `privacy-tasks`                       |
| Ruchy użytkowników           | `privacy-backgroundspatialperception` |
| Filmy wideo                   | `privacy-videos`                      |
| Aktywacja głosowa       | `privacy-voiceactivation`             |

### <a name="network--internet"></a>Sieć i Internet
| Strona Ustawienia | URI                              |
|---------------|----------------------------------|
| Tryb <sup>samolotowy 2</sup> | `network-airplanemode`        |
| Serwer proxy | `network-proxy`        |
| VPN   | `network-vpn`          |
| Wi-Fi  | `network-wifi`<br>`network-wifisettings`<br>`network-status`<br>`wifi-provisioning`    |



### <a name="system"></a>System
| Strona Ustawienia      | URI                                |
|--------------------|------------------------------------|
| Bateria <sup>2</sup>           | `batterysaver`<br>|
| Bateria <sup>2</sup>           | `batterysaver-settings`<br>|
| Kolory             | `colors`<br>`personalization-colors` |
| Hologramy <sup>2</sup>  |  `holograms`  |
| <sup>2.</sup> |  `calibration` |
| Powiadomienia & akcje  | `notifications`          |
| Udostępnione doświadczenia | `crossdevice` 
| Dźwięk <sup>2</sup>           | `sound`<br>|
| Dźwięk > aplikacji i preferencja urządzenia <sup>2</sup>           | `apps-volume`<br>|
| Zarządzanie urządzeniami > dźwięku <sup>2</sup>           | `sound-devices`<br>|
| Storage            | `storagesense`           |
| Storage > konfigurowanie usługi Storage Sense <sup>2</sup>           | `storagepolicies`<br>|

### <a name="time--language"></a>Time & Language
| Strona Ustawienia | URI                                           |
|---------------|-----------------------------------------------|
| Data & <sup>2</sup> | `dateandtime`                  |
| Klawiatura <sup>2</sup> | `keyboard`                  |
| Język <sup>2</sup> | `language`                  |
| Język <sup>2</sup> | `regionlanguage-languageoptions`                  |
| Język      | `regionlanguage`<br>`regionlanguage-adddisplaylanguage`<br>`regionlanguage-setdisplaylanguage` |
| Region (Region)        | `regionformatting`                  |

### <a name="update--security"></a>Aktualizowanie & zabezpieczeń
| Strona Ustawienia                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Opcje zaawansowane                    | `windowsupdate-options`         |
| Resetowanie & odzyskiwania <sup>2</sup>      | `reset`         |
| Niejawny program testów systemu Windows               | `windowsinsider` <br>`windowsinsider-optin`          |
| Windows Update                        | `windowsupdate`<br> `windowsupdate-activehours`  <br> `windowsupdate-history` <br> `windowsupdate-optionalupdates` <br><sup>1</sup>`windowsupdate-options`<br><sup>1</sup>`windowsupdate-restartoptions` |
| Windows Aktualizacja — sprawdzanie, czy są dostępne aktualizacje | `windowsupdate-action`          |


- <sup>1</sup> — W przypadku wersji starszych niż Windows Holographic, wersja 21H1, następujące  dwa interfejsy URI w rzeczywistości nie przejdą do stron Opcje **zaawansowane** ani Opcje. Będą blokować lub wyświetlać tylko główną stronę Windows Aktualizacji.
  -  windowsupdate-options
  -  windowsupdate-restartoptions

- <sup>2</sup> — dostępne w Windows Holographic 21H1 lub wyższej.


Aby uzyskać pełną listę Windows 10 Ustawienia, zapoznaj się z [dokumentacją ustawień uruchamiania.](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)
