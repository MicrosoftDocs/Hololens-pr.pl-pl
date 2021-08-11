---
title: Instrukcje dotyczące współtworowania
description: Dowiedz się, jak współtwolić HoloLens do dokumentów na platformie docs.microsoft.com przy użyciu GitHub języka Markdown.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: cbf0b2e4b61f006d0b5d7d74d3d81a4b33cfd6d8c2e124288b17959d54a5a1ad
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665070"
---
# <a name="contributing-to-the-hololens-documentation"></a>Współtwoowanie dokumentacji HoloLens dokumentacji

Witamy w [HoloLens dokumentacji!](https://github.com/MicrosoftDocs/Hololens) Wszystkie artykuły, które utworzysz lub edytujesz w tym repo, **będą widoczne publicznie.** 

HoloLens są wyświetlane na platformie docs.microsoft.com, która używa GitHub markdown z funkcjami parserów Markdig. Zawartość edytowana w tym repo zostanie sformatowana na strony ze stylizowaną zawartością, które są wyświetlane w /hololens.

Ta strona zawiera podstawowe kroki i wskazówki dotyczące współtworowania oraz linki do podstaw dotyczących znaczników Markdown. Dziękujemy za Twój wkład!

## <a name="available-repos"></a>Dostępne repos

| Nazwa repozytorium | Adres URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Rzeczywistość mieszana | [MicrosoftDocs/mixed-reality](/windows/mixed-reality) |
| Przewodnik po entuzjaściach VR | [MicrosoftDocs/mixed-reality/nakieruj](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a>Przed rozpoczęciem

Jeśli jeszcze go nie masz, musisz utworzyć konto GitHub [konto.](https://github.com/join)

>[!NOTE]
>Jeśli jesteś pracownikiem firmy Microsoft, połącz swoje konto GitHub z aliasem firmy Microsoft w portalu [Microsoft Open Source.](https://repos.opensource.microsoft.com/) Dołącz do **organizacji "Microsoft"** **i "MicrosoftDocs".**

Podczas konfigurowania konta GitHub zalecane są również następujące środki ostrożności:
- Utwórz silne [hasło dla konta GitHub konto.](https://github.com/settings/admin)
- Włącz [uwierzytelnianie dwuskładnikowe.](https://github.com/settings/two_factor_authentication/configure)
- Zapisz [kody odzyskiwania w](https://github.com/settings/auth/recovery-codes) bezpiecznym miejscu.
- Zaktualizuj ustawienia [profilu publicznego.](https://github.com/settings/profile)
   - Ustaw swoją nazwę i rozważ ustawienie opcji Publiczny *adres e-mail* na Nie *pokazuj mojego adresu e-mail.*
   - Zalecamy przekazanie obrazu profilu, ponieważ miniatura jest wyświetlana na stronach dokumentów, które współtworzsz.
- Jeśli planujesz używać wiersza polecenia, rozważ skonfigurowanie usługi [Git Menedżer poświadczeń dla Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest). Dzięki temu nie będzie trzeba wprowadzać hasła za każdym razem, gdy wprowadzasz wkład.

System publikowania jest powiązany z GitHub, dlatego te kroki są ważne. Zostaniesz wymieniony jako autor lub współautor każdego artykułu przy użyciu GitHub aliasu.

## <a name="editing-an-existing-article"></a>Edytowanie istniejącego artykułu

Użyj następującego przepływu pracy, aby wprowadzić aktualizacje *istniejącego* artykułu za pośrednictwem GitHub w przeglądarce internetowej:

1. Przejdź do artykułu, który chcesz edytować, w folderze "mixed-reality-docs".

2. Wybierz przycisk edycji (ikona ołówka) w prawym górnym rogu.

   ![Edytowanie artykułu.](images/editpage.png)

   Spowoduje to automatyczne rozgałęzienie gałęzi jednorazowej poza gałęzią domyślną _master_.

   > [!NOTE]
   > Ten artykuł zawiera odwołania do _wzorca_, terminu, który nie jest już używany przez firmę Microsoft. Po usunięciu terminu z oprogramowania usuniemy go z tego artykułu.
   
3. Edytuj zawartość artykułu zgodnie z podstawowymi ustawieniami [znaczników Markdown.](#markdown-basics)

4. Zaktualizuj metadane w górnej części każdego artykułu:

   * **title**: tytuł strony wyświetlany na karcie przeglądarki podczas wyświetlania artykułu. Tytuły stron są używane do optymalizacji pod kątem wyszukiwarek i indeksowania, więc nie zmieniaj tytułu, chyba że jest to konieczne (chociaż jest to mniej krytyczne, zanim dokumentacja stanie się publiczna).
   * **description:** Napisz krótki opis zawartości artykułu, który przyspiesza optymalizację pod kątem wyszukiwarek i odnajdywanie.
   * **author:** jeśli jesteś głównym właścicielem strony, dodaj tutaj GitHub alias.
   * **ms.author:** jeśli jesteś głównym właścicielem strony, dodaj tutaj swój alias firmy Microsoft (nie potrzebujesz @microsoft.com tylko aliasu ).
   * **ms.date:** zaktualizuj datę, jeśli dodajesz główną zawartość do strony, ale nie dla poprawek, takich jak wyjaśnienie, formatowanie, gramatyka lub pisownia.
   * **keywords:** Słowa kluczowe wspomagają optymalizację pod kątem wyszukiwarek. Dodaj słowa kluczowe rozdzielone przecinkiem i spacją, które są specyficzne dla Twojego artykułu, ale nie będą interpunkcją po ostatnim sdaniu kluczowym na liście. Nie musisz dodawać globalnych słów kluczowych, które mają zastosowanie do wszystkich artykułów, ponieważ są one zarządzane w innym miejscu. 
   
5. Po zakończeniu edycji artykułu przewiń w dół i wybierz pozycję **Zaproponuj zmianę pliku.**

6. Na następnej stronie wybierz pozycję Utwórz żądanie **ściągnięć,** aby scalić automatycznie utworzoną gałąź z gałęzią domyślną _master_.

7. Powtórz powyższe kroki dla następnego artykułu, który chcesz edytować.

## <a name="renaming-or-deleting-an-existing-article"></a>Zmiana nazwy lub usunięcie istniejącego artykułu

Jeśli zmiana spowoduje zmianę nazwy lub usunięcie istniejącego artykułu, pamiętaj o dodaniu przekierowania. Dzięki temu każda osoba mająca link do istniejącego artykułu nadal będzie w odpowiednim miejscu. Przekierowania są zarządzane przez .openpublishing.redirection.jsw pliku w katalogu głównym w repo.

Aby dodać przekierowanie do .openpublishing.redirection.js, dodaj wpis do `redirections` tablicy:

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- To `source_path` względna ścieżka repozytorium do starego artykułu, który usuwasz. Upewnij się, że ścieżka rozpoczyna się od i `mixed-reality-docs` kończy się na `.md` .

- To `redirect_url` względny publiczny adres URL ze starego artykułu do nowego artykułu. Upewnij się, że ten adres URL **nie** zawiera adresu lub , ponieważ odnosi się on do publicznego adresu URL, a `mixed-reality-docs` nie ścieżki `.md` repozytorium. Tworzenie linków do sekcji w nowym artykule przy użyciu `#section` jest dozwolone. W razie potrzeby możesz również użyć ścieżki bezwzględnej do innej witryny.

- `redirect_document_id` wskazuje, czy chcesz zachować identyfikator dokumentu z poprzedniego pliku. Wartość domyślna to `false`. Użyj `true` , jeśli chcesz zachować wartość `ms.documentid` atrybutu z przekierowanego artykułu. Jeśli zachowasz identyfikator dokumentu, dane, takie jak wyświetlenia stron i rankingi, zostaną przeniesione do artykułu docelowego. Zrób to, jeśli przekierowanie jest przede wszystkim zmianą nazwy, a nie wskaźnikiem do innego artykułu, który obejmuje tylko część tej samej zawartości.

Jeśli dodasz przekierowanie, pamiętaj również o usunięciu starego pliku.

## <a name="creating-a-new-article"></a>Tworzenie nowego artykułu

Użyj następującego przepływu *pracy, aby utworzyć nowe artykuły w* repo dokumentacji za pośrednictwem GitHub w przeglądarce internetowej:

1. Utwórz widelec z gałęzi domyślnej _master (master)_ dokumentu MicrosoftDocs/rzeczywistości mieszanej przy użyciu przycisku **Fork** (Utwórz widelec) w prawym górnym rogu.

   ![Rozgałęzienie gałęzi domyślnej, obecnie o nazwie "master".](images/forkbranch.png)

   > [!NOTE]
   > Ten artykuł zawiera odwołania do _wzorca_, terminu, który nie jest już używany przez firmę Microsoft. Po usunięciu terminu z oprogramowania usuniemy go z tego artykułu.
   
2. W folderze "mixed-reality-docs" wybierz pozycję **Utwórz nowy plik** w prawym górnym rogu.

3. Utwórz nazwę strony artykułu (użyj łączników zamiast spacji i nie używaj znaków interpunkcji ani apostrofów) i dołącz ".md"

   ![Nadaj nowej stronie nazwę.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >Pamiętaj, aby utworzyć nowy artykuł z folderu "mixed-reality-docs". Możesz to potwierdzić, sprawdzając tekst "/mixed-reality-docs/" w nowym wierszu nazwy pliku.

4. W górnej części nowej strony dodaj następujący blok metadanych:

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

5. Wypełnij odpowiednie pola metadanych zgodnie z wcześniejszym opisem w [artykule Edytowanie istniejącego artykułu.](#editing-an-existing-article)

6. Pisanie zawartości artykułu przy użyciu podstaw [znaczników Markdown.](#markdown-basics)

7. Dodaj `## See also` sekcję w dolnej części artykułu z linkami do innych odpowiednich artykułów.

8. Po zakończeniu wybierz pozycję **Zat zatwierdzeniu nowego pliku.**

9. Wybierz **pozycję Nowe żądanie ściągnięcie** i scal gałąź master twojego widelec z dokumentami MicrosoftDocs/wzorcem rzeczywistości mieszanej (upewnij się, że strzałka wskazuje poprawne miejsce docelowe).  

   ![Tworzenie żądania ściągnnięcia z twojego widelec do dokumentów MicrosoftDocs/mixed-reality](images/pr-to-master.png)

## <a name="markdown-basics"></a>Podstawy języka znaczników markdown

Następujące zasoby pomogą Ci dowiedzieć się, jak edytować dokumentację przy użyciu języka Markdown:

- [Podstawy języka znaczników markdown](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Dodatkowe zasoby dotyczące pisania znaczników markdown dla docs.microsoft.com](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a>Dodawanie tabel

Ze względu na sposób docs.microsoft.com stylów tabele nie będą mieć obramowań ani stylów niestandardowych, nawet jeśli spróbujesz użyć arkuszy CSS w tekście. Wygląda na to, że będzie działać przez krótki czas, ale ostatecznie platforma będzie odebrać style z tabeli. Dlatego zaplanuj tabele z wyprzedzeniem i zachowaj prostotę. Oto witryna, która ułatwia tabele markdown: [Tables Generator]]( https://www.tablesgenerator.com/markdown_tables) .

Rozszerzenie [Docs Markdown dla](/teamblog/docs-extension) usługi Visual Studio Code ułatwia również generowanie tabel, jeśli używasz usługi [Visual Studio Code (zobacz poniżej)](#using-visual-studio-code) do edytowania dokumentacji.

### <a name="adding-images"></a>Dodawanie obrazów

Musisz przekazać obrazy do folderu "mixed-reality-docs/images" w repocie, a następnie odwołać się do nich odpowiednio w artykule. Obrazy będą automatycznie wyświetlane w pełnym rozmiarze, co oznacza, że duże obrazy wypełnią całą szerokość artykułu. Zalecamy wstępne zmiany rozmiaru obrazów przed ich przekazaniem. Zalecana szerokość to od 600 do 700 pikseli, ale rozmiar należy odpowiednio w górę lub w dół, jeśli jest to gęsty zrzut ekranu lub część zrzutu ekranu.

>[!IMPORTANT]
>Obrazy można przekazywać tylko do rozdętego repo przed scaleniem. Dlatego jeśli planujesz dodawanie obrazów do artykułu, musisz najpierw użyć usługi [Visual Studio Code,](#using-visual-studio-code) aby dodać obrazy do folderu "images" twojego widelecu lub upewnić się, że w przeglądarce internetowej zostały wykonane następujące czynności:
>
>1. Forked the MicrosoftDocs/mixed-reality repo (Forked the MicrosoftDocs/mixed-reality repo).
>2. Zedytował artykuł w twoim widełku.
>3. Przekazane obrazy, do których odwołujesz się w artykule, do folderu "mixed-reality-docs/images" w twoim widełku.
>4. Utworzono **żądanie ściągnięcie** w celu scalenia twojego widelecu z gałęzią master MicrosoftDocs/mixed-reality. 
>
>Aby dowiedzieć się, jak skonfigurować własne forked repo, postępuj zgodnie z instrukcjami [dotyczącymi tworzenia nowego artykułu.](#creating-a-new-article)

## <a name="previewing-your-work"></a>Wyświetlanie podglądu pracy

Podczas edytowania GitHub za pośrednictwem przeglądarki  internetowej możesz wybrać kartę Podgląd w górnej części strony, aby wyświetlić podgląd pracy przed zatwierdzeniem. 

>[!NOTE]
>Wyświetlanie podglądu zmian w review.docs.microsoft.com jest dostępne tylko dla pracowników firmy Microsoft

Pracownicy firmy Microsoft: po scaleniu zawartości z gałęzią domyślną _master_ możesz przejrzeć zawartość, zanim przejdzie ona publicznie na adres </hololens?branch=master>. Znajdź swój artykuł, korzystając ze spisu treści w lewej kolumnie.

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a>Edytowanie w przeglądarce a edytowanie za pomocą klienta klasycznego

Edytowanie w przeglądarce jest najprostszym sposobem na szybkie zmiany, jednak istnieje kilka wad:

- Sprawdzanie pisowni nie jest sprawdzane.
- Nie ma żadnych inteligentnych linków do innych artykułów (musisz ręcznie wpisać nazwę pliku artykułu).
- Przekazywanie obrazów referencyjnych i ich przekazywanie może być kłopotliwe.

Jeśli nie chcesz zajmować się tymi problemami, użyj klienta klasycznego, takiego jak [Visual Studio Code](https://code.visualstudio.com/) z kilku przydatnych [rozszerzeń](#useful-extensions) podczas współtworowania.

## <a name="using-visual-studio-code"></a>Korzystanie z narzędzia Visual Studio Code

Z przyczyn wymienionych [powyżej możesz](#editing-in-the-browser-vs-editing-with-a-desktop-client)edytować dokumentację przy użyciu klienta klasycznego zamiast przeglądarki internetowej. Zalecamy używanie [Visual Studio Code](https://code.visualstudio.com/).

### <a name="setup"></a>Konfigurowanie

Wykonaj następujące kroki, aby skonfigurować Visual Studio Code pracy z tym repo:

1. W przeglądarce internetowej:
    1. Zainstaluj [oprogramowanie Git dla swojego komputera.](https://git-scm.com/downloads)
    2. Zainstaluj [Visual Studio Code](https://code.visualstudio.com/).
    3. [Jeśli jeszcze tego nie zdążę, wydychaj dokumenty MicrosoftDocs/rzeczywistość](#creating-a-new-article) mieszaną.
    4. W twoim widelce wybierz pozycję **Klonuj lub pobierz i** skopiuj adres URL.
2. Utwórz lokalny klon twojego widelecu w Visual Studio Code:
    1. W menu **View (Widok)** wybierz pozycję **Command Palette (Paleta poleceń).**
    2. Wpisz "Git: Clone".
    3. Wklej skopiowany adres URL.
    4. Wybierz miejsce zapisania klonu na komputerze.
    5. W **oknie podręcznym** wybierz pozycję Otwórz repo.

### <a name="editing-documentation"></a>Edytowanie dokumentacji

Użyj następującego przepływu pracy, aby wprowadzić zmiany w dokumentacji za pomocą Visual Studio Code:

>[!NOTE]
>Wszystkie powyższe wskazówki dotyczące [edytowania](#editing-an-existing-article) i [tworzenia](#creating-a-new-article) artykułów oraz podstawowe informacje dotyczące edytowania znaczników [Markdown](#markdown-basics)mają zastosowanie również w przypadku Visual Studio Code artykułów.

1. Upewnij się, że sklonowane widelec jest aktualny z oficjalnym repo.

   1. W przeglądarce internetowej utwórz żądanie ściągnięcie, aby zsynchronizować ostatnie zmiany od innych współautorów w domyślnej gałęzi MicrosoftDocs/rzeczywistości mieszanej _master_ z Twoim widelecem (upewnij się, że strzałka wskazuje poprawną stronę docelową).
      
      ![Synchronizowanie zmian z dokumentu MicrosoftDocs/rzeczywistości mieszanej do twojego widelecu](images/sync-repos.png)
      
   2. W Visual Studio Code wybierz przycisk synchronizacji, aby zsynchronizować nowo zaktualizowane widelec z klonem lokalnym.
      
      ![Kliknij obraz przycisku synchronizacji](images/sync-clone.png)
      
2. Twórz lub edytuj artykuły w sklonowanym repocie przy użyciu Visual Studio Code.

   1. Edytuj co najmniej jeden artykuł (w razie potrzeby dodaj obrazy do folderu "images").
   
   2. **Zapisz** zmiany w **Eksploratorze**.
      
      ![Wybieranie opcji "Zapisz wszystko" w Eksploratorze](images/explorer-save.png)
      
   3. **Zat zatwierdzanie** wszystkich **zmian w kontroli kodu źródłowego** (po wyświetleniu monitu napisz komunikat zatwierdzenia).
   
      ![Wybieranie opcji "Zat zatwierdzanie wszystkich" w kontroli kodu źródłowego](images/source-control-commit.png)
      
   4. Wybierz przycisk **synchronizacji,** aby zsynchronizować zmiany z powrotem do źródła (Twoje widelec na GitHub).
      
      ![Kliknij przycisk synchronizacji](images/sync-back.png)
      
3. W przeglądarce internetowej utwórz żądanie ściągnięcie, aby zsynchronizować nowe zmiany w twoim formacie z powrotem z dokumentami MicrosoftDocs/wzorcem rzeczywistości mieszanej _(upewnij_ się, że strzałka wskazuje poprawną stronę docelową).

   ![Tworzenie żądania ściągnęcie z twojego widelecu do dokumentu MicrosoftDocs/rzeczywistości mieszanej](images/pr-to-master.png)

### <a name="useful-extensions"></a>Przydatne rozszerzenia

Następujące rozszerzenia Visual Studio Code są przydatne podczas edytowania dokumentacji:

- [Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:
   - Wyszukaj przekazane obrazy i przywołuj je.
   - Dodaj formatowanie, takie jak listy, tabele i wywołania specyficzne dla dokumentów, takie jak `>[!NOTE]` .
   - Wyszukaj linki wewnętrzne i zakładki (linki do określonych sekcji na stronie) i odwołuj się do tych linków.
   - Błędy formatowania są wyróżnione (umieść wskaźnik myszy nad błędem, aby dowiedzieć się więcej).
- [Moduł sprawdzania pisowni kodu](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) — wyrazy z błędami pisowni zostaną podkreślone. kliknij prawym przyciskiem myszy wyraz z błędami pisowni, aby go zmienić lub zapisać w słowniku.
