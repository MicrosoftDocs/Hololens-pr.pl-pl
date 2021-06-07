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
ms.openlocfilehash: d68c75dcb2249a67f2e07c77cb1b69997eb0ae72
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379748"
---
# <a name="connect-hololens-to-a-network"></a>Łączenie urządzenia HoloLens z siecią

Aby wykonać większość czynności na urządzeniach HoloLens, musisz mieć połączenie z siecią. Urządzenie HoloLens zawiera przycisk radiowy 2x2 Wi-Fi z możliwością 802.11ac, a połączenie z siecią jest podobne do łączenia urządzenia Windows 10 Desktop lub Mobile z Wi-Fi siecią. Ten przewodnik pomoże Ci:

- Nawiązywanie połączenia z siecią przy użyciu sieci Wi-Fi lub tylko dla urządzenia HoloLens 2 Wi-Fi direct lub Ethernet za pośrednictwem portu USB-C
- Wyłączanie i ponowne włączanie Wi-Fi

Przeczytaj więcej na temat [korzystania z urządzenia HoloLens w trybie offline.](hololens-offline.md)

## <a name="connecting-for-the-first-time"></a>Nawiązywanie połączenia po raz pierwszy

Przy pierwszym użyciu urządzenia HoloLens zostaniesz poprowadzenie przez proces nawiązywania połączenia z Wi-Fi siecią. Jeśli podczas instalacji masz problemy z nawiązaniem połączenia Wi-Fi, upewnij się, że sieć jest siecią otwartą, chronioną hasłem lub siecią w witrynie Captive Portal. Upewnij się również, że sieć nie wymaga używania certyfikatu do nawiązywania połączenia. Po zakończeniu instalacji możesz połączyć się z innymi typami sieci Wi-Fi sieci.

Na urządzeniach HoloLens 2 użytkownik może również użyć adaptera [USB-C](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) do sieci Ethernet, aby połączyć się bezpośrednio z Wi-Fi, aby pomóc w konfigurowaniu urządzenia. Po skonfigurowaniu urządzenia użytkownik może nadal korzystać z karty lub może odłączyć urządzenie od karty i połączyć się [z siecią Wi-Fi po skonfigurowaniu.](hololens-network.md#connecting-to-wi-fi-after-setup) 

## <a name="connecting-to-wi-fi-after-setup"></a>Nawiązywanie połączenia Wi-Fi po instalacji

1. Wstępnie sformuj **gest Start i** wybierz pozycję **Ustawienia.** Aplikacja Ustawienia zostanie automatycznie umieszczona przed toem.
1. Wybierz **pozycję Sieć &**  >  **Wi-Fi.** Upewnij się, że sieć Wi-Fi jest włączona. Jeśli nie widzisz swojej sieci, przewiń listę w dół.
1. Wybierz sieć, a następnie wybierz pozycję **Połącz.**
1. Jeśli zostanie wyświetlony monit o hasło sieciowe, wpisz je, a następnie wybierz przycisk **Dalej.**

![Ustawienia Wi-Fi urządzenia HoloLens](./images/hololens-2-wifi-settings.jpg)

Aby potwierdzić, że masz połączenie z Wi-Fi siecią, sprawdź stan Wi-Fi menu **Start:**

1. Otwórz menu **Start.**
1. Sprawdź, czy w lewym górnym rogu menu **Start** Wi-Fi stan. Zostaną wyświetlone Wi-Fi i SSID połączonej sieci.

> [!TIP]
> Jeśli Wi-Fi jest niedostępny, możesz również połączyć się z sieciami [komórkowymi i 5G.](https://docs.microsoft.com/hololens/hololens-cellular)

> [!IMPORTANT]
> Domyślnie użytkownicy nie mogą dostosować zachowania mobilnego urządzenia HoloLens 2 Wi-Fi — jedynym sposobem odświeżenia listy Wi-Fi jest przełączenie przełącznika Wi-Fi Wyłączone i **Wł.**. Zapobiega to wielu problemom, takim jak to, że urządzenie może pozostać "zablokowane" w ap, gdy będzie poza zakresem.

## <a name="troubleshooting-your-connection-to-wi-fi"></a>Rozwiązywanie problemów z połączeniem z Wi-Fi

Jeśli wystąpią problemy z nawiązywaniem połączenia z siecią Wi-Fi, zobacz Nie można [nawiązać połączenia z siecią Wi-Fi.](./hololens-faq.md#i-cant-connect-to-wi-fi)

Po zalogowaniu się do konta przedsiębiorstwa lub organizacji na urządzeniu może również zostać stosowane zasady usługi Mobile Zarządzanie urządzeniami (MDM), jeśli zasady zostały skonfigurowane przez administratora IT.

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a>Łączenie urządzenia HoloLens z usługą Enterprise Wi-Fi Network

Profile Wi-Fi przedsiębiorstwa używają protokołu uwierzytelniania rozszerzanego (EAP, Extensible Authentication Protocol) do uwierzytelniania Wi-Fi połączeń. Profil urządzenia HoloLens Enterprise Wi-Fi można skonfigurować za pomocą rozwiązania MDM lub pakietu aprowizowania utworzonego przez program [Windows Configuration Designer.](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)

Aby Microsoft Intune zarządzanego urządzenia, zapoznaj się z instrukcjami dotyczącymi konfiguracji usługi [Intune.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)

Aby utworzyć pakiet Wi-Fi aprowizowania w UCD, wymagany jest wstępnie skonfigurowany Wi-Fi .xml aprowizowania. Oto przykładowy profil Wi-Fi dla WPA2-Enterprise z uwierzytelnianiem EAP-TLS:

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

- Schemat WLANv1Profile: [[MS-GPWL]: profil bezprzewodowej sieci LAN w wersji 1 | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- Schemat protokołu EAP-TLS: [[MS-GPWL]: Schemat protokołu TLS protokołu EAP firmy Microsoft | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

## <a name="eap-troubleshooting"></a>Rozwiązywanie problemów z protokołu EAP
> [!TIP]
> Większość problemów z siecią wynika z tego, że jedno z poniższych 3 ustawień jest niepoprawne w profilu sieci Wi-FI. 
1. Sprawdź, Wi-Fi profil ma odpowiednie ustawienia:
   1. Typ protokołu EAP jest poprawnie skonfigurowany, typowe typy protokołu EAP: EAP-TLS (13), EAP-TTLS (21) i PEAP (25).
   1. Wi-Fi SSID jest właściwa i pasuje do ciągu HEX.
   1. W przypadku protokołu EAP-TLS wartość TrustedRootCA zawiera skrót SHA-1 serwera&#39;certyfikatu zaufanego głównego urzędu certyfikacji. Na komputerze zcertutil.exe z systemem Windows polecenie -dump nazwa pliku certyfikatu spowoduje pokazanie certyfikatu&#39;ciągu skrótu &quot; \_ \_ &quot; SHA-1.

2. Zbierz przechwytywanie pakietów sieciowych w dziennikach punktu dostępu, kontrolera lub serwera usługi AAA, aby dowiedzieć się, gdzie sesja protokołu EAP kończy się niepowodzeniem.
   1. Jeśli tożsamość protokołu EAP dostarczana przez urządzenie HoloLens nie jest oczekiwana, sprawdź, czy tożsamość została poprawnie aprowizowana za pośrednictwem Wi-Fi lub certyfikatu klienta.
   1. Jeśli serwer odrzuci certyfikat klienta urządzenia HoloLens, sprawdź, czy wymagany certyfikat klienta został aprowowany na urządzeniu.
   1. Jeśli urządzenie HoloLens odrzuca certyfikat serwera, sprawdź, czy certyfikat głównego urzędu certyfikacji serwera został aprowizowany na urządzeniach HoloLens.
1. Jeśli profil przedsiębiorstwa jest aprowowany za pośrednictwem Wi-Fi aprowizowania, rozważ zastosowanie pakietu aprowizowania na Windows 10 PC. Jeśli na komputerze nie powiedzie się Windows 10, postępuj zgodnie z przewodnikiem rozwiązywania problemów z uwierzytelnianiem klienta [systemu Windows 802.1X.](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication)
1. Ustaw telemetrię na wartość Pełna lub Opcjonalna (w zależności od kompilacji), a następnie wyślij nam swoją opinię za [pośrednictwem Centrum opinii](https://docs.microsoft.com/hololens/hololens-feedback).

### <a name="additional-resources"></a>Dodatkowe zasoby:
- [Eksportowanie ustawień sieci Wi-Fi z urządzenia z systemem Windows](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## <a name="configure-network-proxy"></a>Konfigurowanie serwera proxy sieci

Ta sekcja obejmuje serwer proxy sieci dla systemu operacyjnego HoloLens i platforma uniwersalna systemu Windows (UWP) przy użyciu stosu HTTP systemu Windows. Aplikacje korzystające ze stosu HTTP systemu innych niż Windows mogą mieć własną konfigurację i obsługę serwera proxy. 

### <a name="proxy-configurations"></a>Konfiguracje serwera proxy 

- Skrypt automatycznej konfiguracji serwera proxy (PAC): plik [PAC](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (otwiera witrynę firmy spoza firmy Microsoft) zawiera funkcję języka JavaScript FindProxyForURL(adres URL, host). 
- Statyczny serwer proxy: w postaci Serwer:Port.  
- Protokół autowykrywania serwera proxy sieci Web (WPAD): podaj adres URL pliku konfiguracji serwera proxy za pośrednictwem protokołu DHCP lub DNS. 

### <a name="proxy-provisioning-methods"></a>Metody aprowizowania serwera proxy 
Istnieją trzy sposoby inicjowania obsługi serwerów proxy:

 

1.  **Interfejs użytkownika ustawień:** 
    1. Serwer proxy dla użytkownika (20H2 lub starsze):
        1. Otwórz okno menu Start i wybierz pozycję Ustawienia.
        2. Wybierz pozycję Sieć & Internet, a następnie pozycję Serwer proxy w menu po lewej stronie.
        3. Przewiń w dół do ustawienia Ręczne konfigurowanie serwera proxy i przełącz ustawienie Użyj serwera proxy na Wł.
        4. Wprowadź adres IP serwera proxy.
        5. Wprowadź numer portu.
        6. Kliknij pozycję Zapisz.
      1. Serwer proxy sieci Wi-Fi (21H1 lub wyższy):
          1. Otwórz menu Start i przejdź do Wi-Fi właściwości sieci.
          1. Przewiń w dół do serwera proxy
          1. Zmiana na konfigurację ręczną
          1. Wprowadź adres IP serwera proxy.
          1. Wprowadź numer portu.
          1. Kliknij przycisk Zastosuj.
        
 2. **Zarządzanie urządzeniami przenośnymi** 
     1. Intune — użyj tych [kroków, aby](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) skonfigurować serwer proxy w usłudze Intune. Musisz przewinąć w dół sekcji.
     1. Inne rozwiązania MDM innych firm — użyj sieci [Wi-Fi CSP.](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)

3. **PPKG** 
    1. Otwórz program Windows Configuration Designer
    1. Kliknij pozycję Advanced Provisioning (Aprowizowanie zaawansowane), wprowadź nazwę nowego projektu i kliknij przycisk Next (Dalej).
    1. Wybierz pozycję Windows Holographic (HoloLens 2) i kliknij przycisk Dalej.
    1. Zaimportuj ppkg (opcjonalnie) i kliknij przycisk Zakończ.
    1. Rozwiń pozycję Ustawienia środowiska > -> -> proxy sieci WLAN.
    1. Wprowadź wartość SSID sieci Wi-Fi i kliknij przycisk Dodaj.
    1. Wybierz sieć Wi-Fi sieci w oknie po lewej stronie i wprowadź odpowiednie dostosowania. Włączone dostosowania będą wyświetlane pogrubioną czcionką w menu po lewej stronie.
    1. Kliknij pozycję Zapisz i zakończ.
    1. [Zastosuj](https://docs.microsoft.com/hololens/hololens-provisioning#applyremove-a-provisioning-package-to-hololens-after-setup) pakiet aprowizowania do urządzenia HoloLens.

[Dostawcy CSP](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) znajdują się za wieloma zadaniami i zasadami zarządzania dla Windows 10, zarówno w Microsoft Intune, jak i u dostawców usług mdm firmy Microsoft. Możesz również użyć [projektanta konfiguracji systemu Windows,](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) aby utworzyć pakiet aprowizowania [i](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) zastosować go do urządzenia HoloLens 2.
Najbardziej prawdopodobni CSP, którzy zostaną zastosowani do urządzenia HoloLens 2, to:

- [Wi-Fi CSP:](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)per-profile Wi-Fi proxy 

[Inni CSP obsługiwani na urządzeniach HoloLens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a>VPN
Połączenie sieci VPN może pomóc zapewnić bezpieczniejsze połączenie i dostęp do sieci firmowej i Internetu. Urządzenie HoloLens 2 obsługuje wbudowany klient sieci VPN i platforma uniwersalna systemu Windows sieci VPN (UWP). 

Obsługiwane wbudowane protokoły sieci VPN:
- IKEv2
- L2TP
- PPTP

Jeśli certyfikat jest używany do uwierzytelniania wbudowanego klienta sieci VPN, wymagany certyfikat klienta należy dodać do magazynu certyfikatów użytkownika. Aby sprawdzić, czy wtyczka sieci VPN innej firmy obsługuje urządzenie HoloLens 2, przejdź do sklepu, aby zlokalizować aplikację sieci VPN i sprawdzić, czy urządzenie HoloLens jest wymienione jako obsługiwane urządzenie, a na stronie Wymagania systemowe aplikacja obsługuje architekturę ARM lub ARM64. Urządzenie HoloLens obsługuje tylko platforma uniwersalna systemu Windows sieci VPN innych firm.

 Sieć VPN może być zarządzana przez rozwiązanie MDM za [pośrednictwem ustawień/allowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)i ustawiana za pośrednictwem [zasad Vpnv2-csp.](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)

Dowiedz się więcej na [temat konfigurowania sieci VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) za pomocą tych [przewodników.](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)  

### <a name="vpn-via-ui"></a>Sieć VPN za pośrednictwem interfejsu użytkownika

Sieć VPN nie jest domyślnie włączona,  ale można ją włączyć ręcznie, otwierając aplikację Ustawienia i przechodząc do opcji **Sieć & Internet — > VPN.**
1. Wybierz dostawcę sieci VPN.
1. Utwórz nazwę połączenia. 
1. Wprowadź nazwę lub adres serwera.
1. Wybierz typ sieci VPN.
1. Wybierz typ informacji logowania. 
1. Opcjonalnie dodaj nazwę użytkownika i hasło.
1. Zastosuj ustawienia sieci VPN. 

![Ustawienia sieci VPN urządzenia HoloLens](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a>Zestaw sieci VPN za pośrednictwem pakietu aprowizowania

> [!TIP] 
> W systemie Windows Holographic w wersji 20H2 rozwiązaliśmy problem z konfiguracją serwera proxy dla połączenia sieci VPN. Rozważ uaktualnienie urządzeń do tej kompilacji, jeśli zamierzasz używać tego przepływu.

1. Uruchom program Windows Configuration Designer.
1. Kliknij pozycję **Provision HoloLens devices (Aprowizuj urządzenia HoloLens),** a następnie wybierz pozycję target device (urządzenie docelowe) i **Next (Dalej).**
1. Wprowadź nazwę i ścieżkę pakietu.
1. Kliknij **pozycję Przełącz do edytora zaawansowanego.**
1. Otwórz **ustawienia środowiska**  ->  **uruchomieniowego ŁącznośćProfile VPN**  ->    ->  **VPNUstawienia**.
1. Konfigurowanie pliku VPNProfileName
1. Wybierz pozycję ProfileType: **Native** **lub Third Party**.
    1. W przypadku profilu macierzystego wybierz **pozycję NativeProtocolType,** a następnie skonfiguruj serwer, zasady routingu, typ uwierzytelniania i inne ustawienia.
    1. W przypadku profilu "Innej firmy" skonfiguruj adres URL serwera, nazwę rodziny pakietów aplikacji sieci VPN (tylko 3 wstępnie zdefiniowane) i konfiguracje niestandardowe.
1. Wyeksportuj pakiet.
1. Podłącz urządzenie HoloLens i skopiuj plik ppkg do urządzenia. 
1. Na urządzeniach HoloLens zastosuj ppkg sieci VPN, otwierając pakiet menu Start i wybierając pozycję Ustawienia Dostęp do konta służbowego Dodaj lub usuń pakiet aprowizowania — > wybierz pakiet  ->    ->    ->   sieci VPN.


### <a name="setting-up-vpn-via-intune"></a>Konfigurowanie sieci VPN za pośrednictwem usługi Intune
Aby rozpocząć pracę, postępuj zgodnie z dokumentami usługi Intune. Podczas pracy z tymi krokami należy pamiętać o wbudowanych protokołach sieci VPN, które obsługują urządzenia HoloLens. 

[Utwórz profile sieci VPN w celu nawiązania połączenia z serwerami sieci VPN w usłudze Intune.](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure)

[Windows 10 urządzeniach z systemem Windows Holographic, aby dodać połączenia sieci VPN przy użyciu usługi Intune.](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10)

Gdy wszystko będzie gotowe, pamiętaj o [przypisaniu profilu](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).

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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a>Wyłączanie Wi-Fi na urządzeniach HoloLens (1. generacja)

### <a name="using-the-settings-app-on-hololens"></a>Korzystanie z aplikacji Ustawienia na urządzeniach HoloLens

1. Otwórz menu **Start.**
1. Wybierz aplikację **Ustawienia** z **menu Start** lub z listy **Wszystkie aplikacje** po prawej stronie menu **Start.** Aplikacja **Ustawienia** zostanie automatycznie umieszczona przed toem.
1. Wybierz **pozycję Sieć & Internet.**
1. Wybierz przełącznik Wi-Fi suwaka, aby przenieść go do **pozycji** Wyłączone. Spowoduje to wyłączenie składników RF przycisku radiowego Wi-Fi i wyłączenie wszystkich Wi-Fi na urządzeniach HoloLens.

    > [!WARNING]
    > Po wyłączeniu Wi-Fi urządzenia HoloLens nie będzie można automatycznie załadować [przestrzeni.](hololens-spaces.md)

1. Przesuń przełącznik suwaka  do pozycji Wł., aby włączyć przycisk radiowy Wi-Fi i przywrócić Wi-Fi na Microsoft HoloLens. Wybrany stan Wi-Fi radiowego **(Wł.** lub **Wył.)** będzie zachowywany po ponownym uruchomieniu.

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a>Identyfikowanie adresu IP urządzenia HoloLens w sieci Wi-Fi sieci

### <a name="by-using-the-settings-app"></a>Za pomocą aplikacji Ustawienia

1. Otwórz menu **Start.**
1. Wybierz aplikację **Ustawienia** z **menu Start** lub z listy **Wszystkie aplikacje** po prawej stronie menu **Start.** Aplikacja **Ustawienia** zostanie automatycznie umieszczona przed toem.
1. Wybierz **pozycję Sieć & Internet.**
1. Przewiń w dół do listy dostępnych sieci Wi-Fi i wybierz pozycję **Właściwości sprzętu.**

    ![Właściwości sprzętu w Wi-Fi konfiguracji](./images/wifi-hololens-hwdetails.jpg)

   Adres IP zostanie wyświetlony obok adresu **IPv4.**

### <a name="by-using-voice-commands"></a>Za pomocą poleceń głosowych

W zależności od kompilacji urządzeń możesz użyć wbudowanych poleceń głosowych lub Cortany, aby wyświetlić swój adres IP. W kompilacjach po [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) mówi "What's my IP address?" (Jaki jest mój adres IP?) Zostanie ona wyświetlona. W przypadku wcześniejszych kompilacji lub urządzenia HoloLens (1. generacji) powiedz "Hey Cortana, What's my IP address?" (Hej, Cortana, jaki jest mój adres IP?) Cortana wyświetli i odczyta Twój adres IP.

### <a name="by-using-windows-device-portal"></a>Przy użyciu Portal urządzeń z systemem Windows

1. W przeglądarce internetowej na komputerze otwórz [portal urządzeń](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Przejdź do **sekcji Sieć.**  
   W tej sekcji zostanie wyświetlony Adres IP i inne informacje o sieci. Za pomocą tej metody można skopiować i wkleić adres IP na komputerze dewelopera.

## <a name="change-ip-address-to-static-address"></a>Zmiana adresu IP na adres statyczny
### <a name="by-using-settings"></a>Przy użyciu ustawień
 
1. Otwórz menu **Start.**
1. Wybierz aplikację **Ustawienia** z **menu Start** lub z listy **Wszystkie aplikacje** po prawej stronie menu **Start.** Aplikacja **Ustawienia** zostanie automatycznie umieszczona przed toem.
1. Wybierz **pozycję Sieć & Internet.**
1. Przewiń w dół do listy dostępnych sieci Wi-Fi i wybierz pozycję **Właściwości sprzętu.**
1. W **oknie Edytowanie ustawień adresu IP** zmień pierwsze pole na **Ręczne.**
1. Wprowadź żądaną konfigurację adresu IP w pozostałych polach, a następnie kliknij przycisk **Zapisz.**

### <a name="by-using-windows-device-portal"></a>Przy użyciu Portal urządzeń z systemem Windows

1. W przeglądarce internetowej na komputerze otwórz [portal urządzeń](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Przejdź do **sekcji Sieć.**
1. Wybierz przycisk **Konfiguracja protokołu IPv4.**
1. Wybierz **pozycję Użyj następującego adresu IP** i wprowadź odpowiednią konfigurację protokołu TCP/IP.
1. Wybierz **pozycję Użyj następujących adresów serwerów DNS** i w razie potrzeby wprowadź preferowane i alternatywne adresy serwerów DNS.
1. Kliknij pozycję **Zapisz**. 