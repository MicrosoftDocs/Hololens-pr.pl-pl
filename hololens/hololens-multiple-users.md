---
title: Udostępnianie danych HoloLens wielu osobom
description: Możesz skonfigurować HoloLens współużytkowane przez wiele kont Azure Active Directory lub wielu użytkowników, którzy używają jednego konta.
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
ms.openlocfilehash: 821ef2d17531226177e508b1428af82012c16406e9fbce3ed1a5617c767adfe8
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663077"
---
# <a name="share-your-hololens-with-multiple-people"></a>Udostępnianie danych HoloLens wielu osobom

Często udostępnia się jedną HoloLens wielu osobom lub wiele osób udostępnia zestaw HoloLens urządzeń.  W tym artykule opisano różne sposoby udostępniania urządzenia.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Udostępnianie wielu osobom, z których każda korzysta z własnego konta

**Wymaganie** wstępne: HoloLens musi być uruchomione Windows 10 w wersji 1803 lub nowszej.  HoloLens (1. generacji) należy również uaktualnić do [wersji Windows Holographic for Business](hololens-upgrade-enterprise.md).

Jeśli korzystają oni z własnych kont usługi Azure Active Directory (Azure AD), wielu użytkowników może przechowywać własne ustawienia użytkownika i dane użytkowników na urządzeniu.

Aby upewnić się, że wiele osób może używać własnych kont na HoloLens, wykonaj następujące kroki, aby je skonfigurować:

1. Upewnij się, że na urządzeniu działa Windows 10 w wersji 1803 lub nowszej.
   > [!IMPORTANT]
   > Jeśli używasz urządzenia HoloLens (1. generacji), uaktualnij je do [wersji Windows Holographic for Business.](hololens1-upgrade-enterprise.md)
1. Po skonfigurowaniu urządzenia wybierz pozycję **My work or school owns it** and sign in by an Azure AD account (Moja praca lub szkoła jest jego właścicielem) i zaloguj się przy użyciu konta usługi Azure AD.
1. Po zakończeniu instalacji upewnij się, że ustawienia konta **(** Ustawienia  >  **)** obejmują **innych użytkowników.**

Aby użyć HoloLens, każdy użytkownik musi wykonać następujące kroki:

1. Jeśli inny użytkownik korzysta z urządzenia, wykonaj jedną z następujących czynności:
   - Naciśnij raz przycisk zasilania, aby przejść w stan wstrzymania, a następnie ponownie naciśnij przycisk zasilania, aby powrócić do ekranu blokady
   - HoloLens 2 użytkownicy mogą wybrać kafelek użytkownika z menu Start, aby wylogować bieżącego użytkownika.

1. Użyj poświadczeń konta usługi Azure AD, aby zalogować się na urządzeniu.  
    Jeśli urządzenie jest używane po raz pierwszy, musisz [](hololens-calibration.md) skalibrować HoloLens na własne oczy.

Aby wyświetlić listę użytkowników urządzenia lub usunąć użytkownika z urządzenia, przejdź do Ustawienia   >  **Konta**  >  **innych użytkowników.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Udostępnianie wielu osobom przy użyciu tego samego konta

Wielu użytkowników może również udostępnić HoloLens urządzenia podczas korzystania z jednego konta użytkownika.

W HoloLens **2,** gdy nowy użytkownik po raz pierwszy umieszcza urządzenie na głowy (przy zachowaniu tego samego konta), urządzenie monituje nowego użytkownika o szybkie skalibrowanie i personalizowanie wyświetlania. Urządzenie może przechowywać informacje o pogotowiu, aby w przyszłości urządzenie automatycznie optymalizowało jakość i komfort wyświetlania poszczególnych użytkowników. Użytkownicy nie muszą ponownie skalibrować urządzenia.

**W HoloLens (pierwszej generacji)** użytkownicy, którzy współużytkują konto, będą musieli poprosić o ponowne Ustawienia aplikacji.  Przeczytaj więcej na [temat chłoniaka](hololens-calibration.md).
