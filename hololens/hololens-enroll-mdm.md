---
title: Rejestrowanie urządzenia HoloLens w u usługach MDM
description: Dowiedz się, jak zarejestrować urządzenie HoloLens w funkcji zarządzania urządzeniami przenośnymi (MDM), aby ułatwić zarządzanie wieloma urządzeniami.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 624ebd17335820b1d2858f9d39cabb7032a83bfe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378391"
---
# <a name="enroll-hololens-in-mdm"></a>Rejestrowanie urządzenia HoloLens w u usługach MDM

Możesz zarządzać wieloma urządzeniami Microsoft HoloLens jednocześnie przy użyciu rozwiązań takich [jak Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business). Będzie można zarządzać ustawieniami, wybierać aplikacje do instalowania i ustawiać konfiguracje zabezpieczeń dostosowane do potrzeb organizacji. Zobacz [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)(Zarządzanie urządzeniami z systemem Windows Holographic za pomocą usługi Microsoft Intune), configuration service providers [(CSPs)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)that are supported in Windows Holographic (Dostawcy usług konfiguracji obsługiwani w systemie Windows Holographic) [oraz zasady](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)obsługiwane przez program Windows Holographic for Business .

> [!NOTE]
> Zarządzanie urządzeniami przenośnymi (MDM), w tym funkcje sieci VPN, funkcji BitLocker i trybu kiosku, jest dostępne tylko podczas uaktualniania do [Windows Holographic for Business.](hololens1-upgrade-enterprise.md)

## <a name="requirements"></a>Wymagania

 Aby zarządzać urządzeniami HoloLens, organizacja musi mieć Zarządzanie urządzeniami mobile Zarządzanie urządzeniami (MDM). Dostawcą rozwiązania MDM może być Microsoft Intune lub dostawca innej firmy, który korzysta z interfejsów API zarządzania urządzeniami przenośnymi firmy Microsoft.
 
## <a name="different-ways-to-enroll"></a>Różne sposoby rejestrowania

W zależności od typu [tożsamości wybranej](hololens-identity.md) podczas OOBE lub po zalogowaniu istnieją różne metody rejestracji.

- Jeśli tożsamością jest usługa Azure AD, podczas OOBE lub **Ustawienia przycisku App**  ->  **Access Work or School**  ->  **Connect.**
    - W przypadku usługi Azure AD [automatyczna rejestracja w usłudze MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) występuje tylko wtedy, gdy usługa Azure AD została skonfigurowana przy użyciu adresów URL rejestracji.
     
- Jeśli tożsamość to usługa Azure AD, a urządzenie zostało wstępnie zarejestrowane na serwerze MDM usługi Intune z przypisanym do niego określonym profilem konfiguracji, podczas OOBE nastąpi usługa Azure AD-Join i automatyczna rejestracja w usłudze [MDM.](hololens-enroll-mdm.md#auto-enrollment-in-mdm)
    - Nazywany również [przepływem rozwiązania Autopilot](hololens2-autopilot.md) dostępnym w kompilacjach w wersji [19041.1103+](hololens-release-notes.md#windows-holographic-version-2004).
    

- Jeśli tożsamość to MSA, należy użyć przycisku **Ustawienia Dostęp do** aplikacji Do pracy lub  ->  **Nauki**  ->  **Connect.**
    - Nazywana również przepływem Dodaj konto służbowe (AWA).
- Jeśli tożsamość jest użytkownikiem lokalnym, należy użyć linku **Ustawienia Dostęp** do aplikacji Do pracy lub  ->  **nauki Zarejestruj** się tylko w  ->  **linku do zarządzania** urządzeniami.
    - Nazywany również przepływem rejestracji czystego zarządzania urządzeniami przenośnymi.

Po zarejestrowaniu urządzenia na serwerze MDM aplikacja Ustawienia będzie teraz odzwierciedlać, że urządzenie zostało zarejestrowane w funkcji zarządzania urządzeniami.

## <a name="auto-enrollment-in-mdm"></a>Automatyczna rejestracja w uścisku MDM

Jeśli Twoja organizacja ma subskrypcję usługi [Azure Premium](https://azure.microsoft.com/overview/), korzysta z usługi Azure Active Directory (Azure AD) i rozwiązania MDM, które akceptuje token usługi Azure AD do uwierzytelniania (obecnie obsługiwane tylko w usługach Microsoft Intune i AirWatch), administrator IT może skonfigurować usługę Azure AD tak, aby automatycznie zezwalała na rejestrację w usłudze MDM po tym, jak użytkownik będzie się konfigurować przy użyciu konta usługi Azure AD. [Dowiedz się, jak skonfigurować rejestrację w usłudze Azure AD.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Po włączeniu automatycznej rejestracji nie jest potrzebna żadna dodatkowa rejestracja ręczna. Po zarejestrowaniu się użytkownika przy użyciu konta usługi Azure AD urządzenie zostanie zarejestrowane w usłudze MDM po zakończeniu pierwszego uruchomienia.

Dołączenie urządzenia do usługi Azure AD może mieć wpływ na to, kto jest [właścicielem urządzenia.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>Wywiązywaj urządzenie HoloLens z usługi Intune

W zależności od metody rejestracji odwijanie urządzenia może być niedostępne.

Jeśli urządzenie zostało zarejestrowane przy użyciu konta usługi Azure AD lub rozwiązania Autopilot, nie można go usunąć z usługi Intune. Jeśli chcesz odłączyć urządzenie HoloLens od usługi Azure AD lub dołączyć je ponownie do innej dzierżawy usługi Azure AD, musisz [zresetować/odwrócić](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) ukośnik urządzenia.

Jeśli urządzenie zostało zarejestrowane z konta MSA, które dodało konto służbowe, lub z konta lokalnego zarejestrowanego tylko w usłudze zarządzania urządzeniami, możesz wyrollować urządzenie. Otwórz okno menu Start a następnie wybierz **przycisk Ustawienia Dostęp** do aplikacji Work lub  ->  **School**  ->  *TwojeKonto*  ->  **Rozłącz.**