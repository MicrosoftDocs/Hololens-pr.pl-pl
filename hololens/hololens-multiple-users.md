---
title: Udostępnianie urządzenia HoloLens wielu osobom
description: Urządzenie HoloLens można skonfigurować tak, aby było współużytowane przez Azure Active Directory kont lub wielu użytkowników, którzy używają jednego konta.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378357"
---
# <a name="share-your-hololens-with-multiple-people"></a>Udostępnianie urządzenia HoloLens wielu osobom

Często udostępnia się jeden urządzeniu HoloLens wielu osobom lub wiele osób udostępnia zestaw urządzeń HoloLens.  W tym artykule opisano różne sposoby udostępniania urządzenia.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Udostępnianie wielu osobom, z których każda korzysta z własnego konta

**Wymaganie** wstępne: na urządzeniu HoloLens musi Windows 10 w wersji 1803 lub nowszej.  Urządzenie HoloLens (1. generacji) należy również uaktualnić [do Windows Holographic for Business](hololens-upgrade-enterprise.md).

Jeśli korzystają oni z własnych kont usługi Azure Active Directory (Azure AD), wielu użytkowników może przechowywać własne ustawienia użytkownika i dane użytkowników na urządzeniu.

Aby upewnić się, że wiele osób może używać własnych kont na urządzeniach HoloLens, wykonaj następujące kroki, aby je skonfigurować:

1. Upewnij się, że na urządzeniu działa Windows 10 w wersji 1803 lub nowszej.
   > [!IMPORTANT]
   > Jeśli używasz urządzenia HoloLens (1. generacji), uaktualnij je do [wersji Windows Holographic for Business](hololens1-upgrade-enterprise.md).
1. Po skonfigurowaniu urządzenia wybierz pozycję **My work or school owns it** and sign in by an Azure AD account (Moja praca lub szkoła jest jego właścicielem) i zaloguj się przy użyciu konta usługi Azure AD.
1. Po zakończeniu instalacji upewnij się, że ustawienia konta (**Konta**  >  **ustawień**) obejmują **innych użytkowników.**

Aby korzystać z urządzenia HoloLens, każdy użytkownik musi wykonać następujące kroki:

1. Jeśli inny użytkownik korzysta z urządzenia, wykonaj jedną z następujących czynności:
   - Naciśnij raz przycisk zasilania, aby przejść w stan wstrzymania, a następnie ponownie naciśnij przycisk zasilania, aby powrócić do ekranu blokady
   - Użytkownicy urządzenia HoloLens 2 mogą wybrać kafelek użytkownika z menu Start, aby wylogować bieżącego użytkownika.

1. Użyj poświadczeń konta usługi Azure AD, aby zalogować się na urządzeniu.  
    Jeśli urządzenie jest używane po raz pierwszy, musisz [](hololens-calibration.md) skalibrować urządzenie HoloLens na własne oczy.

Aby wyświetlić listę użytkowników urządzenia lub usunąć użytkownika z urządzenia, przejdź do tematu Ustawienia   >  **Konta**  >  **Inni użytkownicy.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Udostępnianie wielu osobom przy użyciu tego samego konta

Wielu użytkowników może również udostępniać urządzenie HoloLens przy użyciu jednego konta użytkownika.

Na urządzeniu **HoloLens 2,** gdy nowy użytkownik po raz pierwszy włoży urządzenie na łeb (przy zachowaniu tego samego konta), urządzenie monituje nowego użytkownika o szybkie skalibrowanie i personalizowanie wyświetlania. Urządzenie może przechowywać informacje o pogotowiu, aby w przyszłości urządzenie automatycznie optymalizowało jakość i komfort wyświetlania poszczególnych użytkowników. Użytkownicy nie muszą ponownie skalibrować urządzenia.

**Na urządzeniach HoloLens (1. generacji)** użytkownicy, którzy współużytkują konto, będą musieli poprosić o ponowną ujedną w aplikacji Ustawienia.  Przeczytaj więcej na [temat chłoniaka](hololens-calibration.md).
