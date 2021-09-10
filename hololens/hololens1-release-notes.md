---
title: HoloLens wersji 1. generacji
description: Dowiedz się więcej o aktualizacjach w każdej nowej HoloLens wersji.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 1
ms.openlocfilehash: 0fb6c9ed1cd8d3ecc23975052eed54512a465bfb
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428937"
---
# <a name="hololens-1st-gen-release-notes"></a>HoloLens wersji 1. generacji

## <a name="hololens-1st-gen-long-term-servicing"></a>HoloLens (1. generacji) Obsługa długoterminowa
HoloLens (1. generacja) ma stan Long Term Servicing (LTS). Przyszłe aktualizacje skupią się na problemach i poprawkach zabezpieczeń, zachowując równowagę funkcji z wersją 1809 programu Windows 10 Holographic dla wersji 1809 dla HoloLens (1. generacji).

Dla deweloperów oznacza to, że HoloLens (1. generacji) nie będą obsługiwać interfejsu API OpenXR.  Te zestawy nagłowne pozostają obsługiwane w unity 2019 LTS z zapleczami interfejsu API WinRT przez cały cykl życia aparatu Unity 2019 LTS do połowy 2022 r.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 Holographic, wersja 1809

> **Dotyczy: HoloLens** (1. generacja)

| Cecha | Szczegóły |
|---|---|
| **Menu Szybkie akcje** | Gdy jesteś w aplikacji, gest Blooma spowoduje teraz otwarcie menu Szybkie akcje, aby zapewnić szybki dostęp do często używanych funkcji systemowych bez konieczności opuszczania aplikacji. <br> Zobacz [Konfigurowanie HoloLens w trybie kiosku,](hololens-kiosk.md) aby uzyskać informacje o menu Szybkie akcje w trybie kiosku.<br><br> |
| **Zatrzymywanie przechwytywania wideo z menu Start lub szybkich akcji** | Jeśli rozpoczniesz przechwytywanie wideo z menu menu Start lub szybkich akcji, będzie można zatrzymać nagrywanie z tego samego miejsca. (Nie zapomnij, zawsze możesz to zrobić za pomocą poleceń głosowych). |
| **Project z urządzeniem Miracast z włączoną obsługą usługi** | Project zawartość HoloLens na pobliskim urządzeniu Surface lub w odbiorniku TV/Monitor w przypadku korzystania z adaptera Microsoft Display.  Na **stronie Start** wybierz **Połączenie**, a następnie wybierz urządzenie, na którym chcesz projektować. **Uwaga:** Możesz wdrożyć aplikację HoloLens do używania Miracast projekcji bez włączania trybu dewelopera. |
| **Nowe powiadomienia** | Wyświetlaj wyskakujące powiadomienia i odpowiadaj na nie HoloLens, tak jak na komputerze. Spojrzenie, aby odpowiedzieć na nie lub odrzucić je (lub jeśli korzystasz ze środowiska immersyjnego, użyj gestu Blooma). |
| **HoloLens nakładek**<br>(s wyboru plików, klawiatury, okien dialogowych itp.) | Podczas korzystania z aplikacji immersywnych będą teraz wyświetlane nakładki, takie jak klawiatura, okna dialogowe, s wyboru plików itp. |
| **Interfejs użytkownika nakładki opinii wizualnych dla zmiany woluminu** | Po użyciu przycisków regulacji głośności w górę/w dół na HoloLens zostanie wyświetlony wizualny ekran poziomu głośności. |
| **Nowy interfejs użytkownika do rozruchu urządzenia** | Podczas procesu rozruchu dodano wskaźnik ładowania w celu zapewnienia wizualnej opinii o ładowaniu systemu. Uruchom ponownie urządzenie, aby zobaczyć nowy wskaźnik ładowania — jest on między komunikatem "Hello" i Windows rozruchu. |
| **Udostępnianie w pobliżu** | Dodanie możliwości udostępniania Windows w pobliżu, co umożliwia udostępnianie przechwytywania pobliskiej Windows urządzenia. Gdy przechwycisz zdjęcie lub wideo na ekranie HoloLens (lub użyjesz przycisku udostępniania z aplikacji, takiej jak Microsoft Edge), wybierz pobliski Windows urządzenie do udostępnienia. |
| **Udostępnianie z Microsoft Edge** | Przycisk Udostępnij jest teraz dostępny Microsoft Edge oknach HoloLens. W Microsoft Edge wybierz pozycję **Udostępnij.** Użyj s HoloLens udostępniania, aby udostępnić zawartość internetową. |

#### <a name="for-international-customers"></a>Dla klientów międzynarodowych

| Cecha | Szczegóły |
| --- | --- |
| Zlokalizowane kompilacje w języku chińskim i japońskim | Używaj HoloLens z zlokalizowanym interfejsem użytkownika dla języka chińskiego uproszczonego lub japońskiego, w tym zlokalizowanej klawiatury Pinyin, dyktowania i poleceń głosowych.<br>[Dowiedz się, jak zainstalować chińskie i japońskie wersje HoloLens.](hololens1-install-localized.md) |
| Synteza mowy (TTS) | Funkcja syntezy mowy obsługuje teraz język chiński, japoński i angielski. |

#### <a name="for-administrators"></a>Dla administratorów

| Cecha |  Szczegóły  |
|---|----|
| [Włącz aprowizowanie po instalacji](hololens-provisioning.md) | Pakiet aprowizowania środowiska uruchomieniowego można teraz zastosować w dowolnym momencie przy **użyciu Ustawienia**. |
| Przypisany dostęp za pomocą grup usługi Azure AD | Grupy usługi Azure AD można teraz używać do konfigurowania Windows przypisany dostęp w celu skonfigurowania konfiguracji kiosku z jedną aplikacją lub z wieloma aplikacjami. |
| Przełączanie profilu logowania za pomocą numeru PIN z ekranu logowania | Logowanie za pomocą numeru PIN jest teraz dostępne dla **innego użytkownika.** |
| Logowanie się przy użyciu usługi Web Dostawca poświadczeń hasłem | Teraz możesz wybrać opcję logowania Globe, aby uruchomić logowanie internetowe przy użyciu hasła. Na ekranie logowania wybierz **pozycję Opcje** logowania i wybierz opcję Globe, aby uruchomić logowanie do sieci Web. W razie potrzeby wprowadź nazwę użytkownika, a następnie hasło. <br>**Uwaga:** Możesz pominąć dowolne opcje numeru PIN/karty inteligentnej po wyświetleniu monitu podczas logowania do sieci Web. |
| Odczytywanie informacji o sprzęcie urządzenia za pośrednictwem rozwiązania MDM w celu śledzenia urządzeń według numeru seryjnego | Administratorzy IT mogą zobaczyć i śledzić HoloLens według numeru seryjnego urządzenia w konsoli zarządzania urządzeniami przenośnymi. Zapoznaj się z dokumentacją oprogramowania MDM, aby uzyskać informacje o dostępności funkcji i instrukcje. |
| Ustawianie HoloLens urządzenia za pomocą rozwiązania MDM (zmiana nazwy) | Administratorzy IT mogą zobaczyć urządzenia HoloLens i zmienić ich nazwy w konsoli zarządzania urządzeniami przenośnymi. Zapoznaj się z dokumentacją oprogramowania MDM, aby uzyskać informacje o dostępności funkcji i instrukcje. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10, wersja 1803 dla Microsoft HoloLens

> **Dotyczy: HoloLens** (1. generacja)

Windows 10 wersji 1803 jest pierwszą aktualizacją funkcji do wersji Windows Holographic for Business od jej wydania w Windows 10 wersji 1607. Ta aktualizacja wprowadza następujące zmiany:

- Wcześniej można było tylko sprawdzić, czy licencja uaktualnienia dla pakietu Commercial Suite została zastosowana do urządzenia HoloLens, sprawdzając, czy sieć VPN była dostępną opcją na urządzeniu. Teraz **Ustawienia**  >  **system wyświetli**  Windows Holographic for Business po zastosowaniu licencji uaktualnienia. [Dowiedz się, jak odblokować Windows Holographic for Business funkcji.](hololens1-upgrade-enterprise.md)

- Numer kompilacji systemu operacyjnego można wyświetlić we właściwościach urządzenia w aplikacji Eksplorator plików oraz w [narzędziu Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)
- Aprowizowanie urządzenia HoloLens jest teraz łatwiejsze dzięki noweowi kreatorowi Aprowizowanie urządzeń HoloLens **w** narzędziu Windows Configuration Designer. W kreatorze można skonfigurować środowisko konfiguracji i połączenia sieciowe, ustawić tryb dewelopera i uzyskać tokeny zbiorcze usługi Azure AD. [Dowiedz się, jak używać prostego kreatora aprowizowania dla HoloLens.](hololens-provisioning.md#provisioning-package-hololens-wizard)

- Po utworzeniu konta lokalnego w pakiecie aprowizowania hasło nie wygasa już co 42 dni.

- Możesz skonfigurować HoloLens jako kiosk z [pojedynczą aplikacją lub z wieloma aplikacjami.](hololens-kiosk.md) Tryb kiosku z wieloma aplikacjami umożliwia skonfigurowanie aplikacji HoloLens tylko do uruchamiania określonych aplikacji i uniemożliwia użytkownikom wprowadzenie zmian.

- Protokół MTP (Media Transfer Protocol) jest włączony, dzięki czemu można podłączyć urządzenie HoloLens do komputera za pomocą portu USB i przesyłać pliki między HoloLens komputerem. Możesz również użyć aplikacji Eksplorator plików do przenoszenia i usuwania plików z poziomu HoloLens.

- Wcześniej po zalogowaniu się na urządzeniu przy użyciu konta usługi Azure Active Directory (Azure AD) trzeba było dodać dostęp służbowy w usłudze **Ustawienia,** aby uzyskać dostęp do zasobów firmy.  Teraz logujesz się przy użyciu konta usługi Azure AD, a rejestracja odbywa się automatycznie.

- Przed zalogowaniem się możesz wybrać ikonę sieci pod polem hasła, aby wybrać inną sieć Wi-Fi nawiązać połączenie. Możesz również połączyć się z siecią gościa, np. w hotelu, centrum konferencyjnym lub firmie.

- Teraz możesz łatwo udostępniać [dane HoloLens wielu osobom przy użyciu](hololens-multiple-users.md) kont usługi Azure AD.

- Jeśli instalacja lub logowanie nie powiedzie się, wybierz nową opcję **Zbieraj informacje,** aby uzyskać dzienniki diagnostyczne na potrzeby rozwiązywania problemów.

- Poszczegórni użytkownicy mogą synchronizować firmową pocztę e-mail bez rejestrowania swoich urządzeń w funkcji zarządzania urządzeniami przenośnymi (MDM). Możesz używać urządzenia z kontem Microsoft, pobierać i instalować aplikację Poczta oraz bezpośrednio dodawać konto e-mail.

- Stan synchronizacji zarządzania urządzeniami przenośnymi dla urządzenia można sprawdzić w te **Ustawienia** Dostęp do informacji  >    >    >  **służbowych.** W sekcji **Stan synchronizacji urządzeń** możesz rozpocząć synchronizację, wyświetlić obszary zarządzane przez rozwiązanie MDM oraz utworzyć i wyeksportować zaawansowany raport diagnostyczny.
