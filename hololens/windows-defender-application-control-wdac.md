---
title: Windows Defender Kontrola aplikacji (WDAC)
description: Omówienie funkcji Windows Defender Application Control i sposobu używania jej do zarządzania urządzeniami HoloLens rzeczywistości mieszanej.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/21/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: efdc57b5e045c1669587ffc46dbe2132b6de6600
ms.sourcegitcommit: 52ed453cace3851fbec0cfcc228fa2a79f1a2fec
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2021
ms.locfileid: "128075389"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender Kontrola aplikacji — WDAC

## <a name="overview"></a>Omówienie

Funkcja WDAC umożliwia skonfigurowanie HoloLens blokowania uruchamiania aplikacji. Różni się to od trybu kiosku, w którym interfejs użytkownika ukrywa aplikacje, ale nadal można je uruchomiać. Za pomocą usługi WDAC można wyświetlić aplikacje, ale nie można ich uruchomić.

> [!NOTE]
> Gdy użytkownicy końcowi spróbują uruchomić aplikację zablokowaną przez aplikację WDAC na HoloLens, nie zostaną powiadomieni o tym, że nie mogą uruchomić aplikacji.

Do urządzenia można przypisać więcej niż jedną zasady WDAC. Jeśli w systemie ustawiono wiele zasad WDAC, zostaną one wprowadzone w najbardziej restrykcyjnych zasadach.

Poniżej przedstawiono przewodnik dla użytkowników, który zawiera informacje na temat sposobu używania funkcji [WDAC i Windows PowerShell](/mem/intune/configuration/custom-profile-hololens)do zezwalania na aplikacje lub blokowania ich na urządzeniach z systemem HoloLens 2 z Microsoft Intune .

Gdy użytkownicy wyszukują aplikacje zainstalowane na komputerze Windows 10 przy użyciu pierwszego przykładowego kroku, może być konieczne kilku prób zawężenia wyników.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
```

Jeśli nie znasz pełnej nazwy pakietu, być może trzeba będzie kilka razy uruchomić "Get-AppxPackage -name \* YourGueGuess", aby \* go znaleźć. Następnie po nazwie uruchom "$package 1 = Get-AppxPackage -name Actual.PackageName"

Na przykład uruchomienie następującego kodu dla Microsoft Edge zwróci więcej niż jeden wynik, ale z tej listy można zidentyfikować, że pełna nazwa, która jest potrzebna, to Microsoft.MicrosoftEdge.

```powershell
Get-AppxPackage -name *edge*
```

## <a name="package-family-names-for-apps-on-hololens"></a>Nazwy rodzin pakietów dla aplikacji w HoloLens

W przewodniku połączonym powyżej można ręcznie edytować newPolicy.xml i dodawać reguły dla aplikacji, które są zainstalowane tylko w programie HoloLens z nazwami rodzin pakietów. Czasami istnieją aplikacje, których można użyć, które nie znajdują się na komputerze stacjonarnym, które chcesz dodać do zasad.

Poniżej znajduje się lista najczęściej używanych i używanych In-Box dla HoloLens 2 urządzeń.

| Nazwa aplikacji                   | Nazwa rodziny pakietów                                |
|----------------------------|----------------------------------------------------|
| Przeglądarka 3D                  | `Microsoft.Microsoft3DViewer_8wekyb3d8bbwe`          |
| Instalator aplikacji              | `Microsoft.DesktopAppInstaller_8wekyb3d8bbwe`<sup>1</sup>         |
| Kalendarz                   | `microsoft.windowscommunicationsapps_8wekyb3d8bbwe`  |
| Aparat fotograficzny                     | `HoloCamera_cw5n1h2txyewy`                          |
| Cortana                    | `Microsoft.549981C3F5F10_8wekyb3d8bbwe`              |
| Przewodniki dotyczące usługi Dynamics 365        | `Microsoft.Dynamics365.Guides_8wekyb3d8bbwe`         |
| Dynamics 365 Remote Assist | `Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe`      |
| Centrum opinii               | `Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe`         |
| Eksplorator plików              | `c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy` |
| Mail                       | `microsoft.windowscommunicationsapps_8wekyb3d8bbwe`  |
| Sklepie Microsoft            | `Microsoft.WindowsStore_8wekyb3d8bbwe`               |
| Filmy & TV                | `Microsoft.ZuneVideo_8wekyb3d8bbwe`                  |
| OneDrive                   | `microsoft.microsoftskydrive_8wekyb3d8bbwe`          |
| Zdjęcia                     | `Microsoft.Windows.Photos_8wekyb3d8bbwe`             |
| Ustawienia                   | `HolographicSystemSettings_cw5n1h2txyewy`            |
| Porady                       | `Microsoft.HoloLensTips_8wekyb3d8bbwe`               |

- 1 — Blokowanie Instalator aplikacji blokuje tylko aplikację Instalator aplikacji, a nie aplikacje zainstalowane z innych źródeł, takich jak Microsoft Store lub z rozwiązania MDM.

### <a name="using-wdac-to-block-new-microsoft-edge"></a>Blokowanie nowych aplikacji przy użyciu funkcji WDAC Microsoft Edge

W przypadku administratorów IT, którzy chcą zaktualizować swoje zasady [WDAC](windows-defender-application-control-wdac.md) w celu zablokowania nowej [aplikacji](hololens-new-edge.md)Microsoft Edge, należy dodać następujące elementy do zasad.

```xml
<Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" />
```

### <a name="how-to-find-a-package-family-name"></a>Jak znaleźć nazwę rodziny pakietów

Jeśli aplikacji nie ma na tej liście, użytkownik może użyć nazwy Portal urządzeń połączonej z usługą HoloLens 2, na którą zainstalowano aplikację, w celu określenia wartości PackageRelativeID, a następnie uzyskania z tej listy wartości PackageFamilyName.

1. Zainstaluj aplikację na urządzeniu HoloLens 2.

1. Otwórz Ustawienia -> Updates & Security -> Dla deweloperów, włącz tryb  dewelopera, a następnie **portal urządzeń.**

   Aby uzyskać więcej szczegółów i instrukcji, zobacz konfigurowanie i używanie [portalu urządzeń tutaj.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

1. Po Portal urządzeń przejdź do widoków, a **następnie** **wybierz pozycję Aplikacje.**

1. Na panelu Zainstalowane aplikacje użyj listy rozwijanej, aby wybrać zainstalowaną aplikację.

1. Znajdź pakiet PackageRelativeID.

1. Skopiuj znaki aplikacji przed znakiem . Będą to twoje `!` znaki PackageFamilyName.
