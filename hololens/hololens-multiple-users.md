---
title: Udostępnianie danych HoloLens wielu osobom
description: Możesz skonfigurować HoloLens współużytkowane przez wiele kont Azure Active Directory lub wielu użytkowników, którzy używają jednego konta.
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/23/2021
ms.reviewer: anisgup
manager: sean-kerawala
appliesto:
- HoloLens 2
ms.openlocfilehash: bbb955edaa500187ea921538291bb1c7bda05422
ms.sourcegitcommit: be1393d24a98381e37bd1f56183c1f381f87cbd4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2021
ms.locfileid: "129600733"
---
# <a name="share-your-hololens-with-multiple-people"></a>Udostępnianie danych HoloLens wielu osobom

## <a name="overview"></a>Omówienie

Firmy często inwestują w wiele HoloLens urządzeń. Sposób korzystania z HoloLens jest elastyczny w zależności od indywidualnych wymagań. Oto przykład niektórych interfejsów dla wielu użytkowników:

- Flota urządzeń HoloLens 2 jest ustawiana za pośrednictwem rozwiązania Windows Autopilot for HoloLens 2 ze spójnym portfolio aplikacji firmowych na każdym urządzeniu. Masz już kilka różnych profilów kiosku przeznaczonych dla różnych grup usługi Azure AD. Każdy użytkownik loguje się do HoloLens przy użyciu kluczy FIDO2 i loguje się do własnego konta usługi Azure AD i jest przedstawiany dostosowany interfejs.
- Niezależny dostawca oprogramowania (ISV) wynajmuje HoloLens 2 urządzenia z usługą D365 Remote Assist i aplikacją biznesową (LOB) do firmy klienta. Te urządzenia są skonfigurowane dla kiosków, które obejmują tylko ich aplikację LOB i usługę Remote Assist i są współużytkowane przez wielu użytkowników końcowych. WDAC służy do utrzymania aplikacji Ustawienia i Microsoft Edge uruchamiania. Do wypożyczenia jest dołączony pakiet baterii USB-C, który dzięki temu urządzenia są w pełni zasilane z wielu zmian.
- Użytkownik końcowy w przedsiębiorstwie próbuje wprowadzić na urządzeniu zmiany w programie Bluetooth, aby można było połączyć nowe urządzenie, ale zasady Widoczność usługi Page Ustawienia są włączone, aby ograniczyć wyświetlanie strony Urządzenia. Nadal mają oni dostęp do innych stron zgodnie z potrzebami, takich jak Wi-Fi, dzięki czemu mogą używać usługi Remote Assist w wielu lokalizacjach z tym samym HoloLens.

## <a name="best-practices"></a>Najlepsze rozwiązania

Podczas planowania udostępniania urządzeń należy wziąć pod uwagę kilka kwestii, które należy wziąć pod uwagę, aby zoptymalizować środowisko urządzenia w zależności od potrzeb biznesowych.

- [Tożsamość i uwierzytelnianie](#identity-and-authentication)
- [Zarządzanie urządzeniami](#device-management)
- [Zaawansowane zarządzanie urządzeniami — kiosk i funkcja WDAC](#advanced-device-management---kiosk-and-wdac)
- [Zarządzanie fizyczne](#physical-management)

### <a name="identity-and-authentication"></a>[Tożsamość i uwierzytelnianie](hololens-identity.md)

Jeśli planujesz posiadanie wielu kont na urządzeniu, będziesz mieć konta usługi Azure AD ze wszystkimi trybami uwierzytelniania. Te metody uwierzytelniania będą oparte na Windows Hello [,](/windows-hardware/design/device-experiences/windows-hello)w tym irysów i kluczy FIDO2.

- Klucze zabezpieczeń FIDO 2 są doskonałe, jeśli masz wiele urządzeń, wielu użytkowników lub stale używasz nowych urządzeń.
- Jeśli masz co najmniej 10 użytkowników, irysy to szybkie rozwiązanie do logowania użytkowników, którzy wcześniej zalogowali się na tym samym urządzeniu.

### <a name="device-management"></a>[Zarządzanie urządzeniami](hololens-csp-policy-overview.md)

Jeśli urządzenia są współdzielone przez użytkowników, prawdopodobnie będziesz chcieć korzystać z ograniczeń urządzenia. Za pomocą zarządzania urządzeniami można ustawić niektóre zasady w celu lepszego umożliwienia użytkownikom korzystania z urządzenia, zarządzania aktualizacjami lub ograniczenia możliwości urządzenia. Zaleca się przejrzenie naszych [typowych ograniczeń dotyczących urządzeń](hololens-common-device-restrictions.md)i sprawdzenie, czy te zalecenia wydają się pasować do Twojej organizacji. Gdy wiesz, jakich zasad chcesz użyć, możesz je zastosować za pośrednictwem pakietów Endpoint Manager [(MDM)](hololens-mdm-configure.md) firmy Microsoft lub pakietów aprowizowania.

### <a name="advanced-device-management---kiosk-and-wdac"></a>Zaawansowane zarządzanie urządzeniami — [kiosk i](hololens-kiosk.md) funkcja [WDAC](windows-defender-application-control-wdac.md)

W niektórych przypadkach można ograniczyć liczbę aplikacji, do których użytkownicy końcowi mogą uzyskiwać dostęp. Możesz ograniczyć aplikacje prezentowane użytkownikom w menu Start przy użyciu [trybu kiosku.](hololens-kiosk.md) Kiosk można skonfigurować tak, aby przedstawiał różne menu Start w zależności od użytkownika, grup platformy Azure lub specjalnych typów użytkowników. takie odwiedzające lub wykluczające właścicieli urządzeń. Możesz wybrać wiele aplikacji lub tylko jedną aplikację. Kiosk z wieloma aplikacjami nie zatrzymuje uruchamiania innej aplikacji, więc jeśli sklep lub inna aplikacja jest dostępna, użytkownicy mogą nadal uruchamiać inną aplikację.

Możesz również całkowicie zatrzymać uruchamianie aplikacji lub usług przy użyciu usługi [Windows Defender Application Control (WDAC)](windows-defender-application-control-wdac.md) w celu ograniczenia aplikacji. WDAC różni się od kiosku, ponieważ nie zmienia interfejsu użytkownika usługi HoloLens, ale nie zezwala na uruchamianie zablokowanej aplikacji.

[Widoczność Ustawienia strony](settings-uri-list.md) to inny sposób dodawania ograniczeń do urządzenia. W przypadku, gdy musisz udzielić użytkownikom dostępu do niektórych stron w aplikacji Ustawienia, ale nie wszystkiego możesz użyć funkcji Page Ustawienia Visibility, aby ograniczyć dostęp. Jest to przydatne na przykład wtedy, gdy użytkownicy muszą zmienić sieć Wi-Fi, ale nie chcesz, aby użytkownicy musieli uzyskać dostęp do strony Konta.

### <a name="physical-management"></a>Zarządzanie fizyczne

Podczas udostępniania urządzenia wielu użytkownikom należy wziąć pod uwagę pewne kwestie fizyczne.

- Upewnij się, że opłaty za urządzenia są ładowane między shifts.
- Jeśli urządzenie jest wymagane na zmianę i musi być na wielu przesunięciach, rozważ użycie baterii zewnętrznej na początku zmiany, podczas gdy urządzenie nadal ma znaczne opłaty za zarządzanie kierunkiem [cieplnym.](hololens2-charging.md#managing-heat)
- Przechowując urządzenia, nie podłączaj ich do sieci i podłączaj je do sieci. Jest to najlepszy sposób zapewnienia aktualizacji systemu operacyjnego i aplikacji.
- Zastanów się, jak [zamierzasz wyczyścić urządzenie między](hololens2-maintenance.md) użytkownikami.
- W przypadku urządzenia z jednym udostępnionym użytkownikiem, jeśli korzystasz z udostępnionego numeru PIN/hasła dla jednego użytkownika, nie umieszczaj numeru PIN/hasła po stronie urządzenia.
- W przypadku wielu urządzeń z jednym udostępnionym użytkownikiem użyj różnych identyfikatorów PIN/haseł.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Udostępnianie wielu osobom, z których każda korzysta z własnego konta

Indywidualne Azure Active Directory (Azure AD) to preferowany i najbezpieczniejszy przypadek użycia tożsamości HoloLens 2 użytkowników. W przypadku korzystania z własnych kont usługi Azure AD wielu użytkowników może przechowywać własne ustawienia użytkownika i dane użytkowników na urządzeniu. Jednocześnie może być zalogowany tylko jeden użytkownik. Gdy użytkownik się HoloLens, HoloLens się poprzedniego użytkownika.

Aby upewnić się, że wiele osób może używać własnych kont na HoloLens, wykonaj następujące kroki, aby je skonfigurować:

1. Po [skonfigurowaniu urządzenia wybierz pozycję](hololens2-start.md) **My work or school owns it** and sign in by an Azure AD account (Moja praca lub szkoła jest jego właścicielem) i zaloguj się przy użyciu konta usługi Azure AD.
1. Po zakończeniu instalacji upewnij się, że ustawienia konta (konta Ustawienia >) obejmują **innych użytkowników.**

> [!NOTE]
> Jeśli urządzenie nie zostało skonfigurowane przy użyciu konta usługi [](hololens-recovery.md) Azure AD, należy je zresetować lub odchylić i prawidłowo skonfigurować.

Aby użyć HoloLens, każdy użytkownik musi wykonać następujące kroki:

1. Jeśli inny użytkownik korzysta z urządzenia, wybierz jedną z następujących opcji:
   - Naciśnij raz przycisk zasilania, aby przejść w stan wstrzymania, a następnie ponownie naciśnij przycisk zasilania, aby powrócić do ekranu blokady
   - Wybierz kafelek użytkownika z **menu Start** lub wybierz polecenie wyloguj się z **menu Power,** aby wylogować bieżącego użytkownika.

1. Użyj poświadczeń konta usługi Azure AD, aby zalogować się na urządzeniu.  
    - Jeśli urządzenie jest używane po raz pierwszy, zostanie poproszą Cię o skalibrowanie HoloLens na własne oczy. [](hololens-calibration.md)
    - Jeśli wcześniej używano urządzenia:
        - [Windows Holographic, wersja 20H2, kompilacja 19041.1128](hololens-release-notes.md#windows-holographic-version-20h2) lub nowsza, ekran bezproblemowo dostosowuje się pod kątem jakości i wygodnego wyświetlania.
        - Poprzednie kompilacje będą wymagały ręcznego dostosowania się do twoich potrzeb.

> [!TIP]
> Jeśli użytkownik nie zalogował się na urządzeniu, wypróbuj jedną z tych dwóch metod, aby przyspieszyć logowanie:
>
> - **Klucz zabezpieczeń FIDO 2:** klucz zabezpieczeń FIDO2 zostanie automatycznie rozpoznany, a użytkownik nie będzie musiał wpisywać poświadczeń użytkownika ani używać usługi MFA. Jest to najszybsza metoda logowania się na nowym urządzeniu.
> - Uwierzytelnianie **internetowe:** po zalogowaniu się do nowego urządzenia możesz wybrać **link** Zaloguj się z innego urządzenia, co spowoduje wygenerowanie 9-znakowego kodu, którego można użyć w witrynie [aka.ms/devicelogin,](https://login.microsoftonline.com/common/oauth2/deviceauth) aby zalogować się jako użytkownik na urządzeniu, lub wpisać nazwę użytkownika i hasło przy użyciu klawiatury.

Aby wyświetlić listę użytkowników urządzenia lub usunąć użytkownika z urządzenia, przejdź do Ustawienia   >  **Konta**  >  **innych użytkowników.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Udostępnianie wielu osobom przy użyciu tego samego konta

Wielu użytkowników może również udostępniać HoloLens urządzenia podczas korzystania z jednego konta użytkownika. Chociaż preferowane jest logowanie HoloLens na urządzeniu przy użyciu ich indywidualnych tożsamości (kont usługi Azure AD), nie jest to opcja w niektórych organizacjach.

Dostępne są dwie metody udostępnionego urządzenia:

- **Wielu użytkowników końcowych udostępnia 1** urządzenie — HoloLens jest przydzielane do wyznaczonej przestrzeni, w której każdy pracownik może korzystać z urządzenia. Przykładami mogą być czyste pomieszczenie lub pakiet do leczenia.

- **Wielu użytkowników końcowych udostępniających wiele urządzeń** — HoloLens znajdują się w udostępnionym miejscu do magazynowania, w którym pracownicy mogą korzystać z dowolnego urządzenia. Przykładami mogą być rygor olejowy lub autosieć/warsztat samochodowy.

Gdy nowy użytkownik umieszcza urządzenie po raz pierwszy przy zachowaniu tego samego konta, które jest zalogowane, urządzenie monituje użytkownika o szybkie skalibrowanie i personalizowanie wyświetlania. Urządzenie będzie przechowywać informacje o pogotowiu, aby automatycznie zoptymalizować jakość i komfort wyświetlania poszczególnych użytkowników. Użytkownicy nie będą musieli ponownie skalibrować urządzenia.
