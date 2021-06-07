---
title: Udostępnianie urządzenia HoloLens wielu osobom
description: Urządzenie HoloLens można skonfigurować tak, aby było współużytowane przez Azure Active Directory kont lub wielu użytkowników, którzy używają jednego konta.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378357"
---
# <a name="share-your-hololens-with-multiple-people"></a><span data-ttu-id="937bb-103">Udostępnianie urządzenia HoloLens wielu osobom</span><span class="sxs-lookup"><span data-stu-id="937bb-103">Share your HoloLens with multiple people</span></span>

<span data-ttu-id="937bb-104">Często udostępnia się jeden urządzeniu HoloLens wielu osobom lub wiele osób udostępnia zestaw urządzeń HoloLens.</span><span class="sxs-lookup"><span data-stu-id="937bb-104">It's common to share one HoloLens with many people or to have many people share a set of HoloLens devices.</span></span>  <span data-ttu-id="937bb-105">W tym artykule opisano różne sposoby udostępniania urządzenia.</span><span class="sxs-lookup"><span data-stu-id="937bb-105">This article describes the different ways in which you can share a device.</span></span>

## <a name="share-with-multiple-people-each-using-their-own-account"></a><span data-ttu-id="937bb-106">Udostępnianie wielu osobom, z których każda korzysta z własnego konta</span><span class="sxs-lookup"><span data-stu-id="937bb-106">Share with multiple people, each using their own account</span></span>

<span data-ttu-id="937bb-107">**Wymaganie** wstępne: na urządzeniu HoloLens musi Windows 10 w wersji 1803 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="937bb-107">**Prerequisite**: The HoloLens device must be running Windows 10, version 1803 or later.</span></span>  <span data-ttu-id="937bb-108">Urządzenie HoloLens (1. generacji) należy również uaktualnić [do Windows Holographic for Business](hololens-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="937bb-108">HoloLens (1st gen) also need to be [upgraded to Windows Holographic for Business](hololens-upgrade-enterprise.md).</span></span>

<span data-ttu-id="937bb-109">Jeśli korzystają oni z własnych kont usługi Azure Active Directory (Azure AD), wielu użytkowników może przechowywać własne ustawienia użytkownika i dane użytkowników na urządzeniu.</span><span class="sxs-lookup"><span data-stu-id="937bb-109">When they use their own Azure Active Directory (Azure AD) accounts, multiple users can each keep their own user settings and user data on the device.</span></span>

<span data-ttu-id="937bb-110">Aby upewnić się, że wiele osób może używać własnych kont na urządzeniach HoloLens, wykonaj następujące kroki, aby je skonfigurować:</span><span class="sxs-lookup"><span data-stu-id="937bb-110">To make sure that multiple people can use their own accounts on your HoloLens, follow these steps to configure it:</span></span>

1. <span data-ttu-id="937bb-111">Upewnij się, że na urządzeniu działa Windows 10 w wersji 1803 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="937bb-111">Make sure the the device is running Windows 10, version 1803 or later.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="937bb-112">Jeśli używasz urządzenia HoloLens (1. generacji), uaktualnij je do [wersji Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="937bb-112">If you are using a HoloLens (1st gen) device, [upgrade the device to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>
1. <span data-ttu-id="937bb-113">Po skonfigurowaniu urządzenia wybierz pozycję **My work or school owns it** and sign in by an Azure AD account (Moja praca lub szkoła jest jego właścicielem) i zaloguj się przy użyciu konta usługi Azure AD.</span><span class="sxs-lookup"><span data-stu-id="937bb-113">When you set up the device, select **My work or school owns it** and sign in by using an Azure AD account.</span></span>
1. <span data-ttu-id="937bb-114">Po zakończeniu instalacji upewnij się, że ustawienia konta (**Konta**  >  **ustawień**) obejmują **innych użytkowników.**</span><span class="sxs-lookup"><span data-stu-id="937bb-114">After you finish setup, make sure that the account settings (**Settings** > **Accounts**) includes **Other users**.</span></span>

<span data-ttu-id="937bb-115">Aby korzystać z urządzenia HoloLens, każdy użytkownik musi wykonać następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="937bb-115">To use HoloLens, each user follows these steps:</span></span>

1. <span data-ttu-id="937bb-116">Jeśli inny użytkownik korzysta z urządzenia, wykonaj jedną z następujących czynności:</span><span class="sxs-lookup"><span data-stu-id="937bb-116">If another user has been using the device, do one of the following:</span></span>
   - <span data-ttu-id="937bb-117">Naciśnij raz przycisk zasilania, aby przejść w stan wstrzymania, a następnie ponownie naciśnij przycisk zasilania, aby powrócić do ekranu blokady</span><span class="sxs-lookup"><span data-stu-id="937bb-117">Press the power button once to go to standby, and then press the power button again to return to the lock screen</span></span>
   - <span data-ttu-id="937bb-118">Użytkownicy urządzenia HoloLens 2 mogą wybrać kafelek użytkownika z menu Start, aby wylogować bieżącego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="937bb-118">HoloLens 2 users may select the user tile from the Start menu to sign out the current user.</span></span>

1. <span data-ttu-id="937bb-119">Użyj poświadczeń konta usługi Azure AD, aby zalogować się na urządzeniu.</span><span class="sxs-lookup"><span data-stu-id="937bb-119">Use your Azure AD account credentials to sign in to the device.</span></span>  
    <span data-ttu-id="937bb-120">Jeśli urządzenie jest używane po raz pierwszy, musisz [](hololens-calibration.md) skalibrować urządzenie HoloLens na własne oczy.</span><span class="sxs-lookup"><span data-stu-id="937bb-120">If this is the first time that you have used the device, you have to [calibrate](hololens-calibration.md) HoloLens to your own eyes.</span></span>

<span data-ttu-id="937bb-121">Aby wyświetlić listę użytkowników urządzenia lub usunąć użytkownika z urządzenia, przejdź do tematu Ustawienia   >  **Konta**  >  **Inni użytkownicy.**</span><span class="sxs-lookup"><span data-stu-id="937bb-121">To see a list of the device users or to remove a user from the device, go to **Settings** > **Accounts** > **Other users**.</span></span>

## <a name="share-with-multiple-people-all-using-the-same-account"></a><span data-ttu-id="937bb-122">Udostępnianie wielu osobom przy użyciu tego samego konta</span><span class="sxs-lookup"><span data-stu-id="937bb-122">Share with multiple people, all using the same account</span></span>

<span data-ttu-id="937bb-123">Wielu użytkowników może również udostępniać urządzenie HoloLens przy użyciu jednego konta użytkownika.</span><span class="sxs-lookup"><span data-stu-id="937bb-123">Multiple users can also share a HoloLens device while using a single user account.</span></span>

<span data-ttu-id="937bb-124">Na urządzeniu **HoloLens 2,** gdy nowy użytkownik po raz pierwszy włoży urządzenie na łeb (przy zachowaniu tego samego konta), urządzenie monituje nowego użytkownika o szybkie skalibrowanie i personalizowanie wyświetlania.</span><span class="sxs-lookup"><span data-stu-id="937bb-124">**On HoloLens 2**, when a new user puts the device on their head for the first time (while keeping the same account signed in), the device prompts the new user to quickly calibrate and personalize the viewing experience.</span></span> <span data-ttu-id="937bb-125">Urządzenie może przechowywać informacje o pogotowiu, aby w przyszłości urządzenie automatycznie optymalizowało jakość i komfort wyświetlania poszczególnych użytkowników.</span><span class="sxs-lookup"><span data-stu-id="937bb-125">The device can store the calibration information so that in the future, the device can automatically optimize the quality and comfort of each user's viewing experience.</span></span> <span data-ttu-id="937bb-126">Użytkownicy nie muszą ponownie skalibrować urządzenia.</span><span class="sxs-lookup"><span data-stu-id="937bb-126">The users do not need to calibrate the device again.</span></span>

<span data-ttu-id="937bb-127">**Na urządzeniach HoloLens (1. generacji)** użytkownicy, którzy współużytkują konto, będą musieli poprosić o ponowną ujedną w aplikacji Ustawienia.</span><span class="sxs-lookup"><span data-stu-id="937bb-127">**On HoloLens (1st gen)** users sharing an account will need to ask to recalibrate in the Settings app.</span></span>  <span data-ttu-id="937bb-128">Przeczytaj więcej na [temat chłoniaka](hololens-calibration.md).</span><span class="sxs-lookup"><span data-stu-id="937bb-128">Read more about [calibration](hololens-calibration.md).</span></span>
