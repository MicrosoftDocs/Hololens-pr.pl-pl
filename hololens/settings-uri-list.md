---
title: Widoczność Ustawienia stron
description: Bądź na bieżąco z naszą listą obsługiwanych interfejsów URI dla elementów PageVisibilityList i Przewodnika na HoloLens rzeczywistości mieszanej.
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
ms.openlocfilehash: 454d79e8b719feb73d5a39280794dcd76f134952
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639237"
---
# <a name="page-settings-visibility"></a><span data-ttu-id="ada4c-104">Widoczność Ustawienia stron</span><span class="sxs-lookup"><span data-stu-id="ada4c-104">Page Settings Visibility</span></span>

<span data-ttu-id="ada4c-105">Jedną z funkcji, które można zarządzać HoloLens, jest użycie zasad [Ustawienia/PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) w celu ograniczenia stron widocznych w Ustawienia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ada4c-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="ada4c-106">PageVisibilityList to zasady, które umożliwiają administratorom IT uniemożliwić widoczność lub dostępność określonych stron w aplikacji System Ustawienia lub aby to zrobić dla wszystkich stron z wyjątkiem określonych.</span><span class="sxs-lookup"><span data-stu-id="ada4c-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="ada4c-107">Ta funkcja jest dostępna tylko na [platformie Windows Holographic w wersji 20H2](hololens-release-notes.md#windows-holographic-version-20h2) lub wyższej dla urządzeń HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="ada4c-107">This feature is only avalible in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or higher for HoloLens 2 devices.</span></span> <span data-ttu-id="ada4c-108">Upewnij się, że urządzenia, dla których zamierzasz używać tej funkcji, zostały zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="ada4c-108">Please ensure devices you intend to use this for are updated.</span></span>


## <a name="examples"></a><span data-ttu-id="ada4c-109">Przykłady</span><span class="sxs-lookup"><span data-stu-id="ada4c-109">Examples</span></span>
<span data-ttu-id="ada4c-110">Strony są identyfikowane za pomocą skróconej wersji opublikowanych URI, czyli identyfikatora URI pomniejszonej o prefiks "ms-settings:".</span><span class="sxs-lookup"><span data-stu-id="ada4c-110">Pages are identified by a shortened version of the published URIs, which is the URI minus the "ms-settings:" prefix.</span></span>

<span data-ttu-id="ada4c-111">Poniższy przykład ilustruje zasady, które zezwalają na dostęp tylko do stron about i Bluetooth, które mają odpowiednio URI "sieć-sieć-Wi-Fi" i "bluetooth":</span><span class="sxs-lookup"><span data-stu-id="ada4c-111">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "network-wifi" and "bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="ada4c-112">Poniższy przykład ilustruje zasady, które ukrywałyby stronę Resetowanie systemu operacyjnego:</span><span class="sxs-lookup"><span data-stu-id="ada4c-112">The following example illustrates a policy that would hide the OS Reset page:</span></span>
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a><span data-ttu-id="ada4c-113">Wdrażanie tych zasad za pośrednictwem usługi Intune</span><span class="sxs-lookup"><span data-stu-id="ada4c-113">Deploying this policy via Intune</span></span>

<span data-ttu-id="ada4c-114">Są to wartości konfiguracji, które zostaną dostarczone do usługi Intune:</span><span class="sxs-lookup"><span data-stu-id="ada4c-114">These are the configuration values that will be supplied to Intune:</span></span>

- <span data-ttu-id="ada4c-115">**Nazwa:** Preferowana przez administratora nazwa wyświetlana profilu.</span><span class="sxs-lookup"><span data-stu-id="ada4c-115">**Name:** An admin preferred display name for the profile.</span></span>
- <span data-ttu-id="ada4c-116">**OMA-URI:** W pełni kwalifikowany URI strony ustawienia wraz z jej [zakresem](/windows/client-management/mdm/policy-configuration-service-provider).</span><span class="sxs-lookup"><span data-stu-id="ada4c-116">**OMA-URI:** The fully qualified URI of the setting page including its [scope](/windows/client-management/mdm/policy-configuration-service-provider).</span></span> <span data-ttu-id="ada4c-117">W tych przykładach na tej stronie jest on korzystający z `./Device` zakresu .</span><span class="sxs-lookup"><span data-stu-id="ada4c-117">This examples on this page are using the `./Device` scope.</span></span>
- <span data-ttu-id="ada4c-118">**Wartość:** Wartość ciągu wskazująca, czy ukryć lub pokazać *tylko* określone strony.</span><span class="sxs-lookup"><span data-stu-id="ada4c-118">**Value:** A string value that indicates whether to hide or show *only* the specified pages.</span></span> <span data-ttu-id="ada4c-119">Możliwe wartości to `hide:<pagename>` i `showonly:<pagename>` .</span><span class="sxs-lookup"><span data-stu-id="ada4c-119">Possible values are `hide:<pagename>` and `showonly:<pagename>`.</span></span> 
 
<span data-ttu-id="ada4c-120">Można określić wiele stron, oddzielając je średnikami, a listę typowych stron można znaleźć poniżej.</span><span class="sxs-lookup"><span data-stu-id="ada4c-120">Multiple pages can be specified by separating them with a semicolon, and a listing of common pages can be found below.</span></span>

1. <span data-ttu-id="ada4c-121">Utwórz zasady **niestandardowe.**</span><span class="sxs-lookup"><span data-stu-id="ada4c-121">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="ada4c-122">Podczas ustawiania wartości **OMA-URI** wprowadź w pełni zakresowy adres URI.</span><span class="sxs-lookup"><span data-stu-id="ada4c-122">When setting the **OMA-URI** enter the fully scoped URI.</span></span> <span data-ttu-id="ada4c-123">Na przykład: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="ada4c-123">For example: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="ada4c-124">Podczas wybierania danych wybierz **pozycję** Ciąg</span><span class="sxs-lookup"><span data-stu-id="ada4c-124">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="ada4c-125">Podczas określania **wartości** skorzystaj z powyższych wskazówek.</span><span class="sxs-lookup"><span data-stu-id="ada4c-125">When specifying **Value** use the guidance above.</span></span> <span data-ttu-id="ada4c-126">Na przykład: **`showonly:network-wifi;network-proxy;bluetooth`** lub **`hide:reset`**</span><span class="sxs-lookup"><span data-stu-id="ada4c-126">For example: **`showonly:network-wifi;network-proxy;bluetooth`** or **`hide:reset`**</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="ada4c-127">Pamiętaj, aby przypisać niestandardową konfigurację urządzenia do grupy, w która ma być urządzenie.</span><span class="sxs-lookup"><span data-stu-id="ada4c-127">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span> <span data-ttu-id="ada4c-128">Jeśli ten krok nie zostanie wykonany, zasady zostaną wypchniętą, ale nie zostaną zastosowane.</span><span class="sxs-lookup"><span data-stu-id="ada4c-128">If this step is not performed, the policy will be pushed but won't be applied.</span></span>

<span data-ttu-id="ada4c-129">Zobacz [HoloLens mdm,](hololens-mdm-configure.md) aby uzyskać więcej informacji na temat grup i konfiguracji urządzeń usługi Intune.</span><span class="sxs-lookup"><span data-stu-id="ada4c-129">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>


## <a name="deploying-this-policy-via-a-provisioning-package"></a><span data-ttu-id="ada4c-130">Wdrażanie tych zasad za pośrednictwem pakietu aprowizowania</span><span class="sxs-lookup"><span data-stu-id="ada4c-130">Deploying this policy via a Provisioning Package</span></span>

<span data-ttu-id="ada4c-131">Są to wartości konfiguracji, które zostaną określone w Windows Configuration Designer:</span><span class="sxs-lookup"><span data-stu-id="ada4c-131">These are the configuration values that will be specified in Windows Configuration Designer:</span></span>

<span data-ttu-id="ada4c-132">**Wartość:** Wartość ciągu wskazująca, czy ukryć lub pokazać *tylko* określone strony.</span><span class="sxs-lookup"><span data-stu-id="ada4c-132">**Value:** A string value that indicates whether to hide or show *only* the specified pages.</span></span> <span data-ttu-id="ada4c-133">Możliwe wartości to `hide:<pagename>` i `showonly:<pagename>` .</span><span class="sxs-lookup"><span data-stu-id="ada4c-133">Possible values are `hide:<pagename>` and `showonly:<pagename>`.</span></span> <span data-ttu-id="ada4c-134">Można określić wiele stron, oddzielając je średnikami, a listę typowych stron można znaleźć poniżej.</span><span class="sxs-lookup"><span data-stu-id="ada4c-134">Multiple pages can be specified by separating them with a semicolon, and a listing of common pages can be found below.</span></span>


1. <span data-ttu-id="ada4c-135">Podczas tworzenia pakietu w programie Windows Configuration Designer przejdź do opcji **Zasady > Ustawienia > PageVisibilityList**</span><span class="sxs-lookup"><span data-stu-id="ada4c-135">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="ada4c-136">Wprowadź ciąg: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="ada4c-136">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="ada4c-137">Wyeksportuj pakiet aprowizowania.</span><span class="sxs-lookup"><span data-stu-id="ada4c-137">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="ada4c-138">Zastosuj pakiet do urządzenia.</span><span class="sxs-lookup"><span data-stu-id="ada4c-138">Apply the package to your device.</span></span>
<span data-ttu-id="ada4c-139">Aby uzyskać szczegółowe informacje na temat tworzenia i stosowania pakietu aprowizowania, odwiedź [HoloLens aprowizowania.](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="ada4c-139">For full details on how to create and apply a provisioning package visit [the HoloLens provisioning page](hololens-provisioning.md).</span></span>


<span data-ttu-id="ada4c-140">Niezależnie od wybranej metody urządzenie powinno teraz otrzymywać zmiany, a użytkownikom zostaną przedstawione następujące Ustawienia App.</span><span class="sxs-lookup"><span data-stu-id="ada4c-140">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![Zrzut ekranu przedstawiający modyfikację godzin aktywnego Ustawienia aplikacji](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="ada4c-142">Aby skonfigurować Ustawienia aplikacji do pokazywania lub ukrywania własnych wybranych stron, przyjrzyj się dostępnym w Ustawienia URI HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ada4c-142">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <a name="settings-uris"></a><span data-ttu-id="ada4c-143">Ustawienia Identyfikatory uri</span><span class="sxs-lookup"><span data-stu-id="ada4c-143">Settings URIs</span></span>

<span data-ttu-id="ada4c-144">HoloLens i Windows 10 mają różne opcje wyboru stron w Ustawienia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ada4c-144">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="ada4c-145">Na tej stronie znajdziesz tylko ustawienia, które istnieją w HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ada4c-145">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <a name="accounts"></a><span data-ttu-id="ada4c-146">Konta</span><span class="sxs-lookup"><span data-stu-id="ada4c-146">Accounts</span></span>
| <span data-ttu-id="ada4c-147">Strona Ustawienia</span><span class="sxs-lookup"><span data-stu-id="ada4c-147">Settings page</span></span>           | <span data-ttu-id="ada4c-148">URI</span><span class="sxs-lookup"><span data-stu-id="ada4c-148">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="ada4c-149">Dostęp do zasobów służbowych</span><span class="sxs-lookup"><span data-stu-id="ada4c-149">Access work or school</span></span> | `workplace`                         |
| <span data-ttu-id="ada4c-150">Rejestracja irysów</span><span class="sxs-lookup"><span data-stu-id="ada4c-150">Iris Enrollment</span></span>       | `signinoptions-launchirisenrollment` |
| <span data-ttu-id="ada4c-151">Opcje logowania</span><span class="sxs-lookup"><span data-stu-id="ada4c-151">Sign In Options</span></span>         | ` signinoptions `                   |

### <a name="apps"></a><span data-ttu-id="ada4c-152">Apps</span><span class="sxs-lookup"><span data-stu-id="ada4c-152">Apps</span></span>
| <span data-ttu-id="ada4c-153">Strona Ustawienia</span><span class="sxs-lookup"><span data-stu-id="ada4c-153">Settings page</span></span> | <span data-ttu-id="ada4c-154">URI</span><span class="sxs-lookup"><span data-stu-id="ada4c-154">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="ada4c-155">Funkcje & <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ada4c-155">Apps & features <sup>2</sup></span></span>     | `appsfeatures` <br> |
| <span data-ttu-id="ada4c-156">Funkcje & aplikacji > opcje zaawansowane <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ada4c-156">Apps & features > Advanced Options <sup>2</sup></span></span>     | `appsfeatures-app` <br> |
| <span data-ttu-id="ada4c-157">Funkcje & aplikacji > offline Mapy <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ada4c-157">Apps & features > Offline Maps <sup>2</sup></span></span>     | `maps-maps` <br> |
| <span data-ttu-id="ada4c-158">Aplikacje & funkcje > offline Mapy > Pobierz mapy <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ada4c-158">Apps & features > Offline Maps > Download maps <sup>2</sup></span></span>     | `maps-downloadmaps` <br> |

### <a name="devices"></a><span data-ttu-id="ada4c-159">Urządzenia</span><span class="sxs-lookup"><span data-stu-id="ada4c-159">Devices</span></span>
| <span data-ttu-id="ada4c-160">Strona Ustawienia</span><span class="sxs-lookup"><span data-stu-id="ada4c-160">Settings page</span></span> | <span data-ttu-id="ada4c-161">URI</span><span class="sxs-lookup"><span data-stu-id="ada4c-161">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="ada4c-162">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="ada4c-162">Bluetooth</span></span>     | `bluetooth` <br> `connecteddevices` |
| <span data-ttu-id="ada4c-163">Mysz <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ada4c-163">Mouse <sup>2</sup></span></span>      | `mouse` <br>  |
| <span data-ttu-id="ada4c-164">USB <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ada4c-164">USB <sup>2</sup></span></span>      | `usb` <br>  |

### <a name="privacy"></a><span data-ttu-id="ada4c-165">Prywatność</span><span class="sxs-lookup"><span data-stu-id="ada4c-165">Privacy</span></span>
| <span data-ttu-id="ada4c-166">Strona Ustawienia</span><span class="sxs-lookup"><span data-stu-id="ada4c-166">Settings page</span></span>            | <span data-ttu-id="ada4c-167">URI</span><span class="sxs-lookup"><span data-stu-id="ada4c-167">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="ada4c-168">Informacje o koncie</span><span class="sxs-lookup"><span data-stu-id="ada4c-168">Account Info</span></span>             | `privacy-accountinfo`              |
| <span data-ttu-id="ada4c-169">Diagnostyka aplikacji</span><span class="sxs-lookup"><span data-stu-id="ada4c-169">App Diagnostics</span></span>        | `privacy-appdiagnostics`              |
| <span data-ttu-id="ada4c-170">Aplikacje w tle</span><span class="sxs-lookup"><span data-stu-id="ada4c-170">Background Apps</span></span>        | `privacy-backgroundapps`              |
| <span data-ttu-id="ada4c-171">Kalendarz</span><span class="sxs-lookup"><span data-stu-id="ada4c-171">Calendar</span></span>                 | `privacy-calendar`                    |
| <span data-ttu-id="ada4c-172">Historia połączeń</span><span class="sxs-lookup"><span data-stu-id="ada4c-172">Call History</span></span>             | `privacy-callhistory`                 |
| <span data-ttu-id="ada4c-173">Aparat fotograficzny</span><span class="sxs-lookup"><span data-stu-id="ada4c-173">Camera</span></span>                   | `privacy-webcam`                      |
| <span data-ttu-id="ada4c-174">Kontakty</span><span class="sxs-lookup"><span data-stu-id="ada4c-174">Contacts</span></span>                 | `privacy-contacts`                    |
| <span data-ttu-id="ada4c-175">Opinia & diagnostyki</span><span class="sxs-lookup"><span data-stu-id="ada4c-175">Diagnostics & Feedback</span></span> | `privacy-feedback`                    |
| <span data-ttu-id="ada4c-176">Dokumenty</span><span class="sxs-lookup"><span data-stu-id="ada4c-176">Documents</span></span>                | `privacy-documents`                   |
| <span data-ttu-id="ada4c-177">E-mail</span><span class="sxs-lookup"><span data-stu-id="ada4c-177">Email</span></span>                    | `privacy-email`                       |
| <span data-ttu-id="ada4c-178">System plików</span><span class="sxs-lookup"><span data-stu-id="ada4c-178">File system</span></span>              | `privacy-broadfilesystemaccess`       |
| <span data-ttu-id="ada4c-179">Ogólne <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ada4c-179">General <sup>2</sup></span></span>             | `privacy-general`       |
| <span data-ttu-id="ada4c-180">Personalizacja & pisma odręcznego <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ada4c-180">Ink & typing personalization <sup>2</sup></span></span>             | `privacy-speechtyping`       |
| <span data-ttu-id="ada4c-181">Lokalizacja</span><span class="sxs-lookup"><span data-stu-id="ada4c-181">Location</span></span>                 | `privacy-location`                    |
| <span data-ttu-id="ada4c-182">Obsługa wiadomości</span><span class="sxs-lookup"><span data-stu-id="ada4c-182">Messaging</span></span>                | `privacy-messaging`                   |
| <span data-ttu-id="ada4c-183">Mikrofon</span><span class="sxs-lookup"><span data-stu-id="ada4c-183">Microphone</span></span>               | `privacy-microphone`                  |
| <span data-ttu-id="ada4c-184">Ruch <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ada4c-184">Motion <sup>2</sup></span></span>               | `privacy-motion`                  |
| <span data-ttu-id="ada4c-185">Powiadomienia</span><span class="sxs-lookup"><span data-stu-id="ada4c-185">Notifications</span></span>            | `privacy-notifications`               |
| <span data-ttu-id="ada4c-186">Inne urządzenia</span><span class="sxs-lookup"><span data-stu-id="ada4c-186">Other devices</span></span>            | `privacy-customdevices`               |
| <span data-ttu-id="ada4c-187">Obrazy</span><span class="sxs-lookup"><span data-stu-id="ada4c-187">Pictures</span></span>                 | `privacy-pictures`                    |
| <span data-ttu-id="ada4c-188">Radia</span><span class="sxs-lookup"><span data-stu-id="ada4c-188">Radios</span></span>                   | `privacy-radios`                      |
| <span data-ttu-id="ada4c-189">Zrzut ekranu z <sup>obramowaniami 2</sup></span><span class="sxs-lookup"><span data-stu-id="ada4c-189">Screenshot borders <sup>2</sup></span></span>             | `privacy-graphicsCaptureWithoutBorder`       |
| <span data-ttu-id="ada4c-190">Zrzuty ekranu i aplikacje <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ada4c-190">Screenshots and apps <sup>2</sup></span></span>             | `privacy-graphicsCaptureProgrammatic`       |
| <span data-ttu-id="ada4c-191">Mowa</span><span class="sxs-lookup"><span data-stu-id="ada4c-191">Speech</span></span>                   | `privacy-speech`                      |
| <span data-ttu-id="ada4c-192">Zadania</span><span class="sxs-lookup"><span data-stu-id="ada4c-192">Tasks</span></span>                    | `privacy-tasks`                       |
| <span data-ttu-id="ada4c-193">Ruchy użytkowników</span><span class="sxs-lookup"><span data-stu-id="ada4c-193">User movements</span></span>           | `privacy-backgroundspatialperception` |
| <span data-ttu-id="ada4c-194">Filmy wideo</span><span class="sxs-lookup"><span data-stu-id="ada4c-194">Videos</span></span>                   | `privacy-videos`                      |
| <span data-ttu-id="ada4c-195">Aktywacja głosowa</span><span class="sxs-lookup"><span data-stu-id="ada4c-195">Voice Activation</span></span>       | `privacy-voiceactivation`             |

### <a name="network--internet"></a><span data-ttu-id="ada4c-196">Sieć i Internet</span><span class="sxs-lookup"><span data-stu-id="ada4c-196">Network & Internet</span></span>
| <span data-ttu-id="ada4c-197">Strona Ustawienia</span><span class="sxs-lookup"><span data-stu-id="ada4c-197">Settings page</span></span> | <span data-ttu-id="ada4c-198">URI</span><span class="sxs-lookup"><span data-stu-id="ada4c-198">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="ada4c-199">Tryb <sup>samolotowy 2</sup></span><span class="sxs-lookup"><span data-stu-id="ada4c-199">Airplane Mode <sup>2</sup></span></span> | `network-airplanemode`        |
| <span data-ttu-id="ada4c-200">Serwer proxy</span><span class="sxs-lookup"><span data-stu-id="ada4c-200">Proxy</span></span> | `network-proxy`        |
| <span data-ttu-id="ada4c-201">VPN</span><span class="sxs-lookup"><span data-stu-id="ada4c-201">VPN</span></span>   | `network-vpn`          |
| <span data-ttu-id="ada4c-202">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="ada4c-202">Wi-Fi</span></span>  | `network-wifi`<br>`network-wifisettings`<br>`network-status`<br>`wifi-provisioning`    |



### <a name="system"></a><span data-ttu-id="ada4c-203">System</span><span class="sxs-lookup"><span data-stu-id="ada4c-203">System</span></span>
| <span data-ttu-id="ada4c-204">Strona Ustawienia</span><span class="sxs-lookup"><span data-stu-id="ada4c-204">Settings page</span></span>      | <span data-ttu-id="ada4c-205">URI</span><span class="sxs-lookup"><span data-stu-id="ada4c-205">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="ada4c-206">Bateria <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ada4c-206">Battery <sup>2</sup></span></span>           | `batterysaver`<br>|
| <span data-ttu-id="ada4c-207">Bateria <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ada4c-207">Battery <sup>2</sup></span></span>           | `batterysaver-settings`<br>|
| <span data-ttu-id="ada4c-208">Kolory</span><span class="sxs-lookup"><span data-stu-id="ada4c-208">Colors</span></span>             | `colors`<br>`personalization-colors` |
| <span data-ttu-id="ada4c-209">Hologramy <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ada4c-209">Holograms <sup>2</sup></span></span>  |  `holograms`  |
| <span data-ttu-id="ada4c-210"><sup>Przebłyski 2</sup></span><span class="sxs-lookup"><span data-stu-id="ada4c-210">Calibration <sup>2</sup></span></span> |  `calibration` |
| <span data-ttu-id="ada4c-211">Powiadomienia & akcje</span><span class="sxs-lookup"><span data-stu-id="ada4c-211">Notifications & actions</span></span>  | `notifications`          |
| <span data-ttu-id="ada4c-212">Udostępnione doświadczenia</span><span class="sxs-lookup"><span data-stu-id="ada4c-212">Shared Experiences</span></span> | `crossdevice` 
| <span data-ttu-id="ada4c-213">Dźwięk <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ada4c-213">Sound <sup>2</sup></span></span>           | `sound`<br>|
| <span data-ttu-id="ada4c-214">Dźwięk > aplikacji i preferencja urządzenia <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ada4c-214">Sound > App volume and device preference <sup>2</sup></span></span>           | `apps-volume`<br>|
| <span data-ttu-id="ada4c-215">Zarządzanie > dźwięku <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ada4c-215">Sound > Manage sound devices <sup>2</sup></span></span>           | `sound-devices`<br>|
| <span data-ttu-id="ada4c-216">Storage</span><span class="sxs-lookup"><span data-stu-id="ada4c-216">Storage</span></span>            | `storagesense`           |
| <span data-ttu-id="ada4c-217">Storage > Konfigurowanie usługi Storage Sense <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ada4c-217">Storage > Configure Storage Sense <sup>2</sup></span></span>           | `storagepolicies`<br>|

### <a name="time--language"></a><span data-ttu-id="ada4c-218">Język & czasu</span><span class="sxs-lookup"><span data-stu-id="ada4c-218">Time & Language</span></span>
| <span data-ttu-id="ada4c-219">Strona Ustawienia</span><span class="sxs-lookup"><span data-stu-id="ada4c-219">Settings page</span></span> | <span data-ttu-id="ada4c-220">URI</span><span class="sxs-lookup"><span data-stu-id="ada4c-220">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="ada4c-221">Data & <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ada4c-221">Date & time <sup>2</sup></span></span> | `dateandtime`                  |
| <span data-ttu-id="ada4c-222">Klawiatura <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ada4c-222">Keyboard <sup>2</sup></span></span> | `keyboard`                  |
| <span data-ttu-id="ada4c-223">Język <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ada4c-223">Language <sup>2</sup></span></span> | `language`                  |
| <span data-ttu-id="ada4c-224">Język <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ada4c-224">Language <sup>2</sup></span></span> | `regionlanguage-languageoptions`                  |
| <span data-ttu-id="ada4c-225">Język</span><span class="sxs-lookup"><span data-stu-id="ada4c-225">Language</span></span>      | `regionlanguage`<br>`regionlanguage-adddisplaylanguage`<br>`regionlanguage-setdisplaylanguage` |
| <span data-ttu-id="ada4c-226">Region (Region)</span><span class="sxs-lookup"><span data-stu-id="ada4c-226">Region</span></span>        | `regionformatting`                  |

### <a name="update--security"></a><span data-ttu-id="ada4c-227">Aktualizowanie & zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="ada4c-227">Update & Security</span></span>
| <span data-ttu-id="ada4c-228">Strona Ustawienia</span><span class="sxs-lookup"><span data-stu-id="ada4c-228">Settings page</span></span>                         | <span data-ttu-id="ada4c-229">URI</span><span class="sxs-lookup"><span data-stu-id="ada4c-229">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="ada4c-230">Opcje zaawansowane</span><span class="sxs-lookup"><span data-stu-id="ada4c-230">Advanced Options</span></span>                    | `windowsupdate-options`         |
| <span data-ttu-id="ada4c-231">Resetowanie & Recovery <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ada4c-231">Reset & Recovery <sup>2</sup></span></span>      | `reset`         |
| <span data-ttu-id="ada4c-232">Niejawny program testów systemu Windows</span><span class="sxs-lookup"><span data-stu-id="ada4c-232">Windows Insider Program</span></span>               | `windowsinsider` <br>`windowsinsider-optin`          |
| <span data-ttu-id="ada4c-233">Windows Update</span><span class="sxs-lookup"><span data-stu-id="ada4c-233">Windows Update</span></span>                        | `windowsupdate`<br> `windowsupdate-activehours`  <br> `windowsupdate-history` <br> `windowsupdate-optionalupdates` <br><span data-ttu-id="ada4c-234"><sup>1</sup>`windowsupdate-options`</span><span class="sxs-lookup"><span data-stu-id="ada4c-234"><sup>1</sup>`windowsupdate-options`</span></span><br><span data-ttu-id="ada4c-235"><sup>1</sup>`windowsupdate-restartoptions`</span><span class="sxs-lookup"><span data-stu-id="ada4c-235"><sup>1</sup>`windowsupdate-restartoptions`</span></span> |
| <span data-ttu-id="ada4c-236">Windows Aktualizacja — sprawdzanie aktualizacji</span><span class="sxs-lookup"><span data-stu-id="ada4c-236">Windows Update - Checks for updates</span></span> | `windowsupdate-action`          |


- <span data-ttu-id="ada4c-237"><sup>1</sup> — w przypadku wersji wcześniejszych niż Windows Holographic, wersja 21H1, następujące  dwa interfejsy URI w rzeczywistości nie przejdą do stron Opcje zaawansowane **ani** Opcje. Będą blokować lub wyświetlać tylko główną stronę Windows Aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="ada4c-237"><sup>1</sup> - For versions prior to Windows Holographic, version 21H1, the following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
  -  <span data-ttu-id="ada4c-238">windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="ada4c-238">windowsupdate-options</span></span>
  -  <span data-ttu-id="ada4c-239">windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="ada4c-239">windowsupdate-restartoptions</span></span>

- <span data-ttu-id="ada4c-240"><sup>2</sup> — dostępne w Windows Holographic 21H1 lub wyższej.</span><span class="sxs-lookup"><span data-stu-id="ada4c-240"><sup>2</sup> - Available in Windows Holographic 21H1 or higher.</span></span>


<span data-ttu-id="ada4c-241">Aby uzyskać pełną listę Windows 10 Ustawienia URI, odwiedź [dokumentację ustawień uruchamiania.](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)</span><span class="sxs-lookup"><span data-stu-id="ada4c-241">For a full list of Windows 10 Settings URIs, please visit the [launch settings](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
