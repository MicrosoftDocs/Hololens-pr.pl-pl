---
title: Instrukcje dotyczące współtworowania
description: Dowiedz się, jak współtwolić HoloLens do dokumentów na platformie docs.microsoft.com przy użyciu GitHub języka Markdown.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: 73b6e8bcd634cb4d45171bda0a85f2e991a977c9
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635674"
---
# <a name="contributing-to-the-hololens-documentation"></a><span data-ttu-id="21d4e-103">Współtwoowanie dokumentacji HoloLens dokumentacji</span><span class="sxs-lookup"><span data-stu-id="21d4e-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="21d4e-104">Witamy w [HoloLens dokumentacji!](https://github.com/MicrosoftDocs/Hololens)</span><span class="sxs-lookup"><span data-stu-id="21d4e-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="21d4e-105">Wszystkie artykuły, które utworzysz lub edytujesz w tym repo, **będą widoczne publicznie.**</span><span class="sxs-lookup"><span data-stu-id="21d4e-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="21d4e-106">HoloLens są wyświetlane na platformie docs.microsoft.com, która używa GitHub markdown z funkcjami parserów Markdig.</span><span class="sxs-lookup"><span data-stu-id="21d4e-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="21d4e-107">Zawartość edytowana w tym repo zostanie sformatowana na strony ze stylizowaną zawartością, które są wyświetlane w /hololens.</span><span class="sxs-lookup"><span data-stu-id="21d4e-107">The content you edit in this repo gets formatted into stylized pages that show up at /hololens.</span></span>

<span data-ttu-id="21d4e-108">Ta strona zawiera podstawowe kroki i wskazówki dotyczące współtworowania oraz linki do podstaw dotyczących znaczników Markdown.</span><span class="sxs-lookup"><span data-stu-id="21d4e-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="21d4e-109">Dziękujemy za Twój wkład!</span><span class="sxs-lookup"><span data-stu-id="21d4e-109">Thanks for your contribution!</span></span>

## <a name="available-repos"></a><span data-ttu-id="21d4e-110">Dostępne repos</span><span class="sxs-lookup"><span data-stu-id="21d4e-110">Available repos</span></span>

| <span data-ttu-id="21d4e-111">Nazwa repozytorium</span><span class="sxs-lookup"><span data-stu-id="21d4e-111">Repository name</span></span> | <span data-ttu-id="21d4e-112">Adres URL</span><span class="sxs-lookup"><span data-stu-id="21d4e-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="21d4e-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="21d4e-113">HoloLens</span></span> | [<span data-ttu-id="21d4e-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="21d4e-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="21d4e-115">Rzeczywistość mieszana</span><span class="sxs-lookup"><span data-stu-id="21d4e-115">Mixed Reality</span></span> | [<span data-ttu-id="21d4e-116">MicrosoftDocs/mixed-reality</span><span class="sxs-lookup"><span data-stu-id="21d4e-116">MicrosoftDocs/mixed-reality</span></span>](/windows/mixed-reality) |
| <span data-ttu-id="21d4e-117">Przewodnik po entuzjaściach VR</span><span class="sxs-lookup"><span data-stu-id="21d4e-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="21d4e-118">MicrosoftDocs/mixed-reality/nakieruj</span><span class="sxs-lookup"><span data-stu-id="21d4e-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a><span data-ttu-id="21d4e-119">Przed rozpoczęciem</span><span class="sxs-lookup"><span data-stu-id="21d4e-119">Before you start</span></span>

<span data-ttu-id="21d4e-120">Jeśli jeszcze go nie masz, musisz utworzyć konto GitHub [konto.](https://github.com/join)</span><span class="sxs-lookup"><span data-stu-id="21d4e-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="21d4e-121">Jeśli jesteś pracownikiem firmy Microsoft, połącz swoje konto GitHub z aliasem firmy Microsoft w portalu [Microsoft Open Source.](https://repos.opensource.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="21d4e-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="21d4e-122">Dołącz do **organizacji "Microsoft"** **i "MicrosoftDocs".**</span><span class="sxs-lookup"><span data-stu-id="21d4e-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="21d4e-123">Podczas konfigurowania konta GitHub zalecane są również następujące środki ostrożności:</span><span class="sxs-lookup"><span data-stu-id="21d4e-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="21d4e-124">Utwórz silne [hasło dla konta GitHub konto.](https://github.com/settings/admin)</span><span class="sxs-lookup"><span data-stu-id="21d4e-124">Create a [strong password for your GitHub account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="21d4e-125">Włącz [uwierzytelnianie dwuskładnikowe.](https://github.com/settings/two_factor_authentication/configure)</span><span class="sxs-lookup"><span data-stu-id="21d4e-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="21d4e-126">Zapisz [kody odzyskiwania w](https://github.com/settings/auth/recovery-codes) bezpiecznym miejscu.</span><span class="sxs-lookup"><span data-stu-id="21d4e-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="21d4e-127">Zaktualizuj ustawienia [profilu publicznego.](https://github.com/settings/profile)</span><span class="sxs-lookup"><span data-stu-id="21d4e-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="21d4e-128">Ustaw swoją nazwę i rozważ ustawienie opcji Publiczny *adres e-mail* na Nie *pokazuj mojego adresu e-mail.*</span><span class="sxs-lookup"><span data-stu-id="21d4e-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="21d4e-129">Zalecamy przekazanie obrazu profilu, ponieważ miniatura jest wyświetlana na stronach dokumentów, które współtworzsz.</span><span class="sxs-lookup"><span data-stu-id="21d4e-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="21d4e-130">Jeśli planujesz używać wiersza polecenia, rozważ skonfigurowanie usługi [Git Menedżer poświadczeń dla Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span><span class="sxs-lookup"><span data-stu-id="21d4e-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="21d4e-131">Dzięki temu nie będzie trzeba wprowadzać hasła za każdym razem, gdy wprowadzasz wkład.</span><span class="sxs-lookup"><span data-stu-id="21d4e-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="21d4e-132">System publikowania jest powiązany z GitHub, dlatego te kroki są ważne.</span><span class="sxs-lookup"><span data-stu-id="21d4e-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="21d4e-133">Zostaniesz wymieniony jako autor lub współautor każdego artykułu przy użyciu GitHub aliasu.</span><span class="sxs-lookup"><span data-stu-id="21d4e-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <a name="editing-an-existing-article"></a><span data-ttu-id="21d4e-134">Edytowanie istniejącego artykułu</span><span class="sxs-lookup"><span data-stu-id="21d4e-134">Editing an existing article</span></span>

<span data-ttu-id="21d4e-135">Użyj następującego przepływu pracy, aby wprowadzić aktualizacje *istniejącego* artykułu za pośrednictwem GitHub w przeglądarce internetowej:</span><span class="sxs-lookup"><span data-stu-id="21d4e-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="21d4e-136">Przejdź do artykułu, który chcesz edytować, w folderze "mixed-reality-docs".</span><span class="sxs-lookup"><span data-stu-id="21d4e-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>

2. <span data-ttu-id="21d4e-137">Wybierz przycisk edycji (ikona ołówka) w prawym górnym rogu, co spowoduje automatyczne rozgałęzienie gałęzi jednorazowej poza gałęzią "master".</span><span class="sxs-lookup"><span data-stu-id="21d4e-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![Edytowanie artykułu.](images/editpage.png)
   
3. <span data-ttu-id="21d4e-139">Edytuj zawartość artykułu zgodnie z [tematem "Podstawy markdown".](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="21d4e-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>

4. <span data-ttu-id="21d4e-140">Zaktualizuj metadane w górnej części każdego artykułu:</span><span class="sxs-lookup"><span data-stu-id="21d4e-140">Update metadata at the top of each article:</span></span>

   * <span data-ttu-id="21d4e-141">**title**: tytuł strony wyświetlany na karcie przeglądarki podczas wyświetlania artykułu.</span><span class="sxs-lookup"><span data-stu-id="21d4e-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="21d4e-142">Tytuły stron są używane do optymalizacji pod kątem wyszukiwarek i indeksowania, więc nie zmieniaj tytułu, chyba że jest to konieczne (chociaż jest to mniej krytyczne, zanim dokumentacja stanie się publiczna).</span><span class="sxs-lookup"><span data-stu-id="21d4e-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="21d4e-143">**description:** Napisz krótki opis zawartości artykułu, który przyspiesza optymalizację pod kątem wyszukiwarek i odnajdywanie.</span><span class="sxs-lookup"><span data-stu-id="21d4e-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="21d4e-144">**author:** jeśli jesteś głównym właścicielem strony, dodaj tutaj GitHub alias.</span><span class="sxs-lookup"><span data-stu-id="21d4e-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="21d4e-145">**ms.author:** jeśli jesteś głównym właścicielem strony, dodaj tutaj swój alias firmy Microsoft (nie potrzebujesz @microsoft.com tylko aliasu ).</span><span class="sxs-lookup"><span data-stu-id="21d4e-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="21d4e-146">**ms.date:** zaktualizuj datę, jeśli dodajesz główną zawartość do strony, ale nie dla poprawek, takich jak wyjaśnienie, formatowanie, gramatyka lub pisownia.</span><span class="sxs-lookup"><span data-stu-id="21d4e-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="21d4e-147">**keywords:** słowa kluczowe wspomagają optymalizację pod kątem wyszukiwarek.</span><span class="sxs-lookup"><span data-stu-id="21d4e-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="21d4e-148">Dodaj słowa kluczowe rozdzielone przecinkiem i spacją, które są specyficzne dla Twojego artykułu, ale nie będą interpunkcją po ostatnim sdaniu kluczowym na liście.</span><span class="sxs-lookup"><span data-stu-id="21d4e-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="21d4e-149">Nie musisz dodawać globalnych słów kluczowych, które mają zastosowanie do wszystkich artykułów, ponieważ są one zarządzane w innym miejscu.</span><span class="sxs-lookup"><span data-stu-id="21d4e-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
   
5. <span data-ttu-id="21d4e-150">Po zakończeniu edycji artykułu przewiń w dół i wybierz pozycję **Zaproponuj zmianę pliku.**</span><span class="sxs-lookup"><span data-stu-id="21d4e-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>

6. <span data-ttu-id="21d4e-151">Na następnej stronie wybierz pozycję **Utwórz żądanie ściągnięć,** aby scalić automatycznie utworzoną gałąź z gałęzią "master".</span><span class="sxs-lookup"><span data-stu-id="21d4e-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>

7. <span data-ttu-id="21d4e-152">Powtórz powyższe kroki dla następnego artykułu, który chcesz edytować.</span><span class="sxs-lookup"><span data-stu-id="21d4e-152">Repeat the steps above for the next article you want to edit.</span></span>

## <a name="renaming-or-deleting-an-existing-article"></a><span data-ttu-id="21d4e-153">Zmiana nazwy lub usunięcie istniejącego artykułu</span><span class="sxs-lookup"><span data-stu-id="21d4e-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="21d4e-154">Jeśli zmiana spowoduje zmianę nazwy lub usunięcie istniejącego artykułu, pamiętaj o dodaniu przekierowania.</span><span class="sxs-lookup"><span data-stu-id="21d4e-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="21d4e-155">Dzięki temu każda osoba mająca link do istniejącego artykułu nadal będzie w odpowiednim miejscu.</span><span class="sxs-lookup"><span data-stu-id="21d4e-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="21d4e-156">Przekierowania są zarządzane przez .openpublishing.redirection.jsw pliku w katalogu głównym w repo.</span><span class="sxs-lookup"><span data-stu-id="21d4e-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="21d4e-157">Aby dodać przekierowanie do .openpublishing.redirection.js, dodaj wpis do `redirections` tablicy:</span><span class="sxs-lookup"><span data-stu-id="21d4e-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="21d4e-158">To `source_path` względna ścieżka repozytorium do starego artykułu, który usuwasz.</span><span class="sxs-lookup"><span data-stu-id="21d4e-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="21d4e-159">Upewnij się, że ścieżka rozpoczyna się od i `mixed-reality-docs` kończy się na `.md` .</span><span class="sxs-lookup"><span data-stu-id="21d4e-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>

- <span data-ttu-id="21d4e-160">To `redirect_url` względny publiczny adres URL ze starego artykułu do nowego artykułu.</span><span class="sxs-lookup"><span data-stu-id="21d4e-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="21d4e-161">Upewnij się, że ten adres URL **nie** zawiera adresu lub , ponieważ odnosi się on do publicznego adresu URL, a `mixed-reality-docs` nie ścieżki `.md` repozytorium.</span><span class="sxs-lookup"><span data-stu-id="21d4e-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="21d4e-162">Tworzenie linków do sekcji w nowym artykule przy użyciu `#section` jest dozwolone.</span><span class="sxs-lookup"><span data-stu-id="21d4e-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="21d4e-163">W razie potrzeby możesz również użyć ścieżki bezwzględnej do innej witryny.</span><span class="sxs-lookup"><span data-stu-id="21d4e-163">You can also use an absolute path to another site here, if necessary.</span></span>

- <span data-ttu-id="21d4e-164">`redirect_document_id` wskazuje, czy chcesz zachować identyfikator dokumentu z poprzedniego pliku.</span><span class="sxs-lookup"><span data-stu-id="21d4e-164">`redirect_document_id` indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="21d4e-165">Wartość domyślna to `false`.</span><span class="sxs-lookup"><span data-stu-id="21d4e-165">The default is `false`.</span></span> <span data-ttu-id="21d4e-166">Użyj `true` , jeśli chcesz zachować wartość `ms.documentid` atrybutu z przekierowanego artykułu.</span><span class="sxs-lookup"><span data-stu-id="21d4e-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="21d4e-167">Jeśli zachowasz identyfikator dokumentu, dane, takie jak wyświetlenia stron i rankingi, zostaną przeniesione do artykułu docelowego.</span><span class="sxs-lookup"><span data-stu-id="21d4e-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="21d4e-168">Zrób to, jeśli przekierowanie jest przede wszystkim zmianą nazwy, a nie wskaźnikiem do innego artykułu, który obejmuje tylko część tej samej zawartości.</span><span class="sxs-lookup"><span data-stu-id="21d4e-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="21d4e-169">Jeśli dodasz przekierowanie, pamiętaj również o usunięciu starego pliku.</span><span class="sxs-lookup"><span data-stu-id="21d4e-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <a name="creating-a-new-article"></a><span data-ttu-id="21d4e-170">Tworzenie nowego artykułu</span><span class="sxs-lookup"><span data-stu-id="21d4e-170">Creating a new article</span></span>

<span data-ttu-id="21d4e-171">Użyj następującego przepływu *pracy, aby utworzyć nowe artykuły w* repo dokumentacji za pośrednictwem GitHub w przeglądarce internetowej:</span><span class="sxs-lookup"><span data-stu-id="21d4e-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="21d4e-172">Utwórz widelec z gałęzi "master" MicrosoftDocs/mixed-reality (przy użyciu przycisku **Fork** w prawym górnym rogu).</span><span class="sxs-lookup"><span data-stu-id="21d4e-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![Rozgałęzienie gałęzi głównej.](images/forkbranch.png)
   
2. <span data-ttu-id="21d4e-174">W folderze "mixed-reality-docs" wybierz pozycję **Utwórz nowy plik** w prawym górnym rogu.</span><span class="sxs-lookup"><span data-stu-id="21d4e-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>

3. <span data-ttu-id="21d4e-175">Utwórz nazwę strony artykułu (użyj łączników zamiast spacji i nie używaj znaków interpunkcji ani apostrofów) i dołącz ".md"</span><span class="sxs-lookup"><span data-stu-id="21d4e-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![Nadaj nowej stronie nazwę.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   ><span data-ttu-id="21d4e-177">Pamiętaj, aby utworzyć nowy artykuł z folderu "mixed-reality-docs".</span><span class="sxs-lookup"><span data-stu-id="21d4e-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="21d4e-178">Możesz to potwierdzić, sprawdzając tekst "/mixed-reality-docs/" w nowym wierszu nazwy pliku.</span><span class="sxs-lookup"><span data-stu-id="21d4e-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="21d4e-179">W górnej części nowej strony dodaj następujący blok metadanych:</span><span class="sxs-lookup"><span data-stu-id="21d4e-179">At the top of your new page, add the following metadata block:</span></span>

   ```md
   ---
   title:
   description:
   author:
   ms.author:
   ms.date:
   ms.topic: article
   keywords:
   ---
   ```

5. <span data-ttu-id="21d4e-180">Wypełnij odpowiednie pola metadanych zgodnie z instrukcjami w [powyższej sekcji](#editing-an-existing-article).</span><span class="sxs-lookup"><span data-stu-id="21d4e-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>

6. <span data-ttu-id="21d4e-181">Pisanie zawartości artykułu przy użyciu [podstaw znaczników Markdown.](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="21d4e-181">Write article content using [Markdown basics](#markdown-basics).</span></span>

7. <span data-ttu-id="21d4e-182">Dodaj `## See also` sekcję w dolnej części artykułu z linkami do innych odpowiednich artykułów.</span><span class="sxs-lookup"><span data-stu-id="21d4e-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>

8. <span data-ttu-id="21d4e-183">Po zakończeniu wybierz pozycję **Zat zatwierdzeniu nowego pliku.**</span><span class="sxs-lookup"><span data-stu-id="21d4e-183">When finished, select **Commit new file**.</span></span>

9. <span data-ttu-id="21d4e-184">Wybierz **pozycję Nowe żądanie** ściągnięcie i scal gałąź "master" twojego widelecu z gałęzią "master" MicrosoftDocs/mixed-reality (upewnij się, że strzałka wskazuje prawidłowy sposób).</span><span class="sxs-lookup"><span data-stu-id="21d4e-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Tworzenie żądania ściągnnięcia z twojego widelec do dokumentów MicrosoftDocs/mixed-reality](images/pr-to-master.png)

## <a name="markdown-basics"></a><span data-ttu-id="21d4e-186">Podstawy języka znaczników markdown</span><span class="sxs-lookup"><span data-stu-id="21d4e-186">Markdown basics</span></span>

<span data-ttu-id="21d4e-187">Następujące zasoby pomogą Ci dowiedzieć się, jak edytować dokumentację przy użyciu języka Markdown:</span><span class="sxs-lookup"><span data-stu-id="21d4e-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="21d4e-188">Podstawy języka znaczników markdown</span><span class="sxs-lookup"><span data-stu-id="21d4e-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="21d4e-189">Dodatkowe zasoby dotyczące pisania znaczników markdown dla docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="21d4e-189">Additional resources for writing Markdown for docs.microsoft.com</span></span>](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a><span data-ttu-id="21d4e-190">Dodawanie tabel</span><span class="sxs-lookup"><span data-stu-id="21d4e-190">Adding tables</span></span>

<span data-ttu-id="21d4e-191">Ze względu na sposób docs.microsoft.com stylów tabele nie będą mieć obramowań ani stylów niestandardowych, nawet jeśli spróbujesz użyć arkuszy CSS w tekście.</span><span class="sxs-lookup"><span data-stu-id="21d4e-191">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="21d4e-192">Wygląda na to, że będzie działać przez krótki czas, ale ostatecznie platforma będzie odebrać style z tabeli.</span><span class="sxs-lookup"><span data-stu-id="21d4e-192">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="21d4e-193">Dlatego zaplanuj tabele z wyprzedzeniem i zachowaj prostotę.</span><span class="sxs-lookup"><span data-stu-id="21d4e-193">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="21d4e-194">[Oto witryna, która ułatwia tabele markdown.](https://www.tablesgenerator.com/markdown_tables)</span><span class="sxs-lookup"><span data-stu-id="21d4e-194">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="21d4e-195">Rozszerzenie [Docs Markdown dla](/teamblog/docs-extension) usługi Visual Studio Code ułatwia również generowanie tabel, jeśli używasz usługi [Visual Studio Code (zobacz poniżej)](#using-visual-studio-code) do edytowania dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="21d4e-195">The [Docs Markdown Extension for Visual Studio Code](/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <a name="adding-images"></a><span data-ttu-id="21d4e-196">Dodawanie obrazów</span><span class="sxs-lookup"><span data-stu-id="21d4e-196">Adding images</span></span>

<span data-ttu-id="21d4e-197">Musisz przekazać obrazy do folderu "mixed-reality-docs/images" w repocie, a następnie odwołać się do nich odpowiednio w artykule.</span><span class="sxs-lookup"><span data-stu-id="21d4e-197">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="21d4e-198">Obrazy będą automatycznie wyświetlane w pełnym rozmiarze, co oznacza, że duże obrazy wypełnią całą szerokość artykułu.</span><span class="sxs-lookup"><span data-stu-id="21d4e-198">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="21d4e-199">Zalecamy wstępne rozmiarów obrazów przed ich przekazaniem.</span><span class="sxs-lookup"><span data-stu-id="21d4e-199">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="21d4e-200">Zalecana szerokość wynosi od 600 do 700 pikseli, chociaż rozmiar należy odpowiednio w górę lub w dół, jeśli jest to gęsty zrzut ekranu lub część zrzutu ekranu.</span><span class="sxs-lookup"><span data-stu-id="21d4e-200">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="21d4e-201">Przed scaleniem obrazy można przekazywać tylko do swojego rozdętego repo.</span><span class="sxs-lookup"><span data-stu-id="21d4e-201">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="21d4e-202">Dlatego jeśli planujesz dodawanie obrazów do artykułu, musisz najpierw użyć usługi [Visual Studio Code,](#using-visual-studio-code) aby dodać obrazy do folderu "images" twojego widelecu lub upewnić się, że w przeglądarce internetowej zostały wykonane następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="21d4e-202">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="21d4e-203">Forked the MicrosoftDocs/mixed-reality repo (Forked the MicrosoftDocs/mixed-reality repo).</span><span class="sxs-lookup"><span data-stu-id="21d4e-203">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="21d4e-204">Zedytował artykuł w twoim widełku.</span><span class="sxs-lookup"><span data-stu-id="21d4e-204">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="21d4e-205">Przekazane obrazy, do których odwołujesz się w artykule, do folderu "mixed-reality-docs/images" w twoim widełku.</span><span class="sxs-lookup"><span data-stu-id="21d4e-205">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="21d4e-206">Utworzono **żądanie ściągnięć** w celu scalenia twojego widelecu z gałęzią "master" MicrosoftDocs/mixed-reality.</span><span class="sxs-lookup"><span data-stu-id="21d4e-206">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="21d4e-207">Aby dowiedzieć się, jak skonfigurować własne forked repo, postępuj zgodnie z instrukcjami [dotyczącymi tworzenia nowego artykułu.](#creating-a-new-article)</span><span class="sxs-lookup"><span data-stu-id="21d4e-207">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <a name="previewing-your-work"></a><span data-ttu-id="21d4e-208">Wyświetlanie podglądu pracy</span><span class="sxs-lookup"><span data-stu-id="21d4e-208">Previewing your work</span></span>

<span data-ttu-id="21d4e-209">Podczas edytowania GitHub za pośrednictwem przeglądarki  internetowej możesz wybrać kartę Podgląd w górnej części strony, aby wyświetlić podgląd pracy przed zatwierdzeniem.</span><span class="sxs-lookup"><span data-stu-id="21d4e-209">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="21d4e-210">Wyświetlanie podglądu zmian w review.docs.microsoft.com jest dostępne tylko dla pracowników firmy Microsoft</span><span class="sxs-lookup"><span data-stu-id="21d4e-210">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="21d4e-211">Pracownicy firmy Microsoft: po scaleniu twojego wkładu z gałęzią "master" możesz przejrzeć zawartość, zanim zostanie ona publicznie </hololens?branch=master>.</span><span class="sxs-lookup"><span data-stu-id="21d4e-211">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at </hololens?branch=master>.</span></span> <span data-ttu-id="21d4e-212">Znajdź swój artykuł, korzystając ze spisu treści w lewej kolumnie.</span><span class="sxs-lookup"><span data-stu-id="21d4e-212">Find your article using the table of contents in the left column.</span></span>

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a><span data-ttu-id="21d4e-213">Edytowanie w przeglądarce a edytowanie za pomocą klienta klasycznego</span><span class="sxs-lookup"><span data-stu-id="21d4e-213">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="21d4e-214">Edytowanie w przeglądarce jest najprostszym sposobem na szybkie zmiany, jednak istnieje kilka wad:</span><span class="sxs-lookup"><span data-stu-id="21d4e-214">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="21d4e-215">Sprawdzanie pisowni nie jest sprawdzane.</span><span class="sxs-lookup"><span data-stu-id="21d4e-215">You don't get spell-check.</span></span>
- <span data-ttu-id="21d4e-216">Nie ma żadnych inteligentnych linków do innych artykułów (musisz ręcznie wpisać nazwę pliku artykułu).</span><span class="sxs-lookup"><span data-stu-id="21d4e-216">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="21d4e-217">Przekazywanie obrazów referencyjnych i ich przekazywanie może być kłopotliwe.</span><span class="sxs-lookup"><span data-stu-id="21d4e-217">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="21d4e-218">Jeśli nie chcesz zajmować się tymi problemami, użyj klienta klasycznego, takiego jak [Visual Studio Code](https://code.visualstudio.com/) z kilku przydatnych [rozszerzeń](#useful-extensions) podczas współtworowania.</span><span class="sxs-lookup"><span data-stu-id="21d4e-218">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <a name="using-visual-studio-code"></a><span data-ttu-id="21d4e-219">Korzystanie z narzędzia Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="21d4e-219">Using Visual Studio Code</span></span>

<span data-ttu-id="21d4e-220">Z przyczyn wymienionych [powyżej możesz](#editing-in-the-browser-vs-editing-with-a-desktop-client)edytować dokumentację za pomocą klienta klasycznego zamiast przeglądarki internetowej.</span><span class="sxs-lookup"><span data-stu-id="21d4e-220">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="21d4e-221">Zalecamy używanie [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="21d4e-221">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <a name="setup"></a><span data-ttu-id="21d4e-222">Konfigurowanie</span><span class="sxs-lookup"><span data-stu-id="21d4e-222">Setup</span></span>

<span data-ttu-id="21d4e-223">Wykonaj następujące kroki, aby skonfigurować Visual Studio Code pracy z tym repo:</span><span class="sxs-lookup"><span data-stu-id="21d4e-223">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="21d4e-224">W przeglądarce internetowej:</span><span class="sxs-lookup"><span data-stu-id="21d4e-224">In a web browser:</span></span>
    1. <span data-ttu-id="21d4e-225">Zainstaluj [oprogramowanie Git dla swojego komputera.](https://git-scm.com/downloads)</span><span class="sxs-lookup"><span data-stu-id="21d4e-225">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="21d4e-226">Zainstaluj [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="21d4e-226">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="21d4e-227">[Jeśli jeszcze tego nie zdążę, wydychaj dokumenty MicrosoftDocs/rzeczywistość](#creating-a-new-article) mieszaną.</span><span class="sxs-lookup"><span data-stu-id="21d4e-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="21d4e-228">W twoim widelce wybierz pozycję **Klonuj lub pobierz i** skopiuj adres URL.</span><span class="sxs-lookup"><span data-stu-id="21d4e-228">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="21d4e-229">Utwórz lokalny klon twojego widelecu w Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="21d4e-229">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="21d4e-230">W menu **View (Widok)** wybierz pozycję **Command Palette (Paleta poleceń).**</span><span class="sxs-lookup"><span data-stu-id="21d4e-230">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="21d4e-231">Wpisz "Git: Clone".</span><span class="sxs-lookup"><span data-stu-id="21d4e-231">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="21d4e-232">Wklej skopiowany adres URL.</span><span class="sxs-lookup"><span data-stu-id="21d4e-232">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="21d4e-233">Wybierz miejsce zapisania klonu na komputerze.</span><span class="sxs-lookup"><span data-stu-id="21d4e-233">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="21d4e-234">Wybierz **pozycję Otwórz repo** w oknie podręcznym.</span><span class="sxs-lookup"><span data-stu-id="21d4e-234">Select **Open repo** in the pop-up.</span></span>

### <a name="editing-documentation"></a><span data-ttu-id="21d4e-235">Edytowanie dokumentacji</span><span class="sxs-lookup"><span data-stu-id="21d4e-235">Editing documentation</span></span>

<span data-ttu-id="21d4e-236">Użyj następującego przepływu pracy, aby wprowadzić zmiany w dokumentacji za pomocą Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="21d4e-236">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="21d4e-237">Wszystkie powyższe wskazówki dotyczące [edytowania](#editing-an-existing-article) i [tworzenia](#creating-a-new-article) artykułów oraz podstawowe informacje dotyczące edytowania znaczników [Markdown](#markdown-basics)mają zastosowanie również w przypadku Visual Studio Code artykułów.</span><span class="sxs-lookup"><span data-stu-id="21d4e-237">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="21d4e-238">Upewnij się, że sklonowane widelec jest aktualny z oficjalnym repo.</span><span class="sxs-lookup"><span data-stu-id="21d4e-238">Make sure your cloned fork is up to date with the official repo.</span></span>

   1. <span data-ttu-id="21d4e-239">W przeglądarce internetowej utwórz żądanie ściągnięcie, aby zsynchronizować ostatnie zmiany od innych współautorów w folderze MicrosoftDocs/"master" rzeczywistości mieszanej do twojego widelecu (upewnij się, że strzałka wskazuje właściwy sposób).</span><span class="sxs-lookup"><span data-stu-id="21d4e-239">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![Synchronizowanie zmian z dokumentu MicrosoftDocs/rzeczywistości mieszanej do twojego widelecu](images/sync-repos.png)
      
   2. <span data-ttu-id="21d4e-241">W Visual Studio Code wybierz przycisk synchronizacji, aby zsynchronizować nowo zaktualizowane widelec z klonem lokalnym.</span><span class="sxs-lookup"><span data-stu-id="21d4e-241">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![Kliknij obraz przycisku synchronizacji](images/sync-clone.png)
      
2. <span data-ttu-id="21d4e-243&quot;>Twórz lub edytuj artykuły w sklonowanym repocie przy użyciu Visual Studio Code.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;21d4e-243&quot;>Create or edit articles in your cloned repo using Visual Studio Code.</span></span>

   1. <span data-ttu-id=&quot;21d4e-244&quot;>Edytuj co najmniej jeden artykuł (w razie potrzeby dodaj obrazy do folderu &quot;images").</span><span class="sxs-lookup"><span data-stu-id="21d4e-244">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   
   2. <span data-ttu-id="21d4e-245">**Zapisz** zmiany w **Eksploratorze**.</span><span class="sxs-lookup"><span data-stu-id="21d4e-245">**Save** changes in **Explorer**.</span></span>
      
      ![Wybieranie opcji "Zapisz wszystko" w Eksploratorze](images/explorer-save.png)
      
   3. <span data-ttu-id="21d4e-247">**Zat zatwierdzanie** wszystkich **zmian w kontroli kodu źródłowego** (po wyświetleniu monitu napisz komunikat zatwierdzenia).</span><span class="sxs-lookup"><span data-stu-id="21d4e-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
   
      ![Wybieranie opcji "Zat zatwierdzanie wszystkich" w kontrolce kodu źródłowego](images/source-control-commit.png)
      
   4. <span data-ttu-id="21d4e-249">Wybierz przycisk **synchronizacji,** aby zsynchronizować zmiany z powrotem do źródła (Twoje widelec na GitHub).</span><span class="sxs-lookup"><span data-stu-id="21d4e-249">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![Kliknij przycisk synchronizacji](images/sync-back.png)
      
3. <span data-ttu-id="21d4e-251">W przeglądarce internetowej utwórz żądanie ściągnięcie, aby zsynchronizować nowe zmiany w twoim widełku z dokumentami MicrosoftDocs/"master" rzeczywistości mieszanej (upewnij się, że strzałka wskazuje prawidłowy sposób).</span><span class="sxs-lookup"><span data-stu-id="21d4e-251">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Tworzenie żądania ściągnęcie z twojego widelecu do dokumentu MicrosoftDocs/rzeczywistości mieszanej](images/pr-to-master.png)

### <a name="useful-extensions"></a><span data-ttu-id="21d4e-253">Przydatne rozszerzenia</span><span class="sxs-lookup"><span data-stu-id="21d4e-253">Useful extensions</span></span>

<span data-ttu-id="21d4e-254">Następujące rozszerzenia Visual Studio Code są przydatne podczas edytowania dokumentacji:</span><span class="sxs-lookup"><span data-stu-id="21d4e-254">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="21d4e-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span><span class="sxs-lookup"><span data-stu-id="21d4e-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="21d4e-256">Wyszukaj przekazane obrazy i przywołuj je.</span><span class="sxs-lookup"><span data-stu-id="21d4e-256">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="21d4e-257">Dodaj formatowanie, takie jak listy, tabele i wywołania specyficzne dla dokumentów, takie jak `>[!NOTE]` .</span><span class="sxs-lookup"><span data-stu-id="21d4e-257">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="21d4e-258">Wyszukaj linki wewnętrzne i zakładki (linki do określonych sekcji na stronie) i odwołuj się do tych linków.</span><span class="sxs-lookup"><span data-stu-id="21d4e-258">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="21d4e-259">Błędy formatowania są wyróżnione (umieść wskaźnik myszy nad błędem, aby dowiedzieć się więcej).</span><span class="sxs-lookup"><span data-stu-id="21d4e-259">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="21d4e-260">[Moduł sprawdzania pisowni kodu](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) — wyrazy z błędami pisowni zostaną podkreślone. kliknij prawym przyciskiem myszy wyraz z błędami pisowni, aby go zmienić lub zapisać w słowniku.</span><span class="sxs-lookup"><span data-stu-id="21d4e-260">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
