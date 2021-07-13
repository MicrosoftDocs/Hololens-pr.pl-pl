---
title: Intune i Portal firmy
description: Dowiedz się, jak skonfigurować, przypisać i utworzyć wygodne środowisko użytkownika za pomocą usługi Intune, zarządzania urządzeniami przenośnymi i portalu firmy.
keywords: intune, zarządzanie aplikacją, aplikacja, portal firmy, portal, hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b192732f5e7edffaa1d0ab081454e4034c416191
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635504"
---
# <a name="intune--company-portal"></a>Usługa Intune & Portal firmy

Usługa Mobile Zarządzanie urządzeniami (MDM) umożliwia wdrażanie własnych aplikacji niestandardowych za pośrednictwem usługi [Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) bezpośrednio na urządzeniach HoloLens mobilnych. Microsoft Intune to usługa chmurowa, której głównym celem jest zarządzanie urządzeniami mobilnymi (MDM, mobile device management) i zarządzanie aplikacjami mobilnymi (MAM, mobile application management). Usługa Intune jest zawarta w pakiecie [Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security) firmy Microsoft i pozwala użytkownikom na wydajną pracę przy zachowaniu ochrony danych organizacji. Aby dowiedzieć się więcej o usłudze Intune, przeczytaj [Co to jest usługa Intune.](/mem/intune/fundamentals/what-is-intune)

## <a name="setup"></a>Konfigurowanie

1. Upload aplikację do aplikacji biznesowej lub przekaż aplikację niestandardową do dzierżawy usługi Intune. Zobacz też: [Enterprise zarządzania aplikacją.](/windows/client-management/mdm/enterprise-app-management)

2. [Przypisz aplikację do grupy](/mem/intune/apps/apps-deploy). W zależności od wybranego typu przypisania aplikacja może zostać dostarczona automatycznie lub może być łatwo ściągnięta, jeśli masz wybór aplikacji.

> [!NOTE]
> Podczas tworzenia pakietu appx pamiętaj o uwzględnieniu architektury dla wdrażanych urządzeń. HoloLens 2 to arm64, a HoloLens (1. generacja) to x86. Jeśli planujesz środowisko urządzeń mieszanych, możesz uwzględnić oba te pakiety w jednym pakiecie appx.

## <a name="assignment-types"></a>Typy przypisań

Aby aplikacja została automatycznie zainstalowana na urządzeniu po rejestracji, wybierz pozycję Wymagane **dla** tych grup.
Aby udostępnić aplikację do pobrania na urządzeniach zarejestrowanych za pośrednictwem portalu firmy, wybierz pozycję **Dostępne dla zarejestrowanych urządzeń.**

## <a name="end-user-experience"></a>End-User użytkownika

Po skonfigurowaniu konfiguracji w usłudze Intune użytkownicy końcowi mogą odbierać wybrane aplikacje.

Wykonaj następujące kroki, aby automatycznie pobrać aplikacje:

1. Zarejestruj urządzenie w dzierżawie.
2. Po zakończeniu rejestracji urządzenia aplikacja powinna zostać na twoim urządzeniu.
3. Jeśli nie widzisz aplikacji natychmiast, przejdź do strony **Ustawienia** Konta służbowe i przewiń w dół, aby wyświetlić informacje o stanie  >    >    >   zainstalowanej aplikacji.

Jak uzyskać dostęp do aplikacji za pośrednictwem Portal firmy:

1. Otwórz **menu Start i** wybierz pozycję **Microsoft Store**.
2. Wyszukaj **Portal firmy** i pobierz aplikację.
3. Zaloguj się do swojego konta.
4. Wybierz aplikację, którą chcesz otrzymać, i pobierz ją.

> [!Tip]
> Dowiedz się więcej [na temat automatycznego instalowania aplikacji Portal firmy](/mem/intune/apps/company-portal-app) i wdrażania aplikacji oraz zarządzania nimi w [usłudze Intune.](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)
