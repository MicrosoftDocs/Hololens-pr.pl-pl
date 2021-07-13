---
title: Jak ładować bezpośrednio i instalować aplikacje za pośrednictwem HoloLens 2 Instalator aplikacji
description: Dowiedz się, jak instalować aplikacje i rozwiązywać problemy z aplikacjami za pomocą instalatora aplikacji oraz ładować bezpośrednio i instalować aplikacje za pomocą interfejsu użytkownika.
keywords: zarządzanie aplikacją, aplikacja, hololens, instalator aplikacji
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 8f236ee27903069b65d3ded8eb7a1f37c65f535e
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635589"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="e9a7b-104">Instalowanie aplikacji na HoloLens 2 za pośrednictwem Instalator aplikacji</span><span class="sxs-lookup"><span data-stu-id="e9a7b-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="e9a7b-105">Ta funkcja została udostępnione na Windows Holographic w wersji [20H2 – aktualizacja z grudnia 2020 r.](hololens-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="e9a7b-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="e9a7b-106">Upewnij się, że urządzenie [zostało zaktualizowane do](hololens-update-hololens.md) korzystania z tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="e9a7b-107">Dodaliśmy **nową funkcję (Instalator aplikacji),** aby umożliwić bezproblemowe instalowanie aplikacji na urządzeniach z HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="e9a7b-108">Ta funkcja będzie domyślnie **włączona dla urządzeń nieza pomocą programu**.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="e9a7b-109">Aby zapobiec zakłóceniom pracy przedsiębiorstw, instalator aplikacji nie **będzie w** tej chwili dostępny dla zarządzanych urządzeń.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="e9a7b-110">Urządzenie jest uznawane za "zarządzane", **jeśli** spełnione są dowolne z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="e9a7b-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="e9a7b-111">Zarejestrowane w usłudze ZARZĄDZANIA [urządzeniami przenośnymi](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="e9a7b-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="e9a7b-112">Skonfigurowano przy użyciu [pakietu aprowizowania](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="e9a7b-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="e9a7b-113">Tożsamość [użytkownika to](hololens-identity.md) usługa Azure AD</span><span class="sxs-lookup"><span data-stu-id="e9a7b-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="e9a7b-114">Teraz możesz instalować aplikacje bez konieczności włączania trybu dewelopera ani korzystania z Portal urządzeń.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="e9a7b-115">Pobierz (za pośrednictwem portu USB lub za pośrednictwem Microsoft Edge) pakiet Appx na urządzenie i przejdź do pakietu Appx Eksplorator plików w celu monitu o rozpoczynanie instalacji.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="e9a7b-116">Alternatywnie [zainicjuj instalację ze strony internetowej](/windows/msix/app-installer/installing-windows10-apps-web).</span><span class="sxs-lookup"><span data-stu-id="e9a7b-116">Alternatively, [initiate an install from a web page](/windows/msix/app-installer/installing-windows10-apps-web).</span></span> <span data-ttu-id="e9a7b-117">Podobnie jak aplikacje instalowane z usługi Microsoft Store lub ładowane bezpośrednio przy użyciu funkcji wdrażania aplikacji LOB rozwiązania [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) MDM, aplikacje muszą być podpisane cyfrowo za pomocą narzędzia podpisywania, a certyfikat używany do podpisywania musi być zaufany przez urządzenie HoloLens, zanim będzie można wdrożyć aplikację. [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="e9a7b-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <a name="requirements"></a><span data-ttu-id="e9a7b-118">Wymagania</span><span class="sxs-lookup"><span data-stu-id="e9a7b-118">Requirements</span></span>

### <a name="for-your-devices"></a><span data-ttu-id="e9a7b-119">Dla urządzeń:</span><span class="sxs-lookup"><span data-stu-id="e9a7b-119">For your devices:</span></span>

<span data-ttu-id="e9a7b-120">Ta funkcja jest obecnie dostępna w kompilacjach Windows Holographic 20H2 dla HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-120">This feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="e9a7b-121">Upewnij się, że wszystkie urządzenia korzystające z tej metody zostały [zaktualizowane.](hololens-update-hololens.md)</span><span class="sxs-lookup"><span data-stu-id="e9a7b-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <a name="for-your-apps"></a><span data-ttu-id="e9a7b-122">Dla aplikacji:</span><span class="sxs-lookup"><span data-stu-id="e9a7b-122">For your apps:</span></span>

<span data-ttu-id="e9a7b-123">Konfiguracja rozwiązania aplikacji musi być  wzorcem lub wydaniem, ponieważ Instalator aplikacji będą używać zależności ze sklepu. </span><span class="sxs-lookup"><span data-stu-id="e9a7b-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="e9a7b-124">Zobacz więcej na [temat tworzenia pakietów aplikacji.](/windows/msix/app-installer/create-appinstallerfile-vs)</span><span class="sxs-lookup"><span data-stu-id="e9a7b-124">See more about [creating app packages](/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="e9a7b-125">Aplikacje instalowane za pomocą tej metody muszą być podpisane cyfrowo.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="e9a7b-126">Do podpisania aplikacji będzie konieczne użycie certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="e9a7b-127">Certyfikat można pobrać z listy zaufanych urzędu certyfikacji firmy [MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT). W takim przypadku nie trzeba będzie podjąć żadnych dodatkowych działań.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="e9a7b-128">Możesz też podpisać własny certyfikat, jednak ten certyfikat będzie musiał zostać wypchnięty na urządzenie.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="e9a7b-129">Jak podpisywać aplikacje [przy użyciu narzędzia do podpisywania.](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="e9a7b-129">How to sign apps [using the Sign Tool.](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

<span data-ttu-id="e9a7b-130">**Opcje certyfikatów:**</span><span class="sxs-lookup"><span data-stu-id="e9a7b-130">**Certificate options:**</span></span>

- [<span data-ttu-id="e9a7b-131">Lista zaufanych urzędu certyfikacji MS</span><span class="sxs-lookup"><span data-stu-id="e9a7b-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

<span data-ttu-id="e9a7b-132">**Wybierz metodę wdrażania certyfikatu.**</span><span class="sxs-lookup"><span data-stu-id="e9a7b-132">**Pick a certificate deployment method.**</span></span>

- <span data-ttu-id="e9a7b-133">[Pakiety aprowizowania](hololens-provisioning.md) można stosować do urządzeń lokalnych.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="e9a7b-134">Rozwiązanie MDM może służyć do [stosowania certyfikatów z konfiguracjami urządzeń.](/mem/intune/protect/certificates-configure)</span><span class="sxs-lookup"><span data-stu-id="e9a7b-134">MDM can be used to [apply certificates with device configurations](/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="e9a7b-135">Użyj menedżera certyfikatów [na urządzeniu](certificate-manager.md).</span><span class="sxs-lookup"><span data-stu-id="e9a7b-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <a name="installation-method"></a><span data-ttu-id="e9a7b-136">Metoda instalacji</span><span class="sxs-lookup"><span data-stu-id="e9a7b-136">Installation method</span></span>

1. <span data-ttu-id="e9a7b-137">Sprawdź, czy urządzenie nie jest uznawane za zarządzane.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="e9a7b-138">Sprawdź, czy urządzenie HoloLens 2 jest włączone i że użytkownik jest zalogowany.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="e9a7b-139">Na komputerze przejdź do aplikacji niestandardowej i skopiuj plik yourapp.appxbundle do katalogu yourdevicename\Internal Storage\Downloads.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="e9a7b-140">Po zakończeniu kopiowania pliku możesz rozłączyć urządzenie i zakończyć instalację później.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="e9a7b-141">Na urządzeniu HoloLens 2 Otwórz **menu Start,** wybierz pozycję **Wszystkie aplikacje** i uruchom **Eksplorator plików** aplikację.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="e9a7b-142">Przejdź do folderu Pobrane.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="e9a7b-143">W lewym panelu aplikacji może być konieczne wybranie najpierw opcji **To urządzenie,** a następnie przejście do sekcji Pliki do pobrania.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="e9a7b-144">Wybierz plik yourapp.appxbundle.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="e9a7b-145">Zostanie Instalator aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-145">The App Installer will launch.</span></span> <span data-ttu-id="e9a7b-146">Wybierz przycisk **Zainstaluj,** aby zainstalować aplikację.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="e9a7b-147">Zainstalowana aplikacja zostanie automatycznie uruchamiana po zakończeniu instalacji.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-147">The installed app will automatically launch upon the completion of installing.</span></span>

![Instalowanie przykładów mrTK za pośrednictwem Instalator aplikacji](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a><span data-ttu-id="e9a7b-149">Rozwiązywanie problemów z instalacjami</span><span class="sxs-lookup"><span data-stu-id="e9a7b-149">Troubleshooting Installs</span></span>

<span data-ttu-id="e9a7b-150">Jeśli instalacja aplikacji nie powiodła się, zapoznaj się z następującymi tematami, aby rozwiązać problem:</span><span class="sxs-lookup"><span data-stu-id="e9a7b-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="e9a7b-151">Twoja aplikacja jest kompilacją master lub kompilacją wydania.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="e9a7b-152">Urządzenie zostanie zaktualizowane do kompilacji, na której ta funkcja jest dostępna.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="e9a7b-153">Masz połączenie [z Internetem.](hololens-network.md)</span><span class="sxs-lookup"><span data-stu-id="e9a7b-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="e9a7b-154">Punkty [końcowe dla Microsoft Store](hololens-offline.md) są poprawnie skonfigurowane.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <a name="web-installer"></a><span data-ttu-id="e9a7b-155">Instalator sieci Web</span><span class="sxs-lookup"><span data-stu-id="e9a7b-155">Web Installer</span></span>

<span data-ttu-id="e9a7b-156">Użytkownicy mogą instalować aplikację bezpośrednio z serwera internetowego.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="e9a7b-157">Ten przepływ korzysta z Instalator aplikacji w połączeniu z łatwą metodą pobierania i instalowania dystrybucji.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <a name="how-to-set-up-web-install"></a><span data-ttu-id="e9a7b-158">Jak skonfigurować instalację internetową:</span><span class="sxs-lookup"><span data-stu-id="e9a7b-158">How to set up web install:</span></span>

1. <span data-ttu-id="e9a7b-159">Upewnij się, że aplikacja jest poprawnie skonfigurowana do instalacji.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="e9a7b-160">Wykonaj następujące [kroki, aby włączyć instalację ze strony internetowej](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span><span class="sxs-lookup"><span data-stu-id="e9a7b-160">Follow these [steps to enable install from a web page](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <a name="end-user-experience"></a><span data-ttu-id="e9a7b-161">Środowisko użytkownika końcowego:</span><span class="sxs-lookup"><span data-stu-id="e9a7b-161">End user experience:</span></span>

1. <span data-ttu-id="e9a7b-162">Użytkownik odbiera i instaluje certyfikat na urządzeniu przy użyciu metody wybranej wcześniej.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="e9a7b-163">Użytkownik odwiedzi adres URL utworzony w powyższym kroku.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="e9a7b-164">Aplikacja zostanie teraz instalowana na urządzeniu.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-164">The app will now install to the device.</span></span> <span data-ttu-id="e9a7b-165">Aby znaleźć aplikację, otwórz menu Start **i** wybierz **Wszystkie aplikacje,** aby znaleźć aplikację.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="e9a7b-166">Aby uzyskać więcej pomocy dotyczącej rozwiązywania problemów z metodą instalacji instalatora aplikacji, odwiedź [stronę rozwiązywanie problemów z instalatorem aplikacji.](/windows/msix/app-installer/troubleshoot-appinstaller-issues)</span><span class="sxs-lookup"><span data-stu-id="e9a7b-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="e9a7b-167">Interfejs użytkownika podczas procesu aktualizacji nie jest obsługiwany.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-167">UI during the update process is not supported.</span></span> <span data-ttu-id="e9a7b-168">Dlatego opcja ShowPrompt na [tej stronie](/windows/msix/app-installer/update-settings) i powiązane opcje nie są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-168">So the ShowPrompt option on [this page](/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <a name="sample-apps"></a><span data-ttu-id="e9a7b-169">Przykładowe aplikacje</span><span class="sxs-lookup"><span data-stu-id="e9a7b-169">Sample Apps</span></span>

<span data-ttu-id="e9a7b-170">Wypróbuj te Instalator aplikacji jedną z naszych dostępnych przykładowych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e9a7b-170">Try out the App Installer with one of our available sample apps.</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="e9a7b-171">Przykładowe aplikacje</span><span class="sxs-lookup"><span data-stu-id="e9a7b-171">Sample apps</span></span>](/windows/mixed-reality/develop/features-and-samples)
