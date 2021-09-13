---
title: Używanie Przeglądarka 3D Beta na HoloLens (1. generacja)
description: Opisuje typy plików i funkcji, które są Przeglądarka 3D beta w HoloLens (1. generacji), a także sposób korzystania z aplikacji i rozwiązywania problemów z aplikacją.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 10/30/2019
ms.reviewer: scooley
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 00e99d3f67e9e4371da12612b9b01c3ce58e71bd
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036029"
---
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a>Używanie Przeglądarka 3D Beta na HoloLens (1. generacja)

Przeglądarka 3D Beta umożliwia wyświetlanie modeli 3D na HoloLens (1. generacji). Obsługiwane pliki fbx *można otwierać* i wyświetlać z Microsoft Edge, OneDrive i innych aplikacji.

>[!NOTE]
>Ten artykuł dotyczy immersywnych aplikacji Unity **Przeglądarka 3D Beta,** która obsługuje pliki fbx i jest dostępna tylko na platformie HoloLens (1. generacja). Wstępnie zainstalowana **aplikacja** Przeglądarka 3D na platformie HoloLens 2 obsługuje otwieranie niestandardowych modeli .glb [](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) 3D w domu rzeczywistości mieszanej (zobacz Przegląd wymagań dotyczących zasobów, aby uzyskać więcej szczegółów.

>[!IMPORTANT]
>Chociaż Przeglądarka 3D Beta może pozostać dostępna w wersji Microsoft Store dla HoloLens (1. generacji), nie jest już aktywnie programowa i nie jest już obsługiwana.

Jeśli masz problemy z otwarciem modelu 3D w wersji Przeglądarka 3D Beta lub niektóre funkcje modelu 3D nie są obsługiwane, zobacz obsługiwane specyfikacje [zawartości](#supported-content-specifications) poniżej.

Aby tworzyć lub optymalizować modele 3D do użycia z usługą Przeglądarka 3D Beta, zobacz Optymalizacja modeli [3D dla](#optimizing-3d-models-for-3d-viewer-beta) wersji Przeglądarka 3D Beta poniżej.

Istnieją dwa sposoby otwierania modelu 3D na HoloLens. Aby dowiedzieć się więcej, zobacz Wyświetlanie plików [FBX HoloLens](#viewing-fbx-files-on-hololens) poniżej.

Jeśli po przeczytaniu tych tematów masz problemy, zobacz [Rozwiązywanie problemów poniżej.](#troubleshooting)

## <a name="supported-content-specifications"></a>Obsługiwane specyfikacje zawartości

### <a name="file-format"></a>Format pliku

- Format FBX
- Maksymalna wersja FBX 2015.1.0

### <a name="file-size"></a>Rozmiar pliku

- Minimum 5 KB
- Maksymalnie 500 MB

### <a name="geometry"></a>Geometria

- Tylko modele wielokątne. Brak powierzchni podpodziału ani NUMB
- Układ współrzędnych po prawej stronie
- Zmiana w macierzach przekształcania nie jest obsługiwana

### <a name="textures"></a>Tekstury

- Mapy tekstur muszą być osadzone w pliku FBX
- Obsługiwane formaty obrazów
  - Obrazy JPEG i PNG
  - Obrazy BMP (24-bitowy kolor true RGB)
  - Obrazy TGA (24-bitowy RGB i 32-bitowy rgbQ true-color)
- Maksymalna rozdzielczość tekstury 2048 x 2048
- Maksymalnie jedna mapa cykań, jedna mapa normalna i jedna mapa modułu odbicia na siatkę
- Kanał alfa w teksturach tekstury powoduje odrzucenie pikseli, jeśli wartość jest poniżej 50%

### <a name="animation"></a>Animacja

- Animacja skalowania/obrotu/tłumaczenia poszczególnych obiektów
- Animacja Podgiełowej (pomocniczej) ze zmianą koloru
  - Maksymalnie 4 wpływy na wierzchołek

### <a name="materials"></a>Materiały

- Obsługiwane są materiały Lamberta i P berta z dostosowywaymi parametrami
- Obsługiwane właściwości materiału dla Lamberta
  - Main Texture (RGB + test alfa)
  - Color (RGB)
  - Kolor otoczenia (RGB)
- Obsługiwane właściwości materiału dla łańcowej
  - Main Texture (RGB + test alfa)
  - Color (RGB)
  - Kolor otoczenia (RGB)
  - Kolor spektrum (RGB)
  - Połyskliwości
  - Odbicia
- Materiały niestandardowe nie są obsługiwane
- Maksymalnie jeden materiał na siatkę
- Maksymalnie jedna warstwa materiału
- Maksymalnie 8 materiałów na plik

### <a name="file-and-model-limitations"></a>Ograniczenia dotyczące plików i modeli

Istnieją twarde ograniczenia dotyczące rozmiaru plików, a także liczby modeli, wierzchołków i siatek, które mogą być otwierane jednocześnie w wersji Przeglądarka 3D Beta:

- Maksymalny rozmiar pliku 500 MB na model
- Wierzchołki: 600 000 połączonych we wszystkich otwartych modelach
- Siatki: 1600 połączonych na wszystkich otwartych modelach
- Maksymalnie 40 modeli otwieranych jednocześnie

## <a name="optimizing-3d-models-for-3d-viewer-beta"></a>Optymalizacja modeli 3D pod Przeglądarka 3D Beta

### <a name="special-considerations"></a>Uwagi specjalne

- Unikaj czarnych materiałów lub czarnych obszarów w mapach tekstur. Hologramy są wykonane z światła, HoloLens więc czarny (brak światła) jako przezroczysty.
- Przed eksportowaniem do FBX z narzędzia do tworzenia upewnij się, że cała geometria jest widoczna i odblokowana, a żadne warstwy zawierające geometrię nie są wyłączone ani nie są szablonowane. Widoczność nie jest przestrzegana.
- Unikaj bardzo dużych przesunięć translacji między węzłami (na przykład 100 000 jednostek). Może to spowodować zakłócony model podczas przesuwania/skalowania/obracania.

### <a name="performance-optimization"></a>Optymalizacja wydajności

Pamiętaj o wydajności podczas tworzenia zawartości i weryfikowania jej w aplikacji Przeglądarka 3D Beta na platformie HoloLens podczas procesu tworzenia, aby uzyskać najlepsze wyniki. Przeglądarka 3D Beta renderuje zawartość w czasie rzeczywistym, a wydajność jest HoloLens możliwości sprzętu.  

W modelu 3D istnieje wiele zmiennych, które mogą mieć wpływ na wydajność. Przeglądarka 3D beta będzie wyświetlać ostrzeżenie dotyczące obciążenia, jeśli istnieje więcej niż 150 000 wierzchołków lub więcej niż 400 siatek. Animacje mogą mieć wpływ na wydajność innych otwartych modeli. Istnieją również twarde limity całkowitej liczby modeli, wierzchołków i siatek, które mogą być otwierane jednocześnie w wersji Przeglądarka 3D Beta (zobacz Ograniczenia dotyczące plików [i modeli).](#file-and-model-limitations)  

Jeśli model 3D nie działa dobrze ze względu na złożoność modelu, rozważ:

- Zmniejszenie liczby wielokątów
- Zmniejszenie liczby chłoniaka w animacji pomocniczej
- Unikanie samodzielnego oklulacji

Renderowanie dwustronna jest obsługiwane w wersji Przeglądarka 3D Beta, chociaż jest domyślnie wyłączone ze względu na wydajność. Tę możliwość można włączona za pomocą **przycisku Dwustronna** strona **na stronie** Szczegóły. Aby uzyskać najlepszą wydajność, unikaj stosowania renderowania dwustronnego w zawartości.

### <a name="validating-your-3d-model"></a>Sprawdzania poprawności modelu 3D

Zweryfikuj model, otwierając go w Przeglądarka 3D beta na HoloLens. Wybierz przycisk **Szczegóły,** aby wyświetlić charakterystyki modelu i ostrzeżenia dotyczące nieobsługiwanej zawartości (jeśli jest obecna).

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a>Renderowanie modeli 3D z wymiarami rzeczywistymi

Domyślnie model 3D Przeglądarka 3D beta wyświetla modele 3D w wygodnym rozmiarze i pozycji względem użytkownika. Jeśli jednak renderowanie modelu 3D z pomiarami wartości true-to-life jest ważne (na przykład podczas oceny modelialików w pomieszczeniu), twórca zawartości może ustawić flagę w metadanych pliku, aby zapobiec ponownemu rozmiarowi tego modelu zarówno przez aplikację, jak i użytkownika.

Aby zapobiec skalowaniu modelu, dodaj niestandardowy atrybut logiczny do dowolnego obiektu w scenie o nazwie Microsoft_DisableScale i ustaw go na wartość true. Przeglądarka 3D Beta będzie wówczas uwzględniać informacje FbxSystemUnit zawarte w pliku FBX. Skalowanie w Przeglądarka 3D Beta wynosi 1 miernik na jednostkę FBX.

## <a name="viewing-fbx-files-on-hololens"></a>Wyświetlanie plików FBX w HoloLens

### <a name="open-an-fbx-file-from-microsoft-edge"></a>Otwórz plik FBX z Microsoft Edge

Pliki FBX można otwierać bezpośrednio z witryny internetowej przy użyciu Microsoft Edge na HoloLens.

1. W Microsoft Edge przejdź do strony internetowej zawierającej plik FBX, który chcesz wyświetlić.
1. Wybierz plik, aby go pobrać.
1. Po zakończeniu pobierania wybierz  przycisk Otwórz w Microsoft Edge, aby otworzyć plik w programie Przeglądarka 3D Beta.

Dostęp do pobranego pliku można uzyskać i otworzyć ponownie później przy użyciu funkcji Pobierania w Microsoft Edge. Aby zapisać model 3D i zapewnić dalszy dostęp, pobierz plik na komputer i zapisz go na swoim OneDrive danych. Plik można następnie otworzyć z aplikacji OneDrive w HoloLens.

> [!NOTE]
> Niektóre witryny internetowe z modelami FBX do pobrania zapewniają je w skompresowanym formacie ZIP. Przeglądarka 3D Beta nie może otwierać plików ZIP bezpośrednio. Zamiast tego użyj komputera, aby wyodrębnić plik FBX i zapisać go na OneDrive konta. Plik można następnie otworzyć z aplikacji OneDrive w HoloLens.

### <a name="open-an-fbx-file-from-onedrive"></a>Otwórz plik FBX z OneDrive

Pliki FBX można otwierać z OneDrive przy użyciu OneDrive na HoloLens. Upewnij się, że zainstalowano program OneDrive przy użyciu aplikacji Microsoft Store na komputerze HoloLens i że plik FBX został już przekazany do OneDrive na komputerze.

Po w OneDrive plików FBX można otwierać na stronie HoloLens przy użyciu Przeglądarka 3D Beta na jeden z dwóch sposobów:

- Uruchom OneDrive na HoloLens i wybierz plik FBX, aby otworzyć go w Przeglądarka 3D Beta.
- Uruchom Przeglądarka 3D beta, naciśnij w powietrzu, aby wyświetlić pasek narzędzi, a następnie wybierz **pozycję Otwórz plik.** OneDrive, co umożliwia wybranie pliku FBX.

## <a name="troubleshooting"></a>Rozwiązywanie problemów

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a>Po otwarciu modelu 3D jest wyświetlane ostrzeżenie

Ostrzeżenie zostanie wyświetlony, jeśli spróbujemy otworzyć model 3D zawierający funkcje, które nie są obsługiwane przez usługę Przeglądarka 3D Beta, lub jeśli model jest zbyt złożony i może to mieć wpływ na wydajność. Przeglądarka 3D beta nadal będzie ładować model 3D, ale wydajność lub wierność wizualna może zostać naruszona.

Aby uzyskać więcej informacji, zobacz [Supported content specifications (Obsługiwane](#supported-content-specifications) specyfikacje zawartości) i [Optimizing 3D models for Przeglądarka 3D Beta (Optymalizacja modeli 3D pod Przeglądarka 3D Beta).](#optimizing-3d-models-for-3d-viewer-beta)

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a>Widzę ostrzeżenie i model 3D nie ładuje się

Zostanie wyświetlony komunikat o błędzie, gdy usługa Przeglądarka 3D Beta nie może załadować modelu 3D ze względu na złożoność lub rozmiar pliku albo jeśli plik FBX jest uszkodzony lub nieprawidłowy. Zostanie również wyświetlony komunikat o błędzie, jeśli osiągnięto limit całkowitej liczby modeli, wierzchołków lub siatek, które mogą być otwierane jednocześnie.  

Aby uzyskać więcej informacji, zobacz [Supported content specifications (Obsługiwane specyfikacje zawartości)](#supported-content-specifications) [oraz File and model limitations (Ograniczenia dotyczące plików i modeli).](#file-and-model-limitations)

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a>Mój model 3D ładuje się, ale nie jest wyświetlany zgodnie z oczekiwaniami

Jeśli model 3D nie wygląda zgodnie z oczekiwaniami w wersji Przeglądarka 3D Beta, naciśnij w powietrzu, aby wyświetlić pasek narzędzi, a następnie wybierz pozycję **Szczegóły.** Aspekty pliku, które nie są obsługiwane przez program Przeglądarka 3D Beta, zostaną wyróżnione jako ostrzeżenia.

Najbardziej powszechnym problemem, który może wystąpić, jest brak tekstury, prawdopodobnie dlatego, że nie są one osadzone w pliku FBX. W tym przypadku model będzie wyświetlany jako biały. Ten problem można rozwiązać w procesie tworzenia, eksportując z narzędzia do tworzenia do FBX z wybraną opcją osadzania tekstur.

Aby uzyskać więcej informacji, zobacz [Supported content specifications (Obsługiwane](#supported-content-specifications) specyfikacje zawartości) i [Optimizing 3D models for Przeglądarka 3D Beta (Optymalizacja modeli 3D pod Przeglądarka 3D Beta).](#optimizing-3d-models-for-3d-viewer-beta)

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a>Podczas wyświetlania modelu 3D odczuwam spadek wydajności

Na wydajność ładowania i wyświetlania modelu 3D może mieć wpływ złożoność modelu, liczba otwartych jednocześnie modeli lub liczba modeli z aktywnymi animacjami.

Aby uzyskać więcej informacji, zobacz [Optimizing 3D models for Przeglądarka 3D Beta](#optimizing-3d-models-for-3d-viewer-beta) (Optymalizacja modeli 3D pod Przeglądarka 3D beta) oraz File and model limitations (Ograniczenia dotyczące plików i [modeli).](#file-and-model-limitations)

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a>Po otwarciu pliku FBX na stronie HoloLens nie jest on otwierany w programie Przeglądarka 3D Beta

Przeglądarka 3D beta jest automatycznie skojarzona z rozszerzeniem pliku fbx po jego zainstalowaniu.

Jeśli spróbujesz otworzyć plik FBX i zostanie wyświetlone okno dialogowe z daniem Microsoft Store, obecnie nie masz aplikacji skojarzonej z rozszerzeniem pliku fbx na HoloLens.

Sprawdź, Przeglądarka 3D beta jest zainstalowana. Jeśli nie jest zainstalowany, pobierz go ze strony Microsoft Store na HoloLens.

Jeśli Przeglądarka 3D beta jest już zainstalowana, uruchom Przeglądarka 3D Beta, a następnie spróbuj ponownie otworzyć plik. Jeśli problem będzie się powtarzać, odinstaluj i zainstaluj ponownie Przeglądarka 3D beta. Spowoduje to ponowne skojarzenie rozszerzenia pliku .fbx z Przeglądarka 3D Beta.

Jeśli próbujesz otworzyć plik FBX, otwierasz aplikację inną niż Przeglądarka 3D Beta, ta aplikacja została prawdopodobnie zainstalowana po wersji Przeglądarka 3D Beta i przejmuje skojarzenie z rozszerzeniem pliku fbx. Jeśli wolisz, Przeglądarka 3D beta ma być skojarzona z rozszerzeniem pliku fbx, odinstaluj i zainstaluj ponownie Przeglądarka 3D Beta.

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a>Przycisk Otwórz plik w Przeglądarka 3D Beta nie uruchamia aplikacji

Przycisk **Otwórz plik** otwiera aplikację skojarzoną z funkcją s wyboru plików na HoloLens. Jeśli OneDrive jest zainstalowany, przycisk **Otwórz plik** powinien zostać OneDrive. Jeśli jednak obecnie żadna aplikacja nie jest skojarzona z funkcją s wyboru plików zainstalowaną na HoloLens, zostaniesz skierowany do Microsoft Store.

Jeśli przycisk **Otwórz plik** uruchamia aplikację inną niż OneDrive, ta aplikacja została prawdopodobnie zainstalowana po OneDrive i przejmuje skojarzenie z funkcją s wyboru plików. Jeśli wolisz uruchamiać OneDrive podczas  wybierania przycisku Otwórz plik w programie Przeglądarka 3D Beta, odinstaluj i ponownie zainstaluj OneDrive.

Jeśli przycisk **Otwórz plik** nie jest aktywny, możliwe, że jednocześnie osiągnięto limit modeli, które mogą być otwierane w wersji Przeglądarka 3D Beta. Jeśli masz otwarte 40 modeli w wersji Przeglądarka 3D Beta, musisz je zamknąć, zanim będzie można otworzyć dodatkowe modele.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Fora pomocy](http://forums.hololens.com/categories/3d-viewer-beta) technicznej — tylko do celów archiwalnych. To forum nie jest już aktywne.
- [Uwagi innych firm](https://www.microsoft.com/{lang-locale}/legal/products)
