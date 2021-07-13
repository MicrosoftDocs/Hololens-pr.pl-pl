---
title: Szyfrowanie i ochrona danych
description: Dowiedz się więcej o szyfrowaniu i ochronie danych na HoloLens 2, w tym o integracji funkcji BitLocker i platformy Azure.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, Encryption, Data Protection, BitLocker Device, BitLocker, bitlocker, bitlocker encryption, bitlocker encryption, azure integration,
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: e156fc21bfd1541dd8718a7349e7ba82b45576be
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639373"
---
# <a name="encryption-and-data-protection"></a>Szyfrowanie i ochrona danych

Szyfrowanie i ochrona danych chronią dane w przypadku zgubienia lub kradzieży urządzenia oraz uniemożliwiają nieautoryzowanym aplikacjom dostęp do poufnych informacji.

## <a name="bitlocker-device-encryption"></a>Szyfrowanie urządzenia za pomocą funkcji BitLocker

Funkcja BitLocker to funkcja szyfrowania pełnego woluminu, która zapewnia ochronę integralności multimediów tylko do odczytu (RO) i ochronę prywatności na nośnikach zapisywalnych.  Od samego początku stanowi ona efektywną ochronę przed nieautoryzowanym dostępem do danych podczas ataków w trybie offline. HoloLens 2 domyślnie umożliwia funkcji Bitlocker szyfrowanie urządzeń (BDE) ochronę danych przed nieautoryzowanym fizycznym dostępem do urządzenia. Firma Microsoft nieustannie rozwija się, aby spełniać potrzeby przyszłości, nieustannie inwestując i ulepszającą tę technologię.

BDE to funkcja ochrony danych, która wykorzystuje szyfrowanie AES-XTS-256 na wszystkich woluminach w układzie rozdzielonych stanami urządzenia. Program BDE zapewnia szyfrowanie na poziomie urządzenia w układzie rozdzielonych stanami. Funkcja BitLocker szyfrowanie urządzeń jest automatycznie włączona w systemie operacyjnym i stałych woluminach danych i nie może być wyłączona, nawet przez administratorów IT, dzięki czemu urządzenie jest zawsze chronione.

Klucze szyfrowania BDE są następnie używane do przezroczystego odszyfrowywania plików binarnych i danych wymaganych do rozruchu urządzenia. Gdy wolumin systemu operacyjnego jest odblokowany, a system jest uruchamiany, inne woluminy stają się dostępne przy użyciu wersji funkcji ochrony automatycznego odblokowywania specyficznej dla woluminu. Nie są dostępne żadne inne ochrony prywatności użytkownika i dysk można odblokować tylko na tym samym urządzeniu. Wymuszanie tylko do odczytu (RO) na wymaganych woluminach jest stosowane i wymuszane natychmiast, począwszy od pierwszego rozruchu. Klucz odzyskiwania funkcji BitLocker nie jest wymagany w cyklu życia HoloLens 2.

## <a name="azure-integration"></a>Integracja z Azure 

HoloLens 2 umożliwia klientom integrowanie urządzeń z usługami platformy Azure. Komunikacja między HoloLens 2 a platformą Azure używa protokołu TLS (Transport Layer Security) do ochrony danych przenoszanych między sobą i usługami w chmurze, co zapewnia silne uwierzytelnianie, prywatność komunikatów i integralność. Wszystkie usługi platformy Azure w pełni obsługują TLS 1.2 i wszystkie usługi, w których klienci korzystający tylko z wersji TLS 1.2 akceptują tylko ruch TLS 1.2. Standardy szyfrowania danych przesyłania na platformie Azure zostały szczegółowo opisane w tesłudze [Azure Encryption overview (Omówienie szyfrowania na platformie Azure).](/azure/security/fundamentals/encryption-overview) Odwiedź dokumentację platformy Azure, aby dowiedzieć się więcej o najlepszych rozwiązaniach dotyczących zabezpieczeń i [szyfrowania danych na platformie Azure.](/azure/security/fundamentals/data-encryption-best-practices) 

OneDrive, przykład integracji z chmurą z usługą HoloLens 2, ma funkcję automatycznego przekazywania, w której pliki i dokumenty mogą być automatycznie przekazywane do chmury po połączeniu z Internetem. Nie można wyłączyć automatycznego synchronizowania plików za pomocą zasad, ale można je bezpośrednio skonfigurować za pośrednictwem środowiska użytkownika. 
