---
title: Wytyczne dotyczące infrastruktury dla HoloLens
description: Poznaj wytyczne dotyczące infrastruktury dla urządzeń HoloLens, w tym obsługę sieci bezprzewodowej, pomoc zdalną i zarządzanie urządzeniami przenośnymi.
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e3f87c524ce0f8af05ec8c92877d46facd962fb4
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639288"
---
# <a name="configure-your-network-for-hololens"></a><span data-ttu-id="b9a0d-103">Konfigurowanie sieci na HoloLens</span><span class="sxs-lookup"><span data-stu-id="b9a0d-103">Configure Your Network for HoloLens</span></span>

<span data-ttu-id="b9a0d-104">Ta część dokumentu będzie wymagać następujących osób:</span><span class="sxs-lookup"><span data-stu-id="b9a0d-104">This portion of the document will require the following people:</span></span>

1. <span data-ttu-id="b9a0d-105">Administrator sieci z uprawnieniami do zmieniania serwera proxy/zapory</span><span class="sxs-lookup"><span data-stu-id="b9a0d-105">Network Admin with permissions to make changes to the proxy/firewall</span></span>
2. <span data-ttu-id="b9a0d-106">Azure Active Directory Admin</span><span class="sxs-lookup"><span data-stu-id="b9a0d-106">Azure Active Directory Admin</span></span>
3. <span data-ttu-id="b9a0d-107">Administrator Menedżer urządzeń urządzeń przenośnych</span><span class="sxs-lookup"><span data-stu-id="b9a0d-107">Mobile Device Manager Admin</span></span>

## <a name="infrastructure-requirements"></a><span data-ttu-id="b9a0d-108">Wymagania dotyczące infrastruktury</span><span class="sxs-lookup"><span data-stu-id="b9a0d-108">Infrastructure Requirements</span></span>

<span data-ttu-id="b9a0d-109">HoloLens to podstawowe urządzenie przenośne zintegrowane Windows platformą Azure.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-109">HoloLens is, at its core, a Windows mobile device integrated with Azure.</span></span>  <span data-ttu-id="b9a0d-110">Najlepiej sprawdza się w środowiskach komercyjnych z dostępnością sieci bezprzewodowej (Wi-Fi) i dostępem do usługi firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-110">It works best in commercial environments with wireless network availability (wi-fi) and access to Microsoft services.</span></span>

<span data-ttu-id="b9a0d-111">Krytyczne usługi w chmurze obejmują:</span><span class="sxs-lookup"><span data-stu-id="b9a0d-111">Critical cloud services include:</span></span>

- <span data-ttu-id="b9a0d-112">Azure active directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="b9a0d-112">Azure active directory (Azure AD)</span></span>
- <span data-ttu-id="b9a0d-113">Windows Aktualizacja (WU)</span><span class="sxs-lookup"><span data-stu-id="b9a0d-113">Windows Update (WU)</span></span>

<span data-ttu-id="b9a0d-114">Klienci komercyjni będą potrzebować infrastruktury zarządzania mobilnością w przedsiębiorstwie (EMM) lub zarządzania urządzeniami przenośnymi (MDM) w celu zarządzania HoloLens urządzeniami przenośnymi na dużą skalę.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-114">Commercial customers will need enterprise mobility management (EMM) or mobile device management (MDM) infrastructure to manage HoloLens devices at scale.</span></span>  <span data-ttu-id="b9a0d-115">W tym [przewodniku Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) jako przykład, chociaż każdy dostawca z pełną obsługą zasad firmy Microsoft może obsługiwać HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-115">This guide uses [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) as an example, though any provider with full support for Microsoft Policy can support HoloLens.</span></span>  <span data-ttu-id="b9a0d-116">Zapytaj dostawcę zarządzania urządzeniami przenośnymi, czy obsługuje HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-116">Ask your mobile device management provider if they support HoloLens 2.</span></span>

<span data-ttu-id="b9a0d-117">HoloLens obsługuje ograniczony zestaw odłączonych od chmury możliwości.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-117">HoloLens does support a limited set of cloud disconnected experiences.</span></span>

### <a name="wireless-network-eap-support"></a><span data-ttu-id="b9a0d-118">Obsługa protokołu EAP sieci bezprzewodowej</span><span class="sxs-lookup"><span data-stu-id="b9a0d-118">Wireless network EAP support</span></span>

- <span data-ttu-id="b9a0d-119">PEAP-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="b9a0d-119">PEAP-MS-CHAPv2</span></span>
- <span data-ttu-id="b9a0d-120">PEAP-TLS</span><span class="sxs-lookup"><span data-stu-id="b9a0d-120">PEAP-TLS</span></span>
- <span data-ttu-id="b9a0d-121">TLS</span><span class="sxs-lookup"><span data-stu-id="b9a0d-121">TLS</span></span>
- <span data-ttu-id="b9a0d-122">TTLS-CHAP</span><span class="sxs-lookup"><span data-stu-id="b9a0d-122">TTLS-CHAP</span></span>
- <span data-ttu-id="b9a0d-123">TTLS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="b9a0d-123">TTLS-CHAPv2</span></span>
- <span data-ttu-id="b9a0d-124">TTLS-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="b9a0d-124">TTLS-MS-CHAPv2</span></span>
- <span data-ttu-id="b9a0d-125">TTLS-PAP</span><span class="sxs-lookup"><span data-stu-id="b9a0d-125">TTLS-PAP</span></span>
- <span data-ttu-id="b9a0d-126">TTLS-TLS</span><span class="sxs-lookup"><span data-stu-id="b9a0d-126">TTLS-TLS</span></span>

### <a name="hololens-specific-network-requirements"></a><span data-ttu-id="b9a0d-127">HoloLens Określone wymagania dotyczące sieci</span><span class="sxs-lookup"><span data-stu-id="b9a0d-127">HoloLens Specific Network Requirements</span></span>

<span data-ttu-id="b9a0d-128">Upewnij się, [że ta lista](hololens-offline.md) punktów końcowych jest dozwolona w zaporze sieciowej.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-128">Make sure that [this list](hololens-offline.md) of endpoints are allowed on your network firewall.</span></span> <span data-ttu-id="b9a0d-129">Umożliwi to prawidłowe HoloLens funkcji.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-129">This will enable HoloLens to function properly.</span></span>

### <a name="remote-assist-specific-network-requirements"></a><span data-ttu-id="b9a0d-130">Wymagania dotyczące sieci z określoną usługą Remote Assist</span><span class="sxs-lookup"><span data-stu-id="b9a0d-130">Remote Assist Specific Network Requirements</span></span>

1. <span data-ttu-id="b9a0d-131">Zalecana przepustowość dla optymalnej wydajności usługi Remote Assist to 1,5 Mb/s.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-131">The recommended bandwidth for optimal performance of Remote Assist is 1.5Mbps.</span></span> <span data-ttu-id="b9a0d-132">Aby uzyskać [dodatkowe informacje, zobacz](/MicrosoftTeams/prepare-network) szczegółowe wymagania dotyczące sieci.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-132">See the [detailed network requirements](/MicrosoftTeams/prepare-network) for additional information.</span></span>
<span data-ttu-id="b9a0d-133">**(Pamiętaj, że jeśli nie masz szybkości sieci co najmniej 1,5 Mb/s, usługa Remote Assist nadal będzie działać. Jednak jakość może ulec zaochłoce).**</span><span class="sxs-lookup"><span data-stu-id="b9a0d-133">**(Please note, if you don't network have network speeds of at least 1.5Mbps, Remote Assist will still work. However, quality may suffer).**</span></span>
1. <span data-ttu-id="b9a0d-134">Upewnij się, że te porty i adresy URL są dozwolone w zaporze sieciowej, aby umożliwić Microsoft Teams funkcji.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-134">Make sure that these ports and URLs are allowed on your network firewall to enable Microsoft Teams to function.</span></span> <span data-ttu-id="b9a0d-135">Bądź na bieżąco z [najnowszą listą portów.](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="b9a0d-135">Stay up to date with the [latest list of ports](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

- <span data-ttu-id="b9a0d-136">Dowiedz się więcej o określonych [wymaganiach dotyczących sieci dla usługi Remote Assist.](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)</span><span class="sxs-lookup"><span data-stu-id="b9a0d-136">Learn more about the specific [Network Requirements for Remote Assist](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span></span> 
- <span data-ttu-id="b9a0d-137">Dowiedz się więcej o [tym, jak przygotować sieć organizacji do](/MicrosoftTeams/prepare-network) Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b9a0d-137">Learn more about how to [prepare your organization's network for Microsoft Teams](/MicrosoftTeams/prepare-network)</span></span>

### <a name="guides-specific-network-requirements"></a><span data-ttu-id="b9a0d-138">Przewodniki z określonymi wymaganiami sieciowymi</span><span class="sxs-lookup"><span data-stu-id="b9a0d-138">Guides Specific Network Requirements</span></span>

<span data-ttu-id="b9a0d-139">Przewodniki wymagają tylko dostępu do sieci w celu pobrania i używania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-139">Guides only require network access to download and use the app.</span></span>

## <a name="azure-active-directory-guidance"></a><span data-ttu-id="b9a0d-140">Azure Active Directory Wskazówki</span><span class="sxs-lookup"><span data-stu-id="b9a0d-140">Azure Active Directory Guidance</span></span>

> [!NOTE]
> <span data-ttu-id="b9a0d-141">Ten krok jest niezbędny tylko wtedy, gdy firma planuje zarządzanie HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-141">This step is only necessary if your company plans on managing the HoloLens.</span></span>

1. <span data-ttu-id="b9a0d-142">Upewnij się, że masz licencję usługi Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-142">Ensure that you have an Azure AD License.</span></span>
<span data-ttu-id="b9a0d-143">Aby [uzyskać dodatkowe HoloLens, zapoznaj się](hololens-licenses-requirements.md) z wymaganiami licencyjnymi.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-143">Please [HoloLens Licenses Requirements](hololens-licenses-requirements.md) for additional information.</span></span>

1. <span data-ttu-id="b9a0d-144">Jeśli planujesz korzystanie z automatycznego rejestrowania, musisz skonfigurować [rejestrację w usłudze Azure AD.](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span><span class="sxs-lookup"><span data-stu-id="b9a0d-144">If you plan on using Auto Enrollment, you will have to [Configure Azure AD enrollment.](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span></span>

1. <span data-ttu-id="b9a0d-145">Upewnij się, że użytkownicy Twojej firmy znajdują się w Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="b9a0d-145">Ensure that your company's users are in Azure Active Directory (Azure AD).</span></span>
<span data-ttu-id="b9a0d-146">Zapoznaj się z [poniższymi instrukcjami](/azure/active-directory/fundamentals/add-users-azure-active-directory) dotyczącymi dodawania użytkowników.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-146">See the following [instructions](/azure/active-directory/fundamentals/add-users-azure-active-directory) for adding users.</span></span>

1. <span data-ttu-id="b9a0d-147">Zalecamy, aby użytkownicy, którzy potrzebują podobnych licencji, dodali się do tej samej grupy.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-147">We suggest that users who need similar licenses are added to the same group.</span></span>
    1. [<span data-ttu-id="b9a0d-148">Tworzenie grupy</span><span class="sxs-lookup"><span data-stu-id="b9a0d-148">Create a Group</span></span>](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [<span data-ttu-id="b9a0d-149">Dodawanie użytkowników do grup</span><span class="sxs-lookup"><span data-stu-id="b9a0d-149">Add users to groups</span></span>](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. <span data-ttu-id="b9a0d-150">Upewnij się, że użytkownicy (lub grupa użytkowników) firmy mają przypisane niezbędne licencje.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-150">Ensure that your company's users (or group of users) are assigned the necessary licenses.</span></span>
<span data-ttu-id="b9a0d-151">Jeśli musisz przypisać licencje, postępuj zgodnie z tymi [instrukcjami](/azure/active-directory/fundamentals/license-users-groups).</span><span class="sxs-lookup"><span data-stu-id="b9a0d-151">If you need to assign licenses, follow these [directions](/azure/active-directory/fundamentals/license-users-groups).</span></span>

1. <span data-ttu-id="b9a0d-152">Ten krok należy wykonać tylko wtedy, gdy użytkownicy mają zarejestrować swoje urządzenie HoloLens/urządzenie przenośne (dostępne są trzy opcje) Te kroki zapewniają, że użytkownicy w firmie (lub grupa użytkowników) mogą dodawać urządzenia.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-152">Only do this step if users are expected to enroll their HoloLens/Mobile device into you (There are three options) These steps ensure that your company's users (or a group of users) can add devices.</span></span>
    1. <span data-ttu-id="b9a0d-153">**Opcja 1.** Nadaj wszystkim użytkownikom uprawnienia do dołączania urządzeń do usługi Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-153">**Option 1:** Give all users permission to join devices to Azure AD.</span></span>
<span data-ttu-id="b9a0d-154">**Zaloguj się do Azure Portal jako administrator**  >  **Azure Active Directory**  >  **Urządzenia**  >  **Ustawienia Ustawienia**  >
 **Ustaw dla ustawienia Użytkownicy mogą dołączać urządzenia do usługi Azure AD wartość *Wszystkie***</span><span class="sxs-lookup"><span data-stu-id="b9a0d-154">**Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
**Set Users may join devices to Azure AD to *All***</span></span>

    1. <span data-ttu-id="b9a0d-155">**Opcja 2.** Nadaj wybranym użytkownikom/grupom uprawnienia do dołączania urządzeń do usługi Azure AD Zaloguj się do usługi **Azure Portal** jako administrator urządzenia Azure Active Directory  >    >  **Urządzenia**  >  **Ustawienia**  >
 \*\*\*\* 
 ![ Ustaw, że użytkownicy mogą dołączać urządzenia do usługi Azure AD do wybranego obrazu wyświetlającego konfigurację urządzeń przyłączone do usługi Azure AD](images/azure-ad-image.png)</span><span class="sxs-lookup"><span data-stu-id="b9a0d-155">**Option 2:** Give selected users/groups permission to join devices to Azure AD **Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
\*\*Set Users may join devices to Azure AD to \*Selected\*\*\*
![Image that shows Configuration of Azure AD Joined Devices](images/azure-ad-image.png)</span></span>

    1. <span data-ttu-id="b9a0d-156">**Opcja 3.** Możesz zablokować wszystkim użytkownikom możliwość dołączania swoich urządzeń do domeny.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-156">**Option 3:** You can block all users from joining their devices to the domain.</span></span> <span data-ttu-id="b9a0d-157">Oznacza to, że wszystkie urządzenia muszą zostać zarejestrowane ręcznie.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-157">This means that all devices will need to be manually enrolled.</span></span>

## <a name="mobile-device-manager-guidance"></a><span data-ttu-id="b9a0d-158">Wskazówki dotyczące Menedżer urządzeń mobilnych</span><span class="sxs-lookup"><span data-stu-id="b9a0d-158">Mobile Device Manager Guidance</span></span>

### <a name="ongoing-device-management"></a><span data-ttu-id="b9a0d-159">Bieżące zarządzanie urządzeniami</span><span class="sxs-lookup"><span data-stu-id="b9a0d-159">Ongoing device management</span></span>

> [!NOTE]
> <span data-ttu-id="b9a0d-160">Ten krok jest niezbędny tylko wtedy, gdy firma planuje zarządzanie HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-160">This step is only necessary if your company plans to manage the HoloLens.</span></span>

<span data-ttu-id="b9a0d-161">Bieżące zarządzanie urządzeniami będzie zależeć od infrastruktury zarządzania urządzeniami przenośnymi.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-161">Ongoing device management will depend on your mobile device management infrastructure.</span></span>  <span data-ttu-id="b9a0d-162">Większość z tych funkcji ma tę samą ogólną funkcjonalność, ale interfejs użytkownika może się znacznie różnić.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-162">Most have the same general functionality but the user interface may vary widely.</span></span>

1. <span data-ttu-id="b9a0d-163">[Dostawcy CSP (dostawcy usług konfiguracji)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) umożliwiają tworzenie i wdrażanie ustawień zarządzania dla urządzeń w sieci.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-163">[CSPs (Configuration Service Providers)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) lets you to create and deploy management settings for the devices on your network.</span></span> <span data-ttu-id="b9a0d-164">Zapoznaj się [z listą HoloLens CSP,](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) aby uzyskać informacje.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-164">See the [list of HoloLens CSPs](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) for reference.</span></span>

1. <span data-ttu-id="b9a0d-165">[Zasady zgodności](/intune/device-compliance-get-started) to reguły i ustawienia, które urządzenia muszą spełniać, aby zapewnić zgodność w infrastrukturze firmowej.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-165">[Compliance policies](/intune/device-compliance-get-started) are rules and settings that devices must meet to be compliant in your corporate infrastructure.</span></span> <span data-ttu-id="b9a0d-166">Użyj tych zasad z dostępem warunkowym, aby zablokować dostęp do zasobów firmy dla niezgodnych urządzeń.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-166">Use these policies with Conditional Access to block access to company resources for devices that are non-compliant.</span></span> <span data-ttu-id="b9a0d-167">Na przykład możesz utworzyć zasady wymagające włączenia funkcji Bitlocker.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-167">For example, you can create a policy that requires Bitlocker be enabled.</span></span>

1. <span data-ttu-id="b9a0d-168">[Utwórz zasady zgodności.](/intune/protect/compliance-policy-create-windows)</span><span class="sxs-lookup"><span data-stu-id="b9a0d-168">[Create Compliance Policy](/intune/protect/compliance-policy-create-windows).</span></span>

1. <span data-ttu-id="b9a0d-169">Dostęp warunkowy zezwala na dostęp urządzeń przenośnych i aplikacji mobilnych do zasobów firmy lub odmówi go.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-169">Conditional Access allows/denies mobile devices and mobile applications from accessing company resources.</span></span> <span data-ttu-id="b9a0d-170">Przydatne mogą być dwa dokumenty: [Planowanie wdrożenia urzędu certyfikacji](/azure/active-directory/conditional-access/plan-conditional-access) i najlepsze [rozwiązania.](/azure/active-directory/conditional-access/best-practices)</span><span class="sxs-lookup"><span data-stu-id="b9a0d-170">Two documents you may find helpful are [Plan your CA Deployment](/azure/active-directory/conditional-access/plan-conditional-access) and [Best Practices](/azure/active-directory/conditional-access/best-practices).</span></span>

1. <span data-ttu-id="b9a0d-171">[W tym](/intune/fundamentals/windows-holographic-for-business) artykule omówienia narzędzi do zarządzania usługą Intune dla HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-171">[This article](/intune/fundamentals/windows-holographic-for-business) talks about Intune's management tools for HoloLens.</span></span>

1. [<span data-ttu-id="b9a0d-172">Tworzenie profilu urządzenia</span><span class="sxs-lookup"><span data-stu-id="b9a0d-172">Create a device profile</span></span>](/intune/configuration/device-profile-create)

### <a name="manage-updates"></a><span data-ttu-id="b9a0d-173">Zarządzanie aktualizacjami</span><span class="sxs-lookup"><span data-stu-id="b9a0d-173">Manage updates</span></span>

<span data-ttu-id="b9a0d-174">Usługa Intune zawiera funkcję o nazwie Pierścienie aktualizacji dla urządzeń Windows 10, w tym HoloLens 2 i HoloLens v1 (z platformą Holographic for Business).</span><span class="sxs-lookup"><span data-stu-id="b9a0d-174">Intune includes a feature called Update rings for Windows 10 devices, including HoloLens 2 and HoloLens v1 (with Holographic for Business).</span></span> <span data-ttu-id="b9a0d-175">Pierścienie aktualizacji obejmują grupę ustawień, które określają, jak i kiedy są instalowane aktualizacje.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-175">Update rings include a group of settings that determine how and when updates are installed.</span></span>

<span data-ttu-id="b9a0d-176">Na przykład możesz utworzyć okno obsługi, aby zainstalować aktualizacje lub wybrać opcję ponownego uruchomienia po zainstalowaniu aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-176">For example, you can create a maintenance window to install updates, or choose to restart after updates are installed.</span></span>  <span data-ttu-id="b9a0d-177">Możesz również wstrzymać aktualizacje na czas nieokreślony do momentu, aż wszystko będzie gotowe do aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-177">You can also choose to pause updates indefinitely until you're ready to update.</span></span>

<span data-ttu-id="b9a0d-178">Przeczytaj więcej na [temat konfigurowania pierścieni aktualizacji za pomocą usługi Intune.](/intune/windows-update-for-business-configure)</span><span class="sxs-lookup"><span data-stu-id="b9a0d-178">Read more about [configuring update rings with Intune](/intune/windows-update-for-business-configure).</span></span>

### <a name="application-management"></a><span data-ttu-id="b9a0d-179">Zarządzanie aplikacjami</span><span class="sxs-lookup"><span data-stu-id="b9a0d-179">Application management</span></span>

<span data-ttu-id="b9a0d-180">Zarządzanie HoloLens aplikacjami za pomocą:</span><span class="sxs-lookup"><span data-stu-id="b9a0d-180">Manage HoloLens applications through:</span></span>

1. <span data-ttu-id="b9a0d-181">Sklepie Microsoft</span><span class="sxs-lookup"><span data-stu-id="b9a0d-181">Microsoft Store</span></span>  
  <span data-ttu-id="b9a0d-182">Ten Microsoft Store to najlepszy sposób rozpowszechniania i zużywania aplikacji na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-182">The Microsoft Store is the best way to distribute and consume applications on HoloLens.</span></span>  <span data-ttu-id="b9a0d-183">Istnieje doskonały zestaw podstawowych aplikacji HoloLens już dostępnych w sklepie lub możesz [opublikować własny.](/windows/uwp/publish/)</span><span class="sxs-lookup"><span data-stu-id="b9a0d-183">There is a great set of core HoloLens applications already available in the store or you can [publish your own](/windows/uwp/publish/).</span></span>  
  <span data-ttu-id="b9a0d-184">Wszystkie aplikacje w sklepie są publicznie dostępne dla wszystkich, ale jeśli nie jest to akceptowalne, należy wyewidencjonować Microsoft Store dla Firm.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-184">All applications in the store are available publicly to everyone, but if it isn't acceptable, checkout the Microsoft Store for Business.</span></span>  

1. [<span data-ttu-id="b9a0d-185">Sklep Microsoft dla Firm</span><span class="sxs-lookup"><span data-stu-id="b9a0d-185">Microsoft Store for Business</span></span>](/microsoft-store/)  
  <span data-ttu-id="b9a0d-186">Microsoft Store dla Firm education to magazyn niestandardowy dla środowiska firmowego.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-186">Microsoft Store for Business and Education is a custom store for your corporate environment.</span></span>  <span data-ttu-id="b9a0d-187">Umożliwia ona korzystanie z Microsoft Store wbudowanych Windows 10 i HoloLens do znajdowanie, pozyskiwanie i rozpowszechnianie aplikacji dla organizacji oraz zarządzanie nimi.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-187">It lets you use the Microsoft Store built into Windows 10 and HoloLens to find, acquire, distribute, and manage apps for your organization.</span></span>  <span data-ttu-id="b9a0d-188">Umożliwia również wdrażanie aplikacji specyficznych dla środowiska komercyjnego, ale nie dla świata.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-188">It also lets you deploy apps that are specific to your commercial environment but not to the world.</span></span>

1. <span data-ttu-id="b9a0d-189">Wdrażanie aplikacji i zarządzanie nimi za pośrednictwem usługi Intune lub innego rozwiązania do zarządzania urządzeniami przenośnymi</span><span class="sxs-lookup"><span data-stu-id="b9a0d-189">Application deployment and management via Intune or another mobile device management solution</span></span>  
  <span data-ttu-id="b9a0d-190">Większość rozwiązań do zarządzania urządzeniami przenośnymi, w tym usługa Intune, umożliwia wdrażanie aplikacji biznesowych bezpośrednio na zestawie zarejestrowanych urządzeń.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-190">Most mobile device management solutions, including Intune, provide a way to deploy line of business applications directly to a set of enrolled devices.</span></span>  <span data-ttu-id="b9a0d-191">Zobacz ten artykuł, aby [zainstalować aplikację usługi Intune.](/intune/apps-deploy)</span><span class="sxs-lookup"><span data-stu-id="b9a0d-191">See this article for [Intune app install](/intune/apps-deploy).</span></span>

1. <span data-ttu-id="b9a0d-192">_nie jest zalecane_ Portal urządzeń</span><span class="sxs-lookup"><span data-stu-id="b9a0d-192">_not recommended_ Device Portal</span></span>  
  <span data-ttu-id="b9a0d-193">Aplikacje można również instalować na HoloLens bezpośrednio przy użyciu Windows Portal urządzeń.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-193">Applications can also be installed on HoloLens directly using the Windows Device Portal.</span></span>  <span data-ttu-id="b9a0d-194">Nie jest to zalecane, ponieważ aby można było korzystać z portalu urządzeń, należy włączyć tryb dewelopera.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-194">This isn't recommended since Developer Mode has to be enabled to use the device portal.</span></span>

<span data-ttu-id="b9a0d-195">Przeczytaj więcej na [temat instalowania aplikacji na HoloLens](hololens-install-apps.md).</span><span class="sxs-lookup"><span data-stu-id="b9a0d-195">Read more about [installing apps on HoloLens](hololens-install-apps.md).</span></span>

### <a name="certificates"></a><span data-ttu-id="b9a0d-196">Certyfikaty</span><span class="sxs-lookup"><span data-stu-id="b9a0d-196">Certificates</span></span>

<span data-ttu-id="b9a0d-197">Certyfikaty można rozpowszechniać za pośrednictwem dostawcy rozwiązania MDM.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-197">You can distribute certificates through your MDM provider.</span></span> <span data-ttu-id="b9a0d-198">Jeśli firma wymaga certyfikatów, usługa Intune obsługuje certyfikaty PKCS, PFX i SCEP.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-198">If your company requires certificates, Intune supports PKCS, PFX, and SCEP.</span></span> <span data-ttu-id="b9a0d-199">Ważne jest, aby zrozumieć, który certyfikat jest odpowiedni dla Twojej firmy.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-199">It is important to understand which certificate is right for your company.</span></span> <span data-ttu-id="b9a0d-200">Zapoznaj się z [dokumentacją konfiguracji certyfikatów,](/intune/protect/certificates-configure) aby ustalić, który certyfikat jest dla Ciebie najlepszy.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-200">Please visit the [certificate configurations](/intune/protect/certificates-configure) documentation to determine which cert is best for you.</span></span> <span data-ttu-id="b9a0d-201">Jeśli zamierzasz używać certyfikatów do uwierzytelniania HoloLens, plik PFX lub SCEP może być odpowiedni dla Ciebie.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-201">If you plan to use certificates for HoloLens Authentication, PFX or SCEP may be right for you.</span></span>

<span data-ttu-id="b9a0d-202">Zapoznaj się z poniższymi krokami korzystania z [SCEP.](/intune/protect/certificates-profile-scep)</span><span class="sxs-lookup"><span data-stu-id="b9a0d-202">See the following steps for using [SCEP](/intune/protect/certificates-profile-scep).</span></span>

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a><span data-ttu-id="b9a0d-203">Jak uaktualnić do pakietu Holographics for Business Commercial Suite</span><span class="sxs-lookup"><span data-stu-id="b9a0d-203">How to Upgrade to Holographics for Business Commercial Suite</span></span>

> [!NOTE]
> <span data-ttu-id="b9a0d-204">Windows Holographics for Business (pakiet komercyjny) jest przeznaczony tylko dla HoloLens pierwszej generacji.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-204">Windows Holographics for Business (commercial suite) is only intended for HoloLens 1st gen devices.</span></span> <span data-ttu-id="b9a0d-205">Profil nie zostanie zastosowany do urządzeń HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-205">The profile will not be applied to HoloLens 2 devices.</span></span>

<span data-ttu-id="b9a0d-206">Wskazówki dotyczące uaktualniania do pakietu komercyjnego można znaleźć w dokumentacji [uaktualnienia holograficznego.](/intune/configuration/holographic-upgrade)</span><span class="sxs-lookup"><span data-stu-id="b9a0d-206">You can find directions for upgrading to the commercial suite in the [holographic upgrade](/intune/configuration/holographic-upgrade) documentation.</span></span>

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a><span data-ttu-id="b9a0d-207">Jak skonfigurować tryb kiosku przy użyciu Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b9a0d-207">How to Configure Kiosk Mode Using Microsoft Intune</span></span>

1. <span data-ttu-id="b9a0d-208">Synchronizacja Microsoft Store z usługą Intune (zobacz następujące [instrukcje).](/intune/apps/windows-store-for-business)</span><span class="sxs-lookup"><span data-stu-id="b9a0d-208">Sync Microsoft Store to Intune (See the following [instructions](/intune/apps/windows-store-for-business)).</span></span>

1. <span data-ttu-id="b9a0d-209">Sprawdzanie ustawień aplikacji</span><span class="sxs-lookup"><span data-stu-id="b9a0d-209">Check your app settings</span></span>
    1. <span data-ttu-id="b9a0d-210">Zaloguj się do konta Microsoft Store Business</span><span class="sxs-lookup"><span data-stu-id="b9a0d-210">Log into your Microsoft Store Business account</span></span>
    1. <span data-ttu-id="b9a0d-211">**Zarządzanie > Produktami i usługami > Apps and Software > Wybierz aplikację, którą chcesz zsynchronizować > dostępność sklepu prywatnego > wybierz pozycję "Wszyscy" lub "Określone grupy"**</span><span class="sxs-lookup"><span data-stu-id="b9a0d-211">**Manage > Products and Services > Apps and Software > Select the app you want to sync > Private Store Availability > Select "Everyone" or "Specific Groups"**</span></span>
        >[!NOTE]
        ><span data-ttu-id="b9a0d-212">Jeśli nie widzisz chętnych aplikacji, musisz "pobrać" aplikację, wyszukując aplikację w sklepie.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-212">If you don't see the app you want, you will have to "get" the app by searching the store for your app.</span></span> <span data-ttu-id="b9a0d-213">**Kliknij pasek "Wyszukaj"** w prawym górnym rogu, > wpisz nazwę aplikacji, > kliknij aplikację, > wybierz pozycję "Pobierz".</span><span class="sxs-lookup"><span data-stu-id="b9a0d-213">**Click the "Search" bar in the upper right-hand corner > type in the name of the app > click on the app > select "Get"**.</span></span>
    1. <span data-ttu-id="b9a0d-214">Jeśli nie widzisz aplikacji w usłudze **Intune > Client Apps > Apps,** może być ponownie trzeba [zsynchronizować](/intune/apps/windows-store-for-business#synchronize-apps) aplikacje.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-214">If you do not see your apps in **Intune > Client Apps > Apps** , you may have to [sync your apps](/intune/apps/windows-store-for-business#synchronize-apps) again.</span></span>

1. [<span data-ttu-id="b9a0d-215">Tworzenie profilu urządzenia dla trybu kiosku</span><span class="sxs-lookup"><span data-stu-id="b9a0d-215">Create a device profile for Kiosk mode</span></span>](/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> <span data-ttu-id="b9a0d-216">Różnych użytkowników można skonfigurować tak, aby mieli różne środowisko trybu kiosku, używając "Azure AD" jako "typu logowania użytkownika".</span><span class="sxs-lookup"><span data-stu-id="b9a0d-216">You can configure different users to have different Kiosk Mode experiences by using "Azure AD" as the "User logon type".</span></span> <span data-ttu-id="b9a0d-217">Jednak ta opcja jest dostępna tylko w trybie kiosku z wieloma aplikacjami.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-217">However, this option is only available in Multi-App kiosk mode.</span></span> <span data-ttu-id="b9a0d-218">Tryb kiosku z wieloma aplikacjami będzie działać tylko z jedną aplikacją, a także z wieloma aplikacjami.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-218">Multi-App kiosk mode will work with only one app as well as multiple apps.</span></span>

![Obraz z konfiguracją trybu kiosku w usłudze Intune](images/aad-kioskmode.png)

<span data-ttu-id="b9a0d-220">W przypadku innych usług MDM zapoznaj się z dokumentacją dostawcy, aby uzyskać instrukcje.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-220">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="b9a0d-221">Zapoznaj się z [HoloLens kiosku,](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) jeśli chcesz użyć ustawienia niestandardowego i pełnej konfiguracji XML w celu skonfigurowania kiosku w usłudze MDM.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-221">Refer to the [HoloLens kiosk](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) instructions if you need to use a custom setting and full XML configuration to set up a kiosk in your MDM service.</span></span>

## <a name="certificates-and-authentication"></a><span data-ttu-id="b9a0d-222">Certyfikaty i uwierzytelnianie</span><span class="sxs-lookup"><span data-stu-id="b9a0d-222">Certificates and Authentication</span></span>

<span data-ttu-id="b9a0d-223">Certyfikaty można wdrażać za pośrednictwem rozwiązania MDM (zobacz sekcję "certyfikaty" w [sekcji MDM).](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)</span><span class="sxs-lookup"><span data-stu-id="b9a0d-223">Certificates can be deployed via you MDM (see "certificates" in the [MDM Section](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span></span> <span data-ttu-id="b9a0d-224">Certyfikaty można również wdrażać na HoloLens przez aprowizowanie pakietów.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-224">Certificates can also be deployed to the HoloLens through package provisioning.</span></span> <span data-ttu-id="b9a0d-225">Aby uzyskać dodatkowe informacje, zobacz [HoloLens Provisioning](hololens-provisioning.md) (Aprowizowanie).</span><span class="sxs-lookup"><span data-stu-id="b9a0d-225">Please see [HoloLens Provisioning](hololens-provisioning.md) for additional information.</span></span>

### <a name="additional-intune-quick-links"></a><span data-ttu-id="b9a0d-226">Dodatkowe szybkie linki do usługi Intune</span><span class="sxs-lookup"><span data-stu-id="b9a0d-226">Additional Intune Quick Links</span></span>

1. <span data-ttu-id="b9a0d-227">[Tworzenie profilów:](/intune/configuration/device-profile-create) Profile umożliwiają dodawanie i konfigurowanie ustawień, które będą wypychane do urządzeń w organizacji.</span><span class="sxs-lookup"><span data-stu-id="b9a0d-227">[Create Profiles:](/intune/configuration/device-profile-create) Profiles allow you to add and configure settings that will be pushed to the devices in your organization.</span></span>

