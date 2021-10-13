---
title: Sklep Microsoft dla Firm
description: Dowiedz się, jak pracować z Microsoft Store dla Firm, aby publikować aplikacje rzeczywistości mieszanej w firmie.
keywords: Microsoft Store dla Firm, msfb, wdrażanie aplikacji, sklep
author: evmill
ms.author: v-evmill
ms.date: 10/13/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
ms.openlocfilehash: 5bc719539aaa254b8aacb05e24554152231f7e5a
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924322"
---
# <a name="microsoft-store-for-business"></a>Sklep Microsoft dla Firm

Aplikacja [Microsoft Store dla Firm](/microsoft-store/microsoft-store-for-business-overview) jest przeznaczona głównie dla osób decyzyjnych IT i administratorów w firmach lub organizacjach w elastyczny sposób na znajdowanie, pozyskiwanie i dystrybuowanie bezpłatnych i płatnych aplikacji na wybranych rynkach oraz zarządzanie nimi na wybranych rynkach do Windows 10 urządzeń w ilości. 

Możesz zarządzać Microsoft Store i prywatnymi aplikacjami biznesowymi w jednym spisie oraz przypisywać i ponownie używać licencji zgodnie z potrzebami. Możesz również wybrać najlepszą metodę dystrybucji dla swojej organizacji: bezpośrednie przypisywanie aplikacji do poszczególnych osób i zespołów, publikowanie aplikacji na stronach prywatnych w programie Microsoft Store lub łączenie się z rozwiązaniami do zarządzania, aby uzyskać więcej opcji.

Gdy Microsoft Store dla Firm przez użytkownika końcowego, uruchomi aplikację Microsoft Store aplikację. Po jego zakończeniu użytkownik będzie mógł wybrać kartę z nazwą organizacji, a następnie zostanie im przedstawiona aplikacja dostępna dla użytkownika lub tego urządzenia.

> [!Note]
> Microsoft Store dla Firm automatycznie pobiera (wypychać) aplikacji na urządzenia. Jednak aplikacje z serwera Microsoft Store dla Firm można skojarzyć z serwerem zarządzania urządzeniami (MDM), aby kierować aplikacje do urządzeń i synchronizować je.

Odwiedź następujące strony, aby dowiedzieć się więcej o tym, jak używać Microsoft Store dla Firm:

* [Poziomy uprawnień używanych do instalowania aplikacji](/mem/intune/configuration/device-restrictions-windows-holographic#app-store)
* [Jak dodać aplikację do sklepu Store dla Firm](/mem/intune/apps/store-apps-windows)
* [Jak przypisywać aplikacje do grup pracowników](/mem/intune/apps/windows-store-for-business)

Aby skojarzyć Microsoft Store dla Firm, odwiedź [stronę Kojarzenie aplikacji Microsoft Store dla Firm z usługą Intune.](/mem/intune/apps/windows-store-for-business#associate-your-microsoft-store-for-business-account-with-intune)

> [!Tip]
> Dowiedz się więcej na temat dystrybucji aplikacji [w trybie offline](/microsoft-store/distribute-offline-apps) w przypadku korzystania z aplikacji, takich jak Advanced Recovery Companion (ARC) i Windows Configuration Designer (WCD).

## <a name="use-only-private-store-apps-for-microsoft-store"></a>Używaj tylko aplikacji ze sklepu prywatnego dla Microsoft Store

- Wprowadzono w [Windows Holographic w wersji 21H2.](hololens-release-notes.md#windows-holographic-version-21h2)

Zasady RequirePrivateStoreOnly zostały włączone dla HoloLens. Te zasady umożliwiają skonfigurowanie Microsoft Store tak, aby wyświetlała tylko magazyn prywatny skonfigurowany dla twojej organizacji. Ograniczenie dostępu tylko do aplikacji, które zostały udostępnione.

Dowiedz się więcej o [applicationmanagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

## <a name="smart-retry-for-app-updates"></a>Inteligentne ponawianie próby aktualizacji aplikacji

- Wprowadzono w [Windows Holographic w wersji 21H2.](hololens-release-notes.md#windows-holographic-version-21h2)

Teraz włączone dla usługi HoloLens to nowe zasady, które umożliwiają administratorom IT ustawienie cyklicznej lub jednodniowej daty ponownego uruchomienia aplikacji, których aktualizacja nie powiodła się z powodu używania aplikacji, co umożliwia zastosowanie aktualizacji. Można je ustawić na podstawie kilku różnych wyzwalaczy, takich jak zaplanowany czas lub logowanie. Aby dowiedzieć się więcej na temat używania tych zasad, zobacz [ApplicationManagement/ScheduleForceRestartForUpdateFailures.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)