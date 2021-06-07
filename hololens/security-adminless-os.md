---
title: Zabezpieczenia systemu operacyjnego bez uprawnień administratora
description: Dowiedz się więcej o systemach operacyjnych bez uprawnień administratora, właścicielach urządzeń i zabezpieczeniach na urządzeniach rzeczywistości mieszanej HoloLens.
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, adminless, admin-less, operating system, admin-less operating system, admin os, admin-less os, hololens 2, hololens2 security,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 972bbc689505d42993cf47d82351ceeb79a0606b
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379717"
---
# <a name="admin-less-operating-system"></a>System operacyjny bez uprawnień administratora

Urządzenie HoloLens 2 minimalizuje obszar powierzchni dla podwyższenia poziomu uprawnień, wyłączając obsługę grupy Administratorzy i ograniczając wykonywanie wszystkich kodu aplikacji platformy uniwersalnej systemu Windows innych firm tylko jako użytkownicy standardowi w piaskownicy appContainer. Ten kod ma dostęp tylko do tych zasobów chronionych przez funkcje jawnie manifestowane w aplikacji dla użytkownika bez uprawnień oprócz zasobów dostępnych dla wszystkich urządzeń AppContainer.
Te możliwości aplikacji nadal mają trzywarstwowy model klasyfikacji:
  * Ogólne
  * Z ograniczeniami
  * Windows

Składniki systemu Windows mogą również korzystać z piaskownicy AppContainer za pośrednictwem funkcji UwPs systemu. Aby dowiedzieć się więcej o platforma uniwersalna systemu Windows (UWP), zobacz [dokumentację platformy uniwersalnej systemu Windows](https://docs.microsoft.com/windows/uwp/). Ponadto składniki systemu Windows z większymi potrzebami dotyczącymi redukcji uprawnień (na przykład stron zawartości przeglądarki lub parserów) korzystają z piaskownicy Less Privileged AppContainer (LPAC), która odcięła dostęp do zestawu zasobów dostępnych dla wszystkich elementów AppContainer.

## <a name="device-owner"></a>Właściciel urządzenia

Ponadto wykonywanie określonych operacji na całym urządzeniu, takich jak dołączanie urządzenia do dzierżawy lub zarządzania użytkownikami, jest dozwolone tylko dla "właścicieli urządzeń". Ta grupa jest wypełniana przez użytkowników na urządzeniu za pomocą jednego z następujących kroków:
  * Pierwszy użytkownik na urządzeniu jest zawsze wyznaczony jako właściciel. 
> [!IMPORTANT]
>W przypadku użytkowników usługi Azure AD wyjątkiem od tej reguły jest to, że jeśli urządzenie jest przyłączone do usługi Azure AD za pośrednictwem rozwiązania Autopilot lub rejestracji zbiorczej w usłudze Azure AD, która używa nie rzeczywistego użytkownika. W takim przypadku pierwszy użytkownik usługi AAD, który loguje się do urządzenia, może nie zostać automatycznie właścicielem urządzenia, chyba że ma przypisaną rolę "administratora globalnego" lub "administratora urządzenia" w Azure Portal. Aby uzyskać więcej informacji, zobacz uwagę poniżej.  

  * Gdy użytkownik ma zostać właścicielem z interfejsu użytkownika ustawień przez innego właściciela urządzenia.
  * Jeśli właściciel urządzenia nie jest już dostępny (opuszcza firmę), a urządzenie jest przyłączone do usługi Azure AD, administrator dzierżawy może zmienić właściciela urządzenia na nowego użytkownika w Azure Portal. Administratorzy globalni i administratorzy urządzeń dzierżawy usługi Azure AD są niejawnie zalogowani na urządzeniu jako właściciele bez konieczności poprzednich kroków.  

 Administratorzy IT mogą zarządzać tym, do jakich aplikacji mogą uzyskać dostęp za [pośrednictwem zasad](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) ochrony prywatności. 

> [!NOTE]
> Aby dowiedzieć się więcej o tym, kto jest właścicielem urządzenia na urządzeniu przyłączony do usługi Azure AD, zobacz dokumentację "Przypisywanie administratora lokalnego" (ale przeczytaj "administrator [lokalny"](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) jako "właściciel urządzenia", ponieważ administrator nie istnieje na urządzeniu HoloLens).