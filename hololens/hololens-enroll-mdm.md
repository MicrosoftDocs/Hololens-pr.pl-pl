---
title: Rejestrowanie HoloLens zarządzania urządzeniami przenośnymi
description: Dowiedz się, jak zarejestrować HoloLens zarządzania urządzeniami przenośnymi (MDM) w celu łatwiejszego zarządzania wieloma urządzeniami.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/15/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: fa114633afe70a11a180c67fedbd40eb423ece99
ms.sourcegitcommit: 19d1abb7589cebf14ba45e830f49224f7b4fcfe9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/15/2021
ms.locfileid: "130034182"
---
# <a name="enroll-hololens-in-mdm"></a>Rejestrowanie HoloLens zarządzania urządzeniami przenośnymi

Możesz zarządzać wieloma urządzeniami Microsoft HoloLens jednocześnie przy użyciu rozwiązań takich [jak Microsoft Intune](/intune/windows-holographic-for-business). Będzie można zarządzać ustawieniami, wybierać aplikacje do instalowania i ustawiać konfiguracje zabezpieczeń dostosowane do potrzeb organizacji. Zobacz [Manage devices running Windows Holographic with Microsoft Intune](/intune/windows-holographic-for-business)(Zarządzanie urządzeniami z systemem Windows Holographic przy użyciu programu Microsoft Intune), dostawcy usług konfiguracji [(CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)obsługiwani w usłudze Windows Holographic oraz zasady obsługiwane przez program [Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> Zarządzanie urządzeniami przenośnymi (MDM), w tym funkcje sieci VPN, funkcji BitLocker i trybu kiosku, jest dostępne tylko podczas uaktualniania do [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)

## <a name="requirements"></a>Wymagania

 Aby zarządzać urządzeniami przenośnymi, organizacja musi mieć Zarządzanie urządzeniami mobile HoloLens (MDM). Dostawcą rozwiązania MDM może być Microsoft Intune lub dostawca innej firmy, który korzysta z interfejsów API zarządzania urządzeniami przenośnymi firmy Microsoft.

## <a name="different-ways-to-enroll"></a>Różne sposoby rejestrowania

W zależności od typu [tożsamości wybranej](hololens-identity.md) podczas OOBE lub po zalogowaniu istnieją różne metody rejestracji.

- Jeśli tożsamością jest usługa Azure AD, podczas OOBE lub Ustawienia **app**  ->  **access work** lub school  ->  **Połączenie** przycisku.
    - W przypadku usługi Azure AD [automatyczna rejestracja w usłudze MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) występuje tylko wtedy, gdy usługa Azure AD została skonfigurowana przy użyciu adresów URL rejestracji.

- Jeśli tożsamość to usługa Azure AD, a urządzenie zostało wstępnie zarejestrowane na serwerze MDM usługi Intune z przypisanym do niego określonym profilem konfiguracji, podczas procesu OOBE wystąpi usługa Azure AD-Join i automatyczna rejestracja w usłudze [MDM.](hololens-enroll-mdm.md#auto-enrollment-in-mdm)
    - Nazywany również [przepływem rozwiązania Autopilot](hololens2-autopilot.md) dostępnym w kompilacjach w wersji [19041.1103+](hololens-release-notes.md#windows-holographic-version-2004).


- Jeśli tożsamość to MSA, należy użyć **Ustawienia aplikacji App** Access Work lub  ->  **School**  ->  **Połączenie** aplikacji.
    - Nazywana również przepływem Dodaj konto służbowe (AWA).
- Jeśli tożsamość jest użytkownikiem lokalnym, należy użyć Ustawienia **App**  ->  **Access Work lub School** Enroll tylko za pomocą  ->  **linku do zarządzania** urządzeniami.
    - Nazywana również przepływem rejestracji w czystym modelu MDM.

Po zarejestrowaniu urządzenia na serwerze MDM aplikacja Ustawienia będzie teraz odzwierciedlać, że urządzenie zostało zarejestrowane w funkcji zarządzania urządzeniami.

## <a name="auto-enrollment-in-mdm"></a>Automatyczna rejestracja w uścisku MDM

Jeśli Twoja organizacja ma subskrypcję usługi [Azure Premium,](https://azure.microsoft.com/overview/)korzysta z usługi Azure Active Directory (Azure AD) i rozwiązania MDM, które akceptuje token usługi Azure AD do uwierzytelniania (obecnie obsługiwane tylko w usługach Microsoft Intune i AirWatch), administrator IT może skonfigurować usługę Azure AD tak, aby automatycznie zezwalała na rejestrację w rozwiązaniu MDM po zarejestrowaniu się użytkownika w usłudze Azure AD Konta. [Dowiedz się, jak skonfigurować rejestrację w usłudze Azure AD.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Po włączeniu automatycznej rejestracji nie jest potrzebna żadna dodatkowa rejestracja ręczna. Po zarejestrowaniu się użytkownika przy użyciu konta usługi Azure AD urządzenie zostanie zarejestrowane w usłudze MDM po zakończeniu pierwszego uruchomienia.

Gdy urządzenie jest przyłączone do usługi Azure AD, może to mieć wpływ na to, kto jest [właścicielem urządzenia.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>Wywrzeć HoloLens z usługi Intune

W zależności od metody rejestracji odwijanie urządzenia może być niedostępne.

Jeśli urządzenie zostało zarejestrowane przy użyciu konta usługi Azure AD lub rozwiązania Autopilot, nie można go usunąć z usługi Intune. Jeśli chcesz odłączyć urządzenie HoloLens z usługi Azure AD lub ponownie do innej dzierżawy usługi Azure AD, musisz [zresetować/odwrócić](hololens-recovery.md#restart-the-device) ukośnik urządzenia.

Jeśli urządzenie zostało zarejestrowane z konta MSA, które dodało konto służbowe, lub z konta lokalnego zarejestrowanego tylko w usłudze zarządzania urządzeniami, możesz wyrollować urządzenie. Otwórz okno menu Start a następnie wybierz **Ustawienia App** Access Work  ->  **lub School**  ->  *YourAccount* Disconnect  ->  (Rozłącz swoje **konto).**

## <a name="enrollment-troubleshooting"></a>Rozwiązywanie problemów z rejestracją

### <a name="ensure-valid-license-is-assigned-to-the-user"></a>Upewnij się, że do użytkownika przypisano prawidłową licencję

Zapoznaj się [z Windows problemami z](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors) rejestrowaniem urządzeń w Microsoft Intune w poniższych sekcjach, tj. Sprawdź ograniczenia typów urządzeń i Przypisz prawidłową [](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#check-device-type-restrictions) [licencję do użytkownika.](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#assign-a-valid-license-to-the-user)

### <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>Upewnij się, że rejestracja mdm nie jest zablokowana dla Windows urządzeń

Aby rejestracja powiodła się, musisz upewnić się, że twoje urządzenia HoloLens mogą być rejestrowane. Ponieważ HoloLens jest uznawane za Windows, nie trzeba będzie mieć żadnych ograniczeń rejestracji, które mogłyby zablokować wdrożenie. [Przejrzyj tę listę ograniczeń i](/mem/intune/enrollment/enrollment-restrictions-set) upewnij się, że będziesz mieć możliwość rejestrowania urządzeń.