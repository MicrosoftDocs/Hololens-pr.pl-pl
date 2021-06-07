---
title: Używanie głosu do obsługi urządzenia HoloLens
description: Dowiedz się, jak Cortana może ułatwić Ci różnego rodzaju czynności na urządzeniach HoloLens rzeczywistości mieszanej, w tym polecenia głosowe, dyktowanie i interakcje hologramów.
ms.assetid: fd96fb0e-6759-4dbe-be1f-58bedad66fed
ms.date: 03/10/2020
keywords: Hololens
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
audience: ITPro
ms.author: v-tea
ms.topic: article
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f6e3dd8f7dc90cea158d000251973ec75dc76a90
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379761"
---
# <a name="use-your-voice-to-operate-hololens"></a><span data-ttu-id="ee836-104">Używanie głosu do obsługi urządzenia HoloLens</span><span class="sxs-lookup"><span data-stu-id="ee836-104">Use your voice to operate HoloLens</span></span>

<span data-ttu-id="ee836-105">Za pomocą głosu możesz wykonać niemal wszystko na urządzeniach HoloLens, na przykład zrobić szybkie zdjęcie lub otworzyć aplikację.</span><span class="sxs-lookup"><span data-stu-id="ee836-105">You can use your voice to do almost anything on HoloLens, such as taking a quick photo or opening an app.</span></span> <span data-ttu-id="ee836-106">Wiele poleceń głosowych jest wbudowanych w urządzenie HoloLens, a inne są dostępne za pośrednictwem Cortany.</span><span class="sxs-lookup"><span data-stu-id="ee836-106">Many voice commands are built into HoloLens, while others are available through Cortana.</span></span>

<span data-ttu-id="ee836-107">W tym artykule popisano, jak sterować urządzeniem HoloLens i światem holograficznym za pomocą głosu i Cortany.</span><span class="sxs-lookup"><span data-stu-id="ee836-107">This article teaches you how to control HoloLens and your holographic world with your voice and with Cortana.</span></span>

> [!NOTE]
> <span data-ttu-id="ee836-108">Mowa jest obsługiwana tylko w [niektórych językach.](hololens2-language-support.md)</span><span class="sxs-lookup"><span data-stu-id="ee836-108">Speech is only supported in [some languages](hololens2-language-support.md).</span></span> <span data-ttu-id="ee836-109">Język mowy jest oparty na języku wyświetlania systemu Windows, a nie na języku klawiatury.</span><span class="sxs-lookup"><span data-stu-id="ee836-109">The speech language is based on the Windows display language, not the keyboard language.</span></span>  
>  
> <span data-ttu-id="ee836-110">Język wyświetlania systemu Windows można sprawdzić, wybierając **pozycję Czas** ustawień  >  **i Język**  >  **języka**.</span><span class="sxs-lookup"><span data-stu-id="ee836-110">You can verify the Windows display language by selecting **Settings** > **Time and Language** > **Language**.</span></span>

## <a name="built-in-voice-commands"></a><span data-ttu-id="ee836-111">Wbudowane polecenia głosowe</span><span class="sxs-lookup"><span data-stu-id="ee836-111">Built-in voice commands</span></span>

<span data-ttu-id="ee836-112">Szybciej omów urządzenie HoloLens za pomocą tych podstawowych poleceń.</span><span class="sxs-lookup"><span data-stu-id="ee836-112">Get around HoloLens faster with these basic commands.</span></span> <span data-ttu-id="ee836-113">Aby można było ich używać, należy włączyć mowę podczas pierwszego uruchomienia urządzenia lub w ustawieniach  >  **mowy dotyczącej**  >  **prywatności.**</span><span class="sxs-lookup"><span data-stu-id="ee836-113">In order to use these, you need to enable Speech during the first run of the device or in **Settings** > **Privacy** > **Speech**.</span></span> <span data-ttu-id="ee836-114">Zawsze możesz sprawdzić, czy mowa jest włączona, patrząc na stan w górnej części menu Start.</span><span class="sxs-lookup"><span data-stu-id="ee836-114">You can always check whether speech is enabled by looking at the status at the top of the Start menu.</span></span> <span data-ttu-id="ee836-115">Aby uzyskać najlepsze wyniki rozpoznawania mowy, urządzenie HoloLens 2 korzysta z usług firmy Microsoft opartych na chmurze.</span><span class="sxs-lookup"><span data-stu-id="ee836-115">For the best speech recognition results, HoloLens 2 uses the Microsoft cloud-based services.</span></span> <span data-ttu-id="ee836-116">Można jednak wyłączyć tę funkcję za pomocą ustawień.</span><span class="sxs-lookup"><span data-stu-id="ee836-116">However, you can use Settings to disable this feature.</span></span> <span data-ttu-id="ee836-117">Aby to zrobić, w ustawieniach wyłącz pozycję **Rozpoznawanie mowy w trybie online.**</span><span class="sxs-lookup"><span data-stu-id="ee836-117">To do this, in Settings, turn off **Online speech recognition**.</span></span> <span data-ttu-id="ee836-118">Po zmianie tego ustawienia urządzenie HoloLens 2 będzie przetwarzać dane głosowe tylko lokalnie w celu rozpoznawania poleceń i dyktowania, a Cortana nie będzie dostępna.</span><span class="sxs-lookup"><span data-stu-id="ee836-118">After you change this setting, HoloLens 2 will only process voice data locally to recognize commands and dictation, and Cortana will not be available.</span></span>

### <a name="general-speech-commands"></a><span data-ttu-id="ee836-119">Ogólne polecenia mowy</span><span class="sxs-lookup"><span data-stu-id="ee836-119">General speech commands</span></span>

<span data-ttu-id="ee836-120">Użyj tych poleceń w Windows Mixed Reality, aby szybciej się omiąć.</span><span class="sxs-lookup"><span data-stu-id="ee836-120">Use these commands throughout Windows Mixed Reality to get around faster.</span></span> <span data-ttu-id="ee836-121">Niektóre polecenia używają kursora spojrzenia, który można wyprowadzić, mówiąc "select".</span><span class="sxs-lookup"><span data-stu-id="ee836-121">Some commands use the gaze cursor, which you bring up by saying "select."</span></span>

> [!NOTE]
> <span data-ttu-id="ee836-122">Promienie rąk nie są obsługiwane na urządzeniach HoloLens (1. generacji).</span><span class="sxs-lookup"><span data-stu-id="ee836-122">Hand rays are not supported on HoloLens (1st Gen).</span></span>

| <span data-ttu-id="ee836-123">Powiedz to</span><span class="sxs-lookup"><span data-stu-id="ee836-123">Say this</span></span> | <span data-ttu-id="ee836-124">Wymagana czynność</span><span class="sxs-lookup"><span data-stu-id="ee836-124">To do this</span></span> |
| - | - |
| <span data-ttu-id="ee836-125">"Wybierz"</span><span class="sxs-lookup"><span data-stu-id="ee836-125">"Select"</span></span> | <span data-ttu-id="ee836-126">Powiedz "select", aby wyprowadzić kursor.</span><span class="sxs-lookup"><span data-stu-id="ee836-126">Say "select" to bring up the gaze cursor.</span></span> <span data-ttu-id="ee836-127">Następnie ustaw kursor na rzecz, którą chcesz wybrać, i powiedz "select" (wybierz).</span><span class="sxs-lookup"><span data-stu-id="ee836-127">Then, turn your head to position the cursor on the thing you want to select, and say "select" again.</span></span> |
| <span data-ttu-id="ee836-128">"Przejdź do startu"</span><span class="sxs-lookup"><span data-stu-id="ee836-128">"Go to Start"</span></span> |  <span data-ttu-id="ee836-129">Otwieranie menu Start</span><span class="sxs-lookup"><span data-stu-id="ee836-129">Open the Start menu</span></span> |
| <span data-ttu-id="ee836-130">"Zamknij"</span><span class="sxs-lookup"><span data-stu-id="ee836-130">"Close"</span></span>  | <span data-ttu-id="ee836-131">Zamknij menu Start</span><span class="sxs-lookup"><span data-stu-id="ee836-131">Close the Start menu</span></span> |
| <span data-ttu-id="ee836-132">Powiedz "Przejdź do startu", aby uruchomić menu szybkich akcji, a następnie powiedz "Mixed reality home".</span><span class="sxs-lookup"><span data-stu-id="ee836-132">Say "Go to Start" to bring up the quick actions menu, then say "Mixed reality home."</span></span>  | <span data-ttu-id="ee836-133">Opuszczanie aplikacji immersyjnej</span><span class="sxs-lookup"><span data-stu-id="ee836-133">Leave an immersive app</span></span> |
| <span data-ttu-id="ee836-134">"Hide hand ray" / "Show hand ray" (Ukryj promienie dłoni) / "Show hand ray" (Pokaż promienie dłoni)</span><span class="sxs-lookup"><span data-stu-id="ee836-134">"Hide hand ray" / "Show hand ray"</span></span> | <span data-ttu-id="ee836-135">Ukrywanie i pokazywanie promienia dłoni</span><span class="sxs-lookup"><span data-stu-id="ee836-135">Hide and show hand ray</span></span> |
| <span data-ttu-id="ee836-136">"Co mogę powiedzieć?"</span><span class="sxs-lookup"><span data-stu-id="ee836-136">"What can I say?"</span></span>  | <span data-ttu-id="ee836-137">Zobacz dostępne polecenia mowy</span><span class="sxs-lookup"><span data-stu-id="ee836-137">See available speech commands</span></span> |

<span data-ttu-id="ee836-138">Począwszy od wersji 19041.x urządzenia HoloLens 2, można również użyć tych poleceń:</span><span class="sxs-lookup"><span data-stu-id="ee836-138">Starting with version 19041.x of HoloLens 2, you can also use these commands:</span></span>

| <span data-ttu-id="ee836-139">Powiedz to</span><span class="sxs-lookup"><span data-stu-id="ee836-139">Say this</span></span> | <span data-ttu-id="ee836-140">Wymagana czynność</span><span class="sxs-lookup"><span data-stu-id="ee836-140">To do this</span></span> |
| - | - |
| <span data-ttu-id="ee836-141">"Uruchom ponownie urządzenie"</span><span class="sxs-lookup"><span data-stu-id="ee836-141">"Restart device"</span></span> | <span data-ttu-id="ee836-142">Uruchom dialog, aby potwierdzić, że chcesz ponownie uruchomić urządzenie.</span><span class="sxs-lookup"><span data-stu-id="ee836-142">Bring up a dialogue to confirm you want to restart the device.</span></span> <span data-ttu-id="ee836-143">Możesz powiedzieć "tak", aby ponownie uruchomić.</span><span class="sxs-lookup"><span data-stu-id="ee836-143">You can say "yes" to restart.</span></span> |
| <span data-ttu-id="ee836-144">"Zamykanie urządzenia"</span><span class="sxs-lookup"><span data-stu-id="ee836-144">"Shutdown device"</span></span> | <span data-ttu-id="ee836-145">Aby potwierdzić, że chcesz wyłączyć urządzenie, zostanie wyzłoszysz dialog.</span><span class="sxs-lookup"><span data-stu-id="ee836-145">Bring up a dialogue to confirm you want to turn off the device.</span></span> <span data-ttu-id="ee836-146">Możesz powiedzieć "tak", aby potwierdzić.</span><span class="sxs-lookup"><span data-stu-id="ee836-146">You can say "yes" to confirm.</span></span> |
| <span data-ttu-id="ee836-147">"Jasność w górę/w dół"</span><span class="sxs-lookup"><span data-stu-id="ee836-147">"Brightness up/down"</span></span> | <span data-ttu-id="ee836-148">Zwiększ lub zmniejsz jasność ekranu o 10%.</span><span class="sxs-lookup"><span data-stu-id="ee836-148">Increase or decrease the display brightness by 10%.</span></span> |
| <span data-ttu-id="ee836-149">"Wolumin w górę/w dół"</span><span class="sxs-lookup"><span data-stu-id="ee836-149">"Volume up/down"</span></span> | <span data-ttu-id="ee836-150">Zwiększ lub zmniejsz wolumin o 10%.</span><span class="sxs-lookup"><span data-stu-id="ee836-150">Increase or decrease the volume by 10%.</span></span> |
| <span data-ttu-id="ee836-151">"What's my IP address" (Jaki jest mój adres IP)</span><span class="sxs-lookup"><span data-stu-id="ee836-151">"What's my IP address"</span></span> | <span data-ttu-id="ee836-152">Wyświetl dialog z bieżącym adresem IP urządzenia w sieci lokalnej.</span><span class="sxs-lookup"><span data-stu-id="ee836-152">Bring up a dialogue displaying your device's current IP address on the local network.</span></span> |
| <span data-ttu-id="ee836-153">"Take a picture" (Zrób zdjęcie)</span><span class="sxs-lookup"><span data-stu-id="ee836-153">"Take a picture"</span></span> | <span data-ttu-id="ee836-154">Przechwyć zdjęcie rzeczywistości mieszanej z tym, co obecnie widzisz.</span><span class="sxs-lookup"><span data-stu-id="ee836-154">Capture a mixed reality photo of what you are currently seeing.</span></span> |
| <span data-ttu-id="ee836-155">"Take a video" (Zrób film wideo)</span><span class="sxs-lookup"><span data-stu-id="ee836-155">"Take a video"</span></span> | <span data-ttu-id="ee836-156">Rozpocznij nagrywanie wideo rzeczywistości mieszanej.</span><span class="sxs-lookup"><span data-stu-id="ee836-156">Start recording a mixed reality video.</span></span> | 
| <span data-ttu-id="ee836-157">"Zatrzymaj nagrywanie"</span><span class="sxs-lookup"><span data-stu-id="ee836-157">"Stop recording"</span></span> | <span data-ttu-id="ee836-158">Zatrzymuje bieżące nagrywanie wideo rzeczywistości mieszanej, jeśli jest w toku.</span><span class="sxs-lookup"><span data-stu-id="ee836-158">Stops the current mixed reality video recording if one is in progress.</span></span> |

### <a name="hologram-commands"></a><span data-ttu-id="ee836-159">Polecenia hologramu</span><span class="sxs-lookup"><span data-stu-id="ee836-159">Hologram commands</span></span>

<span data-ttu-id="ee836-160">Aby użyć tych poleceń, spojrz na obiekt 3D, hologram lub okno aplikacji.</span><span class="sxs-lookup"><span data-stu-id="ee836-160">To use these commands, gaze at a 3D object, hologram, or app window.</span></span>

| <span data-ttu-id="ee836-161">Powiedz to</span><span class="sxs-lookup"><span data-stu-id="ee836-161">Say this</span></span> | <span data-ttu-id="ee836-162">Wymagana czynność</span><span class="sxs-lookup"><span data-stu-id="ee836-162">To do this</span></span> |
| - | - |
| <span data-ttu-id="ee836-163">"Większe"</span><span class="sxs-lookup"><span data-stu-id="ee836-163">"Bigger"</span></span> | <span data-ttu-id="ee836-164">Uaduj ją</span><span class="sxs-lookup"><span data-stu-id="ee836-164">Make it bigger</span></span> |
| <span data-ttu-id="ee836-165">"Mniejsze"</span><span class="sxs-lookup"><span data-stu-id="ee836-165">"Smaller"</span></span> | <span data-ttu-id="ee836-166">Mniejsze rozmiary</span><span class="sxs-lookup"><span data-stu-id="ee836-166">Make it smaller</span></span> |
| <span data-ttu-id="ee836-167">"Face me"</span><span class="sxs-lookup"><span data-stu-id="ee836-167">"Face me"</span></span> | <span data-ttu-id="ee836-168">Przekróć ją w twarz</span><span class="sxs-lookup"><span data-stu-id="ee836-168">Turn it to face you</span></span> |
| <span data-ttu-id="ee836-169">"Przenieś to"</span><span class="sxs-lookup"><span data-stu-id="ee836-169">"Move this"</span></span> | <span data-ttu-id="ee836-170">Przenieś go (za spojrzeniem)</span><span class="sxs-lookup"><span data-stu-id="ee836-170">Move it (follow your gaze)</span></span> |
| <span data-ttu-id="ee836-171">"Zamknij"</span><span class="sxs-lookup"><span data-stu-id="ee836-171">"Close"</span></span> | <span data-ttu-id="ee836-172">Zamknij go</span><span class="sxs-lookup"><span data-stu-id="ee836-172">Close it</span></span> |
| <span data-ttu-id="ee836-173">"Obserwuj mnie" / "Przestań obserwować"</span><span class="sxs-lookup"><span data-stu-id="ee836-173">"Follow me" / "Stop following"</span></span> | <span data-ttu-id="ee836-174">Poruszaj się po nim</span><span class="sxs-lookup"><span data-stu-id="ee836-174">Make it follow you as you move around</span></span> |

### <a name="see-it-say-it"></a><span data-ttu-id="ee836-175">Zobacz, powiedz to</span><span class="sxs-lookup"><span data-stu-id="ee836-175">See it, say it</span></span>

<span data-ttu-id="ee836-176">Wiele przycisków i innych elementów na urządzeniach HoloLens reaguje  również na Twój głos **—** na przykład Obserwuj mnie i zamknij na pasku aplikacji lub przycisk **Wstecz** w aplikacji Edge.</span><span class="sxs-lookup"><span data-stu-id="ee836-176">Many buttons and other elements on HoloLens also respond to your voice—for example, **Follow me** and **Close** on the app bar, or the **Back** button in Edge.</span></span> <span data-ttu-id="ee836-177">Aby dowiedzieć się, czy przycisk ma włączoną  obsługę głosu,  na chwilę umieść kursor w ręki, kursor dotykowy lub promieniej na nim.</span><span class="sxs-lookup"><span data-stu-id="ee836-177">To find out if a button is voice-enabled, rest your **gaze cursor**, **touch cursor** or one **hand ray** on it for a moment.</span></span> <span data-ttu-id="ee836-178">Jeśli przycisk ma włączoną obsługę głosu, zobaczysz poradę głosową.</span><span class="sxs-lookup"><span data-stu-id="ee836-178">If the button is voice-enabled, you'll see a voice tip.</span></span>

### <a name="dictation-mode"></a><span data-ttu-id="ee836-179">Tryb dyktowania</span><span class="sxs-lookup"><span data-stu-id="ee836-179">Dictation mode</span></span>

<span data-ttu-id="ee836-180">Masz dość pisania?</span><span class="sxs-lookup"><span data-stu-id="ee836-180">Tired of typing?</span></span> <span data-ttu-id="ee836-181">Przełącz się do trybu dyktowania za każdym razem, gdy klawiatura holograficzna jest aktywna.</span><span class="sxs-lookup"><span data-stu-id="ee836-181">Switch to dictation mode anytime that the holographic keyboard is active.</span></span> <span data-ttu-id="ee836-182">Aby rozpocząć, wybierz przycisk mikrofonu lub powiedz "Rozpocznij dyktowanie".</span><span class="sxs-lookup"><span data-stu-id="ee836-182">To get started, select the microphone button or say "Start dictating."</span></span> <span data-ttu-id="ee836-183">Aby zatrzymać dyktowanie, ponownie wybierz przycisk lub powiedz "Zatrzymaj dyktowanie".</span><span class="sxs-lookup"><span data-stu-id="ee836-183">To stop dictating, select the button again or say "Stop dictating."</span></span> <span data-ttu-id="ee836-184">Aby usunąć właśnie dyktowane dane, powiedz "Usuń to".</span><span class="sxs-lookup"><span data-stu-id="ee836-184">To delete what you just dictated, say "Delete that."</span></span> 

> [!NOTE]
> <span data-ttu-id="ee836-185">Aby korzystać z trybu dyktowania, musisz mieć połączenie internetowe.</span><span class="sxs-lookup"><span data-stu-id="ee836-185">To use dictation mode, you have to have an internet connection.</span></span>

<span data-ttu-id="ee836-186">Dyktowanie urządzenia HoloLens używa jawnej interpunkcji, co oznacza, że mówisz nazwę interpunkcji, której chcesz użyć.</span><span class="sxs-lookup"><span data-stu-id="ee836-186">HoloLens dictation uses explicit punctuation, meaning that you say the name of the punctuation you want to use.</span></span> <span data-ttu-id="ee836-187">Na przykład możesz powiedzieć "Hey **przecinek** what are you up to **question mark".**</span><span class="sxs-lookup"><span data-stu-id="ee836-187">For instance, you might say "Hey **comma** what are you up to **question mark**."</span></span>

<span data-ttu-id="ee836-188">Poniżej znajdują się słowa kluczowe interpunkcji, których można użyć:</span><span class="sxs-lookup"><span data-stu-id="ee836-188">Here are the punctuation keywords that you can use:</span></span>

- <span data-ttu-id="ee836-189">Okres, przecinek, znak zapytania, wykrzyknik/wykrzyknik</span><span class="sxs-lookup"><span data-stu-id="ee836-189">Period, comma, question mark, exclamation point/exclamation mark</span></span>
- <span data-ttu-id="ee836-190">Nowy wiersz/nowy akapit</span><span class="sxs-lookup"><span data-stu-id="ee836-190">New line/new paragraph</span></span>
- <span data-ttu-id="ee836-191">Średnik, dwukropek</span><span class="sxs-lookup"><span data-stu-id="ee836-191">Semicolon, colon</span></span>
- <span data-ttu-id="ee836-192">Oferty otwarte, cudzysłowy zamknięcia</span><span class="sxs-lookup"><span data-stu-id="ee836-192">Open quote(s), close quote(s)</span></span>
- <span data-ttu-id="ee836-193">Hasztag, uśmiechnięta/uśmiechnięta buźka, frowny, winky</span><span class="sxs-lookup"><span data-stu-id="ee836-193">Hashtag, smiley/smiley face, frowny, winky</span></span>
- <span data-ttu-id="ee836-194">Dolar, procent</span><span class="sxs-lookup"><span data-stu-id="ee836-194">Dollar, percent</span></span>

<span data-ttu-id="ee836-195">Czasami pomocne jest pisownia takich adresów e-mail.</span><span class="sxs-lookup"><span data-stu-id="ee836-195">Sometimes it's helpful to spell out things like email addresses.</span></span> <span data-ttu-id="ee836-196">Na przykład, aby dyktować , należy powiedzieć example@outlook.com "E X A M P L E w outlook dot com".</span><span class="sxs-lookup"><span data-stu-id="ee836-196">For instance, to dictate example@outlook.com, you'd say "E X A M P L E at outlook dot com."</span></span>

## <a name="do-more-with-cortana"></a><span data-ttu-id="ee836-197">Więcej informacji za pomocą Cortany</span><span class="sxs-lookup"><span data-stu-id="ee836-197">Do more with Cortana</span></span>

<span data-ttu-id="ee836-198">Cortana może pomóc w wszelkiego rodzaju czynnościach na urządzeniach HoloLens, ale w zależności od tego, której wersji systemu Windows Holographic używasz, możliwości mogą się różnić.</span><span class="sxs-lookup"><span data-stu-id="ee836-198">Cortana can help you do all kinds of things on your HoloLens, but depending on which version of Windows Holographic you're using, the capabilities may be different.</span></span> <span data-ttu-id="ee836-199">Więcej informacji o zaktualizowanych możliwościach najnowszej wersji Cortany można znaleźć tutaj: Cortana w nadchodzącej wersji Windows 10: skoncentrowanie się na produktywności z rozszerzonymi zabezpieczeniami [i prywatnością.](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)</span><span class="sxs-lookup"><span data-stu-id="ee836-199">You can learn more about the updated capabilities of the latest version of Cortana here: [Cortana in the upcoming Windows 10 release: focused on your productivity with enhanced security and privacy](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).</span></span> 

![Hej, Cortana!](images/cortana-on-hololens.png)

<span data-ttu-id="ee836-201">Oto kilka rzeczy, które możesz spróbować powiedzieć (pamiętaj, aby najpierw powiedzieć "Hey Cortana".</span><span class="sxs-lookup"><span data-stu-id="ee836-201">Here are some things you can try saying (remember to say "Hey Cortana" first).</span></span>

<span data-ttu-id="ee836-202">**Hey, Cortana**...</span><span class="sxs-lookup"><span data-stu-id="ee836-202">**Hey, Cortana**...</span></span>

- <span data-ttu-id="ee836-203">What can I say? (Co mogę powiedzieć?)</span><span class="sxs-lookup"><span data-stu-id="ee836-203">What can I say?</span></span>
- <span data-ttu-id="ee836-204">Uruchom <*nazwę>.*</span><span class="sxs-lookup"><span data-stu-id="ee836-204">Launch <*app name*>.</span></span>
- <span data-ttu-id="ee836-205">Która jest godzina?</span><span class="sxs-lookup"><span data-stu-id="ee836-205">What time is it?</span></span>
- <span data-ttu-id="ee836-206">Pokaż mi najnowsze wyniki NBA.</span><span class="sxs-lookup"><span data-stu-id="ee836-206">Show me the latest NBA scores.</span></span>
- <span data-ttu-id="ee836-207">Tell me a joke. (Opowiedz mi dowcip).</span><span class="sxs-lookup"><span data-stu-id="ee836-207">Tell me a joke.</span></span>

<span data-ttu-id="ee836-208">Jeśli używasz wersji *18362.x lub starszej,* możesz również użyć tych poleceń:</span><span class="sxs-lookup"><span data-stu-id="ee836-208">If you're using *version 18362.x or earlier*, you can also use these commands:</span></span>

<span data-ttu-id="ee836-209">**Hey, Cortana**...</span><span class="sxs-lookup"><span data-stu-id="ee836-209">**Hey, Cortana**...</span></span>

- <span data-ttu-id="ee836-210">Zwiększ wolumin.</span><span class="sxs-lookup"><span data-stu-id="ee836-210">Increase the volume.</span></span>
- <span data-ttu-id="ee836-211">Zmniejsz jasność.</span><span class="sxs-lookup"><span data-stu-id="ee836-211">Decrease the brightness.</span></span>
- <span data-ttu-id="ee836-212">Zamknij.</span><span class="sxs-lookup"><span data-stu-id="ee836-212">Shut down.</span></span>
- <span data-ttu-id="ee836-213">Uruchom ponownie.</span><span class="sxs-lookup"><span data-stu-id="ee836-213">Restart.</span></span>
- <span data-ttu-id="ee836-214">Idź spać.</span><span class="sxs-lookup"><span data-stu-id="ee836-214">Go to sleep.</span></span>
- <span data-ttu-id="ee836-215">Wycisz.</span><span class="sxs-lookup"><span data-stu-id="ee836-215">Mute.</span></span>
- <span data-ttu-id="ee836-216">Przenieś <*nazwę*> w tym miejscu (spojrzenie w miejscu, do którego chcesz przenieść aplikację).</span><span class="sxs-lookup"><span data-stu-id="ee836-216">Move <*app name*> here (gaze at the spot that you want the app to move to).</span></span>
- <span data-ttu-id="ee836-217">Przejdź do pozycji Start.</span><span class="sxs-lookup"><span data-stu-id="ee836-217">Go to Start.</span></span>
- <span data-ttu-id="ee836-218">Zrób zdjęcie.</span><span class="sxs-lookup"><span data-stu-id="ee836-218">Take a picture.</span></span>
- <span data-ttu-id="ee836-219">Rozpocznij nagrywanie.</span><span class="sxs-lookup"><span data-stu-id="ee836-219">Start recording.</span></span> <span data-ttu-id="ee836-220">(Rozpoczyna nagrywanie wideo).</span><span class="sxs-lookup"><span data-stu-id="ee836-220">(Starts recording a video.)</span></span>
- <span data-ttu-id="ee836-221">Zatrzymaj nagrywanie.</span><span class="sxs-lookup"><span data-stu-id="ee836-221">Stop recording.</span></span> <span data-ttu-id="ee836-222">(Zatrzymuje nagrywanie wideo).</span><span class="sxs-lookup"><span data-stu-id="ee836-222">(Stops recording a video.)</span></span>
- <span data-ttu-id="ee836-223">Ile baterii pozostało?</span><span class="sxs-lookup"><span data-stu-id="ee836-223">How much battery do I have left?</span></span>

<span data-ttu-id="ee836-224">Niektóre funkcje Cortany, z których korzystasz z systemu Windows na komputerze lub telefonie (na przykład przypomnienia i powiadomienia), nie są obsługiwane na platformie Microsoft HoloLens, a środowisko Cortany może się różnić w zależności od regionu.</span><span class="sxs-lookup"><span data-stu-id="ee836-224">Some Cortana features that you're used to from Windows on your PC or phone (for example, reminders and notifications) aren't supported in Microsoft HoloLens, and the Cortana experience may vary from one region to another.</span></span>

### <a name="turn-cortana-off"></a><span data-ttu-id="ee836-225">Wyłączanie Cortany</span><span class="sxs-lookup"><span data-stu-id="ee836-225">Turn Cortana off</span></span>

<span data-ttu-id="ee836-226">Cortana jest włączana przy pierwszym użyciu urządzenia HoloLens po włączeniu mowy.</span><span class="sxs-lookup"><span data-stu-id="ee836-226">Cortana is on the first time you use HoloLens when you enable speech.</span></span> <span data-ttu-id="ee836-227">Możesz wyłączyć ją w ustawieniach Cortany.</span><span class="sxs-lookup"><span data-stu-id="ee836-227">You can turn her off in Cortana's settings.</span></span> <span data-ttu-id="ee836-228">Na liście **Wszystkie aplikacje** wybierz pozycję **Ustawienia**  >  **Cortany.**</span><span class="sxs-lookup"><span data-stu-id="ee836-228">In the **All apps** list, select **Cortana** > **Settings**.</span></span> <span data-ttu-id="ee836-229">Następnie wyłącz cortanę, aby przekazać Ci sugestie, pomysły, przypomnienia, alerty i nie tylko.</span><span class="sxs-lookup"><span data-stu-id="ee836-229">Then turn off Cortana can give you suggestions, ideas, reminders, alerts, and more.</span></span>

<span data-ttu-id="ee836-230">Jeśli Cortana nie odpowiada na "Hej Cortanę", sprawdź, czy mowa jest włączona w menu Start, a następnie przejdź do ustawień Cortany i upewnij się, że jest włączona.</span><span class="sxs-lookup"><span data-stu-id="ee836-230">If Cortana isn't responding to "Hey Cortana," check that speech is enabled on Start and go to Cortana's settings and check to make sure she's on.</span></span>
