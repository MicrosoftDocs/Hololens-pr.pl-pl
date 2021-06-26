---
title: Rozwiązywanie problemów z implementacją urządzenia HoloLens 2 i urządzeniem zarządzanym
description: Rozwiązywanie problemów z urządzeniami HoloLens 2 w środowisku przedsiębiorstwa
author: JoyJaz
ms.author: v-jjaswinski
ms.date: 6/22/2021
ms.topic: article
keywords: rozwiązywanie problemów
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 911e5b9494eae00ace8007ee6a29b30e6aaf98dd
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961640"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a><span data-ttu-id="177af-104">Rozwiązywanie problemów z implementacją i urządzeniami zarządzanymi</span><span class="sxs-lookup"><span data-stu-id="177af-104">Troubleshooting implementation and managed devices</span></span> 

<span data-ttu-id="177af-105">W tym artykule opisano sposób rozwiązywania kilku problemów lub odpowiadania na pytania dotyczące implementacji urządzenia HoloLens 2 i zarządzania nim.</span><span class="sxs-lookup"><span data-stu-id="177af-105">This article describes how to resolve several issues or answer questions regarding implementation and management of HoloLens 2.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="177af-106">Przed rozpoczęciem procedury rozwiązywania problemów upewnij się, że urządzenie jest obciążane od **20 do 40%** pojemności baterii, jeśli jest to możliwe.</span><span class="sxs-lookup"><span data-stu-id="177af-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="177af-107">Wskaźniki [naładowania baterii znajdujące](hololens2-setup.md#lights-that-indicate-the-battery-level) się pod przyciskiem zasilania to szybki sposób na sprawdzenie pojemności baterii bez logowania się do urządzenia.</span><span class="sxs-lookup"><span data-stu-id="177af-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>


<a id="list"></a>
- [<span data-ttu-id="177af-108">Rozwiązywanie problemów z protokołu EAP</span><span class="sxs-lookup"><span data-stu-id="177af-108">EAP Troubleshooting</span></span>](#eap-troubleshooting)
- [<span data-ttu-id="177af-109">Rozwiązywanie problemów z siecią Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="177af-109">Wi-Fi Troubleshooting</span></span>](#wi-fi-troubleshooting)
- [<span data-ttu-id="177af-110">Rozwiązywanie problemów z siecią</span><span class="sxs-lookup"><span data-stu-id="177af-110">Network Troubleshooting</span></span>](#network-troubleshooting)
- [<span data-ttu-id="177af-111">Nie można zalogować się do wcześniej skonfigurować urządzenia HoloLens</span><span class="sxs-lookup"><span data-stu-id="177af-111">Can't sign in to a previously setup HoloLens device</span></span>](#cant-sign-in-to-a-previously-setup-hololens-device)
- [<span data-ttu-id="177af-112">Nie można zalogować się po zaktualizowaniu do systemu Windows Holographic 21H1</span><span class="sxs-lookup"><span data-stu-id="177af-112">Can't login after updating to Windows Holographic 21H1</span></span>](#cant-login-after-updating-to-windows-holographic-21h1)
- [<span data-ttu-id="177af-113">Rozwiązywanie problemów z rozwiązaniem Autopilot</span><span class="sxs-lookup"><span data-stu-id="177af-113">Autopilot Troubleshooting</span></span>](#autopilot-troubleshooting)
- [<span data-ttu-id="177af-114">Zarządzane urządzenia HoloLens : często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="177af-114">Managed HoloLens Devices FAQs</span></span>](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a><span data-ttu-id="177af-115">Rozwiązywanie problemów z protokołu EAP</span><span class="sxs-lookup"><span data-stu-id="177af-115">EAP Troubleshooting</span></span>
1. <span data-ttu-id="177af-116">Sprawdź, Wi-Fi profil ma odpowiednie ustawienia:</span><span class="sxs-lookup"><span data-stu-id="177af-116">Double check Wi-Fi profile has right settings:</span></span>
    - <span data-ttu-id="177af-117">Typ protokołu EAP jest poprawnie skonfigurowany, typowe typy protokołu EAP: EAP-TLS (13), EAP-TTLS (21) i PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="177af-117">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
    - <span data-ttu-id="177af-118">Wi-Fi nazwa SSID jest właściwa i pasuje do ciągu HEX.</span><span class="sxs-lookup"><span data-stu-id="177af-118">Wi-Fi SSID name is right and matches with HEX string.</span></span>
    - <span data-ttu-id="177af-119">W przypadku protokołu EAP-TLS wartość TrustedRootCA zawiera skrót SHA-1 zaufanego certyfikatu głównego urzędu certyfikacji serwera.</span><span class="sxs-lookup"><span data-stu-id="177af-119">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server's trusted root CA certificate.</span></span> <span data-ttu-id="177af-120">Na komputerze z systemem Windows "certutil.exe -dump cert_file_name" polecenie spowoduje pokazanie ciągu skrótu SHA-1 certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="177af-120">On Windows PC "certutil.exe -dump cert_file_name" command will show a certificate's SHA-1 hash string.</span></span>
2. <span data-ttu-id="177af-121">Zbierz przechwytywanie pakietów sieciowych w dziennikach punktu dostępu, kontrolera lub serwera usługi AAA, aby dowiedzieć się, gdzie sesja protokołu EAP kończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="177af-121">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
    - <span data-ttu-id="177af-122">Jeśli tożsamość protokołu EAP dostarczana przez urządzenie HoloLens nie jest oczekiwana, sprawdź, czy tożsamość została poprawnie aprowizowana za pośrednictwem Wi-Fi lub certyfikatu klienta.</span><span class="sxs-lookup"><span data-stu-id="177af-122">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
    - <span data-ttu-id="177af-123">Jeśli serwer odrzuci certyfikat klienta urządzenia HoloLens, sprawdź, czy wymagany certyfikat klienta został zaaprowizowany na urządzeniu.</span><span class="sxs-lookup"><span data-stu-id="177af-123">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
    - <span data-ttu-id="177af-124">Jeśli urządzenie HoloLens odrzuci certyfikat serwera, sprawdź, czy certyfikat głównego urzędu certyfikacji serwera został aprowowany na urządzeniach HoloLens.</span><span class="sxs-lookup"><span data-stu-id="177af-124">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
3. <span data-ttu-id="177af-125">Jeśli profil przedsiębiorstwa jest aprowowany za pośrednictwem Wi-Fi aprowizowania, rozważ zastosowanie pakietu aprowizowania na Windows 10 PC.</span><span class="sxs-lookup"><span data-stu-id="177af-125">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="177af-126">Jeśli na komputerze Windows 10 również nie powiedzie się, postępuj zgodnie z przewodnikiem rozwiązywania problemów z uwierzytelnianiem klienta systemu Windows 802.1X.</span><span class="sxs-lookup"><span data-stu-id="177af-126">If it also fails on Windows 10 PC, follow the Windows client 802.1X authentication troubleshooting guide.</span></span>
4. <span data-ttu-id="177af-127">Prześlij nam opinię za pośrednictwem Centrum opinii.</span><span class="sxs-lookup"><span data-stu-id="177af-127">Send us feedback through Feedback Hub.</span></span>

[<span data-ttu-id="177af-128">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="177af-128">Back to list</span></span>](#list)

## <a name="wi-fi-troubleshooting"></a><span data-ttu-id="177af-129">Wi-Fi rozwiązywania problemów</span><span class="sxs-lookup"><span data-stu-id="177af-129">Wi-Fi Troubleshooting</span></span>

<span data-ttu-id="177af-130">Oto kilka rzeczy do wypróbowania, jeśli nie można połączyć urządzenia HoloLens z Wi-Fi siecią:</span><span class="sxs-lookup"><span data-stu-id="177af-130">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

1. <span data-ttu-id="177af-131">Upewnij się, Wi-Fi jest włączona.</span><span class="sxs-lookup"><span data-stu-id="177af-131">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="177af-132">Aby to sprawdzić, użyj gestu Start, a następnie wybierz pozycję Ustawienia > Sieci & Internet > Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="177af-132">To check, use the Start gesture, then select Settings > Network & Internet > Wi-Fi.</span></span> <span data-ttu-id="177af-133">Jeśli Wi-Fi jest wł., spróbuj go wyłączyć, a następnie ponownie wł.</span><span class="sxs-lookup"><span data-stu-id="177af-133">If Wi-Fi is on, try turning it off and then on again.</span></span>
2. <span data-ttu-id="177af-134">Umieść komputer bliżej routera lub punktu dostępu.</span><span class="sxs-lookup"><span data-stu-id="177af-134">Move closer to the router or access point.</span></span>
3. <span data-ttu-id="177af-135">Uruchom ponownie router Wi-Fi, a następnie ponownie uruchom urządzenie HoloLens.</span><span class="sxs-lookup"><span data-stu-id="177af-135">Restart your Wi-Fi router, then restart HoloLens.</span></span> <span data-ttu-id="177af-136">Spróbuj ponownie nałączyć połączenie.</span><span class="sxs-lookup"><span data-stu-id="177af-136">Try connecting again.</span></span>
4. <span data-ttu-id="177af-137">Jeśli żadna z tych czynności nie działa, upewnij się, że router korzysta z najnowszego oprogramowania układowego.</span><span class="sxs-lookup"><span data-stu-id="177af-137">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="177af-138">Te informacje można znaleźć w witrynie internetowej producenta.</span><span class="sxs-lookup"><span data-stu-id="177af-138">You can find this information on the manufacturer website.</span></span>

<span data-ttu-id="177af-139">Po zalogowaniu się do konta przedsiębiorstwa lub organizacji na urządzeniu może również zostać stosowane zasady usługi Mobile Zarządzanie urządzeniami (MDM), jeśli zasady zostały skonfigurowane przez administratora IT.</span><span class="sxs-lookup"><span data-stu-id="177af-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <a name="network-troubleshooting"></a><span data-ttu-id="177af-140">Rozwiązywanie problemów z siecią</span><span class="sxs-lookup"><span data-stu-id="177af-140">Network Troubleshooting</span></span>
<span data-ttu-id="177af-141">Jeśli problemy z siecią są przeszkodą dla pomyślnego wdrożenia i używania urządzenia HoloLens 2 w organizacji, dowiedz się, w jaki sposób dwa dobrze znane narzędzia diagnostyczne sieci — Fiddler i Wireshark — mogą pomóc w skanowaniu, diagnozowaniu i identyfikowaniu problemów.</span><span class="sxs-lookup"><span data-stu-id="177af-141">If network issues are an obstacle to successfully deploying and using HoloLens 2 in your organization, learn how two well-known network diagnostic tools, Fiddler and Wireshark can help you scan, diagnose, and identify problems.</span></span> <span data-ttu-id="177af-142">Aby uzyskać więcej [informacji, zapoznaj](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) się z tym blogiem.</span><span class="sxs-lookup"><span data-stu-id="177af-142">Check out this [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) for more details.</span></span>

[<span data-ttu-id="177af-143">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="177af-143">Back to list</span></span>](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a><span data-ttu-id="177af-144">Nie można zalogować się do wcześniej skonfigurować urządzenia HoloLens</span><span class="sxs-lookup"><span data-stu-id="177af-144">Can't sign in to a previously setup HoloLens device</span></span>

<span data-ttu-id="177af-145">Jeśli urządzenie zostało wcześniej ustawione dla kogoś innego , dla klienta lub dla byłego pracownika i nie masz hasła do [](https://docs.microsoft.com/intune/remote-actions/devices-wipe) odblokowania urządzenia, możesz użyć usługi Intune do zdalnego wyczyszczenia urządzenia.</span><span class="sxs-lookup"><span data-stu-id="177af-145">If your device was previously set up for someone else, either for a client or for a former employee, and you don't have their password to unlock the device, you can use Intune to remotely [wipe](https://docs.microsoft.com/intune/remote-actions/devices-wipe) the device.</span></span> <span data-ttu-id="177af-146">Następnie urządzenie zostanie ponownie flashe.</span><span class="sxs-lookup"><span data-stu-id="177af-146">The device then re-flashes itself.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="177af-147">Podczas czyszczenia urządzenia upewnij się, że pole Zachowaj stan rejestracji i **konto użytkownika nie** jest zaznaczone.</span><span class="sxs-lookup"><span data-stu-id="177af-147">When you wipe the device, make sure to leave **Retain enrollment state and user account** unchecked.</span></span>
[<span data-ttu-id="177af-148">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="177af-148">Back to list</span></span>](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a><span data-ttu-id="177af-149">Nie można zalogować się po zaktualizowaniu do systemu Windows Holographic 21H1</span><span class="sxs-lookup"><span data-stu-id="177af-149">Can't login after updating to Windows Holographic 21H1</span></span>

### <a name="symptoms"></a><span data-ttu-id="177af-150">Objawy</span><span class="sxs-lookup"><span data-stu-id="177af-150">Symptoms</span></span>
- <span data-ttu-id="177af-151">Logowanie przy użyciu numeru PIN nie powiedzie się po wprowadzeniu poprawnego numeru PIN.</span><span class="sxs-lookup"><span data-stu-id="177af-151">Using PIN to logon will fail after entering the correct PIN.</span></span>
- <span data-ttu-id="177af-152">Użycie metody logowania do sieci Web zakończy się niepowodzeniem po pomyślnym zalogowaniu się na stronie internetowej.</span><span class="sxs-lookup"><span data-stu-id="177af-152">Using the web logon method will fail after successfully signing in on the web page.</span></span>
- <span data-ttu-id="177af-153">Urządzenie nie jest wyświetlane jako "Azure AD joined" w Azure Portal [-> Azure Active Directory](https://portal.azure.com/) -> Devices.</span><span class="sxs-lookup"><span data-stu-id="177af-153">The device is not listed as “Azure AD joined” in [Azure portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span></span>

### <a name="cause"></a><span data-ttu-id="177af-154">Przyczyna</span><span class="sxs-lookup"><span data-stu-id="177af-154">Cause</span></span>
<span data-ttu-id="177af-155">Urządzenie, na które ma to wpływ, zostało usunięte z dzierżawy usługi Azure AD.</span><span class="sxs-lookup"><span data-stu-id="177af-155">The impacted device may have been deleted from the Azure AD tenant.</span></span> <span data-ttu-id="177af-156">Na przykład może się to zdarzyć, ponieważ:</span><span class="sxs-lookup"><span data-stu-id="177af-156">For example, this may happen because:</span></span>

- <span data-ttu-id="177af-157">Administrator lub użytkownik usunął urządzenie w Azure Portal lub przy użyciu programu PowerShell.</span><span class="sxs-lookup"><span data-stu-id="177af-157">An administrator or user deleted the device in the Azure portal or using PowerShell.</span></span>
- <span data-ttu-id="177af-158">Urządzenie zostało usunięte z dzierżawy usługi Azure AD z powodu braku aktywności.</span><span class="sxs-lookup"><span data-stu-id="177af-158">The device was removed from the Azure AD tenant due to inactivity.</span></span> <span data-ttu-id="177af-159">W przypadku wydajnie zarządzanego środowiska zwykle zalecamy administratorom IT usunięcie nieaktywnych, nieaktywnych urządzeń [ze swojej dzierżawy usługi Azure AD.](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices)</span><span class="sxs-lookup"><span data-stu-id="177af-159">For an efficiently managed environment, we typically recommend IT admins to [remove stale, inactive devices from their Azure AD tenant](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices).</span></span>

<span data-ttu-id="177af-160">Gdy urządzenie, na które ma to wpływ, spróbuje ponownie skontaktować się z dzierżawą usługi Azure AD po jej usunięciu, uwierzytelnianie w usłudze Azure AD nie powiedzie się.</span><span class="sxs-lookup"><span data-stu-id="177af-160">When an impacted device attempts to contact the Azure AD tenant again after it has been deleted it will fail to authenticate with Azure AD.</span></span> <span data-ttu-id="177af-161">Ten efekt jest często niewidoczny dla użytkownika urządzenia, ponieważ logowanie z pamięci podręcznej przy użyciu numeru PIN będzie nadal zezwalać użytkownikowi na logowanie.</span><span class="sxs-lookup"><span data-stu-id="177af-161">This effect is often invisible to the user of the device, as cached logon via PIN will continue to allow the user to logon.</span></span>

### <a name="mitigation"></a><span data-ttu-id="177af-162">Ograniczanie ryzyka</span><span class="sxs-lookup"><span data-stu-id="177af-162">Mitigation</span></span>
<span data-ttu-id="177af-163">Obecnie nie ma możliwości dodania usuniętego urządzenia HoloLens z powrotem do usługi Azure AD.</span><span class="sxs-lookup"><span data-stu-id="177af-163">There is currently no way to add a deleted HoloLens device back into Azure AD.</span></span> <span data-ttu-id="177af-164">Należy wyczyścić reflashed urządzeń, zgodnie z instrukcjami [dotyczącymi reflashing ich urządzenia.](hololens-recovery.md#clean-reflash-the-device)</span><span class="sxs-lookup"><span data-stu-id="177af-164">Affected devices will need to be clean-reflashed by following the instructions on [reflashing their device](hololens-recovery.md#clean-reflash-the-device).</span></span>

## <a name="autopilot-troubleshooting"></a><span data-ttu-id="177af-165">Rozwiązywanie problemów z rozwiązaniem Autopilot</span><span class="sxs-lookup"><span data-stu-id="177af-165">Autopilot Troubleshooting</span></span>

<span data-ttu-id="177af-166">Następujące artykuły mogą być przydatnym zasobem, aby dowiedzieć się więcej i rozwiązać problemy z rozwiązaniem Autopilot, jednak należy pamiętać, że te artykuły są oparte na programie Windows 10 Desktop i nie wszystkie informacje mogą dotyczyć urządzenia HoloLens:</span><span class="sxs-lookup"><span data-stu-id="177af-166">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="177af-167">Windows Autopilot — znane problemy</span><span class="sxs-lookup"><span data-stu-id="177af-167">Windows Autopilot - known issues</span></span>](https://docs.microsoft.com/mem/autopilot/known-issues)
- [<span data-ttu-id="177af-168">Rozwiązywanie problemów dotyczących rejestrowania urządzeń z systemem Windows w usłudze Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="177af-168">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="177af-169">Windows Autopilot — konflikty zasad</span><span class="sxs-lookup"><span data-stu-id="177af-169">Windows Autopilot - Policy Conflicts</span></span>](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a><span data-ttu-id="177af-170">Zarządzane urządzenia HoloLens : często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="177af-170">Managed HoloLens Devices FAQs</span></span>

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a><span data-ttu-id="177af-171">Czy mogę używać System Center Menedżer konfiguracji (SCCM) do zarządzania urządzeniami HoloLens?</span><span class="sxs-lookup"><span data-stu-id="177af-171">Can I use System Center Configuration Manager (SCCM) to manage HoloLens devices?</span></span>

<span data-ttu-id="177af-172">Nie.</span><span class="sxs-lookup"><span data-stu-id="177af-172">No.</span></span> <span data-ttu-id="177af-173">Do zarządzania urządzeniami HoloLens należy użyć systemu MDM.</span><span class="sxs-lookup"><span data-stu-id="177af-173">You have to use an MDM system to manage HoloLens devices.</span></span>

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a><span data-ttu-id="177af-174">Czy mogę używać Active Directory Domain Services (AD DS) do zarządzania kontami użytkowników urządzenia HoloLens?</span><span class="sxs-lookup"><span data-stu-id="177af-174">Can I use Active Directory Domain Services (AD DS) to manage HoloLens user accounts?</span></span>

<span data-ttu-id="177af-175">Nie.</span><span class="sxs-lookup"><span data-stu-id="177af-175">No.</span></span> <span data-ttu-id="177af-176">Aby zarządzać kontami użytkowników urządzeń HoloLens, musisz użyć usługi Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="177af-176">You have to use Azure Active Directory (Azure AD) to manage user accounts for HoloLens devices.</span></span>

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a><span data-ttu-id="177af-177">Czy urządzenie HoloLens jest w stanie automatycznie ująć w rejestrację zautomatyzowane systemy przechwytywania danych (ADCS)?</span><span class="sxs-lookup"><span data-stu-id="177af-177">Is HoloLens capable of Automated Data Capture Systems (ADCS) auto-enrollment?</span></span>

<span data-ttu-id="177af-178">Nie.</span><span class="sxs-lookup"><span data-stu-id="177af-178">No.</span></span>

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a><span data-ttu-id="177af-179">Czy urządzenie HoloLens może uczestniczyć w Integrated Windows Authentication?</span><span class="sxs-lookup"><span data-stu-id="177af-179">Can HoloLens participate in Integrated Windows Authentication?</span></span>

<span data-ttu-id="177af-180">Nie.</span><span class="sxs-lookup"><span data-stu-id="177af-180">No.</span></span>

### <a name="does-hololens-support-branding"></a><span data-ttu-id="177af-181">Czy urządzenie HoloLens obsługuje znakowanie?</span><span class="sxs-lookup"><span data-stu-id="177af-181">Does HoloLens support branding?</span></span>

<span data-ttu-id="177af-182">Nie.</span><span class="sxs-lookup"><span data-stu-id="177af-182">No.</span></span> <span data-ttu-id="177af-183">Ten problem można jednak ominić przy użyciu jednej z następujących metod:</span><span class="sxs-lookup"><span data-stu-id="177af-183">However, you can work around this issue by using one of the following approaches:</span></span>

- <span data-ttu-id="177af-184">Utwórz aplikację niestandardową, a następnie włącz [tryb kiosku.](hololens-kiosk.md)</span><span class="sxs-lookup"><span data-stu-id="177af-184">Create a custom app, and then [enable Kiosk mode](hololens-kiosk.md).</span></span> <span data-ttu-id="177af-185">Aplikacja niestandardowa może mieć znakowanie i może uruchamiać inne aplikacje (takie jak Remote Assist).</span><span class="sxs-lookup"><span data-stu-id="177af-185">The custom app can have branding, and can launch other apps (such as Remote Assist).</span></span>  
- <span data-ttu-id="177af-186">Zmień wszystkie obrazy profilu użytkownika w usłudze Azure AD na logo firmy.</span><span class="sxs-lookup"><span data-stu-id="177af-186">Change all of the user profile pictures in Azure AD to your company logo.</span></span> <span data-ttu-id="177af-187">Jednak może to nie być pożądane we wszystkich scenariuszach.</span><span class="sxs-lookup"><span data-stu-id="177af-187">However, this may not be desirable for all scenarios.</span></span>

### <a name="what-logging-capabilities-does-hololens-2-offer"></a><span data-ttu-id="177af-188">Jakie możliwości rejestrowania oferuje urządzenie HoloLens 2?</span><span class="sxs-lookup"><span data-stu-id="177af-188">What logging capabilities does HoloLens 2 offer?</span></span>

<span data-ttu-id="177af-189">Rejestrowanie jest ograniczone do śladów, które mogą być przechwytywane w scenariuszach tworzenia lub rozwiązywania problemów, lub danych telemetrycznych, które urządzenia wysyłają do serwerów firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="177af-189">Logging is limited to traces that can be captured in development or troubleshooting scenarios, or telemetry that the devices send to Microsoft servers.</span></span>

## <a name="questions-about-securing-hololens-devices"></a><span data-ttu-id="177af-190">Pytania dotyczące zabezpieczania urządzeń HoloLens</span><span class="sxs-lookup"><span data-stu-id="177af-190">Questions about securing HoloLens devices</span></span>

<span data-ttu-id="177af-191">Zobacz [nasze informacje o zabezpieczeniach urządzenia HoloLens 2.](security-overview.md)</span><span class="sxs-lookup"><span data-stu-id="177af-191">See [our HoloLens 2 security information](security-overview.md).</span></span>
<span data-ttu-id="177af-192">W przypadku urządzeń HoloLens 1. generacji zapoznaj się z często [zadawanymi pytaniami.](hololens1-faq-security.md)</span><span class="sxs-lookup"><span data-stu-id="177af-192">For HoloLens 1st Gen devices please review [this FAQ](hololens1-faq-security.md).</span></span>

[<span data-ttu-id="177af-193">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="177af-193">Back to list</span></span>](#list)
