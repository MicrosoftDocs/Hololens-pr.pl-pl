---
title: Odblokowywanie Windows Holographic for Business funkcji
description: Po uaktualnieniu do wersji Windows Holographic for Business HoloLens dodatkowe funkcje przeznaczone dla firm.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: b5ae9b0d6859c0f916b5b906e2e9ec54cad6cbd9
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635198"
---
# <a name="unlock-windows-holographic-for-business-features"></a><span data-ttu-id="cc9c7-103">Odblokowywanie Windows Holographic for Business funkcji</span><span class="sxs-lookup"><span data-stu-id="cc9c7-103">Unlock Windows Holographic for Business features</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc9c7-104">Ta strona dotyczy tylko HoloLens pierwszej generacji.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-104">This page only applies to HoloLens 1st Gen.</span></span>

<span data-ttu-id="cc9c7-105">Microsoft HoloLens jest dostępna w wersji *Development Edition*, która działa z platformą Windows Holographic (edycją systemu Windows 10 zaprojektowaną dla systemu HoloLens) oraz w pakiecie [Commercial Suite](hololens-commercial-features.md), który zapewnia dodatkowe funkcje przeznaczone dla firm.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-105">Microsoft HoloLens is available in the *Development Edition*, which runs Windows Holographic (an edition of Windows 10 that is designed for HoloLens), and in the [Commercial Suite](hololens-commercial-features.md), which provides extra features designed for business.</span></span>

<span data-ttu-id="cc9c7-106">Po zakupie pakietu Commercial Suite otrzymasz licencję, która uaktualnia platformę Windows Holographic do Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-106">When you purchase the Commercial Suite, you receive a license that upgrades Windows Holographic to Windows Holographic for Business.</span></span> <span data-ttu-id="cc9c7-107">Tę licencję można zastosować do urządzenia przy użyciu dostawcy zarządzania urządzeniami przenośnymi [(MDM)](#edition-upgrade-by-using-mdm) organizacji lub pakietu [aprowizowania.](#edition-upgrade-by-using-a-provisioning-package)</span><span class="sxs-lookup"><span data-stu-id="cc9c7-107">You can apply this license to the device either by using the organization's [mobile device management (MDM) provider](#edition-upgrade-by-using-mdm) or a [provisioning package](#edition-upgrade-by-using-a-provisioning-package).</span></span>

> [!TIP]
> <span data-ttu-id="cc9c7-108">W Windows 10 wersji 1803 możesz sprawdzić, czy HoloLens została uaktualniona do wersji biznesowej, wybierając pozycję **Ustawienia**  >  **System**.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-108">In Windows 10, version 1803, you can check that the HoloLens has been upgraded to the business edition by selecting **Settings** > **System**.</span></span>

## <a name="edition-upgrade-by-using-mdm"></a><span data-ttu-id="cc9c7-109">Uaktualnianie wersji przy użyciu rozwiązania MDM</span><span class="sxs-lookup"><span data-stu-id="cc9c7-109">Edition upgrade by using MDM</span></span>

<span data-ttu-id="cc9c7-110">Licencję przedsiębiorstwa może zastosować dowolny dostawca mdm, który obsługuje dostawcę usług konfiguracji [(CSP) systemu WindowsLicensing.](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx)</span><span class="sxs-lookup"><span data-stu-id="cc9c7-110">The enterprise license can be applied by any MDM provider that supports the [WindowsLicensing configuration service provider (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span></span> <span data-ttu-id="cc9c7-111">Najnowsza wersja interfejsu API zarządzania urządzeniami przenośnymi firmy Microsoft będzie obsługiwać usługę WindowsLicensing CSP.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-111">The latest version of the Microsoft MDM API will support WindowsLicensing CSP.</span></span>

<span data-ttu-id="cc9c7-112">Aby uzyskać instrukcje krok po kroku dotyczące uaktualniania HoloLens przy użyciu programu Microsoft Intune, zobacz Uaktualnianie urządzeń z systemem [Windows Holographic do Windows Holographic for Business](/intune/holographic-upgrade).</span><span class="sxs-lookup"><span data-stu-id="cc9c7-112">For step-by-step instructions for upgrading HoloLens by using Microsoft Intune, see [Upgrade devices running Windows Holographic to Windows Holographic for Business](/intune/holographic-upgrade).</span></span>

 <span data-ttu-id="cc9c7-113">W przypadku innych dostawców zarządzania urządzeniami przenośnymi konkretne kroki konfigurowania i wdrażania zasad mogą się różnić.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-113">On other MDM providers, the specific steps for setting up and deploying the policy might vary.</span></span>

## <a name="edition-upgrade-by-using-a-provisioning-package"></a><span data-ttu-id="cc9c7-114">Uaktualnianie wersji przy użyciu pakietu aprowizowania</span><span class="sxs-lookup"><span data-stu-id="cc9c7-114">Edition upgrade by using a provisioning package</span></span>

<span data-ttu-id="cc9c7-115">Pakiety aprowizowania to pliki utworzone przez narzędzie Windows Configuration Designer, które stosuje określoną konfigurację do urządzenia.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-115">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span>

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a><span data-ttu-id="cc9c7-116">Tworzenie pakietu aprowizowania uaktualnia Windows Holographic Edition</span><span class="sxs-lookup"><span data-stu-id="cc9c7-116">Create a provisioning package that upgrades the Windows Holographic edition</span></span>

1. [<span data-ttu-id="cc9c7-117">Utwórz pakiet aprowizowania dla HoloLens.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-117">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="cc9c7-118">Przejdź do **ustawień środowiska**  >  **uruchomieniowego EditionUpgrade** i wybierz **pozycję EditionUpgradeWithLicense.**</span><span class="sxs-lookup"><span data-stu-id="cc9c7-118">Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.</span></span>

    ![Uaktualnij wydanie z wybranym ustawieniem licencji](images/icd1.png)

1. <span data-ttu-id="cc9c7-120">Znajdź plik licencji XML dostarczony podczas zakupu pakietu komercyjnego.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-120">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cc9c7-121">W [pakiecie aprowizowania można skonfigurować dodatkowe ustawienia.](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="cc9c7-121">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="cc9c7-122">W menu **File** (Plik) wybierz polecenie **Save** (Zapisz).</span><span class="sxs-lookup"><span data-stu-id="cc9c7-122">On the **File** menu, select **Save**.</span></span> 

1. <span data-ttu-id="cc9c7-123">Przeczytaj ostrzeżenie, że pliki projektu mogą zawierać poufne informacje, a następnie kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-123">Read the warning that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="cc9c7-124">Podczas tworzenia pakietu aprowizowania możesz uwzględnić poufne informacje w plikach projektu i pliku pakietu aprowizowania (ppkg).</span><span class="sxs-lookup"><span data-stu-id="cc9c7-124">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="cc9c7-125">Mimo że istnieje możliwość zaszyfrowania pliku ppkg, pliki projektu nie są szyfrowane.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-125">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="cc9c7-126">Pliki projektu należy przechowywać w bezpiecznej lokalizacji i usuwać je, gdy nie będą już potrzebne.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-126">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="cc9c7-127">W menu **Eksportuj** wybierz pozycję **Pakiet aprowizowania.**</span><span class="sxs-lookup"><span data-stu-id="cc9c7-127">On the **Export** menu, select **Provisioning package**.</span></span>

1. <span data-ttu-id="cc9c7-128">Zmień **ustawienie Właściciel** na Administrator **IT**, które ustawia pierwszeństwo tego pakietu aprowizowania na wyższe niż inne zastosowane do tego urządzenia z różnych źródeł, a następnie wybierz przycisk **Dalej.**</span><span class="sxs-lookup"><span data-stu-id="cc9c7-128">Change **Owner** to **IT Admin**, which sets the precedence of this provisioning package to be higher than others applied to this device from different sources, and then select **Next**.</span></span>

1. <span data-ttu-id="cc9c7-129">Ustaw wartość dla wersji **pakietu**.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-129">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="cc9c7-130">Możesz wprowadzić zmiany w istniejących pakietach i zmienić numer wersji, aby zaktualizować wcześniej zastosowane pakiety.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-130">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="cc9c7-131">Na stronie Select security details for the provisioning package (Wybierz szczegóły zabezpieczeń **dla pakietu aprowizowania)** wybierz **pozycję Next (Dalej).**</span><span class="sxs-lookup"><span data-stu-id="cc9c7-131">On **Select security details for the provisioning package**, select **Next**.</span></span>

1. <span data-ttu-id="cc9c7-132">Wybierz **przycisk** Dalej, aby określić lokalizację wyjściową, w której ma zostać sbudowaną zawartość pakietu aprowizowania.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-132">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="cc9c7-133">Domyślnie program Windows ICD używa folderu projektu jako lokalizacji wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-133">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="cc9c7-134">Opcjonalnie możesz wybrać pozycję **Przeglądaj,** aby zmienić domyślną lokalizację wyjściową.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-134">Optionally, you can select **Browse** to change the default output location.</span></span>

1. <span data-ttu-id="cc9c7-135">Wybierz opcję **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-135">Select **Next**.</span></span>

1. <span data-ttu-id="cc9c7-136">Wybierz **pozycję Kompilacja,** aby rozpocząć tworzenie pakietu.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-136">Select **Build** to start building the package.</span></span> <span data-ttu-id="cc9c7-137">Na stronie kompilacji są wyświetlane informacje o projekcie, a pasek postępu wskazuje stan kompilacji.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-137">The build page displays the project information, and the progress bar indicates the build status.</span></span>

1. <span data-ttu-id="cc9c7-138">Po zakończeniu kompilacji wybierz pozycję **Zakończ.**</span><span class="sxs-lookup"><span data-stu-id="cc9c7-138">When the build completes, select **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="cc9c7-139">Zastosuj pakiet aprowizowania do HoloLens</span><span class="sxs-lookup"><span data-stu-id="cc9c7-139">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="cc9c7-140">Za pomocą kabla USB podłącz urządzenie do komputera.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-140">Using the USB cable, connect the device to a PC.</span></span> <span data-ttu-id="cc9c7-141">Uruchom urządzenie, ale nie przeszukaj strony dopasowania w początkowym oknie konfiguracji (pierwsza strona z niebieskim polem). </span><span class="sxs-lookup"><span data-stu-id="cc9c7-141">Start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span> <span data-ttu-id="cc9c7-142">Na komputerze HoloLens jako urządzenie w Eksplorator plików.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-142">On the PC, HoloLens shows up as a device in File Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cc9c7-143">Jeśli na HoloLens jest uruchomiony program Windows 10 w wersji 1607 lub starszej, otwórz program Eksplorator plików przez krótkie naciśnięcie i zwolnienie przycisków Volume **Down** i **Power** jednocześnie na urządzeniu.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-143">If the HoloLens device is running Windows 10, version 1607 or earlier, open File Explorer by briefly pressing and releasing the **Volume Down** and **Power** buttons simultaneously on the device.</span></span>

1. <span data-ttu-id="cc9c7-144">W Eksplorator plików przeciągnij i upuść pakiet aprowizowania (ppkg) do magazynu urządzenia.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-144">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

1. <span data-ttu-id="cc9c7-145">Chociaż HoloLens nadal znajduje się na stronie **dopasowania,** naciśnij krótko  i ponownie zwolnij przyciski **Regulacji** głośności i Zasilania.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-145">While HoloLens is still on the **fit** page, briefly press and release the **Volume Down** and **Power** buttons simultaneously again.</span></span>

1. <span data-ttu-id="cc9c7-146">HoloLens pytanie, czy ufasz pakietowi i chcesz go zastosować.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-146">HoloLens asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="cc9c7-147">Upewnij się, że pakiet jest zaufany.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-147">Confirm that you trust the package.</span></span>

1. <span data-ttu-id="cc9c7-148">Zobaczysz, czy pakiet został zastosowany pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-148">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="cc9c7-149">Jeśli nie został on zastosowany pomyślnie, możesz naprawić pakiet i spróbować ponownie.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-149">If it was not applied successfully, you can fix your package and try again.</span></span> <span data-ttu-id="cc9c7-150">Jeśli to się powiedzie, przejdź do konfiguracji urządzenia.</span><span class="sxs-lookup"><span data-stu-id="cc9c7-150">If successful, proceed with device setup.</span></span>
