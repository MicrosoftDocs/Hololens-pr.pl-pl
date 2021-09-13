---
title: Połączenie HoloLens do sieci
description: Dowiedz się, jak skonfigurować i połączyć się z Internetem za pomocą HoloLens oraz jak zidentyfikować adres IP urządzenia.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, sieć Wi-Fi, sieć bezprzewodowa, Internet, adres IP, adres IP
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: fe1c47de48e413a6f45921ba1e247016873ca996
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036535"
---
# <a name="connect-hololens-to-a-network"></a>Połączenie HoloLens do sieci

Aby wykonać większość czynności na HoloLens, musisz mieć połączenie z siecią. HoloLens zawiera przycisk radiowy z możliwością 802.11ac, 2x2 Wi-Fi i łączenie go z siecią jest podobny do łączenia urządzenia Windows 10 Desktop lub Mobile z siecią Wi-Fi siecią. Ten przewodnik pomoże Ci:

- Połączenie z siecią przy użyciu sieci Wi-Fi lub tylko HoloLens 2, Wi-Fi direct lub Ethernet przez USB-C
- Wyłączanie i ponowne włączanie Wi-Fi

Przeczytaj więcej na temat [korzystania z HoloLens offline.](hololens-offline.md)

## <a name="connecting-for-the-first-time"></a>Nawiązywanie połączenia po raz pierwszy

Przy pierwszym użyciu konta HoloLens zostaniesz pokierować przez proces nawiązywania połączenia z Wi-Fi siecią. Jeśli podczas instalacji masz problemy z nawiązaniem połączenia z usługą Wi-Fi, upewnij się, że twoja sieć jest otwartą siecią chronioną hasłem lub siecią w witrynie Captive Portal. Upewnij się również, że sieć nie wymaga użycia certyfikatu do nawiązania połączenia. Po instalacji możesz połączyć się z innymi typami sieci Wi-Fi sieci.

Na HoloLens 2 użytkownik może również użyć adaptera [USB-C](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) do sieci Ethernet, aby połączyć się bezpośrednio z Wi-Fi, aby pomóc w konfigurowaniu urządzenia. Po skonfigurowaniu urządzenia użytkownik może nadal korzystać z karty lub może odłączyć urządzenie od karty i połączyć się z [siecią Wi-Fi po skonfigurowaniu.](hololens-network.md#connecting-to-wi-fi-after-setup) 

## <a name="connecting-to-wi-fi-after-setup"></a>Nawiązywanie połączenia z Wi-Fi po instalacji

1. Wstępnie sformuj **gest Start** i wybierz **Ustawienia**. Aplikacja Ustawienia zostanie automatycznie umieszczona przed Tomem.
1. Wybierz **pozycję Sieć &**  >  **Wi-Fi.** Upewnij się, że sieć Wi-Fi jest włączona. Jeśli nie widzisz swojej sieci, przewiń listę w dół.
1. Wybierz sieć, a następnie wybierz pozycję **Połączenie**.
1. Jeśli zostanie wyświetlony monit o hasło sieci, wpisz je, a następnie wybierz przycisk **Dalej.**

![HoloLens Wi-Fi ustawienia.](./images/hololens-2-wifi-settings.jpg)

Aby potwierdzić, że masz połączenie z Wi-Fi siecią, sprawdź stan Wi-Fi menu **Start:**

1. Otwórz menu **Start.**
1. W lewym górnym rogu menu **Start** sprawdź stan Wi-Fi Start. Zostanie pokazany stan Wi-Fi i SSID podłączonej sieci.

> [!TIP]
> Jeśli Wi-Fi nie jest dostępny, możesz również połączyć się z sieciami [komórkowymi i 5G.](hololens-cellular.md)

> [!IMPORTANT]
> Domyślnie użytkownicy nie mogą dostosować Wi-Fi mobilnego zachowania usługi HoloLens 2 — jedynym sposobem odświeżania listy Wi-Fi jest przełączenie przełącznika Wi-Fi Wyłączone i **Wł.**. Zapobiega to wielu problemom, takim jak to, że urządzenie może pozostać "zablokowane" dla ap, gdy będzie poza zakresem.

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a>Połączenie HoloLens do Enterprise Wi-Fi Sieci

Enterprise Wi-Fi używają protokołu EAP (Extensible Authentication Protocol) do uwierzytelniania Wi-Fi sieciowych. HoloLens Enterprise Wi-Fi można skonfigurować za pomocą rozwiązania MDM lub pakietu aprowizowania utworzonego przez Windows [Configuration Designer.](/windows/configuration/provisioning-packages/provisioning-packages)

Aby Microsoft Intune zarządzanego urządzenia, zapoznaj się z instrukcjami dotyczącymi konfiguracji w usłudze [Intune.](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)

Aby utworzyć pakiet Wi-Fi aprowizowania w UCD, wymagany jest wstępnie Wi-Fi pliku .xml aprowizowania. Oto przykładowy profil Wi-Fi dla WPA2-Enterprise z uwierzytelnianiem EAP-TLS:

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


W zależności od typu protokołu EAP może być konieczne aprowizowania certyfikatu głównego urzędu certyfikacji serwera i certyfikatu klienta na urządzeniu.

Dodatkowe zasoby:

- Schemat WLANv1Profile: [[MS-GPWL]: profil bezprzewodowej sieci LAN v1 schematu | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- Schemat protokołu EAP-TLS: [[MS-GPWL]: Schemat protokołu TLS protokołu EAP firmy Microsoft | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

Jeśli masz [problemy z nawiązaniem](hololens2-enterprise-troubleshooting.md#) połączenia z siecią Wi-Fi, sprawdź stronę Rozwiązywanie problemów.

## <a name="configure-network-proxy"></a>Konfigurowanie serwera proxy sieci

Ta sekcja obejmuje serwer proxy sieci dla HoloLens systemu operacyjnego i aplikacji platformy uniwersalnej systemu Windows (UWP) przy użyciu Windows stosu HTTP. Aplikacje korzystające z Windows stosu HTTP mogą mieć własną konfigurację i obsługę serwera proxy. 

### <a name="proxy-configurations"></a>Konfiguracje serwera proxy 

- Skrypt automatycznej konfiguracji serwera proxy (PAC): plik [PAC](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (otwiera witrynę firmy spoza firmy Microsoft) zawiera funkcję Języka JavaScript FindProxyForURL(adres URL, host). 
- Statyczny serwer proxy: w postaci Serwer:Port.  
- Protokół automatycznego odnajdywania serwera proxy sieci Web (WPAD): podaj adres URL pliku konfiguracji serwera proxy za pośrednictwem protokołu DHCP lub DNS. 

### <a name="proxy-provisioning-methods"></a>Metody aprowizowania serwera proxy 
Istnieją trzy sposoby inicjowania obsługi serwerów proxy:

 

1.  **Ustawienia INTERFEJSU UŻYTKOWNIKA:** 
    1. Serwer proxy dla użytkownika (20H2 lub starsze):
        1. Otwórz menu Start i wybierz pozycję Ustawienia.
        2. Wybierz pozycję Sieć & Internet, a następnie pozycję Serwer proxy w menu po lewej stronie.
        3. Przewiń w dół do ustawienia Ręczne konfigurowanie serwera proxy i przełącz ustawienie Użyj serwera proxy na Wł.
        4. Wprowadź adres IP serwera proxy.
        5. Wprowadź numer portu.
        6. Kliknij pozycję Zapisz.
      1. Serwer proxy sieci Wi-Fi (21H1 lub wyższy):
          1. Otwórz menu Start i przejdź do Wi-Fi właściwości sieci wirtualnej.
          1. Przewiń w dół do serwera proxy
          1. Zmiana na konfigurację ręczną
          1. Wprowadź adres IP serwera proxy.
          1. Wprowadź numer portu.
          1. Kliknij przycisk Zastosuj.
        
 2. **Zarządzanie urządzeniami przenośnymi** 
     1. Intune — użyj tych [kroków, aby](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) skonfigurować serwer proxy w usłudze Intune. Musisz przewinąć do dołu sekcji.
     1. Inne rozwiązania MDM innych firm — użyj usługi [CSP sieci Wi-Fi.](/windows/client-management/mdm/wifi-csp)

3. **PpKG** 
    1. Otwórz Windows Configuration Designer
    1. Kliknij pozycję Advanced Provisioning (Aprowizowanie zaawansowane), wprowadź nazwę nowej Project kliknij przycisk Next (Dalej).
    1. Wybierz Windows Holographic (HoloLens 2) i kliknij przycisk Dalej.
    1. Zaimportuj ppkg (opcjonalnie) i kliknij przycisk Zakończ.
    1. Rozwiń w Ustawienia -> profilów łączności -> sieci WLAN -> proxy sieci WLAN.
    1. Wprowadź wartość SSID sieci Wi-Fi a następnie kliknij przycisk Dodaj.
    1. Wybierz sieć Wi-Fi w oknie po lewej stronie i wprowadź odpowiednie dostosowania. Włączone dostosowania będą wyświetlane pogrubioną czcionką w menu po lewej stronie.
    1. Kliknij pozycję Zapisz i zakończ.
    1. [Zastosuj](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) pakiet aprowizowania do HoloLens.

[Dostawcy CSP](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) są za wieloma zadaniami zarządzania i zasadami dla Windows 10, zarówno w Microsoft Intune, jak i u dostawców usług MDM innych firm. Możesz również użyć [Windows Configuration Designer,](/windows/configuration/provisioning-packages/provisioning-install-icd) aby utworzyć pakiet aprowizowania i zastosować go do HoloLens 2. [](/windows/configuration/provisioning-packages/provisioning-packages)
Najbardziej prawdopodobne są CSP, które zostaną zastosowane do Twojego HoloLens 2:

- [Wi-Fi CSP:](/windows/client-management/mdm/wifi-csp)per-profile Wi-Fi proxy 

[Inni CSP obsługiwani na urządzeniach HoloLens mobilnych](/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a>VPN
Połączenie sieci VPN może pomóc zapewnić bezpieczniejsze połączenie i dostęp do sieci firmowej i Internetu. HoloLens 2 obsługuje wbudowanego klienta sieci VPN i wtyczkę sieci VPN Windows Platform (UWP). 

Obsługiwane wbudowane protokoły sieci VPN:
- IKEv2
- L2TP
- PPTP

Jeśli certyfikat jest używany do uwierzytelniania wbudowanego klienta sieci VPN, wymagany certyfikat klienta należy dodać do magazynu certyfikatów użytkownika. Aby sprawdzić, czy wtyczka sieci VPN innej firmy obsługuje usługę HoloLens 2, przejdź do sklepu, aby zlokalizować aplikację sieci VPN i sprawdzić, czy usługa HoloLens jest wymieniona jako obsługiwane urządzenie, a na stronie Wymagania systemowe aplikacja obsługuje architekturę ARM lub ARM64. HoloLens obsługuje tylko aplikacje platformy universal Windows Platform dla sieci VPN innych firm.

 Sieć VPN może być zarządzana przez rozwiązanie MDM za [pośrednictwem sieci Ustawienia/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)i ustawiana za pośrednictwem [zasad Vpnv2-csp.](/windows/client-management/mdm/vpnv2-csp)

Dowiedz się więcej na [temat konfigurowania sieci VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) za pomocą tych [przewodników.](/windows/security/identity-protection/vpn/vpn-guide)  

### <a name="vpn-via-ui"></a>Sieć VPN za pośrednictwem interfejsu użytkownika

Sieć VPN nie jest domyślnie włączona, ale można ją włączyć ręcznie, otwierając aplikację Ustawienia **i** przechodząc do opcji Sieć & Internet **> VPN.**
1. Wybierz dostawcę sieci VPN.
1. Utwórz nazwę połączenia. 
1. Wprowadź nazwę lub adres serwera.
1. Wybierz typ sieci VPN.
1. Wybierz typ informacji logowania. 
1. Opcjonalnie dodaj nazwę użytkownika i hasło.
1. Zastosuj ustawienia sieci VPN. 

![HoloLens Ustawienia sieci VPN.](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a>Zestaw sieci VPN za pośrednictwem pakietu aprowizowania

> [!TIP] 
> W naszym Windows Holographic w wersji 20H2 rozwiązaliśmy problem z konfiguracją serwera proxy dla połączenia sieci VPN. Rozważ uaktualnienie urządzeń do tej kompilacji, jeśli zamierzasz używać tego przepływu.

1. Uruchom Windows Configuration Designer.
1. Kliknij **pozycję Aprowizuj HoloLens,** a następnie wybierz pozycję urządzenie docelowe i **pozycję Dalej.**
1. Wprowadź nazwę i ścieżkę pakietu.
1. Kliknij **pozycję Przełącz do edytora zaawansowanego.**
1. Otwórz **ustawienia środowiska**  ->  **uruchomieniowego ConnectivityProfiles**  ->  **VPN**  ->  **VPNUstawienia**.
1. Konfigurowanie pliku VPNProfileName
1. Wybierz pozycję ProfileType: **Native** **lub Third Party**.
    1. W przypadku profilu macierzystego wybierz **pozycję NativeProtocolType,** a następnie skonfiguruj serwer, zasady routingu, typ uwierzytelniania i inne ustawienia.
    1. W przypadku profilu "Innej firmy" skonfiguruj adres URL serwera, nazwę rodziny pakietów aplikacji sieci VPN (tylko 3 wstępnie zdefiniowane) i konfiguracje niestandardowe.
1. Wyeksportuj pakiet.
1. Połączenie swój HoloLens i skopiuj plik ppkg na urządzenie. 
1. Na HoloLens sieci VPN zastosuj ppkg sieci VPN, otwierając pakiet menu Start i wybierając pozycję **Ustawienia**  ->  **Account**  ->  **Access work or school** Add or remove  ->  **provisioning package** -> Select your VPN package (Dodaj lub usuń pakiet aprowizowania —> Wybierz pakiet sieci VPN).


### <a name="setting-up-vpn-via-intune"></a>Konfigurowanie sieci VPN za pośrednictwem usługi Intune
Aby rozpocząć pracę, postępuj zgodnie z dokumentami usługi Intune. Podczas pracy z tymi krokami należy pamiętać o wbudowanych protokołach sieci VPN, które HoloLens urządzenia. 

[Utwórz profile sieci VPN w celu nawiązania połączenia z serwerami sieci VPN w usłudze Intune.](/mem/intune/configuration/vpn-settings-configure)

[Windows 10 i Windows urządzenia Holographic, aby dodać](/mem/intune/configuration/vpn-settings-windows-10)połączenia sieci VPN przy użyciu usługi Intune.

Gdy wszystko będzie gotowe, [pamiętaj o przypisaniu profilu](/mem/intune/configuration/device-profile-assign).

### <a name="vpn-via-3rd-party-mdm-solutions"></a>Sieć VPN za pośrednictwem rozwiązań MDM innych firm
Przykład połączenia sieci VPN innej firmy:
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

Przykład natywnej sieci VPN ZKEv2:
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a>Wyłączanie Wi-Fi na HoloLens (1. generacja)

### <a name="using-the-settings-app-on-hololens"></a>Używanie aplikacji Ustawienia na HoloLens

1. Otwórz menu **Start.**
1. Wybierz aplikację **Ustawienia** **startową** lub z listy **Wszystkie aplikacje** po prawej stronie menu **Start.** Aplikacja **Ustawienia** zostanie automatycznie umieszczona przed toem.
1. Wybierz **pozycję Sieć & Internet.**
1. Wybierz przełącznik Wi-Fi, aby przenieść go do **pozycji Wyłączone.** Spowoduje to wyłączenie składników RF przycisku radiowego Wi-Fi i wyłączenie wszystkich funkcji Wi-Fi na HoloLens.

    > [!WARNING]
    > Po wyłączeniu Wi-Fi radiowego HoloLens nie będzie można automatycznie załadować [przestrzeni.](hololens-spaces.md)

1. Przesuń przełącznik suwaka  do pozycji Wł., aby włączyć przycisk radiowy Wi-Fi i przywrócić Wi-Fi na Microsoft HoloLens. Wybrany stan Wi-Fi radiowego **(Wł.** lub **Wył.)** będzie zachowywany po ponownym uruchomieniu.

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a>Identyfikowanie adresu IP HoloLens sieci Wi-Fi sieci

### <a name="by-using-the-settings-app"></a>Przy użyciu Ustawienia aplikacji

1. Otwórz menu **Start.**
1. Wybierz aplikację **Ustawienia** **startową** lub z listy **Wszystkie aplikacje** po prawej stronie menu **Start.** Aplikacja **Ustawienia** zostanie automatycznie umieszczona przed toem.
1. Wybierz **pozycję Sieć & Internet.**
1. Przewiń w dół do poniżej listy dostępnych sieci Wi-Fi i wybierz pozycję **Właściwości sprzętu.**

    ![Właściwości sprzętu w Wi-Fi ustawień.](./images/wifi-hololens-hwdetails.jpg)

   Adres IP zostanie wyświetlony obok adresu **IPv4.**

### <a name="by-using-voice-commands"></a>Za pomocą poleceń głosowych

W zależności od kompilacji urządzeń możesz użyć wbudowanych poleceń głosowych lub Cortana do wyświetlania adresu IP. W kompilacjach po [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) mówi "What's my IP address?" (Jaki jest mój adres IP?) Zostanie ona wyświetlona. W przypadku wcześniejszych kompilacji lub HoloLens (1. generacja) powiedz "Hey Cortana, What's my IP address?" (Jaki jest mój adres IP?) i Cortana wyświetli i odczyta Twój adres IP.

### <a name="by-using-windows-device-portal"></a>Przy użyciu Windows Portal urządzeń

1. W przeglądarce internetowej na komputerze otwórz [portal urządzeń](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Przejdź do **sekcji Sieć.**  
   W tej sekcji zostanie wyświetlony Adres IP i inne informacje o sieci. Za pomocą tej metody można skopiować i wkleić adres IP na komputerze dewelopera.

## <a name="change-ip-address-to-static-address"></a>Zmiana adresu IP na adres statyczny
### <a name="by-using-settings"></a>Przy użyciu Ustawienia
 
1. Otwórz menu **Start.**
1. Wybierz aplikację **Ustawienia** **startową** lub z listy **Wszystkie aplikacje** po prawej stronie menu **Start.** Aplikacja **Ustawienia** zostanie automatycznie umieszczona przed toem.
1. Wybierz **pozycję Sieć & Internet.**
1. Przewiń w dół do poniżej listy dostępnych sieci Wi-Fi i wybierz pozycję **Właściwości sprzętu.**
1. W **oknie Edytowanie ustawień adresu IP** zmień pierwsze pole na **Ręczne.**
1. Wprowadź żądaną konfigurację adresu IP w pozostałych polach, a następnie kliknij przycisk **Zapisz.**

### <a name="by-using-windows-device-portal"></a>Przy użyciu Windows Portal urządzeń

1. W przeglądarce internetowej na komputerze otwórz [portal urządzeń](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Przejdź do **sekcji Sieć.**
1. Wybierz przycisk **Konfiguracja protokołu IPv4.**
1. Wybierz **pozycję Użyj następującego adresu IP** i wprowadź odpowiednią konfigurację protokołu TCP/IP.
1. Wybierz **pozycję Użyj następujących adresów serwerów DNS** i w razie potrzeby wprowadź preferowane i alternatywne adresy serwerów DNS.
1. Kliknij pozycję **Zapisz**. 
