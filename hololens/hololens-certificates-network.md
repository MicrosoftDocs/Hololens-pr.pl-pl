---
title: Przygotowywanie certyfikatów i profilów sieciowych do HoloLens 2
description: Dowiedz się, jak konfigurować, używać, wdrażać i rozwiązywać problemy z certyfikatami dla sieci na HoloLens 2 urządzeniach rzeczywistości mieszanej.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: aboeger
ms.topic: article
ms.localizationpriority: high
ms.date: 9/15/2020
ms.reviewer: v-evmill
audience: ITPro
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: cf9e14ffbda01bb1fd9e788385f7b85884d1dc8c
ms.sourcegitcommit: 73a1555fb8b84f3d20c480282c648d8d800a6c98
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/26/2021
ms.locfileid: "130351621"
---
# <a name="prepare-certificates-and-network-profiles-for-hololens-2"></a>Przygotowywanie certyfikatów i profilów sieciowych do HoloLens 2

Uwierzytelnianie oparte na certyfikatach jest powszechnym wymaganiem dla klientów korzystających HoloLens 2. Aby uzyskać dostęp do sieci Wi-Fi, nawiązać połączenie z rozwiązaniami sieci VPN lub uzyskać dostęp do zasobów wewnętrznych w organizacji, mogą być wymagane certyfikaty.

Ponieważ urządzenia HoloLens 2 są zwykle przyłączone do usługi Azure Active Directory (Azure AD) i zarządzane przez usługę Intune lub innego dostawcę mdm, należy wdrożyć takie certyfikaty przy użyciu infrastruktury certyfikatów prosty protokół rejestrowania certyfikatów (SCEP) lub PKCS (Public Key Cryptography Standard) zintegrowanej z rozwiązaniem MDM. 

>[!NOTE]
> Jeśli nie masz dostawcy rozwiązania MDM, możesz nadal [](hololens-provisioning.md#create-the-provisioning-package) wdrażać certyfikaty za pośrednictwem pakietu [](certificate-manager.md) aprowizowania w programie [Windows Configuration Designer](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?rtc=1&activetab=pivot:regionofsystemrequirementstab) lub za pomocą Menedżera certyfikatów, przechodząc do menedżera certyfikatów usługi **Ustawienia > Update & Security >.**

## <a name="certificate-requirements"></a>Wymagania certyfikatu
Certyfikaty główne są wymagane do wdrażania certyfikatów za pośrednictwem infrastruktury SCEP lub PKCS. Inne aplikacje i usługi w organizacji mogą wymagać wdrożenia certyfikatów głównych na urządzeniach HoloLens 2. 

## <a name="wi-fi-connectivity-requirements"></a>Wi-Fi wymagań dotyczących łączności
Aby umożliwić automatyczne dostarczanie urządzenia z wymaganą Wi-Fi konfiguracji sieci przedsiębiorstwa, potrzebny jest Wi-Fi konfiguracji. Aby wdrożyć te profile na urządzeniach, można skonfigurować usługę Intune lub innego dostawcę zarządzania urządzeniami przenośnymi. Jeśli zabezpieczenia sieci wymagają, aby urządzenia były częścią domeny lokalnej, może być również konieczne oszacowanie infrastruktury sieci Wi-Fi w celu upewnienie się, że jest ona zgodna z urządzeniami z systemem HoloLens 2 (urządzenia z systemem HoloLens 2 są przyłączone tylko do usługi Azure AD).

## <a name="deploy-certificate-infrastructure"></a>Wdrażanie infrastruktury certyfikatów
Jeśli jeszcze nie istnieje infrastruktura SCEP lub PKCS, należy przygotować infrastrukturę. Aby obsługiwać uwierzytelnianie przy użyciu certyfikatów SCEP lub PKCS, usługa Intune wymaga użycia [łącznika certyfikatów.](/mem/intune/protect/certificate-connectors)

> [!NOTE]
> W przypadku używania SCEP z urzędu certyfikacji firmy Microsoft należy również [skonfigurować usługa rejestracji urządzeń sieciowych (NDES)](/mem/intune/protect/certificates-scep-configure#set-up-ndes)

Aby uzyskać więcej informacji, [zobacz Konfigurowanie profilu certyfikatu dla urządzeń w programie Microsoft Intune.](/intune/certificates-configure)

## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Wdrażanie certyfikatów i profilu sieci Wi-Fi/VPN
Aby wdrożyć certyfikaty i profile, wykonaj następujące kroki:

1.  Utwórz profil dla każdego certyfikatu głównego i pośredniego (zobacz [Tworzenie profilów zaufanych certyfikatów).](/intune/protect/certificates-configure#create-trusted-certificate-profiles) Każdy z tych profilów musi mieć opis, który zawiera datę wygaśnięcia w formacie DD/MM/YYYY. **Profile certyfikatów bez daty wygaśnięcia nie zostaną wdrożone.**

2.  Utwórz profil dla każdego certyfikatu SCEP lub PKCS (zobacz Tworzenie profilu certyfikatu SCEP lub Tworzenie profilu certyfikatu [PKCS).](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)Każdy z tych profilów musi mieć opis, który zawiera datę wygaśnięcia w formacie DD/MM/YYYY. **Profile certyfikatów bez daty wygaśnięcia nie zostaną wdrożone.**

    > [!NOTE]
    > Ponieważ urządzenie HoloLens 2 jest uznawane za urządzenie udostępnione, a wielu użytkowników na urządzenie, zaleca się wdrożenie certyfikatów urządzeń zamiast certyfikatów użytkownika na Wi-Fi uwierzytelniania tam, gdzie to możliwe

3.  Utwórz profil dla każdej sieci Wi-Fi firmowej (zobacz [Ustawienia sieci Wi-Fi dla Windows 10 i nowszych).](/intune/wi-fi-settings-windows) 

    > [!NOTE]
    > Zaleca się, aby profil Wi-Fi [](/mem/intune/configuration/device-profile-assign) był przypisywany do grup urządzeń, a nie grup użytkowników tam, gdzie jest to możliwe. 

    > [!TIP]
    > Możesz również wyeksportować roboczy profil Wi-Fi z komputera Windows 10 w sieci firmowej. Ten eksport tworzy plik XML ze wszystkimi bieżącymi ustawieniami. Następnie zaimportuj ten plik do usługi Intune i użyj go jako profilu Wi-Fi dla urządzeń HoloLens 2. Zobacz [Eksportowanie i importowanie Wi-Fi dla Windows urządzeń.](/mem/intune/configuration/wi-fi-settings-import-windows-8-1)

4.  Utwórz profil dla każdej firmowej sieci VPN (zobacz Windows 10 i [Windows urządzenia Holographic,](/intune/vpn-settings-windows-10)aby dodać połączenia sieci VPN przy użyciu usługi Intune).

## <a name="troubleshooting"></a>Rozwiązywanie problemów

### <a name="issue---unable-to-connect-with-network-using-certificate-based-authentication"></a>Problem — nie można nawiązać połączenia z siecią przy użyciu uwierzytelniania opartego na certyfikatach ###

**Objawy**

Urządzenie nie może nawiązać połączenia sieciowego z uwierzytelnianiem opartym na certyfikatach.

**Kroki rozwiązywania problemów**

1. W przypadku konieczności zweryfikowania, czy certyfikat został wdrożony [](certificate-manager.md) poprawnie, użyj Menedżera certyfikatów na urządzeniu, aby sprawdzić, czy certyfikat jest obecny.  

    >[!WARNING]
    > Chociaż certyfikaty wdrożone przez rozwiązanie MDM można wyświetlić w Menedżerze certyfikatów, nie można ich odinstalować w Menedżerze certyfikatów. Należy je odinstalować za pośrednictwem rozwiązania MDM.

2. Tylko w przypadku usługi Intune prosty protokół rejestrowania certyfikatów (SCEP) jest używany do wdrażania certyfikatów, upewnij się, że adres URL serwera usługi usługa rejestracji urządzeń sieciowych (NDES) jest dostępny z urządzenia. [Aby uzyskać informacje dotyczące konfiguracji, zobacz Certyfikaty SCEP w](/mem/intune/protect/certificates-profile-scep) usłudze Intune. Jeśli rekord CNAME jest używany zamiast w pełni kwalifikowanej domeny dla serwera usługi NDES, upewnij się, że jest on poprawnie rozpoznany, wpisując ten adres URL w przeglądarce internetowej na urządzeniu.
