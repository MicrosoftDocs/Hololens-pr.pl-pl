---
title: Szyfrowanie funkcją BitLocker na urządzeniach HoloLens
description: Dowiedz się, jak włączyć szyfrowanie urządzeń funkcją BitLocker w celu ochrony plików przechowywanych na urządzeniach rzeczywistości mieszanej HoloLens.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 2929cbea826e0cc92a72550c7874995506b94257
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/25/2021
ms.locfileid: "111378237"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a><span data-ttu-id="68782-103">Szyfrowanie funkcją BitLocker na urządzeniach HoloLens (1. generacji)</span><span class="sxs-lookup"><span data-stu-id="68782-103">HoloLens (1st Gen) BitLocker Encryption</span></span>

<span data-ttu-id="68782-104">Urządzenia HoloLens (1. generacja) i HoloLens 2 obsługują szyfrowanie urządzenia przy użyciu funkcji BitLocker, jednak funkcja BitLocker jest zawsze włączona na urządzeniu HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="68782-104">HoloLens (1st gen) and HoloLens 2 both support device encryption using BitLocker, however, BitLocker is always enabled on HoloLens 2.</span></span>

<span data-ttu-id="68782-105">Ten artykuł pomoże włączyć funkcję BitLocker na urządzeniach HoloLens (1. generacji) i zarządzać nimi.</span><span class="sxs-lookup"><span data-stu-id="68782-105">This article will help you enable and manage BitLocker on HoloLens (1st gen).</span></span>

<span data-ttu-id="68782-106">Na urządzeniu HoloLens (1. generacji) można ręcznie włączyć szyfrowanie za pomocą funkcji BitLocker lub za pomocą funkcji zarządzania urządzeniami przenośnymi (MDM).</span><span class="sxs-lookup"><span data-stu-id="68782-106">On HoloLens (1st gen) you can enable BitLocker device encryption manually or using mobile device management (MDM).</span></span> <span data-ttu-id="68782-107">Postępuj zgodnie z tymi instrukcjami, aby włączyć szyfrowanie urządzenia za pomocą funkcji [BitLocker,](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) aby chronić pliki i informacje przechowywane na urządzeniu HoloLens.</span><span class="sxs-lookup"><span data-stu-id="68782-107">Follow these instructions to enable [BitLocker device encryption](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) to protect files and information stored on the HoloLens.</span></span> <span data-ttu-id="68782-108">Szyfrowanie urządzenia pomaga chronić dane przy użyciu metody szyfrowania AES-CBC 128, która jest odpowiednikiem metody [3 EncryptionMethodByDriveType](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) w dostawcy usług konfiguracji funkcji BitLocker.</span><span class="sxs-lookup"><span data-stu-id="68782-108">Device encryption helps protect your data using the AES-CBC 128 encryption method, which is equivalent to [EncryptionMethodByDriveType method 3](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) in the BitLocker configuration service provider (CSP).</span></span> <span data-ttu-id="68782-109">Personel, który ma prawidłowy klucz szyfrowania (na przykład hasło), może go odszyfrować lub przeprowadzić odzyskiwanie danych.</span><span class="sxs-lookup"><span data-stu-id="68782-109">Personnel who have the correct encryption key (such as a password) can decrypt it or perform a data recovery.</span></span>

## <a name="enable-device-encryption-using-mdm"></a><span data-ttu-id="68782-110">Włączanie szyfrowania urządzenia przy użyciu rozwiązania MDM</span><span class="sxs-lookup"><span data-stu-id="68782-110">Enable device encryption using MDM</span></span>

<span data-ttu-id="68782-111">Możesz użyć dostawcy usługi Mobile Zarządzanie urządzeniami (MDM), aby zastosować zasady, które wymagają szyfrowania urządzenia.</span><span class="sxs-lookup"><span data-stu-id="68782-111">You can use your Mobile Device Management (MDM) provider to apply a policy that requires device encryption.</span></span> <span data-ttu-id="68782-112">Zasady do użycia to ustawienie [Security/RequireDeviceEncryption](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) w programie Policy CSP.</span><span class="sxs-lookup"><span data-stu-id="68782-112">The policy to use is the [Security/RequireDeviceEncryption setting](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) in the Policy CSP.</span></span>

[<span data-ttu-id="68782-113">Zobacz instrukcje dotyczące włączania szyfrowania urządzenia przy użyciu Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="68782-113">See instructions for enabling device encryption using Microsoft Intune.</span></span>](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

<span data-ttu-id="68782-114">Instrukcje dotyczące innych narzędzi MDM można znaleźć w dokumentacji dostawcy usług MDM.</span><span class="sxs-lookup"><span data-stu-id="68782-114">For other MDM tools, see your MDM provider's documentation for instructions.</span></span> <span data-ttu-id="68782-115">Jeśli dostawca rozwiązania MDM wymaga niestandardowego URI szyfrowania urządzenia, użyj następującej konfiguracji:</span><span class="sxs-lookup"><span data-stu-id="68782-115">If your MDM provider requires custom URI for device encryption, use the following configuration:</span></span>

- <span data-ttu-id="68782-116">**Nazwa:** nazwa, która jest wybierana</span><span class="sxs-lookup"><span data-stu-id="68782-116">**Name**: a name of your choice</span></span>
- <span data-ttu-id="68782-117">**Opis:** opcjonalny</span><span class="sxs-lookup"><span data-stu-id="68782-117">**Description**: optional</span></span>
- <span data-ttu-id="68782-118">**OMA-URI:**`./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span><span class="sxs-lookup"><span data-stu-id="68782-118">**OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`</span></span>
- <span data-ttu-id="68782-119">**Typ danych:** liczba całkowita</span><span class="sxs-lookup"><span data-stu-id="68782-119">**Data type**: integer</span></span>
- <span data-ttu-id="68782-120">**Wartość**: `1`</span><span class="sxs-lookup"><span data-stu-id="68782-120">**Value**: `1`</span></span>

## <a name="enable-device-encryption-using-a-provisioning-package"></a><span data-ttu-id="68782-121">Włączanie szyfrowania urządzenia przy użyciu pakietu aprowizowania</span><span class="sxs-lookup"><span data-stu-id="68782-121">Enable device encryption using a provisioning package</span></span>

<span data-ttu-id="68782-122">Pakiety aprowizowania to pliki utworzone przez narzędzie Windows Configuration Designer, które stosują określoną konfigurację do urządzenia.</span><span class="sxs-lookup"><span data-stu-id="68782-122">Provisioning packages are files created by the Windows Configuration Designer tool that apply a specified configuration to a device.</span></span> 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a><span data-ttu-id="68782-123">Tworzenie pakietu aprowizowania, który uaktualnia wersję systemu Windows Holographic i włącza szyfrowanie</span><span class="sxs-lookup"><span data-stu-id="68782-123">Create a provisioning package that upgrades the Windows Holographic edition and enables encryption</span></span>

1. [<span data-ttu-id="68782-124">Utwórz pakiet aprowizowania dla urządzenia HoloLens.</span><span class="sxs-lookup"><span data-stu-id="68782-124">Create a provisioning package for HoloLens.</span></span>](hololens-provisioning.md)
1. <span data-ttu-id="68782-125">Przejdź do **opcji Zabezpieczenia**  >  **zasad ustawień środowiska**  >  **uruchomieniowego** i wybierz pozycję **WymagajUrządzajSzyfruj.**</span><span class="sxs-lookup"><span data-stu-id="68782-125">Go to **Runtime settings** > **Policies** > **Security**, and select **RequireDeviceEncryption**.</span></span>

    ![Wymagaj ustawienia szyfrowania urządzenia skonfigurowanego na tak](images/device-encryption.png)

1. <span data-ttu-id="68782-127">Znajdź plik licencji XML dostarczony podczas zakupu pakietu Commercial Suite.</span><span class="sxs-lookup"><span data-stu-id="68782-127">Find the XML license file that was provided when you purchased the Commercial Suite.</span></span>

1. <span data-ttu-id="68782-128">Przejdź do pliku licencji XML i wybierz go, który został podany podczas zakupu pakietu Commercial Suite.</span><span class="sxs-lookup"><span data-stu-id="68782-128">Browse to and select the XML license file that was provided when you purchased the Commercial Suite.</span></span>
    > [!NOTE]
    > <span data-ttu-id="68782-129">Dodatkowe ustawienia [można skonfigurować w pakiecie aprowizowania.](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="68782-129">You can configure [additional settings in the provisioning package](hololens-provisioning.md).</span></span>

1. <span data-ttu-id="68782-130">W menu **Plik** kliknij polecenie **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="68782-130">On the **File** menu, click **Save**.</span></span> 

1. <span data-ttu-id="68782-131">Przeczytaj ostrzeżenie z wyjaśnieniem, że pliki projektu mogą zawierać poufne informacje, a następnie kliknij przycisk **OK.**</span><span class="sxs-lookup"><span data-stu-id="68782-131">Read the warning explaining that project files may contain sensitive information and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="68782-132">Podczas kompilowania pakietu aprowizowania możesz uwzględnić informacje poufne w plikach projektu i pliku pakietu aprowizowania (ppkg).</span><span class="sxs-lookup"><span data-stu-id="68782-132">When you build a provisioning package, you may include sensitive information in the project files and provisioning package (.ppkg) file.</span></span> <span data-ttu-id="68782-133">Mimo że istnieje możliwość zaszyfrowania pliku ppkg, pliki projektu nie są szyfrowane.</span><span class="sxs-lookup"><span data-stu-id="68782-133">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="68782-134">Pliki projektu należy przechowywać w bezpiecznej lokalizacji i usuwać je, gdy nie będą już potrzebne.</span><span class="sxs-lookup"><span data-stu-id="68782-134">You should store the project files in a secure location and delete the project files when no longer needed.</span></span>

1. <span data-ttu-id="68782-135">W menu **Eksport** kliknij pozycję **Pakiet aprowizowania.**</span><span class="sxs-lookup"><span data-stu-id="68782-135">On the **Export** menu, click **Provisioning package**.</span></span>
1. <span data-ttu-id="68782-136">Zmień **właściciela** na **administratora IT**, co spowoduje ustawienie pierwszeństwa tego pakietu aprowizowania wyższego niż pakiet aprowizowania zastosowany do tego urządzenia z innych źródeł, a następnie wybierz pozycję **Dalej.**</span><span class="sxs-lookup"><span data-stu-id="68782-136">Change **Owner** to **IT Admin**, which will set the precedence of this provisioning package higher than provisioning packages applied to this device from other sources, and then select **Next**.</span></span>
1. <span data-ttu-id="68782-137">Ustaw wartość dla wersji **pakietu**.</span><span class="sxs-lookup"><span data-stu-id="68782-137">Set a value for **Package Version**.</span></span>

    > [!TIP]
    > <span data-ttu-id="68782-138">Możesz wprowadzić zmiany w istniejących pakietach i zmienić numer wersji, aby zaktualizować wcześniej zastosowane pakiety.</span><span class="sxs-lookup"><span data-stu-id="68782-138">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

1. <span data-ttu-id="68782-139">Na stronie Select security details for the provisioning package (Wybierz szczegóły zabezpieczeń **dla pakietu aprowizowania)** kliknij przycisk **Next (Dalej).**</span><span class="sxs-lookup"><span data-stu-id="68782-139">On the **Select security details for the provisioning package**, click **Next**.</span></span>
1. <span data-ttu-id="68782-140">Kliknij **przycisk** Dalej, aby określić lokalizację wyjściową, do której ma przejść pakiet aprowizowania po jego s zbudowaniu.</span><span class="sxs-lookup"><span data-stu-id="68782-140">Click **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="68782-141">Domyślnie funkcja ICD systemu Windows używa folderu projektu jako lokalizacji wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="68782-141">By default, Windows ICD uses the project folder as the output location.</span></span>

    <span data-ttu-id="68782-142">Opcjonalnie możesz kliknąć przycisk Przeglądaj, aby zmienić domyślną lokalizację wyjściową.</span><span class="sxs-lookup"><span data-stu-id="68782-142">Optionally, you can click Browse to change the default output location.</span></span>

1. <span data-ttu-id="68782-143">Kliknij przycisk **Dalej**.</span><span class="sxs-lookup"><span data-stu-id="68782-143">Click **Next**.</span></span>
1. <span data-ttu-id="68782-144">Kliknij **pozycję Build (Kompilacja),** aby rozpocząć kompilowanie pakietu.</span><span class="sxs-lookup"><span data-stu-id="68782-144">Click **Build** to start building the package.</span></span> <span data-ttu-id="68782-145">Informacje o projekcie są wyświetlane na stronie kompilacji, a pasek postępu wskazuje stan kompilacji.</span><span class="sxs-lookup"><span data-stu-id="68782-145">The project information is displayed in the build page and the progress bar indicates the build status.</span></span>
1. <span data-ttu-id="68782-146">Po zakończeniu kompilacji kliknij przycisk **Zakończ.**</span><span class="sxs-lookup"><span data-stu-id="68782-146">When the build completes, click **Finish**.</span></span>

### <a name="apply-the-provisioning-package-to-hololens"></a><span data-ttu-id="68782-147">Stosowanie pakietu aprowizowania na urządzeniach HoloLens</span><span class="sxs-lookup"><span data-stu-id="68782-147">Apply the provisioning package to HoloLens</span></span>

1. <span data-ttu-id="68782-148">Podłącz urządzenie za pośrednictwem portu USB do komputera i  uruchom urządzenie, ale nie przeszukaj strony dopasowania początkowej konfiguracji (pierwsza strona z niebieskim polem).</span><span class="sxs-lookup"><span data-stu-id="68782-148">Connect the device via USB to a PC and start the device, but do not continue past the **fit** page of the initial setup experience (the first page with the blue box).</span></span>
1. <span data-ttu-id="68782-149">Naciśnij krótko i zwolnij przyciski **Volume Down** i **Power** jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="68782-149">Briefly press and release the **Volume Down** and **Power** buttons simultaneously.</span></span>
1. <span data-ttu-id="68782-150">Urządzenie HoloLens będzie wyświetlane jako urządzenie w Eksplorator plików na komputerze.</span><span class="sxs-lookup"><span data-stu-id="68782-150">HoloLens will show up as a device in File Explorer on the PC.</span></span>
1. <span data-ttu-id="68782-151">W Eksplorator plików przeciągnij i upuść pakiet aprowizowania (ppkg) do magazynu urządzenia.</span><span class="sxs-lookup"><span data-stu-id="68782-151">In File Explorer, drag and drop the provisioning package (.ppkg) onto the device storage.</span></span>
1. <span data-ttu-id="68782-152">Naciśnij krótko i zwolnij przyciski **Volume Down** i **Power** jednocześnie na **stronie** dopasowania.</span><span class="sxs-lookup"><span data-stu-id="68782-152">Briefly press and release the **Volume Down** and **Power** buttons simultaneously again while on the **fit** page.</span></span>
1. <span data-ttu-id="68782-153">Urządzenie zapyta, czy pakiet jest zaufany i czy chcesz go zastosować.</span><span class="sxs-lookup"><span data-stu-id="68782-153">The device will ask you if you trust the package and would like to apply it.</span></span> <span data-ttu-id="68782-154">Upewnij się, że pakiet jest zaufany.</span><span class="sxs-lookup"><span data-stu-id="68782-154">Confirm that you trust the package.</span></span>
1. <span data-ttu-id="68782-155">Zobaczysz, czy pakiet został zastosowany pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="68782-155">You will see whether the package was applied successfully or not.</span></span> <span data-ttu-id="68782-156">Jeśli to się nie powiedzie, możesz naprawić pakiet i spróbować ponownie.</span><span class="sxs-lookup"><span data-stu-id="68782-156">If it failed, you can fix your package and try again.</span></span> <span data-ttu-id="68782-157">Jeśli to się powiodło, przejdź do konfiguracji urządzenia.</span><span class="sxs-lookup"><span data-stu-id="68782-157">If it succeeded, proceed with device setup.</span></span>

> [!NOTE]
> <span data-ttu-id="68782-158">Jeśli urządzenie zostało zakupione przed sierpniem 2016 r., musisz zalogować się do urządzenia przy użyciu usługi konto Microsoft, pobrać najnowszą aktualizację systemu operacyjnego, a następnie zresetować system operacyjny, aby zastosować pakiet aprowizowania.</span><span class="sxs-lookup"><span data-stu-id="68782-158">If the device was purchased before August 2016, you will need to sign into the device with a Microsoft account, get the latest OS update, and then reset the OS in order to apply the provisioning package.</span></span>

## <a name="verify-device-encryption"></a><span data-ttu-id="68782-159">Weryfikowanie szyfrowania urządzenia</span><span class="sxs-lookup"><span data-stu-id="68782-159">Verify device encryption</span></span>

<span data-ttu-id="68782-160">Szyfrowanie na urządzeniach HoloLens jest dyskretne.</span><span class="sxs-lookup"><span data-stu-id="68782-160">Encryption is silent on HoloLens.</span></span> <span data-ttu-id="68782-161">Aby sprawdzić stan szyfrowania urządzenia:</span><span class="sxs-lookup"><span data-stu-id="68782-161">To verify the device encryption status:</span></span>

- <span data-ttu-id="68782-162">Na urządzeniach HoloLens przejdź do **tematu Settings** System About  >    >  **(Informacje o systemie ustawień).**</span><span class="sxs-lookup"><span data-stu-id="68782-162">On HoloLens, go to **Settings** > **System** > **About**.</span></span> <span data-ttu-id="68782-163">**Funkcja BitLocker** **jest włączona,** jeśli urządzenie jest zaszyfrowane.</span><span class="sxs-lookup"><span data-stu-id="68782-163">**BitLocker** is **enabled** if the device is encrypted.</span></span> 

    ![Ekran Informacje z włączoną funkcją BitLocker](images/about-encryption.png)
