---
title: Niejawna wersja zapoznawcza dla Microsoft HoloLens
description: Dowiedz się, jak rozpocząć pracę z kompilacjami niejawnych testerów i przekazać cenną opinię na temat naszej następnej ważnej aktualizacji systemu operacyjnego na HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 87b606e634d4035da02802ddd1a8e1a980f1f1d6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636097"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="67ea8-103">Niejawna wersja zapoznawcza dla Microsoft HoloLens</span><span class="sxs-lookup"><span data-stu-id="67ea8-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="67ea8-104">Witamy w najnowszych kompilacjach insider preview dla HoloLens!</span><span class="sxs-lookup"><span data-stu-id="67ea8-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="67ea8-105">Łatwo jest rozpocząć pracę [i przekazać](hololens-insider.md#start-receiving-insider-builds) cenną opinię na temat naszej następnej ważnej aktualizacji systemu operacyjnego na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="67ea8-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="67ea8-106">Windows Informacje o wersji dla niejawnych testerów</span><span class="sxs-lookup"><span data-stu-id="67ea8-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="67ea8-107">Z przyjemnością zaczynamy ponownie testować nowe funkcje, aby Windows niejawnych testerów.</span><span class="sxs-lookup"><span data-stu-id="67ea8-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="67ea8-108">Nowe kompilacje będą dostępne w kanałach Dev i Beta, aby uzyskać najnowsze aktualizacje.</span><span class="sxs-lookup"><span data-stu-id="67ea8-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="67ea8-109">Będziemy aktualizować tę stronę w przypadku dodawania kolejnych funkcji i aktualizacji do naszych Windows niejawnych testerów.</span><span class="sxs-lookup"><span data-stu-id="67ea8-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="67ea8-110">Ekscytują i przygotują się do pomieszania tych aktualizacji ze swoją rzeczywistością.</span><span class="sxs-lookup"><span data-stu-id="67ea8-110">Get excited and ready to mix these updates into your reality.</span></span>

| <span data-ttu-id="67ea8-111">Cecha</span><span class="sxs-lookup"><span data-stu-id="67ea8-111">Feature</span></span>                 | <span data-ttu-id="67ea8-112">Opis</span><span class="sxs-lookup"><span data-stu-id="67ea8-112">Description</span></span>                | <span data-ttu-id="67ea8-113">Użytkownik lub scenariusz</span><span class="sxs-lookup"><span data-stu-id="67ea8-113">User or Scenario</span></span> | <span data-ttu-id="67ea8-114">Wprowadzono kompilację</span><span class="sxs-lookup"><span data-stu-id="67ea8-114">Build introduced</span></span> |
|-------------------------|----------------------------|--------------|------------------|
| [<span data-ttu-id="67ea8-115">Zmiany WSP dotyczące raportowania HoloLens szczegóły</span><span class="sxs-lookup"><span data-stu-id="67ea8-115">CSP changes for reporting HoloLens details</span></span>](#csp-changes-for-reporting-hololens-details) | <span data-ttu-id="67ea8-116">Nowi CSP dla programu do wykonywania zapytań o dane</span><span class="sxs-lookup"><span data-stu-id="67ea8-116">New CSPs for to query data</span></span> | <span data-ttu-id="67ea8-117">Administratorzy IT</span><span class="sxs-lookup"><span data-stu-id="67ea8-117">IT Admins</span></span>    | <span data-ttu-id="67ea8-118">20348.1403</span><span class="sxs-lookup"><span data-stu-id="67ea8-118">20348.1403</span></span>                 |
| [<span data-ttu-id="67ea8-119">Zasady automatycznego logowania kontrolowane przez zasady CSP</span><span class="sxs-lookup"><span data-stu-id="67ea8-119">Auto login policy controlled by CSP</span></span>](#auto-login-policy-controlled-by-csp) | <span data-ttu-id="67ea8-120">Używane do automatycznego logowania się do konta</span><span class="sxs-lookup"><span data-stu-id="67ea8-120">Used to log in an account automatically</span></span> | <span data-ttu-id="67ea8-121">Administratorzy IT</span><span class="sxs-lookup"><span data-stu-id="67ea8-121">IT Admins</span></span> | <span data-ttu-id="67ea8-122">20348.1405</span><span class="sxs-lookup"><span data-stu-id="67ea8-122">20348.1405</span></span> |
| [<span data-ttu-id="67ea8-123">Obsługa plików PFX dla Menedżera certyfikatów</span><span class="sxs-lookup"><span data-stu-id="67ea8-123">PFX file support for Certificate Manager</span></span>](#pfx-file-support-for-certificate-manager) | <span data-ttu-id="67ea8-124">Dodawanie certyfikatów PFX za pomocą interfejsu Ustawienia użytkownika</span><span class="sxs-lookup"><span data-stu-id="67ea8-124">Add PFX certs via Settings UI</span></span> | <span data-ttu-id="67ea8-125">Użytkownik końcowy</span><span class="sxs-lookup"><span data-stu-id="67ea8-125">End User</span></span> | <span data-ttu-id="67ea8-126">20348.1405</span><span class="sxs-lookup"><span data-stu-id="67ea8-126">20348.1405</span></span> |
| [<span data-ttu-id="67ea8-127">Wyświetlanie zaawansowanego raportu diagnostycznego w Ustawienia na HoloLens</span><span class="sxs-lookup"><span data-stu-id="67ea8-127">View advanced diagnostic report in Settings on HoloLens</span></span>](#view-advanced-diagnostic-report-in-settings-on-hololens) | <span data-ttu-id="67ea8-128">Wyświetlanie dzienników diagnostycznych mdm na urządzeniu</span><span class="sxs-lookup"><span data-stu-id="67ea8-128">View MDM diagnostic logs on device</span></span> | <span data-ttu-id="67ea8-129">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="67ea8-129">Troubleshooting</span></span> | <span data-ttu-id="67ea8-130">20348.1405</span><span class="sxs-lookup"><span data-stu-id="67ea8-130">20348.1405</span></span> |
| [<span data-ttu-id="67ea8-131">Powiadomienia diagnostyki w trybie offline</span><span class="sxs-lookup"><span data-stu-id="67ea8-131">Offline Diagnostics notifications</span></span>](#offline-diagnostics-notifications) | <span data-ttu-id="67ea8-132">Opinie dotyczące zbierania dzienników</span><span class="sxs-lookup"><span data-stu-id="67ea8-132">Audiovisual feedback for log collection</span></span> | <span data-ttu-id="67ea8-133">Rozwiązywanie problemów</span><span class="sxs-lookup"><span data-stu-id="67ea8-133">Troubleshooting</span></span> | <span data-ttu-id="67ea8-134">20348.1405</span><span class="sxs-lookup"><span data-stu-id="67ea8-134">20348.1405</span></span> |


### <a name="csp-changes-for-reporting-hololens-details"></a><span data-ttu-id="67ea8-135">Zmiany WSP dotyczące raportowania HoloLens szczegóły</span><span class="sxs-lookup"><span data-stu-id="67ea8-135">CSP changes for reporting HoloLens details</span></span>

- <span data-ttu-id="67ea8-136">Wprowadzono w kompilacji Windows Insider, 20348.1403</span><span class="sxs-lookup"><span data-stu-id="67ea8-136">Introduced in Windows Insider build, 20348.1403</span></span>

<span data-ttu-id="67ea8-137">Następujący CSP zostały zaktualizowane o nowe sposoby zgłaszania informacji z HoloLens urządzeń.</span><span class="sxs-lookup"><span data-stu-id="67ea8-137">The following CSPs have been updated with new ways to report information from your HoloLens devices.</span></span>

#### <a name="devdetail-csp---free-storage"></a><span data-ttu-id="67ea8-138">DevDetail CSP — bezpłatne Storage</span><span class="sxs-lookup"><span data-stu-id="67ea8-138">DevDetail CSP - Free Storage</span></span>

<span data-ttu-id="67ea8-139">DevDetail CSP now also reports free storage space on HoloLens device.</span><span class="sxs-lookup"><span data-stu-id="67ea8-139">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="67ea8-140">Powinno to być w przybliżeniu zgodne z wartością wyświetlaną na Ustawienia aplikacji Storage aplikacji.</span><span class="sxs-lookup"><span data-stu-id="67ea8-140">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="67ea8-141">Poniżej znajduje się konkretny węzeł zawierający te informacje.</span><span class="sxs-lookup"><span data-stu-id="67ea8-141">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="67ea8-142">./DevDetail/Ext/Microsoft/FreeStorage (tylko operacja GET)</span><span class="sxs-lookup"><span data-stu-id="67ea8-142">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp---ssid-and-bssid"></a><span data-ttu-id="67ea8-143">DeviceStatus CSP — SSID i BSSID</span><span class="sxs-lookup"><span data-stu-id="67ea8-143">DeviceStatus CSP - SSID and BSSID</span></span>

<span data-ttu-id="67ea8-144">DeviceStatus CSP teraz raporty SSID i BSSID Wi-Fi sieci, z którą HoloLens jest aktywnie połączony.</span><span class="sxs-lookup"><span data-stu-id="67ea8-144">DeviceStatus CSP now also reports SSID and BSSID of Wi-Fi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="67ea8-145">Poniżej przedstawiono określone węzły zawierające te informacje.</span><span class="sxs-lookup"><span data-stu-id="67ea8-145">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="67ea8-146">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*adres mac* karty Wi-Fi /SSID</span><span class="sxs-lookup"><span data-stu-id="67ea8-146">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="67ea8-147">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*adres mac* karty Wi-Fi /BSSID</span><span class="sxs-lookup"><span data-stu-id="67ea8-147">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="67ea8-148">Przykładowy obiekt blob syncml (dla dostawców mdm) do wykonywania zapytań o identyfikatory sieci</span><span class="sxs-lookup"><span data-stu-id="67ea8-148">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a><span data-ttu-id="67ea8-149">Zasady automatycznego logowania kontrolowane przez zasady CSP</span><span class="sxs-lookup"><span data-stu-id="67ea8-149">Auto login policy controlled by CSP</span></span>

<span data-ttu-id="67ea8-150">Ta nowa zasada AutoLogonUser określa, czy użytkownik będzie automatycznie zalogowany.</span><span class="sxs-lookup"><span data-stu-id="67ea8-150">This new AutoLogonUser policy controls whether a user will be automatically logged on.</span></span> <span data-ttu-id="67ea8-151">Niektórzy klienci chcą skonfigurować urządzenia, które są powiązane z tożsamością, ale nie chcą mieć żadnego logowania.</span><span class="sxs-lookup"><span data-stu-id="67ea8-151">Some customers want to set up devices that are tied to an identity but don't want any sign-in experience.</span></span> <span data-ttu-id="67ea8-152">Imagine urządzenie i natychmiast korzystać ze zdalnej pomocy.</span><span class="sxs-lookup"><span data-stu-id="67ea8-152">Imagine picking up a device and using remote assist immediately.</span></span> <span data-ttu-id="67ea8-153">Możesz też skorzystać z możliwości szybkiej dystrybucji urządzeń HoloLens i umożliwienia użytkownikom końcowi przyspieszenia logowania.</span><span class="sxs-lookup"><span data-stu-id="67ea8-153">Or have a benefit of being able to rapidly  distribute HoloLens devices and enable their end users to expedite login.</span></span>

<span data-ttu-id="67ea8-154">Gdy zasady są ustawione na wartość niepustą, określają adres e-mail użytkownika logowania automatycznego.</span><span class="sxs-lookup"><span data-stu-id="67ea8-154">When the policy is set to a non-empty value, it specifies the email address of the auto-logon user.</span></span> <span data-ttu-id="67ea8-155">Określony użytkownik musi logować się na urządzeniu co najmniej raz, aby włączyć automatyczne logowanie.</span><span class="sxs-lookup"><span data-stu-id="67ea8-155">The specified user must logon to the device at least once to enable auto-logon.</span></span>

<span data-ttu-id="67ea8-156">OMA-URI wartości ciągu `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` nowych zasad</span><span class="sxs-lookup"><span data-stu-id="67ea8-156">The OMA-URI of new policy `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` String value</span></span>

- <span data-ttu-id="67ea8-157">Użytkownik z tym samym adresem e-mail będzie mieć włączone automatyczne logowanie.</span><span class="sxs-lookup"><span data-stu-id="67ea8-157">User with the same email address will have auto logon enabled.</span></span>

<span data-ttu-id="67ea8-158">Na urządzeniu, na którym te zasady są skonfigurowane, użytkownik określony w zasadach musi się logować co najmniej raz.</span><span class="sxs-lookup"><span data-stu-id="67ea8-158">On a device where this policy is configured, the user specified in the policy will need to logon at least once.</span></span> <span data-ttu-id="67ea8-159">Kolejne ponowne uruchomienie urządzenia po pierwszym zalogowaniu spowoduje automatyczne zalogowanie określonego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="67ea8-159">Subsequent reboots of the device after the first logon will have the specified user automatically logged on.</span></span> <span data-ttu-id="67ea8-160">Obsługiwany jest tylko jeden użytkownik z automatycznym logowaniem.</span><span class="sxs-lookup"><span data-stu-id="67ea8-160">Only a single auto-logon user is supported.</span></span> <span data-ttu-id="67ea8-161">Po włączeniu automatycznie zalogowany użytkownik nie będzie mógł wylogować się ręcznie.</span><span class="sxs-lookup"><span data-stu-id="67ea8-161">Once enabled, the automatically logged on user will not be able to log out manually.</span></span> <span data-ttu-id="67ea8-162">Aby logować się jako inny użytkownik, należy najpierw wyłączyć zasady.</span><span class="sxs-lookup"><span data-stu-id="67ea8-162">To logon as a different user, the policy must first be disabled.</span></span>

> [!NOTE]
> - <span data-ttu-id="67ea8-163">Niektóre zdarzenia, takie jak główne aktualizacje systemu operacyjnego, mogą wymagać od określonego użytkownika ponownego zalogowania się na urządzeniu w celu wznowienia zachowania automatycznego logowania.</span><span class="sxs-lookup"><span data-stu-id="67ea8-163">Some events such as major OS updates may require the specified user to logon to the device again to resume auto-logon behavior.</span></span> 
> - <span data-ttu-id="67ea8-164">Automatyczne logowanie jest obsługiwane tylko dla użytkowników msa i usługi AAD.</span><span class="sxs-lookup"><span data-stu-id="67ea8-164">Auto-logon is only supported for MSA and AAD users.</span></span>

### <a name="pfx-file-support-for-certificate-manager"></a><span data-ttu-id="67ea8-165">Obsługa plików PFX dla Menedżera certyfikatów</span><span class="sxs-lookup"><span data-stu-id="67ea8-165">PFX file support for Certificate Manager</span></span>

<span data-ttu-id="67ea8-166">Wprowadzono w kompilacji Windows Insider 20348.1405.</span><span class="sxs-lookup"><span data-stu-id="67ea8-166">Introduced in Windows Insider build 20348.1405.</span></span> <span data-ttu-id="67ea8-167">Dodaliśmy obsługę Menedżera [](certificate-manager.md) certyfikatów, aby teraz używać certyfikatów pfx.</span><span class="sxs-lookup"><span data-stu-id="67ea8-167">We’ve added support to the [Certificate Manager](certificate-manager.md) to now use .pfx certificates.</span></span> <span data-ttu-id="67ea8-168">Gdy użytkownicy przejdą do **Ustawienia** zaktualizują & certyfikatów zabezpieczeń, a następnie wybierzą pozycję Zainstaluj certyfikat, interfejs użytkownika obsługuje teraz  >    >  plik certyfikatu pfx. </span><span class="sxs-lookup"><span data-stu-id="67ea8-168">When users navigate to **Settings** > **Update & Security** > **Certificates**, and select **Install a certificate** the UI now supports .pfx certificate file.</span></span>
<span data-ttu-id="67ea8-169">Użytkownicy mogą importować certyfikat PFX z kluczem prywatnym do magazynu użytkowników lub magazynu maszyn.</span><span class="sxs-lookup"><span data-stu-id="67ea8-169">Users can import .pfx certificate, with private key, to user store or machine store.</span></span>

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a><span data-ttu-id="67ea8-170">Wyświetlanie zaawansowanego raportu diagnostycznego w Ustawienia na HoloLens</span><span class="sxs-lookup"><span data-stu-id="67ea8-170">View advanced diagnostic report in Settings on HoloLens</span></span>

<span data-ttu-id="67ea8-171">W przypadku urządzeń zarządzanych podczas rozwiązywania problemów z zachowaniem ważnym krokiem jest potwierdzenie zastosowania oczekiwanej konfiguracji zasad.</span><span class="sxs-lookup"><span data-stu-id="67ea8-171">For managed devices when troubleshooting behavior, confirming that an expected policy configuration is applied is an important step.</span></span> <span data-ttu-id="67ea8-172">Wcześniej ta nowa funkcja musiała zostać wyłączona za pośrednictwem rozwiązania MDM lub w pobliżu urządzenia po wyeksportowaniu dzienników diagnostycznych MDM zebranych za pośrednictwem konta **usługi Ustawienia** Dostęp do miejsca pracy lub nauki, a następnie wybierz pozycję Eksportuj dzienniki zarządzania i wyświetl je na pobliskim  ->    >  komputerze. </span><span class="sxs-lookup"><span data-stu-id="67ea8-172">Previously to this new feature, this had to be done off device via MDM or near the device after exporting MDM diagnostic logs gathered via **Settings** -> **Accounts** > **Access work or school**, and select **Export your management logs** and viewed on a nearby PC.</span></span>

<span data-ttu-id="67ea8-173">Teraz diagnostykę MDM można wyświetlić na urządzeniu przy użyciu przeglądarki Edge.</span><span class="sxs-lookup"><span data-stu-id="67ea8-173">Now the MDM Diagnostics can be viewed on device using the Edge browser.</span></span> <span data-ttu-id="67ea8-174">Aby łatwiej wyświetlić raport diagnostyczny MDM, przejdź do strony Dostęp do konta służbowego i wybierz pozycję **Wyświetl zaawansowany raport diagnostyczny.**</span><span class="sxs-lookup"><span data-stu-id="67ea8-174">To more easily view the MDM Diagnostic report navigate to the Access work or school page, and select **View advanced diagnostic report**.</span></span> <span data-ttu-id="67ea8-175">Spowoduje to wygenerowanie i otwarcie raportu w nowym oknie przeglądarki Edge.</span><span class="sxs-lookup"><span data-stu-id="67ea8-175">This will generate and open the report in a new Edge window.</span></span>

![Wyświetlanie zaawansowanego raportu diagnostycznego Ustawienia aplikacji.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a><span data-ttu-id="67ea8-177">Powiadomienia diagnostyki w trybie offline</span><span class="sxs-lookup"><span data-stu-id="67ea8-177">Offline Diagnostics notifications</span></span>

<span data-ttu-id="67ea8-178">Jest to aktualizacja istniejącej funkcji o nazwie [Diagnostyka w trybie offline.](hololens-diagnostic-logs.md#offline-diagnostics)</span><span class="sxs-lookup"><span data-stu-id="67ea8-178">This an update for an existing feature called [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span></span> <span data-ttu-id="67ea8-179">Wcześniej nie było jasnego wskaźnika dla użytkowników, że wyzwolili kolekcję diagnostyczną lub została ona zakończona.</span><span class="sxs-lookup"><span data-stu-id="67ea8-179">Previously, there was no clear indicator to users that they had triggered diagnostic collection or it had completed.</span></span>
<span data-ttu-id="67ea8-180">Teraz dodano Windows kompilacji niejawnych testerów, istnieją dwie formy informacji zwrotnych dla diagnostyki w trybie offline.</span><span class="sxs-lookup"><span data-stu-id="67ea8-180">Now added in Windows Insider builds, there are two forms of audiovisual feedback for Offline Diagnostics.</span></span> <span data-ttu-id="67ea8-181">Pierwsze to wyskakujące powiadomienia wyświetlane zarówno podczas uruchamiania, jak i zakończenia zbierania.</span><span class="sxs-lookup"><span data-stu-id="67ea8-181">The first being toasts notifications displayed for both when collection starts and completes.</span></span> <span data-ttu-id="67ea8-182">Będą one wyświetlane, gdy użytkownik jest zalogowany i ma wizualizacje.</span><span class="sxs-lookup"><span data-stu-id="67ea8-182">These will be displayed when the user is logged in and has visuals.</span></span>

![Wyskakujące powiadomienia dotyczące zbierania dzienników.](./images/logcollection1.jpg)

![Wyskakujące powiadomienia po zakończeniu zbierania dzienników.](./images/logcollection2.jpg)
 
<span data-ttu-id="67ea8-185">Ponieważ użytkownicy często używają diagnostyki offline jako mechanizmu rezerwowego zbierania dzienników, gdy nie mają dostępu do ekranu, nie mogą się zalogować lub nadal znajdują się w trybie OOBE, podczas zbierania dzienników będzie również odtwarzany sygnał dźwiękowy.</span><span class="sxs-lookup"><span data-stu-id="67ea8-185">Because users often use Offline Diagnostics as a fallback log gathering mechanism for when they don’t have access to a display, can’t log-in or are still in OOBE there will also be an audio cue played when logs are gathered.</span></span> <span data-ttu-id="67ea8-186">Ten dźwięk będzie odtwarzany oprócz powiadomienia wyskakującego.</span><span class="sxs-lookup"><span data-stu-id="67ea8-186">This sound will be played in addition to the toast notification.</span></span>

<span data-ttu-id="67ea8-187">Ta nowa funkcja zostanie włączona podczas aktualizacji urządzenia i nie trzeba jej włączać ani zarządzać.</span><span class="sxs-lookup"><span data-stu-id="67ea8-187">This new feature will be enabled when your device updates, and doesn’t need to be enabled or managed.</span></span> <span data-ttu-id="67ea8-188">W przypadku, gdy nie będzie można wyświetlić ani słyszeć tej nowej opinii, diagnostyka w trybie offline będzie nadal generowana.</span><span class="sxs-lookup"><span data-stu-id="67ea8-188">In any event that this new feedback cannot be displayed or heard, Offline Diagnostics will still be generated.</span></span>

<span data-ttu-id="67ea8-189">Mamy nadzieję, że dzięki temu nowszej dodatku opinii zwrotnej łatwiej jest zbierać dane diagnostyczne i szybciej rozwiązywać problemy.</span><span class="sxs-lookup"><span data-stu-id="67ea8-189">We hope with this newer addition of audiovisual feedback it is easier to gather diagnostic data, and more quickly be able to troubleshoot your problems.</span></span>



### <a name="fixes-and-improvements"></a><span data-ttu-id="67ea8-190">Poprawki i ulepszenia:</span><span class="sxs-lookup"><span data-stu-id="67ea8-190">Fixes and improvements:</span></span>

- <span data-ttu-id="67ea8-191">Rozwiązano znany problem z Portal urządzeń, który nie wyświetlał monitu [o pobranie zablokowanych plików.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="67ea8-191">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="67ea8-192">Rozwiązano [znany problem z Portal urządzeń podczas przekazywania i pobierania.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="67ea8-192">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>


## <a name="start-receiving-insider-builds"></a><span data-ttu-id="67ea8-193">Rozpoczynanie otrzymywania kompilacji niejawnych testerów</span><span class="sxs-lookup"><span data-stu-id="67ea8-193">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="67ea8-194">Jeśli ostatnio nie zaktualizowano, uruchom ponownie urządzenie, aby zaktualizować stan i pobrać najnowszą kompilację.</span><span class="sxs-lookup"><span data-stu-id="67ea8-194">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="67ea8-195">Polecenie głosowe "Reboot device" (Uruchom ponownie urządzenie) działa dobrze.</span><span class="sxs-lookup"><span data-stu-id="67ea8-195">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="67ea8-196">Możesz również wybrać przycisk ponownego uruchamiania w Ustawienia/Windows niejawny program testów.</span><span class="sxs-lookup"><span data-stu-id="67ea8-196">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="67ea8-197">Na zadurze wystąpiła usterka, która może spowodować powrót na tory.</span><span class="sxs-lookup"><span data-stu-id="67ea8-197">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="67ea8-198">Na urządzeniu HoloLens 2 przejdź do Ustawienia  >  **Update & Security**  >  **Windows niejawny program testów** i wybierz pozycję **Wprowadzenie.**</span><span class="sxs-lookup"><span data-stu-id="67ea8-198">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="67ea8-199">Połącz konto użyte do zarejestrowania się jako Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="67ea8-199">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="67ea8-200">Windows niejawny tester jest teraz przenoszący się do kanałów.</span><span class="sxs-lookup"><span data-stu-id="67ea8-200">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="67ea8-201">Szybki **pierścień** stanie się kanałem **dewelopera,** pierścień Wolny stanie  się **kanał beta,** a pierścień wersji zapoznawczej zostanie kanałem wersji  **zapoznawczej.**</span><span class="sxs-lookup"><span data-stu-id="67ea8-201">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="67ea8-202">Oto jak wygląda to mapowanie:</span><span class="sxs-lookup"><span data-stu-id="67ea8-202">Here is what that mapping looks like:</span></span>

![Windows Wyjaśnienie kanałów niejawnych testerów](images/WindowsInsiderChannels.png)

<span data-ttu-id="67ea8-204">Aby uzyskać więcej informacji, zobacz Introducing Windows Insider Channels (Wprowadzenie do [kanałów niejawnych testerów)](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) Windows Blogi.</span><span class="sxs-lookup"><span data-stu-id="67ea8-204">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="67ea8-205">Następnie wybierz **pozycję Active development of Windows**, wybierz, czy chcesz otrzymywać kanał **dewelopera,** czy kanał beta kompilacje, i przejrzyj warunki programu. </span><span class="sxs-lookup"><span data-stu-id="67ea8-205">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="67ea8-206">Wybierz **pozycję > uruchom ponownie teraz,** aby zakończyć.</span><span class="sxs-lookup"><span data-stu-id="67ea8-206">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="67ea8-207">Po ponownym uruchomieniu urządzenia przejdź do Ustawienia > **Update & Security > Sprawdź** aktualizacje, aby pobrać najnowszą kompilację.</span><span class="sxs-lookup"><span data-stu-id="67ea8-207">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="67ea8-208">Błąd aktualizacji 0x80070490 omięcie</span><span class="sxs-lookup"><span data-stu-id="67ea8-208">Update error 0x80070490 work-around</span></span>

<span data-ttu-id="67ea8-209">Jeśli wystąpi błąd aktualizacji 0x80070490 podczas aktualizowania w kanale dewelopera lub wersji beta, spróbuj wykonać następujące krótkoterminowe czynności.</span><span class="sxs-lookup"><span data-stu-id="67ea8-209">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="67ea8-210">Obejmuje to przeniesienie kanału niejawnego testera, pobranie aktualizacji, a następnie przeniesienie kanału niejawnego testera z powrotem.</span><span class="sxs-lookup"><span data-stu-id="67ea8-210">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>

#### <a name="stage-one---release-preview"></a><span data-ttu-id="67ea8-211">Etap pierwszy — wersja zapoznawcza</span><span class="sxs-lookup"><span data-stu-id="67ea8-211">Stage one - Release Preview</span></span>

1.  <span data-ttu-id="67ea8-212">Ustawienia, Zaktualizuj zabezpieczenia &, Windows niejawny program testów wybierz pozycję **Kanał wersji zapoznawczej.**</span><span class="sxs-lookup"><span data-stu-id="67ea8-212">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>

2.  <span data-ttu-id="67ea8-213">Ustawienia, Update & Security, Windows Update, **Check for updates**.</span><span class="sxs-lookup"><span data-stu-id="67ea8-213">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="67ea8-214">Po aktualizacji przejdź do etapu 2.</span><span class="sxs-lookup"><span data-stu-id="67ea8-214">After the update, continue on to Stage two.</span></span>

#### <a name="stage-two---dev-channel"></a><span data-ttu-id="67ea8-215">Etap drugi — kanał dewelopera</span><span class="sxs-lookup"><span data-stu-id="67ea8-215">Stage two - Dev Channel</span></span>

1. <span data-ttu-id="67ea8-216">Ustawienia, Zaktualizuj & Security, Windows niejawny program testów wybierz pozycję **Kanał deweloperów.**</span><span class="sxs-lookup"><span data-stu-id="67ea8-216">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>

2. <span data-ttu-id="67ea8-217">Ustawienia, Update & Security, Windows Update, **Check for updates**.</span><span class="sxs-lookup"><span data-stu-id="67ea8-217">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>

## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="67ea8-218">Wskazówki dotyczące pobierania i flasha z użyciem ffu</span><span class="sxs-lookup"><span data-stu-id="67ea8-218">FFU download and flash directions</span></span>

<span data-ttu-id="67ea8-219">Aby przetestować przy użyciu podpisanego lotu ffu, musisz najpierw odblokować urządzenie przed flashingiem podpisanego lotu ffu.</span><span class="sxs-lookup"><span data-stu-id="67ea8-219">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>

1. <span data-ttu-id="67ea8-220">Na komputerze:</span><span class="sxs-lookup"><span data-stu-id="67ea8-220">On PC:</span></span>
    1. <span data-ttu-id="67ea8-221">Pobierz ffu na komputer ze strony [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .</span><span class="sxs-lookup"><span data-stu-id="67ea8-221">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="67ea8-222">Zainstaluj program ARC (Advanced Recovery Companion) z Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .</span><span class="sxs-lookup"><span data-stu-id="67ea8-222">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="67ea8-223">Na HoloLens — Flight Unlock: **otwórz** Ustawienia  >  **Update & Security**  >  **Windows niejawny program testów** następnie zarejestruj się i uruchom ponownie urządzenie.</span><span class="sxs-lookup"><span data-stu-id="67ea8-223">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="67ea8-224">Flash FFU — teraz możesz flashowane ffu z podpisem lotu przy użyciu usługi ARC.</span><span class="sxs-lookup"><span data-stu-id="67ea8-224">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="67ea8-225">Zgłaszanie opinii i zgłaszanie problemów</span><span class="sxs-lookup"><span data-stu-id="67ea8-225">Provide feedback and report issues</span></span>

<span data-ttu-id="67ea8-226">Użyj aplikacji [Centrum opinii na swoim](hololens-feedback.md) HoloLens, aby przekazać opinię i zgłosić problemy.</span><span class="sxs-lookup"><span data-stu-id="67ea8-226">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="67ea8-227">Użycie Centrum opinii zapewnia, że wszystkie niezbędne informacje diagnostyczne są uwzględniane, aby pomóc naszym inżynierom szybko debugować i rozwiązywać problem.</span><span class="sxs-lookup"><span data-stu-id="67ea8-227">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="67ea8-228">Problemy z chińskim i japońskim wersją HoloLens powinny być zgłaszane w ten sam sposób.</span><span class="sxs-lookup"><span data-stu-id="67ea8-228">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="67ea8-229">Pamiętaj, aby zaakceptować monit z pytaniem, czy chcesz uzyskać Centrum opinii  dostęp do folderu Dokumenty (po wyświetleniu monitu wybierz pozycję Tak).</span><span class="sxs-lookup"><span data-stu-id="67ea8-229">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <a name="note-for-developers"></a><span data-ttu-id="67ea8-230">Uwaga dla deweloperów</span><span class="sxs-lookup"><span data-stu-id="67ea8-230">Note for developers</span></span>

<span data-ttu-id="67ea8-231">Zachęcamy i zachęcamy do wypróbowania tworzenia aplikacji przy użyciu kompilacji niejawnych testerów HoloLens.</span><span class="sxs-lookup"><span data-stu-id="67ea8-231">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="67ea8-232">Zapoznaj się z [dokumentacją HoloLens Developer,](https://developer.microsoft.com/windows/mixed-reality/development) aby rozpocząć pracę.</span><span class="sxs-lookup"><span data-stu-id="67ea8-232">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="67ea8-233">Te same instrukcje działają z kompilacjami niejawnych testerów HoloLens.</span><span class="sxs-lookup"><span data-stu-id="67ea8-233">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="67ea8-234">Możesz użyć tych samych kompilacji aparatu Unity i Visual Studio, których już używasz do HoloLens tworzenia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="67ea8-234">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="67ea8-235">Zatrzymywanie odbierania kompilacji niejawnych testerów</span><span class="sxs-lookup"><span data-stu-id="67ea8-235">Stop receiving Insider builds</span></span>

<span data-ttu-id="67ea8-236">Jeśli nie chcesz już otrzymywać kompilacji systemu Windows Holographic dla niejawnych testerów, możesz zrezygnować z używania kompilacji produkcyjnej na platformie HoloLens lub odzyskać urządzenie za pomocą narzędzia Advanced Recovery Companion, aby odzyskać urządzenie do wersji systemu Windows Holographic, która nie jest niejawnym testerem. [](hololens-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="67ea8-236">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="67ea8-237">Istnieje znany problem, w którym użytkownicy, którzy wyrejestrować się z kompilacji insider preview po ręcznej ponownej instalacji nowej kompilacji w wersji zapoznawczej, zobaczą niebieski ekran.</span><span class="sxs-lookup"><span data-stu-id="67ea8-237">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="67ea8-238">Następnie muszą ręcznie odzyskać urządzenie.</span><span class="sxs-lookup"><span data-stu-id="67ea8-238">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="67ea8-239">Aby uzyskać szczegółowe informacje na temat tego, czy problem może mieć wpływ, zobacz więcej informacji na temat tego [znanego problemu.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)</span><span class="sxs-lookup"><span data-stu-id="67ea8-239">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>

<span data-ttu-id="67ea8-240">Aby sprawdzić, czy HoloLens jest uruchomiona kompilacja produkcyjna:</span><span class="sxs-lookup"><span data-stu-id="67ea8-240">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="67ea8-241">Przejdź do **Ustawienia > System > informacje** i znajdź numer kompilacji.</span><span class="sxs-lookup"><span data-stu-id="67ea8-241">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="67ea8-242">[Zobacz informacje o wersji, aby uzyskać numery kompilacji produkcyjnej.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="67ea8-242">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="67ea8-243">Aby zrezygnować z kompilacji niejawnych testerów:</span><span class="sxs-lookup"><span data-stu-id="67ea8-243">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="67ea8-244">W przypadku HoloLens kompilacji produkcyjnej przejdź do usługi **Ustawienia > Update & Security > Windows niejawny program testów** i wybierz pozycję Zatrzymaj kompilacje niejawnych **testerów.**</span><span class="sxs-lookup"><span data-stu-id="67ea8-244">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="67ea8-245">Postępuj zgodnie z instrukcjami, aby zrezygnować z urządzenia.</span><span class="sxs-lookup"><span data-stu-id="67ea8-245">Follow the instructions to opt out your device.</span></span>
