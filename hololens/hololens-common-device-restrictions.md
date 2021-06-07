---
title: Typowe ograniczenia dotyczące urządzeń
description: Bądź na bieżąco z powszechnymi ograniczeniami i ustawieniami urządzeń HoloLens rzeczywistości mieszanej.
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
ms.openlocfilehash: e9c44466da375611f8864eae1b6e6ceea3ef9b09
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378242"
---
# <a name="common-device-restrictions"></a>Typowe ograniczenia dotyczące urządzeń 

Ten przewodnik ułatwia specjalistom IT zrozumienie najczęściej używanych opcji zarządzania dostępnych Windows 10 Holographic systemu operacyjnego w przedsiębiorstwie. Zapoznaj się z dokumentacją systemu MDM, aby zrozumieć, jak te zasady są włączane przez dostawcę rozwiązania MDM. Nie wszystkie systemy MDM obsługują wszystkie ustawienia opisane w tym przewodniku. Niektóre obsługują zasady niestandardowe za pośrednictwem plików XML OMA-URI. Zobacz [Microsoft Intune obsługę zasad niestandardowych.](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) Konwencje nazewnictwa mogą się również różnić w zależności od dostawcy rozwiązań MDM.

## <a name="prevent-changing-of-settings"></a>Zapobiegaj zmianie ustawień
Pracownicy mogą zwykle zmieniać niektóre ustawienia urządzeń osobistych, które można zablokować na urządzeniach firmowych. Pracownicy mogą interaktywnie dostosowywać niektóre ustawienia urządzenia HoloLens za pomocą interfejsu użytkownika ustawień. Za pomocą rozwiązania MDM można ograniczyć to, co użytkownicy mogą zmieniać. Poniżej wymieniono często używane ustawienia zarządzania urządzeniami przenośnymi, które Windows 10 Holographic do konfigurowania ograniczeń ustawień:
-   [Zezwalaj na sieć VPN:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Umożliwia użytkownikowi zmianę ustawień sieci VPN
-   [Zezwalaj na ręczną konfigurację sieci Wi-Fi:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Umożliwia użytkownikom tworzenie połączeń Wi-Fi poza sieciami aprowizowanych przez rozwiązanie MDM
-   [Zezwalaj na ręczne unejestrowanie rozwiązania MDM](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Określa, czy użytkownicy mogą usunąć konto firmowe (tj. wyrollować urządzenie z systemu MDM)

Dodano w [systemie Windows Holographic w wersji 20H2](hololens-release-notes.md#windows-holographic-version-20h2) dla urządzeń HoloLens 2:
- [Zezwalaj na dodawanie pakietu aprowizowania:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Przełącz się, jeśli użytkownicy mogą dodawać nowe pakiety aprowizowania, nadpisując je nowymi wartościami.
- [Zezwalaj na usuwanie pakietu aprowizowania:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Przełącz się, jeśli użytkownicy mogą usuwać pakiety aprowizowania, umożliwiając im przełączanie wcześniej zablokowanych ustawień.

Więcej szczegółów na temat opcji zasad można znaleźć w obsługiwanych przez urządzenia HoloLens [zasadach CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="hardware-restrictions"></a>Ograniczenia sprzętowe
Windows 10 Holographic urządzenia używają najnowocześniejszej technologii, która obejmuje popularne funkcje sprzętowe, takie jak kamery, mikrofony, głośniki, interfejsy USB, interfejsy Bluetooth i sieć Wi-Fi. Aby kontrolować dostępność tych funkcji, można użyć ograniczeń sprzętowych.
Poniżej wymieniono często używane ustawienia zarządzania urządzeniami przenośnymi, które Windows 10 Holographic do konfigurowania ograniczeń sprzętowych:

> [!NOTE]
> Niektóre z tych ograniczeń sprzętowych mają wpływ na łączność i pomagają w ochronie danych.

-   [Zezwalaj na sieć Wi-Fi:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Określa, czy użytkownicy mogą włączać i używać urządzenia radiowego Wi-Fi na swoich urządzeniach.
-   [Zezwalaj na połączenie USB:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Czy połączenie USB jest włączone (nie ma wpływu na ładowanie USB).
-   [Zezwalaj na połączenia Bluetooth:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Określa, czy użytkownicy mogą włączać i używać przycisku radiowego Bluetooth na swoich urządzeniach.
-   [Ogranicz aparat:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Określa, czy aplikacje systemu Windows mogą uzyskać dostęp do aparatu.
-   [Ogranicz mikrofony:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Określa, czy aplikacje systemu Windows mogą uzyskać dostęp do mikrofonu.

Dodano w systemie Windows Holographic w wersji [20H2](hololens-release-notes.md#windows-holographic-version-20h2) dla urządzeń HoloLens 2. 
- [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Ustaw czas do momentu wyłączenia wyświetlania i wyłączenia wyświetlania zablokuje urządzenie. 
- [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Ustaw czas do momentu wyłączenia wyświetlania i wyłączenia wyświetlania zablokuje urządzenie. 
