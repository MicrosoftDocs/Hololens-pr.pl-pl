---
title: HoloLens 2 i rozwiązywanie problemów z urządzeniami zarządzanymi
description: Rozwiązywanie problemów HoloLens 2 urządzeń w Enterprise środowisku
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
ms.openlocfilehash: 9f3950de51e4bfa2a76431a2a070d87aa81ed443
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636881"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a><span data-ttu-id="9352e-104">Rozwiązywanie problemów z implementacją i urządzeniami zarządzanymi</span><span class="sxs-lookup"><span data-stu-id="9352e-104">Troubleshooting implementation and managed devices</span></span> 

<span data-ttu-id="9352e-105">W tym artykule opisano sposób rozwiązywania kilku problemów lub odpowiadania na pytania dotyczące implementacji i zarządzania HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="9352e-105">This article describes how to resolve several issues or answer questions regarding implementation and management of HoloLens 2.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="9352e-106">Przed rozpoczęciem procedury rozwiązywania problemów upewnij się, że urządzenie jest obciążane od **20 do 40%** pojemności baterii, jeśli jest to możliwe.</span><span class="sxs-lookup"><span data-stu-id="9352e-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="9352e-107">Wskaźniki [naładowania baterii znajdujące](hololens2-setup.md#lights-that-indicate-the-battery-level) się pod przyciskiem zasilania to szybki sposób na sprawdzenie pojemności baterii bez logowania się do urządzenia.</span><span class="sxs-lookup"><span data-stu-id="9352e-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>


<a id="list"></a>
- [<span data-ttu-id="9352e-108">Rozwiązywanie problemów z protokołu EAP</span><span class="sxs-lookup"><span data-stu-id="9352e-108">EAP Troubleshooting</span></span>](#eap-troubleshooting)
- [<span data-ttu-id="9352e-109">Rozwiązywanie problemów z siecią Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="9352e-109">Wi-Fi Troubleshooting</span></span>](#wi-fi-troubleshooting)
- [<span data-ttu-id="9352e-110">Rozwiązywanie problemów z siecią</span><span class="sxs-lookup"><span data-stu-id="9352e-110">Network Troubleshooting</span></span>](#network-troubleshooting)
- [<span data-ttu-id="9352e-111">Nie można zalogować się do wcześniej HoloLens urządzenia</span><span class="sxs-lookup"><span data-stu-id="9352e-111">Can't sign in to a previously setup HoloLens device</span></span>](#cant-sign-in-to-a-previously-setup-hololens-device)
- [<span data-ttu-id="9352e-112">Nie można zalogować się po aktualizacji do Windows Holographic 21H1</span><span class="sxs-lookup"><span data-stu-id="9352e-112">Can't login after updating to Windows Holographic 21H1</span></span>](#cant-login-after-updating-to-windows-holographic-21h1)
- [<span data-ttu-id="9352e-113">Rozwiązywanie problemów z rozwiązaniem Autopilot</span><span class="sxs-lookup"><span data-stu-id="9352e-113">Autopilot Troubleshooting</span></span>](#autopilot-troubleshooting)
- [<span data-ttu-id="9352e-114">Często zadawane pytania HoloLens urządzeń zarządzanych</span><span class="sxs-lookup"><span data-stu-id="9352e-114">Managed HoloLens Devices FAQs</span></span>](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a><span data-ttu-id="9352e-115">Rozwiązywanie problemów z protokołu EAP</span><span class="sxs-lookup"><span data-stu-id="9352e-115">EAP Troubleshooting</span></span>
1. <span data-ttu-id="9352e-116">Sprawdź, Wi-Fi profil ma odpowiednie ustawienia:</span><span class="sxs-lookup"><span data-stu-id="9352e-116">Double check Wi-Fi profile has right settings:</span></span>
    - <span data-ttu-id="9352e-117">Typ protokołu EAP jest poprawnie skonfigurowany, typowe typy protokołu EAP: EAP-TLS (13), EAP-TTLS (21) i PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="9352e-117">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
    - <span data-ttu-id="9352e-118">Wi-Fi SSID jest właściwa i pasuje do ciągu HEX.</span><span class="sxs-lookup"><span data-stu-id="9352e-118">Wi-Fi SSID name is right and matches with HEX string.</span></span>
    - <span data-ttu-id="9352e-119">W przypadku protokołu EAP-TLS wartość TrustedRootCA zawiera skrót SHA-1 certyfikatu zaufanego głównego urzędu certyfikacji serwera.</span><span class="sxs-lookup"><span data-stu-id="9352e-119">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server's trusted root CA certificate.</span></span> <span data-ttu-id="9352e-120">Na Windows pc "certutil.exe -dump cert_file_name" będzie wyświetlać ciąg skrótu SHA-1 certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="9352e-120">On Windows PC "certutil.exe -dump cert_file_name" command will show a certificate's SHA-1 hash string.</span></span>
2. <span data-ttu-id="9352e-121">Zbierz przechwytywanie pakietów sieciowych w dziennikach punktu dostępu, kontrolera lub serwera usługi AAA, aby dowiedzieć się, gdzie sesja protokołu EAP kończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="9352e-121">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
    - <span data-ttu-id="9352e-122">Jeśli tożsamość EAP dostarczana przez HoloLens jest oczekiwana, sprawdź, czy tożsamość została poprawnie aprowizowana za pośrednictwem profilu Wi-Fi certyfikatu klienta.</span><span class="sxs-lookup"><span data-stu-id="9352e-122">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
    - <span data-ttu-id="9352e-123">Jeśli serwer odrzuci HoloLens klienta, sprawdź, czy wymagany certyfikat klienta został aprowowany na urządzeniu.</span><span class="sxs-lookup"><span data-stu-id="9352e-123">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
    - <span data-ttu-id="9352e-124">Jeśli HoloLens certyfikat serwera, sprawdź, czy certyfikat głównego urzędu certyfikacji serwera został aprowowany na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9352e-124">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
3. <span data-ttu-id="9352e-125">Jeśli profil przedsiębiorstwa jest aprowowany za pośrednictwem Wi-Fi aprowizowania, rozważ zastosowanie pakietu aprowizowania na komputerze Windows 10 PC.</span><span class="sxs-lookup"><span data-stu-id="9352e-125">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="9352e-126">Jeśli na komputerze nie powiedzie się Windows 10, postępuj zgodnie z Windows rozwiązywania problemów z uwierzytelnianiem klienta 802.1X.</span><span class="sxs-lookup"><span data-stu-id="9352e-126">If it also fails on Windows 10 PC, follow the Windows client 802.1X authentication troubleshooting guide.</span></span>
4. <span data-ttu-id="9352e-127">Prześlij nam opinię za pośrednictwem Centrum opinii.</span><span class="sxs-lookup"><span data-stu-id="9352e-127">Send us feedback through Feedback Hub.</span></span>

[<span data-ttu-id="9352e-128">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="9352e-128">Back to list</span></span>](#list)

## <a name="wi-fi-troubleshooting"></a><span data-ttu-id="9352e-129">Wi-Fi rozwiązywania problemów</span><span class="sxs-lookup"><span data-stu-id="9352e-129">Wi-Fi Troubleshooting</span></span>

<span data-ttu-id="9352e-130">Oto kilka rzeczy, które należy wypróbować, jeśli nie można połączyć HoloLens z Wi-Fi siecią:</span><span class="sxs-lookup"><span data-stu-id="9352e-130">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

1. <span data-ttu-id="9352e-131">Upewnij się, Wi-Fi jest włączona.</span><span class="sxs-lookup"><span data-stu-id="9352e-131">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="9352e-132">Aby to sprawdzić, użyj gestu Uruchom, a następnie wybierz pozycję Ustawienia > Network & Internet > Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="9352e-132">To check, use the Start gesture, then select Settings > Network & Internet > Wi-Fi.</span></span> <span data-ttu-id="9352e-133">Jeśli Wi-Fi jest wł., spróbuj go wyłączyć, a następnie ponownie wł.</span><span class="sxs-lookup"><span data-stu-id="9352e-133">If Wi-Fi is on, try turning it off and then on again.</span></span>
2. <span data-ttu-id="9352e-134">Umieść komputer bliżej routera lub punktu dostępu.</span><span class="sxs-lookup"><span data-stu-id="9352e-134">Move closer to the router or access point.</span></span>
3. <span data-ttu-id="9352e-135">Uruchom ponownie Wi-Fi, a następnie uruchom ponownie HoloLens.</span><span class="sxs-lookup"><span data-stu-id="9352e-135">Restart your Wi-Fi router, then restart HoloLens.</span></span> <span data-ttu-id="9352e-136">Spróbuj ponownie nałączyć połączenie.</span><span class="sxs-lookup"><span data-stu-id="9352e-136">Try connecting again.</span></span>
4. <span data-ttu-id="9352e-137">Jeśli żadna z tych czynności nie działa, upewnij się, że router korzysta z najnowszego oprogramowania układowego.</span><span class="sxs-lookup"><span data-stu-id="9352e-137">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="9352e-138">Te informacje można znaleźć w witrynie internetowej producenta.</span><span class="sxs-lookup"><span data-stu-id="9352e-138">You can find this information on the manufacturer website.</span></span>

<span data-ttu-id="9352e-139">Po zalogowaniu się do konta przedsiębiorstwa lub organizacji na urządzeniu może również zostać stosowane zasady usługi Mobile Zarządzanie urządzeniami (MDM), jeśli zasady zostały skonfigurowane przez administratora IT.</span><span class="sxs-lookup"><span data-stu-id="9352e-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

[<span data-ttu-id="9352e-140">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="9352e-140">Back to list</span></span>](#list)

## <a name="network-troubleshooting"></a><span data-ttu-id="9352e-141">Rozwiązywanie problemów z siecią</span><span class="sxs-lookup"><span data-stu-id="9352e-141">Network Troubleshooting</span></span>
<span data-ttu-id="9352e-142">Jeśli problemy z siecią są przeszkodą dla pomyślnego wdrożenia i używania programu HoloLens 2 w organizacji, skonfiguruj program Fiddler i/lub Wireshark, aby przechwytywać i analizować ruch HTTP/HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9352e-142">If network issues are an obstacle to successfully deploying and using HoloLens 2 in your organization, configure Fiddler and/or Wireshark to capture and analyze HTTP/HTTPS traffic.</span></span> 

### <a name="configure-fiddler-to-capture-http-traffic"></a><span data-ttu-id="9352e-143">Konfigurowanie programu Fiddler do przechwytywania ruchu HTTP</span><span class="sxs-lookup"><span data-stu-id="9352e-143">Configure Fiddler to capture HTTP traffic</span></span>
<span data-ttu-id="9352e-144">Program Fiddler to internetowy serwer proxy debugowania, który służy do rozwiązywania problemów z protokołu HTTP(S).</span><span class="sxs-lookup"><span data-stu-id="9352e-144">Fiddler is a web debugging proxy and is used to troubleshoot HTTP(S) issues.</span></span> <span data-ttu-id="9352e-145">Przechwytuje każde żądanie HTTP, które komputer wykonuje, i rejestruje wszystkie skojarzone z nim dane.</span><span class="sxs-lookup"><span data-stu-id="9352e-145">It captures every HTTP request the computer makes and records everything associated with it.</span></span> <span data-ttu-id="9352e-146">Odkrywanie problemów z uwierzytelnianiem użytkowników końcowych dla aplikacji HTTPS zwiększa produktywność i wydajność dla docelowych HoloLens 2 przypadków użycia.</span><span class="sxs-lookup"><span data-stu-id="9352e-146">Uncovering end-user authentication issues for your HTTPS apps drives better productivity and efficiency for your target HoloLens 2 use cases.</span></span> 

#### <a name="prerequisites"></a><span data-ttu-id="9352e-147">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="9352e-147">Prerequisites</span></span>
 
- <span data-ttu-id="9352e-148">HoloLens 2 i komputer musi znajdować się w tej samej sieci</span><span class="sxs-lookup"><span data-stu-id="9352e-148">HoloLens 2 devices and your PC must be on the same network</span></span>
- <span data-ttu-id="9352e-149">Zanotuj adres IP komputera</span><span class="sxs-lookup"><span data-stu-id="9352e-149">Note the IP address of your PC</span></span>

#### <a name="install-and-configure-fiddler"></a><span data-ttu-id="9352e-150">Instalowanie i konfigurowanie programu Fiddler</span><span class="sxs-lookup"><span data-stu-id="9352e-150">Install and Configure Fiddler</span></span>

1. <span data-ttu-id="9352e-151">Na komputerze — zainstaluj [i](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) uruchom program Fiddler.</span><span class="sxs-lookup"><span data-stu-id="9352e-151">On your PC - [install](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) and start Fiddler.</span></span>  
1. <span data-ttu-id="9352e-152">Na komputerze — skonfiguruj program Fiddler tak, aby zezwalał komputerom zdalnym na nawiązywanie połączenia.</span><span class="sxs-lookup"><span data-stu-id="9352e-152">On your PC - configure Fiddler to allow remote computers to connect.</span></span>
    1. <span data-ttu-id="9352e-153">Przejdź do fiddler Ustawienia -> Connections</span><span class="sxs-lookup"><span data-stu-id="9352e-153">Go to Fiddler Settings -> Connections</span></span>
    1. <span data-ttu-id="9352e-154">Zwróć uwagę na port nasłuchiwania dla programu Fiddler (wartość domyślna to 8866)</span><span class="sxs-lookup"><span data-stu-id="9352e-154">Note the listening port for Fiddler (default is 8866)</span></span>
    1. <span data-ttu-id="9352e-155">Zaznacz pole wyboru Zezwalaj komputerom zdalnym na nawiązywanie połączeń</span><span class="sxs-lookup"><span data-stu-id="9352e-155">Check Allow remote computers to connect</span></span>
    1. <span data-ttu-id="9352e-156">Klikanie pozycji Zapisz.</span><span class="sxs-lookup"><span data-stu-id="9352e-156">Click Save</span></span>
3. <span data-ttu-id="9352e-157">Na komputerze HoloLens 2 — skonfiguruj program Fiddler jako serwer proxy<sup>1:</sup></span><span class="sxs-lookup"><span data-stu-id="9352e-157">On your HoloLens 2 – configure Fiddler as the proxy server<sup>1</sup>:</span></span>
    1. <span data-ttu-id="9352e-158">Otwórz okno menu Start i wybierz pozycję Ustawienia</span><span class="sxs-lookup"><span data-stu-id="9352e-158">Open the Start menu and select Settings</span></span>
    1. <span data-ttu-id="9352e-159">Wybierz pozycję Sieć & Internet, a następnie pozycję Serwer proxy w menu po lewej stronie</span><span class="sxs-lookup"><span data-stu-id="9352e-159">Select Network & Internet and then Proxy on the left menu</span></span>
    1. <span data-ttu-id="9352e-160">Przewiń w dół do ręcznej konfiguracji serwera proxy i przełącz ustawienie Użyj serwera proxy na Wł.</span><span class="sxs-lookup"><span data-stu-id="9352e-160">Scroll down to Manual proxy setup and toggle Use a proxy server to On</span></span>
    1. <span data-ttu-id="9352e-161">Wprowadź adres IP komputera, na którym zainstalowano program Fiddler</span><span class="sxs-lookup"><span data-stu-id="9352e-161">Enter the IP address of the PC where Fiddler is installed</span></span>
    1. <span data-ttu-id="9352e-162">Wprowadź numer portu zanotowyny powyżej (wartość domyślna to 8866)</span><span class="sxs-lookup"><span data-stu-id="9352e-162">Enter the port number noted above (default is 8866)</span></span>
    1. <span data-ttu-id="9352e-163">Klikanie pozycji Zapisz.</span><span class="sxs-lookup"><span data-stu-id="9352e-163">Click Save</span></span>

<span data-ttu-id="9352e-164"><sup>1</sup> W przypadku kompilacji 20279.1006+ (niejawni testerzy i nadchodzące wydanie) użyj następujących kroków, aby skonfigurować serwer proxy:</span><span class="sxs-lookup"><span data-stu-id="9352e-164"><sup>1</sup> For builds 20279.1006+ (Insiders and the upcoming release), use the following steps to configure proxy:</span></span>
1. <span data-ttu-id="9352e-165">Otwórz menu Start i przejdź do strony właściwości Wi-Fi sieci wirtualnej</span><span class="sxs-lookup"><span data-stu-id="9352e-165">Open the Start menu and go to your Wi-Fi Network’s Properties page</span></span> 
1. <span data-ttu-id="9352e-166">Przewiń w dół do serwera proxy</span><span class="sxs-lookup"><span data-stu-id="9352e-166">Scroll down to Proxy</span></span>
1. <span data-ttu-id="9352e-167">Zmiana na konfigurację ręczną</span><span class="sxs-lookup"><span data-stu-id="9352e-167">Change to Manual Setup</span></span>
1. <span data-ttu-id="9352e-168">Wprowadź adres IP komputera, na którym zainstalowano program Fiddler</span><span class="sxs-lookup"><span data-stu-id="9352e-168">Enter the IP address of the PC where Fiddler is installed</span></span>
1. <span data-ttu-id="9352e-169">Wprowadź numer portu zanotowyny powyżej.</span><span class="sxs-lookup"><span data-stu-id="9352e-169">Enter the port number noted above.</span></span> <span data-ttu-id="9352e-170">(wartość domyślna to 8866)</span><span class="sxs-lookup"><span data-stu-id="9352e-170">(default is 8866)</span></span>
1. <span data-ttu-id="9352e-171">Kliknij przycisk Zastosuj</span><span class="sxs-lookup"><span data-stu-id="9352e-171">Click Apply</span></span>
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a><span data-ttu-id="9352e-172">Odszyfrowywanie ruchu HTTPS z HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="9352e-172">Decrypt HTTPS traffic from HoloLens 2</span></span>

1. <span data-ttu-id="9352e-173">Na komputerze — wyeksportuj certyfikat fiddler.</span><span class="sxs-lookup"><span data-stu-id="9352e-173">On your PC – export the Fiddler certificate.</span></span>
    1. <span data-ttu-id="9352e-174">Przejdź do strony Fiddler Ustawienia -> HTTPS i rozwiń Ustawienia</span><span class="sxs-lookup"><span data-stu-id="9352e-174">Go to Fiddler Settings -> HTTPS and expand Advanced Settings</span></span>
    2. <span data-ttu-id="9352e-175">Kliknij pozycję Eksportuj certyfikat fiddler.</span><span class="sxs-lookup"><span data-stu-id="9352e-175">Click Export Fiddler certificate.</span></span> <span data-ttu-id="9352e-176">Spowoduje to zapisanie na pulpicie</span><span class="sxs-lookup"><span data-stu-id="9352e-176">It will save to your desktop</span></span>
    3. <span data-ttu-id="9352e-177">Przenieś certyfikat do folderu Pobrane na komputerze HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="9352e-177">Move the certificate over to the Downloads folder on your HoloLens 2</span></span>

2.  <span data-ttu-id="9352e-178">Na komputerze HoloLens 2 — zaimportuj certyfikat fiddler.</span><span class="sxs-lookup"><span data-stu-id="9352e-178">On your HoloLens 2 - import the Fiddler certificate.</span></span>
    1. <span data-ttu-id="9352e-179">Przejdź do Ustawienia -> Update i Security -> Certificates</span><span class="sxs-lookup"><span data-stu-id="9352e-179">Go to Settings -> Update and Security -> Certificates</span></span>
    2. <span data-ttu-id="9352e-180">Kliknij pozycję Zainstaluj certyfikat, przejdź do folderu Pobrane i wybierz certyfikat programu Fiddler.</span><span class="sxs-lookup"><span data-stu-id="9352e-180">Click Install Certificate, browse to the Downloads folder and select the Fiddler certificate</span></span>
    3. <span data-ttu-id="9352e-181">Zmień lokalizację magazynu na Komputer lokalny</span><span class="sxs-lookup"><span data-stu-id="9352e-181">Change Store Location to Local Machine</span></span>
    4. <span data-ttu-id="9352e-182">Zmienianie magazynu certyfikatów na główny</span><span class="sxs-lookup"><span data-stu-id="9352e-182">Change Certificate Store to root</span></span>
    5. <span data-ttu-id="9352e-183">Wybierz pozycję Zainstaluj</span><span class="sxs-lookup"><span data-stu-id="9352e-183">Select Install</span></span>
    6. <span data-ttu-id="9352e-184">Upewnij się, że certyfikat jest pokazywany na liście certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="9352e-184">Confirm the certificate is showing in the list of certificates.</span></span> <span data-ttu-id="9352e-185">Jeśli nie, powtórz powyższe kroki</span><span class="sxs-lookup"><span data-stu-id="9352e-185">If not, repeat the above steps</span></span>

#### <a name="inspect-https-sessions"></a><span data-ttu-id="9352e-186">Inspekcja sesji HTTP(S)</span><span class="sxs-lookup"><span data-stu-id="9352e-186">Inspect HTTP(S) sessions</span></span>

<span data-ttu-id="9352e-187">Na komputerze program Fiddler będzie wyświetlać HoloLens http(S) na żywo w wersji 2.</span><span class="sxs-lookup"><span data-stu-id="9352e-187">On your PC, Fiddler will show the HoloLens 2’s live HTTP(S) sessions.</span></span> <span data-ttu-id="9352e-188">Panel Inspektorzy w programie Fiddler może wyświetlać żądania/odpowiedzi HTTP(S) w różnych widokach — na przykład widok "Nieprzetworzone" wyświetla nieprzetworzone żądanie lub odpowiedź w postaci zwykłego tekstu.</span><span class="sxs-lookup"><span data-stu-id="9352e-188">The Inspectors panel in Fiddler can show HTTP(S) request/response in different views - for example, the “Raw” view shows the raw request or response in plain text.</span></span> 

### <a name="configure-wireshark-to-capture-network-traffic"></a><span data-ttu-id="9352e-189">Konfigurowanie aplikacji Wireshark do przechwytywania ruchu sieciowego</span><span class="sxs-lookup"><span data-stu-id="9352e-189">Configure Wireshark to capture network traffic</span></span>
<span data-ttu-id="9352e-190">Wireshark to analizator protokołu sieciowego, który służy do sprawdzania ruchu TCP/UDP z i do urządzeń HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="9352e-190">Wireshark is a network protocol analyzer and is used to inspect TCP/UDP traffic from and to your HoloLens 2 devices.</span></span> <span data-ttu-id="9352e-191">Dzięki temu można łatwo określić, jaki ruch jest przekraczany przez sieć do sieci HoloLens 2, jaka jest jej część, jak często występuje opóźnienie między określonymi przeskokami itd.</span><span class="sxs-lookup"><span data-stu-id="9352e-191">This makes it easy to identify what traffic is crossing your network to your HoloLens 2, how much of it, how frequently, how much latency there is between certain hops, and so forth.</span></span>

#### <a name="prerequisites"></a><span data-ttu-id="9352e-192">Wymagania wstępne:</span><span class="sxs-lookup"><span data-stu-id="9352e-192">Prerequisites:</span></span>
- <span data-ttu-id="9352e-193">Komputer musi mieć dostęp do Internetu i obsługiwać udostępnianie Internetu za pośrednictwem Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="9352e-193">PC must have internet access and support Internet sharing over Wi-Fi</span></span>

#### <a name="install-and-configure-wireshark"></a><span data-ttu-id="9352e-194">Instalowanie i konfigurowanie programu Wireshark</span><span class="sxs-lookup"><span data-stu-id="9352e-194">Install and Configure Wireshark</span></span>
1. <span data-ttu-id="9352e-195">Na komputerze — zainstaluj program [Wireshark](https://www.wireshark.org/#download)</span><span class="sxs-lookup"><span data-stu-id="9352e-195">On your PC - install [Wireshark](https://www.wireshark.org/#download)</span></span> 
1. <span data-ttu-id="9352e-196">Na komputerze — włącz opcję Mobilny hotspot, aby udostępnić połączenie internetowe z sieci Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="9352e-196">On your PC - enable Mobile hotspot to share your Internet connection from Wi-Fi.</span></span>
1. <span data-ttu-id="9352e-197">Na komputerze — uruchom program Wireshark i przechwyć ruch z interfejsu mobilnego hotspotu.</span><span class="sxs-lookup"><span data-stu-id="9352e-197">On your PC - start Wireshark and capture traffic from the Mobile hotspot interface.</span></span> 
1. <span data-ttu-id="9352e-198">Na komputerze HoloLens 2 — zmień sieć Wi-Fi na hotspot mobilny komputera.</span><span class="sxs-lookup"><span data-stu-id="9352e-198">On your HoloLens 2 – change its Wi-Fi network to the PC’s Mobile hotspot.</span></span> <span data-ttu-id="9352e-199">HoloLens 2 ruch IP będzie pokazywany w programie Wireshark.</span><span class="sxs-lookup"><span data-stu-id="9352e-199">HoloLens 2 IP traffic will show up in Wireshark.</span></span>

#### <a name="analyze-wireshark-logs"></a><span data-ttu-id="9352e-200">Analizowanie dzienników wireshark</span><span class="sxs-lookup"><span data-stu-id="9352e-200">Analyze Wireshark logs</span></span>
<span data-ttu-id="9352e-201">Filtry Wireshark mogą pomóc w odfiltrowyniu pakietów zainteresowania.</span><span class="sxs-lookup"><span data-stu-id="9352e-201">Wireshark filters can help filtering out the packets of interests.</span></span> 

<span data-ttu-id="9352e-202">Zapoznaj się z oryginalnym [blogiem](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458).</span><span class="sxs-lookup"><span data-stu-id="9352e-202">Check out the original [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458).</span></span>

[<span data-ttu-id="9352e-203">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="9352e-203">Back to list</span></span>](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a><span data-ttu-id="9352e-204">Nie można zalogować się do wcześniej HoloLens urządzenia</span><span class="sxs-lookup"><span data-stu-id="9352e-204">Can't sign in to a previously setup HoloLens device</span></span>

<span data-ttu-id="9352e-205">Jeśli urządzenie zostało wcześniej ustawione dla kogoś innego , dla klienta lub dla byłego pracownika i nie masz hasła do [](/intune/remote-actions/devices-wipe) odblokowania urządzenia, możesz użyć usługi Intune do zdalnego wyczyszczenia urządzenia.</span><span class="sxs-lookup"><span data-stu-id="9352e-205">If your device was previously set up for someone else, either for a client or for a former employee, and you don't have their password to unlock the device, you can use Intune to remotely [wipe](/intune/remote-actions/devices-wipe) the device.</span></span> <span data-ttu-id="9352e-206">Następnie urządzenie zostanie ponownie flashe.</span><span class="sxs-lookup"><span data-stu-id="9352e-206">The device then re-flashes itself.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="9352e-207">Podczas czyszczenia urządzenia upewnij się, że pole Zachowaj stan rejestracji i **konto użytkownika nie** jest zaznaczone.</span><span class="sxs-lookup"><span data-stu-id="9352e-207">When you wipe the device, make sure to leave **Retain enrollment state and user account** unchecked.</span></span>

[<span data-ttu-id="9352e-208">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="9352e-208">Back to list</span></span>](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a><span data-ttu-id="9352e-209">Nie można zalogować się po aktualizacji do Windows Holographic 21H1</span><span class="sxs-lookup"><span data-stu-id="9352e-209">Can't login after updating to Windows Holographic 21H1</span></span>

### <a name="symptoms"></a><span data-ttu-id="9352e-210">Objawy</span><span class="sxs-lookup"><span data-stu-id="9352e-210">Symptoms</span></span>
- <span data-ttu-id="9352e-211">Logowanie przy użyciu numeru PIN nie powiedzie się po wprowadzeniu poprawnego numeru PIN.</span><span class="sxs-lookup"><span data-stu-id="9352e-211">Using PIN to logon will fail after entering the correct PIN.</span></span>
- <span data-ttu-id="9352e-212">Użycie metody logowania do sieci Web zakończy się niepowodzeniem po pomyślnym zalogowaniu się na stronie internetowej.</span><span class="sxs-lookup"><span data-stu-id="9352e-212">Using the web logon method will fail after successfully signing in on the web page.</span></span>
- <span data-ttu-id="9352e-213">Urządzenie nie jest wyświetlane jako "Azure AD joined" w Azure Portal [-> Azure Active Directory](https://portal.azure.com/) -> Devices.</span><span class="sxs-lookup"><span data-stu-id="9352e-213">The device is not listed as “Azure AD joined” in [Azure portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span></span>

### <a name="cause"></a><span data-ttu-id="9352e-214">Przyczyna</span><span class="sxs-lookup"><span data-stu-id="9352e-214">Cause</span></span>
<span data-ttu-id="9352e-215">Urządzenie, na które ma to wpływ, zostało usunięte z dzierżawy usługi Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9352e-215">The impacted device may have been deleted from the Azure AD tenant.</span></span> <span data-ttu-id="9352e-216">Na przykład może się to zdarzyć, ponieważ:</span><span class="sxs-lookup"><span data-stu-id="9352e-216">For example, this may happen because:</span></span>

- <span data-ttu-id="9352e-217">Administrator lub użytkownik usunął urządzenie w Azure Portal lub przy użyciu programu PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9352e-217">An administrator or user deleted the device in the Azure portal or using PowerShell.</span></span>
- <span data-ttu-id="9352e-218">Urządzenie zostało usunięte z dzierżawy usługi Azure AD z powodu braku aktywności.</span><span class="sxs-lookup"><span data-stu-id="9352e-218">The device was removed from the Azure AD tenant due to inactivity.</span></span> <span data-ttu-id="9352e-219">W przypadku wydajnie zarządzanego środowiska zwykle zalecamy administratorom IT usunięcie nieaktywnych, nieaktywnych urządzeń [ze swojej dzierżawy usługi Azure AD.](/azure/active-directory/devices/manage-stale-devices)</span><span class="sxs-lookup"><span data-stu-id="9352e-219">For an efficiently managed environment, we typically recommend IT admins to [remove stale, inactive devices from their Azure AD tenant](/azure/active-directory/devices/manage-stale-devices).</span></span>

<span data-ttu-id="9352e-220">Gdy urządzenie, na które ma to wpływ, spróbuje ponownie skontaktować się z dzierżawą usługi Azure AD po jej usunięciu, uwierzytelnianie w usłudze Azure AD nie powiedzie się.</span><span class="sxs-lookup"><span data-stu-id="9352e-220">When an impacted device attempts to contact the Azure AD tenant again after it has been deleted it will fail to authenticate with Azure AD.</span></span> <span data-ttu-id="9352e-221">Ten efekt jest często niewidoczny dla użytkownika urządzenia, ponieważ logowanie z pamięci podręcznej przy użyciu numeru PIN będzie nadal zezwalać użytkownikowi na logowanie.</span><span class="sxs-lookup"><span data-stu-id="9352e-221">This effect is often invisible to the user of the device, as cached logon via PIN will continue to allow the user to logon.</span></span>

### <a name="mitigation"></a><span data-ttu-id="9352e-222">Ograniczanie ryzyka</span><span class="sxs-lookup"><span data-stu-id="9352e-222">Mitigation</span></span>
<span data-ttu-id="9352e-223">Obecnie nie ma możliwości dodania usuniętego urządzenia HoloLens z powrotem do usługi Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9352e-223">There is currently no way to add a deleted HoloLens device back into Azure AD.</span></span> <span data-ttu-id="9352e-224">Należy wyczyścić reflashed urządzeń, zgodnie z instrukcjami [dotyczącymi reflashing ich urządzenia.](hololens-recovery.md#clean-reflash-the-device)</span><span class="sxs-lookup"><span data-stu-id="9352e-224">Affected devices will need to be clean-reflashed by following the instructions on [reflashing their device](hololens-recovery.md#clean-reflash-the-device).</span></span>

[<span data-ttu-id="9352e-225">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="9352e-225">Back to list</span></span>](#list)

## <a name="autopilot-troubleshooting"></a><span data-ttu-id="9352e-226">Rozwiązywanie problemów z rozwiązaniem Autopilot</span><span class="sxs-lookup"><span data-stu-id="9352e-226">Autopilot Troubleshooting</span></span>

<span data-ttu-id="9352e-227">Następujące artykuły mogą być przydatnym zasobem, który pozwala uzyskać więcej informacji i rozwiązywać problemy z rozwiązaniem Autopilot, należy jednak pamiętać, że te artykuły są oparte na programie Windows 10 Desktop i nie wszystkie informacje mogą mieć zastosowanie do HoloLens:</span><span class="sxs-lookup"><span data-stu-id="9352e-227">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="9352e-228">Windows Autopilot — znane problemy</span><span class="sxs-lookup"><span data-stu-id="9352e-228">Windows Autopilot - known issues</span></span>](/mem/autopilot/known-issues)
- [<span data-ttu-id="9352e-229">Rozwiązywanie problemów dotyczących rejestrowania urządzeń z systemem Windows w usłudze Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="9352e-229">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="9352e-230">Windows Autopilot — konflikty zasad</span><span class="sxs-lookup"><span data-stu-id="9352e-230">Windows Autopilot - Policy Conflicts</span></span>](/mem/autopilot/policy-conflicts)

[<span data-ttu-id="9352e-231">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="9352e-231">Back to list</span></span>](#list)

## <a name="managed-hololens-devices-faqs"></a><span data-ttu-id="9352e-232">Często zadawane pytania HoloLens urządzeń zarządzanych</span><span class="sxs-lookup"><span data-stu-id="9352e-232">Managed HoloLens Devices FAQs</span></span>

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a><span data-ttu-id="9352e-233">Czy mogę używać System Center Configuration Manager (SCCM) do zarządzania HoloLens urządzeniami?</span><span class="sxs-lookup"><span data-stu-id="9352e-233">Can I use System Center Configuration Manager (SCCM) to manage HoloLens devices?</span></span>

<span data-ttu-id="9352e-234">Nie.</span><span class="sxs-lookup"><span data-stu-id="9352e-234">No.</span></span> <span data-ttu-id="9352e-235">Do zarządzania urządzeniami przenośnymi należy używać HoloLens MDM.</span><span class="sxs-lookup"><span data-stu-id="9352e-235">You have to use an MDM system to manage HoloLens devices.</span></span>

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a><span data-ttu-id="9352e-236">Czy mogę używać Active Directory Domain Services (AD DS) do zarządzania HoloLens kontami użytkowników?</span><span class="sxs-lookup"><span data-stu-id="9352e-236">Can I use Active Directory Domain Services (AD DS) to manage HoloLens user accounts?</span></span>

<span data-ttu-id="9352e-237">Nie.</span><span class="sxs-lookup"><span data-stu-id="9352e-237">No.</span></span> <span data-ttu-id="9352e-238">Aby zarządzać kontami użytkowników Azure Active Directory (Azure AD), należy użyć usługi HoloLens urządzeń.</span><span class="sxs-lookup"><span data-stu-id="9352e-238">You have to use Azure Active Directory (Azure AD) to manage user accounts for HoloLens devices.</span></span>

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a><span data-ttu-id="9352e-239">Czy HoloLens automatyczne rejestrowanie w systemach automatycznego przechwytywania danych (ADCS)?</span><span class="sxs-lookup"><span data-stu-id="9352e-239">Is HoloLens capable of Automated Data Capture Systems (ADCS) auto-enrollment?</span></span>

<span data-ttu-id="9352e-240">Nie.</span><span class="sxs-lookup"><span data-stu-id="9352e-240">No.</span></span>

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a><span data-ttu-id="9352e-241">Czy HoloLens uczestniczyć w zintegrowanym Windows uwierzytelniania?</span><span class="sxs-lookup"><span data-stu-id="9352e-241">Can HoloLens participate in Integrated Windows Authentication?</span></span>

<span data-ttu-id="9352e-242">Nie.</span><span class="sxs-lookup"><span data-stu-id="9352e-242">No.</span></span>

### <a name="does-hololens-support-branding"></a><span data-ttu-id="9352e-243">Czy HoloLens znakowanie?</span><span class="sxs-lookup"><span data-stu-id="9352e-243">Does HoloLens support branding?</span></span>

<span data-ttu-id="9352e-244">Nie.</span><span class="sxs-lookup"><span data-stu-id="9352e-244">No.</span></span> <span data-ttu-id="9352e-245">Ten problem można jednak ominić przy użyciu jednej z następujących metod:</span><span class="sxs-lookup"><span data-stu-id="9352e-245">However, you can work around this issue by using one of the following approaches:</span></span>

- <span data-ttu-id="9352e-246">Utwórz aplikację niestandardową, a następnie włącz [tryb kiosku.](hololens-kiosk.md)</span><span class="sxs-lookup"><span data-stu-id="9352e-246">Create a custom app, and then [enable Kiosk mode](hololens-kiosk.md).</span></span> <span data-ttu-id="9352e-247">Aplikacja niestandardowa może mieć znakowanie i może uruchamiać inne aplikacje (takie jak Remote Assist).</span><span class="sxs-lookup"><span data-stu-id="9352e-247">The custom app can have branding, and can launch other apps (such as Remote Assist).</span></span>  
- <span data-ttu-id="9352e-248">Zmień wszystkie obrazy profilu użytkownika w usłudze Azure AD na logo firmy.</span><span class="sxs-lookup"><span data-stu-id="9352e-248">Change all of the user profile pictures in Azure AD to your company logo.</span></span> <span data-ttu-id="9352e-249">Jednak może to nie być pożądane we wszystkich scenariuszach.</span><span class="sxs-lookup"><span data-stu-id="9352e-249">However, this may not be desirable for all scenarios.</span></span>

### <a name="what-logging-capabilities-does-hololens-2-offer"></a><span data-ttu-id="9352e-250">Jakie możliwości rejestrowania oferuje HoloLens 2?</span><span class="sxs-lookup"><span data-stu-id="9352e-250">What logging capabilities does HoloLens 2 offer?</span></span>

<span data-ttu-id="9352e-251">Rejestrowanie jest ograniczone do śladów, które mogą być przechwytywane w scenariuszach tworzenia lub rozwiązywania problemów, lub danych telemetrycznych, które urządzenia wysyłają do serwerów firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9352e-251">Logging is limited to traces that can be captured in development or troubleshooting scenarios, or telemetry that the devices send to Microsoft servers.</span></span>

## <a name="questions-about-securing-hololens-devices"></a><span data-ttu-id="9352e-252">Pytania dotyczące zabezpieczania urządzeń HoloLens sieciowych</span><span class="sxs-lookup"><span data-stu-id="9352e-252">Questions about securing HoloLens devices</span></span>

<span data-ttu-id="9352e-253">Zobacz [nasze HoloLens zabezpieczeń 2.](security-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9352e-253">See [our HoloLens 2 security information](security-overview.md).</span></span>
<span data-ttu-id="9352e-254">Aby HoloLens 1. generacji, zapoznaj się z często [zadawanymi pytaniami.](hololens1-faq-security.yml)</span><span class="sxs-lookup"><span data-stu-id="9352e-254">For HoloLens 1st Gen devices please review [this FAQ](hololens1-faq-security.yml).</span></span>

[<span data-ttu-id="9352e-255">Powrót do listy</span><span class="sxs-lookup"><span data-stu-id="9352e-255">Back to list</span></span>](#list)
