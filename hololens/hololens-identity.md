---
title: Zarządzanie tożsamością użytkownika i logowaniem dla urządzenia HoloLens
description: Dowiedz się, jak zarządzać tożsamościami użytkowników, pomocą techniczną dla wielu użytkowników, zabezpieczeniami, uwierzytelnianiem przedsiębiorstwa i logowaniem dla urządzeń HoloLens.
keywords: HoloLens, user, account, AAD, Azure AD, adfs, microsoft account, msa, credentials, reference
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: scooley
ms.author: scooley
ms.date: 10/6/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: fbef357053900f6495cb59f52cba8669f0d0a3db
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924421"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>Zarządzanie tożsamością użytkownika i logowaniem dla urządzenia HoloLens

> [!NOTE]
> Ten artykuł jest dokumentacją techniczną dla specjalistów IT i entuzjaści technologii. Jeśli szukasz instrukcji dotyczących konfigurowania urządzenia HoloLens, przeczytaj "Konfigurowanie urządzenia[HoloLens (1. generacja)](hololens1-start.md)" lub " Konfigurowanie urządzenia[HoloLens 2".](hololens2-start.md)

Podobnie jak inne urządzenia z systemem Windows, urządzenie HoloLens zawsze działa w kontekście użytkownika. Zawsze istnieje tożsamość użytkownika. Urządzenie HoloLens traktuje tożsamość w prawie taki sam sposób, jak inne Windows 10 urządzenia. Ten artykuł zawiera bardziej głębną referencję na temat tożsamości na urządzeniu HoloLens i koncentruje się na tym, czym urządzenia HoloLens różnią się od innych Windows 10 urządzeń.

Urządzenie HoloLens obsługuje kilka rodzajów tożsamości użytkowników. Aby się zalogować, możesz użyć co najmniej jednego konta użytkownika. Poniżej przedstawiono omówienie typów tożsamości i opcji uwierzytelniania na urządzeniach HoloLens:

| Typ tożsamości | Konta na urządzenie | Opcje uwierzytelniania |
| --- | --- | --- |
| [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Dostawca poświadczeń internetowych platformy Azure</li><li>Aplikacja Azure Authenticator</li><li>Biometryczne (irysy) &ndash; HoloLens 2 tylko<sup>2</sup> </li><li>Opcjonalny numer PIN &ndash; dla urządzenia HoloLens (1. generacja), wymagany dla urządzenia HoloLens 2</li><li>Hasło</li></ul> |
| [Konto Microsoft (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Tylko urządzenie Biometryczne (Iris) &ndash; HoloLens 2</li><li>Opcjonalny numer PIN &ndash; dla urządzenia HoloLens (1. generacja), wymagany dla urządzenia HoloLens 2</li><li>Hasło</li></ul> |
| [Konto lokalne](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | Hasło |

Konta połączone z chmurą (Azure AD i MSA) oferują więcej funkcji, ponieważ mogą korzystać z usług platformy Azure.  
> [!IMPORTANT]
> 1 — Azure AD — wersja Premium logowanie do urządzenia nie jest wymagane. Jest to jednak wymagane w przypadku innych funkcji wdrożenia opartego na chmurze z niskim poziomem dotyku, takich jak automatyczne rejestrowanie i rozwiązanie Autopilot.

> [!NOTE]
> 2 — Chociaż urządzenie HoloLens 2 może obsługiwać maksymalnie 64 konta usługi Azure AD, tylko 10 z nich może zarejestrować się w usłudze Iris Authentication. Jest to dostosowane do innych opcji uwierzytelniania [biometrycznego dla Windows Hello dla firm](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer).

## <a name="setting-up-users"></a>Konfigurowanie użytkowników

Najczęstszym sposobem skonfigurowania nowego użytkownika jest środowisko OOBE (out-of-box experience) urządzenia HoloLens. Podczas instalacji urządzenie HoloLens monituje użytkownika o zalogowanie się przy użyciu konta, którego chce użyć na urządzeniu. To konto może być kontem konto Microsoft lub kontem przedsiębiorstwa skonfigurowanym na platformie Azure. Zobacz Konfigurowanie urządzenia [HoloLens (1. generacji)](hololens1-start.md) lub [HoloLens 2.](hololens2-start.md)

Podobnie jak w przypadku systemu Windows na innych urządzeniach logowanie podczas instalacji powoduje utworzenie profilu użytkownika na urządzeniu. Profil użytkownika przechowuje aplikacje i dane. To samo konto umożliwia również logowanie się pojedynczego dla aplikacji, takich jak Microsoft Edge lub Microsoft Store, przy użyciu interfejsów API Menedżera kont systemu Windows.  

Jeśli do logowania się na urządzeniach HoloLens używasz konta przedsiębiorstwa lub organizacji, urządzenie HoloLens zostanie rejestrowane w infrastrukturze IT organizacji. Ta rejestracja umożliwia administratorowi IT skonfigurowanie usługi Mobile Zarządzanie urządzeniami (MDM) w celu wysyłania zasad grupy do urządzenia HoloLens.

Domyślnie, podobnie jak w Windows 10 urządzeniach, konieczne będzie ponowne zalogowanie się po ponownym uruchomieniu urządzenia HoloLens lub wznowieniu go z trybu wstrzymania. Aby zmienić to zachowanie, można użyć aplikacji Ustawienia lub można kontrolować zachowanie za pomocą zasad grupy.

### <a name="linked-accounts"></a>Połączone konta

Podobnie jak w przypadku klasycznej wersji systemu Windows, możesz połączyć dodatkowe poświadczenia konta internetowego z kontem holoLens. Takie łączenie ułatwia dostęp do zasobów w aplikacjach lub w aplikacjach (takich jak Sklep) lub łączenie dostępu do zasobów osobistych i służbowych. Po połączeniu konta z urządzeniem możesz udzielić uprawnień do używania urządzenia w aplikacjach, aby nie trzeba było logować się do poszczególnych aplikacji.

Łączenie kont nie oddziela danych użytkownika utworzonych na urządzeniu, takich jak obrazy lub pliki do pobrania.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Konfigurowanie obsługi wielu użytkowników (tylko usługa Azure AD)

Urządzenie HoloLens obsługuje wielu użytkowników z tej samej dzierżawy usługi Azure AD. Aby korzystać z tej funkcji, należy użyć konta należącego do organizacji w celu skonfigurowania urządzenia. Następnie inni użytkownicy z tej samej dzierżawy mogą zalogować się na urządzeniu z ekranu logowania lub przez naciśnięcie kafelka użytkownika w panelu Start. W tym samym czasie może być zalogowany tylko jeden użytkownik. Gdy użytkownik się wyczyszczy, urządzenie HoloLens wyebieruje poprzedniego użytkownika. Pierwszy użytkownik na urządzeniu jest traktowany jako właściciel urządzenia, ale w przypadku dołączenia do usługi Azure AD dowiedz się więcej [o właścicielach urządzeń.](security-adminless-os.md#device-owner)

Wszyscy użytkownicy mogą używać aplikacji zainstalowanych na urządzeniu. Jednak każdy użytkownik ma własne dane aplikacji i preferencje. Usunięcie aplikacji z urządzenia powoduje usunięcie jej dla wszystkich użytkowników.  

Urządzenia ustawione przy użyciu kont usługi Azure AD nie będą zezwalać na logowanie się na urządzeniu przy użyciu konta Microsoft. Wszystkie kolejne używane konta muszą być kontami usługi Azure AD z tej samej dzierżawy co urządzenie. Nadal możesz [zalogować się przy użyciu konta Microsoft do aplikacji,](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) które je obsługują (takich jak Microsoft Store). Aby zmienić sposób logowania na urządzeniu przy użyciu kont usługi Azure AD na konta Microsoft, należy zmienić [jego ukośnik.](hololens-recovery.md#clean-reflash-the-device)

> [!NOTE]
> **Urządzenie HoloLens (1. generacja)** zaczęło obsługiwać wielu użytkowników usługi Azure AD w Aktualizacja systemu Windows 10 z kwietnia 2018 [w](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) ramach [Windows Holographic for Business](hololens-upgrade-enterprise.md).

### <a name="multiple-users-listed-on-sign-in-screen"></a>Wielu użytkowników na ekranie logowania

Wcześniej na ekranie Logowanie był pokazywany tylko ostatnio zalogowany użytkownik, a także punkt wejścia "Inny użytkownik". Otrzymaliśmy opinie klientów, że nie jest to wystarczające, jeśli wielu użytkowników zalogowało się na urządzeniu. Nadal wymagane było ponowne wpisze nazwę użytkownika itp.

Wprowadzona w systemie Windows Holographic w wersji  [21H1](hololens-release-notes.md#windows-holographic-version-21h1)po wybraniu pozycji Inny użytkownik, która znajduje się po prawej stronie pola wprowadzania numeru PIN, na ekranie Logowanie będzie wyświetlanych wielu użytkowników, którzy wcześniej zalogowali się na urządzeniu. Dzięki temu użytkownicy mogą wybrać swój profil użytkownika, a następnie zalogować się przy użyciu Windows Hello poświadczeń. Nowego użytkownika można również dodać do urządzenia z tej strony Inni użytkownicy za pośrednictwem **przycisku Dodaj** konto.

W menu Inni użytkownicy na przycisku Inni użytkownicy zostanie wyświetlany ostatni użytkownik zalogowany na urządzeniu. Wybierz ten przycisk, aby powrócić do ekranu Logowania dla tego użytkownika.

![Domyślny ekran logowania](./images/multiusers1.jpg)

<br>

![Ekran logowania innych użytkowników](./images/multiusers2.jpg)

## <a name="removing-users"></a>Usuwanie użytkowników

Możesz usunąć użytkownika z urządzenia, przechodząc do menu Ustawienia  >  **Konta Inne**  >  **osoby.** Ta akcja odzyskuje również miejsce, usuwając wszystkie dane aplikacji tego użytkownika z urządzenia.  

## <a name="using-single-sign-on-within-an-app"></a>Korzystanie z logowania pojedynczego w aplikacji

Jako deweloper aplikacji możesz korzystać z połączonych tożsamości na urządzeniu HoloLens przy użyciu interfejsów API Menedżera kont systemu [Windows,](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core)tak jak na innych urządzeniach z systemem Windows. Przykłady kodu dla tych interfejsów API są dostępne w witrynie GitHub: [Przykład zarządzania kontami internetowymi](https://go.microsoft.com/fwlink/p/?LinkId=620621).

Wszelkie ewentualne przerwania konta, takie jak żądanie zgody użytkownika na informacje o koncie, uwierzytelnianie dwuskładnikowe itd., muszą być obsługiwane, gdy aplikacja zażąda tokenu uwierzytelniania.

Jeśli aplikacja wymaga określonego typu konta, które nie zostało wcześniej połączone, aplikacja może poprosić system o monit o dodanie konta przez użytkownika. To żądanie wyzwala uruchomienie okienka ustawień konta jako modalnego podrzędnego działania aplikacji. W przypadku aplikacji 2D to okno jest renderowane bezpośrednio na środku aplikacji. W przypadku aplikacji aparatu Unity to żądanie krótko pobiera użytkownika z aplikacji holograficznej w celu renderowania okna podrzędnego. Aby uzyskać informacje o dostosowywaniu poleceń i akcji w tym okienku, zobacz [WebAccountCommand, klasa](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## <a name="enterprise-and-other-authentication"></a>Uwierzytelnianie przedsiębiorstwa i inne

Jeśli aplikacja używa innych typów uwierzytelniania, takich jak NTLM, Basic lub Kerberos, możesz użyć interfejsu użytkownika poświadczeń systemu [Windows](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) do zbierania, przetwarzania i przechowywania poświadczeń użytkownika. Środowisko użytkownika do zbierania tych poświadczeń jest bardzo podobne do innych przerwań konta opartego na chmurze i jest wyświetlane jako aplikacja podrzędna na podstawie aplikacji 2D lub przez krótki czas wstrzymuje aplikację aparatu Unity w celu pokazania interfejsu użytkownika.

## <a name="deprecated-apis"></a>Przestarzałe interfejsy API

Jednym ze sposobów tworzenia aplikacji dla urządzenia HoloLens jest to, że interfejs API [OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) nie jest w pełni obsługiwany. Mimo że interfejs API zwraca token, jeśli konto podstawowe działa prawidłowo, przerwania, takie jak opisane w tym artykule, nie wyświetlają żadnego interfejsu użytkownika dla użytkownika i nie mogą poprawnie uwierzytelnić konta.

## <a name="frequently-asked-questions"></a>Często zadawane pytania

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>Czy Windows Hello dla firm na urządzeniach HoloLens (1. generacja)?

Windows Hello dla firm (która obsługuje logowanie przy użyciu numeru PIN) jest obsługiwana dla urządzenia HoloLens (1. generacja). Aby zezwolić Windows Hello dla firm numeru PIN na urządzeniach HoloLens:

1. Urządzenie HoloLens musi być [zarządzane przez rozwiązanie MDM.](hololens-enroll-mdm.md)
1. Musisz włączyć Windows Hello dla firm dla urządzenia. (Zobacz[instrukcje dotyczące Microsoft Intune.](https://docs.microsoft.com/intune/windows-hello))
1. Na urządzeniach HoloLens użytkownik może następnie skonfigurować numer PIN przy użyciu opcji logowania Ustawienia Dodaj numer  >    >   PIN.

> [!NOTE]
> Użytkownicy, którzy logują się przy użyciu konta konto Microsoft mogą również skonfigurować numer PIN w ustawieniach Opcje logowania  >    >  **Dodaj numer PIN.** Ten numer PIN jest skojarzony [z Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello), a nie [Windows Hello dla firm](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>Jak zaimplementowano uwierzytelnianie biometryczne irysów na urządzeniach HoloLens 2?

Urządzenie HoloLens 2 obsługuje uwierzytelnianie irysów. Iris jest oparty na technologii Windows Hello i jest obsługiwany do użytku zarówno przez Azure Active Directory jak i konta Microsoft. Irysy są implementowane w taki sam sposób jak inne Windows Hello i osiągają zabezpieczenia biometryczne FAR na 1/100 tys.

Zobacz wymagania [biometryczne i specyfikacje dotyczące Windows Hello,](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) aby uzyskać więcej informacji. Dowiedz się więcej [o Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) i [Windows Hello dla firm](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). 

### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>Jak typ konta wpływa na zachowanie logowania?

Jeśli stosujesz zasady logowania, zasady są zawsze przestrzegane. Jeśli nie zastosowano żadnych zasad logowania, są to domyślne zachowania dla każdego typu konta:

- **Azure AD:** prosi o uwierzytelnianie domyślnie i można je skonfigurować za pomocą **ustawień,** aby nie żądać już uwierzytelniania.
- **konto Microsoft:** zachowanie blokady różni się, umożliwiając automatyczne odblokowywanie, jednak uwierzytelnianie logowania jest nadal wymagane podczas ponownego uruchamiania.
- **Konto lokalne:** zawsze pyta o uwierzytelnienie w postaci hasła, nie można go skonfigurować w **ustawieniach**

> [!NOTE]
> Czasomierze nieaktywności nie są obecnie obsługiwane, co oznacza, że zasady **AllowIdleReturnWithoutPassword** są przestrzegane tylko wtedy, gdy urządzenie przejdzie do trybu StandBy.

## <a name="additional-resources"></a>Dodatkowe zasoby

Przeczytaj o wiele więcej na temat ochrony tożsamości użytkowników i uwierzytelniania w [dokumentacji Windows 10 zabezpieczeń i tożsamości.](https://docs.microsoft.com/windows/security/identity-protection/)

Dowiedz się więcej na temat konfigurowania infrastruktury tożsamości hybrydowej dokładnie z [dokumentacji tożsamości hybrydowej platformy Azure.](https://docs.microsoft.com/azure/active-directory/hybrid/)
