---
title: Windows Defender Kontrola aplikacji — WDAC
description: Omówienie tego, czym Windows Defender jest kontrola aplikacji i jak za jej pomocą zarządzać HoloLens rzeczywistości mieszanej.
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
ms.openlocfilehash: a27a16913873c5245f734dbe084eb2b7ed007c20
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639934"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender Kontrola aplikacji — WDAC

Funkcja WDAC umożliwia administratorowi IT skonfigurowanie urządzeń tak, aby blokowały uruchamianie aplikacji na urządzeniach. Różni się to od metod ograniczeń dotyczących urządzeń, takich jak tryb kiosku, w którym użytkownik jest prezentowany za pomocą interfejsu użytkownika, który ukrywa aplikacje na urządzeniu, ale można je nadal uruchomiać. Podczas implementowania usługi WDAC aplikacje są nadal widoczne na liście Wszystkie aplikacje, ale wdac zatrzymuje te aplikacje i procesy mogą być uruchomione przez użytkownika urządzenia.

Do urządzenia można przypisać więcej niż jedną zasady WDAC. Jeśli w systemie ustawiono wiele zasad WDAC, zostaną one wprowadzone w najbardziej restrykcyjnych zasadach. 

> [!NOTE]
> Gdy użytkownicy końcowi spróbują uruchomić aplikację zablokowaną przez centrum WDAC, na HoloLens nie otrzymają powiadomienia o tym, że nie można uruchomić tej aplikacji.

Poniżej przedstawiono przewodnik dla użytkowników, aby dowiedzieć się, jak używać funkcji [WDAC i Windows PowerShell](/mem/intune/configuration/custom-profile-hololens)do zezwalania na aplikacje lub blokowania ich na urządzeniach z systemem HoloLens 2 przy użyciu usługi Microsoft Intune .

Gdy użytkownicy wyszukują aplikacje zainstalowane na komputerze Windows 10 przy użyciu pierwszego przykładowego kroku, może być konieczne kilku prób zawężenia wyników.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Jeśli nie znasz pełnej nazwy pakietu, być może trzeba będzie kilka razy uruchomić "Get-AppxPackage -name \* YourGueGuess", aby \* go znaleźć. Następnie po nazwie uruchom "$package 1 = Get-AppxPackage -name Actual.PackageName"

Na przykład uruchomienie następującej Microsoft Edge spowoduje zwrócenie więcej niż jednego wyniku, ale z tej listy można zidentyfikować, że pełna nazwa, która jest potrzebna, to Microsoft.MicrosoftEdge.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>Nazwy rodzin pakietów dla aplikacji na HoloLens

W powyższym przewodniku można ręcznie edytować i dodawać newPolicy.xml dla aplikacji, które są instalowane tylko na HoloLens z nazwami rodzin pakietów. Czasami istnieją aplikacje, których można użyć, które nie znajdują się na komputerze stacjonarnym, które chcesz dodać do zasad.

Poniżej znajduje się lista najczęściej używanych i używanych In-Box dla HoloLens 2.

| Nazwa aplikacji                   | Nazwa rodziny pakietów                                |
|----------------------------|----------------------------------------------------|
| Przeglądarka 3D                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| Instalator aplikacji              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup>         |
| Kalendarz                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Aparat fotograficzny                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Przewodniki dotyczące usługi Dynamics 365        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
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

- 1 — Blokowanie Instalator aplikacji blokuje tylko aplikację Instalator aplikacji, a nie aplikacje zainstalowane z innych źródeł, takich jak Microsoft Store lub z rozwiązania MDM.

### <a name="how-to-find-a-package-family-name"></a>Jak znaleźć nazwę rodziny pakietów

Jeśli aplikacja nie znajduje się na tej liście, użytkownik może użyć nazwy Portal urządzeń połączonej z urządzeniem HoloLens 2, na których zainstalowano aplikację, w celu określenia wartości PackageRelativeID, a następnie uzyskania wartości PackageFamilyName.

1. Zainstaluj aplikację na urządzeniu HoloLens 2. 
1. Otwórz Ustawienia -> Updates & Security -> Dla deweloperów, włącz tryb dewelopera, a następnie **portal urządzeń.**  
    1. Aby uzyskać więcej szczegółowych instrukcji, przeczytaj więcej na temat konfigurowania i [używania portalu urządzeń tutaj.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. Po Portal urządzeń przejdź do menu **Widoki,** a następnie **wybierz pozycję Aplikacje.** 
1. Na panelu Zainstalowane aplikacje użyj listy rozwijanej, aby wybrać zainstalowaną aplikację. 
1. Znajdź pakiet PackageRelativeID. 
1. Skopiuj znaki aplikacji przed znakiem !. Będą to twoje znaki PackageFamilyName.


