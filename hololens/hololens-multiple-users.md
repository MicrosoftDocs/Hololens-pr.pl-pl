---
title: Udostępnianie aplikacji HoloLens wielu osobom
description: Możesz skonfigurować HoloLens współużytkowane przez wiele Azure Active Directory kont lub przez wielu użytkowników, którzy używają jednego konta.
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e3acd2665e93e44bce2c5dad467c825dc768bfed
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427473"
---
# <a name="share-your-hololens-with-multiple-people"></a>Udostępnianie aplikacji HoloLens wielu osobom

## <a name="overview"></a>Omówienie
Firmy często inwestują w wiele HoloLens urządzeń. Sposób korzystania z HoloLens jest elastyczny w zależności od indywidualnych wymagań. Oto przykład niektórych interfejsów dla wielu użytkowników: 

- Urządzenia, na których są naliczane opłaty i które mają przewodniki usługi Dynamics 365 i umożliwiają pracownikom otwieranie aplikacji Ustawienia w celu dostosowania do potrzeb usługi Wi-Fi, ale zasady widoczności usługi Page Ustawienia są włączone, aby ograniczyć liczbę stron dostępnych w aplikacji Ustawienia.
- Urządzenia, które są dostępne dla usługi Remote Assist, oraz twoja aplikacja biznesowa, które są wypożyczone do innych firm. Te urządzenia mają kioski, które obejmują tylko Twoją aplikację i usługę Remote Assist. WDAC służy do Ustawienia aplikacji i Microsoft Edge przed uruchomieniem. Do wypożyczenia jest dołączony pakiet baterii USB-C, który dba o pełne opłaty za urządzenia na wiele zmian.
- Wszystkie urządzenia są ustawione na funkcję Autopilot i pobierają wszystkie aplikacje firmowe. Masz już kilka różnych profilów kiosku przeznaczonych dla różnych grup usługi Azure AD. Każdy użytkownik loguje się do HoloLens przy użyciu kluczy FIDO2 i loguje się do własnego konta usługi Azure AD, a jego środowisko jest prezentowane w dostosowany sposób.



## <a name="share-with-multiple-people-each-using-their-own-account"></a>Udostępnianie wielu osobom, z których każda korzysta z własnego konta

**Wymaganie** wstępne: HoloLens musi działać Windows 10 w wersji 1803 lub nowszej.  HoloLens (1. generacji) należy również uaktualnić [do wersji Windows Holographic for Business](hololens-upgrade-enterprise.md).

W przypadku korzystania z własnych Azure Active Directory (Azure AD) wielu użytkowników może przechowywać własne ustawienia użytkownika i dane użytkownika na urządzeniu.

Aby upewnić się, że wiele osób może używać własnych kont na HoloLens, wykonaj następujące kroki, aby je skonfigurować:

1. Upewnij się, że na urządzeniu działa Windows 10 w wersji 1803 lub nowszej.
   > [!IMPORTANT]
   > Jeśli używasz urządzenia HoloLens (1. generacji), [uaktualnij](hololens1-upgrade-enterprise.md)je do wersji Windows Holographic for Business .
1. Po skonfigurowaniu urządzenia wybierz pozycję **Moja praca lub** szkoła jest jego właścicielem i zaloguj się przy użyciu konta usługi Azure AD.
1. Po zakończeniu instalacji upewnij się, że ustawienia konta **(** Ustawienia  >  **Konta**) obejmują **innych użytkowników.**

Aby użyć HoloLens, każdy użytkownik musi wykonać następujące kroki:

1. Jeśli inny użytkownik korzysta z urządzenia, wybierz jedną z następujących opcji:
   - Naciśnij raz przycisk zasilania, aby przejść w stan wstrzymania, a następnie ponownie naciśnij przycisk zasilania, aby powrócić do ekranu blokady
   - HoloLens 2 użytkownicy mogą wybrać kafelek użytkownika z menu Start, aby wylogować bieżącego użytkownika.

1. Użyj poświadczeń konta usługi Azure AD, aby zalogować się na urządzeniu.  
    Jeśli urządzenie jest używane po raz pierwszy, musisz skalibrować dane [HoloLens](hololens-calibration.md) na własne oczy.

Aby wyświetlić listę użytkowników urządzenia lub usunąć użytkownika z urządzenia, przejdź do Ustawienia   >  **Konta**  >  **innych użytkowników.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Udostępnianie wielu osobom przy użyciu tego samego konta

Wielu użytkowników może również udostępnić HoloLens urządzenia podczas korzystania z jednego konta użytkownika.

W HoloLens **2,** gdy nowy użytkownik po raz pierwszy przyłoży urządzenie do głowy (przy zachowaniu tego samego konta, na którym się zalogowano), urządzenie monituje nowego użytkownika o szybkie skalibrowanie i spersonalizowanie wyświetlania. Urządzenie może przechowywać informacje o urządzeniu w taki sposób, aby w przyszłości urządzenie automatycznie optymalizowało jakość i komfort wyświetlania poszczególnych użytkowników. Użytkownicy nie muszą ponownie skalibrować urządzenia.

**W HoloLens (1. generacji)** użytkownicy, którzy współużytkują konto, będą musieli poprosić o ponowne Ustawienia aplikacji.  Przeczytaj więcej na [temat podwłasnych](hololens-calibration.md).