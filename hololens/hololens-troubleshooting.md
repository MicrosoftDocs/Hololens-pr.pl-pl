---
title: HoloLens Rozwiązywanie problemów z urządzeniami
description: Bądź na bieżąco z najpopularniejszymi rozwiązaniami, które HoloLens problemów z urządzeniami i technikami rozwiązywania problemów.
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problemy, usterka, rozwiązywanie problemów, poprawka, pomoc, obsługa techniczna, HoloLens, emulator
ms.openlocfilehash: b07514e73e43d267aa856c0fb9a256448e565000
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635453"
---
# <a name="device-troubleshooting"></a><span data-ttu-id="01015-104">Rozwiązywanie problemów z urządzeniami</span><span class="sxs-lookup"><span data-stu-id="01015-104">Device Troubleshooting</span></span>

<span data-ttu-id="01015-105">W tym artykule opisano sposób rozwiązywania kilku typowych HoloLens problemów.</span><span class="sxs-lookup"><span data-stu-id="01015-105">This article describes how to resolve several common HoloLens issues.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="01015-106">Przed rozpoczęciem procedury rozwiązywania problemów upewnij się, że urządzenie jest obciążane od **20 do 40%** pojemności baterii, jeśli jest to możliwe.</span><span class="sxs-lookup"><span data-stu-id="01015-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="01015-107">Wskaźniki [naładowania baterii znajdujące](hololens2-setup.md#lights-that-indicate-the-battery-level) się pod przyciskiem zasilania to szybki sposób na sprawdzenie pojemności baterii bez logowania się do urządzenia.</span><span class="sxs-lookup"><span data-stu-id="01015-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<a id="list"></a>

<span data-ttu-id="01015-108">**Znane problemy**</span><span class="sxs-lookup"><span data-stu-id="01015-108">**Known Issues**</span></span>
- [<span data-ttu-id="01015-109">Wideo remote assist zawiesza się po 20 minutach</span><span class="sxs-lookup"><span data-stu-id="01015-109">Remote Assist video freezes after 20 minutes</span></span>](#remote-assist-video-freezes-after-20-minutes)
- [<span data-ttu-id="01015-110">Automatyczne logowanie wymaga zalogowania</span><span class="sxs-lookup"><span data-stu-id="01015-110">Auto-login asks for log-in</span></span>](#auto-login-asks-for-log-in)
- [<span data-ttu-id="01015-111">Microsoft Edge nie można uruchomić</span><span class="sxs-lookup"><span data-stu-id="01015-111">Microsoft Edge fails to launch</span></span>](#microsoft-edge-fails-to-launch)
- [<span data-ttu-id="01015-112">Klawiatura nie przełącza się na znaki specjalne</span><span class="sxs-lookup"><span data-stu-id="01015-112">Keyboard doesn't switch to special characters</span></span>](#keyboard-doesnt-switch-to-special-characters)
- [<span data-ttu-id="01015-113">Pobieranie zablokowanych plików nie pokazuje błędu</span><span class="sxs-lookup"><span data-stu-id="01015-113">Downloading locked files doesn't show error</span></span>](#downloading-locked-files-doesnt-error)
- [<span data-ttu-id="01015-114">Portal urządzeń przekazywania/pobierania plików</span><span class="sxs-lookup"><span data-stu-id="01015-114">Device Portal file upload/download times out</span></span>](#device-portal-file-uploaddownload-times-out)
- [<span data-ttu-id="01015-115">Niebieski ekran po wywrzeniu z wersji zapoznawczej niejawnego programu testów na urządzeniu z flashem kompilacji niejawnego testera</span><span class="sxs-lookup"><span data-stu-id="01015-115">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [<span data-ttu-id="01015-116">OneDrive nie przekaże automatycznie obrazów</span><span class="sxs-lookup"><span data-stu-id="01015-116">OneDrive doesn't automatically upload pictures</span></span>](#onedrive-doesnt-automatically-upload-pictures)

<span data-ttu-id="01015-117">**Ogólne**</span><span class="sxs-lookup"><span data-stu-id="01015-117">**General**</span></span>
- [<span data-ttu-id="01015-118">HoloLens nie odpowiada lub nie można uruchomić</span><span class="sxs-lookup"><span data-stu-id="01015-118">HoloLens is unresponsive or won't start</span></span>](#hololens-is-unresponsive-or-wont-start)
- [<span data-ttu-id="01015-119">Błąd "Mała ilość miejsca na dysku"</span><span class="sxs-lookup"><span data-stu-id="01015-119">"Low Disk Space" error</span></span>](#low-disk-space-error)
- [<span data-ttu-id="01015-120">Niepowodzenie awarii</span><span class="sxs-lookup"><span data-stu-id="01015-120">Calibration Fails</span></span>](#calibration-fails)
- [<span data-ttu-id="01015-121">Nie można się zalogować, ponieważ HoloLens wcześniej została ustawiona dla kogoś innego</span><span class="sxs-lookup"><span data-stu-id="01015-121">Can't sign in because my HoloLens was previously set up for someone else</span></span>](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [<span data-ttu-id="01015-122">Unity nie działa</span><span class="sxs-lookup"><span data-stu-id="01015-122">Unity isn't working</span></span>](#unity-isnt-working)
- [<span data-ttu-id="01015-123">Windows Portal urządzeń nie działa prawidłowo</span><span class="sxs-lookup"><span data-stu-id="01015-123">Windows Device Portal isn't working correctly</span></span>](#windows-device-portal-isnt-working-correctly)
- [<span data-ttu-id="01015-124">HoloLens Emulator nie działa</span><span class="sxs-lookup"><span data-stu-id="01015-124">The HoloLens Emulator isn't working</span></span>](#the-hololens-emulator-isnt-working)

<span data-ttu-id="01015-125">**Dane wejściowe**</span><span class="sxs-lookup"><span data-stu-id="01015-125">**Input**</span></span>
- [<span data-ttu-id="01015-126">Polecenia głosowe nie działają</span><span class="sxs-lookup"><span data-stu-id="01015-126">Voice commands aren't working</span></span>](#voice-commands-arent-working)
- [<span data-ttu-id="01015-127">Ręczne wprowadzanie danych nie działa</span><span class="sxs-lookup"><span data-stu-id="01015-127">Hand input isn't working</span></span>](#hand-input-isnt-working)

<span data-ttu-id="01015-128">**Połączenia**</span><span class="sxs-lookup"><span data-stu-id="01015-128">**Connectivity**</span></span>
- [<span data-ttu-id="01015-129">Nie można nawiązać połączenia z siecią Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="01015-129">Can't connect to Wi-Fi</span></span>](#cant-connect-to-wi-fi)

<span data-ttu-id="01015-130">**Urządzenia zewnętrzne**</span><span class="sxs-lookup"><span data-stu-id="01015-130">**External Devices**</span></span> 
- [<span data-ttu-id="01015-131">Bluetooth urządzenia nie są parowane</span><span class="sxs-lookup"><span data-stu-id="01015-131">Bluetooth devices aren't pairing</span></span>](#bluetooth-devices-arent-pairing)
- [<span data-ttu-id="01015-132">Mikrofon USB-C nie działa</span><span class="sxs-lookup"><span data-stu-id="01015-132">USB-C Microphone isn't working</span></span>](#usb-c-microphone-isnt-working)
- [<span data-ttu-id="01015-133">Urządzenia wymienione jako dostępne w Ustawienia nie działają</span><span class="sxs-lookup"><span data-stu-id="01015-133">Devices listed as available in Settings don't work</span></span>](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a><span data-ttu-id="01015-134">Wideo remote assist zawiesza się po 20 minutach</span><span class="sxs-lookup"><span data-stu-id="01015-134">Remote Assist video freezes after 20 minutes</span></span>

> [!NOTE]
> <span data-ttu-id="01015-135">Istnieje nowsza wersja usługi Remote Assist, która zawiera poprawkę dla tego problemu.</span><span class="sxs-lookup"><span data-stu-id="01015-135">There is a newer version of Remote Assist which has a fix for this issue.</span></span> <span data-ttu-id="01015-136">Zaktualizuj [usługę Remote Assist](holographic-store-apps.md#update-apps) do najnowszej wersji, aby uniknąć tego problemu.</span><span class="sxs-lookup"><span data-stu-id="01015-136">Please [update Remote Assist](holographic-store-apps.md#update-apps) to the latest version to avoid this issue.</span></span>

> [!NOTE]
> <span data-ttu-id="01015-137">Ze względu na ważność tego znanego problemu tymczasowo wstrzymano dostępność systemu Windows Holographic w wersji 21H1.</span><span class="sxs-lookup"><span data-stu-id="01015-137">Due to this Known Issue's severity we had temporarily paused the availability of Windows Holographic, version 21H1.</span></span> <span data-ttu-id="01015-138">Kompilacja 21H1 jest teraz ponownie dostępna, więc urządzenia mogą zostać ponownie zaktualizowane do najnowszej kompilacji 21H1.</span><span class="sxs-lookup"><span data-stu-id="01015-138">The 21H1 build is now available again, so devices may once again be updated to the latest 21H1 build.</span></span>

<span data-ttu-id="01015-139">W najnowszej wersji systemu Windows Holographic w wersji [21H1](hololens-release-notes.md#windows-holographic-version-21h1)niektórzy użytkownicy usługi Remote Assist doświadczyli blokowania wideo podczas wywołań przez 20 minut.</span><span class="sxs-lookup"><span data-stu-id="01015-139">On the latest release of [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), some users of Remote Assist have experienced video freezing during calls over 20 minutes.</span></span> <span data-ttu-id="01015-140">Jest to znany **problem.**</span><span class="sxs-lookup"><span data-stu-id="01015-140">This is a **known issue**.</span></span>

### <a name="workarounds"></a><span data-ttu-id="01015-141">Obejścia</span><span class="sxs-lookup"><span data-stu-id="01015-141">Workarounds</span></span>

<span data-ttu-id="01015-142">Jeśli nie możesz zaktualizować usługi Remote Assist do nowszej kompilacji, spróbuj wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="01015-142">If you are unable to update Remote Assist to a newer build try the following work around.</span></span>

#### <a name="restart-in-between-calls"></a><span data-ttu-id="01015-143">Uruchom ponownie między wywołaniami</span><span class="sxs-lookup"><span data-stu-id="01015-143">Restart in between calls</span></span>

<span data-ttu-id="01015-144">Jeśli połączenia są trwać ponad 20 minut i występuje ten problem, spróbuj ponownie uruchomić urządzenie.</span><span class="sxs-lookup"><span data-stu-id="01015-144">If your calls are going over a length of 20 minutes and you are experiencing this issue, try rebooting your device.</span></span> <span data-ttu-id="01015-145">Ponowne uruchomienie urządzenia między wywołaniami usługi Remote Assist spowoduje odświeżenie urządzenia i jego ponowne uruchomienie w dobrym stanie.</span><span class="sxs-lookup"><span data-stu-id="01015-145">Rebooting your device between Remote Assist calls will refresh your device and put it back into a good state.</span></span>

<span data-ttu-id="01015-146">Aby szybko ponownie uruchomić urządzenie na platformie Windows Holographic, w wersji [21H1](hololens-release-notes.md#windows-holographic-version-21h1) otwórz menu Start i wybierz ikonę użytkownika, a następnie wybierz pozycję **Uruchom ponownie.**</span><span class="sxs-lookup"><span data-stu-id="01015-146">To quickly restart a device on [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) open the start menu, and select the user icon, then select **Restart**.</span></span>

[<span data-ttu-id="01015-147">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="01015-147">Back to list</span></span>](#list)

## <a name="auto-login-asks-for-log-in"></a><span data-ttu-id="01015-148">Automatyczne logowanie prosi o zalogowanie</span><span class="sxs-lookup"><span data-stu-id="01015-148">Auto-login asks for log-in</span></span>

<span data-ttu-id="01015-149">Urządzenie HoloLens 2 można skonfigurować do automatycznego logowania się za pośrednictwem opcji logowania kont usługi **Ustawienia —**> i w obszarze Wymagane ustawienie wartości  ->    ->    **Nigdy.**</span><span class="sxs-lookup"><span data-stu-id="01015-149">A HoloLens 2 device can be configured to automatically login in via **Settings** -> **Accounts** -> **Sign-in Options** -> and under **Required** setting the value to **Never**.</span></span> <span data-ttu-id="01015-150">Niektórzy użytkownicy mogą być zobowiązani do zalogowania się na urządzeniu ponownie podczas aktualizowania urządzenia przy użyciu znacznie dużej aktualizacji, takiej jak aktualizacja funkcji.</span><span class="sxs-lookup"><span data-stu-id="01015-150">Some users may be required to log-in to the device again when updating a device with a substantially large update, such as a feature update.</span></span> <span data-ttu-id="01015-151">Jest to znany **problem.**</span><span class="sxs-lookup"><span data-stu-id="01015-151">This is a **known issue**.</span></span>

<span data-ttu-id="01015-152">Przykład sytuacji, w których może się to zdarzyć:</span><span class="sxs-lookup"><span data-stu-id="01015-152">Example of when this could occur:</span></span>

- <span data-ttu-id="01015-153">Aktualizowanie urządzenia z systemu Windows Holographic w wersji 2004 (kompilacja 19041.xxxx) do wersji Windows Holographic, wersja 21H1 (kompilacja 20346.xxxx)</span><span class="sxs-lookup"><span data-stu-id="01015-153">Updating a device from Windows Holographic, version 2004 (Build 19041.xxxx) to Windows Holographic, version 21H1 (Build 20346.xxxx)</span></span>
- <span data-ttu-id="01015-154">Aktualizowanie urządzenia w celu podjęcia dużej aktualizacji w tej samej kompilacji, np. Windows Holographic, wersja 2004 do wersji Windows Holographic, wersja 20H2</span><span class="sxs-lookup"><span data-stu-id="01015-154">Updating a device to take a large update on the same major build, e.g. Windows Holographic, version 2004 to Windows Holographic, version 20H2</span></span>
- <span data-ttu-id="01015-155">Aktualizowanie urządzenia z obrazu fabrycznego do najnowszego obrazu</span><span class="sxs-lookup"><span data-stu-id="01015-155">Updating a device from a factory image to the latest image</span></span>

<span data-ttu-id="01015-156">Nie powinno to mieć miejsca w trakcie:</span><span class="sxs-lookup"><span data-stu-id="01015-156">This should not occur during:</span></span>

- <span data-ttu-id="01015-157">Urządzenia korzystające z comiesięcznej aktualizacji obsługi</span><span class="sxs-lookup"><span data-stu-id="01015-157">Devices taking a monthly servicing update</span></span>

<span data-ttu-id="01015-158">Omiń metody:</span><span class="sxs-lookup"><span data-stu-id="01015-158">Work around methods:</span></span>

- <span data-ttu-id="01015-159">Metody logowania, takie jak numer PIN, hasło, irysy, uwierzytelnianie internetowe lub klucze FIDO2.</span><span class="sxs-lookup"><span data-stu-id="01015-159">Sign-in methods such as PIN, Password, Iris, Web Authentication, or FIDO2 keys.</span></span>
- <span data-ttu-id="01015-160">Jeśli nie można zapamiętać numeru PIN urządzenia i inne metody uwierzytelniania są niedostępne, użytkownik może użyć [ręcznego trybu reflashingu.](hololens-recovery.md#manual-procedure)</span><span class="sxs-lookup"><span data-stu-id="01015-160">If device PIN cannot be remembered, and other authentication methods are not available, then a user can use [manual reflashing mode](hololens-recovery.md#manual-procedure).</span></span>

[<span data-ttu-id="01015-161">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="01015-161">Back to list</span></span>](#list)

## <a name="microsoft-edge-fails-to-launch"></a><span data-ttu-id="01015-162">Microsoft Edge nie można uruchomić</span><span class="sxs-lookup"><span data-stu-id="01015-162">Microsoft Edge fails to launch</span></span>

> [!NOTE]
> <span data-ttu-id="01015-163">Ten problem został pierwotnie utworzony z myślą o wersji wysyłkowej Microsoft Edge o tym.</span><span class="sxs-lookup"><span data-stu-id="01015-163">This issue was originally created with the shipping version of Microsoft Edge in-mind.</span></span> <span data-ttu-id="01015-164">Ten problem można rozwiązać w nowej [Microsoft Edge](hololens-new-edge.md).</span><span class="sxs-lookup"><span data-stu-id="01015-164">This issue may be resolved in the [new Microsoft Edge](hololens-new-edge.md).</span></span> <span data-ttu-id="01015-165">Jeśli tak nie jest, prosimy o opinię.</span><span class="sxs-lookup"><span data-stu-id="01015-165">If it is not, please file feedback.</span></span>

<span data-ttu-id="01015-166">Kilku klientów zgłosiło problem, który Microsoft Edge nie można uruchomić.</span><span class="sxs-lookup"><span data-stu-id="01015-166">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="01015-167">W przypadku tych klientów problem będzie nadal występował po ponownym uruchomieniu i nie zostanie rozwiązany Windows aktualizacji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="01015-167">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="01015-168">Jeśli ten problem występuje i potwierdzono, że program [Windows](hololens-updates.md#manually-check-for-updates)jest aktualny, prosimy o zgłaszanie usterki z aplikacji Centrum opinii z następującą kategorią i podkategorią: Instalowanie i aktualizowanie usługi > Pobieranie, instalowanie i konfigurowanie usługi [Windows](hololens-feedback.md) Update.</span><span class="sxs-lookup"><span data-stu-id="01015-168">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="01015-169">Nie ma znanych obejść, ponieważ do tej pory nie można było głównej przyczyny problemu.</span><span class="sxs-lookup"><span data-stu-id="01015-169">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="01015-170">Zgłoszenie usterki za pośrednictwem Centrum opinii pomoże w naszym badaniu!</span><span class="sxs-lookup"><span data-stu-id="01015-170">Filing a bug via Feedback Hub will help our investigation!</span></span> <span data-ttu-id="01015-171">Jest to znany **problem.**</span><span class="sxs-lookup"><span data-stu-id="01015-171">This is a **known issue**.</span></span>

[<span data-ttu-id="01015-172">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="01015-172">Back to list</span></span>](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a><span data-ttu-id="01015-173">Klawiatura nie przełącza się na znaki specjalne</span><span class="sxs-lookup"><span data-stu-id="01015-173">Keyboard doesn't switch to special characters</span></span>

<span data-ttu-id="01015-174">Podczas OOBE występuje problem, który występuje, gdy użytkownik wybrał konto służbowe i wprowadza hasło, próbując przełączyć się na znaki specjalne na klawiaturze, naciskając przycisk &123, nie zmienia się na znaki specjalne.</span><span class="sxs-lookup"><span data-stu-id="01015-174">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> <span data-ttu-id="01015-175">Jest to znany **problem.**</span><span class="sxs-lookup"><span data-stu-id="01015-175">This is a **known issue**.</span></span>

<span data-ttu-id="01015-176">Omiń:</span><span class="sxs-lookup"><span data-stu-id="01015-176">Work-arounds:</span></span>
-   <span data-ttu-id="01015-177">Zamknij klawiaturę i otwórz ją ponownie, naciskając pole tekstowe.</span><span class="sxs-lookup"><span data-stu-id="01015-177">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="01015-178">Niepoprawnie wprowadź hasło.</span><span class="sxs-lookup"><span data-stu-id="01015-178">Incorrectly enter your password.</span></span> <span data-ttu-id="01015-179">Po następnym wznowione klawiatury będzie działać zgodnie z oczekiwaniami.</span><span class="sxs-lookup"><span data-stu-id="01015-179">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="01015-180">Uwierzytelnianie internetowe, zamknij klawiaturę i wybierz **pozycję Zaloguj się z innego urządzenia.**</span><span class="sxs-lookup"><span data-stu-id="01015-180">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span>
-   <span data-ttu-id="01015-181">Jeśli wprowadzasz tylko liczby, użytkownik może nacisnąć i przytrzymać niektóre klawisze, aby otworzyć rozwinięte menu.</span><span class="sxs-lookup"><span data-stu-id="01015-181">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="01015-182">Za pomocą klawiatury USB.</span><span class="sxs-lookup"><span data-stu-id="01015-182">Using a USB keyboard.</span></span>

<span data-ttu-id="01015-183">Nie ma to wpływu na:</span><span class="sxs-lookup"><span data-stu-id="01015-183">This does not affect:</span></span>
- <span data-ttu-id="01015-184">Użytkownicy, którzy wybiorą opcję korzystania z konta osobistego.</span><span class="sxs-lookup"><span data-stu-id="01015-184">Users who choose to use a personal account.</span></span>

[<span data-ttu-id="01015-185">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="01015-185">Back to list</span></span>](#list)

## <a name="downloading-locked-files-doesnt-error"></a><span data-ttu-id="01015-186">Pobieranie zablokowanych plików nie kończy się błędem</span><span class="sxs-lookup"><span data-stu-id="01015-186">Downloading locked files doesn't error</span></span>

> [!NOTE]
> <span data-ttu-id="01015-187">Jest to znany **problem, który został** rozwiązany w kompilacji Windows Insider w wersji 20348.1403.</span><span class="sxs-lookup"><span data-stu-id="01015-187">This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span>

<span data-ttu-id="01015-188">W poprzednich kompilacjach Windows Holographic próba pobrania zablokowanego pliku byłaby stroną błędu HTTP.</span><span class="sxs-lookup"><span data-stu-id="01015-188">In previous builds of Windows Holographic, when attempting to download a locked file, the result would be an HTTP error page.</span></span> <span data-ttu-id="01015-189">Na platformie Windows Holographic aktualizacja w wersji 21H1, próba pobrania zablokowanego pliku powoduje, że nic nie dzieje się widoczne — plik nie jest pobierany i nie występuje błąd.</span><span class="sxs-lookup"><span data-stu-id="01015-189">In the Windows Holographic, version 21H1 update, trying to download a locked file results in nothing visible happening—the file doesn’t download and there’s no error.</span></span>

[<span data-ttu-id="01015-190">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="01015-190">Back to list</span></span>](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a><span data-ttu-id="01015-191">Portal urządzeń przekazywania/pobierania plików</span><span class="sxs-lookup"><span data-stu-id="01015-191">Device Portal file upload/download times out</span></span>
> [!NOTE]
> <span data-ttu-id="01015-192">Jest to znany **problem, który został** rozwiązany w kompilacji Windows Insider w wersji 20348.1403.</span><span class="sxs-lookup"><span data-stu-id="01015-192">This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span> <span data-ttu-id="01015-193">Jeśli wcześniej wyłączono połączenie SSL w ramach obejścia, zdecydowanie zalecamy jego ponowne włączenie.</span><span class="sxs-lookup"><span data-stu-id="01015-193">If you previously disabled SSL Connection as part of the workaround, we highly recommend you re-enable it.</span></span>


<span data-ttu-id="01015-194">Niektórzy klienci odkryli, że podczas próby przekazania lub pobrania plików operacja może się zawieszać, a następnie kończyć się lub nigdy nie kończyć.</span><span class="sxs-lookup"><span data-stu-id="01015-194">Some customers have found, when attempting to upload or download files, the operation might appear to hang and then time out or never complete.</span></span> <span data-ttu-id="01015-195">Jest to oddzielone[](#downloading-locked-files-doesnt-error) od znanego problemu "plik zablokowany" — dotyczy Windows Holographic w wersjach 2004, 20H2 i 21H1 w kompilacjach na rynku.</span><span class="sxs-lookup"><span data-stu-id="01015-195">This is separate from the '[file locked' known issue](#downloading-locked-files-doesnt-error) -- this affects Windows Holographic, versions 2004, 20H2 and 21H1 in-market builds.</span></span> <span data-ttu-id="01015-196">Przyczyną problemu była usterka w obsłudze niektórych żądań Portal urządzeń, która jest najczęściej trafiona w przypadku używania protokołu https, co jest ustawieniem domyślnym.</span><span class="sxs-lookup"><span data-stu-id="01015-196">The problem has been root caused to a bug in Device Portal's handling of certain requests, and is most consistently hit when using https, which is the default.</span></span> 

### <a name="workaround"></a><span data-ttu-id="01015-197">Obejście</span><span class="sxs-lookup"><span data-stu-id="01015-197">Workaround</span></span>

<span data-ttu-id="01015-198">To obejście, które ma zastosowanie w równym Wi-Fi i UsbNcm, polega na wyłączeniu opcji "wymagane" w obszarze "Połączenie SSL".</span><span class="sxs-lookup"><span data-stu-id="01015-198">This workaround, which applies equally to Wi-Fi and UsbNcm, is to disable the "required" option under "SSL Connection".</span></span> <span data-ttu-id="01015-199">W tym celu przejdź do Portal urządzeń **System** i wybierz **stronę Preferencje.**</span><span class="sxs-lookup"><span data-stu-id="01015-199">To do so, navigate to Device Portal, **System**, and select the **Preferences** page.</span></span> <span data-ttu-id="01015-200">W sekcji **Zabezpieczenia urządzenia znajdź** opcję Połączenie **SSL** i usuń zaznaczenie pola wyboru, aby wyłączyć **opcję Wymagane.**</span><span class="sxs-lookup"><span data-stu-id="01015-200">In the **Device Security** section, locate **SSL Connection**, and uncheck to disable **Required**.</span></span>

<span data-ttu-id="01015-201">Użytkownik powinien wtedy przejść do strony http://, https:// (adres IP), a funkcje, takie jak przekazywanie i pobieranie plików, będą działać.</span><span class="sxs-lookup"><span data-stu-id="01015-201">The user should then go to http://, not https:// (IP address) and features like file upload and download will work.</span></span>

[<span data-ttu-id="01015-202">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="01015-202">Back to list</span></span>](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a><span data-ttu-id="01015-203">Niebieski ekran po wywrzeniu z wersji zapoznawczej niejawnego programu testów na urządzeniu z flashem kompilacji niejawnego testera</span><span class="sxs-lookup"><span data-stu-id="01015-203">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>

<span data-ttu-id="01015-204">Jest to problem, który ma wpływ na użytkowników, którzy byli w kompilacji niejawnego testera w wersji zapoznawczej, przekrzywilili swój program HoloLens 2 przy użyciu nowej kompilacji niejawnego programu w wersji zapoznawczej, a następnie nie zakodują się w programie insider.</span><span class="sxs-lookup"><span data-stu-id="01015-204">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> <span data-ttu-id="01015-205">Jest to znany **problem.**</span><span class="sxs-lookup"><span data-stu-id="01015-205">This is a **known issue**.</span></span>

<span data-ttu-id="01015-206">Nie ma to wpływu na:</span><span class="sxs-lookup"><span data-stu-id="01015-206">This does not affect:</span></span>
- <span data-ttu-id="01015-207">Użytkownicy, którzy nie są zarejestrowani w programie Windows Insider</span><span class="sxs-lookup"><span data-stu-id="01015-207">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="01015-208">Wewnętrznych:</span><span class="sxs-lookup"><span data-stu-id="01015-208">Insiders:</span></span>
    - <span data-ttu-id="01015-209">Jeśli urządzenie zostało zarejestrowane od kompilacji niejawnych testerów w wersji 18362.x</span><span class="sxs-lookup"><span data-stu-id="01015-209">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="01015-210">Jeśli flashował kompilację 19041.x podpisaną przez niejawnego testera I pozostał zarejestrowany w programie insider</span><span class="sxs-lookup"><span data-stu-id="01015-210">If they flashed an Insider signed 19041.x build AND stay enrolled in the Insider program</span></span>

<span data-ttu-id="01015-211">Pomiń:</span><span class="sxs-lookup"><span data-stu-id="01015-211">Work-around:</span></span> 
- <span data-ttu-id="01015-212">Unikanie problemu</span><span class="sxs-lookup"><span data-stu-id="01015-212">Avoid the issue</span></span> 
    - <span data-ttu-id="01015-213">Flashuj kompilację, która nie jest niejawnym testerem.</span><span class="sxs-lookup"><span data-stu-id="01015-213">Flash a non-insider build.</span></span> <span data-ttu-id="01015-214">Jedna z regularnych comiesięcznych aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="01015-214">One of the regular monthly updates.</span></span>
    - <span data-ttu-id="01015-215">Stay on Insider Preview</span><span class="sxs-lookup"><span data-stu-id="01015-215">Stay on Insider Preview</span></span>
- <span data-ttu-id="01015-216">Reflash urządzenia</span><span class="sxs-lookup"><span data-stu-id="01015-216">Reflash the device</span></span>

    1. <span data-ttu-id="01015-217">Ręcznie HoloLens [2 w](hololens-recovery.md) tryb flashowania przez całkowite zasilanie bez połączenia.</span><span class="sxs-lookup"><span data-stu-id="01015-217">Put the [HoloLens 2 into flashing mode](hololens-recovery.md) manually by fully powering down while not connect.</span></span> <span data-ttu-id="01015-218">Następnie przy przytrzymaniu przycisku Regulacji głośności naciśnij przycisk Zasilania.</span><span class="sxs-lookup"><span data-stu-id="01015-218">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="01015-219">Połączenie na komputer i otwórz program Advanced Recovery Companion.</span><span class="sxs-lookup"><span data-stu-id="01015-219">Connect to the PC and open Advanced Recovery Companion.</span></span>
    
    1. <span data-ttu-id="01015-220">Flashuj HoloLens 2 do domyślnej kompilacji.</span><span class="sxs-lookup"><span data-stu-id="01015-220">Flash the HoloLens 2 to the default build.</span></span>

[<span data-ttu-id="01015-221">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="01015-221">Back to list</span></span>](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a><span data-ttu-id="01015-222">OneDrive nie przekaże automatycznie obrazów</span><span class="sxs-lookup"><span data-stu-id="01015-222">OneDrive doesn't automatically upload pictures</span></span>

<span data-ttu-id="01015-223">Aplikacja OneDrive dla aplikacji HoloLens nie obsługuje automatycznego przekazywania z aparatu dla kont służbowych.</span><span class="sxs-lookup"><span data-stu-id="01015-223">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span> <span data-ttu-id="01015-224">Jest to znany **problem.**</span><span class="sxs-lookup"><span data-stu-id="01015-224">This is a **known issue**.</span></span>

<span data-ttu-id="01015-225">Obejścia:</span><span class="sxs-lookup"><span data-stu-id="01015-225">Workarounds:</span></span>

- <span data-ttu-id="01015-226">Jeśli jest to możliwe dla Twojej firmy, automatyczne przekazywanie z aparatu jest obsługiwane na kontach Microsoft konsumentów.</span><span class="sxs-lookup"><span data-stu-id="01015-226">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="01015-227">Możesz zalogować się do konta konto Microsoft konta służbowego (aplikacja OneDrive obsługuje logowanie podwójne).</span><span class="sxs-lookup"><span data-stu-id="01015-227">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="01015-228">Z poziomu konto Microsoft w OneDrive można włączyć automatyczne przekazywanie z kamery w tle.</span><span class="sxs-lookup"><span data-stu-id="01015-228">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="01015-229">Jeśli nie możesz bezpiecznie użyć konta konto Microsoft do automatycznego przekazywania zdjęć, możesz ręcznie przekazać zdjęcia na konto służbowe z aplikacji OneDrive aplikacji.</span><span class="sxs-lookup"><span data-stu-id="01015-229">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="01015-230">W tym celu upewnij się, że zalogowano się do konta służbowego w OneDrive aplikacji.</span><span class="sxs-lookup"><span data-stu-id="01015-230">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="01015-231">Wybierz przycisk **+** i wybierz pozycję **Upload**.</span><span class="sxs-lookup"><span data-stu-id="01015-231">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="01015-232">Znajdź zdjęcia lub filmy wideo, które chcesz przekazać, przechodząc do > **Camera Roll**.</span><span class="sxs-lookup"><span data-stu-id="01015-232">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="01015-233">Wybierz zdjęcia lub wideo, które chcesz przekazać, a następnie wybierz **przycisk** Otwórz.</span><span class="sxs-lookup"><span data-stu-id="01015-233">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

[<span data-ttu-id="01015-234">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="01015-234">Back to list</span></span>](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a><span data-ttu-id="01015-235">HoloLens nie odpowiada lub nie można uruchomić</span><span class="sxs-lookup"><span data-stu-id="01015-235">HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="01015-236">Jeśli twój HoloLens się nie uruchamia:</span><span class="sxs-lookup"><span data-stu-id="01015-236">If your HoloLens won't start:</span></span>

- <span data-ttu-id="01015-237">Jeśli diody LED obok przycisku zasilania nie zaczną się oświetlać lub tylko jedna dioda LED miga na krótko, może być konieczne [HoloLens.](hololens2-charging.md#charging-the-device)</span><span class="sxs-lookup"><span data-stu-id="01015-237">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens2-charging.md#charging-the-device)</span></span>
- <span data-ttu-id="01015-238">Jeśli dioda LED zabłyśnie po naciśnięciu przycisku zasilania, ale nie widzisz niczego na ekranach, wykonaj twarde [zresetowanie urządzenia.](hololens-recovery.md#hard-reset-procedure)</span><span class="sxs-lookup"><span data-stu-id="01015-238">If the LEDs light up when you press the power button but you can't see anything on the displays, [do a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="01015-239">Jeśli twój HoloLens jest zamrożony lub nie odpowiada:</span><span class="sxs-lookup"><span data-stu-id="01015-239">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="01015-240">Wyłącz urządzenie HoloLens naciskając przycisk zasilania, aż wszystkie pięć diod LED wyłączy się lub przez 15 sekund, jeśli diody LED nie będą odpowiadać.</span><span class="sxs-lookup"><span data-stu-id="01015-240">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="01015-241">Aby uruchomić HoloLens, ponownie naciśnij przycisk zasilania.</span><span class="sxs-lookup"><span data-stu-id="01015-241">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="01015-242">Jeśli te kroki nie działają, możesz spróbować odzyskać urządzenie z systemem [HoloLens 2](hololens-recovery.md) lub HoloLens [(1. generacji).](hololens1-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="01015-242">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

[<span data-ttu-id="01015-243">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="01015-243">Back to list</span></span>](#list)

## <a name="low-disk-space-error"></a><span data-ttu-id="01015-244">Błąd "Mała ilość miejsca na dysku"</span><span class="sxs-lookup"><span data-stu-id="01015-244">"Low Disk Space" error</span></span>

<span data-ttu-id="01015-245">Konieczne będzie wolne miejsce do magazynowania, wykonując co najmniej jedną z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="01015-245">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="01015-246">Usuń niektóre nieużywane spacje.</span><span class="sxs-lookup"><span data-stu-id="01015-246">Delete some unused spaces.</span></span> <span data-ttu-id="01015-247">Przejdź do **Ustawienia**  >  **System**  >  **Spaces,** wybierz miejsce, które nie jest już **potrzebne,** a następnie wybierz pozycję Usuń .</span><span class="sxs-lookup"><span data-stu-id="01015-247">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="01015-248">Usuń niektóre z umieszczonych hologramów.</span><span class="sxs-lookup"><span data-stu-id="01015-248">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="01015-249">Usuń zdjęcia i filmy wideo z aplikacji Zdjęcia.</span><span class="sxs-lookup"><span data-stu-id="01015-249">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="01015-250">Odinstaluj niektóre aplikacje z HoloLens.</span><span class="sxs-lookup"><span data-stu-id="01015-250">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="01015-251">Na liście **Wszystkie aplikacje** naciśnij i przytrzymaj aplikację, którą chcesz odinstalować, a następnie wybierz pozycję **Odinstaluj.**</span><span class="sxs-lookup"><span data-stu-id="01015-251">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

[<span data-ttu-id="01015-252">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="01015-252">Back to list</span></span>](#list)

## <a name="calibration-fails"></a><span data-ttu-id="01015-253">Niepowodzenie awarii</span><span class="sxs-lookup"><span data-stu-id="01015-253">Calibration fails</span></span>

<span data-ttu-id="01015-254">Większość osób powinna pracować, ale istnieją przypadki, w których nie powiodło się to.</span><span class="sxs-lookup"><span data-stu-id="01015-254">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="01015-255">Niektóre potencjalne przyczyny niepowodzenia awarii to:</span><span class="sxs-lookup"><span data-stu-id="01015-255">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="01015-256">Rozpraszanie uwagi i niesąsiadowanie po docelowych celach</span><span class="sxs-lookup"><span data-stu-id="01015-256">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="01015-257">Zanieczyszczona lub porysowana osłona urządzenia lub urządzenie nie jest prawidłowo pozycjonowane</span><span class="sxs-lookup"><span data-stu-id="01015-257">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="01015-258">Zanieczyszczone lub porysowane okulary</span><span class="sxs-lookup"><span data-stu-id="01015-258">Dirty or scratched glasses</span></span>
- <span data-ttu-id="01015-259">Niektóre typy obiektywów i okularów kontaktowych (kolorowe obiektywy kontaktowe, niektóre torysowe obiektywy kontaktowe, okulary blokujące ir ir, niektóre okulary przeciwsłoneczne, okulary przeciwsłoneczne lub podobne)</span><span class="sxs-lookup"><span data-stu-id="01015-259">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="01015-260">Bardziej wymawiane nagie i niektóre rozszerzenia ukośników</span><span class="sxs-lookup"><span data-stu-id="01015-260">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="01015-261">Zarost lub grube ramki okularów, jeśli blokują one wzrok urządzenia</span><span class="sxs-lookup"><span data-stu-id="01015-261">Hair or thick eyeglass frames if they're blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="01015-262">Niektóre fizjologia, warunki oczu lub operacje oczu, takie jak wąskie oczy, długie ukośniki, amblyopia, nystagmus, niektóre przypadki lasik lub inne operacje oczu</span><span class="sxs-lookup"><span data-stu-id="01015-262">Certain eye physiology, eye conditions, or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="01015-263">Jeśli próba nie powiedzie się, spróbuj:</span><span class="sxs-lookup"><span data-stu-id="01015-263">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="01015-264">Czyszczenie urządzenia</span><span class="sxs-lookup"><span data-stu-id="01015-264">Cleaning your device visor</span></span>
- <span data-ttu-id="01015-265">Czyszczenie okularów</span><span class="sxs-lookup"><span data-stu-id="01015-265">Cleaning your glasses</span></span>
- <span data-ttu-id="01015-266">Wypychanie wizjora urządzenia tak blisko oczu, jak to możliwe</span><span class="sxs-lookup"><span data-stu-id="01015-266">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="01015-267">Przenoszenie obiektów w ośledla poza drogę (takich jak zarost)</span><span class="sxs-lookup"><span data-stu-id="01015-267">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="01015-268">Włączanie światła w pomieszczeniu lub wyprowadzanie się z bezpośredniego światła</span><span class="sxs-lookup"><span data-stu-id="01015-268">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="01015-269">Jeśli wszystkie wytyczne zostały przestrzegane, a nadal brakuje wskazówek, można wyłączyć monit o iniekcja w Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="01015-269">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="01015-270">Ponadto daj nam znać, składając opinię w [Centrum opinii](hololens-feedback.md).</span><span class="sxs-lookup"><span data-stu-id="01015-270">Also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="01015-271">Zobacz również powiązane informacje dotyczące [rozwiązywania problemów z kolorem obrazu lub jasność.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span><span class="sxs-lookup"><span data-stu-id="01015-271">Also see related information for [image color or brightness troubleshooting.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span></span>

<span data-ttu-id="01015-272">Ustawienie adresu IPD nie ma zastosowania HoloLens 2, ponieważ pozycje oka są obliczane przez system.</span><span class="sxs-lookup"><span data-stu-id="01015-272">Setting IPD is not applicable for HoloLens 2, since eye positions are computed by the system.</span></span> 

[<span data-ttu-id="01015-273">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="01015-273">Back to list</span></span>](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a><span data-ttu-id="01015-274">Nie można się zalogować, ponieważ HoloLens wcześniej została ustawiona dla kogoś innego</span><span class="sxs-lookup"><span data-stu-id="01015-274">Can't sign in because my HoloLens was previously set up for someone else</span></span>

<span data-ttu-id="01015-275">Urządzenie można [przesłonić w tryb **flashowania i**](hololens-recovery.md#clean-reflash-the-device) użyć narzędzia Advanced Recovery Companion w celu odzyskania urządzenia.</span><span class="sxs-lookup"><span data-stu-id="01015-275">You can [put the device into **Flashing Mode** and use Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) to recover the device.</span></span>

[<span data-ttu-id="01015-276">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="01015-276">Back to list</span></span>](#list)


## <a name="unity-isnt-working"></a><span data-ttu-id="01015-277">Unity nie działa</span><span class="sxs-lookup"><span data-stu-id="01015-277">Unity isn't working</span></span>

- <span data-ttu-id="01015-278">Zobacz [Instalowanie narzędzi dla](/windows/mixed-reality/install-the-tools) najbardziej aktualnej wersji aparatu Unity zalecanej do HoloLens projektowania.</span><span class="sxs-lookup"><span data-stu-id="01015-278">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="01015-279">Znane problemy z platformą Unity HoloLens Technical Preview są udokumentowane na [forach HoloLens Unity.](https://forum.unity3d.com/threads/known-issues.394627/)</span><span class="sxs-lookup"><span data-stu-id="01015-279">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

[<span data-ttu-id="01015-280">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="01015-280">Back to list</span></span>](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a><span data-ttu-id="01015-281">Windows Portal urządzeń nie działa prawidłowo</span><span class="sxs-lookup"><span data-stu-id="01015-281">Windows Device Portal isn't working correctly</span></span>

- <span data-ttu-id="01015-282">Funkcja podglądu na żywo w Mixed Reality przechwytywania danych może mieć kilka sekund opóźnienia.</span><span class="sxs-lookup"><span data-stu-id="01015-282">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="01015-283">Na stronie Wirtualne dane wejściowe kontrolki Gest i Przewiń w sekcji Gesty wirtualne nie działają.</span><span class="sxs-lookup"><span data-stu-id="01015-283">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="01015-284">Ich użycie nie będzie mieć żadnego efektu.</span><span class="sxs-lookup"><span data-stu-id="01015-284">Using them will have no effect.</span></span> <span data-ttu-id="01015-285">Klawiatura wirtualna na wirtualnej stronie wejściowej działa poprawnie.</span><span class="sxs-lookup"><span data-stu-id="01015-285">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="01015-286">Po włączeniu trybu dewelopera Ustawienia może mieć kilka sekund, zanim Portal urządzeń przełącznik zostanie włączony.</span><span class="sxs-lookup"><span data-stu-id="01015-286">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

[<span data-ttu-id="01015-287">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="01015-287">Back to list</span></span>](#list)

## <a name="the-hololens-emulator-isnt-working"></a><span data-ttu-id="01015-288">HoloLens Emulator nie działa</span><span class="sxs-lookup"><span data-stu-id="01015-288">The HoloLens Emulator isn't working</span></span>

<span data-ttu-id="01015-289">Informacje o emulatorze HoloLens znajdują się w naszej dokumentacji dla deweloperów.</span><span class="sxs-lookup"><span data-stu-id="01015-289">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="01015-290">Przeczytaj więcej na [temat rozwiązywania problemów z HoloLens emulatorem.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="01015-290">Read more about [troubleshooting the HoloLens emulator](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting).</span></span>


- <span data-ttu-id="01015-291">Nie wszystkie aplikacje w Microsoft Store są zgodne z emulatorem.</span><span class="sxs-lookup"><span data-stu-id="01015-291">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="01015-292">Na przykład w emulatorze nie można odtwarzać fragmentów i Young Conker.</span><span class="sxs-lookup"><span data-stu-id="01015-292">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="01015-293">Nie można używać kamery internetowej komputera w Emulator.</span><span class="sxs-lookup"><span data-stu-id="01015-293">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="01015-294">Funkcja podglądu na żywo Windows Portal urządzeń nie działa z emulatorem.</span><span class="sxs-lookup"><span data-stu-id="01015-294">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="01015-295">Nadal możesz przechwytywać Mixed Reality wideo i obrazy.</span><span class="sxs-lookup"><span data-stu-id="01015-295">You can still capture Mixed Reality videos and images.</span></span>

[<span data-ttu-id="01015-296">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="01015-296">Back to list</span></span>](#list)

## <a name="voice-commands-arent-working"></a><span data-ttu-id="01015-297">Polecenia głosowe nie działają</span><span class="sxs-lookup"><span data-stu-id="01015-297">Voice commands aren't working</span></span>

<span data-ttu-id="01015-298">Jeśli Cortana nie odpowiada na polecenia głosowe, upewnij się, że Cortana włączona.</span><span class="sxs-lookup"><span data-stu-id="01015-298">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="01015-299">Na liście Wszystkie aplikacje wybierz **pozycję** Cortana  >  **Menu**  >  **Ustawienia,** aby wprowadzić  >   zmiany.</span><span class="sxs-lookup"><span data-stu-id="01015-299">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="01015-300">Aby dowiedzieć się więcej na temat tego, co możesz powiedzieć, zobacz Używanie głosu [z](hololens-cortana.md)HoloLens.</span><span class="sxs-lookup"><span data-stu-id="01015-300">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

<span data-ttu-id="01015-301">Na HoloLens (1. generacji) wbudowanej funkcji rozpoznawania mowy nie można skonfigurować.</span><span class="sxs-lookup"><span data-stu-id="01015-301">On HoloLens (1st gen), built-in speech recognition is not configurable.</span></span> <span data-ttu-id="01015-302">Jest ona zawsze włączona.</span><span class="sxs-lookup"><span data-stu-id="01015-302">It is always turned on.</span></span> <span data-ttu-id="01015-303">Na HoloLens 2 możesz wybrać, czy podczas konfigurowania urządzenia włączyć zarówno rozpoznawanie mowy, jak i Cortana mowę.</span><span class="sxs-lookup"><span data-stu-id="01015-303">On HoloLens 2, you can choose whether to turn on both speech recognition and Cortana during device setup.</span></span>

<span data-ttu-id="01015-304">Jeśli urządzenie HoloLens 2 nie odpowiada na Twój głos, upewnij się, że funkcja rozpoznawania mowy jest włączona.</span><span class="sxs-lookup"><span data-stu-id="01015-304">If your HoloLens 2 is not responding to your voice, make sure Speech recognition is turned on.</span></span> <span data-ttu-id="01015-305">Przejdź do **tematu Start**  >  **Ustawienia**  >  **Privacy**  >  **Speech** i włącz **rozpoznawanie mowy.**</span><span class="sxs-lookup"><span data-stu-id="01015-305">Go to **Start** > **Settings** > **Privacy** > **Speech** and turn on **Speech recognition**.</span></span>

[<span data-ttu-id="01015-306">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="01015-306">Back to list</span></span>](#list)

## <a name="hand-input-isnt-working"></a><span data-ttu-id="01015-307">Ręczne wprowadzanie danych nie działa</span><span class="sxs-lookup"><span data-stu-id="01015-307">Hand input isn't working</span></span>

<span data-ttu-id="01015-308">Aby upewnić się HoloLens, że twoje ręce będą widać, musisz zachować je w ramce gestu.</span><span class="sxs-lookup"><span data-stu-id="01015-308">To ensure that HoloLens can see your hands, you need to keep them in the gesture frame.</span></span>  <span data-ttu-id="01015-309">Strona Mixed Reality home udostępnia opinię, która informuje o tym, kiedy są śledzone twoje ręce.</span><span class="sxs-lookup"><span data-stu-id="01015-309">The Mixed Reality Home provides feedback that lets you know when your hands are tracked.</span></span>  <span data-ttu-id="01015-310">Opinie są inne w różnych wersjach HoloLens:</span><span class="sxs-lookup"><span data-stu-id="01015-310">The feedback is different on different versions of HoloLens:</span></span>
- <span data-ttu-id="01015-311">Na HoloLens (1. generacja) kursor spojrzenia zmienia się z kropki na pierścień</span><span class="sxs-lookup"><span data-stu-id="01015-311">On HoloLens (1st gen), the gaze cursor changes from a dot to a ring</span></span>
- <span data-ttu-id="01015-312">Na HoloLens 2, gdy ręka jest blisko planszy, pojawia się kursor w zasięgu ręki, a promienia ręki, gdy plansze są dalej</span><span class="sxs-lookup"><span data-stu-id="01015-312">On HoloLens 2, a fingertip cursor appears when your hand is close to a slate, and a hand ray appears when slates are further away</span></span>

<span data-ttu-id="01015-313">Wiele aplikacji immersywnych ma wzorce wejściowe podobne do Mixed Reality Home.</span><span class="sxs-lookup"><span data-stu-id="01015-313">Many immersive apps follow input patterns that are similar to Mixed Reality Home.</span></span>  <span data-ttu-id="01015-314">Dowiedz się więcej o używaniu danych wejściowych ręcznie [HoloLens (1. generacji)](hololens1-basic-usage.md#use-hololens-with-your-hands) [i HoloLens 2.](hololens2-basic-usage.md#the-hand-tracking-frame)</span><span class="sxs-lookup"><span data-stu-id="01015-314">Learn more about using hand input on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) and [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="01015-315">Należy pamiętać, że niektóre typy iniekcj nie działają ze śledzeniem rąk.</span><span class="sxs-lookup"><span data-stu-id="01015-315">If you are wearing gloves, note that some types of gloves do not work with hand tracking.</span></span>  <span data-ttu-id="01015-316">Częstym przykładem są czarne gumy, które zwykle absorbują światło podczerwone i nie są odbierane przez kamerę z głębokością.</span><span class="sxs-lookup"><span data-stu-id="01015-316">A common example is black rubber gloves, which tend to absorb infrared light and are not picked up by the depth camera.</span></span>  <span data-ttu-id="01015-317">Jeśli Twoja praca wiąże się z gumką, zalecamy wypróbowanie jaśniejszego koloru, takiego jak niebieski lub szary.</span><span class="sxs-lookup"><span data-stu-id="01015-317">If your work involves rubber gloves, we recommend trying a lighter color such as blue or gray.</span></span>  <span data-ttu-id="01015-318">Innym przykładem są duże baggy nagie, które zwykle przesłaniają kształt ręki.</span><span class="sxs-lookup"><span data-stu-id="01015-318">Another example is large baggy gloves, which tend to obscure the shape of your hand.</span></span> <span data-ttu-id="01015-319">Zalecamy używanie tak dopasowanych do formularzy, jak to tylko możliwe, aby uzyskać najlepsze wyniki.</span><span class="sxs-lookup"><span data-stu-id="01015-319">We recommend using gloves that are as form-fitting as possible for best results.</span></span>

<span data-ttu-id="01015-320">Jeśli twoje urządzenie ma odciski palców lub smekty, użyj mikrofibry czyszczącej, która została HoloLens, aby wyczyścić ją.</span><span class="sxs-lookup"><span data-stu-id="01015-320">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

[<span data-ttu-id="01015-321">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="01015-321">Back to list</span></span>](#list)

## <a name="cant-connect-to-wi-fi"></a><span data-ttu-id="01015-322">Nie można nawiązać połączenia z Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="01015-322">Can't connect to Wi-Fi</span></span>

<span data-ttu-id="01015-323">Oto kilka rzeczy, które należy wypróbować, jeśli nie można połączyć komputera HoloLens z Wi-Fi siecią:</span><span class="sxs-lookup"><span data-stu-id="01015-323">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

- <span data-ttu-id="01015-324">Upewnij się, Wi-Fi jest włączona.</span><span class="sxs-lookup"><span data-stu-id="01015-324">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="01015-325">Aby to sprawdzić, użyj gestu Start, a następnie wybierz **Ustawienia**  >  **Sieci &amp;**  >  **Wi-Fi.**</span><span class="sxs-lookup"><span data-stu-id="01015-325">To check, use the Start gesture, then select **Settings** > **Network &amp; Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="01015-326">Jeśli Wi-Fi jest wł., spróbuj wyłączyć ją, a następnie ponownie wł.</span><span class="sxs-lookup"><span data-stu-id="01015-326">If Wi-Fi is on, try turning it off and then on again.</span></span>
- <span data-ttu-id="01015-327">Umieść komputer bliżej routera lub punktu dostępu.</span><span class="sxs-lookup"><span data-stu-id="01015-327">Move closer to the router or access point.</span></span>
- <span data-ttu-id="01015-328">Uruchom ponownie Wi-Fi, a następnie [uruchom ponownie HoloLens](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="01015-328">Restart your Wi-Fi router, then [restart HoloLens](hololens-recovery.md).</span></span> <span data-ttu-id="01015-329">Spróbuj ponownie nałączyć połączenie.</span><span class="sxs-lookup"><span data-stu-id="01015-329">Try connecting again.</span></span>
- <span data-ttu-id="01015-330">Jeśli żadna z tych czynności nie działa, upewnij się, że router korzysta z najnowszego oprogramowania układowego.</span><span class="sxs-lookup"><span data-stu-id="01015-330">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="01015-331">Te informacje można znaleźć w witrynie internetowej producenta.</span><span class="sxs-lookup"><span data-stu-id="01015-331">You can find this information on the manufacturer website.</span></span>

[<span data-ttu-id="01015-332">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="01015-332">Back to list</span></span>](#list)

## <a name="bluetooth-devices-arent-pairing"></a><span data-ttu-id="01015-333">Bluetooth urządzenia nie są parowane</span><span class="sxs-lookup"><span data-stu-id="01015-333">Bluetooth devices aren't pairing</span></span>

<span data-ttu-id="01015-334">Jeśli masz problemy z [parowaniem urządzenia Bluetooth,](hololens-connect-devices.md)spróbuj wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="01015-334">If you're having problems [pairing a Bluetooth device](hololens-connect-devices.md), try the following:</span></span>

- <span data-ttu-id="01015-335">Przejdź do **Ustawienia**  >  **Urządzenia** i upewnij się, Bluetooth jest włączona.</span><span class="sxs-lookup"><span data-stu-id="01015-335">Go to **Settings** > **Devices**, and make sure that Bluetooth is turned on.</span></span> <span data-ttu-id="01015-336">Jeśli tak, wyłącz ją i włącz ponownie.</span><span class="sxs-lookup"><span data-stu-id="01015-336">If it is, turn it off and on again.</span></span>
- <span data-ttu-id="01015-337">Upewnij się, że urządzenie Bluetooth jest w pełni obciążone lub ma świeże baterii.</span><span class="sxs-lookup"><span data-stu-id="01015-337">Make sure that your Bluetooth device is fully charged or has fresh batteries.</span></span>
- <span data-ttu-id="01015-338">Jeśli nadal nie możesz nawiązać połączenia, [uruchom ponownie HoloLens](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="01015-338">If you still can't connect, [restart the HoloLens](hololens-recovery.md).</span></span>

[<span data-ttu-id="01015-339">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="01015-339">Back to list</span></span>](#list)

## <a name="usb-c-microphone-isnt-working"></a><span data-ttu-id="01015-340">Mikrofon USB-C nie działa</span><span class="sxs-lookup"><span data-stu-id="01015-340">USB-C Microphone isn't working</span></span>
<span data-ttu-id="01015-341">Należy pamiętać, że niektóre mikrofony USB-C nieprawidłowo zgłaszają się jako mikrofon i *prelegent.*</span><span class="sxs-lookup"><span data-stu-id="01015-341">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="01015-342">Jest to problem z mikrofonem, a nie z HoloLens.</span><span class="sxs-lookup"><span data-stu-id="01015-342">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="01015-343">Podczas podłączania jednego z tych mikrofonów do HoloLens, dźwięk może zostać utracony.</span><span class="sxs-lookup"><span data-stu-id="01015-343">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="01015-344">Na szczęście istnieje prosta poprawka.</span><span class="sxs-lookup"><span data-stu-id="01015-344">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="01015-345">W **Ustawienia**  ->  **System**  ->  **Sound** jawnie ustaw wbudowane osoby mówiące **(sterownik audio** funkcji analogicznej) jako domyślne urządzenie .</span><span class="sxs-lookup"><span data-stu-id="01015-345">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="01015-346">HoloLens zapamiętaj to ustawienie, nawet jeśli mikrofon zostanie później usunięty i ponownie podłączony.</span><span class="sxs-lookup"><span data-stu-id="01015-346">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![Rozwiązywanie problemów z mikrofonami USB-C](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a><span data-ttu-id="01015-348">Urządzenia wymienione jako dostępne Ustawienia nie działają</span><span class="sxs-lookup"><span data-stu-id="01015-348">Devices listed as available in Settings don't work</span></span>

<span data-ttu-id="01015-349">HoloLens (1. generacja) nie obsługuje Bluetooth audio.</span><span class="sxs-lookup"><span data-stu-id="01015-349">HoloLens (1st gen) doesn't support Bluetooth audio profiles.</span></span> <span data-ttu-id="01015-350">Bluetooth audio, takie jak głośników i zestawy nagłowne, mogą być wyświetlane jako dostępne HoloLens ustawieniach, ale nie są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="01015-350">Bluetooth audio devices, such as speakers and headsets, may appear as available in HoloLens settings, but they aren't supported.</span></span>

<span data-ttu-id="01015-351">HoloLens 2 obsługuje Bluetooth audio A2DP do odtwarzania stereo.</span><span class="sxs-lookup"><span data-stu-id="01015-351">HoloLens 2 supports the Bluetooth A2DP audio profile for stereo playback.</span></span> <span data-ttu-id="01015-352">Profil Bluetooth Hands Free, który umożliwia przechwytywanie mikrofonu z urządzenia peryferyjnego Bluetooth HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="01015-352">The Bluetooth Hands Free profile which enables microphone capture from a Bluetooth peripheral is not supported on HoloLens 2.</span></span>

<span data-ttu-id="01015-353">Jeśli masz problemy z używaniem urządzenia Bluetooth, upewnij się, że jest to obsługiwane urządzenie.</span><span class="sxs-lookup"><span data-stu-id="01015-353">If you're having trouble using a Bluetooth device, make sure that it's a supported device.</span></span> <span data-ttu-id="01015-354">Obsługiwane urządzenia są następujące:</span><span class="sxs-lookup"><span data-stu-id="01015-354">Supported devices include the following:</span></span>

- <span data-ttu-id="01015-355">Język angielski QWERTY Bluetooth klawiatury (można ich używać wszędzie tam, gdzie używasz klawiatury holograficznej).</span><span class="sxs-lookup"><span data-stu-id="01015-355">English-language QWERTY Bluetooth keyboards (you can use these anywhere that you use the holographic keyboard).</span></span>
- <span data-ttu-id="01015-356">Bluetooth myszy.</span><span class="sxs-lookup"><span data-stu-id="01015-356">Bluetooth mice.</span></span>
- <span data-ttu-id="01015-357">Kliknij [HoloLens kliknij przycisk](hololens1-clicker.md).</span><span class="sxs-lookup"><span data-stu-id="01015-357">The [HoloLens clicker](hololens1-clicker.md).</span></span>

<span data-ttu-id="01015-358">Inne urządzenia HID Bluetooth MOŻNA sparować z urządzeniami HID HoloLens.</span><span class="sxs-lookup"><span data-stu-id="01015-358">You can pair other Bluetooth HID and GATT devices together with your HoloLens.</span></span> <span data-ttu-id="01015-359">Może być jednak trzeba zainstalować odpowiednie aplikacje towarzyszące z Microsoft Store, aby w rzeczywistości korzystać z urządzeń.</span><span class="sxs-lookup"><span data-stu-id="01015-359">However, you may have to install corresponding companion apps from Microsoft Store to actually use the devices.</span></span>

[<span data-ttu-id="01015-360">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="01015-360">Back to list</span></span>](#list)
