---
title: Sprzętowa integralność i zaświadczenia środowiska uruchomieniowego
description: Sprzętowa integralność i zaświadczenia środowiska uruchomieniowego
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: zabezpieczenia, hololens, integralność sprzętowa, zaświadczenia środowiska uruchomieniowego, uefi, bezpieczny rozruch UEFI, bezpieczny rozruch, moduł TPM, ochrona przed zagrożeniami, gwarancja trwałości systemu Windows, integralność kodu, ochrona kodu,
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 0a89fa5e61e560f629444efd2728f6dd41db60d3
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379734"
---
# <a name="hardware-backed-integrity-and-runtime-attestation"></a>Sprzętowa integralność i zaświadczenia środowiska uruchomieniowego

Sprzętowa integralność i zaświadczenia środowiska uruchomieniowego chronią przed zagrożeniami pochodzącymi przed uruchomieniem systemu operacyjnego, w czasie wykonywania, gdy urządzenie korzysta ze sprzętu i zdalnych usług zaszeeń w celu zapewnienia integralności podczas uruchamiania i przez cały czas trwania środowiska uruchomieniowego.

## <a name="uefi-secure-boot"></a>Bezpieczny rozruch z interfejsem UEFI

Urządzenie HoloLens 2 wymusza zawsze Extensible Firmware Interface (UEFI), a interfejs UEFI uruchamia Windows Holographic for Business.
Bezpieczny rozruch zapewnia, że cały łańcuch rozruchu jest weryfikowany pod względami integralności i że system Windows zawsze uruchamia się z zastosowanymi do niego prawidłowymi zasadami zabezpieczeń. Dowiedz się więcej na [temat bezpiecznego rozruchu.](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)

## <a name="tpm"></a>Moduł TPM

Moduł Trusted Platform Module (TPM) to wyspecjalizowany mikroukład na urządzeniu punktu końcowego. Urządzenie HoloLens 2 używa modułu TPM 2.0, który zapewnia wymuszaną sprzętowo izolację kluczy. Dowiedz się więcej na [temat podstawowych informacji o modułach TPM.](https://docs.microsoft.com/windows/security/information-protection/tpm/tpm-fundamentals)

## <a name="persistence-access-threat-protection"></a>Ochrona przed zagrożeniami dostępu do trwałości

Celem większości cyberataków jest utrzymanie stałego dostępu do urządzenia. W przypadku cyberprzestępczości utrzymywanie tej trwałości umożliwia urządzeniu z systemem Windows, które zostało naruszone, dołączenie do botnetu, sprzedaż dostępu do urządzenia lub innych niegodziwych użytkowników lub umożliwienie wielokrotnej kradzieży danych. W świecie ataków ukierunkowanych trwałość jest niezbędna do pomyślnego ataku cybernetycznego — zarówno na urządzeniu, jak i (najczęściej) w całej sieci.  

W rzeczywistości ukierunkowane ataki są uznawane za "zaawansowane trwałe zagrożenia", ponieważ ich strategiczna potrzeba utrzymania dostępu do docelowego urządzenia lub sieci. Z tego powodu Windows Holographic for Business obronę przed trwałością absolutnie kluczową i używa technologii ochrony przed trwałością, aby zapewnić klientom ironiczny poziom bezpieczeństwa.

### <a name="secure-boot"></a>Bezpieczny rozruch

Urządzenie HoloLens 2 wymusza bezpieczny rozruch Extensible Firmware Interface (UEFI) w całym podstawowym stanie systemu operacyjnego. Interfejs UEFI uruchamia tylko zaufane platformy firmy Microsoft, co gwarantuje, że cały łańcuch rozruchu jest weryfikowany pod względami integralności i że system Windows zawsze uruchamia się z zastosowanymi do niego prawidłowymi zasadami zabezpieczeń. Urządzenie HoloLens 2 nie umożliwia wyłączenia bezpiecznego rozruchu ani nie zezwala na uruchamianie modułu ładującego innych firm.

> [!Tip]
> Dowiedz się więcej na temat [bezpiecznego rozruchu.](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)

### <a name="windows-anti-persistence-assurance"></a>Windows Anti-Persistence Assurance

Ochrona przed trwałością urządzenia HoloLens 2 gwarantuje swoim użytkownikom, że nawet w rzadkich sytuacjach, w których kiedykolwiek dojdzie do naruszenia bezpieczeństwa systemu — takiego jak zdalne wykorzystanie luk w zabezpieczeniach — takie zdarzenie zostanie ograniczone przez usunięcie całego złośliwego kodu z systemu przez wyłączenie urządzenia. Aby jeszcze bardziej wzmocnić ochronę przed trwałością, urządzenie HoloLens 2 dodało zaawansowaną ochronę integralności i zapewnia ochronę tylko do odczytu.

Trwałość danych systemu operacyjnego w postaci danych jest nadal możliwa, chyba że użytkownik wykonuje resetowanie przycisku wypychania (PBR) urządzenia, które czyści wszystkie modyfikowalne partycje. Chociaż trwałość w partycjach niezmiennych jest znacznie trudniejsza, użytkownik musi PBR urządzenia HoloLens 2, aby usunąć wszelkie możliwe zagrożenia-trwałość z modyfikowalnych części.

## <a name="code-integrity-protection"></a>Ochrona integralności kodu

Integralność kodu (CI) to kluczowa właściwość zabezpieczeń nowoczesnego systemu operacyjnego. Wymuszanie CI umożliwia podejmowanie należytych decyzji dotyczących zabezpieczeń, ponieważ gwarantuje, że kod jest niewidoczny zarówno dla użytkownika, jak i dla systemu operacyjnego. Pełna integralność kodu musi rozszerzyć poprzednie podpisywanie obrazów binarnych i obejmować wymuszanie środowiska uruchomieniowego, takie jak integralność przepływu sterowania i ograniczenia kodu dynamicznego. Ci ma kluczowe znaczenie dla zapobiegania wielu klasom ataków, w tym złośliwemu oprogramowaniu opracowanemu przez społeczności, takim jak oprogramowanie wymuszające okup, programy wykorzystujące zdalne wykonywanie kodu i różne inne klasy ataków.
