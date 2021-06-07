---
title: Instrukcje dotyczące współtworowania
description: Dowiedz się, jak współtwolić dokumenty dotyczące urządzenia HoloLens na platformie docs.microsoft.com przy użyciu języka Markdown, który działa w usłudze GitHub.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: dd205ab1fe399d6612be982136c80733a5eb087e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378271"
---
# <a name="contributing-to-the-hololens-documentation"></a>Współtwolenie dokumentacji urządzenia HoloLens

Witamy w [dokumentacji urządzenia HoloLens!](https://github.com/MicrosoftDocs/Hololens) Wszystkie artykuły, które tworzysz lub edytujesz w tym repocie, **będą widoczne publicznie.** 

Dokumenty holoLens są wyświetlane na platformie docs.microsoft.com, która korzysta z znaczników markdown typu GitHub z funkcjami parserów Markdig. Zawartość edytowana w tym repocie jest formatowana na strony ze stylizowaną zawartością, które są wyświetlane https://docs.microsoft.com/hololens pod . 

Ta strona zawiera podstawowe kroki i wskazówki dotyczące współtworowania oraz linki do podstaw dotyczących znaczników Markdown. Dziękujemy za Twój wkład!

## <a name="available-repos"></a>Dostępne repos

| Nazwa repozytorium | Adres URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Rzeczywistość mieszana | [MicrosoftDocs/rzeczywistość mieszana](https://docs.microsoft.com/windows/mixed-reality) |
| Przewodnik po entuzjaściach VR | [MicrosoftDocs/mixed-reality/nakieruj](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a>Przed rozpoczęciem

Jeśli jeszcze go nie masz, musisz utworzyć [konto usługi GitHub.](https://github.com/join)

>[!NOTE]
>Jeśli jesteś pracownikiem firmy Microsoft, połącz konto usługi GitHub z aliasem firmy Microsoft w portalu [Microsoft Open Source](https://repos.opensource.microsoft.com/). Dołącz do **organizacji "Microsoft"** **i "MicrosoftDocs".**

Podczas konfigurowania konta usługi GitHub zalecamy również stosowanie tych środków ostrożności:
- Utwórz silne [hasło dla konta usługi GitHub.](https://github.com/settings/admin)
- Włącz [uwierzytelnianie dwuskładnikowe.](https://github.com/settings/two_factor_authentication/configure)
- Zapisz [kody odzyskiwania w](https://github.com/settings/auth/recovery-codes) bezpiecznym miejscu.
- Zaktualizuj ustawienia [profilu publicznego.](https://github.com/settings/profile)
   - Ustaw swoje imię i nazwisko, a następnie rozważ ustawienie dla ustawienia Publiczny *adres e-mail* wartości Nie *pokazuj mojego adresu e-mail*.
   - Zalecamy przekazanie obrazu profilu, ponieważ miniatura jest wyświetlana na stronach dokumentów, które współtworzsz.
- Jeśli planujesz używać wiersza polecenia, rozważ skonfigurowanie usługi [Git Menedżer poświadczeń dla systemu Windows.](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest) Dzięki temu nie będzie trzeba wprowadzać hasła za każdym razem, gdy wprowadzasz swój wkład.

System publikowania jest powiązany z serwisem GitHub, dlatego te kroki są ważne. Zostaniesz wymieniony jako autor lub współautor każdego artykułu przy użyciu aliasu usługi GitHub.

## <a name="editing-an-existing-article"></a>Edytowanie istniejącego artykułu

Użyj następującego przepływu pracy, aby wprowadzić aktualizacje *istniejącego* artykułu za pośrednictwem usługi GitHub w przeglądarce internetowej:

1. Przejdź do artykułu, który chcesz edytować, w folderze "mixed-reality-docs".

2. Wybierz przycisk edycji (ikona ołówka) w prawym górnym rogu, co spowoduje automatyczne rozgałęzienie gałęzi jednorazowej poza gałęzią "master".

   ![Edytowanie artykułu.](images/editpage.png)
   
3. Edytuj zawartość artykułu zgodnie z [tematem "Markdown basics" (Podstawy znaczników Markdown).](#markdown-basics)

4. Zaktualizuj metadane w górnej części każdego artykułu:

   * **title:** tytuł strony, który jest wyświetlany na karcie przeglądarki podczas wyświetlania artykułu. Tytuły stron są używane do optymalizacji pod kątem wyszukiwarek i indeksowania, więc nie zmieniaj tytułu, chyba że jest to konieczne (chociaż jest to mniej ważne, zanim dokumentacja stanie się publiczna).
   * **description:** Napisz krótki opis zawartości artykułu, który przyspiesza optymalizację pod kątem wyszukiwarek i odnajdywanie.
   * **author:** jeśli jesteś głównym właścicielem strony, dodaj tutaj alias usługi GitHub.
   * **ms.author:** Jeśli jesteś głównym właścicielem strony, dodaj tutaj alias firmy Microsoft (nie potrzebujesz @microsoft.com tylko aliasu ).
   * **ms.date:** zaktualizuj datę, jeśli dodajesz główną zawartość do strony, ale nie dla poprawek, takich jak wyjaśnienie, formatowanie, gramatyka lub pisownia.
   * **keywords:** Słowa kluczowe wspomagają optymalizację pod kątem wyszukiwarek (SEO). Dodaj słowa kluczowe rozdzielone przecinkiem i spacją, które są specyficzne dla Twojego artykułu, ale nie mają interpunkcji po ostatnim sdaniu kluczowym na liście. Nie trzeba dodawać globalnych słów kluczowych, które mają zastosowanie do wszystkich artykułów, ponieważ są one zarządzane w innym miejscu. 
   
5. Po zakończeniu edycji artykułu przewiń w dół i wybierz pozycję **Zaproponuj zmianę pliku.**

6. Na następnej stronie wybierz pozycję **Utwórz żądanie ściągnięcie,** aby scalić automatycznie utworzoną gałąź z gałęzią "master".

7. Powtórz powyższe kroki dla następnego artykułu, który chcesz edytować.

## <a name="renaming-or-deleting-an-existing-article"></a>Zmiana nazwy lub usunięcie istniejącego artykułu

Jeśli zmiana spowoduje zmianę nazwy lub usunięcie istniejącego artykułu, pamiętaj o dodaniu przekierowania. Dzięki temu każda osoba mająca link do istniejącego artykułu nadal będzie w odpowiednim miejscu. Przekierowania są zarządzane przez .openpublishing.redirection.jsw pliku w katalogu głównym w repo.

Aby dodać przekierowanie do .openpublishing.redirection.js, dodaj wpis do `redirections` tablicy :

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- To `source_path` względna ścieżka repozytorium do starego artykułu, który usuwasz. Upewnij się, że ścieżka zaczyna się od i `mixed-reality-docs` kończy się na `.md` .

- To `redirect_url` względny publiczny adres URL ze starego artykułu do nowego artykułu. Upewnij się, że **ten** adres URL nie zawiera adresu lub , ponieważ odwołuje się on do publicznego adresu URL, a `mixed-reality-docs` nie ścieżki `.md` repozytorium. Dozwolone jest tworzenie linków do sekcji w nowym artykule `#section` przy użyciu . W razie potrzeby można również użyć ścieżki bezwzględnej do innej witryny.

- `redirect_document_id` Wskazuje, czy chcesz zachować identyfikator dokumentu z poprzedniego pliku. Wartość domyślna to `false`. Użyj `true` , jeśli chcesz zachować wartość `ms.documentid` atrybutu z przekierowanego artykułu. Jeśli zachowasz identyfikator dokumentu, dane, takie jak wyświetlenia stron i rankingi, zostaną przesłane do artykułu docelowego. Zrób to, jeśli przekierowanie jest przede wszystkim zmianą nazwy, a nie wskaźnikiem do innego artykułu, który obejmuje tylko część tej samej zawartości.

Jeśli dodasz przekierowanie, pamiętaj również o usunięciu starego pliku.

## <a name="creating-a-new-article"></a>Tworzenie nowego artykułu

Użyj następującego przepływu *pracy, aby utworzyć nowe artykuły* w repozytorium dokumentacji za pośrednictwem usługi GitHub w przeglądarce internetowej:

1. Utwórz rozgałęzienie gałęzi "master" MicrosoftDocs/mixed-reality (przy użyciu przycisku **Fork** w prawym górnym rogu).

   ![Rozgałęzienie gałęzi głównej.](images/forkbranch.png)
   
2. W folderze "mixed-reality-docs" wybierz pozycję **Utwórz nowy plik** w prawym górnym rogu.

3. Utwórz nazwę strony artykułu (użyj łączników zamiast spacji i nie używaj znaków interpunkcji ani apostrofów) i dołącz ".md"

   ![Nadaj nowej stronie nazwę.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >Pamiętaj, aby utworzyć nowy artykuł z folderu "mixed-reality-docs". Możesz to potwierdzić, sprawdzając w nowym wierszu nazwy pliku tekst "/mixed-reality-docs/".

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

5. Wypełnij odpowiednie pola metadanych zgodnie z instrukcjami w [powyższej sekcji](#editing-an-existing-article).

6. Pisanie zawartości artykułu przy użyciu [podstaw znaczników Markdown.](#markdown-basics)

7. Dodaj `## See also` sekcję w dolnej części artykułu z linkami do innych odpowiednich artykułów.

8. Po zakończeniu wybierz pozycję **Commit new file (Zat zatwierdzanie nowego pliku).**

9. Wybierz **pozycję Nowe** żądanie ściągnięcie i scal gałąź "master" twojego widelecu z gałęzią "master" microsoftdocs/rzeczywistości mieszanej (upewnij się, że strzałka wskazuje prawidłowy sposób).

   ![Tworzenie żądania ściągnęcie z twojego widelecu do dokumentu MicrosoftDocs/rzeczywistości mieszanej](images/pr-to-master.png)

## <a name="markdown-basics"></a>Podstawy języka znaczników markdown

Następujące zasoby pomogą Ci dowiedzieć się, jak edytować dokumentację przy użyciu języka Markdown:

- [Podstawy języka znaczników markdown](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Dodatkowe zasoby dotyczące pisania znaczników markdown dla docs.microsoft.com](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a>Dodawanie tabel

Ze względu na sposób docs.microsoft.com tabel nie będą one mieć obramowań ani stylów niestandardowych, nawet jeśli spróbujesz użyć arkuszy CSS w tekście. Wygląda na to, że będzie działać przez krótki czas, ale ostatecznie platforma będzie odebrać styl z tabeli. Dlatego należy planować z wyprzedzeniem i zachować prostotę tabel. [Oto witryna, która ułatwia tabele markdown.](https://www.tablesgenerator.com/markdown_tables)

Rozszerzenie [Docs Markdown dla](https://docs.microsoft.com/teamblog/docs-extension) Visual Studio Code ułatwia również generowanie tabel, jeśli używasz narzędzia [Visual Studio Code (patrz poniżej)](#using-visual-studio-code) do edytowania dokumentacji.

### <a name="adding-images"></a>Dodawanie obrazów

Musisz przekazać obrazy do folderu "mixed-reality-docs/images" w repocie, a następnie odwołać się do nich odpowiednio w artykule. Obrazy będą automatycznie wyświetlane w pełnym rozmiarze, co oznacza, że duże obrazy wypełnią całą szerokość artykułu. Zalecamy wstępne zmiany rozmiaru obrazów przed ich przekazaniem. Zalecana szerokość to od 600 do 700 pikseli, ale rozmiar należy odpowiednio w górę lub w dół, jeśli jest to gęsty zrzut ekranu lub część zrzutu ekranu.

>[!IMPORTANT]
>Obrazy można przekazywać tylko do rozdętego repo przed scaleniem. Dlatego jeśli planujesz dodawanie obrazów do artykułu, musisz najpierw użyć usługi [Visual Studio Code,](#using-visual-studio-code) aby dodać obrazy do folderu "images" twojego widelecu, lub upewnij się, że w przeglądarce internetowej zostały wykonane następujące czynności:
>
>1. Forked the MicrosoftDocs/mixed-reality repo ....
>2. Zedytował artykuł w twoim widełku.
>3. Przekazane obrazy, do których odwołujesz się w artykule, do folderu "mixed-reality-docs/images" w twoim widełku.
>4. Utworzono **żądanie ściągnięć,** aby scalić twoje widelec z gałęzią "master" MicrosoftDocs/mixed-reality.
>
>Aby dowiedzieć się, jak skonfigurować własne forked repo, postępuj zgodnie z instrukcjami [dotyczącymi tworzenia nowego artykułu.](#creating-a-new-article)

## <a name="previewing-your-work"></a>Wyświetlanie podglądu pracy

Podczas edytowania w usłudze GitHub  za pośrednictwem przeglądarki internetowej możesz wybrać kartę Podgląd w górnej części strony, aby wyświetlić podgląd pracy przed zatwierdzeniem. 

>[!NOTE]
>Podgląd zmian w witrynie review.docs.microsoft.com jest dostępny tylko dla pracowników firmy Microsoft

Pracownicy firmy Microsoft: po scaleniu twojego wkładu z gałęzią "master" możesz przejrzeć zawartość, zanim przejdzie ona publicznie pod adres https://review.docs.microsoft.com/hololens?branch=master . Znajdź swój artykuł, korzystając ze spisu treści w lewej kolumnie.

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a>Edytowanie w przeglądarce a edytowanie za pomocą klienta klasycznego

Edytowanie w przeglądarce jest najprostszym sposobem na szybkie zmiany, jednak istnieje kilka wad:

- Sprawdzanie pisowni nie jest sprawdzane.
- Nie ma żadnych inteligentnych linków do innych artykułów (musisz ręcznie wpisać nazwę pliku artykułu).
- Przekazywanie obrazów i odwołania do tych obrazów może być kłopotliwe.

Jeśli nie chcesz zajmować się tymi problemami, użyj klienta klasycznego, takiego jak [Visual Studio Code](https://code.visualstudio.com/) z kilku przydatnych rozszerzeń podczas współtworowania. [](#useful-extensions)

## <a name="using-visual-studio-code"></a>Korzystanie z narzędzia Visual Studio Code

Z przyczyn wymienionych [powyżej możesz](#editing-in-the-browser-vs-editing-with-a-desktop-client)edytować dokumentację zamiast w przeglądarce internetowej za pomocą klienta klasycznego. Zalecamy używanie [Visual Studio Code](https://code.visualstudio.com/).

### <a name="setup"></a>Konfigurowanie

Wykonaj następujące kroki, aby skonfigurować Visual Studio Code do pracy z tym repo:

1. W przeglądarce internetowej:
    1. Zainstaluj [program Git dla swojego komputera.](https://git-scm.com/downloads)
    2. Zainstaluj [Visual Studio Code](https://code.visualstudio.com/).
    3. [Jeśli jeszcze tego nie zdążę, zakłoń dokument MicrosoftDocs/rzeczywistość](#creating-a-new-article) mieszaną.
    4. W twoim widełku wybierz pozycję **Klonuj lub pobierz i** skopiuj adres URL.
2. Utwórz lokalny klon twojego widelec w Visual Studio Code:
    1. W menu **Widok** wybierz pozycję **Paleta poleceń.**
    2. Wpisz "Git: Clone".
    3. Wklej skopiowany adres URL.
    4. Wybierz miejsce zapisania klonu na komputerze.
    5. W **oknie podręcznym** wybierz pozycję Otwórz repo.

### <a name="editing-documentation"></a>Edytowanie dokumentacji

Użyj następującego przepływu pracy, aby wprowadzić zmiany w dokumentacji za pomocą Visual Studio Code:

>[!NOTE]
>Wszystkie powyższe wskazówki dotyczące [edytowania](#editing-an-existing-article) i [tworzenia](#creating-a-new-article) artykułów oraz podstawy edytowania znaczników [Markdown](#markdown-basics)mają zastosowanie również w przypadku korzystania z Visual Studio Code.

1. Upewnij się, że sklonowane widelec jest aktualny z oficjalnym repo.

   1. W przeglądarce internetowej utwórz żądanie ściągnięć, aby zsynchronizować ostatnie zmiany od innych współautorów w folderze MicrosoftDocs/mixed-reality 'master' do twojego widelecu (upewnij się, że strzałka wskazuje właściwy sposób).
      
      ![Synchronizowanie zmian z dokumentów MicrosoftDocs/rzeczywistości mieszanej do twojego widelec](images/sync-repos.png)
      
   2. W Visual Studio Code wybierz przycisk synchronizacji, aby zsynchronizować nowo zaktualizowane widelec z klonem lokalnym.
      
      ![Kliknij obraz przycisku synchronizacji](images/sync-clone.png)
      
2. Twórz lub edytuj artykuły w sklonowanym repo przy użyciu Visual Studio Code.

   1. Edytuj co najmniej jeden artykuł (w razie potrzeby dodaj obrazy do folderu "images").
   
   2. **Zapisz** zmiany w **Eksploratorze**.
      
      ![Wybieranie opcji "Zapisz wszystko" w Eksploratorze](images/explorer-save.png)
      
   3. **Zat zatwierdzanie** wszystkich **zmian w kontroli źródła** (po wyświetleniu monitu napisz komunikat o zatwierdzeniu).
   
      ![Wybierz pozycję "Zat zatwierdzeniu wszystkiego" w kontroli kodu źródłowego](images/source-control-commit.png)
      
   4. Wybierz przycisk **synchronizacji,** aby zsynchronizować zmiany z powrotem do źródła (Twoje widelec w usłudze GitHub).
      
      ![Kliknij przycisk synchronizacji](images/sync-back.png)
      
3. W przeglądarce internetowej utwórz żądanie ściągnięć, aby zsynchronizować nowe zmiany w twoim widełku z powrotem z dokumentami MicrosoftDocs/"master" rzeczywistości mieszanej (upewnij się, że strzałka wskazuje prawidłowy sposób).

   ![Tworzenie żądania ściągnnięcia z twojego widelec do dokumentów MicrosoftDocs/mixed-reality](images/pr-to-master.png)

### <a name="useful-extensions"></a>Przydatne rozszerzenia

Następujące rozszerzenia Visual Studio Code są przydatne podczas edytowania dokumentacji:

- [Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:
   - Wyszukaj przekazane obrazy i odwołuj się do tych obrazów.
   - Dodaj formatowanie, takie jak listy, tabele i wywołania specyficzne dla dokumentów, takie jak `>[!NOTE]` .
   - Wyszukaj linki wewnętrzne i zakładki (linki do określonych sekcji na stronie) i odwołuj się do tych linków.
   - Błędy formatowania są wyróżnione (umieść wskaźnik myszy nad błędem, aby dowiedzieć się więcej).
- [Moduł sprawdzania pisowni kodu](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) — wyrazy z błędami pisowni zostaną podkreślone. Kliknij prawym przyciskiem myszy wyraz błędnie napisany, aby go zmienić lub zapisać w słowniku.
