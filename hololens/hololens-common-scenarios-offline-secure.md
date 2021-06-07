---
title: Typowe scenariusze — bezpieczne urządzenie HoloLens 2 w trybie offline
description: Dowiedz się, jak skonfigurować scenariusz bezpiecznego wdrażania i wdrażania aplikacji w trybie offline przy użyciu aprowizowania dla urządzeń HoloLens.
keywords: HoloLens, zarządzanie, offline, bezpieczne w trybie offline
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 8828444a69d7e5d46293340ff771f97eb5eb01e6
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378250"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>Typowe scenariusze — bezpieczne urządzenie HoloLens 2 w trybie offline

## <a name="overview"></a>Omówienie

Ten przewodnik zawiera wskazówki dotyczące stosowania przykładowego pakietu aprowizowania, który zablokuje urządzenie HoloLens 2 do użycia w bezpiecznych środowiskach z następującymi ograniczeniami:

-   Wyłącz sieć Wi-Fi.
-   Wyłącz funkcję BlueTooth.
-   Wyłącz mikrofony.
-   Uniemożliwia dodawanie lub usuwanie pakietów aprowizowania.
-   Żaden użytkownik nie może włączyć żadnego z powyższych składników z ograniczeniami.

[![Scenariusz zabezpieczenia w trybie ](./images/deployment-guides-revised-scenario-c-01.png) offline](./images/deployment-guides-revised-scenario-c-01.png#lightbox)

## <a name="prepare"></a>Przygotowywanie

Windows 10 konfiguracji komputera
1. [Pobierz najnowszy plik systemu operacyjnego HoloLens 2](https://aka.ms/hololens2download) bezpośrednio na komputer. 
   1. Obsługa tej konfiguracji jest uwzględniona w kompilacji 19041.1117 i powyższych.
1. Pobierz/zainstaluj narzędzie Advanced Recovery Companion (ARC) [z](https://www.microsoft.com/store/productId/9P74Z35SFRS8) Microsoft Store na komputer
1. Pobierz/zainstaluj najnowsze narzędzie [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) z Microsoft Store na komputerze.
1. [Pobierz folder OfflineSecureHL2_Sample z plikami projektu,](https://aka.ms/HoloLensDocs-SecureOfflineSample) aby skompilować plik PPKG.
1. Przygotuj aplikację [biznesową w trybie offline do wdrożenia ppkg.](app-deploy-provisioning-package.md) 


## <a name="configure"></a>Konfigurowanie

Tworzenie bezpiecznego pakietu aprowizowania konfiguracji

1. Uruchom narzędzie WCD na komputerze.
1. Wybierz **pozycję Plik -> Otwórz projekt.**
  1. Przejdź do lokalizacji wcześniej zapisanego folderu OfflineSecureHL2_Sample i wybierz pozycję: OfflineSecureHL2_Sample.icdproj.xml
1. Projekt powinien zostać otwarty i powinna zostać wyświetlona lista Dostępnych dostosowań:

   > [!div class="mx-imgBorder"]
   > ![Zrzut ekranu przedstawiający pakiet konfiguracyjnych otwarty w UCD](images/offline-secure-sample-wcd.png)

   Konfiguracje ustawione w tym pakiecie aprowizowania:
   
   |     Element                                                |     Ustawienie                       |     Opis                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     Konta/użytkownicy                                    |     Nazwa użytkownika lokalnego & hasło    |     W przypadku tych urządzeń w trybie offline należy ustawić i udostępnić wszystkim użytkownikom urządzenia pojedynczą nazwę użytkownika i hasło.          |
   |     Pierwsze środowisko / HoloLens / SkipCalibration       |     Prawda                          |     Pomija pominięcia tylko podczas początkowej konfiguracji urządzenia                                                                             |
   |     Pierwsze środowisko / HoloLens / SkipTraining          |     Prawda                          |     Pomija trenowania urządzenia podczas początkowej konfiguracji urządzenia                                                                              |
   |     Pierwsze środowisko / HoloLens / WiFi                  |     Prawda                          |     Pomija Wi-Fi konfiguracji podczas początkowej konfiguracji urządzenia                                                                                 |
   |     Policies/Connectivity/AllowBluetooth                |     Nie                            |     Wyłącza funkcję Bluetooth                                                                                                             |
   |     Zasady/środowisko/AllowCortana                    |     Nie                            |     Wyłącza Cortanę (aby wyeliminować potencjalne problemy, ponieważ mikrofony są wyłączone)                                          |
   |     Policies/MixedReality/MicrophoneDisabled            |     Tak                           |     Wyłącza mikrofon                                                                                                            |
   |     Zasady/Prywatność/LetAppsAccessLocation              |     Wymusz odmowę                    |     Uniemożliwia aplikacjom próby uzyskania dostępu do danych lokalizacji (aby wyeliminować potencjalne problemy, ponieważ śledzenie lokalizacji jest wyłączone)    |
   |     Zasady/Prywatność/LetAppsAccessMicrophone            |     Wymusz odmowę                    |     Uniemożliwia aplikacjom próby uzyskania dostępu do mikrofonów (aby wyeliminować potencjalne problemy, ponieważ mikrofony są wyłączone)           |
   |     Policies/Security/AllowAddProvisioningPackage       |     Nie                            |     Uniemożliwia dodawanie pakietów aprowizowania, które mogą próbować przesłonić zablokowane zasady.                         |
   |     Policies/Security/AllowRemoveProvisioningPackage    |     Nie                            |     Uniemożliwia usunięcie tego zablokowanego pakietu aprowizowania przez wszystkie osoby.                                                           |
   |     Zasady/System/AllowLocation                       |     Nie                            |     Uniemożliwia urządzeniu śledzenie danych lokalizacji.                                                                        |
   |     Policies/WiFi/AllowWiFi                             |     Nie                            |     Wyłącza Wi-Fi                                                                                                                 |

1. W obszarze Ustawienia środowiska uruchomieniowego wybierz **pozycję Accounts / Users / UserName: Holo / Password**.

   Zanotuj hasło i w razie potrzeby zresetuj je.

1. Przejdź do aplikacji UniversalAppInstall/UserContextApp i skonfiguruj aplikację [LOB,](app-deploy-provisioning-package.md) która będzie wdrażana na tych urządzeniach.

   > [!div class="mx-imgBorder"]
   > ![Zrzut ekranu przedstawiający miejsce dodawania aplikacji w udaniu WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)

1. Po zakończeniu wybierz przycisk "Eksportuj" i postępuj zgodnie ze wszystkimi monitami do momentu utworzenia pakietu aprowizowania.

   > [!div class="mx-imgBorder"]
   > ![Zrzut ekranu przedstawiający przycisk Eksportuj dla tego pakietu w Uakiecie WCD.](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>Wdróż

1. Podłącz hl2 do komputera Windows 10 za pośrednictwem kabla USB.
1. Uruchom narzędzie ARC i wybierz pozycję **HoloLens 2**

   ![Początkowy ekran czystego ukośnika HoloLens 2](images/ARC2.png)

1. Na następnym ekranie wybierz opcję **Ręczne wybieranie pakietu.**

   ![Ekran informacyjny urządzenia HoloLens 2 ARC](images/arc_device_info.png)

1. Przejdź do wcześniej pobranego pliku ffu i wybierz pozycję **Otwórz**.
1. Na stronie Ostrzeżenie wybierz pozycję **Kontynuuj.**

   ![Ekran ostrzegawczy urządzenia HoloLens 2 ARC](images/arc_warning.png)

1. Poczekaj, aż narzędzie ARC ukończy instalację systemu operacyjnego HoloLens 2.
1. Po zakończeniu instalacji urządzenia i jego uruchamianiu z komputera przejdź do folderu Eksplorator plików i skopiuj wcześniej zapisany plik PPKG do folderu urządzenia.

   > [!div class="mx-imgBorder"]
   > ![Plik PPKG na komputerze w Eksplorator plików okna.](images/offline-secure-file-explorer.png)

1. Na urządzeniach HoloLens 2 naciśnij następujące kombinacje przycisków, aby uruchomić pakiet aprowizowania: naciśnij jednocześnie pozycję Volume **Down** (Wolumin w dół) **i Power Button (Przycisk** zasilania).
1. Zostanie wyświetlony monit o zastosowanie pakietu aprowizowania, wybierz pozycję **Potwierdź**
1. Po zakończeniu pakietu aprowizowania wybierz przycisk **OK.**
1. Następnie powinien zostać wyświetlony monit o zalogowanie się na urządzeniu przy użyciu udostępnionego konta lokalnego i hasła.

## <a name="maintain"></a>Obsługa

W przypadku tej konfiguracji zaleca się ponowne uruchomienie powyższego procesu i reflashowanie urządzenia za pomocą narzędzia ARC oraz zastosowanie nowego narzędzia PPKG w celu aktualizacji systemu operacyjnego i/lub aplikacji.
