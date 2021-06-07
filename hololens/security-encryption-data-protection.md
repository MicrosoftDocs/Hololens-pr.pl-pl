---
title: Szyfrowanie i ochrona danych
description: Dowiedz się więcej o szyfrowaniu i ochronie danych na urządzeniach HoloLens 2, w tym o integracji funkcji BitLocker i platformy Azure.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, Encryption, Data Protection, BitLocker Device, BitLocker, bitlocker, bitlocker, bitlocker encryption, azure integration,
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: ebe1d072f36cdf4ad9b3543882e61fa2ed4a0300
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379702"
---
# <a name="encryption-and-data-protection"></a>Szyfrowanie i ochrona danych

Szyfrowanie i ochrona danych chronią dane w przypadku zgubienia lub kradzieży urządzenia oraz uniemożliwiają nieautoryzowanym aplikacjom dostęp do poufnych informacji.

## <a name="bitlocker-device-encryption"></a>Szyfrowanie urządzenia za pomocą funkcji BitLocker

Funkcja BitLocker to funkcja szyfrowania pełnego woluminu, która zapewnia ochronę integralności multimediów tylko do odczytu (RO) i ochronę prywatności na nośnikach zapisywalnych.  Od czasu jego powstania stanowi ona efektywną ochronę przed nieautoryzowanym dostępem do danych podczas ataków w trybie offline. Urządzenie HoloLens 2 domyślnie szyfrowanie urządzeń funkcją BitLocker (BDE) w celu ochrony danych przed nieautoryzowanym fizycznym dostępem do urządzenia. Firma Microsoft nieustannie rozwija się, aby zaspokoić potrzeby przyszłości, nadal inwestować i ulepszać tę technologię.

BDE to funkcja ochrony danych, która wykorzystuje szyfrowanie AES-XTS-256 na wszystkich woluminach w układzie rozdzielonych stanami urządzenia. Program BDE zapewnia szyfrowanie na poziomie urządzenia w układzie rozdzielonych stanami. Funkcja BitLocker szyfrowanie urządzeń jest automatycznie włączona w systemie operacyjnym i stałych woluminach danych i nie może być wyłączona, nawet przez administratorów IT, dzięki czemu urządzenie jest zawsze chronione.

Klucze szyfrowania BDE są następnie używane do przezroczystego odszyfrowywania plików binarnych i danych wymaganych do rozruchu urządzenia. W przypadku odblokowania woluminu systemu operacyjnego i rozruchu systemu inne woluminy stają się dostępne przy użyciu wersji funkcji ochrony przed automatycznym odblokowywaniem dla określonego woluminu. Nie są dostępne żadne inne ochrony prywatności użytkownika i dysk można odblokować tylko na tym samym urządzeniu. Wymuszanie tylko do odczytu (RO) na wymaganych woluminach jest stosowane i wymuszane natychmiast, począwszy od pierwszego rozruchu. Klucz odzyskiwania funkcji BitLocker nie jest wymagany w cyklu życia urządzenia HoloLens 2.

## <a name="azure-integration"></a>Integracja z Azure 

Urządzenie HoloLens 2 umożliwia klientom integrowanie urządzeń z usługami platformy Azure. Komunikacja między urządzeniami HoloLens 2 i platformą Azure używa protokołu TLS (Transport Layer Security) do ochrony danych przenoszniętych między samymi urządzeniami i usługami w chmurze, co zapewnia silne uwierzytelnianie, prywatność komunikatów i integralność. Wszystkie usługi platformy Azure w pełni obsługują TLS 1.2 i wszystkie usługi, w przypadku których klienci korzystający tylko z wersji TLS 1.2 akceptują tylko ruch TLS 1.2. Standardy szyfrowania danych podczas przesyłania danych na platformie Azure zostały szczegółowo opisane w tesłudze [Azure Encryption overview (Omówienie szyfrowania na platformie Azure).](https://docs.microsoft.com/azure/security/fundamentals/encryption-overview) Zapoznaj się z dokumentacją platformy Azure, aby dowiedzieć się więcej o najlepszych rozwiązaniach dotyczących zabezpieczeń i [szyfrowania danych na platformie Azure.](https://docs.microsoft.com/azure/security/fundamentals/data-encryption-best-practices) 

Usługa OneDrive, przykład integracji z chmurą z urządzeniem HoloLens 2, ma funkcję automatycznego przekazywania, która umożliwia automatyczne przekazywanie plików i dokumentów do chmury po połączeniu z Internetem. Nie można wyłączyć automatycznego synchronizowania plików za pośrednictwem zasad, ale można je bezpośrednio skonfigurować za pośrednictwem środowiska użytkownika. 
