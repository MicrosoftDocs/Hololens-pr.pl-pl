---
title: Typowe ograniczenia dotyczące urządzeń
description: Bądź na bieżąco z powszechnymi ograniczeniami i ustawieniami urządzeń dla HoloLens rzeczywistości mieszanej.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2021
ms.reviewer: aboeger
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 12dd061565c88fed65d1152c224be9ebbc7185d4
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924310"
---
# <a name="common-device-restrictions"></a>Typowe ograniczenia dotyczące urządzeń

Ten przewodnik ułatwia specjalistom IT zrozumienie najczęściej używanych opcji zarządzania dostępnych Windows 10 Holographic systemu operacyjnego w przedsiębiorstwie. Zapoznaj się z dokumentacją systemu MDM, aby zrozumieć, jak te zasady są włączane przez dostawcę rozwiązania MDM. Nie wszystkie systemy MDM obsługują wszystkie ustawienia opisane w tym przewodniku. Niektóre obsługują zasady niestandardowe za pośrednictwem plików XML OMA-URI. Zobacz [Microsoft Intune obsługę zasad niestandardowych.](/mem/intune/configuration/custom-settings-windows-10) Konwencje nazewnictwa mogą się również różnić w zależności od dostawcy rozwiązań MDM.

## <a name="prevent-changing-of-settings"></a>Zapobiegaj zmianie ustawień

Pracownicy mogą zwykle zmieniać niektóre ustawienia urządzeń osobistych, które można zablokować na urządzeniach firmowych. Pracownicy mogą interaktywnie dostosowywać niektóre ustawienia HoloLens za pośrednictwem interfejsu użytkownika ustawień. Za pomocą rozwiązania MDM można ograniczyć to, co użytkownicy mogą zmieniać.
Poniżej wymieniono często używane ustawienia zarządzania urządzeniami przenośnymi, które Windows 10 Holographic do konfigurowania ograniczeń ustawień:

- [Zezwalaj na sieć VPN:](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Umożliwia użytkownikowi zmianę ustawień sieci VPN
- [Zezwalaj na ręczną konfigurację sieci Wi-Fi:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Umożliwia użytkownikom tworzenie połączeń Wi-Fi poza sieciami aprowizowanych przez rozwiązanie MDM
- [Zezwalaj na ręczne unejestrowanie rozwiązania MDM](/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Określa, czy użytkownicy mogą usunąć konto firmowe (tj. wyrollować urządzenie z systemu MDM)

Dodano Windows [platformie Holographic w wersji 20H2](hololens-release-notes.md#windows-holographic-version-20h2) dla HoloLens 2:

- [Zezwalaj na dodawanie pakietu aprowizowania:](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Przełącz się, jeśli użytkownicy mogą dodawać nowe pakiety aprowizowania, nadpisując je nowymi wartościami.
- [Zezwalaj na usuwanie pakietu aprowizowania:](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Przełącz się, jeśli użytkownicy mogą usuwać pakiety aprowizowania, umożliwiając im przełączanie wcześniej zablokowanych ustawień.

Dodano w [Windows Holographic w wersji 21H2:](hololens-release-notes.md#windows-holographic-version-21h2)

- [Zasady RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly) umożliwiają skonfigurowanie aplikacji Microsoft Store tak, aby wyświetlała tylko prywatny sklep skonfigurowany dla organizacji, ograniczając dostęp tylko do aplikacji, które zostały udostępnione.

Więcej szczegółów na temat opcji zasad można znaleźć HoloLens [obsługiwanych przez CSP zasad](/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="hardware-restrictions"></a>Ograniczenia sprzętowe

Windows 10 Holographic korzystają z najnowocześniejszej technologii, która obejmuje popularne funkcje sprzętowe, takie jak kamery, mikrofony, głośniki, interfejsy USB, interfejsy Bluetooth i sieci Wi-Fi. Aby kontrolować dostępność tych funkcji, można użyć ograniczeń sprzętowych.
Poniżej wymieniono często używane ustawienia zarządzania urządzeniami przenośnymi, które Windows 10 Holographic do konfigurowania ograniczeń sprzętowych:

> [!NOTE]
> Niektóre z tych ograniczeń sprzętowych mają wpływ na łączność i pomagają w ochronie danych.

- [Zezwalaj na sieć Wi-Fi:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Określa, czy użytkownicy mogą włączać i używać urządzenia radiowego Wi-Fi na swoich urządzeniach.
- [Zezwalaj na połączenie USB:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Czy połączenie USB jest włączone (nie ma wpływu na ładowanie USB).
- [Zezwalaj na Bluetooth:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Określa, czy użytkownicy mogą włączać i używać Bluetooth radiowych na swoich urządzeniach.
- [Ogranicz aparat fotograficzny:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Określa, Windows mogą uzyskać dostęp do aparatu fotograficznego.
- [Ogranicz mikrofony:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Określa, Windows aplikacje mogą uzyskać dostęp do mikrofonu.

Dodano Windows [platformie Holographic w wersji 20H2](hololens-release-notes.md#windows-holographic-version-20h2) dla HoloLens 2:

- [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Ustaw czas do momentu wyłączenia wyświetlania i wyłączenia wyświetlania zablokuje urządzenie.
- [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Ustaw czas do momentu wyłączenia wyświetlania i wyłączenia wyświetlania zablokuje urządzenie.
