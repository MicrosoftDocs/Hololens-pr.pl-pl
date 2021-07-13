---
title: Przypisany dostęp globalny
description: Rozpoczynanie pracy z naszym przewodnikiem dotyczącym używania OMA-URI dla kiosków z dostępem przypisanym globalnie przy użyciu usługi Intune i projektanta konfiguracji systemu Windows.
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens, hololens 2, przypisany dostęp, kiosk
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d89c630da76060fe6c2a049e5fa162e88779bb99
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640427"
---
# <a name="global-assigned-access--kiosk"></a>Dostęp przypisany globalnie — kiosk

Ta funkcja konfiguruje urządzenie z systemem HoloLens 2 dla trybu kiosku z wieloma aplikacjami, który ma zastosowanie na poziomie systemu, nie ma koligacji z żadną tożsamością w systemie i ma zastosowanie do wszystkich użytkowników, którzy się na nim pojawiają.

> [!NOTE]
> Ta funkcja jest obecnie dostępna tylko w kompilacjach Windows Insider. Jeśli chcesz wypróbować tę funkcję, zanim będzie ogólnie dostępna w wersjach HoloLens, przeczytaj więcej na temat kompilacji Windows [Insider.](hololens-insider.md)

## <a name="how-to-use-global-assigned-access-in-intune"></a>Jak używać przypisanego globalnie dostępu w usłudze Intune?

> [!NOTE]
> Pamiętaj o obszarach oznaczonych literą "<!-". Te obszary będą wymagały wprowadzania modyfikacji na podstawie Twoich preferencji.

1. Utwórz niestandardowy profil konfiguracji urządzenia OMA URI w następujący sposób i zastosuj go HoloLens grupy urządzeń:

    Wartość URI: ./Device/Vendor/MSFT/AssignedAccess/Configuration

    > [!div class="mx-imgBorder"]
    > ![Globalnie przypisany dostęp OMA-URI w usłudze Intune](images/global-assigned-access-omauri.png)

2. Jako wartość zaktualizuj i wklej następującą zawartość:

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a>Jak używać dostępu przypisanego globalnie w programie Windows Configuration Designer?

1. Zaktualizuj i zapisz obiekt blob XML wymieniony powyżej jako plik XML. 

2. Wykonaj kroki opisane w [sekcji Używanie](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)pakietu aprowizowania, aby skonfigurować kiosk z pojedynczą aplikacją lub z wieloma aplikacjami, a w szczególności sekcję "Prov. package, step 2 — Add the kiosk configuration XML file to a provisioning package" (Dodaj plik XML konfiguracji kiosku do pakietu aprowizowania) i odwołaj się do pliku XML zapisanego w poprzednim kroku.

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a>Czy mogę utworzyć konfigurację, w której konfiguracja globalna ma zastosowanie do wszystkich, a oddzielna konfiguracja dotyczy 1 konta usługi Azure AD lub grupy usługi Azure AD? 

Tak, zapoznaj się z poniższym przykładem obiektu blob XML. Profil przypisany do globalnego dostępu jest stosowany do HoloLens, gdy nie zostanie znaleziony konkretny profil dla zalogowaowego użytkownika, dlatego jest to domyślna konfiguracja trybu kiosku dla zalogowaowego użytkownika.
Oto przykład obiektu blob XML, który ma być używany:

> [!NOTE]
> Pamiętaj o wyróżnione obszary oznaczone znakiem `<!-` . Te obszary będą wymagały wprowadzania modyfikacji na podstawie Twoich preferencji.

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a>Wykluczanie właścicieli urządzeń z globalnego przypisanego profilu dostępu

Ta funkcja umożliwia wykluczenie użytkownika, który jest uznawany za["właściciela](security-adminless-os.md)urządzenia" HoloLens z dostępu przypisanego globalnie. Aby móc korzystać z tej funkcji, w obiekcie blob XML dla konfiguracji kiosku z wieloma aplikacjami upewnij się, że dodano wyróżnione wiersze:

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a>Dodatkowe przykłady przypisanego dostępu globalnego

Jest to przykład kiosku z dostępem globalnym, w którym każdy użytkownik, który się do niego insyguje, będzie miał kiosk z wieloma Ustawienia App, Centrum opinii i Microsoft Edge.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

W tym przykładzie jest to kiosk z dostępem przypisanym globalnie, który wyklucza właściciela urządzenia. Gdy inny użytkownik usługi Azure AD się na nim insyguje, będzie miał kiosk z wieloma Ustawienia App, Centrum opinii i Microsoft Edge. Ten kiosk obejmuje również dodatkową konfigurację kiosku dla konta gościa, do którego może się zalogować każda osoba na ekranie blokady. Gdy użytkownik się na konto gościa, będzie mieć kiosk z wieloma Centrum opinii aplikacji.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
