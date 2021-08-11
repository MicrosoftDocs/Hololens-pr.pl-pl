---
title: Zarządzanie punktami końcowymi połączenia dla HoloLens
description: Dowiedz się, jak skonfigurować sieć HoloLens sieci Wi-Fi podczas zarządzania punktami końcowymi połączeń i konfigurowania ich.
keywords: hololens, offline, OOBE
audience: ITPro
ms.date: 07/01/2019
ms.assetid: b86f603c-d25f-409b-b055-4bbc6edcd301
author: Teresa-Motiv
ms.author: v-tea
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: jarrettr
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 63c82e5b1a953ee2f69bf4c22a8442c7bca07f073cc13f1e5e573fde0ccc1976
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662939"
---
# <a name="manage-connection-endpoints-for-hololens"></a>Zarządzanie punktami końcowymi połączenia dla HoloLens

Niektóre HoloLens, aplikacje i powiązane usługi przesyłły dane do punktów końcowych sieci firmy Microsoft. W tym artykule wymieniono różne punkty końcowe i adresy URL, które muszą być dozwolone w konfiguracji sieci (np. serwer proxy lub zapora), aby te składniki mogły być funkcjonalne.    

## <a name="near-offline-setup"></a>Konfiguracja niemal offline

HoloLens obsługuje ograniczony zestaw środowisk w trybie offline dla klientów, którzy mają ograniczenia środowiska sieciowego. Jednak HoloLens musi przejść przez początkowe skonfigurowanie urządzenia i należy włączyć następujące adresy URL:

| Przeznaczenie | Adres URL |
|------|------|
| IdPS (Identyfikatory TOŻSAMOŚCI) | https://sdx.microsoft.com/frx/idps |
| [NCSI](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services#bkmk-ncsi) |  http://www.msftconnecttest.com/connecttest.txt  |
| AADv9 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/9 |
| AADv10 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/10 |
| AAD Pin | https://account.live.com/aadngc?uiflavor=win10&showSuccess=1 |
| MSA | https://login.live.com/ppsecure/inlineconnect.srf?id=80600 |
| Przypięcie do msa | https://account.live.com/msangc?fl=enroll |

## <a name="endpoint-configuration"></a>Konfiguracja punktu końcowego

Oprócz powyższej listy, aby w pełni wykorzystać możliwości HoloLens, w konfiguracji sieci należy włączyć następujące punkty końcowe.


| Przeznaczenie | Adres URL |
|------|------|
| Azure                                               | wd-prod-fe.cloudapp.azure.com                                       |
|                                                     | ris-prod-atm.trafficmanager.net                                     |
|                                                     | validation-v2.sls.trafficmanager.net                                |
| Uwierzytelnianie wieloskładnikowe w usłudze Azure AD                | https://secure.aadcdn.microsoftonline-p.com                         |
| Konfiguracja usługi Intune i zarządzania urządzeniami przenośnymi                       | activation-v2.sls.microsoft.com/*                                   |
|                                                     | cdn.onenote.net                                                     |
|                                                     | client.wns.windows.com                                              |
|                                                     | crl.microsoft.com/pki/crl/*                                         |
|                                                     | ctldl.windowsupdate.com                                             |
|                                                     | *Displaycatalog.mp.microsoft.com                                    |
|                                                     | dm3p.wns.windows.com                                                |
|                                                     | *microsoft.com/pkiops/*                                             |
|                                                     | ocsp.digicert.com/*                                                 |
|                                                     | r.manage.microsoft.com                                              |
|                                                     | tile-service.weather.microsoft.com                                  |
|                                                     | settings-win.data.microsoft.com                                     |
| Certyfikaty                                        | activation-v2.sls.microsoft.com/*                                   |
|                                                     | crl.microsoft.com/pki/crl/*                                         |
|                                                     | ocsp.digicert.com/*                                                 |
|                                                     | https://www.microsoft.com/pkiops/*                                          |
| Cortana i wyszukiwanie                                  | store-images.*microsoft.com                                         |
|                                                     | www.bing.com/client                                                 |
|                                                     | www.bing.com                                                        |
|                                                     | www.bing.com/proactive                                              |
|                                                     | www.bing.com/threshold/xls.aspx                                     |
|                                                     | exo-ring.msedge.net                                                 |
|                                                     | fp.msedge.net                                                       |
|                                                     | fp-vp.azureedge.net                                                 |
|                                                     | odinvzc.azureedge.net                                               |
|                                                     | spo-ring.msedge.net                                                 |
| Uwierzytelnianie urządzeń                               | login.live.com*                                                     |
| Metadane urządzenia                                     | dmd.metaservices.microsoft.com                                      |
| Lokalizacja                                            | inference.location.live.net                                         |
|                                                     | location-inference-westus.cloudapp.net                              |
| Dane diagnostyczne                                     | v10.events.data.microsoft.com                                       |
|                                                     | v10.vortex-win.data.microsoft.com/collect/v1                        |
|                                                     | https://www.microsoft.com                                                   |
|                                                     | co4.telecommand.telemetry.microsoft.com                             |
|                                                     | cs11.wpc.v0cdn.net                                                  |
|                                                     | cs1137.wpc.gammacdn.net                                             |
|                                                     | modern.watson.data.microsoft.com*                                   |
|                                                     | watson.telemetry.microsoft.com                                      |
| Licencjonowanie                                           | licensing.mp.microsoft.com                                          |
| Konto Microsoft                                   | login.msa.akadns6.net                                               |
|                                                     | us.configsvc1.live.com.akadns.net                                   |
| Microsoft Edge                                      | iecvlist.microsoft.com                                              |
| Usługa przekierowywania linków do przodu firmy Microsoft (FWLink) | go.microsoft.com                                                    |
| Sklepie Microsoft                                     | *.wns.windows.com                                                   |
|                                                     | storecatalogrevocation.storequality.microsoft.com                   |
|                                                     | img-prod-cms-rt-microsoft-com*                                      |
|                                                     | store-images.microsoft.com                                          |
|                                                     | .md.mp.microsoft.com                                                |
|                                                     | *Displaycatalog.mp.microsoft.com                                    |
|                                                     | pti.store.microsoft.com                                             |
|                                                     | storeedgefd.dsx.mp.microsoft.com                                    |
|                                                     | markets.books.microsoft.com                                         |
|                                                     | share.microsoft.com                                                 |
| Wskaźnik stanu połączenia sieciowego (NCSI)          | www.msftconnecttest.com*                                            |
| Office                                              | *.c-msedge.net                                                      |
|                                                     | *.e-msedge.net                                                      |
|                                                     | *.s-msedge.net                                                      |
|                                                     | nexusrules.officeapps.live.com                                      |
|                                                     | ocos-office365-s2s.msedge.net                                       |
|                                                     | officeclient.microsoft.com                                          |
|                                                     | outlook.office365.com                                               |
|                                                     | client-office365-tas.msedge.net                                     |
|                                                     | https://www.office.com                                                      |
|                                                     | onecollector.cloudapp.aria                                          |
|                                                     | v10.events.data.microsoft.com/onecollector/1.0/                     |
|                                                     | self.events.data.microsoft.com                                      |
|                                                     | to-do.microsoft.com                                                 |
| OneDrive                                            | g.live.com/1rewlive5skydrive/*                                      |
|                                                     | msagfx.live.com                                                     |
|                                                     | oneclient.sfx.ms                                                    |
| Aplikacja Photos                                          | evoke-windowsservices-tas.msedge.net                                |
| Ustawienia                                            | cy2.settings.data.microsoft.com.akadns.net                          |
|                                                     | settings.data.microsoft.com                                         |
|                                                     | settings-win.data.microsoft.com                                     |
| Windows Defender                                    | wdcp.microsoft.com                                                  |
|                                                     | definitionupdates.microsoft.com                                     |
|                                                     | go.microsoft.com                                                    |
|                                                     | *smartscreen.microsoft.com                                          |
|                                                     | smartscreen-sn3p.smartscreen.microsoft.com                          |
|                                                     | unitedstates.smartscreen-prod.microsoft.com                         |
| W centrum uwagi Windows                                   | *.search.msn.com                                                    |
|                                                     | arc.msn.com                                                         |
|                                                     | g.msn.com*                                                          |
|                                                     | query.prod.cms.rt.microsoft.com                                     |
|                                                     | ris.api.iris.microsoft.com                                          |
| Windows Update                                      | *.prod.do.dsp.mp.microsoft.com                                      |
|                                                     | cs9.wac.phicdn.net                                                  |
|                                                     | emdl.ws.microsoft.com                                               |
|                                                     | *.dl.delivery.mp.microsoft.com                                      |
|                                                     | *.windowsupdate.com                                                 |
|                                                     | *.delivery.mp.microsoft.com                                         |
|                                                     | *.update.microsoft.com                                              |



## <a name="references"></a>Odwołania

> [!NOTE]
> W przypadku wdrażania usługi Remote Assist usługi D365 należy włączyć punkty końcowe wymienione dla usług SharePoint Online i OneDrive dla Firm w adresach URL Office 365 i zakresach adresów [IP.](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

- [Konfigurowanie Windows danych diagnostycznych w organizacji](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)
- [Zarządzanie punktami końcowymi połączenia dla Windows 10 Enterprise, wersja 1903](/windows/privacy/manage-windows-1903-endpoints)
- [Zarządzanie połączeniami Windows 10 składników systemu operacyjnego do usługi firmy Microsoft](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services)
- [Zarządzanie połączeniami z Windows 10 systemu operacyjnego do programu usługi firmy Microsoft przy użyciu Microsoft Intune MDM Server](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services-using-mdm)
- [Przepustowość i wymagania dotyczące konfiguracji sieci usługi Intune](/intune/fundamentals/network-bandwidth-use#network-communication-requirements)
- [Punkty końcowe sieci dla usługi Microsoft Intune](/intune/fundamentals/intune-endpoints)
- [Adresy URL i zakresy adresów IP usługi Office 365](/office365/enterprise/urls-and-ip-address-ranges)
- [Wymagania wstępne dotyczące programu Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)


## <a name="hololens-limitations"></a>HoloLens ograniczenia

Po skonfigurowaniu HoloLens można jej używać bez połączenia Wi-Fi, ale aplikacje korzystające z połączeń internetowych będą mieć ograniczone możliwości w przypadku korzystania z HoloLens offline.
