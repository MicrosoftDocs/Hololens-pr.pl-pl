---
title: Zabezpieczenia systemu operacyjnego bez uprawnień administratora
description: Dowiedz się więcej o systemach operacyjnych bez uprawnień administratora, właścicielach urządzeń i zabezpieczeniach na HoloLens rzeczywistości mieszanej.
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
ms.openlocfilehash: ed2d5134a6bc5952063f7dc5dc5d0e31db972b08
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639407"
---
# <a name="admin-less-operating-system"></a>System operacyjny bez uprawnień administratora

HoloLens 2 minimalizuje obszar powierzchni dla podwyższenia poziomu uprawnień, wyłączając obsługę grupy Administratorzy i ograniczając wszystkie kod aplikacji platformy UWP innych firm tak, aby był wykonywany tylko jako użytkownicy standardowi w piaskownicy appContainer. Ten kod ma przyznawany dostęp tylko do tych zasobów chronionych przez funkcje jawnie manifestowane w aplikacji dla użytkownika bez uprawnień, oprócz zasobów dostępnych dla wszystkich urządzeń AppContainer.
Te możliwości aplikacji nadal mają trzywarstwowy model klasyfikacji:
  * Ogólne
  * Z ograniczeniami
  * Windows

Windows mogą również korzystać z piaskownicy AppContainer za pośrednictwem ujścia systemu. Aby dowiedzieć się więcej o platformie uniwersalnej Windows (UWP), zobacz [dokumentację platformy UWP.](/windows/uwp/) Ponadto składniki usługi Windows z większymi potrzebami redukcji uprawnień (takie jak strony zawartości przeglądarki lub parsery) korzystają z piaskownicy Less Privileged AppContainer (LPAC), która odcięła dostęp do zestawu zasobów dostępnych dla wszystkich aplikacji AppContainer.

## <a name="device-owner"></a>Właściciel urządzenia

Ponadto wykonywanie określonych operacji na całym urządzeniu, takich jak dołączanie urządzenia do dzierżawy lub zarządzania użytkownikami, jest dozwolone tylko dla "właścicieli urządzeń". Ta grupa jest wypełniana przez użytkowników na urządzeniu za pomocą jednego z następujących kroków:
  * Pierwszy użytkownik na urządzeniu jest zawsze wyznaczony jako właściciel. 
> [!IMPORTANT]
>W przypadku użytkowników usługi Azure AD wyjątkiem od tej reguły jest to, że jeśli urządzenie jest przyłączone do usługi Azure AD za pośrednictwem rozwiązania Autopilot lub rejestracji zbiorczej w usłudze Azure AD, która korzysta z nie rzeczywistego użytkownika. W takim przypadku pierwszy użytkownik usługi AAD, który ma zalogować się na urządzeniu, może nie zostać automatycznie właścicielem urządzenia, chyba że ma przypisaną rolę "administrator globalny" lub "administrator urządzenia" w Azure Portal. Aby uzyskać więcej informacji, zobacz uwaga poniżej.  

  * Gdy użytkownik ma zostać właścicielem z witryny Ustawienia użytkownika przez innego właściciela urządzenia.
  * Jeśli właściciel urządzenia nie jest już dostępny (opuszcza firmę), a urządzenie jest przyłączone do usługi Azure AD, administrator dzierżawy może zmienić właściciela urządzenia na nowego użytkownika w usłudze Azure Portal. Administratorzy globalni i administratorzy urządzeń dzierżawy usługi Azure AD są niejawnie zalogowani jako właściciele na urządzeniu bez konieczności poprzednich kroków.  

 Administratorzy IT mogą zarządzać tym, do jakich aplikacji mogą uzyskać dostęp za [pośrednictwem zasad](/windows/client-management/mdm/policy-csp-privacy) ochrony prywatności. 

> [!NOTE]
> Aby dowiedzieć się więcej na temat tego, kto jest właścicielem urządzenia przyłączonego do usługi Azure AD, zobacz dokumentację "Przypisywanie administratora lokalnego" (ale przeczytaj "administrator [lokalny"](/azure/active-directory/devices/assign-local-admin) jako "właściciel urządzenia", ponieważ administrator nie istnieje na HoloLens).