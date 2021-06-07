---
title: Architektura zabezpieczeń urządzenia HoloLens
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379703"
---
# <a name="security-overview-and-architecture"></a>Omówienie zabezpieczeń i architektura

Architektura zabezpieczeń urządzenia HoloLens 2 została zaprojektowana i zaprojektowana od podstaw, aby była wolna od starszych problemów z zabezpieczeniami, jednocześnie tworząc zminimalizowaną powierzchnię ataku. Ta nowa, nowatorska architektura oferuje bezpieczne lokalizacje magazynu i zaawansowane elementy zabezpieczeń z mechanizmami umożliwiającymi ochronę systemów operacyjnych przed potencjalnymi zagrożeniami i lukami w zabezpieczeniach.

Urządzenie HoloLens 2 łączy sprzęt, oprogramowanie, sieć i usługi, aby zapewnić użytkownikom optymalne środowisko. W przypadku urządzenia HoloLens 2 większość funkcji zabezpieczeń jest teraz włączana automatycznie, minimalizując nakład pracy wymagany do prawidłowego skonfigurowania i skonfigurowania systemu operacyjnego.

Architektura systemu Windows HoloLens 2 i systemu operacyjnego oferuje następujące innowacyjne funkcje zabezpieczeń:

  * **Separacja i** izolacja stanu: ta nowa architektura chroni krytyczne części systemu operacyjnego HoloLens 2 przed zmianami— takimi jak te, które są wymagane do uruchomienia podstawowego systemu operacyjnego w zaufanym stanie. Technologia izolacji służy do ograniczenia niezaufanych aplikacji w obszarze piaskownicy, zapewniając, że nie mogą one mieć wpływu na zabezpieczenia systemu. Cały system operacyjny jest segmentowany na bezpieczne sekcje, a każda sekcja jest chroniona przez kombinację różnych technologii zabezpieczeń.
  
  * **Ochrona danych:** w przypadku zgubienia lub kradzieży urządzenia Użytkownika urządzenie HoloLens 2 uniemożliwia nieautoryzowanym aplikacjom odczytywanie poufnych informacji przez użycie szyfrowania danych funkcją BitLocker. 
  
  * **System operacyjny bez hasła:** starsze systemy operacyjne oparte na hasłach mogły przypadkowo uwidocznić użytkowników w celu wyłudzania informacji i często były odpowiedzialne za złamane konta. Windows Holographic for Business eliminuje użycie haseł do logowania w usłudze MSA i usłudze Azure AD oraz wzmacnia ochronę tożsamości użytkowników za pomocą Windows Hello™ i FIDO2. 
  
    > [!NOTE]
    > Aby zapewnić obsługę fido2, urządzenie musi być w kompilacji 19041 lub wyższej. 

  * **Zabezpieczenia sieciowe:** urządzenie HoloLens 2 oferuje większe bezpieczeństwo sieci dzięki ulepszonym protokołom i domyślnym ustawieniem.
