---
title: HoloLens wersji 1. generacji
description: Dowiedz się więcej o aktualizacjach w HoloLens wersji.
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
ms.openlocfilehash: e332794baf20fbab8278a138ceeafb651c6fa2a06f3f41a66038e544f7a6e46b
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661838"
---
# <a name="hololens-1st-gen-release-notes"></a>HoloLens wersji 1. generacji

## <a name="hololens-1st-gen-long-term-servicing"></a>HoloLens (1. generacja) Obsługa długoterminowa
HoloLens (1. generacja) ma stan Long Term Servicing (LTS). Przyszłe aktualizacje skupią się na problemach i poprawkach zabezpieczeń przy zachowaniu zgodności funkcji z wersją Windows 10 Holographic 1809 wersji 1809 programu HoloLens (1. generacja).

Dla deweloperów oznacza to, że HoloLens (1. generacji) nie będą obsługiwać interfejsu API OpenXR.  Te zestawy nagłowne pozostają obsługiwane w unity 2019 LTS z zapleczami interfejsu API WinRT przez cały cykl życia aparatu Unity 2019 LTS do połowy 2022 r.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 Holographic, wersja 1809

> **Dotyczy:** HoloLens (1. generacja)

| Cecha | Szczegóły |
|---|---|
| **Menu Szybkie akcje** | Gdy jesteś w aplikacji, gest Blooma spowoduje teraz otwarcie menu Szybkie akcje, aby zapewnić szybki dostęp do często używanych funkcji systemu bez konieczności opuszczania aplikacji. <br> Aby uzyskać informacje na temat menu Szybkie akcje w trybie [kiosku,](hololens-kiosk.md) zobacz Set up HoloLens in kiosk mode (Konfigurowanie aplikacji w trybie kiosku).<br><br> |
| **Zatrzymywanie przechwytywania wideo z menu Start lub szybkich akcji** | Jeśli rozpoczniesz przechwytywanie wideo z menu Start menu akcji lub szybkich akcji, będzie można zatrzymać nagrywanie z tego samego miejsca. (Nie zapomnij, zawsze możesz to zrobić za pomocą poleceń głosowych). |
| **Project do urządzenia Miracast z włączoną obsługą usługi** | Project zawartość HoloLens na pobliskim urządzeniu Surface lub w odbiorniku TV/Monitor, jeśli używasz adaptera Microsoft Display.  Na **ekranie** **Start Połączenie** pozycję , a następnie wybierz urządzenie, na którym chcesz projektować projekt. **Uwaga:** Możesz wdrożyć aplikację HoloLens używać projekcji Miracast bez włączania trybu dewelopera. |
| **Nowe powiadomienia** | Wyświetlaj wyskakujące powiadomienia i odpowiadaj na nie HoloLens, tak jak na komputerze. Spojrzenie, aby odpowiedzieć na nie lub odrzucić je (lub, jeśli korzystasz z immersywnych doświadczeń, użyj gestu Blooma). |
| **HoloLens nakładki**<br>(s wyboru plików, klawiatury, okien dialogowych itp.) | Podczas korzystania z aplikacji immersywnych będą teraz wyświetlane nakładki, takie jak klawiatura, okna dialogowe, s wyboru plików itp. |
| **Interfejs użytkownika nakładki opinii wizualnych dla zmiany woluminu** | Po użyciu przycisków regulacji głośności w górę/w dół na HoloLens zostanie wyświetlony wizualny ekran poziomu głośności. |
| **Nowy interfejs użytkownika do rozruchu urządzenia** | Podczas procesu rozruchu dodano wskaźnik ładowania w celu zapewnienia wizualnej opinii o ładowaniu systemu. Uruchom ponownie urządzenie, aby zobaczyć nowy wskaźnik ładowania — jest on między komunikatem "Hello" a Windows rozruchu. |
| **Udostępnianie w pobliżu** | Dodanie możliwości Windows udostępnianie w pobliżu, co pozwala na udostępnianie przechwytywania pobliskiej Windows urządzeniu. Gdy przechwycisz zdjęcie lub wideo na ekranie HoloLens (lub użyjesz przycisku udostępniania z aplikacji, takiej jak Microsoft Edge), wybierz pobliski Windows urządzenie do udostępnienia. |
| **Udostępnianie z Microsoft Edge** | Przycisk Udostępnij jest teraz dostępny Microsoft Edge oknach HoloLens. W Microsoft Edge wybierz pozycję **Udostępnij.** Użyj s HoloLens udostępniania, aby udostępnić zawartość internetową. |

#### <a name="for-international-customers"></a>Dla klientów międzynarodowych

| Cecha | Szczegóły |
| --- | --- |
| Zlokalizowane kompilacje w języku chińskim i japońskim | Używaj HoloLens z zlokalizowanym interfejsem użytkownika dla języka chińskiego uproszczonego lub japońskiego, w tym zlokalizowanej klawiatury Pinyin, dyktowania i poleceń głosowych.<br>[Dowiedz się, jak zainstalować wersję języka chińskiego i japońskiego HoloLens.](hololens1-install-localized.md) |
| Synteza mowy (TTS) | Funkcja syntezy mowy obsługuje teraz język chiński, japoński i angielski. |

#### <a name="for-administrators"></a>Dla administratorów

| Cecha |  Szczegóły  |
|---|----|
| [Włącz aprowizowanie po instalacji](hololens-provisioning.md) | Teraz możesz zastosować pakiet aprowizowania środowiska uruchomieniowego w dowolnym momencie przy użyciu **Ustawienia**. |
| Przypisany dostęp za pomocą grup usługi Azure AD | Grupy usługi Azure AD można teraz używać do konfigurowania Windows dostępu w celu skonfigurowania konfiguracji kiosku z jedną aplikacją lub z wieloma aplikacjami. |
| Przełączanie profilu logowania za pomocą numeru PIN z ekranu logowania | Logowanie za pomocą numeru PIN jest teraz dostępne dla **innego użytkownika.** |
| Logowanie za pomocą usługi Web Dostawca poświadczeń przy użyciu hasła | Teraz możesz wybrać opcję logowania Globe, aby uruchomić logowanie internetowe przy użyciu hasła. Na ekranie logowania wybierz **pozycję Opcje** logowania i wybierz opcję Globe, aby uruchomić logowanie internetowe. W razie potrzeby wprowadź nazwę użytkownika, a następnie hasło. <br>**Uwaga:** Możesz pominąć dowolne opcje numeru PIN/karty inteligentnej po wyświetleniu monitu podczas logowania do sieci Web. |
| Odczytywanie informacji o sprzęcie urządzenia za pośrednictwem rozwiązania MDM w celu śledzenia urządzeń według numeru seryjnego | Administratorzy IT mogą zobaczyć i śledzić HoloLens według numeru seryjnego urządzenia w konsoli zarządzania urządzeniami przenośnymi. Zapoznaj się z dokumentacją oprogramowania MDM, aby uzyskać informacje o dostępności funkcji i instrukcje. |
| Ustawianie HoloLens urządzenia za pomocą rozwiązania MDM (zmiana nazwy) | Administratorzy IT mogą zobaczyć i zmienić HoloLens urządzeń w konsoli zarządzania urządzeniami przenośnymi. Zapoznaj się z dokumentacją oprogramowania MDM, aby uzyskać informacje o dostępności funkcji i instrukcje. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10, wersja 1803 dla Microsoft HoloLens

> **Dotyczy:** HoloLens (1. generacja)

Windows 10, wersja 1803, jest pierwszą aktualizacją funkcji do wersji Windows Holographic for Business od jej wydania w wersji Windows 10 wersji 1607. Ta aktualizacja wprowadza następujące zmiany:

- Wcześniej można było tylko sprawdzić, czy licencja uaktualnienia dla pakietu Commercial Suite została zastosowana do urządzenia HoloLens, sprawdzając, czy sieć VPN była dostępną opcją na urządzeniu. Teraz **Ustawienia**  >  **system wyświetli**  Windows Holographic for Business po zastosowaniu licencji uaktualnienia. [Dowiedz się, jak odblokować Windows Holographic for Business funkcji.](hololens1-upgrade-enterprise.md)

- Numer kompilacji systemu operacyjnego można wyświetlić we właściwościach urządzenia w aplikacji Eksplorator plików oraz w narzędziu [Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)
- Aprowizowanie urządzenia HoloLens jest teraz łatwiejsze dzięki noweowi kreatorowi Aprowizowanie urządzeń HoloLens **w** narzędziu Windows Configuration Designer. W kreatorze można skonfigurować środowisko konfiguracji i połączenia sieciowe, ustawić tryb dewelopera i uzyskać tokeny zbiorcze usługi Azure AD. [Dowiedz się, jak używać prostego kreatora aprowizowania dla HoloLens.](hololens-provisioning.md#provisioning-package-hololens-wizard)

- Po utworzeniu konta lokalnego w pakiecie aprowizowania hasło nie wygasa już co 42 dni.

- Możesz skonfigurować [HoloLens jako kiosk z pojedynczą aplikacją lub z wieloma aplikacjami.](hololens-kiosk.md) Tryb kiosku z wieloma aplikacjami umożliwia skonfigurowanie aplikacji HoloLens tylko do aplikacji, które określisz, i uniemożliwia użytkownikom wprowadzenie zmian.

- Protokół MTP (Media Transfer Protocol) jest włączony, dzięki czemu można podłączyć urządzenie HoloLens do komputera za pomocą portu USB i przesyłać pliki między HoloLens i komputerem. Możesz również użyć aplikacji Eksplorator plików, aby przenosić i usuwać pliki z poziomu HoloLens.

- Wcześniej po zalogowaniu się na urządzeniu przy użyciu konta usługi Azure Active Directory (Azure AD) trzeba było dodać dostęp służbowy w usłudze **Ustawienia,** aby uzyskać dostęp do zasobów firmy.  Teraz logujesz się przy użyciu konta usługi Azure AD, a rejestracja odbywa się automatycznie.

- Przed zalogowaniem się możesz wybrać ikonę sieci pod polem hasła, aby wybrać inną sieć Wi-Fi nawiązać połączenie. Możesz również połączyć się z siecią gości, np. w hotelu, centrum konferencyjnym lub firmie.

- Teraz możesz łatwo udostępniać [dane HoloLens wielu osobom przy użyciu](hololens-multiple-users.md) kont usługi Azure AD.

- W przypadku niepowodzenia instalacji lub logowania wybierz nową opcję Zbieraj **informacje,** aby pobrać dzienniki diagnostyczne na potrzeby rozwiązywania problemów.

- Poszczegórni użytkownicy mogą synchronizować firmową pocztę e-mail bez rejestrowania swoich urządzeń w funkcji zarządzania urządzeniami przenośnymi (MDM). Możesz używać urządzenia z kontem Microsoft, pobierać i instalować aplikację Poczta oraz bezpośrednio dodawać konto e-mail.

- Stan synchronizacji zarządzania urządzeniami przenośnymi dla urządzenia można sprawdzić na stronie konta usługi **Ustawienia** Dostęp do informacji  >    >    >  **służbowych.** W sekcji **Stan synchronizacji urządzenia** możesz rozpocząć synchronizację, wyświetlić obszary zarządzane przez rozwiązanie MDM oraz utworzyć i wyeksportować zaawansowany raport diagnostyczny.
