---
title: Rejestracja w przedsiębiorstwie urządzeń HoloLens w środowisku z ograniczeniami adresów MAC Wi-Fi Mac
description: Jak adres MAC sieci na urządzeniach HoloLens 2
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
ms.openlocfilehash: a577eace62040e2d48de5d3e4cc99ef108bd006c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379707"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a><span data-ttu-id="bc216-103">Rejestracja w przedsiębiorstwie urządzeń HoloLens w środowisku z ograniczeniami adresów MAC Wi-Fi Mac</span><span class="sxs-lookup"><span data-stu-id="bc216-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="bc216-104">W tym dokumencie opisano wspólny scenariusz zidentyfikowany w środowiskach klientów, w których adres Wi-Fi jest ograniczony przez adresy MAC lub certyfikaty są wymagane do dołączenia do sieci bezprzewodowych.</span><span class="sxs-lookup"><span data-stu-id="bc216-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="bc216-105">Przykładowy scenariusz</span><span class="sxs-lookup"><span data-stu-id="bc216-105">Example Scenario</span></span>

<span data-ttu-id="bc216-106">Wielu klientów w bezpiecznych środowiskach ma ograniczenia dotyczące sieci bezprzewodowych lub przewodowych, które zezwalają na pomyślne łączenie się tylko zatwierdzonych urządzeń (na podstawie adresów MAC).</span><span class="sxs-lookup"><span data-stu-id="bc216-106">Many customers in secure environments have restrictions on their Wireless or wired networks that will only allow approved devices (based on MAC Addresses) to connect successfully.</span></span> <span data-ttu-id="bc216-107">Można to wymusić za pomocą filtrowania adresów MAC w punkcie dostępu bezprzewodowego lub na serwerze DHCP.</span><span class="sxs-lookup"><span data-stu-id="bc216-107">This may be enforced through MAC Address filtering on a Wireless Access Point or through a DHCP server.</span></span> <span data-ttu-id="bc216-108">Ponadto niektóre sieci bezprzewodowe mogą być chronione za pomocą protokołu PEAP, który wymaga, aby certyfikat został zastosowany do urządzenia przed uwierzytelnianiem w sieci bezprzewodowej.</span><span class="sxs-lookup"><span data-stu-id="bc216-108">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to authenticating on the Wireless network.</span></span>

<span data-ttu-id="bc216-109">W tym scenariuszu dwa kluczowe wymagania mogą powodować opóźnienia lub wymagać ręcznej interwencji podczas dołączania urządzeń HoloLens do sieci:</span><span class="sxs-lookup"><span data-stu-id="bc216-109">In this scenario, two key requirements may introduce delays or require manual intervention when joining HoloLens devices to the network:</span></span>

- <span data-ttu-id="bc216-110">Przed pomyślnym dołączeniem urządzenia do sieci bezprzewodowej należy do urządzenia zastosować certyfikat PEAP sieci bezprzewodowej.</span><span class="sxs-lookup"><span data-stu-id="bc216-110">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="bc216-111">Adres MAC adaptera Wi-Fi HoloLens musi być zarejestrowany.</span><span class="sxs-lookup"><span data-stu-id="bc216-111">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="bc216-112">Podstawowe wyzwania związane z powyższymi wymaganiami to:</span><span class="sxs-lookup"><span data-stu-id="bc216-112">The core challenges with the requirements above are:</span></span>

1. <span data-ttu-id="bc216-113">Adres MAC można obecnie zidentyfikować tylko z aplikacji Ustawienia na urządzeniu lub z usługi Intune po pomyślnej rejestracji.</span><span class="sxs-lookup"><span data-stu-id="bc216-113">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful enrollment.</span></span>

2. <span data-ttu-id="bc216-114">Bez adresu MAC urządzenie nie może dołączyć do sieci Wi-Fi, aby rozpocząć rejestrację.</span><span class="sxs-lookup"><span data-stu-id="bc216-114">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>

3. <span data-ttu-id="bc216-115">Ręczne obejścia tych problemów wymagają, aby technik wchodził w interakcję z urządzeniem.</span><span class="sxs-lookup"><span data-stu-id="bc216-115">Manual workarounds to these challenges require a technician to interact with the device.</span></span>

## <a name="solutions"></a><span data-ttu-id="bc216-116">Rozwiązania</span><span class="sxs-lookup"><span data-stu-id="bc216-116">Solutions</span></span>

<span data-ttu-id="bc216-117">Istnieje wiele sposobów, aby poprawić tę sytuację, w zależności od infrastruktury dostępnej w środowisku.</span><span class="sxs-lookup"><span data-stu-id="bc216-117">There are many ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="bc216-118">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="bc216-118">Solution</span></span> | <span data-ttu-id="bc216-119">Korzyści</span><span class="sxs-lookup"><span data-stu-id="bc216-119">Benefits</span></span> | <span data-ttu-id="bc216-120">Wymagania</span><span class="sxs-lookup"><span data-stu-id="bc216-120">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="bc216-121">Pakiet aprowizowania z adapterem Ethernet</span><span class="sxs-lookup"><span data-stu-id="bc216-121">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="bc216-122">Ulepsza środowisko OOBE i umożliwia szybsze środowisko techników.</span><span class="sxs-lookup"><span data-stu-id="bc216-122">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="bc216-123">Adapter USB-C Hub + Ethernet zgodny z urządzeniem HoloLens i technik będą nadal musieli wchodzić w interakcje z urządzeniem w celu przechwytywania adresów MAC i finalizacji OOBE</span><span class="sxs-lookup"><span data-stu-id="bc216-123">HoloLens compatible USB-C Hub + Ethernet adaptor, and technician will still need to interact with the device for MAC capture and OOBE finalization</span></span> |
| <span data-ttu-id="bc216-124">Autopilot z rejestracją w usłudze Intune za pośrednictwem sieci Ethernet</span><span class="sxs-lookup"><span data-stu-id="bc216-124">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="bc216-125">Jest to jednoetapowe połączenie i rejestracja urządzenia w środowisku klienta.</span><span class="sxs-lookup"><span data-stu-id="bc216-125">This is a single-step connection and registration of the device to the customer environment.</span></span> <span data-ttu-id="bc216-126">Przechwytywanie adresów MAC można ukończyć bez konieczności interakcji z urządzeniem</span><span class="sxs-lookup"><span data-stu-id="bc216-126">MAC capture can be completed without needing to interact with the device</span></span> | <span data-ttu-id="bc216-127">Usługa Intune włączona dla dzierżawy usługi AAD klienta i adaptera Ethernet zgodnego z urządzeniem HoloLens USB-C</span><span class="sxs-lookup"><span data-stu-id="bc216-127">Intune enabled for the customer AAD tenant and a HoloLens compatible USB-C Ethernet adaptor</span></span> |
| <span data-ttu-id="bc216-128">Automatyczne raportowanie adresów MAC</span><span class="sxs-lookup"><span data-stu-id="bc216-128">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="bc216-129">Gdy urządzenia są zarejestrowane w dzierżawie usługi Intune, skrypt może zgłosić adres MAC technikowi.</span><span class="sxs-lookup"><span data-stu-id="bc216-129">When devices are registered with the Intune tenant, a script can report the MAC address to the technician.</span></span> | <span data-ttu-id="bc216-130">Polecenia cmdlet programu PowerShell w usłudze Intune</span><span class="sxs-lookup"><span data-stu-id="bc216-130">Intune PowerShell cmdlets</span></span> |

## <a name="provisioning-package-with-ethernet-adaptor"></a><span data-ttu-id="bc216-131">Pakiet aprowizowania z adapterem Ethernet</span><span class="sxs-lookup"><span data-stu-id="bc216-131">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="bc216-132">Jeśli sieć przewodowa podlega również ograniczeniom mac, adres MAC adaptera USB-C Hub + Ethernet również musi być wstępnie zatwierdzony.</span><span class="sxs-lookup"><span data-stu-id="bc216-132">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Hub + Ethernet adaptor will also need to be pre-approved.</span></span> <span data-ttu-id="bc216-133">Należy zachować ostrożność przy użyciu tej karty, ponieważ umożliwi to dostęp do sieci z innych urządzeń.</span><span class="sxs-lookup"><span data-stu-id="bc216-133">Care should be taken with this adapter as it will allow access to the network from other devices.</span></span>

### <a name="requirements"></a><span data-ttu-id="bc216-134">Wymagania</span><span class="sxs-lookup"><span data-stu-id="bc216-134">Requirements</span></span>

- <span data-ttu-id="bc216-135">Port sieci przewodowej z dostępem do sieci klienta</span><span class="sxs-lookup"><span data-stu-id="bc216-135">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="bc216-136">Koncentrator USB-C zgodny z urządzeniem HoloLens z adapterem Ethernet — odpowiednie powinny być wszystkie adaptery, które nie wymagają dodatkowych sterowników ani instalacji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="bc216-136">HoloLens Compatible USB-C Hub with Ethernet adaptor — Any adapter that doesn't require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="bc216-137">Pakiet aprowizowania zawierający:</span><span class="sxs-lookup"><span data-stu-id="bc216-137">Provisioning Package containing:</span></span>
  - <span data-ttu-id="bc216-138">Zawierający informacje o sieci bezprzewodowej i certyfikat</span><span class="sxs-lookup"><span data-stu-id="bc216-138">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="bc216-139">Opcjonalnie zawierające informacje o rejestracji w usłudze Azure AD organizacji</span><span class="sxs-lookup"><span data-stu-id="bc216-139">Optionally containing enrollment information for the Organization's Azure AD</span></span>
  - <span data-ttu-id="bc216-140">Zawierające wszystkie inne wymagane ustawienia aprowowania</span><span class="sxs-lookup"><span data-stu-id="bc216-140">Containing any other required provisioning settings</span></span>

### <a name="process"></a><span data-ttu-id="bc216-141">Proces</span><span class="sxs-lookup"><span data-stu-id="bc216-141">Process</span></span>

<span data-ttu-id="bc216-142">Proces może się różnić w zależności od poziomu oprogramowania urządzenia.</span><span class="sxs-lookup"><span data-stu-id="bc216-142">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="bc216-143">Jeśli urządzenie ma aktualizację [z maja 2004 r.,](hololens-release-notes.md#windows-holographic-version-2004)wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="bc216-143">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="bc216-144">Umieść pakiet aprowizowania w katalogu głównym dysku USB i podłącz go do koncentratora.</span><span class="sxs-lookup"><span data-stu-id="bc216-144">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="bc216-145">Podłącz kabel Ethernet do adaptera Koncentrator i Ethernet.</span><span class="sxs-lookup"><span data-stu-id="bc216-145">Connect Ethernet cable to the Hub + Ethernet adapter.</span></span>
3. <span data-ttu-id="bc216-146">Podłącz koncentrator USB-C do urządzenia HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bc216-146">Connect USB-C Hub to HoloLens device.</span></span>
4. <span data-ttu-id="bc216-147">Włącz urządzenie HoloLens i umieść je na urządzeniu.</span><span class="sxs-lookup"><span data-stu-id="bc216-147">Turn on the HoloLens and put on the device.</span></span>
5. <span data-ttu-id="bc216-148">Naciśnij przycisk **Volume Down (W dół woluminu) i Power (Zasilanie),** aby zastosować pakiet aprowizowania.</span><span class="sxs-lookup"><span data-stu-id="bc216-148">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="bc216-149">Technik może teraz obserwować OOBE, a po zakończeniu pracy otwórz aplikację Ustawienia, aby pobrać adres MAC urządzenia.</span><span class="sxs-lookup"><span data-stu-id="bc216-149">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="bc216-150">Jeśli urządzenie ma kompilację systemu operacyjnego przed aktualizacją z [maja 2004](hololens-release-notes.md#windows-holographic-version-2004)r., wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="bc216-150">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="bc216-151">Włącz urządzenie HoloLens i podłącz urządzenie do komputera.</span><span class="sxs-lookup"><span data-stu-id="bc216-151">Turn on the HoloLens and plug the device into a PC.</span></span>
2. <span data-ttu-id="bc216-152">Urządzenie powinno być wyświetlane na komputerze jako urządzenie do przechowywania plików.</span><span class="sxs-lookup"><span data-stu-id="bc216-152">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="bc216-153">Kopiowanie pakietu aprowizowania na urządzenie</span><span class="sxs-lookup"><span data-stu-id="bc216-153">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="bc216-154">Podłącz kabel Ethernet do koncentratora.</span><span class="sxs-lookup"><span data-stu-id="bc216-154">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="bc216-155">Podłącz koncentrator USB-C do urządzenia HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bc216-155">Connect USB-C Hub to HoloLens device.</span></span>
6. <span data-ttu-id="bc216-156">Umieść na urządzeniach HoloLens</span><span class="sxs-lookup"><span data-stu-id="bc216-156">Put on the HoloLens</span></span>
7. <span data-ttu-id="bc216-157">Naciśnij przycisk **Volume Down (W dół woluminu) i Power (Zasilanie),** aby zastosować pakiet aprowizowania.</span><span class="sxs-lookup"><span data-stu-id="bc216-157">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="bc216-158">Technik może teraz obserwować OOBE, a po zakończeniu pracy otwórz aplikację Ustawienia, aby pobrać adres MAC urządzenia.</span><span class="sxs-lookup"><span data-stu-id="bc216-158">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

### <a name="benefits"></a><span data-ttu-id="bc216-159">Korzyści</span><span class="sxs-lookup"><span data-stu-id="bc216-159">Benefits</span></span>

<span data-ttu-id="bc216-160">Umożliwi to "pojedyncze dotknięcie" urządzenia w celu zastosowania poprawnego pakietu aprowizowania i zebrania adresu MAC urządzenia.</span><span class="sxs-lookup"><span data-stu-id="bc216-160">This will allow a "Single touch" of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="bc216-161">Pakiety aprowizowania można tworzyć zgodnie ze wskazówkami w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="bc216-161">Provisioning packages can be created following the guidance here.</span></span>](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="autopilot-with-intune-enrollment"></a><span data-ttu-id="bc216-162">Funkcja Autopilot z rejestracją w usłudze Intune</span><span class="sxs-lookup"><span data-stu-id="bc216-162">Autopilot with Intune Enrollment</span></span>

### <a name="requirements"></a><span data-ttu-id="bc216-163">Wymagania</span><span class="sxs-lookup"><span data-stu-id="bc216-163">Requirements</span></span>

- <span data-ttu-id="bc216-164">Port sieci przewodowej z dostępem do sieci klienta</span><span class="sxs-lookup"><span data-stu-id="bc216-164">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="bc216-165">Urządzenia HoloLens z systemem Windows Holographic 2004</span><span class="sxs-lookup"><span data-stu-id="bc216-165">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="bc216-166">Adapter Ethernet zgodny z urządzeniem HoloLens USB-C</span><span class="sxs-lookup"><span data-stu-id="bc216-166">HoloLens Compatible USB-C Ethernet adapter</span></span>
- <span data-ttu-id="bc216-167">Konfigurowanie i włączanie usługi Intune dla dzierżawy klienta</span><span class="sxs-lookup"><span data-stu-id="bc216-167">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="bc216-168">Urządzenie zarejestrowane w programie Autopilot i zaimportowane do dzierżawy klienta</span><span class="sxs-lookup"><span data-stu-id="bc216-168">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="bc216-169">Zasady usługi Intune zdefiniowane dla urządzenia:</span><span class="sxs-lookup"><span data-stu-id="bc216-169">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="bc216-170">Zawierający informacje o sieci bezprzewodowej i certyfikat</span><span class="sxs-lookup"><span data-stu-id="bc216-170">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="bc216-171">Zawierające wszystkie inne wymagane ustawienia aprowowania</span><span class="sxs-lookup"><span data-stu-id="bc216-171">Containing any other required provisioning settings</span></span>

<span data-ttu-id="bc216-172">Umożliwi to klientowi z zaawansowanymi wymaganiami sieciowymi zarejestrowanie urządzeń w praktycznej, skalowalnej podejściu</span><span class="sxs-lookup"><span data-stu-id="bc216-172">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="bc216-173">Wymagane będą dodatkowe wymagania wstępne, jak podano poniżej:</span><span class="sxs-lookup"><span data-stu-id="bc216-173">Additional pre-requisites will be needed as below:</span></span>
1. <span data-ttu-id="bc216-174">[Włącz dzierżawę dla rozwiązania Autopilot w wersji zapoznawczej.](https://docs.microsoft.com/hololens/hololens2-autopilot)</span><span class="sxs-lookup"><span data-stu-id="bc216-174">[Enable the Tenant for the Autopilot preview](https://docs.microsoft.com/hololens/hololens2-autopilot).</span></span>
1. <span data-ttu-id="bc216-175">Utwórz zasady urządzenia HoloLens, aby zastąpić pakiet aprowizowania w usłudze Intune.</span><span class="sxs-lookup"><span data-stu-id="bc216-175">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="bc216-176">Utwórz zasady usługi Intune dla urządzenia HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bc216-176">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="bc216-177">Przypisz urządzenia do odpowiedniej grupy.</span><span class="sxs-lookup"><span data-stu-id="bc216-177">Assign the devices to the correct group.</span></span>

### <a name="process"></a><span data-ttu-id="bc216-178">Proces</span><span class="sxs-lookup"><span data-stu-id="bc216-178">Process</span></span>

1. <span data-ttu-id="bc216-179">Podłącz kabel ethernet do adaptera i podłącz go do portu USB-C na urządzeniu HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="bc216-179">Connect the ethernet cable to the adapter and plug the adapter into the USB-C port on the HoloLens 2 device.</span></span>

2. <span data-ttu-id="bc216-180">Włącz urządzenie HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bc216-180">Turn on the HoloLens.</span></span>

3. <span data-ttu-id="bc216-181">Urządzenie powinno automatycznie łączyć się z Internetem podczas OOBE za pośrednictwem adaptera Ethernet.</span><span class="sxs-lookup"><span data-stu-id="bc216-181">The device should automatically connect to the internet during OOBE via the Ethernet adaptor.</span></span> <span data-ttu-id="bc216-182">Powinien wykrywać konfigurację rozwiązania Autopilot i automatycznie rejestrować się w usługach Azure AD i Intune.</span><span class="sxs-lookup"><span data-stu-id="bc216-182">It should detect the Autopilot configuration and automatically register with Azure AD and Intune.</span></span>

4. <span data-ttu-id="bc216-183">Urządzenie zastosuje wymagane certyfikaty usługi Wi-Fi i inną konfigurację zgodnie z potrzebami za pośrednictwem usługi Intune.</span><span class="sxs-lookup"><span data-stu-id="bc216-183">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune.</span></span>

5. <span data-ttu-id="bc216-184">Po zakończeniu technik może załadować portal usługi Intune (Endpoint Manager) i przejść do strony właściwości urządzenia na stronie Strona główna **-> Devices -> DeviceName -> Hardware**.</span><span class="sxs-lookup"><span data-stu-id="bc216-184">When complete, the technician can load the Intune (Endpoint Manager) Portal and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**.</span></span>

6. <span data-ttu-id="bc216-185">Adres Wi-Fi MAC będzie widoczny w portalu usługi Intune.</span><span class="sxs-lookup"><span data-stu-id="bc216-185">The Wi-Fi MAC address will be visible within the Intune Portal.</span></span>

   ![Adres MAC za pośrednictwem usługi Intune](images/mac-address-intune.jpg)

7. <span data-ttu-id="bc216-187">Technik doda ten adres MAC jako dozwolone urządzenie.</span><span class="sxs-lookup"><span data-stu-id="bc216-187">The technician will add this MAC address as an allowed device.</span></span>

### <a name="benefits"></a><span data-ttu-id="bc216-188">Korzyści</span><span class="sxs-lookup"><span data-stu-id="bc216-188">Benefits</span></span>

<span data-ttu-id="bc216-189">Pozwoli to na "odsłonięte" środowisko wdrażania dla techników, dzięki którym urządzenie będzie możliwe od skrzynki do zarejestrowania w usłudze Azure AD i Intune bez konieczności noszenia urządzenia przez technika ani ręcznej interakcji ze środowiskiem HoloLens.</span><span class="sxs-lookup"><span data-stu-id="bc216-189">This will allow a "Heads off" deployment experience for the Technician, with the device being able to go from the box to enrolled in Azure AD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <a name="reporting-of-mac-addresses-to-the-technician"></a><span data-ttu-id="bc216-190">Raportowanie adresów MAC technikowi</span><span class="sxs-lookup"><span data-stu-id="bc216-190">Reporting of MAC addresses to the Technician</span></span>

### <a name="requirements"></a><span data-ttu-id="bc216-191">Wymagania</span><span class="sxs-lookup"><span data-stu-id="bc216-191">Requirements</span></span>

- <span data-ttu-id="bc216-192">Autoryzacja "programu PowerShell programu Intune Graph" względem dzierżawy klienta</span><span class="sxs-lookup"><span data-stu-id="bc216-192">Authorization of the "Intune Graph PowerShell" against the customer Tenant</span></span>
- <span data-ttu-id="bc216-193">Instalacja programu PowerShell programu Intune Graph na maszynie techników.</span><span class="sxs-lookup"><span data-stu-id="bc216-193">Installation of the Intune Graph PowerShell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="bc216-194">Dostęp do odczytu do elementów "Urządzenia zarządzane" w usłudze Intune.</span><span class="sxs-lookup"><span data-stu-id="bc216-194">Read access to the "Managed Devices" elements of Intune.</span></span> <span data-ttu-id="bc216-195">(Operator pomocy technicznej lub powyższy albo rola niestandardowa)</span><span class="sxs-lookup"><span data-stu-id="bc216-195">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="bc216-196">Obecnie nie ma "prostego" sposobu wyzwalania polecenia automatyzacji na podstawie rejestracji nowego urządzenia w usłudze Intune.</span><span class="sxs-lookup"><span data-stu-id="bc216-196">At present, there is no "simple" way to trigger an automation command based on the enrollment of a new device within Intune.</span></span> <span data-ttu-id="bc216-197">W związku z tym to polecenie zapewni technikowi prosty sposób pobierania adresu MAC bez konieczności logowania się do portalu i ręcznego pobierania go.</span><span class="sxs-lookup"><span data-stu-id="bc216-197">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="bc216-198">Spowoduje to zwrócenie nazwy i adresu MAC wszystkich urządzeń HoloLens zarejestrowanych w ciągu ostatnich 30 dni.</span><span class="sxs-lookup"><span data-stu-id="bc216-198">This will return the name and MAC address of any HoloLens devices that have been enrolled in the last 30 days.</span></span>

![Adres MAC za pośrednictwem programu PowerShell](images/mac-address-powershell.jpg)

### <a name="process"></a><span data-ttu-id="bc216-200">Proces</span><span class="sxs-lookup"><span data-stu-id="bc216-200">Process</span></span>

<span data-ttu-id="bc216-201">Po zakończeniu rejestracji w usłudze Intune technik uruchamia powyższy skrypt, aby pobrać adres MAC.</span><span class="sxs-lookup"><span data-stu-id="bc216-201">After the Intune enrollment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
