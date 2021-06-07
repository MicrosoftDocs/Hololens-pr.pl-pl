---
title: Widoczność ustawień strony
description: Bądź na bieżąco z naszą listą obsługiwanych adresów URI dla elementów PageVisibilityList i Guide on HoloLens mixed reality devices (Lista elementów PageVisibilityList i Przewodnik na urządzeniach z rzeczywistością mieszaną HoloLens).
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
ms.openlocfilehash: b5779ffa1de1700b4fcd17fc17b8ae3a82a45c22
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379733"
---
# <a name="page-settings-visibility"></a><span data-ttu-id="9d182-104">Widoczność ustawień strony</span><span class="sxs-lookup"><span data-stu-id="9d182-104">Page Settings Visibility</span></span>

<span data-ttu-id="9d182-105">Jedną z funkcji, które można zarządzać na urządzeniach HoloLens, jest użycie zasad [Settings/PageVisibilityList w](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) celu ograniczenia stron widocznych w aplikacji Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="9d182-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="9d182-106">PageVisibilityList to zasady, które umożliwiają administratorom IT uniemożliwić widoczność lub dostępność określonych stron w aplikacji Ustawienia systemowe lub na ich użycie dla wszystkich stron z wyjątkiem określonych.</span><span class="sxs-lookup"><span data-stu-id="9d182-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="9d182-107">Ta funkcja jest dostępna tylko w systemie Windows Holographic w wersji [20H2](hololens-release-notes.md#windows-holographic-version-20h2) lub wyższej dla urządzeń HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="9d182-107">This feature is only avalible in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or higher for HoloLens 2 devices.</span></span> <span data-ttu-id="9d182-108">Upewnij się, że urządzenia, dla których zamierzasz używać tej funkcji, zostały zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="9d182-108">Please ensure devices you intend to use this for are updated.</span></span>

<span data-ttu-id="9d182-109">Poniższy przykład ilustruje zasady, które zezwalają na dostęp tylko do stron about i Bluetooth, które mają odpowiednio URI "ms-settings:network-wifi" i "ms-settings:bluetooth":</span><span class="sxs-lookup"><span data-stu-id="9d182-109">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "ms-settings:network-wifi" and "ms-settings:bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="9d182-110">Aby to ustawić za pośrednictwem pakietu aprowizowania:</span><span class="sxs-lookup"><span data-stu-id="9d182-110">To set this via a Provisioning Package:</span></span>

1. <span data-ttu-id="9d182-111">Podczas tworzenia pakietu w projektancie konfiguracji systemu Windows przejdź do opcji **> ustawienia > PageVisibilityList**</span><span class="sxs-lookup"><span data-stu-id="9d182-111">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="9d182-112">Wprowadź ciąg: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="9d182-112">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="9d182-113">Wyeksportuj pakiet aprowizowania.</span><span class="sxs-lookup"><span data-stu-id="9d182-113">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="9d182-114">Zastosuj pakiet do urządzenia.</span><span class="sxs-lookup"><span data-stu-id="9d182-114">Apply the package to your device.</span></span>
<span data-ttu-id="9d182-115">Aby uzyskać szczegółowe informacje na temat tworzenia i stosowania pakietu aprowizowania, odwiedź [tę stronę.](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="9d182-115">For full details on how to create and apply a provisioning package visit [this page](hololens-provisioning.md).</span></span>

<span data-ttu-id="9d182-116">Można to zrobić za pośrednictwem usługi Intune przy użyciu OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="9d182-116">This can be done via Intune using OMA-URI:</span></span>

1. <span data-ttu-id="9d182-117">Utwórz zasady **niestandardowe.**</span><span class="sxs-lookup"><span data-stu-id="9d182-117">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="9d182-118">Podczas ustawiania wartości OMA-URI użyj ciągu: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="9d182-118">When setting the OMA-URI use the string: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="9d182-119">Podczas wybierania danych wybierz **pozycję** Ciąg</span><span class="sxs-lookup"><span data-stu-id="9d182-119">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="9d182-120">Podczas wpisywania wartości użyj: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="9d182-120">When typing the value use: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="9d182-121">Pamiętaj, aby przypisać niestandardową konfigurację urządzenia do grupy, w która ma się znaleźć urządzenie.</span><span class="sxs-lookup"><span data-stu-id="9d182-121">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span>

<span data-ttu-id="9d182-122">Aby uzyskać więcej informacji na temat grup i konfiguracji urządzeń usługi Intune, zobacz Konfiguracja urządzenia [HoloLens MDM.](hololens-mdm-configure.md)</span><span class="sxs-lookup"><span data-stu-id="9d182-122">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>

<span data-ttu-id="9d182-123">Niezależnie od wybranej metody urządzenie powinno teraz otrzymywać zmiany, a użytkownikom zostanie przedstawiona następująca aplikacja Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="9d182-123">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![Zrzut ekranu przedstawiający modyfikację godzin aktywnego działania w aplikacji Ustawienia](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="9d182-125">Aby skonfigurować strony aplikacji Ustawienia do pokazywania lub ukrywania własnych wybranych stron, przyjrzyj się interfejsom URI ustawień dostępnym na urządzeniach HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9d182-125">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <a name="settings-uris"></a><span data-ttu-id="9d182-126">Ustawienia URI</span><span class="sxs-lookup"><span data-stu-id="9d182-126">Settings URIs</span></span>

<span data-ttu-id="9d182-127">Urządzenia HoloLens i Windows 10 mają różne strony w aplikacji Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="9d182-127">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="9d182-128">Na tej stronie znajdziesz tylko ustawienia, które istnieją na urządzeniach HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9d182-128">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <a name="accounts"></a><span data-ttu-id="9d182-129">Konta</span><span class="sxs-lookup"><span data-stu-id="9d182-129">Accounts</span></span>
| <span data-ttu-id="9d182-130">Strona Ustawienia</span><span class="sxs-lookup"><span data-stu-id="9d182-130">Settings page</span></span>           | <span data-ttu-id="9d182-131">URI</span><span class="sxs-lookup"><span data-stu-id="9d182-131">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="9d182-132">Dostęp do zasobów służbowych</span><span class="sxs-lookup"><span data-stu-id="9d182-132">Access work or school</span></span> | `ms-settings:workplace`                         |
| <span data-ttu-id="9d182-133">Rejestracja irysów</span><span class="sxs-lookup"><span data-stu-id="9d182-133">Iris Enrollment</span></span>       | `ms-settings:signinoptions-launchirisenrollment` |
| <span data-ttu-id="9d182-134">Opcje logowania</span><span class="sxs-lookup"><span data-stu-id="9d182-134">Sign In Options</span></span>         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a><span data-ttu-id="9d182-135">Apps</span><span class="sxs-lookup"><span data-stu-id="9d182-135">Apps</span></span>
| <span data-ttu-id="9d182-136">Strona Ustawienia</span><span class="sxs-lookup"><span data-stu-id="9d182-136">Settings page</span></span> | <span data-ttu-id="9d182-137">URI</span><span class="sxs-lookup"><span data-stu-id="9d182-137">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="9d182-138">Funkcje &<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9d182-138">Apps & features<sup>2</sup></span></span>     | `ms-settings:appsfeatures` <br> |
| <span data-ttu-id="9d182-139">Funkcje & aplikacji > opcje zaawansowane <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9d182-139">Apps & features > Advanced Options <sup>2</sup></span></span>     | `ms-settings::appsfeatures-app` <br> |
| <span data-ttu-id="9d182-140">Funkcje & aplikacji > Offline Maps <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9d182-140">Apps & features > Offline Maps <sup>2</sup></span></span>     | `ms-settings:maps-maps` <br> |
| <span data-ttu-id="9d182-141">Aplikacje & funkcje > Mapy offline > Pobieranie map <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9d182-141">Apps & features > Offline Maps > Download maps <sup>2</sup></span></span>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a><span data-ttu-id="9d182-142">Urządzenia</span><span class="sxs-lookup"><span data-stu-id="9d182-142">Devices</span></span>
| <span data-ttu-id="9d182-143">Strona Ustawienia</span><span class="sxs-lookup"><span data-stu-id="9d182-143">Settings page</span></span> | <span data-ttu-id="9d182-144">URI</span><span class="sxs-lookup"><span data-stu-id="9d182-144">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="9d182-145">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="9d182-145">Bluetooth</span></span>     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| <span data-ttu-id="9d182-146">Mysz <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9d182-146">Mouse <sup>2</sup></span></span>      | `ms-settings:mouse` <br>  |
| <span data-ttu-id="9d182-147">USB <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9d182-147">USB <sup>2</sup></span></span>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a><span data-ttu-id="9d182-148">Prywatność</span><span class="sxs-lookup"><span data-stu-id="9d182-148">Privacy</span></span>
| <span data-ttu-id="9d182-149">Strona Ustawienia</span><span class="sxs-lookup"><span data-stu-id="9d182-149">Settings page</span></span>            | <span data-ttu-id="9d182-150">URI</span><span class="sxs-lookup"><span data-stu-id="9d182-150">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="9d182-151">Informacje o koncie</span><span class="sxs-lookup"><span data-stu-id="9d182-151">Account Info</span></span>             | `ms-settings:privacy-accountinfo`              |
| <span data-ttu-id="9d182-152">Diagnostyka aplikacji</span><span class="sxs-lookup"><span data-stu-id="9d182-152">App Diagnostics</span></span>        | `ms-settings:privacy-appdiagnostics`              |
| <span data-ttu-id="9d182-153">Aplikacje w tle</span><span class="sxs-lookup"><span data-stu-id="9d182-153">Background Apps</span></span>        | `ms-settings:privacy-backgroundapps`              |
| <span data-ttu-id="9d182-154">Kalendarz</span><span class="sxs-lookup"><span data-stu-id="9d182-154">Calendar</span></span>                 | `ms-settings:privacy-calendar`                    |
| <span data-ttu-id="9d182-155">Historia połączeń</span><span class="sxs-lookup"><span data-stu-id="9d182-155">Call History</span></span>             | `ms-settings:privacy-callhistory`                 |
| <span data-ttu-id="9d182-156">Aparat fotograficzny</span><span class="sxs-lookup"><span data-stu-id="9d182-156">Camera</span></span>                   | `ms-settings:privacy-webcam`                      |
| <span data-ttu-id="9d182-157">Kontakty</span><span class="sxs-lookup"><span data-stu-id="9d182-157">Contacts</span></span>                 | `ms-settings:privacy-contacts`                    |
| <span data-ttu-id="9d182-158">Opinia & diagnostyki</span><span class="sxs-lookup"><span data-stu-id="9d182-158">Diagnostics & Feedback</span></span> | `ms-settings:privacy-feedback`                    |
| <span data-ttu-id="9d182-159">Dokumenty</span><span class="sxs-lookup"><span data-stu-id="9d182-159">Documents</span></span>                | `ms-settings:privacy-documents`                   |
| <span data-ttu-id="9d182-160">E-mail</span><span class="sxs-lookup"><span data-stu-id="9d182-160">Email</span></span>                    | `ms-settings:privacy-email`                       |
| <span data-ttu-id="9d182-161">System plików</span><span class="sxs-lookup"><span data-stu-id="9d182-161">File system</span></span>              | `ms-settings:privacy-broadfilesystemaccess`       |
| <span data-ttu-id="9d182-162">Ogólne <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9d182-162">General <sup>2</sup></span></span>             | `ms-settings:privacy-general`       |
| <span data-ttu-id="9d182-163">Personalizacja & pisma odręcznego <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9d182-163">Ink & typing personalization <sup>2</sup></span></span>             | `ms-settings:privacy-speechtyping`       |
| <span data-ttu-id="9d182-164">Lokalizacja</span><span class="sxs-lookup"><span data-stu-id="9d182-164">Location</span></span>                 | `ms-settings:privacy-location`                    |
| <span data-ttu-id="9d182-165">Obsługa wiadomości</span><span class="sxs-lookup"><span data-stu-id="9d182-165">Messaging</span></span>                | `ms-settings:privacy-messaging`                   |
| <span data-ttu-id="9d182-166">Mikrofon</span><span class="sxs-lookup"><span data-stu-id="9d182-166">Microphone</span></span>               | `ms-settings:privacy-microphone`                  |
| <span data-ttu-id="9d182-167">Ruch <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9d182-167">Motion <sup>2</sup></span></span>               | `ms-settings:privacy-motion`                  |
| <span data-ttu-id="9d182-168">Powiadomienia</span><span class="sxs-lookup"><span data-stu-id="9d182-168">Notifications</span></span>            | `ms-settings:privacy-notifications`               |
| <span data-ttu-id="9d182-169">Inne urządzenia</span><span class="sxs-lookup"><span data-stu-id="9d182-169">Other devices</span></span>            | `ms-settings:privacy-customdevices`               |
| <span data-ttu-id="9d182-170">Obrazy</span><span class="sxs-lookup"><span data-stu-id="9d182-170">Pictures</span></span>                 | `ms-settings:privacy-pictures`                    |
| <span data-ttu-id="9d182-171">Radia</span><span class="sxs-lookup"><span data-stu-id="9d182-171">Radios</span></span>                   | `ms-settings:privacy-radios`                      |
| <span data-ttu-id="9d182-172">Zrzut ekranu <sup>obramowania 2</sup></span><span class="sxs-lookup"><span data-stu-id="9d182-172">Screenshot borders <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| <span data-ttu-id="9d182-173">Zrzuty ekranu i aplikacje <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9d182-173">Screenshots and apps <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| <span data-ttu-id="9d182-174">Mowa</span><span class="sxs-lookup"><span data-stu-id="9d182-174">Speech</span></span>                   | `ms-settings:privacy-speech`                      |
| <span data-ttu-id="9d182-175">Zadania</span><span class="sxs-lookup"><span data-stu-id="9d182-175">Tasks</span></span>                    | `ms-settings:privacy-tasks`                       |
| <span data-ttu-id="9d182-176">Ruchy użytkowników</span><span class="sxs-lookup"><span data-stu-id="9d182-176">User movements</span></span>           | `ms-settings:privacy-backgroundspatialperception` |
| <span data-ttu-id="9d182-177">Filmy wideo</span><span class="sxs-lookup"><span data-stu-id="9d182-177">Videos</span></span>                   | `ms-settings:privacy-videos`                      |
| <span data-ttu-id="9d182-178">Aktywacja głosowa</span><span class="sxs-lookup"><span data-stu-id="9d182-178">Voice Activation</span></span>       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a><span data-ttu-id="9d182-179">Sieć i Internet</span><span class="sxs-lookup"><span data-stu-id="9d182-179">Network & Internet</span></span>
| <span data-ttu-id="9d182-180">Strona Ustawienia</span><span class="sxs-lookup"><span data-stu-id="9d182-180">Settings page</span></span> | <span data-ttu-id="9d182-181">URI</span><span class="sxs-lookup"><span data-stu-id="9d182-181">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="9d182-182">Tryb <sup>samolotowy 2</sup></span><span class="sxs-lookup"><span data-stu-id="9d182-182">Airplane Mode <sup>2</sup></span></span> | `ms-settings:network-airplanemode`        |
| <span data-ttu-id="9d182-183">Serwer proxy</span><span class="sxs-lookup"><span data-stu-id="9d182-183">Proxy</span></span> | `ms-settings:network-proxy`        |
| <span data-ttu-id="9d182-184">VPN</span><span class="sxs-lookup"><span data-stu-id="9d182-184">VPN</span></span>   | `ms-settings:network-vpn`          |
| <span data-ttu-id="9d182-185">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="9d182-185">Wi-Fi</span></span>  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a><span data-ttu-id="9d182-186">System</span><span class="sxs-lookup"><span data-stu-id="9d182-186">System</span></span>
| <span data-ttu-id="9d182-187">Strona Ustawienia</span><span class="sxs-lookup"><span data-stu-id="9d182-187">Settings page</span></span>      | <span data-ttu-id="9d182-188">URI</span><span class="sxs-lookup"><span data-stu-id="9d182-188">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="9d182-189">Bateria <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9d182-189">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver`<br>|
| <span data-ttu-id="9d182-190">Bateria <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9d182-190">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver-settings`<br>|
| <span data-ttu-id="9d182-191">Kolory</span><span class="sxs-lookup"><span data-stu-id="9d182-191">Colors</span></span>             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| <span data-ttu-id="9d182-192">Hologramy <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9d182-192">Holograms <sup>2</sup></span></span>  |  `ms-settings:holograms`  |
| <span data-ttu-id="9d182-193"><sup>Przebłyski 2</sup></span><span class="sxs-lookup"><span data-stu-id="9d182-193">Calibration <sup>2</sup></span></span> |  `ms-settings:calibration` |
| <span data-ttu-id="9d182-194">Powiadomienia & akcje</span><span class="sxs-lookup"><span data-stu-id="9d182-194">Notifications & actions</span></span>  | `ms-settings:notifications`          |
| <span data-ttu-id="9d182-195">Udostępnione doświadczenia</span><span class="sxs-lookup"><span data-stu-id="9d182-195">Shared Experiences</span></span> | `ms-settings:crossdevice` 
| <span data-ttu-id="9d182-196">Dźwięk <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9d182-196">Sound <sup>2</sup></span></span>           | `ms-settings:sound`<br>|
| <span data-ttu-id="9d182-197">Dźwięk > aplikacji i preferencja urządzenia <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9d182-197">Sound > App volume and device preference <sup>2</sup></span></span>           | `ms-settings:apps-volume`<br>|
| <span data-ttu-id="9d182-198">Zarządzanie > dźwięku <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9d182-198">Sound > Manage sound devices <sup>2</sup></span></span>           | `ms-settings:sound-devices`<br>|
| <span data-ttu-id="9d182-199">Storage</span><span class="sxs-lookup"><span data-stu-id="9d182-199">Storage</span></span>            | `ms-settings:storagesense`           |
| <span data-ttu-id="9d182-200">Konfiguracja > magazynu Czujnik pamięci <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9d182-200">Storage > Configue Storage Sense <sup>2</sup></span></span>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a><span data-ttu-id="9d182-201">Język & czasu</span><span class="sxs-lookup"><span data-stu-id="9d182-201">Time & Language</span></span>
| <span data-ttu-id="9d182-202">Strona Ustawienia</span><span class="sxs-lookup"><span data-stu-id="9d182-202">Settings page</span></span> | <span data-ttu-id="9d182-203">URI</span><span class="sxs-lookup"><span data-stu-id="9d182-203">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="9d182-204">Data & <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9d182-204">Date & time <sup>2</sup></span></span> | `ms-settings:dateandtime`                  |
| <span data-ttu-id="9d182-205">Klawiatura <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9d182-205">Keyboard <sup>2</sup></span></span> | `ms-settings:keyboard`                  |
| <span data-ttu-id="9d182-206">Język <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9d182-206">Language <sup>2</sup></span></span> | `ms-settings:language`                  |
| <span data-ttu-id="9d182-207">Język <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9d182-207">Language <sup>2</sup></span></span> | `ms-settings:regionlanguage-languageoptions`                  |
| <span data-ttu-id="9d182-208">Język</span><span class="sxs-lookup"><span data-stu-id="9d182-208">Language</span></span>      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| <span data-ttu-id="9d182-209">Region (Region)</span><span class="sxs-lookup"><span data-stu-id="9d182-209">Region</span></span>        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a><span data-ttu-id="9d182-210">Aktualizowanie & zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="9d182-210">Update & Security</span></span>
| <span data-ttu-id="9d182-211">Strona Ustawienia</span><span class="sxs-lookup"><span data-stu-id="9d182-211">Settings page</span></span>                         | <span data-ttu-id="9d182-212">URI</span><span class="sxs-lookup"><span data-stu-id="9d182-212">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="9d182-213">Opcje zaawansowane</span><span class="sxs-lookup"><span data-stu-id="9d182-213">Advanced Options</span></span>                    | `ms-settings:windowsupdate-options`         |
| <span data-ttu-id="9d182-214">Resetowanie & odzyskiwania <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9d182-214">Reset & Recovery <sup>2</sup></span></span>      | `ms-settings:reset`         |
| <span data-ttu-id="9d182-215">Niejawny program testów systemu Windows</span><span class="sxs-lookup"><span data-stu-id="9d182-215">Windows Insider Program</span></span>               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| <span data-ttu-id="9d182-216">Windows Update</span><span class="sxs-lookup"><span data-stu-id="9d182-216">Windows Update</span></span>                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><span data-ttu-id="9d182-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span><span class="sxs-lookup"><span data-stu-id="9d182-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span></span><br><span data-ttu-id="9d182-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span><span class="sxs-lookup"><span data-stu-id="9d182-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span></span> |
| <span data-ttu-id="9d182-219">Windows Update — sprawdzanie aktualizacji</span><span class="sxs-lookup"><span data-stu-id="9d182-219">Windows Update - Checks for updates</span></span> | `ms-settings:windowsupdate-action`          |


>  <span data-ttu-id="9d182-220"><sup>1</sup> W przypadku wersji wcześniejszych niż Windows Holographic, wersja 21H1, następujące  dwa interfejsy URI w rzeczywistości nie przejdą do stron Opcje zaawansowane **ani** Opcje. Będą blokować lub wyświetlać tylko główną Windows Update internetową.</span><span class="sxs-lookup"><span data-stu-id="9d182-220"><sup>1</sup> For versions prior to Windows Holographic, version 21H1, the following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
> - <span data-ttu-id="9d182-221">ms-settings:windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="9d182-221">ms-settings:windowsupdate-options</span></span>
> - <span data-ttu-id="9d182-222">ms-settings:windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="9d182-222">ms-settings:windowsupdate-restartoptions</span></span>
 
> <span data-ttu-id="9d182-223"><sup>2 —</sup> dostępne w systemie Windows Holographic 21H1 lub wyższym.</span><span class="sxs-lookup"><span data-stu-id="9d182-223"><sup>2</sup> - Available in Windows Holographic 21H1 or higher.</span></span>


<span data-ttu-id="9d182-224">Aby uzyskać pełną listę Windows 10 URI ustawień uruchamiania, zapoznaj się z [dokumentacją ustawień uruchamiania.](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)</span><span class="sxs-lookup"><span data-stu-id="9d182-224">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
