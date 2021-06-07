---
title: Menedżer certyfikatów
description: Dowiedz się, jak ręcznie instalować i usuwać certyfikaty oraz zarządzać nimi na urządzeniach z rzeczywistością mieszaną HoloLens 2.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: f9dcf98cbd200ac54cd786648fdfe286bff1aa00
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378278"
---
# <a name="certificate-manager"></a><span data-ttu-id="8c421-103">Menedżer certyfikatów</span><span class="sxs-lookup"><span data-stu-id="8c421-103">Certificate Manager</span></span>

- <span data-ttu-id="8c421-104">Ulepszono narzędzia do inspekcji, diagnostyki i weryfikacji zabezpieczeń i zgodności urządzeń za pośrednictwem nowego Menedżera certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="8c421-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="8c421-105">Ta funkcja umożliwi wdrażanie, rozwiązywanie problemów i weryfikowanie certyfikatów na dużą skalę w środowiskach komercyjnych.</span><span class="sxs-lookup"><span data-stu-id="8c421-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="8c421-106">W systemie Windows Holographic w wersji 20H2 dodajemy Menedżera certyfikatów w aplikacji Ustawienia urządzenia HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="8c421-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="8c421-107">Przejdź do **ustawień > Update & Security > Certificates**.</span><span class="sxs-lookup"><span data-stu-id="8c421-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="8c421-108">Ta funkcja zapewnia prosty i przyjazny dla użytkownika sposób wyświetlania, instalowania i usuwania certyfikatów na urządzeniu.</span><span class="sxs-lookup"><span data-stu-id="8c421-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="8c421-109">Dzięki nowej funkcji Menedżer certyfikatów administratorzy i użytkownicy mają teraz ulepszone narzędzia inspekcji, diagnostyki i walidacji, aby zapewnić, że urządzenia pozostaną bezpieczne i zgodne.</span><span class="sxs-lookup"><span data-stu-id="8c421-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="8c421-110">**Inspekcja:** Możliwość zweryfikowania, czy certyfikat został wdrożony poprawnie, lub potwierdzenia, że został on odpowiednio usunięty.</span><span class="sxs-lookup"><span data-stu-id="8c421-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="8c421-111">**Diagnostyka:** W przypadku problemów podczas sprawdzania, czy na urządzeniu istnieją odpowiednie certyfikaty, oszczędzasz czas i pomagasz w rozwiązywaniu problemów.</span><span class="sxs-lookup"><span data-stu-id="8c421-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="8c421-112">**Walidacja:** Sprawdzenie, czy certyfikat służy zamierzony cel i jest funkcjonalny, może zaoszczędzić dużo czasu, szczególnie w środowiskach komercyjnych przed wdrożeniem certyfikatów na większą skalę.</span><span class="sxs-lookup"><span data-stu-id="8c421-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="8c421-113">Aby szybko znaleźć określony certyfikat na liście, dostępne są opcje sortowania według nazwy, magazynu lub daty wygaśnięcia.</span><span class="sxs-lookup"><span data-stu-id="8c421-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="8c421-114">Użytkownicy mogą również bezpośrednio wyszukiwać certyfikat.</span><span class="sxs-lookup"><span data-stu-id="8c421-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="8c421-115">Aby wyświetlić właściwości poszczególnych certyfikatów, wybierz certyfikat i kliknij pozycję **Informacje.**</span><span class="sxs-lookup"><span data-stu-id="8c421-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="8c421-116">Instalacja certyfikatu obsługuje obecnie pliki cer i crt.</span><span class="sxs-lookup"><span data-stu-id="8c421-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="8c421-117">Właściciele urządzeń mogą instalować certyfikaty na komputerze lokalnym i w bieżącym użytkowniku;  Wszyscy inni użytkownicy mogą instalować tylko w programie Current User.</span><span class="sxs-lookup"><span data-stu-id="8c421-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="8c421-118">Użytkownicy mogą usuwać tylko certyfikaty zainstalowane bezpośrednio z interfejsu użytkownika ustawień.</span><span class="sxs-lookup"><span data-stu-id="8c421-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="8c421-119">Jeśli certyfikat został zainstalowany za pośrednictwem innych środków, należy go również usunąć za pomocą tego samego mechanizmu.</span><span class="sxs-lookup"><span data-stu-id="8c421-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <a name="to-install-a-certificate"></a><span data-ttu-id="8c421-120">Aby zainstalować certyfikat:</span><span class="sxs-lookup"><span data-stu-id="8c421-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="8c421-121">Podłącz urządzenie HoloLens 2 do komputera.</span><span class="sxs-lookup"><span data-stu-id="8c421-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="8c421-122">Umieść plik certyfikatu, który chcesz zainstalować, w lokalizacji na urządzeniach HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="8c421-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="8c421-123">Przejdź do **ustawień App > Update & Security > Certificates**, a następnie wybierz pozycję Zainstaluj certyfikat.</span><span class="sxs-lookup"><span data-stu-id="8c421-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="8c421-124">Kliknij **pozycję Importuj** plik i przejdź do lokalizacji, w którym zapisano certyfikat.</span><span class="sxs-lookup"><span data-stu-id="8c421-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="8c421-125">Wybierz **pozycję Store Location (Lokalizacja sklepu).**</span><span class="sxs-lookup"><span data-stu-id="8c421-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="8c421-126">Wybierz **pozycję Magazyn certyfikatów.**</span><span class="sxs-lookup"><span data-stu-id="8c421-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="8c421-127">Kliknij przycisk **Zainstaluj**.</span><span class="sxs-lookup"><span data-stu-id="8c421-127">Click **Install**.</span></span>

<span data-ttu-id="8c421-128">Certyfikat powinien być teraz zainstalowany na urządzeniu.</span><span class="sxs-lookup"><span data-stu-id="8c421-128">The certificate should now be installed on the device.</span></span>

## <a name="to-remove-a-certificate"></a><span data-ttu-id="8c421-129">Aby usunąć certyfikat:</span><span class="sxs-lookup"><span data-stu-id="8c421-129">To remove a certificate:</span></span> 
>[!WARNING]
> <span data-ttu-id="8c421-130">Chociaż certyfikaty wdrożone przez rozwiązanie MDM można wyświetlić w Menedżerze certyfikatów, nie można ich odinstalować w Menedżerze certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="8c421-130">Although you can view MDM-deployed certificates in Certificate Manager, you cannot uninstall them in Certificate Manager.</span></span> <span data-ttu-id="8c421-131">Należy je odinstalować za pośrednictwem rozwiązania MDM.</span><span class="sxs-lookup"><span data-stu-id="8c421-131">You must uninstall them through MDM.</span></span>
1. <span data-ttu-id="8c421-132">Przejdź do **ustawień App > Update and Security > Certificates**(Aktualizacje i > zabezpieczeń).</span><span class="sxs-lookup"><span data-stu-id="8c421-132">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="8c421-133">Wyszukaj certyfikat według nazwy w polu wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="8c421-133">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="8c421-134">Wybierz certyfikat.</span><span class="sxs-lookup"><span data-stu-id="8c421-134">Select the certificate.</span></span>
1. <span data-ttu-id="8c421-135">Kliknij pozycję **Usuń.**</span><span class="sxs-lookup"><span data-stu-id="8c421-135">Click **Remove**</span></span>
1. <span data-ttu-id="8c421-136">Po **wyświetleniu** monitu o potwierdzenie wybierz pozycję Tak.</span><span class="sxs-lookup"><span data-stu-id="8c421-136">Select **Yes** when prompted for confirmation.</span></span>



![Przeglądarka certyfikatów w aplikacji Ustawienia w obszarze Certyfikaty](images/certificate-viewer-device.jpg)

![Obraz przedstawiający sposób instalowania certyfikatu za pomocą interfejsu użytkownika certyfikatu w ustawieniach.](images/certificate-device-install.jpg)
