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
ms.openlocfilehash: b6206f7121d1ba78908d96f71c5c809ec97b06d5
ms.sourcegitcommit: 6c8406bbcc79c1f624736cc68e1aaeab70436902
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2021
ms.locfileid: "127904348"
---
# <a name="enroll-hololens-in-mdm"></a>Rejestrowanie HoloLens zarządzania urządzeniami przenośnymi

Możesz zarządzać wieloma urządzeniami Microsoft HoloLens jednocześnie przy użyciu rozwiązań takich [jak Microsoft Intune](/intune/windows-holographic-for-business). Będzie można zarządzać ustawieniami, wybierać aplikacje do instalowania i ustawiać konfiguracje zabezpieczeń dostosowane do potrzeb organizacji. Zobacz [Manage devices running Windows Holographic with Microsoft Intune (Zarządzanie](/intune/windows-holographic-for-business)urządzeniami z systemem Microsoft Intune Holographic), dostawcy usług konfiguracji [(CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)obsługiwani w usłudze Windows Holographic i zasady obsługiwane przez program [Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> Zarządzanie urządzeniami przenośnymi (MDM, Mobile Device Management), w tym funkcje sieci VPN, funkcji BitLocker i trybu kiosku, jest dostępne tylko podczas uaktualniania do [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)

## <a name="requirements"></a>Wymagania

 Aby zarządzać urządzeniami przenośnymi, organizacja musi mieć Zarządzanie urządzeniami mobile HoloLens (MDM). Twój dostawca mdm może być Microsoft Intune lub dostawcą innej firmy, który korzysta z interfejsów API mdm firmy Microsoft.

## <a name="different-ways-to-enroll"></a>Różne sposoby rejestrowania

W zależności od typu [tożsamości wybranej](hololens-identity.md) podczas OOBE lub po zalogowaniu istnieją różne metody rejestracji.

- Jeśli tożsamością jest usługa Azure AD, podczas OOBE lub Ustawienia **App**  ->  **Access work lub School**  ->  **Połączenie** przycisku.
    - W przypadku usługi Azure AD [automatyczna rejestracja w usłudze MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) występuje tylko wtedy, gdy usługa Azure AD została skonfigurowana przy użyciu adresów URL rejestracji.

- Jeśli tożsamość to usługa Azure AD, a urządzenie zostało wstępnie zarejestrowane na serwerze MDM usługi Intune z przypisanym do niego określonym profilem konfiguracji, usługa Azure AD-Join i automatyczna rejestracja w usłudze [MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) wystąpią podczas OOBE.
    - Nazywany również [przepływem rozwiązania Autopilot](hololens2-autopilot.md) dostępnym w [kompilacjach 19041.1103+.](hololens-release-notes.md#windows-holographic-version-2004)


- Jeśli tożsamość to MSA, należy użyć **Ustawienia aplikacji App** Access Work lub  ->  **School**  ->  **Połączenie** aplikacji.
    - Nazywana również przepływem Dodaj konto służbowe (AWA).
- Jeśli tożsamość jest użytkownikiem lokalnym, wówczas za **pomocą Ustawienia aplikacji App** Access Work lub  ->  **School** Enroll tylko  ->  **w linku do zarządzania** urządzeniami.
    - Nazywany również przepływem rejestracji w czystym modelu MDM.

Po zarejestrowaniu urządzenia na serwerze MDM aplikacja Ustawienia będzie teraz odzwierciedlać, że urządzenie zostało zarejestrowane w usłudze zarządzania urządzeniami.

## <a name="auto-enrollment-in-mdm"></a>Automatyczna rejestracja w uścisku MDM

Jeśli Twoja organizacja ma subskrypcję usługi [Azure Premium,](https://azure.microsoft.com/overview/)korzysta z usługi Azure Active Directory (Azure AD) i rozwiązania MDM, które akceptuje token usługi Azure AD do uwierzytelniania (obecnie obsługiwane tylko w usługach Microsoft Intune i AirWatch), administrator IT może skonfigurować usługę Azure AD tak, aby automatycznie zezwalała na rejestrację w usłudze MDM po tym, jak użytkownik będzie się uwierzytelniać przy użyciu konta usługi Azure AD. [Dowiedz się, jak skonfigurować rejestrację w usłudze Azure AD.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Po włączeniu automatycznej rejestracji nie jest potrzebna żadna dodatkowa rejestracja ręczna. Po zarejestrowaniu się użytkownika przy użyciu konta usługi Azure AD urządzenie zostanie zarejestrowane w usłudze MDM po zakończeniu pierwszego uruchomienia.

Gdy urządzenie jest przyłączone do usługi Azure AD, może to mieć wpływ na to, kto jest [właścicielem urządzenia.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>Wyerolluj HoloLens z usługi Intune

W zależności od metody rejestracji odejmowanie urządzenia może być niedostępne.

Jeśli urządzenie zostało zarejestrowane przy użyciu konta usługi Azure AD lub rozwiązania Autopilot, nie można go usunąć z usługi Intune. Jeśli chcesz odłączyć się od HoloLens z usługi Azure AD lub ponownie dołączyć do innej dzierżawy usługi Azure AD, musisz [zresetować/odwrócić](hololens-recovery.md#reset-the-device) ukośnik urządzenia.

Jeśli urządzenie zostało zarejestrowane z konta MSA, które dodało konto służbowe lub z konta lokalnego, które zostało zarejestrowane tylko w usłudze zarządzania urządzeniami, możesz wyrolliować urządzenie. Otwórz okno menu Start a następnie wybierz **Ustawienia App** Access Work  ->  **or School**  ->  *YourAccount* Disconnect  ->  (Rozłącz swoje **konto** aplikacji).

## <a name="enrollment-troubleshooting"></a>Rozwiązywanie problemów z rejestracją

### <a name="ensure-valid-license-is-assigned-to-the-user"></a>Upewnij się, że do użytkownika przypisano prawidłową licencję

Zapoznaj się [z Windows problemami z](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors) rejestracją urządzeń w sekcji Microsoft Intune w szczególności w poniższych sekcjach, tj. Sprawdź ograniczenia typów urządzeń i Przypisz prawidłową [](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#check-device-type-restrictions) [licencję do użytkownika.](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#assign-a-valid-license-to-the-user)

### <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>Upewnij się, że rejestracja mdm nie jest zablokowana dla Windows urządzeń

Aby rejestracja zakończyła się pomyślnie, musisz upewnić się, że twoje HoloLens mogą być rejestrowane. Ponieważ HoloLens jest uznawany za Windows, nie trzeba będzie mieć żadnych ograniczeń rejestracji, które mogłyby zablokować wdrożenie. [Przejrzyj tę listę ograniczeń i](/mem/intune/enrollment/enrollment-restrictions-set) upewnij się, że będziesz mieć możliwość rejestrowania urządzeń.