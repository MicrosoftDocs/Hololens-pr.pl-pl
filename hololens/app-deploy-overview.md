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
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635555"
---
# <a name="app-management-overview"></a>Zarządzanie aplikacją: Omówienie

Aplikacje można wdrażać w czterech różnych ścieżkach: **mobile Zarządzanie urządzeniami (MDM),** **Microsoft Store dla Firm,** **Microsoft Store** lub przez zainstalowanie ich za pomocą **aprowizowania**.

## <a name="mobile-device-management-mdm"></a>Mobile Zarządzanie urządzeniami (MDM)

Rozwiązanie MDM umożliwia twórcom i administratorom IT prywatną automatyczną instalację (wypychanie) własnych aplikacji biznesowych lub kupowanie aplikacji za pośrednictwem sklepu dla grupy użytkowników. HoloLens działają najlepiej z usługą Microsoft Endpoint Manager (Intune) do [zarządzania aplikacją.](app-deploy-intune.md) Usługa Intune oferuje również użytkownikom wędszą kontrolę nad aplikacjami zarządzanymi przez it za pośrednictwem Portal firmy do pobrania.

> [!NOTE]
> Poniższe instrukcje są dostępne dla użytkowników, którzy chcą zarządzać aplikacjami za pomocą usługi Intune. Firma Microsoft zaleca używanie usługi Intune do zarządzania aplikacją i urządzeniami.

Rozwiązanie mobile Zarządzanie urządzeniami (MDM) ma zastosowanie do:

* Wdrożone rozwiązanie MDM i Portal firmy
* Aplikacje biznesowe (nie publiczna)
* Ręczna instalacja dostępnych aplikacji za pośrednictwem Portal firmy
* Wypychanie przez administratora za pośrednictwem zasad zarządzania urządzeniami przenośnymi
* Automatyczna aktualizacja za pośrednictwem rozwiązania MDM

## <a name="microsoft-store-for-business"></a>Sklep Microsoft dla Firm

Ten [Microsoft Store dla Firm](app-deploy-store-business.md) dla osób decyzyjnych IT i administratorów w firmach w celu znalezienia, pozyskania i rozpowszechniania bezpłatnych i płatnych aplikacji oraz zarządzania nimi. Administratorzy IT mogą zarządzać Microsoft Store i prywatnymi aplikacjami biznesowymi w jednym spisie oraz przypisywać i ponownie używać licencji zgodnie z potrzebami. Aby uzyskać więcej informacji, odwiedź [stronę Prerequisites for using the Microsoft Store dla Firm](/microsoft-store/prerequisites-microsoft-store-for-business).

Ten Microsoft Store dla Firm ma zastosowanie do:

* Aplikacje publiczne lub biznesowe
* Automatyczna instalacja wymaganych aplikacji za pośrednictwem skojarzenia MDM
* Użytkownik ręcznie pobiera aplikacje
* Automatyczna aktualizacja

## <a name="microsoft-store-apps"></a>Aplikacje ze Sklepu Microsoft

Ten Microsoft Store to, że decydenci IT i administratorzy w firmach mogą znaleźć, pozyskiwać i rozpowszechniać aplikacje publiczne oraz zarządzać nimi.

Ten Microsoft Store ma zastosowanie do:

* Tylko aplikacje publiczne
* Użytkownik ręcznie pobiera aplikacje
* Automatyczna aktualizacja w przypadku połączenia z Internetem

Aby uzyskać więcej informacji, odwiedź stronę Holographic Store Apps ( [Aplikacje ze sklepu Holographic Store).](/hololens/holographic-store-apps)

## <a name="install-via-provisioning-packages"></a>Instalowanie za pośrednictwem pakietów aprowingu

[Pakiety aprowizowania](app-deploy-provisioning-package.md) umożliwiają instalowanie niestandardowych lub biznesowych aplikacji, dzięki czemu informatycy i administratorzy mogą szybko instalować aplikacje na urządzeniach lokalnych za pośrednictwem portu USB. Tę instalację można wykonać bez połączenia internetowego i dla dowolnego typu tożsamości.

Instalowanie za pomocą pakietów aprowizowania ma zastosowanie w przypadku:

* Aplikacje biznesowe/samodzielnie opracowane (nie publiczne)
* Aplikacje publiczne (jeśli dostępny jest instalator offline)
* Tylko ładowanie boczne USB
* Brak automatycznej aktualizacji (wymaga ręcznej aktualizacji za pośrednictwem pakietu aprowizowania)

## <a name="install-apps-on-hololens-2-via-app-installer"></a>Instalowanie aplikacji na HoloLens 2 za pośrednictwem Instalator aplikacji

Użytkownicy usługi [Instalator aplikacji](app-deploy-app-installer.md) mogą mieć środowisko, które jest proste do instalowania aplikacji na urządzeniach lokalnych lub udostępniania aplikacji innej osobie, która nie jest zaznajomina z innymi metodami instalowania aplikacji na HoloLens. Można to zrobić bez konieczności włączania trybu dewelopera ani używania Portal urządzeń. Jest to prosta metoda dystrybucji całkowicie sbudowaną aplikacji. Bez względu na to, czy chcesz po prostu zmienić wersję aplikacji na wersję demonstracyjną dla innego użytkownika z HoloLens, czy chcesz wdrożyć aplikację, ta metoda działa łatwo.

Instalowanie za pośrednictwem Instalator aplikacji ma zastosowanie w przypadku:

* Aplikacje biznesowe/samodzielnie opracowane (nie publiczne)
* Tylko ładowanie boczne
* Nie wymaga trybu dewelopera ani portalu urządzeń
* Łatwość instalacji przez użytkownika końcowego
