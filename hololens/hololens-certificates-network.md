---
title: Przygotowywanie certyfikatów i profilów sieciowych dla HoloLens 2
description: Dowiedz się, jak konfigurować, używać, wdrażać i rozwiązywać problemy z certyfikatami dla sieci na urządzeniach rzeczywistości mieszanej HoloLens 2.
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
ms.openlocfilehash: 62eedd0c05bb23f11a4e17a97b4ab5441a2931cf
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036059"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>Przygotowywanie certyfikatów i profilów sieciowych dla HoloLens 2

Uwierzytelnianie oparte na certyfikatach jest powszechnym wymaganiem dla klientów korzystających z HoloLens 2. Możesz wymagać certyfikatów w celu uzyskania dostępu do sieci Wi-Fi, połączenia z rozwiązaniami sieci VPN lub uzyskiwania dostępu do zasobów wewnętrznych w organizacji.

Ponieważ urządzenia z systemem HoloLens 2 są zwykle przyłączone do usługi Azure Active Directory (Azure AD) i zarządzane przez usługę Intune lub innego dostawcę mdm, należy wdrożyć takie certyfikaty przy użyciu infrastruktury certyfikatów prosty protokół rejestrowania certyfikatów (SCEP) lub PKCS (Public Key Cryptography Standard) zintegrowanej z rozwiązaniem MDM. 

>[!NOTE]
> Jeśli nie masz dostawcy mdm, możesz nadal wdrażać [](hololens-provisioning.md#steps-for-creating-provisioning-packages) certyfikaty za pośrednictwem pakietu aprowizowania w programie [Windows Configuration Designer](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) lub za pomocą Menedżera certyfikatów, przechodząc do menedżera certyfikatów usługi Ustawienia > Update & **Security >.** [](certificate-manager.md)

## <a name="certificate-requirements"></a>Wymagania certyfikatu
Certyfikaty główne są wymagane do wdrażania certyfikatów za pośrednictwem infrastruktury SCEP lub PKCS. Inne aplikacje i usługi w organizacji mogą wymagać wdrożenia certyfikatów głównych na urządzeniach HoloLens 2. 

## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi wymagań dotyczących łączności
Aby umożliwić automatyczne dostarczanie urządzenia z wymaganą Wi-Fi konfiguracji sieci przedsiębiorstwa, wymagany jest Wi-Fi konfiguracji. Aby wdrożyć te profile na urządzeniach, można skonfigurować usługę Intune lub innego dostawcę rozwiązania MDM. Jeśli zabezpieczenia sieci wymagają, aby urządzenia były częścią domeny lokalnej, może być również konieczne oszacowanie infrastruktury sieci usługi Wi-Fi w celu upewnienie się, że jest ona zgodna z urządzeniami z systemem HoloLens 2 (urządzenia z systemem HoloLens 2 są przyłączone tylko do usługi Azure AD).

## <a name="deploy-certificate-infrastructure"></a>Wdrażanie infrastruktury certyfikatów
Jeśli jeszcze nie istnieje infrastruktura SCEP lub PKCS, należy przygotować infrastrukturę. Aby obsługiwać uwierzytelnianie przy użyciu certyfikatów SCEP lub PKCS, usługa Intune wymaga użycia [łącznika certyfikatów.](/mem/intune/protect/certificate-connectors)

> [!NOTE]
> W przypadku używania SCEP z urzędu certyfikacji firmy Microsoft należy również skonfigurować usługa rejestracji urządzeń sieciowych [(NDES)](/mem/intune/protect/certificates-scep-configure#set-up-ndes)

Aby uzyskać więcej informacji, zobacz Konfigurowanie profilu certyfikatu dla urządzeń w u [Microsoft Intune.](/intune/certificates-configure)

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Wdrażanie certyfikatów i profilu sieci Wi-Fi/VPN
Aby wdrożyć certyfikaty i profile, wykonaj następujące kroki:
1.  Utwórz profil dla każdego certyfikatu głównego i pośredniego (zobacz [Tworzenie profilów zaufanych certyfikatów).](/intune/protect/certificates-configure#create-trusted-certificate-profiles) Każdy z tych profilów musi mieć opis, który zawiera datę wygaśnięcia w formacie DD/MM/YYYY. **Profile certyfikatów bez daty wygaśnięcia nie zostaną wdrożone.**
1.  Utwórz profil dla każdego certyfikatu SCEP lub PKCS (zobacz Tworzenie profilu certyfikatu SCEP lub Tworzenie profilu certyfikatu [PKCS).](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)Każdy z tych profilów musi mieć opis, który zawiera datę wygaśnięcia w formacie DD/MM/YYYY. **Profile certyfikatów bez daty wygaśnięcia nie zostaną wdrożone.**

    > [!NOTE]
    > Ponieważ urządzenie HoloLens 2 jest uznawane za urządzenie udostępnione lub wielu użytkowników na urządzenie, zaleca się wdrożenie certyfikatów urządzeń zamiast certyfikatów użytkowników na Wi-Fi uwierzytelniania, jeśli jest to możliwe

3.  Utwórz profil dla każdej firmowej Wi-Fi sieci (zobacz [Ustawienia sieci Wi-Fi](/intune/wi-fi-settings-windows)dla urządzeń Windows 10 i nowszych). 
    > [!NOTE]
    > Zaleca się, aby profil Wi-Fi był [przypisywany](/mem/intune/configuration/device-profile-assign) do grup urządzeń, a nie do grup użytkowników tam, gdzie jest to możliwe. 

    > [!TIP]
    > Możesz również wyeksportować roboczy profil Wi-Fi z komputera Windows 10 w sieci firmowej. Ten eksport tworzy plik XML ze wszystkimi bieżącymi ustawieniami. Następnie zaimportuj ten plik do usługi Intune i użyj go jako Wi-Fi profilu dla HoloLens 2 urządzeń. Zobacz [Eksportowanie i importowanie Wi-Fi ustawień Windows urządzeń.](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

4.  Utwórz profil dla każdej firmowej sieci VPN (zobacz Windows 10 i Windows [urządzenia Holographic,](/intune/vpn-settings-windows-10)aby dodać połączenia sieci VPN przy użyciu usługi Intune).

## <a name="troubleshooting-certificates"></a>Rozwiązywanie problemów z certyfikatami

W przypadku konieczności zweryfikowania, czy certyfikat został wdrożony [](certificate-manager.md) poprawnie, użyj Menedżera certyfikatów na urządzeniu, aby sprawdzić, czy certyfikat jest obecny.  

>[!WARNING]
> Chociaż certyfikaty wdrożone przez rozwiązanie MDM można wyświetlić w Menedżerze certyfikatów, nie można ich odinstalować w Menedżerze certyfikatów. Należy je odinstalować za pośrednictwem rozwiązania MDM.


