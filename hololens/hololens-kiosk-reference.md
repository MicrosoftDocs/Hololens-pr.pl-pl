---
title: HoloLens informacji referencyjnych dotyczących kiosku
description: Informacje i przykłady dla kiosków na HoloLens urządzeniach.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9f8cfd0013ac5b8cf85a334cbb89c458440820d9
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427073"
---
# <a name="hololens-kiosk-reference-information"></a>HoloLens Informacje referencyjne dotyczące kiosku

Ta strona zawiera przydatne informacje dotyczące konfigurowania HoloLens trybu kiosku urządzenia. Te informacje obejmują identyfikatory AUMID dla aplikacji skrzynki odbiorczej i lokalizowanie aplikacji oraz kilka przykładów XML dla trybu kiosku, które nie są jeszcze gotowe do użycia w kilku różnych scenariuszach. Aby uzyskać informacje na temat konfigurowania kiosku, przeczytaj [stronę konfigurowania kiosku.](hololens-kiosk.md)

## <a name="hololens-application-user-model-ids-aumids"></a>HoloLens Identyfikatory modeli użytkowników aplikacji (AUMID)  

Aby uzyskać ogólne informacje na temat wybierania aplikacji kiosku, zobacz Wytyczne dotyczące wybierania aplikacji do przypisanego dostępu [(tryb kiosku).](/windows/configuration/guidelines-for-assigned-access-app)

Jeśli używasz systemu mobile Zarządzanie urządzeniami (MDM) lub pakietu aprowizowania do konfigurowania trybu kiosku, użyj dostawcy usług konfiguracji [AssignedAccess (CSP)](/windows/client-management/mdm/assignedaccess-csp) do określenia aplikacji. Program CSP używa [identyfikatorów modelu użytkownika aplikacji (AUMID)](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) do identyfikowania aplikacji. W poniższej tabeli wymieniono identyfikatory AUMID niektórych aplikacji, których można używać w kiosku z wieloma aplikacjami.

<a id="aumids"></a>

|Nazwa aplikacji |AUMID |
| --- | --- |
|Przeglądarka 3D |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|Kalendarz |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
|Aparat<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! App |
|S wyboru urządzenia na HoloLens (1. generacja) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|S wyboru urządzenia w HoloLens 2 |Microsoft. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft.Windows. DevicesFlowHost |
|Przewodniki dotyczące usługi Dynamics 365 |Microsoft.Dynamics365.Guides \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft.RemoteAssist |
|Centrum &nbsp; opinii |Microsoft.WindowsFeedbackHub \_ 8wekyb3d8bbwe \! App |
|Eksplorator plików |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy! App |
|Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Stary Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge |
|Nowe Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Sklepie Microsoft |Microsoft.WindowsStore_8wekyb3d8bbwe! App |
|Miracast<sup>4</sup> | &nbsp; |
|Filmy & TV |Microsoft.ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive \_ 8wekyb3d8bbwe \! App |
|Zdjęcia |Microsoft. Windows. Zdjęcia \_ 8wekyb3d8bbwe \! App |
|Stary Ustawienia |HolographicSystemSettings_cw5n1h2txyewy! App |
|Nowe Ustawienia |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
|Porady |Microsoft.HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> Aby włączyć funkcję przechwytywania zdjęć lub wideo, należy włączyć aplikację Aparat jako aplikację kiosku.  
> <sup>2</sup> Po włączeniu aplikacji Aparat należy pamiętać o następujących warunkach:
> - Menu Szybkie akcje zawiera przyciski Zdjęcie i Wideo.
> - Należy również włączyć aplikację (taką jak Zdjęcia, Poczta lub OneDrive), która może wchodzić w interakcje z obrazami lub je pobierać.  
>  
> <sup>3</sup> Nawet jeśli nie włączysz Cortana jako aplikacji kiosku, wbudowane polecenia głosowe są włączone. Jednak polecenia związane z wyłączonymi funkcjami nie mają żadnego efektu.  
> <sup>4</sup> Nie można włączyć Miracast bezpośrednio. Aby włączyć Miracast jako aplikację kiosku, włącz aplikacje Aparat i S wyboru urządzeń.

Ponadto aplikacji Mixed Reality Home nie można ustawić jako aplikacji kiosku.

Powrót do [obsługiwanych scenariuszy trybu kiosku na podstawie typu tożsamości](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

## <a name="kiosk-xml-code-samples"></a>Przykłady kodu XML kiosku

1. [Profil dostępu przypisanego globalnie przez wiele aplikacji](#multiple-app-global-assigned-access-profile)
1. [Profil dostępu przypisanego globalnie przez wiele aplikacji z wyłączeniem właścicieli urządzeń](#multiple-app-global-assigned-access-profile-excluding-device-owners)
1. [Profil dostępu przypisany do wielu aplikacji dla konta lokalnego lub konta użytkownika usługi AAD](#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account)
1. [Wiele profilów dostępu przypisanych do aplikacji dla co najmniej dwóch użytkowników usługi AAD](#multiple-app-assigned-access-profiles-for-two-aad-users-or-more)
1. [Profil dostępu przypisany do wielu aplikacji dla jednej grupy usługi AAD](#multiple-app-assigned-access-profile-for-one-aad-group)
1. [Profil dostępu przypisany do wielu aplikacji dla co najmniej dwóch grup usługi AAD](#multiple-app-assigned-access-profile-for-two-aad-groups-or-more)
1. [Wiele profilów dostępu przypisanych do aplikacji dla jednego konta usługi AAD i jednej grupy usługi AAD](#multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group)
1. [Profil dostępu przypisany do wielu aplikacji dla gości](#multiple-app-assigned-access-profile-for-visitors)

> [!NOTE]
> Zastąp akcje TODO zgodnie z wymaganiami.

### <a name="multiple-app-global-assigned-access-profile"></a>Profil dostępu przypisanego globalnie przez wiele aplikacji

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone.xml" highlight="18-20":::

[Powrót do listy](#kiosk-xml-code-samples) <br>
Powrót do [obsługiwanych scenariuszy trybu kiosku na podstawie typu tożsamości](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-global-assigned-access-profile-excluding-device-owners"></a>Profil dostępu przypisanego globalnie przez wiele aplikacji z wyłączeniem właścicieli urządzeń

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone-excluding-device-owners.xml" highlight="18-20":::

[Powrót do listy](#kiosk-xml-code-samples) <br>
Powrót do [obsługiwanych scenariuszy trybu kiosku na podstawie typu tożsamości](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account"></a>Profil dostępu przypisany do wielu aplikacji dla konta lokalnego lub konta użytkownika usługi AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-local-or-aad-user.xml" highlight="18-20,51,55":::

[Powrót do listy](#kiosk-xml-code-samples) <br>
Powrót do [obsługiwanych scenariuszy trybu kiosku na podstawie typu tożsamości](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profiles-for-two-aad-users-or-more"></a>Wiele profilów dostępu przypisanych do aplikacji dla co najmniej dwóch użytkowników usługi AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-users-or-more.xml" highlight="22-24,52,53,80,88":::

[Powrót do listy](#kiosk-xml-code-samples) <br>
Powrót do [obsługiwanych scenariuszy trybu kiosku na podstawie typu tożsamości](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-group"></a>Profil dostępu przypisany do wielu aplikacji dla jednej grupy usługi AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-one-aad-group.xml" highlight="28":::

[Powrót do listy](#kiosk-xml-code-samples) <br>
Powrót do [obsługiwanych scenariuszy trybu kiosku na podstawie typu tożsamości](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-two-aad-groups-or-more"></a>Profil dostępu przypisany do wielu aplikacji dla co najmniej dwóch grup usługi AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-groups-or-more.xml" highlight="22-24,52,53,83,94":::

[Powrót do listy](#kiosk-xml-code-samples) <br>
Powrót do [obsługiwanych scenariuszy trybu kiosku na podstawie typu tożsamości](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group"></a>Wiele profilów dostępu przypisanych do aplikacji dla jednego konta usługi AAD i jednej grupy usługi AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-for-aad-user-and-aad-group.xml" highlight="22-24,52,53,80,91":::

[Powrót do listy](#kiosk-xml-code-samples) <br>
Powrót do [obsługiwanych scenariuszy trybu kiosku na podstawie typu tożsamości](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-visitors"></a>Profil dostępu przypisany do wielu aplikacji dla gości

:::code language="xml" source="samples/kiosk-sample-multi-app-visitor-user.xml" highlight="18-20":::

[Powrót do listy](#kiosk-xml-code-samples) <br>
Powrót do [obsługiwanych scenariuszy trybu kiosku na podstawie typu tożsamości](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)
