---
title: Zarządzanie aplikacjami niestandardowymi dla HoloLens (1. generacja)
description: Dowiedz się, jak instalować, odinstalowywać i ładować po stronie niestandardowe aplikacje holograficzne HoloLens urządzeniach przy użyciu Portal urządzeń i Visual Studio.
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
ms.openlocfilehash: a179032978e1fc062273a6754e3b0a1ad50a5211
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635912"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a>Zarządzanie aplikacjami niestandardowymi dla HoloLens (1. generacja)

HoloLens obsługuje wiele istniejących aplikacji z Microsoft Store, a także nowe aplikacje opracowane specjalnie dla HoloLens. Ten artykuł koncentruje się na niestandardowych aplikacjach holograficznych.  

Aby uzyskać więcej informacji na temat aplikacji ze sklepu, zobacz [Zarządzanie aplikacjami w sklepie](holographic-store-apps.md).

> [!IMPORTANT]
> Następujące informacje zostały utworzone dla HoloLens (1. generacji), nazywanej również HoloLens Developer Edition w tym czasie. W związku z tym ładowanie bezpośrednio aplikacji za pośrednictwem portalu urządzeń i instalowanie aplikacji za pośrednictwem Visual Studio wtedy były powszechnie spotykane. W przypadku wdrożeń dla przedsiębiorstw nie zalecamy włączania trybu dewelopera, którego używają obie te metody. Jeśli interesuje Cię metoda bezpiecznego wdrażania aplikacji, zapoznaj się z naszym [tematem Zarządzanie aplikacją: Omówienie.](app-deploy-overview.md)
>
> Jeśli szukasz metody instalacji aplikacji dla deweloperów dla urządzeń z systemem HoloLens 2, zapoznaj się z tematem:
>
> - [Portal urządzeń: Instalowanie aplikacji](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Wdrażanie i Visual Studio debugowanie aplikacji przy użyciu usługi Visual Studio](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>Instalowanie aplikacji niestandardowych

Możesz instalować własne aplikacje na HoloLens za pomocą Portal urządzeń lub wdrażając aplikacje z Visual Studio.

### <a name="installing-an-application-package-with-the-device-portal"></a>Instalowanie pakietu aplikacji przy użyciu Portal urządzeń

1. Ustanów połączenie [z Portal urządzeń](/windows/mixed-reality/using-the-windows-device-portal) do docelowego HoloLens.

1. W lewym okienku nawigacji przejdź do **strony** Aplikacje.

1. W **obszarze Pakiet aplikacji** przejdź do pliku appx skojarzonego z aplikacją.

   > [!IMPORTANT]
   > Pamiętaj, aby odwołać się do wszystkich skojarzonych plików zależności i certyfikatów.

1. Wybierz **pozycję Przejdź.**

   > [!div class="mx-imgBorder"]
   > ![Instalowanie formularza aplikacji w Windows Portal urządzeń na Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>Wdrażanie od Microsoft Visual Studio 2015 r.

1. Otwórz rozwiązanie aplikacji Visual Studio (plik sln).

1. Otwórz okno **Właściwości projektu**.

1. Wybierz następującą konfigurację kompilacji: **Master/x86/Remote Machine**.

1. Po wybraniu opcji **Maszyna zdalna:**
   - Upewnij się, że adres wskazuje Wi-Fi adres IP HoloLens.
   - Ustaw uwierzytelnianie na **wartość Universal (Unencrypted Protocol).**
   
1. Skompilowanie rozwiązania.

1. Aby wdrożyć aplikację z komputera dewelopera na komputerze HoloLens, wybierz **pozycję Komputer zdalny.** Jeśli masz już istniejącą kompilację na HoloLens, wybierz pozycję **Tak,** aby zainstalować nowszą wersję.  

   ![Wdrażanie na maszynie zdalnej dla aplikacji do Microsoft HoloLens w Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. Aplikacja zostanie automatycznie instalowana i uruchamiana na HoloLens.

Po zainstalowaniu aplikacji znajdziesz ją na liście  Wszystkie aplikacje ( Uruchom  >  **Wszystkie aplikacje**).
