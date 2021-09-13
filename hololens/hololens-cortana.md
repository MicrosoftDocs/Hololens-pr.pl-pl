---
title: Używanie głosu do obsługi HoloLens
description: Dowiedz się, Cortana mogą ułatwić ci różnego rodzaju działania na urządzeniach rzeczywistości mieszanej HoloLens, w tym polecenia głosowe, dyktowanie i interakcje hologramu.
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036023"
---
# <a name="use-your-voice-to-operate-hololens"></a>Używanie głosu do obsługi HoloLens

Za pomocą głosu możesz wykonać niemal wszystko na HoloLens, na przykład zrobić szybkie zdjęcie lub otworzyć aplikację. Wiele poleceń głosowych jest wbudowanych w HoloLens, podczas gdy inne są dostępne za pośrednictwem Cortana.

W tym artykule opisano sposób kontrolowania HoloLens i świata holograficznego przy użyciu głosu i Cortana.

> [!NOTE]
> Mowa jest obsługiwana tylko w [niektórych językach.](hololens2-language-support.md) Język mowy jest oparty na języku wyświetlania Windows, a nie na języku klawiatury.  
>  
> Aby zweryfikować język wyświetlania Windows, wybierz pozycję **Ustawienia**  >  **i Język**  >  **językowy.**

## <a name="built-in-voice-commands"></a>Wbudowane polecenia głosowe

Szybsze HoloLens dzięki tym podstawowym poleceniem. Aby można było ich używać, należy włączyć mowę podczas pierwszego uruchomienia urządzenia lub w Ustawienia  >  **mowy o** ochronie  >  **prywatności.** Zawsze możesz sprawdzić, czy mowa jest włączona, patrząc na stan w górnej części menu Start. Aby uzyskać najlepsze wyniki rozpoznawania mowy, HoloLens 2 korzysta z usług firmy Microsoft opartych na chmurze. Można jednak użyć Ustawienia, aby wyłączyć tę funkcję. Aby to zrobić, w Ustawienia wyłączyć rozpoznawanie mowy **w trybie online.** Po zmianie tego ustawienia komputer HoloLens 2 będzie przetwarzać tylko dane głosowe lokalnie w celu rozpoznawania poleceń i dyktowania, a Cortana będą niedostępne.

### <a name="general-speech-commands"></a>Ogólne polecenia mowy

Użyj tych poleceń w Windows Mixed Reality, aby szybciej się omiąć. Niektóre polecenia używają kursora spojrzenia, który jest wywniośany przez powiedzenie "select".

> [!NOTE]
> Promienie rąk nie są obsługiwane HoloLens (1. generacji).

| Powiedz to | Wymagana czynność |
| - | - |
| "Wybierz" | Powiedz "select", aby wyprowadzić kursor. Następnie ustaw kursor na rzeczy, którą chcesz wybrać, i powiedz "select" (wybierz). |
| "Przejdź do startu" |  Otwieranie menu Start |
| "Zamknij"  | Zamknij menu Start |
| Powiedz "Przejdź do startu", aby uruchomić menu szybkich akcji, a następnie powiedz "Mixed reality home".  | Opuszczanie aplikacji immersyjnej |
| "Hide hand ray" / "Show hand ray" (Ukryj promienie dłoni) / "Show hand ray" (Pokaż promienie dłoni) | Ukrywanie i pokazywanie promienia dłoni |
| "Co mogę powiedzieć?"  | Zobacz dostępne polecenia mowy |

Począwszy od wersji 19041.x HoloLens 2, można również używać tych poleceń:

| Powiedz to | Wymagana czynność |
| - | - |
| "Uruchom ponownie urządzenie" | Uruchom dialog, aby potwierdzić, że chcesz ponownie uruchomić urządzenie. Możesz powiedzieć "tak", aby ponownie uruchomić. |
| "Zamykanie urządzenia" | Aby potwierdzić, że chcesz wyłączyć urządzenie, zostanie wyzłoszysz dialog. Możesz powiedzieć "tak", aby potwierdzić. |
| "Jasność w górę/w dół" | Zwiększ lub zmniejsz jasność ekranu o 10%. |
| "Wolumin w górę/w dół" | Zwiększ lub zmniejsz wolumin o 10%. |
| "What's my IP address" (Jaki jest mój adres IP) | Wyświetl dialog z bieżącym adresem IP urządzenia w sieci lokalnej. |
| "Take a picture" (Zrób zdjęcie) | Przechwyć zdjęcie rzeczywistości mieszanej z tym, co obecnie widzisz. |
| "Take a video" (Zrób film wideo) | Rozpocznij nagrywanie wideo rzeczywistości mieszanej. | 
| "Zatrzymaj nagrywanie" | Zatrzymuje bieżące nagrywanie wideo rzeczywistości mieszanej, jeśli jest w toku. |

### <a name="hologram-commands"></a>Polecenia hologramu

Aby użyć tych poleceń, spojrz na obiekt 3D, hologram lub okno aplikacji.

| Powiedz to | Wymagana czynność |
| - | - |
| "Większe" | Uaduj ją |
| "Mniejsze" | Mniejsze rozmiary |
| "Face me" | Przekróć ją w twarz |
| "Przenieś to" | Przenieś go (podążaj za spojrzeniem) |
| "Zamknij" | Zamknij go |
| "Obserwuj mnie" / "Przestań obserwować" | Poruszaj się po nim |

### <a name="see-it-say-it"></a>Zobacz, powiedz to

Wiele przycisków i innych elementów na HoloLens odpowiada również  na Twój  głos — na przykład Obserwuj mnie i zamknij na pasku aplikacji lub przycisk Wstecz **na** krawędzi. Aby dowiedzieć się, czy przycisk ma włączoną  obsługę głosu,  na chwilę umieść kursor w ręki, kursor dotykowy lub promieniej na nim. Jeśli przycisk ma włączoną obsługę głosu, zobaczysz poradę głosową.

### <a name="dictation-mode"></a>Tryb dyktowania

Masz dość pisania? Przełącz się do trybu dyktowania za każdym razem, gdy klawiatura holograficzna jest aktywna. Aby rozpocząć, wybierz przycisk mikrofonu lub powiedz "Rozpocznij dyktowanie". Aby zatrzymać dyktowanie, ponownie wybierz przycisk lub powiedz "Zatrzymaj dyktowanie". Aby usunąć właśnie dyktowane dane, powiedz "Usuń to". 

> [!NOTE]
> Aby korzystać z trybu dyktowania, musisz mieć połączenie internetowe.

HoloLens używa jawnej interpunkcji, co oznacza, że mówisz nazwę interpunkcji, której chcesz użyć. Na przykład możesz powiedzieć "Hey **przecinek** what are you up to **question mark".**

Poniżej znajdują się słowa kluczowe interpunkcji, których można użyć:

- Okres, przecinek, znak zapytania, wykrzyknik/wykrzyknik
- Nowy wiersz/nowy akapit
- Średnik, dwukropek
- Oferty otwarte, cudzysłowy zamknięcia
- Hasztag, uśmiechnięta/uśmiechnięta buźka, frowny, winky
- Dolar, procent

Czasami pomocne jest pisownia takich adresów e-mail. Na przykład, aby dyktować , należy powiedzieć example@outlook.com "E X A M P L E w outlook dot com".

## <a name="do-more-with-cortana"></a>Więcej informacji dzięki Cortana

Cortana może pomóc w wszelkiego rodzaju czynnościach na komputerze HoloLens, ale w zależności od tego, której wersji systemu Windows Holographic używasz, możliwości mogą być inne. Więcej informacji o zaktualizowanych możliwościach najnowszej wersji programu Cortana można znaleźć tutaj: Cortana w nadchodzącej wersji Windows 10: skoncentrowanie się na produktywności z rozszerzonymi zabezpieczeniami i [prywatnością.](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/) 

![Hej, Cortana!](images/cortana-on-hololens.png)

Oto kilka rzeczy, które możesz spróbować powiedzieć (pamiętaj, aby najpierw powiedzieć "Hey Cortana").

**Hey, Cortana**...

- What can I say? (Co mogę powiedzieć?)
- Uruchom <*aplikacji>.*
- Która jest godzina?
- Pokaż mi najnowsze wyniki NBA.
- Tell me a joke. (Opowiedz mi dowcip).

Jeśli używasz wersji *18362.x lub starszej,* możesz również użyć tych poleceń:

**Hey, Cortana**...

- Zwiększ wolumin.
- Zmniejsz jasność.
- Zamknij.
- Uruchom ponownie.
- Idź spać.
- Wycisz.
- Przenieś <*nazwę* aplikacji> w tym miejscu (spojrzenie w miejscu, do którego aplikacja ma przejść).
- Przejdź do pozycji Start.
- Zrób zdjęcie.
- Rozpocznij nagrywanie. (Rozpoczyna nagrywanie wideo).
- Zatrzymaj nagrywanie. (Zatrzymuje nagrywanie wideo).
- Ile baterii pozostało?

Niektóre Cortana, które są używane z usługą Windows na komputerze lub telefonie (na przykład przypomnienia i powiadomienia) nie są obsługiwane w u usługach Microsoft HoloLens, a środowisko Cortana może się różnić w zależności od regionu.

### <a name="turn-cortana-off"></a>Wyłącz Cortana

Cortana jest włączana przy pierwszym użyciu HoloLens podczas włączania mowy. Możesz wyłączyć ją w Cortana ustawień aplikacji. Na liście **Wszystkie aplikacje** wybierz pozycję **Cortana**  >  **Ustawienia**. Następnie wyłącz Cortana, aby dawać sugestie, pomysły, przypomnienia, alerty i nie tylko.

Jeśli Cortana odpowiada na "Hey Cortana", sprawdź, czy mowa jest włączona w menu Start, a następnie przejdź do ustawień usługi Cortana i upewnij się, że jest włączona.
