---
title: Typowe ograniczenia dotyczące urządzeń
description: Bądź na bieżąco ze wspólnymi ograniczeniami i ustawieniami urządzeń dla HoloLens rzeczywistości mieszanej.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 6a09766a06fff912aae20dc07974b723d812bd370562a33297552dc0d2f7f12c
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664285"
---
# <a name="common-device-restrictions"></a>Typowe ograniczenia dotyczące urządzeń 

Ten przewodnik ułatwia specjalistom IT zrozumienie najczęściej używanych opcji zarządzania dostępnych Windows 10 Holographic systemu operacyjnego w przedsiębiorstwie. Zapoznaj się z dokumentacją systemu MDM, aby zrozumieć, w jaki sposób te zasady są włączane przez dostawcę rozwiązania MDM. Nie wszystkie systemy MDM obsługują wszystkie ustawienia opisane w tym przewodniku. Niektóre obsługują zasady niestandardowe za pośrednictwem plików XML OMA-URI. Zobacz [Microsoft Intune obsługę zasad niestandardowych.](/mem/intune/configuration/custom-settings-windows-10) Konwencje nazewnictwa mogą się również różnić w zależności od dostawcy rozwiązań MDM.

## <a name="prevent-changing-of-settings"></a>Zapobieganie zmianie ustawień
Pracownicy mogą zwykle zmieniać niektóre ustawienia urządzeń osobistych, które można zablokować na urządzeniach firmowych. Pracownicy mogą interaktywnie dostosowywać niektóre ustawienia HoloLens za pośrednictwem interfejsu użytkownika ustawień. Za pomocą rozwiązania MDM można ograniczyć to, co użytkownicy mogą zmieniać. Poniżej wymieniono często używane ustawienia zarządzania urządzeniami przenośnymi, które Windows 10 Holographic do konfigurowania ograniczeń ustawień:
-   [Zezwalaj na sieć VPN:](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Umożliwia użytkownikowi zmianę ustawień sieci VPN
-   [Zezwalaj na ręczną konfigurację sieci Wi-Fi:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Umożliwia użytkownikom tworzenie połączeń Wi-Fi poza sieciami aprowizowanych przez rozwiązanie MDM
-   [Zezwalaj na ręczne wywijanie rozwiązania MDM](/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Określa, czy użytkownicy mogą usuwać konto w miejscu pracy (tj. wyrollować urządzenie z systemu MDM)

Dodano Windows urządzeniu Holographic w wersji [20H2](hololens-release-notes.md#windows-holographic-version-20h2) dla HoloLens 2:
- [Zezwalaj na dodawanie pakietu aprowizowania:](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Przełącz się, jeśli użytkownicy mogą dodawać nowe pakiety aprowizowania, nadpisując nowe wartości.
- [Zezwalaj na usuwanie pakietu aprowizowania:](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Przełącz się, jeśli użytkownicy mogą usuwać pakiety aprowizowania, umożliwiając im przełączanie wcześniej zablokowanych ustawień.

Więcej szczegółów na temat opcji zasad można znaleźć HoloLens [obsługiwanych przez CSP zasad](/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="hardware-restrictions"></a>Ograniczenia sprzętowe
Windows 10 Holographic korzystają z najnowocześniejszej technologii, która obejmuje popularne funkcje sprzętowe, takie jak kamery, mikrofony, prelegenty, interfejsy USB, interfejsy Bluetooth i Wi-Fi. Aby kontrolować dostępność tych funkcji, można użyć ograniczeń sprzętowych.
Poniżej wymieniono często używane ustawienia zarządzania urządzeniami przenośnymi, które Windows 10 Holographic do konfigurowania ograniczeń sprzętowych:

> [!NOTE]
> Niektóre z tych ograniczeń sprzętowych mają wpływ na łączność i pomagają w ochronie danych.

-   [Zezwalaj na sieć Wi-Fi:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Określa, czy użytkownicy mogą włączać i używać przycisku radiowego sieci Wi-Fi na swoich urządzeniach.
-   [Zezwalaj na połączenie USB:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Czy połączenie USB jest włączone (nie ma wpływu na ładowanie USB).
-   [Zezwalaj Bluetooth:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Określa, czy użytkownicy mogą włączać i używać Bluetooth radiowego na swoich urządzeniach.
-   [Ogranicz aparat:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Określa, Windows aplikacje mogą uzyskać dostęp do aparatu fotograficznego.
-   [Ogranicz mikrofony:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Określa, Windows aplikacje mogą uzyskać dostęp do mikrofonu.

Dodano [Windows holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) dla HoloLens 2 urządzeń. 
- [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Ustaw czas do wyłączenia wyświetlania i wyłączenia wyświetlania powoduje zablokowanie urządzenia. 
- [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Ustaw czas do wyłączenia wyświetlania i wyłączenia wyświetlania powoduje zablokowanie urządzenia. 
