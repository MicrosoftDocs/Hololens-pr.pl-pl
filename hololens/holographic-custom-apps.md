---
title: Zarządzanie aplikacjami niestandardowymi dla HoloLens (1. generacja)
description: Dowiedz się, jak instalować, odinstalowywać i ładować obok siebie niestandardowe aplikacje holograficzne na urządzeniach HoloLens przy użyciu Portal urządzeń i Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, sideload, side load, side-load, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: b6769c36f821ee3619ac9b62efd637ac561192bb
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2021
ms.locfileid: "123188852"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a>Zarządzanie aplikacjami niestandardowymi dla HoloLens (1. generacja)

HoloLens obsługuje wiele istniejących aplikacji z Microsoft Store, a także nowe aplikacje opracowane specjalnie dla HoloLens. Ten artykuł koncentruje się na niestandardowych aplikacjach holograficznych.  

Aby uzyskać więcej informacji na temat aplikacji ze sklepu, zobacz [Zarządzanie aplikacjami w sklepie](holographic-store-apps.md).

> [!IMPORTANT]
> Następujące informacje zostały utworzone dla HoloLens (1. generacji), nazywanej również HoloLens Developer Edition w tym czasie. W związku z tym ładowanie bezpośrednio aplikacji za pośrednictwem portalu urządzeń i instalowanie aplikacji za pośrednictwem Visual Studio wtedy były powszechnie spotykane. W przypadku wdrożeń w przedsiębiorstwie nie zalecamy włączania trybu dewelopera, którego używają obie te metody. Jeśli interesuje Cię metoda bezpiecznego wdrażania aplikacji, zapoznaj się z [tematem Zarządzanie aplikacją: Omówienie.](app-deploy-overview.md)
>
> Jeśli szukasz metody instalacji aplikacji dla deweloperów dla urządzeń z systemem HoloLens 2, zapoznaj się z:
>
> - [Portal urządzeń: Instalowanie aplikacji](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Wdrażanie i Visual Studio debugowanie aplikacji przy użyciu programu Visual Studio](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>Instalowanie aplikacji niestandardowych

Możesz instalować własne aplikacje na komputerze HoloLens za pomocą Portal urządzeń lub wdrażając aplikacje z Visual Studio.

### <a name="installing-an-application-package-with-the-device-portal"></a>Instalowanie pakietu aplikacji przy użyciu Portal urządzeń

1. Nawiąz połączenie [Portal urządzeń](/windows/mixed-reality/using-the-windows-device-portal) z docelowym HoloLens.

1. W lewym okienku nawigacji przejdź do **strony** Aplikacje.

1. W **obszarze Pakiet** aplikacji przejdź do pliku appx skojarzonego z aplikacją.

   > [!IMPORTANT]
   > Pamiętaj, aby odwołać się do wszystkich skojarzonych plików zależności i certyfikatów.

1. Wybierz **pozycję Przejdź.**

   > [!div class="mx-imgBorder"]
   > ![Zainstaluj formularz aplikacji w Windows Portal urządzeń na Microsoft HoloLens.](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>Wdrażanie od Microsoft Visual Studio 2015 r.

1. Otwórz rozwiązanie Visual Studio aplikacji (plik sln).

1. Otwórz okno **Właściwości projektu**.

1. Wybierz następującą konfigurację kompilacji: **Master/x86/Remote Machine**.

1. Po wybraniu opcji **Maszyna zdalna:**
   - Upewnij się, że adres wskazuje Wi-Fi adres IP HoloLens.
   - Ustaw uwierzytelnianie **na wartość Universal (Unencrypted Protocol)**.
   
1. Skompilowanie rozwiązania.

1. Aby wdrożyć aplikację z komputera dewelopera na komputerze HoloLens, wybierz **pozycję Maszyna zdalna.** Jeśli masz już istniejącą kompilację na HoloLens, wybierz pozycję **Tak,** aby zainstalować nowszą wersję.  

   ![Wdrażanie aplikacji na maszynie zdalnej do Microsoft HoloLens w Visual Studio.](images/vs2015-remotedeployment.jpg)  
   
1. Aplikacja zostanie automatycznie instalowana i uruchamiana na HoloLens.

Po zainstalowaniu aplikacji znajdziesz ją na liście  Wszystkie aplikacje **(** Uruchom Wszystkie aplikacje  >  ).
