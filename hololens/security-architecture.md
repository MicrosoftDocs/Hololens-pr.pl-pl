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
ms.openlocfilehash: fd6409f5087ef7d6e7ab90d6ef8dcb83e1c490746803ad869ef075dace24bae7
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665526"
---
# <a name="security-overview-and-architecture"></a>Omówienie zabezpieczeń i architektura

Architektura zabezpieczeń HoloLens 2 została zaprojektowana i zaprojektowana od podstaw w taki sposób, aby była wolna od starszych problemów z zabezpieczeniami przy jednoczesnym utworzeniu zminimalizowanej powierzchni ataku. Ta nowa, nowatorska architektura oferuje bezpieczne lokalizacje przechowywania i zaawansowane elementy zabezpieczeń z mechanizmami umożliwiającymi ochronę systemów operacyjnych przed potencjalnymi zagrożeniami i lukami w zabezpieczeniach.

HoloLens 2 łączy sprzęt, oprogramowanie, sieć i usługi, aby zapewnić użytkownikom optymalne środowisko. W HoloLens 2 większość funkcji zabezpieczeń jest teraz automatycznie włączona, minimalizując nakład pracy wymagany do poprawnego skonfigurowania i skonfigurowania systemu operacyjnego.

Windows HoloLens 2 i architektura systemu operacyjnego oferują następujące innowacyjne funkcje zabezpieczeń:

  * **Separacja i** izolacja stanu: ta nowa architektura chroni krytyczne części systemu operacyjnego HoloLens 2 przed zmianami, takimi jak te, które są wymagane do uruchomienia podstawowego systemu operacyjnego do stanu zaufanego. Technologia izolacji służy do ograniczenia niezaufanych aplikacji w obszarze piaskownicy, zapewniając, że nie mogą one mieć wpływu na zabezpieczenia systemu. Cały system operacyjny jest segmentowany na bezpieczne sekcje, a każda sekcja jest chroniona przez kombinację różnych technologii zabezpieczeń.
  
  * **Ochrona danych:** w przypadku zgubienia lub kradzieży urządzenia użytkownika HoloLens 2 uniemożliwia nieautoryzowanym aplikacjom odczytywanie poufnych informacji przez poleganie na szyfrowaniu danych za pomocą funkcji BitLocker. 
  
  * **System operacyjny bez hasła:** starsze systemy operacyjne oparte na hasłach mogły przypadkowo uwidocznić użytkowników w celu wyłudzania informacji i często były odpowiedzialne za złamane konta. Windows Holographic for Business eliminuje użycie haseł do logowania msa i usługi Azure AD oraz wzmacnia ochronę tożsamości użytkowników przy użyciu Windows Hello™ i FIDO2. 
  
    > [!NOTE]
    > Aby zapewnić obsługę fido2, urządzenie musi być w kompilacji 19041 lub wyższej. 

  * **Zabezpieczenia sieciowe:** HoloLens 2 oferuje użytkownikowi większe bezpieczeństwo sieci za pośrednictwem ulepszonych protokołów i ustawień domyślnych.
