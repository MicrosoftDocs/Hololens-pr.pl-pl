---
title: Przygotowywanie certyfikatów i profilów sieciowych dla urządzenia HoloLens 2
description: Dowiedz się, jak konfigurować, używać, wdrażać i rozwiązywać problemy z certyfikatami dla sieci na urządzeniach z rzeczywistością mieszaną HoloLens 2.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: eedb451847757eba02465d7ded4494b9712497ff
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379678"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>Przygotowywanie certyfikatów i profilów sieciowych dla urządzenia HoloLens 2

Uwierzytelnianie oparte na certyfikatach jest częstym wymaganiem dla klientów korzystających z urządzenia HoloLens 2. Aby uzyskać dostęp do sieci Wi-Fi, nawiązać połączenie z rozwiązaniami sieci VPN lub uzyskać dostęp do zasobów wewnętrznych w organizacji, mogą być wymagane certyfikaty.

Ponieważ urządzenia HoloLens 2 są zwykle przyłączone do usługi Azure Active Directory (Azure AD) i zarządzane przez usługę Intune lub innego dostawcę mdm, należy wdrożyć takie certyfikaty przy użyciu infrastruktury certyfikatów prosty protokół rejestrowania certyfikatów (SCEP) lub PKCS (Public Key Cryptography Standard) zintegrowanej z rozwiązaniem MDM. 

>[!NOTE]
> Jeśli nie masz dostawcy zarządzania urządzeniami przenośnymi, możesz [](https://docs.microsoft.com/hololens/hololens-provisioning#steps-for-creating-provisioning-packages) nadal wdrażać certyfikaty za [](https://docs.microsoft.com/hololens/certificate-manager) pośrednictwem pakietu aprowizowania w Projektancie konfiguracji systemu [Windows](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) lub za pośrednictwem Menedżera certyfikatów, przechodząc do opcji Ustawienia **> Update & Security > Certificate Manager.**

## <a name="certificate-requirements"></a>Wymagania certyfikatu
Certyfikaty główne są wymagane do wdrażania certyfikatów za pośrednictwem infrastruktury SCEP lub PKCS. Inne aplikacje i usługi w organizacji mogą również wymagać wdrożenia certyfikatów głównych na urządzeniach HoloLens 2. 

## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi wymagań dotyczących łączności
Aby umożliwić automatyczne dostarczanie urządzenia z wymaganą Wi-Fi konfiguracji sieci przedsiębiorstwa, wymagany jest Wi-Fi konfiguracji. Aby wdrożyć te profile na urządzeniach, można skonfigurować usługę Intune lub innego dostawcę zarządzania urządzeniami przenośnymi. Jeśli zabezpieczenia sieci wymagają, aby urządzenia były częścią domeny lokalnej, może być również konieczne oszacowanie infrastruktury sieci Wi-Fi, aby upewnić się, że jest ona zgodna z urządzeniami HoloLens 2 (urządzenia HoloLens 2 są przyłączone tylko do usługi Azure AD).

## <a name="deploy-certificate-infrastructure"></a>Wdrażanie infrastruktury certyfikatów
Jeśli jeszcze nie istnieje infrastruktura SCEP lub PKCS, należy przygotować infrastrukturę. Aby obsługiwać uwierzytelnianie przy użyciu certyfikatów SCEP lub PKCS, usługa Intune wymaga użycia [łącznika certyfikatów.](https://docs.microsoft.com/mem/intune/protect/certificate-connectors)

> [!NOTE]
> W przypadku używania SCEP z urzędu certyfikacji firmy Microsoft należy również [skonfigurować usługa rejestracji urządzeń sieciowych (NDES)](https://docs.microsoft.com/mem/intune/protect/certificates-scep-configure#set-up-ndes)

Aby uzyskać więcej informacji, [zobacz Konfigurowanie profilu certyfikatu dla urządzeń w programie Microsoft Intune.](https://docs.microsoft.com/intune/certificates-configure)

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Wdrażanie certyfikatów i profilu sieci Wi-Fi/VPN
Aby wdrożyć certyfikaty i profile, wykonaj następujące kroki:
1.  Utwórz profil dla każdego certyfikatu głównego i pośredniego (zobacz [Tworzenie profilów zaufanych certyfikatów).](https://docs.microsoft.com/intune/protect/certificates-configure#create-trusted-certificate-profiles) Każdy z tych profilów musi mieć opis, który zawiera datę wygaśnięcia w formacie DD/MM/YYYY. **Profile certyfikatów bez daty wygaśnięcia nie zostaną wdrożone.**
1.  Utwórz profil dla każdego certyfikatu SCEP lub PKCS (zobacz Tworzenie profilu certyfikatu SCEP lub Tworzenie profilu certyfikatu [PKCS).](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)Każdy z tych profilów musi mieć opis, który zawiera datę wygaśnięcia w formacie DD/MM/YYYY. **Profile certyfikatów bez daty wygaśnięcia nie zostaną wdrożone.**

    > [!NOTE]
    > Ponieważ urządzenie HoloLens 2 jest uznawane za urządzenie udostępnione, a wielu użytkowników na urządzenie, zaleca się wdrożenie certyfikatów urządzenia zamiast certyfikatów użytkowników na Wi-Fi uwierzytelniania, jeśli jest to możliwe

3.  Utwórz profil dla każdej sieci Wi-Fi firmowej (zobacz [Ustawienia sieci Wi-Fi dla Windows 10 i nowszych).](https://docs.microsoft.com/intune/wi-fi-settings-windows) 
    > [!NOTE]
    > Zaleca się, aby profil Wi-Fi był przypisywany [do](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign) grup urządzeń, a nie grup użytkowników tam, gdzie jest to możliwe. 

    > [!TIP]
    > Możesz również wyeksportować profil profilu Wi-Fi z komputera Windows 10 w sieci firmowej. Ten eksport tworzy plik XML ze wszystkimi bieżącymi ustawieniami. Następnie zaimportuj ten plik do usługi Intune i użyj go jako profilu Wi-Fi urządzeń HoloLens 2. Zobacz [Eksportowanie i importowanie Wi-Fi dla urządzeń z systemem Windows.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

4.  Utwórz profil dla każdej firmowej sieci VPN (zobacz ustawienia urządzeń [Windows 10 i Windows Holographic,](https://docs.microsoft.com/intune/vpn-settings-windows-10)aby dodać połączenia sieci VPN przy użyciu usługi Intune).

## <a name="troubleshooting-certificates"></a>Rozwiązywanie problemów z certyfikatami

W przypadku konieczności zweryfikowania, czy certyfikat został wdrożony [](certificate-manager.md) poprawnie, użyj Menedżera certyfikatów na urządzeniu, aby sprawdzić, czy certyfikat jest obecny.  

>[!WARNING]
> Chociaż certyfikaty wdrożone przez rozwiązanie MDM można wyświetlić w Menedżerze certyfikatów, nie można ich odinstalować w Menedżerze certyfikatów. Należy je odinstalować za pośrednictwem rozwiązania MDM.


