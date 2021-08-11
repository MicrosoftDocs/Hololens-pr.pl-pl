---
title: Sprzętowa integralność i zaświadczenia środowiska uruchomieniowego
description: Sprzętowa integralność i zaświadczenia środowiska uruchomieniowego
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: zabezpieczenia, hololens, integralność sprzętowa, zaświadczenia środowiska uruchomieniowego, UEFI, bezpieczny rozruch UEFI, bezpieczny rozruch, moduł TPM, ochrona przed zagrożeniami, Windows Anti-Persistence Assurance, integralność kodu, ochrona kodu,
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: de12231b87c028ed9d8ca785a5b351fc4cb1c6fd8dbe304e4baaccd6803c5f6a
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665407"
---
# <a name="hardware-backed-integrity-and-runtime-attestation"></a>Sprzętowa integralność i zaświadczenia środowiska uruchomieniowego

Sprzętowa integralność i zaświadczenia środowiska uruchomieniowego chronią przed zagrożeniami pochodzącymi przed uruchomieniem systemu operacyjnego, w czasie wykonywania, gdy urządzenie korzysta ze sprzętu i zdalnych usług zaszeeń w celu zapewnienia integralności podczas uruchamiania i przez cały czas trwania środowiska uruchomieniowego.

## <a name="uefi-secure-boot"></a>Bezpieczny rozruch z interfejsem UEFI

HoloLens 2 wymusza zawsze bezpieczny rozruch Extensible Firmware Interface (UEFI), a interfejs UEFI uruchamia Windows Holographic for Business.
Bezpieczny rozruch gwarantuje, że cały łańcuch rozruchu jest weryfikowany pod Windows jest zawsze uruchamiany z zastosowanymi do niego prawidłowymi zasadami zabezpieczeń. Dowiedz się więcej na [temat bezpiecznego rozruchu.](/windows-hardware/design/device-experiences/oem-secure-boot)

## <a name="tpm"></a>Moduł TPM

Moduł Trusted Platform Module (TPM) to wyspecjalizowany mikroukład na urządzeniu punktu końcowego. HoloLens 2 używa modułu TPM 2.0, który zapewnia sprzętową izolację kluczy. Dowiedz się więcej na [temat podstawowych informacji o modułach TPM.](/windows/security/information-protection/tpm/tpm-fundamentals)

## <a name="persistence-access-threat-protection"></a>Ochrona przed zagrożeniami dostępu do trwałości

Celem większości cyberataków jest utrzymanie stałego dostępu do urządzenia. W przypadku cyberprzestępczości utrzymywanie tej trwałości umożliwia urządzeniu z naruszonym Windows dołączenie do botnetu, sprzedawanie dostępu do urządzenia lub innym niegroźnym użytkownikom albo umożliwia wielokrotne kradzieży danych. W świecie ataków ukierunkowanych trwałość jest niezbędna do pomyślnego ataku cybernetycznego — zarówno na urządzeniu, jak i (najczęściej) w całej sieci.  

W rzeczywistości ukierunkowane ataki są uznawane za "zaawansowane trwałe zagrożenia", ponieważ ich strategiczna potrzeba utrzymania dostępu do docelowego urządzenia lub sieci. Z tego powodu Windows Holographic for Business obronę przed trwałością, która jest absolutnie kluczowa, i używa technologii antytrwałej, aby zapewnić klientom ironiczne obietnice bezpieczeństwa.

### <a name="secure-boot"></a>Bezpieczny rozruch

HoloLens 2 wymusza ujednolicony Extensible Firmware Interface (UEFI) bezpieczny rozruch we wszystkich podstawowych stanach systemu operacyjnego. Interfejs UEFI uruchamia tylko zaufane platformy firmy Microsoft, co zapewnia, że cały łańcuch rozruchu jest weryfikowany pod Windows zawsze uruchamia się z zastosowanymi do niego prawidłowymi zasadami zabezpieczeń. HoloLens 2 nie zabezpiecza rozruchu, aby wyłączyć, ani nie zezwala na 3 innych firm modułu ładującego rozruchu.

> [!Tip]
> Dowiedz się więcej na temat [bezpiecznego rozruchu.](/windows-hardware/design/device-experiences/oem-secure-boot)

### <a name="windows-anti-persistence-assurance"></a>Windows Ochrona przed trwałością

HoloLens 2 gwarantuje swoim użytkownikom, że nawet w rzadkich sytuacjach, kiedykolwiek wystąpi zagrożenie środowiska uruchomieniowego systemu — takie jak zdalne wykorzystanie luk w zabezpieczeniach — takie zdarzenie zostanie ograniczone przez usunięcie całego złośliwego kodu z systemu przez wyłączenie urządzenia. Aby jeszcze bardziej wzmocnić ochronę przed trwałością, HoloLens 2 dodała zaawansowaną ochronę integralności i zabezpieczenia tylko do odczytu.

Trwałość danych systemu operacyjnego w postaci danych jest nadal możliwa, chyba że użytkownik wykonuje resetowanie przycisku wypychania (PBR) urządzenia, które czyści wszystkie modyfikowalne partycje. Chociaż trwałość w partycjach niezmiennych jest znacznie trudniejsza, użytkownik musi PBR HoloLens 2, aby usunąć wszelkie możliwe trwałość zagrożeń z modyfikowalnych części.

## <a name="code-integrity-protection"></a>Ochrona integralności kodu

Integralność kodu (CI) to kluczowa właściwość zabezpieczeń nowoczesnego systemu operacyjnego. Wymuszanie CI umożliwia podejmowanie należytych decyzji dotyczących zabezpieczeń, ponieważ gwarantuje, że kod jest niewidoczny zarówno dla użytkownika, jak i dla systemu operacyjnego. Pełna integralność kodu musi rozszerzyć poprzednie podpisywanie obrazów binarnych i obejmować wymuszanie środowiska uruchomieniowego, takie jak integralność przepływu sterowania i ograniczenia kodu dynamicznego. Ci ma kluczowe znaczenie dla zapobiegania wielu klasom ataków, w tym złośliwemu oprogramowaniu opracowanemu przez społeczności, takim jak oprogramowanie wymuszające okup, programy wykorzystujące zdalne wykonywanie kodu i różne inne klasy ataków.
