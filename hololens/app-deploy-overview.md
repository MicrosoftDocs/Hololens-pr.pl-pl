---
title: Omówienie — zarządzanie aplikacją
description: Rozpoczynanie pracy z omówieniem zarządzania aplikacjami rzeczywistości mieszanej za pomocą zarządzania urządzeniami przenośnymi, sklepu Microsoft Store dla Firm i pakietów aprowizowania.
keywords: HoloLens, użytkownik, konto, aplikacja, zarządzanie aplikacją,
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ca87f34718319d489b69ba33ad24731628d87fac
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428485"
---
# <a name="app-management-overview"></a>Zarządzanie aplikacją: Omówienie

Aplikacje można wdrażać w czterech różnych ścieżkach: **mobile Zarządzanie urządzeniami (MDM),** **Microsoft Store dla Firm,** **Microsoft Store**, lub instalując je za pomocą **aprowizowania**.

## <a name="mobile-device-management-mdm"></a>Mobile Zarządzanie urządzeniami (MDM)

Rozwiązanie MDM umożliwia twórcom i administratorom IT prywatną autoinstalowanie (wypychanie) własnych aplikacji biznesowych lub kupowanie aplikacji za pośrednictwem sklepu dla grupy użytkowników. HoloLens działają najlepiej z usługą Microsoft Endpoint Manager (Intune) w celu [zarządzania aplikacją.](app-deploy-intune.md) Usługa Intune oferuje również użytkownikom precyzyjne sterowanie aplikacjami zarządzanymi przez system IT za pośrednictwem Portal firmy do pobrania.

> [!NOTE]
> Poniższe instrukcje są dostępne dla użytkowników, którzy chcą zarządzać aplikacjami za pomocą usługi Intune. Firma Microsoft zaleca używanie usługi Intune do zarządzania aplikacją i urządzeniami.

Rozwiązanie mobile Zarządzanie urządzeniami (MDM) ma zastosowanie do:

* Wdrożone rozwiązanie MDM i Portal firmy
* Aplikacje biznesowe (niepublicznie)
* Ręczna instalacja dostępnych aplikacji za pośrednictwem Portal firmy
* Wypychanie przez administratora za pośrednictwem zasad zarządzania urządzeniami przenośnymi
* Automatyczna aktualizacja za pośrednictwem rozwiązania MDM

## <a name="microsoft-store-for-business"></a>Sklep Microsoft dla Firm

Ten [Microsoft Store dla Firm](app-deploy-store-business.md) umożliwia twórcom i administratorom IT w firmach znajdowanie, pozyskiwanie i rozpowszechnianie bezpłatnych i płatnych aplikacji oraz zarządzanie nimi. Administratorzy IT mogą zarządzać Microsoft Store i prywatnymi aplikacjami biznesowymi w jednym spisie oraz przypisywać i ponownie używać licencji zgodnie z potrzebami. Aby uzyskać więcej informacji, odwiedź [stronę Wymagania wstępne dotyczące korzystania z Microsoft Store dla Firm](/microsoft-store/prerequisites-microsoft-store-for-business).

Ten Microsoft Store dla Firm ma zastosowanie do:

* Aplikacje publiczne lub biznesowe
* Automatyczna instalacja wymaganych aplikacji za pośrednictwem skojarzenia MDM
* Użytkownik ręcznie pobiera aplikacje
* Automatyczna aktualizacja

## <a name="microsoft-store-apps"></a>Aplikacje ze Sklepu Microsoft

Ten Microsoft Store to, że decydenci i administratorzy IT w firmach mogą znaleźć, pozyskiwać i rozpowszechniać aplikacje publiczne oraz zarządzać nimi.

Ten Microsoft Store ma zastosowanie do:

* Tylko aplikacje publiczne
* Użytkownik ręcznie pobiera aplikacje
* Automatyczna aktualizacja w przypadku połączenia z Internetem

Aby uzyskać więcej informacji, odwiedź [stronę Aplikacje ze sklepu Holographic Store.](/hololens/holographic-store-apps)

## <a name="install-via-provisioning-packages"></a>Instalowanie za pośrednictwem pakietów aprowizowania

[Pakiety aprowizowania](app-deploy-provisioning-package.md) umożliwiają instalowanie niestandardowych lub biznesowych aplikacji, dzięki czemu informatycy i administratorzy mogą szybko instalować aplikacje na urządzeniach lokalnych za pośrednictwem portu USB. Tę instalację można wykonać bez połączenia z Internetem i dla dowolnego typu tożsamości.

Instalowanie za pomocą pakietów aprowizowania ma zastosowanie do:

* Aplikacje biznesowe/samodzielnie opracowane (nie publiczne)
* Aplikacje publiczne (jeśli dostępny jest instalator offline)
* Tylko ładowanie boczne USB
* Brak automatycznej aktualizacji (wymaga ręcznego aktualizowania za pośrednictwem pakietu aprowingu)

## <a name="install-apps-on-hololens-2-via-app-installer"></a>Instalowanie aplikacji na HoloLens 2 za pośrednictwem Instalator aplikacji

Użytkownicy aplikacji [Instalator aplikacji](app-deploy-app-installer.md) mogą mieć środowisko, które jest proste do instalowania aplikacji na urządzeniach lokalnych lub udostępniania aplikacji innej osobie, która nie jest zaznajomina z innymi metodami instalowania aplikacji na HoloLens. Można to zrobić bez konieczności włączania trybu dewelopera lub używania Portal urządzeń. Jest to prosta metoda dystrybucji całkowicie sbudowaną aplikacji. Bez względu na to, czy chcesz po prostu pokazać aplikację inowi użytkownikowi z HoloLens, czy chcesz wdrożyć aplikację, ta metoda działa łatwo.

Instalowanie za Instalator aplikacji ma zastosowanie w przypadku:

* Aplikacje biznesowe/samodzielnie opracowane (nie publiczne)
* Tylko ładowanie boczne
* Nie wymaga trybu dewelopera ani portalu urządzenia
* Łatwa instalacja przez użytkownika końcowego
