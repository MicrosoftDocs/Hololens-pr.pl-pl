---
title: Odblokowywanie Windows Holographic for Business zabezpieczeń
description: Po uaktualnieniu do wersji Windows Holographic for Business holoLens udostępnia dodatkowe funkcje, które są przeznaczone dla firm.
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
ms.openlocfilehash: 8d42c935e698f156aed894e4fa5012c9f04d8d49
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378341"
---
# <a name="unlock-windows-holographic-for-business-features"></a><span data-ttu-id="874cd-103">Odblokowywanie Windows Holographic for Business zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="874cd-103">Unlock Windows Holographic for Business features</span></span>

> [!IMPORTANT]
> <span data-ttu-id="874cd-104">Ta strona dotyczy tylko urządzenia HoloLens 1st Gen.</span><span class="sxs-lookup"><span data-stu-id="874cd-104">This page only applies to HoloLens 1st Gen.</span></span>

<span data-ttu-id="874cd-105">Microsoft HoloLens jest dostępna w wersji *Development Edition*, na której działa system Windows Holographic (wersja systemu Windows 10 przeznaczona dla urządzenia HoloLens) oraz w pakiecie [Commercial Suite,](hololens-commercial-features.md)który udostępnia dodatkowe funkcje przeznaczone dla firm.</span><span class="sxs-lookup"><span data-stu-id="874cd-105">Microsoft HoloLens is available in the *Development Edition*, which runs Windows Holographic (an edition of Windows 10 that is designed for HoloLens), and in the [Commercial Suite](hololens-commercial-features.md), which provides extra features designed for business.</span></span>

<span data-ttu-id="874cd-106">Po zakupie pakietu Commercial Suite otrzymasz licencję, która uaktualni system Windows Holographic do wersji Windows Holographic for Business.</span><span class="sxs-lookup"><span data-stu-id="874cd-106">When you purchase the Commercial Suite, you receive a license that upgrades Windows Holographic to Windows Holographic for Business.</span></span> <span data-ttu-id="874cd-107">Tę licencję można zastosować do urządzenia przy użyciu dostawcy zarządzania urządzeniami przenośnymi [(MDM)](#edition-upgrade-by-using-mdm) organizacji lub pakietu [aprowizowania](#edition-upgrade-by-using-a-provisioning-package).</span><span class="sxs-lookup"><span data-stu-id="874cd-107">You can apply this license to the device either by using the organization's [mobile device management (MDM) provider](#edition-upgrade-by-using-mdm) or a [provisioning package](#edition-upgrade-by-using-a-provisioning-package).</span></span>

> [!TIP]
> <span data-ttu-id="874cd-108">W Windows 10 wersji 1803 możesz sprawdzić, czy urządzenie HoloLens zostało uaktualnione do wersji biznesowej, wybierając pozycję  >  **System ustawień**.</span><span class="sxs-lookup"><span data-stu-id="874cd-108">In Windows 10, version 1803, you can check that the HoloLens has been upgraded to the business edition by selecting **Settings** > **System**.</span></span>

## <a name="edition-upgrade-by-using-mdm"></a><span data-ttu-id="874cd-109">Uaktualnianie wersji przy użyciu rozwiązania MDM</span><span class="sxs-lookup"><span data-stu-id="874cd-109">Edition upgrade by using MDM</span></span>

<span data-ttu-id="874cd-110">Licencję przedsiębiorstwa może stosować dowolny dostawca mdm obsługujący dostawcę usług konfiguracji [(CSP) systemu WindowsLicensing.](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx)</span><span class="sxs-lookup"><span data-stu-id="874cd-110">The enterprise license can be applied by any MDM provider that supports the [WindowsLicensing configuration service provider (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx).</span></span> <span data-ttu-id="874cd-111">Najnowsza wersja interfejsu API zarządzania urządzeniami przenośnymi firmy Microsoft będzie obsługiwać usługę WindowsLicensing CSP.</span><span class="sxs-lookup"><span data-stu-id="874cd-111">The latest version of the Microsoft MDM API will support WindowsLicensing CSP.</span></span>

<span data-ttu-id="874cd-112">Aby uzyskać instrukcje krok po kroku dotyczące uaktualniania urządzenia HoloLens przy użyciu urządzenia Microsoft Intune, zobacz Uaktualnianie urządzeń z systemem [Windows Holographic](https://docs.microsoft.com/intune/holographic-upgrade)do Windows Holographic for Business .</span><span class="sxs-lookup"><span data-stu-id="874cd-112">For step-by-step instructions for upgrading HoloLens by using Microsoft Intune, see [Upgrade devices running Windows Holographic to Windows Holographic for Business](https://docs.microsoft.com/intune/holographic-upgrade).</span></span>

 <span data-ttu-id="874cd-113">W przypadku innych dostawców zarządzania urządzeniami przenośnymi konkretne kroki konfigurowania i wdrażania zasad mogą się różnić.</span><span class="sxs-lookup"><span data-stu-id="874cd-113">On other MDM providers, the specific steps for setting up and deploying the policy might vary.</span></span>

## <a name="edition-upgrade-by-using-a-provisioning-package"></a><span data-ttu-id="874cd-114">Uaktualnianie wersji przy użyciu pakietu aprowizowania</span><span class="sxs-lookup"><span data-stu-id="874cd-114">Edition upgrade by using a provisioning package</span></span>

<span data-ttu-id="874cd-115">Pakiety aprowizowania to pliki utworzone przez narzędzie Windows Configuration Designer, które stosują określoną konfigurację do urządzenia.</span><span class="sxs-lookup"><span data-stu-id="874cd-115">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span>

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a><span data-ttu-id="874cd-116">Tworzenie pakietu aprowizowania, który uaktualnia wersję systemu Windows Holographic</span><span class="sxs-lookup"><span data-stu-id="874cd-116">Create a provisioning package that upgrades the Windows Holographic edition</span></span>

1. [<span data-ttu-id="874cd-117">Utwórz pakiet aprowizowania dla urządzenia HoloLens.</span><span class="sxs-lookup"><span data-stu-id="874cd-117">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="874cd-118">Przejdź do **opcji Ustawienia środowiska**  >  **uruchomieniowego EditionUpgrade** i wybierz **pozycję EditionUpgradeWithLicense.**</span><span class="sxs-lookup"><span data-stu-id="874cd-118">Go to **Runtime settings** > **EditionUpgrade**, and select **EditionUpgradeWithLicense**.</span></span>

    ![Uaktualnianie wersji z wybranym ustawieniem licencji](images/icd1.png)

1. <span data-ttu-id="874cd-120">Znajdź plik licencji XML dostarczony podczas zakupu pakietu Commercial Suite.</span><span class="sxs-lookup"><span data-stu-id="874cd-120">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

    > [!NOTE]
    > <span data-ttu-id="874cd-121">Dodatkowe ustawienia [można skonfigurować w pakiecie aprowizowania.](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="874cd-121">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="874cd-122">W menu **File** (Plik) wybierz polecenie **Save** (Zapisz).</span><span class="sxs-lookup"><span data-stu-id="874cd-122">On the **File** menu, select **Save**.</span></span> 

1. <span data-ttu-id="874cd-123">Przeczytaj ostrzeżenie, że pliki projektu mogą zawierać poufne informacje, a następnie kliknij przycisk **OK.**</span><span class="sxs-lookup"><span data-stu-id="874cd-123">Read the warning that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="874cd-124">Podczas kompilowania pakietu aprowizowania możesz uwzględnić informacje poufne w plikach projektu i pliku pakietu aprowizowania (ppkg).</span><span class="sxs-lookup"><span data-stu-id="874cd-124">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="874cd-125">Mimo że istnieje możliwość zaszyfrowania pliku ppkg, pliki projektu nie są szyfrowane.</span><span class="sxs-lookup"><span data-stu-id="874cd-125">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="874cd-126">Pliki projektu należy przechowywać w bezpiecznej lokalizacji i usuwać je, gdy nie będą już potrzebne.</span><span class="sxs-lookup"><span data-stu-id="874cd-126">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="874cd-127">W menu **Eksport** wybierz pozycję **Pakiet aprowizowania.**</span><span class="sxs-lookup"><span data-stu-id="874cd-127">On the **Export** menu, select **Provisioning package**.</span></span>

1. <span data-ttu-id="874cd-128">Zmień **właściciela** na **administratora IT,** który ustawia pierwszeństwo tego pakietu aprowizowania na wyższy niż inne, które mają zastosowanie do tego urządzenia z różnych źródeł, a następnie wybierz pozycję **Dalej.**</span><span class="sxs-lookup"><span data-stu-id="874cd-128">Change **Owner** to **IT Admin**, which sets the precedence of this provisioning package to be higher than others applied to this device from different sources, and then select **Next**.</span></span>

1. <span data-ttu-id="874cd-129">Ustaw wartość dla wersji **pakietu**.</span><span class="sxs-lookup"><span data-stu-id="874cd-129">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="874cd-130">Możesz wprowadzić zmiany w istniejących pakietach i zmienić numer wersji, aby zaktualizować wcześniej zastosowane pakiety.</span><span class="sxs-lookup"><span data-stu-id="874cd-130">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="874cd-131">Na stronie Select security details for the provisioning package (Wybierz szczegóły zabezpieczeń **pakietu aprowizowania)** wybierz pozycję **Next (Dalej).**</span><span class="sxs-lookup"><span data-stu-id="874cd-131">On **Select security details for the provisioning package**, select **Next**.</span></span>

1. <span data-ttu-id="874cd-132">Wybierz **przycisk** Dalej, aby określić lokalizację wyjściową, do której ma przejść pakiet aprowizowania po jego sbudowaną zawartość.</span><span class="sxs-lookup"><span data-stu-id="874cd-132">Select **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="874cd-133">Domyślnie funkcja ICD systemu Windows używa folderu projektu jako lokalizacji wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="874cd-133">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="874cd-134">Opcjonalnie możesz wybrać pozycję **Przeglądaj,** aby zmienić domyślną lokalizację wyjściową.</span><span class="sxs-lookup"><span data-stu-id="874cd-134">Optionally, you can select **Browse** to change the default output location.</span></span>

1. <span data-ttu-id="874cd-135">Wybierz opcję **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="874cd-135">Select **Next**.</span></span>

1. <span data-ttu-id="874cd-136">Wybierz **pozycję Kompilacja,** aby rozpocząć kompilowanie pakietu.</span><span class="sxs-lookup"><span data-stu-id="874cd-136">Select **Build** to start building the package.</span></span> <span data-ttu-id="874cd-137">Na stronie kompilacji są wyświetlane informacje o projekcie, a pasek postępu wskazuje stan kompilacji.</span><span class="sxs-lookup"><span data-stu-id="874cd-137">The build page displays the project information, and the progress bar indicates the build status.</span></span>

1. <span data-ttu-id="874cd-138">Po zakończeniu kompilacji wybierz pozycję **Zakończ.**</span><span class="sxs-lookup"><span data-stu-id="874cd-138">When the build completes, select **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="874cd-139">Stosowanie pakietu aprowizowania na urządzeniach HoloLens</span><span class="sxs-lookup"><span data-stu-id="874cd-139">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="874cd-140">Za pomocą kabla USB podłącz urządzenie do komputera.</span><span class="sxs-lookup"><span data-stu-id="874cd-140">Using the USB cable, connect the device to a PC.</span></span> <span data-ttu-id="874cd-141">Uruchom urządzenie, ale nie przeszukaj strony dopasowania początkowej konfiguracji (pierwsza strona z niebieskim polem). </span><span class="sxs-lookup"><span data-stu-id="874cd-141">Start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span> <span data-ttu-id="874cd-142">Na komputerze urządzenie HoloLens jest Eksplorator plików.</span><span class="sxs-lookup"><span data-stu-id="874cd-142">On the PC, HoloLens shows up as a device in File Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="874cd-143">Jeśli na urządzeniu HoloLens działa urządzenie Windows 10 w wersji 1607 lub starszej, otwórz program Eksplorator plików przez krótkie naciśnięcie i zwolnienie przycisków **Volume Down** i **Power** jednocześnie na urządzeniu.</span><span class="sxs-lookup"><span data-stu-id="874cd-143">If the HoloLens device is running Windows 10, version 1607 or earlier, open File Explorer by briefly pressing and releasing the **Volume Down** and **Power** buttons simultaneously on the device.</span></span>

1. <span data-ttu-id="874cd-144">W Eksplorator plików przeciągnij i upuść pakiet aprowizowania (ppkg) do magazynu urządzenia.</span><span class="sxs-lookup"><span data-stu-id="874cd-144">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>

1. <span data-ttu-id="874cd-145">Chociaż urządzenie HoloLens nadal znajduje się na **stronie** dopasowania, naciśnij krótko i ponownie zwolnij przyciski **Volume Down** i **Power.**</span><span class="sxs-lookup"><span data-stu-id="874cd-145">While HoloLens is still on the **fit** page, briefly press and release the **Volume Down** and **Power** buttons simultaneously again.</span></span>

1. <span data-ttu-id="874cd-146">Urządzenie HoloLens zapyta, czy ufasz pakietowi i chcesz go zastosować.</span><span class="sxs-lookup"><span data-stu-id="874cd-146">HoloLens asks you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="874cd-147">Upewnij się, że pakiet jest zaufany.</span><span class="sxs-lookup"><span data-stu-id="874cd-147">Confirm that you trust the package.</span></span>

1. <span data-ttu-id="874cd-148">Zobaczysz, czy pakiet został zastosowany pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="874cd-148">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="874cd-149">Jeśli nie został on zastosowany pomyślnie, możesz naprawić pakiet i spróbować ponownie.</span><span class="sxs-lookup"><span data-stu-id="874cd-149">If it was not applied successfully, you can fix your package and try again.</span></span> <span data-ttu-id="874cd-150">Jeśli to się powiedzie, przejdź do konfiguracji urządzenia.</span><span class="sxs-lookup"><span data-stu-id="874cd-150">If successful, proceed with device setup.</span></span>
