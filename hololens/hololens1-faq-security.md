---
title: Często zadawane pytania zabezpieczające
description: Bądź na bieżąco z często zadawane pytaniami zabezpieczającymi i odpowiedziami na pytania dotyczące urządzeń HoloLens rzeczywistości mieszanej.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: pawinfie
ms.author: pawinfie
ms.date: 02/19/2020
keywords: hololens, Windows Mixed Reality, zabezpieczenia
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: bradke
ms.openlocfilehash: 371c901acbf23feecfe98e72569caeaf63e2198f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111378443"
---
# <a name="frequently-asked-hololens-1st-gen-security-questions"></a>Często zadawane pytania zabezpieczające dotyczące urządzenia HoloLens (1. generacji)

1. **Jaki poziom ochrony danych oferuje urządzenie HoloLens 1?**
    1. Zobacz [HoloLens (1. generacja) Szyfrowanie funkcją BitLocker](hololens1-encryption.md)
1. **Jakiego typu sieci bezprzewodowej jest używany?**
    1. 802.11ac i Bluetooth 4.1 LE
1. **Jakiego typu architektura została włączona?  Na przykład: wskaż, siatkę, czy coś innego?**
    1. Wi-Fi mogą być używane w trybie infrastruktury do komunikowania się z innymi punktami dostępu bezprzewodowego.
    1. Połączenia Bluetooth można używać do komunikacji równorzędnej między wieloma urządzeniami HoloLens, jeśli aplikacja klienta go obsługuje, lub z innymi urządzeniami Bluetooth.
1. **Co to jest identyfikator FCC?**
    1. C3K1688
1. **Na jakim zakresie częstotliwości i kanałach działa urządzenie i czy można je konfigurować?**
    1. Wi-Fi: zakres częstotliwości nie jest konfigurowalny przez użytkownika i zależy od kraju użytkowania. W Usa Wi-Fi kanały 2,4 GHz (1–11) i 5 GHz (36–64, 100–165).
    1. Bluetooth: funkcja Bluetooth używa standardowego zakresu 2,4–2,48 GHz.
1. **Czy urządzenie może zezwalać na określone częstotliwości lub blokować je?**
    1. Nie jest to kontrolowanie przez użytkownika/urządzenie.
1. **Jaki jest poziom zasilania zarówno przesyłania, jak i odbierania? Czy można go dostosowywać? Jaki jest zakres operacji?**
    1. Nasze standardy testowania emisji można [znaleźć tutaj.](https://fccid.io/C3K1688) Zakres operacji jest w dużym stopniu zależny od punktu dostępu i środowiska, ale jest w przybliżeniu odpowiednikiem innych wysokiej jakości telefonów, tabletów lub komputerów.
1. **Jaki jest cykl/okres istnienia obowiązków w przypadku normalnego działania?**
    1. 2–3 godz. aktywnego użytkowania i do dwóch tygodni czasu wstrzymania
    1. Okres istnienia baterii jest niedostępny.
1. **Co to jest zachowanie przesyłania i odbierania, gdy narzędzie nie jest w zasięgu?**
    1. Urządzenie HoloLens przesyła/odbiera zgodnie ze standardowym wzorcem sieci Wi-Fi/Bluetooth. Na granicy zakresu prawdopodobnie zauważysz, że dane wejściowe będą się czekać na całkowite rozłączenia, ale po powrocie do tego zakresu powinny szybko nawiązać ponownie połączenie.
1. **Co to jest gęstość wdrożenia na stopę kwadratową?**
    1. Jest to zależne od infrastruktury sieci.
1. **Czy urządzenie może używać infrastruktury jako klienta?**
    1. Tak
1. **Jaki protokół jest używany?**
    1. Urządzenie HoloLens nie używa żadnych zastrzeżonych protokołów
1. **Częstotliwość aktualizacji systemu operacyjnego — jaka jest częstotliwość aktualizacji systemu operacyjnego dla hl?  Czy istnieje ustawiony harmonogram?  Czy firma Microsoft wydaje poprawki zabezpieczeń w razie potrzeby itp.**
    1. Firma Microsoft zapewnia aktualizacje systemu operacyjnego na urządzeniach HoloLens dokładnie tak samo jak w przypadku urządzenia Windows 10. Zwykle w ciągu roku istnieją dwie ważne aktualizacje, jedna na wiosnę, a jedna na wiosnę. Ponieważ urządzenie HoloLens to urządzenie z systemem Windows, koncepcja aktualizacji jest taka sama jak w przypadku każdego innego urządzenia z systemem Windows. Firma Microsoft wydaje poprawki zabezpieczeń zgodnie z potrzebami i stosuje tę samą koncepcję co na innych urządzeniach z systemem Windows.
1. **Wzmacnianie zabezpieczeń systemu operacyjnego — jakie opcje mają na celu wzmacnianie zabezpieczeń systemu operacyjnego?  Czy możemy usunąć lub zamknąć niepotrzebne aplikacje lub usługi?**
    1. Urządzenie HoloLens zachowuje się jak smartfon. Jest to porównywalne z innymi nowoczesnymi urządzeniami z systemem Windows. Urządzeniem HoloLens można zarządzać za pomocą Microsoft Intune lub innych nowoczesnych rozwiązań Zarządzanie urządzeniami, takich jak MobileIron, Airwatch lub Soti. Istnieją zasady, które można ustawić w tych systemach zarządzania, aby umieścić zasady zabezpieczeń na urządzeniu i w celu wzmacniania zabezpieczeń urządzenia. Istnieje również możliwość usunięcia niepotrzebnych aplikacji, jeśli jest to potrzebne.
1. **W jaki sposób aplikacje będą zarządzane i aktualizowane? Jaka kontrola jest dostępna do zdefiniowania, które aplikacje są ładowane, i proces aktualizacji aplikacji dla aplikacji, które znajdują się w sklepie Microsoft Store?**
    1. Urządzenie HoloLens pobiera aplikacje tylko za pośrednictwem Sklepu Windows. Można zainstalować tylko pakiety aplikacji Appx opracowane na użytek urządzenia HoloLens. Można to zobaczyć na ekranie Microsoft Store z małym logo obok aplikacji, która pokazuje urządzenie HoloLens. Każda kontrola nad zarządzaniem aplikacjami ze sklepu dotyczy również urządzenia HoloLens. Możesz użyć koncepcji oficjalnego sklepu lub sklepu dla firm. Aplikacje mogą być ładowane bezpośrednio (ręczny proces ładowania aplikacji na urządzeniu z systemem Windows) lub mogą być zarządzane za pośrednictwem rozwiązania MDM, dzięki czemu aplikacje są automatycznie ściągane ze sklepu w razie potrzeby.
1. **Jaka jest częstotliwość aktualizacji aplikacji w sklepie dla urządzenia HoloLens?**
    1. Ponieważ postępujemy zgodnie z tym samym pojęciem Microsoft Store i ściągania z nich aplikacji, cykl aktualizacji jest określany przez dewelopera aplikacji. Wszystkie opcje zarządzania, które trzeba kontrolować mechanizm aktualizacji w magazynie, dotyczą również urządzenia HoloLens.
1. **Czy na urządzeniach HoloLens jest możliwość bezpiecznego rozruchu?**
    1. Tak
1. **Czy istnieje możliwość wyłączenia lub odłączenia obsługi urządzeń peryferyjnych od urządzenia?**
    1. Tak
1. **Czy istnieje możliwość kontrolowania lub wyłączania używania portów na urządzeniu?**
    1. Urządzenie HoloLens zawiera tylko dwa porty (jeden dla słuchawki i jeden do ładowania lub łączenia się z komputerami). Nie ma możliwości wyłączenia portu ze względu na funkcje i odzyskiwanie.
1. **Oprogramowanie antywirusowe, wykrywanie punktów końcowych, adresy IP, lista zezwalań kontroli aplikacji — dowolna możliwość uruchamiania oprogramowania antywirusowego, wykrywania punktów końcowych, adresów IP, listy zezwalań kontroli aplikacji itp.**
    1. Windows Holographic for Business (pakiet komercyjny) obsługuje Windows Defender Smart Screen. Jeśli firma antywirusowa ma utworzyć i opublikować swoją aplikację na platforma uniwersalna systemu Windows, można ją pobrać na urządzenie HoloLens. Obecnie żadne firmy nie wykonały tego w przypadku urządzenia HoloLens.
    1. Zezwalanie na aplikacje jest możliwe za pomocą sklepu Microsoft Enterprise Store, w którym można wybrać tylko określone aplikacje do pobrania. Ponadto za pomocą rozwiązania MDM można zablokować określone aplikacje, które mogą być uruchamiane, a nawet widoczne na urządzeniu.
1. **Czy można poddać je kwarantannie z sieci prod do momentu zaktualizowania urządzenia, jeśli przez dłuższy czas było ono w trybie offline?  Na przykład urządzenie było w szufladzie, które nie było zasilane przez okres (sześć miesięcy) i nie otrzymało żadnych aktualizacji, poprawek itp.  Czy podczas próby dołączenia do sieci możemy ją flagować i powiedzieć, że należy zaktualizować ją w innej sieci przed skarżeniami w celu dołączenia do sieci.**
    1. Jest to coś, co może być zarządzane na poziomie infrastruktury przez rozwiązanie MDM lub serwer lokalnym. Urządzenie może być oflagowane jako niezgodne, jeśli nie spełnia określonej wersji aktualizacji.
1. **Czy firma Microsoft obejmuje jakiekolwiek tylne drzwi lub dostęp do usług, które umożliwiają firmie Microsoft łączenie się z urządzeniem w celu udostępniania ekranu lub zdalnej pomocy technicznej w dowolnej chwili?**
    1. Nie
1. **Gdy certyfikat PKI jest generowany dla zaufanej komunikacji, chcemy, aby certyfikat został wygenerowany na urządzeniu, aby wiedzieliśmy, że jest on tylko na tym urządzeniu, unikatowy dla tego urządzenia i nie można go wyeksportować ani użyć do personifikacji urządzenia. Czy jest to prawdziwe na urządzeniach HoloLens? Jeśli nie, czy istnieje potencjalne ograniczenie ryzyka?**
    1. Na samym urządzeniu jest generowany kod CSR dla SCEP. Usługa Intune i łącznik lokalnego SCEP pomagają zabezpieczyć żądania samodzielnie, dodając i weryfikując ciąg wyzwania wysyłany do klienta.
    1. Ponieważ urządzenia HoloLens (1. generacja i 2. generacja) mają moduł TPM, te certyfikaty będą przechowywane w module TPM i nie będzie można ich wyodrębnić. Ponadto, nawet jeśli można je wyodrębnić, nie można zweryfikować ciągów wyzwania na innym urządzeniu, przez co certyfikaty/klucz nie mogą być używane na różnych urządzeniach.
