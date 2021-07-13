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
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a><span data-ttu-id="42e27-103">Enterprise Rejestrowanie urządzeń HoloLens w środowisku z ograniczeniami adresów MAC Wi-Fi MAC</span><span class="sxs-lookup"><span data-stu-id="42e27-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="42e27-104">W tym dokumencie opisano wspólny scenariusz zidentyfikowany w środowiskach klientów, w których adres Wi-Fi jest ograniczony przez adresy MAC lub certyfikaty są wymagane do dołączenia do sieci bezprzewodowych.</span><span class="sxs-lookup"><span data-stu-id="42e27-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="42e27-105">Przykładowy scenariusz</span><span class="sxs-lookup"><span data-stu-id="42e27-105">Example Scenario</span></span>

<span data-ttu-id="42e27-106">Wielu klientów w bezpiecznych środowiskach ma ograniczenia dotyczące sieci bezprzewodowych lub przewodowych, które umożliwią pomyślne łączenie się tylko zatwierdzonym urządzeniem (na podstawie adresów MAC).</span><span class="sxs-lookup"><span data-stu-id="42e27-106">Many customers in secure environments have restrictions on their Wireless or wired networks that will only allow approved devices (based on MAC Addresses) to connect successfully.</span></span> <span data-ttu-id="42e27-107">Można to wymusić za pomocą filtrowania adresów MAC w punkcie dostępu bezprzewodowego lub na serwerze DHCP.</span><span class="sxs-lookup"><span data-stu-id="42e27-107">This may be enforced through MAC Address filtering on a Wireless Access Point or through a DHCP server.</span></span> <span data-ttu-id="42e27-108">Ponadto niektóre sieci bezprzewodowe mogą być chronione przy użyciu protokołu PEAP, który wymaga, aby certyfikat był stosowany do urządzenia przed uwierzytelnienia w sieci bezprzewodowej.</span><span class="sxs-lookup"><span data-stu-id="42e27-108">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to authenticating on the Wireless network.</span></span>

<span data-ttu-id="42e27-109">W tym scenariuszu dwa kluczowe wymagania mogą powodować opóźnienia lub wymagać ręcznej interwencji podczas dołączania HoloLens urządzeń do sieci:</span><span class="sxs-lookup"><span data-stu-id="42e27-109">In this scenario, two key requirements may introduce delays or require manual intervention when joining HoloLens devices to the network:</span></span>

- <span data-ttu-id="42e27-110">Aby urządzenie pomyślnie dołączyło do sieci bezprzewodowej, należy do urządzenia zastosować certyfikat PEAP sieci bezprzewodowej.</span><span class="sxs-lookup"><span data-stu-id="42e27-110">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="42e27-111">Adres MAC adaptera HoloLens Wi-Fi musi być zarejestrowany.</span><span class="sxs-lookup"><span data-stu-id="42e27-111">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="42e27-112">Podstawowe wyzwania związane z powyższymi wymaganiami to:</span><span class="sxs-lookup"><span data-stu-id="42e27-112">The core challenges with the requirements above are:</span></span>

1. <span data-ttu-id="42e27-113">Adres MAC można obecnie zidentyfikować tylko z aplikacji Ustawienia na urządzeniu lub z usługi Intune po pomyślnej rejestracji.</span><span class="sxs-lookup"><span data-stu-id="42e27-113">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful enrollment.</span></span>

2. <span data-ttu-id="42e27-114">Bez adresu MAC urządzenie nie może dołączyć do sieci Wi-Fi, aby rozpocząć rejestrację.</span><span class="sxs-lookup"><span data-stu-id="42e27-114">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>

3. <span data-ttu-id="42e27-115">Ręczne obejścia tych problemów wymagają, aby technik współdziałał z urządzeniem.</span><span class="sxs-lookup"><span data-stu-id="42e27-115">Manual workarounds to these challenges require a technician to interact with the device.</span></span>

## <a name="solutions"></a><span data-ttu-id="42e27-116">Rozwiązania</span><span class="sxs-lookup"><span data-stu-id="42e27-116">Solutions</span></span>

<span data-ttu-id="42e27-117">Istnieje wiele sposobów na poprawienie tej sytuacji, w zależności od infrastruktury dostępnej w środowisku.</span><span class="sxs-lookup"><span data-stu-id="42e27-117">There are many ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="42e27-118">Rozwiązanie</span><span class="sxs-lookup"><span data-stu-id="42e27-118">Solution</span></span> | <span data-ttu-id="42e27-119">Korzyści</span><span class="sxs-lookup"><span data-stu-id="42e27-119">Benefits</span></span> | <span data-ttu-id="42e27-120">Wymagania</span><span class="sxs-lookup"><span data-stu-id="42e27-120">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="42e27-121">Pakiet aprowizowania z adapterem Ethernet</span><span class="sxs-lookup"><span data-stu-id="42e27-121">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="42e27-122">Ulepsza środowisko OOBE i umożliwia szybsze środowisko techników.</span><span class="sxs-lookup"><span data-stu-id="42e27-122">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="42e27-123">HoloLens zgodny adapter USB-C Hub + Ethernet, a technik nadal będzie musiał wchodzić w interakcję z urządzeniem na potrzeby przechwytywania MAC i finalizacji OOBE</span><span class="sxs-lookup"><span data-stu-id="42e27-123">HoloLens compatible USB-C Hub + Ethernet adaptor, and technician will still need to interact with the device for MAC capture and OOBE finalization</span></span> |
| <span data-ttu-id="42e27-124">Funkcja Autopilot z rejestracją w usłudze Intune za pośrednictwem sieci Ethernet</span><span class="sxs-lookup"><span data-stu-id="42e27-124">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="42e27-125">Jest to jednoetapowe połączenie i rejestracja urządzenia w środowisku klienta.</span><span class="sxs-lookup"><span data-stu-id="42e27-125">This is a single-step connection and registration of the device to the customer environment.</span></span> <span data-ttu-id="42e27-126">Przechwytywanie danych MAC można ukończyć bez konieczności interakcji z urządzeniem</span><span class="sxs-lookup"><span data-stu-id="42e27-126">MAC capture can be completed without needing to interact with the device</span></span> | <span data-ttu-id="42e27-127">Usługa Intune włączona dla dzierżawy usługi AAD klienta i HoloLens adaptera Ethernet USB-C</span><span class="sxs-lookup"><span data-stu-id="42e27-127">Intune enabled for the customer AAD tenant and a HoloLens compatible USB-C Ethernet adaptor</span></span> |
| <span data-ttu-id="42e27-128">Automatyczne raportowanie adresów MAC</span><span class="sxs-lookup"><span data-stu-id="42e27-128">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="42e27-129">Gdy urządzenia są zarejestrowane w dzierżawie usługi Intune, skrypt może zgłosić adres MAC technikowi.</span><span class="sxs-lookup"><span data-stu-id="42e27-129">When devices are registered with the Intune tenant, a script can report the MAC address to the technician.</span></span> | <span data-ttu-id="42e27-130">Polecenia cmdlet programu PowerShell w usłudze Intune</span><span class="sxs-lookup"><span data-stu-id="42e27-130">Intune PowerShell cmdlets</span></span> |

## <a name="provisioning-package-with-ethernet-adaptor"></a><span data-ttu-id="42e27-131">Pakiet aprowizowania z adapterem Ethernet</span><span class="sxs-lookup"><span data-stu-id="42e27-131">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="42e27-132">Jeśli sieć przewodowa podlega również ograniczeniom adresów MAC, adres MAC adaptera USB-C Hub + Ethernet również musi być wstępnie zatwierdzony.</span><span class="sxs-lookup"><span data-stu-id="42e27-132">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Hub + Ethernet adaptor will also need to be pre-approved.</span></span> <span data-ttu-id="42e27-133">Należy zachować ostrożność przy użyciu tej karty, ponieważ umożliwi to dostęp do sieci z innych urządzeń.</span><span class="sxs-lookup"><span data-stu-id="42e27-133">Care should be taken with this adapter as it will allow access to the network from other devices.</span></span>

### <a name="requirements"></a><span data-ttu-id="42e27-134">Wymagania</span><span class="sxs-lookup"><span data-stu-id="42e27-134">Requirements</span></span>

- <span data-ttu-id="42e27-135">Port sieci przewodowej z dostępem do sieci klienta</span><span class="sxs-lookup"><span data-stu-id="42e27-135">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="42e27-136">HoloLens Zgodny koncentrator USB-C z adapterem Ethernet — odpowiednia powinna być każda karta, która nie wymaga dodatkowych sterowników ani instalacji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="42e27-136">HoloLens Compatible USB-C Hub with Ethernet adaptor — Any adapter that doesn't require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="42e27-137">Pakiet aprowizowania zawierający:</span><span class="sxs-lookup"><span data-stu-id="42e27-137">Provisioning Package containing:</span></span>
  - <span data-ttu-id="42e27-138">Zawierający informacje o sieci bezprzewodowej i certyfikat</span><span class="sxs-lookup"><span data-stu-id="42e27-138">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="42e27-139">Opcjonalnie zawierające informacje o rejestracji dla usługi Azure AD organizacji</span><span class="sxs-lookup"><span data-stu-id="42e27-139">Optionally containing enrollment information for the Organization's Azure AD</span></span>
  - <span data-ttu-id="42e27-140">Zawiera wszystkie inne wymagane ustawienia aprowowania</span><span class="sxs-lookup"><span data-stu-id="42e27-140">Containing any other required provisioning settings</span></span>

### <a name="process"></a><span data-ttu-id="42e27-141">Proces</span><span class="sxs-lookup"><span data-stu-id="42e27-141">Process</span></span>

<span data-ttu-id="42e27-142">Proces może się różnić w zależności od poziomu oprogramowania urządzenia.</span><span class="sxs-lookup"><span data-stu-id="42e27-142">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="42e27-143">Jeśli urządzenie ma aktualizację [z maja 2004](hololens-release-notes.md#windows-holographic-version-2004)r., wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="42e27-143">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="42e27-144">Umieść pakiet aprowizowania na katalogu głównym dysku USB i podłącz go do koncentratora.</span><span class="sxs-lookup"><span data-stu-id="42e27-144">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="42e27-145">Połączenie Kabel Ethernet do adaptera Koncentrator + Ethernet.</span><span class="sxs-lookup"><span data-stu-id="42e27-145">Connect Ethernet cable to the Hub + Ethernet adapter.</span></span>
3. <span data-ttu-id="42e27-146">Połączenie Koncentrator USB-C do HoloLens urządzenia.</span><span class="sxs-lookup"><span data-stu-id="42e27-146">Connect USB-C Hub to HoloLens device.</span></span>
4. <span data-ttu-id="42e27-147">Włącz HoloLens i umieść je na urządzeniu.</span><span class="sxs-lookup"><span data-stu-id="42e27-147">Turn on the HoloLens and put on the device.</span></span>
5. <span data-ttu-id="42e27-148">Naciśnij przycisk **Volume Down (Dół woluminu) i Power (Zasilanie),** aby zastosować pakiet aprowizowania.</span><span class="sxs-lookup"><span data-stu-id="42e27-148">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="42e27-149">Technik może teraz postępować zgodnie z ustawieniami OOBE, a po zakończeniu otwórz aplikację Ustawienia, aby pobrać adres MAC urządzenia.</span><span class="sxs-lookup"><span data-stu-id="42e27-149">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="42e27-150">Jeśli urządzenie ma kompilację systemu operacyjnego przed aktualizacją z [maja 2004](hololens-release-notes.md#windows-holographic-version-2004)r., wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="42e27-150">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="42e27-151">Włącz urządzenie HoloLens podłącz urządzenie do komputera.</span><span class="sxs-lookup"><span data-stu-id="42e27-151">Turn on the HoloLens and plug the device into a PC.</span></span>
2. <span data-ttu-id="42e27-152">Urządzenie powinno być wyświetlane na komputerze jako urządzenie do przechowywania plików.</span><span class="sxs-lookup"><span data-stu-id="42e27-152">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="42e27-153">Kopiowanie pakietu aprowizowania na urządzenie</span><span class="sxs-lookup"><span data-stu-id="42e27-153">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="42e27-154">Połączenie Kabel Ethernet do koncentratora.</span><span class="sxs-lookup"><span data-stu-id="42e27-154">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="42e27-155">Połączenie Koncentrator USB-C do HoloLens urządzenia.</span><span class="sxs-lookup"><span data-stu-id="42e27-155">Connect USB-C Hub to HoloLens device.</span></span>
6. <span data-ttu-id="42e27-156">Umieść na HoloLens</span><span class="sxs-lookup"><span data-stu-id="42e27-156">Put on the HoloLens</span></span>
7. <span data-ttu-id="42e27-157">Naciśnij przycisk **Volume Down (Dół woluminu) i Power (Zasilanie),** aby zastosować pakiet aprowizowania.</span><span class="sxs-lookup"><span data-stu-id="42e27-157">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="42e27-158">Technik może teraz postępować zgodnie z ustawieniami OOBE, a po zakończeniu otwórz aplikację Ustawienia, aby pobrać adres MAC urządzenia.</span><span class="sxs-lookup"><span data-stu-id="42e27-158">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

### <a name="benefits"></a><span data-ttu-id="42e27-159">Korzyści</span><span class="sxs-lookup"><span data-stu-id="42e27-159">Benefits</span></span>

<span data-ttu-id="42e27-160">Pozwoli to na "dotknięcie pojedynczego dotyku" urządzenia w celu zastosowania poprawnego pakietu aprowizowania i zebrania adresu MAC urządzenia.</span><span class="sxs-lookup"><span data-stu-id="42e27-160">This will allow a "Single touch" of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="42e27-161">Pakiety aprowizowania można tworzyć zgodnie ze wskazówkami tutaj.</span><span class="sxs-lookup"><span data-stu-id="42e27-161">Provisioning packages can be created following the guidance here.</span></span>](hololens-provisioning.md)

## <a name="autopilot-with-intune-enrollment"></a><span data-ttu-id="42e27-162">Funkcja Autopilot z rejestracją w usłudze Intune</span><span class="sxs-lookup"><span data-stu-id="42e27-162">Autopilot with Intune Enrollment</span></span>

### <a name="requirements"></a><span data-ttu-id="42e27-163">Wymagania</span><span class="sxs-lookup"><span data-stu-id="42e27-163">Requirements</span></span>

- <span data-ttu-id="42e27-164">Port sieci przewodowej z dostępem do sieci klienta</span><span class="sxs-lookup"><span data-stu-id="42e27-164">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="42e27-165">HoloLens z systemem Windows Holographic 2004</span><span class="sxs-lookup"><span data-stu-id="42e27-165">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="42e27-166">HoloLens Zgodny adapter Ethernet USB-C</span><span class="sxs-lookup"><span data-stu-id="42e27-166">HoloLens Compatible USB-C Ethernet adapter</span></span>
- <span data-ttu-id="42e27-167">Konfigurowanie i włączanie usługi Intune dla dzierżawy klienta</span><span class="sxs-lookup"><span data-stu-id="42e27-167">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="42e27-168">Urządzenie zarejestrowane na potrzeby rozwiązania Autopilot i zaimportowane do dzierżawy klienta</span><span class="sxs-lookup"><span data-stu-id="42e27-168">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="42e27-169">Zasady usługi Intune zdefiniowane dla urządzenia:</span><span class="sxs-lookup"><span data-stu-id="42e27-169">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="42e27-170">Zawierający informacje o sieci bezprzewodowej i certyfikat</span><span class="sxs-lookup"><span data-stu-id="42e27-170">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="42e27-171">Zawiera wszystkie inne wymagane ustawienia aprowowania</span><span class="sxs-lookup"><span data-stu-id="42e27-171">Containing any other required provisioning settings</span></span>

<span data-ttu-id="42e27-172">Umożliwi to klientowi z zaawansowanymi wymaganiami sieciowymi zarejestrowanie urządzeń w praktycznej, skalowalnej podejściu</span><span class="sxs-lookup"><span data-stu-id="42e27-172">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="42e27-173">Wymagane będą dodatkowe wymagania wstępne, jak podano poniżej:</span><span class="sxs-lookup"><span data-stu-id="42e27-173">Additional pre-requisites will be needed as below:</span></span>
1. <span data-ttu-id="42e27-174">[Włącz dzierżawę dla wersji zapoznawczej rozwiązania Autopilot.](hololens2-autopilot.md)</span><span class="sxs-lookup"><span data-stu-id="42e27-174">[Enable the Tenant for the Autopilot preview](hololens2-autopilot.md).</span></span>
1. <span data-ttu-id="42e27-175">Utwórz zasady HoloLens, aby zastąpić pakiet aprowizowania w usłudze Intune.</span><span class="sxs-lookup"><span data-stu-id="42e27-175">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="42e27-176">Utwórz zasady HoloLens Intune.</span><span class="sxs-lookup"><span data-stu-id="42e27-176">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="42e27-177">Przypisz urządzenia do odpowiedniej grupy.</span><span class="sxs-lookup"><span data-stu-id="42e27-177">Assign the devices to the correct group.</span></span>

### <a name="process"></a><span data-ttu-id="42e27-178">Proces</span><span class="sxs-lookup"><span data-stu-id="42e27-178">Process</span></span>

1. <span data-ttu-id="42e27-179">Połączenie do adaptera i podłącz go do portu USB-C na urządzeniu HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="42e27-179">Connect the ethernet cable to the adapter and plug the adapter into the USB-C port on the HoloLens 2 device.</span></span>

2. <span data-ttu-id="42e27-180">Włącz HoloLens.</span><span class="sxs-lookup"><span data-stu-id="42e27-180">Turn on the HoloLens.</span></span>

3. <span data-ttu-id="42e27-181">Urządzenie powinno automatycznie łączyć się z Internetem podczas OOBE za pośrednictwem adaptera Ethernet.</span><span class="sxs-lookup"><span data-stu-id="42e27-181">The device should automatically connect to the internet during OOBE via the Ethernet adaptor.</span></span> <span data-ttu-id="42e27-182">Powinna ona wykrywać konfigurację rozwiązania Autopilot i automatycznie rejestrować się w usłudze Azure AD i Intune.</span><span class="sxs-lookup"><span data-stu-id="42e27-182">It should detect the Autopilot configuration and automatically register with Azure AD and Intune.</span></span>

4. <span data-ttu-id="42e27-183">Urządzenie zastosuje wymagane certyfikaty usługi Wi-Fi i inną konfigurację zgodnie z potrzebami za pośrednictwem usługi Intune.</span><span class="sxs-lookup"><span data-stu-id="42e27-183">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune.</span></span>

5. <span data-ttu-id="42e27-184">Po zakończeniu technik może załadować portal usługi Intune (Endpoint Manager) i przejść do strony właściwości urządzenia na stronie Strona główna **-> Devices -> DeviceName -> Hardware**.</span><span class="sxs-lookup"><span data-stu-id="42e27-184">When complete, the technician can load the Intune (Endpoint Manager) Portal and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**.</span></span>

6. <span data-ttu-id="42e27-185">Adres Wi-Fi MAC będzie widoczny w portalu usługi Intune.</span><span class="sxs-lookup"><span data-stu-id="42e27-185">The Wi-Fi MAC address will be visible within the Intune Portal.</span></span>

   ![Adres MAC za pośrednictwem usługi Intune](images/mac-address-intune.jpg)

7. <span data-ttu-id="42e27-187">Technik doda ten adres MAC jako dozwolone urządzenie.</span><span class="sxs-lookup"><span data-stu-id="42e27-187">The technician will add this MAC address as an allowed device.</span></span>

### <a name="benefits"></a><span data-ttu-id="42e27-188">Korzyści</span><span class="sxs-lookup"><span data-stu-id="42e27-188">Benefits</span></span>

<span data-ttu-id="42e27-189">Umożliwi to technikowi "odebranie" środowiska wdrażania z urządzeniem, które będzie możliwe z urządzenia do zarejestrowania w usłudze Azure AD i Intune bez konieczności noszenia urządzenia lub ręcznej interakcji ze środowiskiem HoloLens intune.</span><span class="sxs-lookup"><span data-stu-id="42e27-189">This will allow a "Heads off" deployment experience for the Technician, with the device being able to go from the box to enrolled in Azure AD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <a name="reporting-of-mac-addresses-to-the-technician"></a><span data-ttu-id="42e27-190">Raportowanie adresów MAC technikowi</span><span class="sxs-lookup"><span data-stu-id="42e27-190">Reporting of MAC addresses to the Technician</span></span>

### <a name="requirements"></a><span data-ttu-id="42e27-191">Wymagania</span><span class="sxs-lookup"><span data-stu-id="42e27-191">Requirements</span></span>

- <span data-ttu-id="42e27-192">Autoryzacja usługi "Intune Graph PowerShell" względem dzierżawy klienta</span><span class="sxs-lookup"><span data-stu-id="42e27-192">Authorization of the "Intune Graph PowerShell" against the customer Tenant</span></span>
- <span data-ttu-id="42e27-193">Instalacja programu PowerShell Graph Intune na maszynie techników.</span><span class="sxs-lookup"><span data-stu-id="42e27-193">Installation of the Intune Graph PowerShell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="42e27-194">Dostęp do odczytu do elementów "Urządzenia zarządzane" usługi Intune.</span><span class="sxs-lookup"><span data-stu-id="42e27-194">Read access to the "Managed Devices" elements of Intune.</span></span> <span data-ttu-id="42e27-195">(Operator pomocy technicznej lub powyższy albo rola niestandardowa)</span><span class="sxs-lookup"><span data-stu-id="42e27-195">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="42e27-196">Obecnie nie ma "prostego" sposobu wyzwalania polecenia automatyzacji na podstawie rejestracji nowego urządzenia w usłudze Intune.</span><span class="sxs-lookup"><span data-stu-id="42e27-196">At present, there is no "simple" way to trigger an automation command based on the enrollment of a new device within Intune.</span></span> <span data-ttu-id="42e27-197">W związku z tym to polecenie zapewni technikowi prosty sposób pobierania adresu MAC bez konieczności logowania się do portalu i ręcznego pobierania go.</span><span class="sxs-lookup"><span data-stu-id="42e27-197">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="42e27-198">Spowoduje to zwrócenie nazwy i adresu MAC wszystkich urządzeń HoloLens zarejestrowanych w ciągu ostatnich 30 dni.</span><span class="sxs-lookup"><span data-stu-id="42e27-198">This will return the name and MAC address of any HoloLens devices that have been enrolled in the last 30 days.</span></span>

![Adres MAC za pośrednictwem programu PowerShell](images/mac-address-powershell.jpg)

### <a name="process"></a><span data-ttu-id="42e27-200">Proces</span><span class="sxs-lookup"><span data-stu-id="42e27-200">Process</span></span>

<span data-ttu-id="42e27-201">Po zakończeniu rejestracji w usłudze Intune technik uruchamia powyższy skrypt, aby pobrać adres MAC.</span><span class="sxs-lookup"><span data-stu-id="42e27-201">After the Intune enrollment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
