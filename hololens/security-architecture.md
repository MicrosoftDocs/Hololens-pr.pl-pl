---
title: HoloLens architektury zabezpieczeń
description: Architektura zabezpieczeń
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, hololens 2, hololens2 security, security overview, security architecture, architecture, hololens 2 architecture
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d8e68f73d05db397a7ee088382e82dfa762177b0
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036607"
---
# <a name="security-overview-and-architecture"></a>Omówienie zabezpieczeń i architektura

Architektura zabezpieczeń HoloLens 2 została zaprojektowana i zaprojektowana od podstaw w taki sposób, aby była wolna od starszych problemów z zabezpieczeniami przy jednoczesnym utworzeniu zminimalizowanej powierzchni ataku. Ta nowa, nowatorska architektura oferuje bezpieczne lokalizacje przechowywania i zaawansowane elementy zabezpieczeń z mechanizmami umożliwiającymi ochronę systemów operacyjnych przed potencjalnymi zagrożeniami i lukami w zabezpieczeniach.

HoloLens 2 łączy sprzęt, oprogramowanie, sieć i usługi, aby zapewnić użytkownikom optymalne środowisko. W HoloLens 2 większość funkcji zabezpieczeń jest teraz automatycznie włączona, minimalizując nakład pracy wymagany do poprawnego skonfigurowania i skonfigurowania systemu operacyjnego.

Windows HoloLens 2 i architektura systemu operacyjnego oferują następujące innowacyjne funkcje zabezpieczeń:

  * **Separacja i** izolacja stanu: ta nowa architektura chroni krytyczne części systemu operacyjnego HoloLens 2 przed zmianami, takimi jak te, które są wymagane do uruchomienia podstawowego systemu operacyjnego w zaufanym stanie. Technologia izolacji służy do ograniczenia niezaufanych aplikacji w obszarze piaskownicy, zapewniając, że nie mogą one mieć wpływu na zabezpieczenia systemu. Cały system operacyjny jest segmentowany na bezpieczne sekcje, a każda sekcja jest chroniona przez kombinację różnych technologii zabezpieczeń.
  
  * **Ochrona danych:** w przypadku zgubienia lub kradzieży urządzenia użytkownika HoloLens 2 uniemożliwia nieautoryzowanym aplikacjom odczytywanie poufnych informacji przez poleganie na szyfrowaniu danych za pomocą funkcji BitLocker. 
  
  * **System operacyjny bez hasła:** starsze systemy operacyjne oparte na hasłach mogły przypadkowo uwidocznić użytkowników w celu wyłudzania informacji i często były odpowiedzialne za złamane konta. Windows Holographic for Business hasła do logowania msa i usługi Azure AD oraz wzmacnia ochronę tożsamości użytkowników przy użyciu Windows Hello™ i FIDO2. 
  
    > [!NOTE]
    > Aby zapewnić obsługę fido2, urządzenie musi być w kompilacji 19041 lub wyższej. 

  * **Bezpieczeństwo sieci:** HoloLens 2 oferuje użytkownikowi większe bezpieczeństwo sieci za pośrednictwem ulepszonych protokołów i ustawień domyślnych.
