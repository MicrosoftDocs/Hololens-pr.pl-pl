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
# <a name="security-overview-and-architecture"></a><span data-ttu-id="620f8-104">Omówienie zabezpieczeń i architektura</span><span class="sxs-lookup"><span data-stu-id="620f8-104">Security overview and architecture</span></span>

<span data-ttu-id="620f8-105">Architektura zabezpieczeń urządzenia HoloLens 2 została zaprojektowana i zaprojektowana od podstaw, aby była wolna od starszych problemów z zabezpieczeniami, jednocześnie tworząc zminimalizowaną powierzchnię ataku.</span><span class="sxs-lookup"><span data-stu-id="620f8-105">The HoloLens 2 security architecture was designed and engineered from the ground up to be free from legacy security issues, while creating a minimized attack surface.</span></span> <span data-ttu-id="620f8-106">Ta nowa, nowatorska architektura oferuje bezpieczne lokalizacje magazynu i zaawansowane elementy zabezpieczeń z mechanizmami umożliwiającymi ochronę systemów operacyjnych przed potencjalnymi zagrożeniami i lukami w zabezpieczeniach.</span><span class="sxs-lookup"><span data-stu-id="620f8-106">This new, innovative architecture offers secure storage locations and advanced security elements, with mechanisms capable of shielding operating systems from potential threats and vulnerabilities.</span></span>

<span data-ttu-id="620f8-107">Urządzenie HoloLens 2 łączy sprzęt, oprogramowanie, sieć i usługi, aby zapewnić użytkownikom optymalne środowisko.</span><span class="sxs-lookup"><span data-stu-id="620f8-107">HoloLens 2 combines hardware, software, networking, and services to deliver end-to-end security, while providing the user with an optimal experience.</span></span> <span data-ttu-id="620f8-108">W przypadku urządzenia HoloLens 2 większość funkcji zabezpieczeń jest teraz włączana automatycznie, minimalizując nakład pracy wymagany do prawidłowego skonfigurowania i skonfigurowania systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="620f8-108">With HoloLens 2, a large majority of security features are now turned on automatically, minimizing the effort required to correctly set up and configure the operating system.</span></span>

<span data-ttu-id="620f8-109">Architektura systemu Windows HoloLens 2 i systemu operacyjnego oferuje następujące innowacyjne funkcje zabezpieczeń:</span><span class="sxs-lookup"><span data-stu-id="620f8-109">Windows HoloLens 2 and operating system architecture offers these innovative security features:</span></span>

  * <span data-ttu-id="620f8-110">**Separacja i** izolacja stanu: ta nowa architektura chroni krytyczne części systemu operacyjnego HoloLens 2 przed zmianami— takimi jak te, które są wymagane do uruchomienia podstawowego systemu operacyjnego w zaufanym stanie.</span><span class="sxs-lookup"><span data-stu-id="620f8-110">**State separation and isolation**:  This new architecture protects critical portions of the HoloLens 2 operating system from change - such as those required for the core operating system to boot into a trusted state.</span></span> <span data-ttu-id="620f8-111">Technologia izolacji służy do ograniczenia niezaufanych aplikacji w obszarze piaskownicy, zapewniając, że nie mogą one mieć wpływu na zabezpieczenia systemu.</span><span class="sxs-lookup"><span data-stu-id="620f8-111">Isolation technology is used to confine untrusted apps in a sandbox area, ensuring that they cannot impact the system security.</span></span> <span data-ttu-id="620f8-112">Cały system operacyjny jest segmentowany na bezpieczne sekcje, a każda sekcja jest chroniona przez kombinację różnych technologii zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="620f8-112">The entire operating system is segmented into secure sections, with each section shielded by a combination of different security technologies.</span></span>
  
  * <span data-ttu-id="620f8-113">**Ochrona danych:** w przypadku zgubienia lub kradzieży urządzenia Użytkownika urządzenie HoloLens 2 uniemożliwia nieautoryzowanym aplikacjom odczytywanie poufnych informacji przez użycie szyfrowania danych funkcją BitLocker.</span><span class="sxs-lookup"><span data-stu-id="620f8-113">**Data Protection**: If a user’s device is lost or stolen, HoloLens 2 prevents unauthorized applications from reading sensitive information by relying on BitLocker encryption of data.</span></span> 
  
  * <span data-ttu-id="620f8-114">**System operacyjny bez hasła:** starsze systemy operacyjne oparte na hasłach mogły przypadkowo uwidocznić użytkowników w celu wyłudzania informacji i często były odpowiedzialne za złamane konta.</span><span class="sxs-lookup"><span data-stu-id="620f8-114">**Password-less operating system**:  Older, password-based operating systems could inadvertently expose users to phishing threats and were often responsible for compromised accounts.</span></span> <span data-ttu-id="620f8-115">Windows Holographic for Business eliminuje użycie haseł do logowania w usłudze MSA i usłudze Azure AD oraz wzmacnia ochronę tożsamości użytkowników za pomocą Windows Hello™ i FIDO2.</span><span class="sxs-lookup"><span data-stu-id="620f8-115">Windows Holographic for Business eliminates the use of passwords for MSA and Azure AD sign-in and strengthens user-identity protection with Windows Hello™ and FIDO2 sign-in.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="620f8-116">Aby zapewnić obsługę fido2, urządzenie musi być w kompilacji 19041 lub wyższej.</span><span class="sxs-lookup"><span data-stu-id="620f8-116">To have FIDO2 support, the device must be on Build 19041 or higher.</span></span> 

  * <span data-ttu-id="620f8-117">**Zabezpieczenia sieciowe:** urządzenie HoloLens 2 oferuje większe bezpieczeństwo sieci dzięki ulepszonym protokołom i domyślnym ustawieniem.</span><span class="sxs-lookup"><span data-stu-id="620f8-117">**Network security**: HoloLens 2 offers the user increased network security via improved protocols and default settings.</span></span>
