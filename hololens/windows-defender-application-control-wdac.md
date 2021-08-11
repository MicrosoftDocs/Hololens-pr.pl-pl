---
title: Windows Defender Kontrola aplikacji — WDAC
description: Omówienie tego, czym Windows Defender jest kontrola aplikacji i jak za jej pomocą zarządzać urządzeniami HoloLens rzeczywistości mieszanej.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/26/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: ab05f1bbe1570d4966932d6f8ac857e5bd2d8a7d3a8f5b93aaba0335eda05b01
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665560"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender Kontrola aplikacji — WDAC

Funkcja WDAC umożliwia administratorowi IT skonfigurowanie urządzeń tak, aby blokowały uruchamianie aplikacji na urządzeniach. Różni się to od metod ograniczeń urządzenia, takich jak tryb kiosku, w którym użytkownik jest prezentowany z interfejsem użytkownika, który ukrywa aplikacje na urządzeniu, ale można je nadal uruchomiać. Podczas implementowania usługi WDAC aplikacje są nadal widoczne na liście Wszystkie aplikacje, ale wDAC zatrzymuje te aplikacje i procesy mogą być uruchomione przez użytkownika urządzenia.

Do urządzenia można przypisać więcej niż jedną zasady WDAC. Jeśli w systemie ustawiono wiele zasad WDAC, zostaną one wprowadzone w najbardziej restrykcyjnych zasadach. 

> [!NOTE]
> Gdy użytkownicy końcowi spróbują uruchomić aplikację zablokowaną przez centrum WDAC, na HoloLens nie otrzymają powiadomienia o tym, że nie mogą uruchomić tej aplikacji.

Poniżej przedstawiono przewodnik dla użytkowników, aby dowiedzieć się, jak używać funkcji [WDAC i Windows PowerShell](/mem/intune/configuration/custom-profile-hololens)do zezwalania na aplikacje lub blokowania ich na urządzeniach z systemem HoloLens 2 przy użyciu usługi Microsoft Intune .

Gdy użytkownicy wyszukują aplikacje zainstalowane na komputerze Windows 10 pc przy użyciu pierwszego przykładowego kroku, może być konieczne kilka prób zawężenia wyników.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Jeśli nie znasz pełnej nazwy pakietu, być może trzeba będzie kilka razy uruchomić "Get-AppxPackage -name \* YourGueGuess", aby \* go znaleźć. Następnie po uruchomieniu nazwy uruchom "$package 1 = Get-AppxPackage -name Actual.PackageName"

Na przykład uruchomienie następującego ciągu dla Microsoft Edge zwróci więcej niż jeden wynik, ale z tej listy można zidentyfikować, że pełna nazwa, która jest potrzebna, to Microsoft.MicrosoftEdge.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>Nazwy rodzin pakietów dla aplikacji na HoloLens

W przewodniku połączonym powyżej możesz ręcznie edytować newPolicy.xml i dodawać reguły dla aplikacji, które są instalowane tylko na HoloLens z nazwami rodzin pakietów. Czasami istnieją aplikacje, których można użyć, które nie znajdują się na komputerze stacjonarnym, które chcesz dodać do zasad.

Poniżej znajduje się lista najczęściej używanych i używanych In-Box dla HoloLens 2.

| Nazwa aplikacji                   | Nazwa rodziny pakietów                                |
|----------------------------|----------------------------------------------------|
| Przeglądarka 3D                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| Instalator aplikacji              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup>         |
| Kalendarz                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Aparat fotograficzny                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365 Guides        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| Centrum opinii               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| Eksplorator plików              | c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| Mail                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Sklepie Microsoft            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| Filmy & TV                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| Zdjęcia                     | Microsoft. Windows. Photos_8wekyb3d8bbwe             |
| Ustawienia                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Porady                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1 — Blokowanie Instalator aplikacji będzie blokować tylko aplikację Instalator aplikacji, a nie aplikacje zainstalowane z innych źródeł, takich jak Microsoft Store lub z rozwiązania MDM.

### <a name="how-to-find-a-package-family-name"></a>Jak znaleźć nazwę rodziny pakietów

Jeśli aplikacji nie ma na tej liście, użytkownik może użyć usługi Portal urządzeń połączonej z urządzeniem HoloLens 2, na których zainstalowano aplikację, w celu określenia wartości PackageRelativeID, a następnie uzyskania wartości PackageFamilyName.

1. Zainstaluj aplikację na urządzeniu HoloLens 2. 
1. Otwórz Ustawienia -> Updates & Security -> Dla deweloperów i włącz tryb **dewelopera,** a następnie **portal urządzeń.** 
    1. Aby uzyskać więcej szczegółowych instrukcji, przeczytaj więcej na temat konfigurowania i [używania portalu urządzeń tutaj.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. Po Portal urządzeń przejdź do widoków, a **następnie** **wybierz pozycję Aplikacje.** 
1. Na panelu Zainstalowane aplikacje wybierz zainstalowaną aplikację przy użyciu listy rozwijanej. 
1. Znajdź packageRelativeID. 
1. Skopiuj znaki aplikacji przed znakiem !. Będzie to Twoja nazwa PackageFamilyName.


