---
title: Łączenie urządzenia HoloLens z siecią
description: Dowiedz się, jak skonfigurować urządzenie HoloLens i połączyć się z Internetem oraz jak zidentyfikować adres IP urządzenia.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, Wi-Fi, bezprzewodowe, Internet, ip, adres IP
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: 8564fb0483226a16722ada345de325577cda77d6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923605"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="21f98-104">Łączenie urządzenia HoloLens z siecią</span><span class="sxs-lookup"><span data-stu-id="21f98-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="21f98-105">Aby wykonać większość czynności na urządzeniach HoloLens, musisz mieć połączenie z siecią.</span><span class="sxs-lookup"><span data-stu-id="21f98-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="21f98-106">Urządzenie HoloLens zawiera przycisk radiowy 2x2 Wi-Fi z możliwością 802.11ac, a połączenie z siecią jest podobne do łączenia urządzenia Windows 10 Desktop lub Mobile z Wi-Fi siecią.</span><span class="sxs-lookup"><span data-stu-id="21f98-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="21f98-107">Ten przewodnik pomoże Ci:</span><span class="sxs-lookup"><span data-stu-id="21f98-107">This guide will help you:</span></span>

- <span data-ttu-id="21f98-108">Nawiązywanie połączenia z siecią przy użyciu sieci Wi-Fi lub tylko dla urządzenia HoloLens 2 Wi-Fi Direct lub Ethernet za pośrednictwem portu USB-C</span><span class="sxs-lookup"><span data-stu-id="21f98-108">Connect to a network using Wi-Fi, or for HoloLens 2 only, Wi-Fi Direct or Ethernet over USB-C</span></span>
- <span data-ttu-id="21f98-109">Wyłączanie i ponowne włączanie Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="21f98-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="21f98-110">Przeczytaj więcej na temat [korzystania z urządzenia HoloLens w trybie offline.](hololens-offline.md)</span><span class="sxs-lookup"><span data-stu-id="21f98-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="21f98-111">Nawiązywanie połączenia po raz pierwszy</span><span class="sxs-lookup"><span data-stu-id="21f98-111">Connecting for the first time</span></span>

<span data-ttu-id="21f98-112">Przy pierwszym użyciu urządzenia HoloLens zostaniesz poprowadzenie przez proces nawiązywania połączenia z Wi-Fi siecią.</span><span class="sxs-lookup"><span data-stu-id="21f98-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="21f98-113">Jeśli podczas instalacji masz problemy z nawiązaniem połączenia z usługą Wi-Fi, upewnij się, że sieć jest siecią otwartą, chronioną hasłem lub siecią w witrynie Captive Portal.</span><span class="sxs-lookup"><span data-stu-id="21f98-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="21f98-114">Upewnij się również, że sieć nie wymaga użycia certyfikatu do nawiązania połączenia.</span><span class="sxs-lookup"><span data-stu-id="21f98-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="21f98-115">Po zakończeniu instalacji możesz połączyć się z innymi typami sieci Wi-Fi sieci.</span><span class="sxs-lookup"><span data-stu-id="21f98-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="21f98-116">Na urządzeniach HoloLens 2 użytkownik może również użyć adaptera [USB-C](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) do sieci Ethernet, aby połączyć się bezpośrednio z Wi-Fi, aby pomóc w konfigurowaniu urządzenia.</span><span class="sxs-lookup"><span data-stu-id="21f98-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="21f98-117">Po skonfigurowaniu urządzenia użytkownik może nadal korzystać z karty lub może odłączyć urządzenie od karty i połączyć się [z siecią Wi-Fi po skonfigurowaniu.](hololens-network.md#connecting-to-wi-fi-after-setup)</span><span class="sxs-lookup"><span data-stu-id="21f98-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="21f98-118">Nawiązywanie połączenia Wi-Fi po instalacji</span><span class="sxs-lookup"><span data-stu-id="21f98-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="21f98-119">Wstępnie sformuj **gest Start i** wybierz pozycję **Ustawienia.**</span><span class="sxs-lookup"><span data-stu-id="21f98-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="21f98-120">Aplikacja Ustawienia zostanie automatycznie umieszczona przed toem.</span><span class="sxs-lookup"><span data-stu-id="21f98-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="21f98-121">Wybierz **pozycję Sieć &**  >  **Wi-Fi.**</span><span class="sxs-lookup"><span data-stu-id="21f98-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="21f98-122">Upewnij się, że sieć Wi-Fi jest włączona.</span><span class="sxs-lookup"><span data-stu-id="21f98-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="21f98-123">Jeśli nie widzisz swojej sieci, przewiń listę w dół.</span><span class="sxs-lookup"><span data-stu-id="21f98-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="21f98-124">Wybierz sieć, a następnie wybierz pozycję **Połącz.**</span><span class="sxs-lookup"><span data-stu-id="21f98-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="21f98-125">Jeśli zostanie wyświetlony monit o hasło sieciowe, wpisz je, a następnie wybierz przycisk **Dalej.**</span><span class="sxs-lookup"><span data-stu-id="21f98-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![Ustawienia Wi-Fi urządzenia HoloLens](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="21f98-127">Aby potwierdzić, że masz połączenie z Wi-Fi siecią, sprawdź stan Wi-Fi w menu **Start:**</span><span class="sxs-lookup"><span data-stu-id="21f98-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="21f98-128">Otwórz menu **Start.**</span><span class="sxs-lookup"><span data-stu-id="21f98-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="21f98-129">Sprawdź, czy w lewym górnym rogu menu **Start** Wi-Fi stan.</span><span class="sxs-lookup"><span data-stu-id="21f98-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="21f98-130">Zostaną wyświetlone Wi-Fi i SSID połączonej sieci.</span><span class="sxs-lookup"><span data-stu-id="21f98-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="21f98-131">Jeśli Wi-Fi jest niedostępny, możesz również połączyć się [z sieciami komórkowymi i 5G.](hololens-cellular.md)</span><span class="sxs-lookup"><span data-stu-id="21f98-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](hololens-cellular.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="21f98-132">Domyślnie użytkownicy nie mogą dostosować zachowania mobilnego urządzenia HoloLens 2 w Wi-Fi — jedynym sposobem odświeżenia listy Wi-Fi jest przełączenie przełącznika Wi-Fi Wyłączone i **Wł.**.</span><span class="sxs-lookup"><span data-stu-id="21f98-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="21f98-133">Zapobiega to wielu problemom, takim jak to, że urządzenie może pozostać "zablokowane" w ap, gdy będzie poza zakresem.</span><span class="sxs-lookup"><span data-stu-id="21f98-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="21f98-134">Łączenie urządzenia HoloLens z usługą Enterprise Wi-Fi Network</span><span class="sxs-lookup"><span data-stu-id="21f98-134">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="21f98-135">Profile Wi-Fi przedsiębiorstwa używają protokołu uwierzytelniania rozszerzanego (EAP, Extensible Authentication Protocol) do uwierzytelniania Wi-Fi połączeń.</span><span class="sxs-lookup"><span data-stu-id="21f98-135">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="21f98-136">Profil urządzenia HoloLens Enterprise Wi-Fi można skonfigurować za pomocą rozwiązania MDM lub pakietu aprowizowania utworzonego przez program [Windows Configuration Designer.](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)</span><span class="sxs-lookup"><span data-stu-id="21f98-136">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="21f98-137">Aby Microsoft Intune zarządzanego urządzenia, zapoznaj się z instrukcjami dotyczącymi konfiguracji usługi [Intune.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)</span><span class="sxs-lookup"><span data-stu-id="21f98-137">For Microsoft Intune managed device, refer to [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="21f98-138">Aby utworzyć pakiet Wi-Fi aprowizowania w UCD, wymagany jest wstępnie skonfigurowany Wi-Fi .xml aprowizowania.</span><span class="sxs-lookup"><span data-stu-id="21f98-138">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="21f98-139">Oto przykładowy profil Wi-Fi dla WPA2-Enterprise z uwierzytelnianiem EAP-TLS:</span><span class="sxs-lookup"><span data-stu-id="21f98-139">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

``` xml
<?xml version="1.0"?> 
<WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1"> 
    <name>SampleEapTlsProfile</name> 
    <SSIDConfig> 
        <SSID> 
            <hex>53616d706c65</hex> 
            <name>Sample</name> 
        </SSID> 
        <nonBroadcast>true</nonBroadcast> 
    </SSIDConfig> 
    <connectionType>ESS</connectionType> 
    <connectionMode>auto</connectionMode> 
    <autoSwitch>false</autoSwitch> 
    <MSM> 
        <security> 
            <authEncryption> 
                <authentication>WPA2</authentication> 
                <encryption>AES</encryption> 
                <useOneX>true</useOneX> 
                <FIPSMode xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode> 
            </authEncryption> 
            <PMKCacheMode>disabled</PMKCacheMode> 
            <OneX xmlns="http://www.microsoft.com/networking/OneX/v1"> 
                <authMode>machine</authMode> 
                <EAPConfig> 
                    <EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                        <EapMethod> 
                            <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type> 
                            <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId> 
                            <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType> 
                            <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId> 
                        </EapMethod> 
                        <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                            <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"> 
                                <Type>13</Type> 
                                <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"> 
                                    <CredentialsSource><CertificateStore><SimpleCertSelection>true</SimpleCertSelection> 
                                        </CertificateStore> 
                                    </CredentialsSource> 
                                    <ServerValidation> 
                                        <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation> 
                                        <ServerNames></ServerNames> 
                                        <TrustedRootCA>00 01 02 03 04 05 06 07 08 09 0a 0b 0c 0d 0e 0f 10 11 12 13</TrustedRootCA> 
                                    </ServerValidation> 
                                    <DifferentUsername>false</DifferentUsername> 
                                    <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">true</PerformServerValidation> 
                                    <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName> 
                                </EapType> 
                            </Eap> 
                        </Config> 
                    </EapHostConfig> 
                </EAPConfig> 
            </OneX> 
        </security> 
    </MSM> 
</WLANProfile> 
```


<span data-ttu-id="21f98-140">W zależności od typu protokołu EAP może być konieczne aprowizowania certyfikatu głównego urzędu certyfikacji serwera i certyfikatu klienta na urządzeniu.</span><span class="sxs-lookup"><span data-stu-id="21f98-140">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="21f98-141">Dodatkowe zasoby:</span><span class="sxs-lookup"><span data-stu-id="21f98-141">Additional resources:</span></span>

- <span data-ttu-id="21f98-142">Schemat WLANv1Profile: [[MS-GPWL]: profil sieci bezprzewodowej LAN v1 schematu | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="21f98-142">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="21f98-143">Schemat protokołu EAP-TLS: [[MS-GPWL]: Schemat protokołu TLS protokołu EAP firmy Microsoft | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="21f98-143">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

<span data-ttu-id="21f98-144">Jeśli masz [problemy](hololens2-enterprise-troubleshooting.md#) z nawiązaniem połączenia z siecią Wi-Fi, zapoznaj się ze stroną Rozwiązywanie problemów.</span><span class="sxs-lookup"><span data-stu-id="21f98-144">Check our [Troubleshooting](hololens2-enterprise-troubleshooting.md#) page if you are having problems connecting to your Wi-Fi.</span></span>

## <a name="configure-network-proxy"></a><span data-ttu-id="21f98-145">Konfigurowanie serwera proxy sieci</span><span class="sxs-lookup"><span data-stu-id="21f98-145">Configure Network Proxy</span></span>

<span data-ttu-id="21f98-146">Ta sekcja obejmuje serwer proxy sieci dla systemu operacyjnego HoloLens i platforma uniwersalna systemu Windows (UWP) przy użyciu stosu HTTP systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="21f98-146">This section covers network proxy for HoloLens OS and Universal Windows Platform (UWP) Apps using Windows HTTP stack.</span></span> <span data-ttu-id="21f98-147">Aplikacje korzystające ze stosu HTTP systemu innych niż Windows mogą mieć własną konfigurację i obsługę serwera proxy.</span><span class="sxs-lookup"><span data-stu-id="21f98-147">Applications using non-Windows HTTP stack may have their own proxy configuration and handling.</span></span> 

### <a name="proxy-configurations"></a><span data-ttu-id="21f98-148">Konfiguracje serwera proxy</span><span class="sxs-lookup"><span data-stu-id="21f98-148">Proxy Configurations</span></span> 

- <span data-ttu-id="21f98-149">Skrypt automatycznej konfiguracji serwera proxy (PAC): plik [PAC](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (otwiera witrynę firmy spoza firmy Microsoft) zawiera funkcję języka JavaScript FindProxyForURL(adres URL, host).</span><span class="sxs-lookup"><span data-stu-id="21f98-149">Proxy Auto-Config (PAC) script: a [PAC file](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (opens a non-Microsoft site) contains a JavaScript function FindProxyForURL(url, host).</span></span> 
- <span data-ttu-id="21f98-150">Statyczny serwer proxy: w postaci Serwer:Port.</span><span class="sxs-lookup"><span data-stu-id="21f98-150">Static Proxy: in the form of Server:Port.</span></span>  
- <span data-ttu-id="21f98-151">Protokół automatycznego odnajdywania serwera proxy sieci Web (WPAD): podaj adres URL pliku konfiguracji serwera proxy za pośrednictwem protokołu DHCP lub DNS.</span><span class="sxs-lookup"><span data-stu-id="21f98-151">Web Proxy Auto-Discovery Protocol (WPAD): provide URL of proxy configuration file through DHCP or DNS.</span></span> 

### <a name="proxy-provisioning-methods"></a><span data-ttu-id="21f98-152">Metody aprowizowania serwera proxy</span><span class="sxs-lookup"><span data-stu-id="21f98-152">Proxy Provisioning Methods</span></span> 
<span data-ttu-id="21f98-153">Istnieją trzy sposoby inicjowania obsługi serwerów proxy:</span><span class="sxs-lookup"><span data-stu-id="21f98-153">There are three ways to provision proxies:</span></span>

 

1.  <span data-ttu-id="21f98-154">**Interfejs użytkownika ustawień:**</span><span class="sxs-lookup"><span data-stu-id="21f98-154">**Settings UI:**</span></span> 
    1. <span data-ttu-id="21f98-155">Serwer proxy dla użytkownika (20H2 lub starsze):</span><span class="sxs-lookup"><span data-stu-id="21f98-155">Per-user proxy (20H2 or earlier):</span></span>
        1. <span data-ttu-id="21f98-156">Otwórz okno menu Start i wybierz pozycję Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="21f98-156">Open the Start menu and select Settings.</span></span>
        2. <span data-ttu-id="21f98-157">Wybierz pozycję Sieć & Internet, a następnie pozycję Serwer proxy w menu po lewej stronie.</span><span class="sxs-lookup"><span data-stu-id="21f98-157">Select Network & Internet and then Proxy on the left menu.</span></span>
        3. <span data-ttu-id="21f98-158">Przewiń w dół do ustawienia Ręczne konfigurowanie serwera proxy i przełącz ustawienie Użyj serwera proxy na Wł.</span><span class="sxs-lookup"><span data-stu-id="21f98-158">Scroll down to Manual proxy setup and toggle Use a proxy server to On.</span></span>
        4. <span data-ttu-id="21f98-159">Wprowadź adres IP serwera proxy.</span><span class="sxs-lookup"><span data-stu-id="21f98-159">Enter the IP address of the proxy server.</span></span>
        5. <span data-ttu-id="21f98-160">Wprowadź numer portu.</span><span class="sxs-lookup"><span data-stu-id="21f98-160">Enter the port number.</span></span>
        6. <span data-ttu-id="21f98-161">Kliknij pozycję Zapisz.</span><span class="sxs-lookup"><span data-stu-id="21f98-161">Click Save.</span></span>
      1. <span data-ttu-id="21f98-162">Serwer proxy sieci Wi-Fi (21H1 lub wyższy):</span><span class="sxs-lookup"><span data-stu-id="21f98-162">WiFi proxy (21H1 or higher):</span></span>
          1. <span data-ttu-id="21f98-163">Otwórz menu Start i przejdź do Wi-Fi właściwości sieci.</span><span class="sxs-lookup"><span data-stu-id="21f98-163">Open the Start menu and go to your Wi-Fi Network’s Properties page.</span></span>
          1. <span data-ttu-id="21f98-164">Przewiń w dół do serwera proxy</span><span class="sxs-lookup"><span data-stu-id="21f98-164">Scroll down to Proxy</span></span>
          1. <span data-ttu-id="21f98-165">Zmiana na konfigurację ręczną</span><span class="sxs-lookup"><span data-stu-id="21f98-165">Change to Manual Setup</span></span>
          1. <span data-ttu-id="21f98-166">Wprowadź adres IP serwera proxy.</span><span class="sxs-lookup"><span data-stu-id="21f98-166">Enter the IP address of the proxy server.</span></span>
          1. <span data-ttu-id="21f98-167">Wprowadź numer portu.</span><span class="sxs-lookup"><span data-stu-id="21f98-167">Enter the port number.</span></span>
          1. <span data-ttu-id="21f98-168">Kliknij przycisk Zastosuj.</span><span class="sxs-lookup"><span data-stu-id="21f98-168">Click Apply.</span></span>
        
 2. <span data-ttu-id="21f98-169">**Zarządzanie urządzeniami przenośnymi**</span><span class="sxs-lookup"><span data-stu-id="21f98-169">**MDM**</span></span> 
     1. <span data-ttu-id="21f98-170">Intune — użyj tych [kroków, aby](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) skonfigurować serwer proxy w usłudze Intune.</span><span class="sxs-lookup"><span data-stu-id="21f98-170">Intune - Use these [steps](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) to configure proxy in Intune.</span></span> <span data-ttu-id="21f98-171">Musisz przewinąć w dół sekcji.</span><span class="sxs-lookup"><span data-stu-id="21f98-171">You will need to scroll to the bottom of the section.</span></span>
     1. <span data-ttu-id="21f98-172">Inne rozwiązania MDM innych firm — użyj usługi [CSP sieci Wi-Fi.](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)</span><span class="sxs-lookup"><span data-stu-id="21f98-172">Other 3rd party MDM solutions - Use a [WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp).</span></span>

3. <span data-ttu-id="21f98-173">**PPKG**</span><span class="sxs-lookup"><span data-stu-id="21f98-173">**PPKG**</span></span> 
    1. <span data-ttu-id="21f98-174">Otwórz program Windows Configuration Designer</span><span class="sxs-lookup"><span data-stu-id="21f98-174">Open Windows Configuration Designer</span></span>
    1. <span data-ttu-id="21f98-175">Kliknij pozycję Advanced Provisioning (Aprowizowanie zaawansowane), wprowadź nazwę nowego projektu i kliknij przycisk Next (Dalej).</span><span class="sxs-lookup"><span data-stu-id="21f98-175">Click on Advanced Provisioning, enter the name for your new Project and click Next.</span></span>
    1. <span data-ttu-id="21f98-176">Wybierz pozycję Windows Holographic (HoloLens 2) i kliknij przycisk Dalej.</span><span class="sxs-lookup"><span data-stu-id="21f98-176">Select Windows Holographic (HoloLens 2) and click Next.</span></span>
    1. <span data-ttu-id="21f98-177">Zaimportuj ppkg (opcjonalnie) i kliknij przycisk Zakończ.</span><span class="sxs-lookup"><span data-stu-id="21f98-177">Import your PPKG (optional) and click Finish.</span></span>
    1. <span data-ttu-id="21f98-178">Rozwiń pozycję Ustawienia środowiska > -> -> proxy sieci WLAN.</span><span class="sxs-lookup"><span data-stu-id="21f98-178">Expand Runtime Settings -> Connectivity Profiles -> WLAN -> WLAN Proxy.</span></span>
    1. <span data-ttu-id="21f98-179">Wprowadź wartość SSID sieci Wi-Fi i kliknij przycisk Dodaj.</span><span class="sxs-lookup"><span data-stu-id="21f98-179">Enter the SSID of your Wi-Fi network and click Add.</span></span>
    1. <span data-ttu-id="21f98-180">Wybierz sieć Wi-Fi sieci w oknie po lewej stronie i wprowadź odpowiednie dostosowania.</span><span class="sxs-lookup"><span data-stu-id="21f98-180">Select your Wi-Fi network in the left window and enter your desired customizations.</span></span> <span data-ttu-id="21f98-181">Włączone dostosowania będą wyświetlane pogrubioną czcionką w menu po lewej stronie.</span><span class="sxs-lookup"><span data-stu-id="21f98-181">The enabled customizations will show in bold on the left menu.</span></span>
    1. <span data-ttu-id="21f98-182">Kliknij pozycję Zapisz i zakończ.</span><span class="sxs-lookup"><span data-stu-id="21f98-182">Click Save and Exit.</span></span>
    1. <span data-ttu-id="21f98-183">[Zastosuj](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) pakiet aprowizowania do urządzenia HoloLens.</span><span class="sxs-lookup"><span data-stu-id="21f98-183">[Apply](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) the provisioning package to the HoloLens.</span></span>

<span data-ttu-id="21f98-184">[Dostawcy CSP](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) znajdują się za wieloma zadaniami i zasadami zarządzania dla Windows 10, zarówno w Microsoft Intune, jak i u dostawców usług MDM innych firm.</span><span class="sxs-lookup"><span data-stu-id="21f98-184">[CSPs](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) are behind many of the management tasks and policies for Windows 10, both in Microsoft Intune and in non-Microsoft MDM service providers.</span></span> <span data-ttu-id="21f98-185">Możesz również użyć [projektanta konfiguracji systemu Windows,](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) aby utworzyć pakiet aprowizowania [i](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) zastosować go do urządzenia HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="21f98-185">You can also use [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) to create a [provisioning package](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) and apply it to the HoloLens 2.</span></span>
<span data-ttu-id="21f98-186">Najbardziej prawdopodobne CSP, które zostaną zastosowane do urządzenia HoloLens 2, to:</span><span class="sxs-lookup"><span data-stu-id="21f98-186">The most likely CSPs that will be applied to your HoloLens 2 are:</span></span>

- <span data-ttu-id="21f98-187">[Wi-Fi CSP:](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)per-profile Wi-Fi proxy</span><span class="sxs-lookup"><span data-stu-id="21f98-187">[WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp): per-profile Wi-Fi proxy</span></span> 

[<span data-ttu-id="21f98-188">Inni CSP obsługiwani na urządzeniach HoloLens</span><span class="sxs-lookup"><span data-stu-id="21f98-188">Other CSPs supported in HoloLens devices</span></span>](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a><span data-ttu-id="21f98-189">VPN</span><span class="sxs-lookup"><span data-stu-id="21f98-189">VPN</span></span>
<span data-ttu-id="21f98-190">Połączenie sieci VPN może pomóc zapewnić bezpieczniejsze połączenie i dostęp do sieci firmowej i Internetu.</span><span class="sxs-lookup"><span data-stu-id="21f98-190">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="21f98-191">Urządzenie HoloLens 2 obsługuje wbudowany klient sieci VPN i platforma uniwersalna systemu Windows sieci VPN (UWP).</span><span class="sxs-lookup"><span data-stu-id="21f98-191">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="21f98-192">Obsługiwane wbudowane protokoły sieci VPN:</span><span class="sxs-lookup"><span data-stu-id="21f98-192">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="21f98-193">IKEv2</span><span class="sxs-lookup"><span data-stu-id="21f98-193">IKEv2</span></span>
- <span data-ttu-id="21f98-194">L2TP</span><span class="sxs-lookup"><span data-stu-id="21f98-194">L2TP</span></span>
- <span data-ttu-id="21f98-195">PPTP</span><span class="sxs-lookup"><span data-stu-id="21f98-195">PPTP</span></span>

<span data-ttu-id="21f98-196">Jeśli certyfikat jest używany do uwierzytelniania wbudowanego klienta sieci VPN, wymagany certyfikat klienta należy dodać do magazynu certyfikatów użytkownika.</span><span class="sxs-lookup"><span data-stu-id="21f98-196">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="21f98-197">Aby sprawdzić, czy wtyczka sieci VPN innej firmy obsługuje urządzenie HoloLens 2, przejdź do sklepu, aby zlokalizować aplikację sieci VPN i sprawdzić, czy urządzenie HoloLens jest wymienione jako obsługiwane urządzenie, a na stronie Wymagania systemowe aplikacja obsługuje architekturę ARM lub ARM64.</span><span class="sxs-lookup"><span data-stu-id="21f98-197">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="21f98-198">Urządzenie HoloLens obsługuje tylko platforma uniwersalna systemu Windows sieci VPN innych firm.</span><span class="sxs-lookup"><span data-stu-id="21f98-198">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="21f98-199">Sieć VPN może być zarządzana przez rozwiązanie MDM za [pośrednictwem ustawień/allowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)i ustawiana za pośrednictwem [zasad Vpnv2-csp.](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)</span><span class="sxs-lookup"><span data-stu-id="21f98-199">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="21f98-200">Dowiedz się więcej na [temat konfigurowania sieci VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) za pomocą tych [przewodników.](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)</span><span class="sxs-lookup"><span data-stu-id="21f98-200">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="21f98-201">Sieć VPN za pośrednictwem interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="21f98-201">VPN via UI</span></span>

<span data-ttu-id="21f98-202">Sieć VPN nie jest domyślnie włączona,  ale można ją włączyć ręcznie, otwierając aplikację Ustawienia i przechodząc do opcji **Sieć & Internet — > VPN.**</span><span class="sxs-lookup"><span data-stu-id="21f98-202">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="21f98-203">Wybierz dostawcę sieci VPN.</span><span class="sxs-lookup"><span data-stu-id="21f98-203">Select a VPN provider.</span></span>
1. <span data-ttu-id="21f98-204">Utwórz nazwę połączenia.</span><span class="sxs-lookup"><span data-stu-id="21f98-204">Create a connection name.</span></span> 
1. <span data-ttu-id="21f98-205">Wprowadź nazwę lub adres serwera.</span><span class="sxs-lookup"><span data-stu-id="21f98-205">Enter your server name or address.</span></span>
1. <span data-ttu-id="21f98-206">Wybierz typ sieci VPN.</span><span class="sxs-lookup"><span data-stu-id="21f98-206">Select the VPN type.</span></span>
1. <span data-ttu-id="21f98-207">Wybierz typ informacji logowania.</span><span class="sxs-lookup"><span data-stu-id="21f98-207">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="21f98-208">Opcjonalnie dodaj nazwę użytkownika i hasło.</span><span class="sxs-lookup"><span data-stu-id="21f98-208">Optionally add user name and password.</span></span>
1. <span data-ttu-id="21f98-209">Zastosuj ustawienia sieci VPN.</span><span class="sxs-lookup"><span data-stu-id="21f98-209">Apply the VPN settings.</span></span> 

![Ustawienia sieci VPN urządzenia HoloLens](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="21f98-211">Zestaw sieci VPN za pośrednictwem pakietu aprowizowania</span><span class="sxs-lookup"><span data-stu-id="21f98-211">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="21f98-212">W systemie Windows Holographic w wersji 20H2 rozwiązaliśmy problem z konfiguracją serwera proxy dla połączenia sieci VPN.</span><span class="sxs-lookup"><span data-stu-id="21f98-212">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="21f98-213">Rozważ uaktualnienie urządzeń do tej kompilacji, jeśli zamierzasz używać tego przepływu.</span><span class="sxs-lookup"><span data-stu-id="21f98-213">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="21f98-214">Uruchom program Windows Configuration Designer.</span><span class="sxs-lookup"><span data-stu-id="21f98-214">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="21f98-215">Kliknij pozycję **Provision HoloLens devices (Aprowizuj urządzenia HoloLens),** a następnie wybierz pozycję target device (urządzenie docelowe) i **Next (Dalej).**</span><span class="sxs-lookup"><span data-stu-id="21f98-215">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="21f98-216">Wprowadź nazwę pakietu i ścieżkę.</span><span class="sxs-lookup"><span data-stu-id="21f98-216">Enter package name and path.</span></span>
1. <span data-ttu-id="21f98-217">Kliknij **pozycję Przełącz do edytora zaawansowanego.**</span><span class="sxs-lookup"><span data-stu-id="21f98-217">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="21f98-218">Otwórz **ustawienia środowiska**  ->  **uruchomieniowego ŁącznośćProfile VPN**  ->    ->  **VPNUstawienia**.</span><span class="sxs-lookup"><span data-stu-id="21f98-218">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="21f98-219">Konfigurowanie profilu VPNProfileName</span><span class="sxs-lookup"><span data-stu-id="21f98-219">Configure VPNProfileName</span></span>
1. <span data-ttu-id="21f98-220">Wybierz pozycję ProfileType: **Native** **lub Third Party**.</span><span class="sxs-lookup"><span data-stu-id="21f98-220">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="21f98-221">W przypadku profilu macierzystego wybierz **pozycję NativeProtocolType,** a następnie skonfiguruj serwer, zasady routingu, typ uwierzytelniania i inne ustawienia.</span><span class="sxs-lookup"><span data-stu-id="21f98-221">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="21f98-222">W przypadku profilu "Innej firmy" skonfiguruj adres URL serwera, nazwę rodziny pakietów aplikacji sieci VPN (tylko 3 wstępnie zdefiniowane) i konfiguracje niestandardowe.</span><span class="sxs-lookup"><span data-stu-id="21f98-222">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="21f98-223">Wyeksportuj pakiet.</span><span class="sxs-lookup"><span data-stu-id="21f98-223">Export your package.</span></span>
1. <span data-ttu-id="21f98-224">Podłącz urządzenie HoloLens i skopiuj plik ppkg do urządzenia.</span><span class="sxs-lookup"><span data-stu-id="21f98-224">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="21f98-225">Na urządzeniach HoloLens zastosuj ppkg sieci VPN, otwierając pakiet menu Start i wybierając pozycję Ustawienia Dostęp do konta służbowego Dodaj lub usuń pakiet aprowizowania — > wybierz pakiet  ->    ->    ->   sieci VPN.</span><span class="sxs-lookup"><span data-stu-id="21f98-225">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="21f98-226">Konfigurowanie sieci VPN za pośrednictwem usługi Intune</span><span class="sxs-lookup"><span data-stu-id="21f98-226">Setting up VPN via Intune</span></span>
<span data-ttu-id="21f98-227">Aby rozpocząć pracę, postępuj zgodnie z dokumentami usługi Intune.</span><span class="sxs-lookup"><span data-stu-id="21f98-227">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="21f98-228">Podczas pracy z tymi krokami należy pamiętać o wbudowanych protokołach sieci VPN, które obsługują urządzenia HoloLens.</span><span class="sxs-lookup"><span data-stu-id="21f98-228">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="21f98-229">[Utwórz profile sieci VPN w celu nawiązania połączenia z serwerami sieci VPN w usłudze Intune.](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure)</span><span class="sxs-lookup"><span data-stu-id="21f98-229">[Create VPN profiles to connect to VPN servers in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="21f98-230">[Windows 10 urządzeniach z systemem Windows Holographic, aby dodać połączenia sieci VPN przy użyciu usługi Intune.](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10)</span><span class="sxs-lookup"><span data-stu-id="21f98-230">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="21f98-231">Gdy wszystko będzie gotowe, pamiętaj [o przypisaniu profilu](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span><span class="sxs-lookup"><span data-stu-id="21f98-231">When done please remember to [assign the profile](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="21f98-232">Sieć VPN za pośrednictwem rozwiązań MDM innych firm</span><span class="sxs-lookup"><span data-stu-id="21f98-232">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="21f98-233">Przykład połączenia sieci VPN innej firmy:</span><span class="sxs-lookup"><span data-stu-id="21f98-233">3rd party VPN connection example:</span></span>
```xml
<!-- Configure VPN Server Name or Address (PhoneNumber=) [Comma Separated]-->
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/ServerUrlList</LocURI>
          </Target>
          <Data>selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <!-- Configure VPN Plugin AppX Package ID (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/PluginPackageFamilyName</LocURI>
          </Target>
          <Data>TestVpnPluginApp-SL_8wekyb3d8bbwe</Data>
        </Item>
      </Add>

      <!-- Configure Microsoft's Custom XML (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/CustomConfiguration</LocURI>
          </Target>          <Data><pluginschema><ipAddress>auto</ipAddress><port>443</port><networksettings><routes><includev4><route><address>172.10.10.0</address><prefix>24</prefix></route></includev4></routes><namespaces><namespace><space>.vpnbackend.com</space><dnsservers><server>172.10.10.11</server></dnsservers></namespace></namespaces></networksettings></pluginschema></Data>
        </Item>
      </Add>
```

<span data-ttu-id="21f98-234">Przykład natywnej sieci VPN IKEv2:</span><span class="sxs-lookup"><span data-stu-id="21f98-234">Native IKEv2 VPN example:</span></span>
```xml
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Servers</LocURI>
          </Target>
          <Data>Selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/RoutingPolicyType</LocURI>
          </Target>
          <Data>ForceTunnel</Data>
        </Item>
      </Add>

      <!-- Configure VPN Protocol Type (L2tp, Pptp, Ikev2) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/NativeProtocolType</LocURI>
          </Target>
          <Data>Ikev2</Data>
        </Item>
      </Add>

      <!-- Configure VPN User Method (Mschapv2, Eap) -->
      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/UserMethod</LocURI>
          </Target>
          <Data>Eap</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/Eap/Configuration</LocURI>
          </Target>
          <Data>EAP_configuration_xml_content</Data>
        </Item>
      </Add>
```
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="21f98-235">Wyłączanie Wi-Fi na urządzeniach HoloLens (1. generacja)</span><span class="sxs-lookup"><span data-stu-id="21f98-235">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="21f98-236">Korzystanie z aplikacji Ustawienia na urządzeniach HoloLens</span><span class="sxs-lookup"><span data-stu-id="21f98-236">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="21f98-237">Otwórz menu **Start.**</span><span class="sxs-lookup"><span data-stu-id="21f98-237">Open the **Start** menu.</span></span>
1. <span data-ttu-id="21f98-238">Wybierz aplikację **Ustawienia** z **menu Start** lub z listy **Wszystkie aplikacje** po prawej stronie menu **Start.**</span><span class="sxs-lookup"><span data-stu-id="21f98-238">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="21f98-239">Aplikacja **Ustawienia** zostanie automatycznie umieszczona przed toem.</span><span class="sxs-lookup"><span data-stu-id="21f98-239">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="21f98-240">Wybierz **pozycję Sieć & Internet.**</span><span class="sxs-lookup"><span data-stu-id="21f98-240">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="21f98-241">Wybierz przełącznik Wi-Fi suwaka, aby przenieść go do **pozycji** Wyłączone.</span><span class="sxs-lookup"><span data-stu-id="21f98-241">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="21f98-242">Spowoduje to wyłączenie składników RF przycisku radiowego Wi-Fi i wyłączenie wszystkich Wi-Fi na urządzeniach HoloLens.</span><span class="sxs-lookup"><span data-stu-id="21f98-242">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="21f98-243">Po wyłączeniu Wi-Fi urządzenia HoloLens nie będzie można automatycznie załadować [przestrzeni.](hololens-spaces.md)</span><span class="sxs-lookup"><span data-stu-id="21f98-243">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="21f98-244">Przesuń przełącznik suwaka  do pozycji Wł., aby włączyć przycisk radiowy Wi-Fi i przywrócić Wi-Fi na Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="21f98-244">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="21f98-245">Wybrany stan Wi-Fi radiowego **(Wł.** lub **Wył.)** będzie zachowywany po ponownym uruchomieniu.</span><span class="sxs-lookup"><span data-stu-id="21f98-245">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="21f98-246">Identyfikowanie adresu IP urządzenia HoloLens w sieci Wi-Fi sieci</span><span class="sxs-lookup"><span data-stu-id="21f98-246">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="21f98-247">Za pomocą aplikacji Ustawienia</span><span class="sxs-lookup"><span data-stu-id="21f98-247">By using the Settings app</span></span>

1. <span data-ttu-id="21f98-248">Otwórz menu **Start.**</span><span class="sxs-lookup"><span data-stu-id="21f98-248">Open the **Start** menu.</span></span>
1. <span data-ttu-id="21f98-249">Wybierz aplikację **Ustawienia** z **menu Start** lub z listy **Wszystkie aplikacje** po prawej stronie menu **Start.**</span><span class="sxs-lookup"><span data-stu-id="21f98-249">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="21f98-250">Aplikacja **Ustawienia** zostanie automatycznie umieszczona przed toem.</span><span class="sxs-lookup"><span data-stu-id="21f98-250">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="21f98-251">Wybierz **pozycję Sieć & Internet.**</span><span class="sxs-lookup"><span data-stu-id="21f98-251">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="21f98-252">Przewiń w dół do listy dostępnych sieci Wi-Fi i wybierz pozycję **Właściwości sprzętu.**</span><span class="sxs-lookup"><span data-stu-id="21f98-252">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Właściwości sprzętu w Wi-Fi konfiguracji](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="21f98-254">Adres IP zostanie wyświetlony obok adresu **IPv4.**</span><span class="sxs-lookup"><span data-stu-id="21f98-254">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="21f98-255">Za pomocą poleceń głosowych</span><span class="sxs-lookup"><span data-stu-id="21f98-255">By using voice commands</span></span>

<span data-ttu-id="21f98-256">W zależności od kompilacji urządzeń możesz użyć wbudowanych poleceń głosowych lub Cortany, aby wyświetlić swój adres IP.</span><span class="sxs-lookup"><span data-stu-id="21f98-256">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="21f98-257">W kompilacjach po [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) mówi "What's my IP address?" (Jaki jest mój adres IP?)</span><span class="sxs-lookup"><span data-stu-id="21f98-257">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="21f98-258">Zostanie ona wyświetlona.</span><span class="sxs-lookup"><span data-stu-id="21f98-258">and it will be displayed.</span></span> <span data-ttu-id="21f98-259">W przypadku wcześniejszych kompilacji lub urządzenia HoloLens (1. generacji) powiedz "Hey Cortana, What's my IP address?" (Hej, Cortana, jaki jest mój adres IP?)</span><span class="sxs-lookup"><span data-stu-id="21f98-259">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="21f98-260">Cortana wyświetli i odczyta Twój adres IP.</span><span class="sxs-lookup"><span data-stu-id="21f98-260">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="21f98-261">Przy użyciu Portal urządzeń z systemem Windows</span><span class="sxs-lookup"><span data-stu-id="21f98-261">By using Windows Device Portal</span></span>

1. <span data-ttu-id="21f98-262">W przeglądarce internetowej na komputerze otwórz [portal urządzenia](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="21f98-262">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="21f98-263">Przejdź do **sekcji Sieć.**</span><span class="sxs-lookup"><span data-stu-id="21f98-263">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="21f98-264">W tej sekcji zostanie wyświetlony Twój adres IP i inne informacje o sieci.</span><span class="sxs-lookup"><span data-stu-id="21f98-264">This section displays your IP address and other network information.</span></span> <span data-ttu-id="21f98-265">Za pomocą tej metody można skopiować i wkleić adres IP na komputerze dewelopera.</span><span class="sxs-lookup"><span data-stu-id="21f98-265">By using this method, you can copy and paste of the IP address on your development PC.</span></span>

## <a name="change-ip-address-to-static-address"></a><span data-ttu-id="21f98-266">Zmiana adresu IP na adres statyczny</span><span class="sxs-lookup"><span data-stu-id="21f98-266">Change IP Address to static address</span></span>
### <a name="by-using-settings"></a><span data-ttu-id="21f98-267">Przy użyciu ustawień</span><span class="sxs-lookup"><span data-stu-id="21f98-267">By using Settings</span></span>
 
1. <span data-ttu-id="21f98-268">Otwórz menu **Start.**</span><span class="sxs-lookup"><span data-stu-id="21f98-268">Open the **Start** menu.</span></span>
1. <span data-ttu-id="21f98-269">Wybierz aplikację **Ustawienia** z **menu Start** lub z listy **Wszystkie aplikacje** po prawej stronie menu **Start.**</span><span class="sxs-lookup"><span data-stu-id="21f98-269">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="21f98-270">Aplikacja **Ustawienia** zostanie automatycznie umieszczona przed toem.</span><span class="sxs-lookup"><span data-stu-id="21f98-270">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="21f98-271">Wybierz **pozycję Sieć & Internet.**</span><span class="sxs-lookup"><span data-stu-id="21f98-271">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="21f98-272">Przewiń w dół do listy dostępnych sieci Wi-Fi i wybierz pozycję **Właściwości sprzętu.**</span><span class="sxs-lookup"><span data-stu-id="21f98-272">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>
1. <span data-ttu-id="21f98-273">W **oknie Edytowanie ustawień adresu IP** zmień pierwsze pole na **Ręczne.**</span><span class="sxs-lookup"><span data-stu-id="21f98-273">In the **Edit IP settings** window, change the first field to **Manual**.</span></span>
1. <span data-ttu-id="21f98-274">Wprowadź żądaną konfigurację adresu IP w pozostałych polach, a następnie kliknij przycisk **Zapisz.**</span><span class="sxs-lookup"><span data-stu-id="21f98-274">Input the desired IP configuration in the remaining fields and then click **Save**.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="21f98-275">Przy użyciu Portal urządzeń z systemem Windows</span><span class="sxs-lookup"><span data-stu-id="21f98-275">By using Windows Device Portal</span></span>

1. <span data-ttu-id="21f98-276">W przeglądarce internetowej na komputerze otwórz [portal urządzenia](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="21f98-276">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="21f98-277">Przejdź do **sekcji Sieć.**</span><span class="sxs-lookup"><span data-stu-id="21f98-277">Navigate to the **Networking** section.</span></span>
1. <span data-ttu-id="21f98-278">Wybierz przycisk **Konfiguracja protokołu IPv4.**</span><span class="sxs-lookup"><span data-stu-id="21f98-278">Select the **IPv4 Configuration** button.</span></span>
1. <span data-ttu-id="21f98-279">Wybierz **pozycję Użyj następującego adresu IP** i wprowadź odpowiednią konfigurację protokołu TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="21f98-279">Select **Use the following IP address** and input the desired TCP/IP configuration.</span></span>
1. <span data-ttu-id="21f98-280">Wybierz **pozycję Użyj następujących adresów serwera DNS** i wprowadź preferowane i alternatywne adresy serwerów DNS, jeśli to konieczne.</span><span class="sxs-lookup"><span data-stu-id="21f98-280">Select **Use the following DNS server addresses** and enter the Preferred and Alternate DNS server addresses, if needed.</span></span>
1. <span data-ttu-id="21f98-281">Kliknij pozycję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="21f98-281">Click **Save**.</span></span> 
