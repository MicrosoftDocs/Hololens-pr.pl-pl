---
title: Zarządzanie tożsamością użytkownika i logowaniem na HoloLens
description: Dowiedz się, jak zarządzać tożsamościami użytkowników, pomocą techniczną dla wielu użytkowników, zabezpieczeniami, uwierzytelnianiem przedsiębiorstwa i logowaniem HoloLens urządzeń.
keywords: HoloLens, user, account, AAD, Azure AD, adfs, microsoft account, msa, credentials, reference
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: qianw211
ms.author: v-qianwen
ms.date: 8/13/2021
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: sekerawa
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: c2fd7c8ee82fbf70b9eaa2b5eee1d73e1235d8b5
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033254"
---
# <a name="manage-user-identity-and-login-for-hololens"></a>Zarządzanie tożsamością użytkownika i logowaniem na HoloLens

> [!NOTE]
> Ten artykuł zawiera informacje techniczne dla specjalistów IT i entuzjaści technologii. Jeśli szukasz instrukcji konfigurowania HoloLens, przeczytaj temat["Konfigurowanie aplikacji HoloLens (1. generacji)](hololens1-start.md)" lub " Konfigurowanie HoloLens[2".](hololens2-start.md)

## <a name="lets-talk-about-setting-up-user-identity-for-hololens-2"></a>Porozmawiajmy o konfigurowaniu tożsamości użytkownika dla HoloLens 2

Podobnie jak Windows urządzeń, HoloLens zawsze działają w kontekście użytkownika. Zawsze istnieje tożsamość użytkownika. HoloLens traktuje tożsamość w niemal taki sam sposób jak Windows 10 urządzenia. Logowanie podczas instalacji powoduje utworzenie profilu użytkownika na HoloLens, w których są przechowywane aplikacje i dane. To samo konto zapewnia również logowanie pojedyncze dla aplikacji, takich jak Edge lub Dynamics 365 Remote Assist, przy użyciu interfejsów API Windows Account Manager. 

HoloLens obsługuje kilka rodzajów tożsamości użytkowników. Możesz wybrać dowolny z tych trzech typów kont, ale zdecydowanie zalecamy usługę Azure AD, ponieważ jest ona najlepsza do zarządzania urządzeniami. Tylko konta usługi Azure AD obsługują wielu użytkowników. 

| Typ tożsamości | Konta na urządzenie | Opcje uwierzytelniania |
| --- | --- | --- |
| [Azure Active Directory](/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Dostawca poświadczeń internetowych platformy Azure</li><li>Azure Authenticator App</li><li>Biometryczne (irysy) &ndash; HoloLens<sup></sup> tylko 2 </li><li>Klucz zabezpieczeń FIDO2</li><li>Numer PIN &ndash; opcjonalny dla HoloLens (1. generacji), wymagany dla HoloLens 2</li><li>Hasło</li></ul> |
| [Konto Microsoft (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Tylko biometryczne &ndash; (irysy) HoloLens 2</li><li>Numer PIN &ndash; opcjonalny dla HoloLens (1. generacji), wymagany dla HoloLens 2</li><li>Hasło</li></ul> |
| [Konto lokalne](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | 1 | Hasło |

Konta połączone z chmurą (Azure AD i MSA) oferują więcej funkcji, ponieważ mogą korzystać z usług platformy Azure.  
> [!IMPORTANT]
> 1 — Azure AD — wersja Premium logowanie do urządzenia nie jest wymagane. Jest to jednak wymagane w przypadku innych funkcji wdrażania w chmurze o niskim poziomie dotyku, takich jak rejestracja automatyczna i rozwiązanie Autopilot.

> [!NOTE]
> 2 — Chociaż urządzenie HoloLens 2 może obsługiwać maksymalnie 64 konta usługi Azure AD, tylko 31 z tych kont może zarejestrować się w uwierzytelnianiu irysów. Jest to zgodne z innymi opcjami uwierzytelniania [biometrycznego dla usługi Windows Hello for Business.](/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)

> [!IMPORTANT]
> 3 — Konto lokalne można skonfigurować tylko na urządzeniu za pośrednictwem pakietu aprowizowania podczas [OOBE.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)Nie można go dodać później w aplikacji ustawienia. Jeśli chcesz użyć konta lokalnego na urządzeniu, które jest już ustawione, musisz odlashować lub [zresetować urządzenie.](hololens-recovery.md)

## <a name="setting-up-users"></a>Konfigurowanie użytkowników

Istnieją dwa sposoby skonfigurowania nowego użytkownika na HoloLens. Najbardziej powszechnym sposobem jest HoloLens out-of-box experience (OOBE). Jeśli używasz Azure Active Directory, [inni użytkownicy mogą logować się](#setting-up-multi-user-support-azure-ad-only) po OOBE przy użyciu poświadczeń usługi Azure AD. HoloLens urządzenia, które są początkowo ustawione przy użyciu konta MSA lub konta lokalnego podczas OOBE, nie będą obsługiwać wielu użytkowników. Zobacz Konfigurowanie aplikacji [HoloLens (1. generacja)](hololens1-start.md) [lub HoloLens 2.](hololens2-start.md)

Jeśli używasz konta przedsiębiorstwa lub organizacji do logowania się do HoloLens, HoloLens zostanie HoloLens w infrastrukturze IT organizacji. Ta rejestracja umożliwia administratorowi IT skonfigurowanie usługi Mobile Zarządzanie urządzeniami (MDM) w celu wysyłania zasad grupy do HoloLens.

Podobnie Windows na innych urządzeniach logowanie podczas instalacji powoduje utworzenie profilu użytkownika na urządzeniu. Profil użytkownika przechowuje aplikacje i dane. To samo konto zapewnia również logowanie pojedyncze dla aplikacji, takich jak Edge lub Microsoft Store, przy użyciu interfejsów API Windows Account Manager.

Domyślnie, podobnie jak w Windows 10 urządzeń, musisz zalogować się ponownie po ponownym uruchomieniu HoloLens wznowieniu z trybu wstrzymania. Możesz użyć aplikacji Ustawienia, aby zmienić to zachowanie, lub zachowanie może być kontrolowane przez zasady grupy.

### <a name="linked-accounts"></a>Połączone konta

Podobnie jak w przypadku klasycznej Windows, możesz połączyć inne poświadczenia konta internetowego z kontem HoloLens sieci Web. Takie łączenie ułatwia dostęp do zasobów w aplikacjach lub w aplikacjach (takich jak Sklep) lub łączenie dostępu do zasobów osobistych i służbowych. Po połączeniu konta z urządzeniem możesz udzielić uprawnień do używania urządzenia w aplikacjach, aby nie trzeba było logować się do poszczególnych aplikacji.

Łączenie kont nie oddziela danych użytkownika utworzonych na urządzeniu, takich jak obrazy lub pliki do pobrania.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Konfigurowanie obsługi wielu użytkowników (tylko usługa Azure AD)

HoloLens obsługuje wielu użytkowników z tej samej dzierżawy usługi Azure AD. Aby korzystać z tej funkcji, należy użyć konta należącego do organizacji w celu skonfigurowania urządzenia. Następnie inni użytkownicy z tej samej dzierżawy mogą zalogować się na urządzeniu z ekranu logowania lub przez naciśnięcie kafelka użytkownika w panelu Start. Jednocześnie może być zalogowany tylko jeden użytkownik. Gdy użytkownik się HoloLens, HoloLens się poprzedniego użytkownika. 

>[!IMPORTANT]
> Pierwszy użytkownik urządzenia jest traktowany jako właściciel urządzenia, ale w przypadku dołączenia do usługi Azure AD dowiedz się [więcej o właścicielach urządzeń.](security-adminless-os.md#device-owner)

Wszyscy użytkownicy mogą korzystać z aplikacji zainstalowanych na urządzeniu. Jednak każdy użytkownik ma własne dane aplikacji i preferencje. Usunięcie aplikacji z urządzenia powoduje jej usunięcie dla wszystkich użytkowników.  

Urządzenia ustawione przy użyciu kont usługi Azure AD nie zezwalają na logowanie się na urządzeniu przy użyciu konta Microsoft. Wszystkie kolejne używane konta muszą być kontami usługi Azure AD z tej samej dzierżawy co urządzenie. Nadal możesz [zalogować się przy użyciu konta Microsoft do aplikacji,](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) które je obsługują (takich jak Microsoft Store). Aby zmienić sposób logowania z kont usługi Azure AD na konta Microsoft w celu zalogowania się na urządzeniu, należy [zmienić jego ukośnik.](hololens-recovery.md#clean-reflash-the-device)

> [!NOTE]
> **HoloLens (1. generacji)** rozpoczęto obsługę wielu użytkowników usługi Azure AD w aktualizacji z kwietnia [2018 Windows 10 kwietnia 2018](/windows/mixed-reality/release-notes-april-2018) r. w ramach [Windows Holographic for Business.](hololens-upgrade-enterprise.md)

### <a name="multiple-users-are-listed-on-sign-in-screen"></a>Na ekranie logowania znajduje się wielu użytkowników

Wcześniej na ekranie logowania był pokazywany tylko ostatnio zalogowany użytkownik i punkt wejścia "Inny użytkownik". Otrzymaliśmy opinie klientów, że nie jest to wystarczające, jeśli wielu użytkowników zalogowało się na urządzeniu. Nadal wymagane było ponowne wpisze swoją nazwę użytkownika itp.

Wprowadzone w wersji [21H1](hololens-release-notes.md#windows-holographic-version-21h1)systemu Windows Holographic  po wybraniu pozycji Inny użytkownik znajdującej się po prawej stronie pola wprowadzania numeru PIN na ekranie logowania zostanie wyświetlanych wielu użytkowników, którzy wcześniej zalogowali się na urządzeniu. Dzięki temu użytkownicy mogą wybrać swój profil użytkownika, a następnie zalogować się przy użyciu Windows Hello poświadczeń. Nowego użytkownika można również dodać do  urządzenia z tej strony innych użytkowników za pośrednictwem **przycisku Dodaj** konto.

W menu **Inni użytkownicy** na **przycisku Inni użytkownicy** zostanie wyświetlany ostatni użytkownik zalogowany na urządzeniu. Wybierz ten przycisk, aby powrócić do ekranu logowania dla tego użytkownika.

![Domyślny ekran logowania.](./images/multiusers1.jpg)

<br>

![Ekran logowania innych użytkowników.](./images/multiusers2.jpg)

## <a name="removing-users"></a>Usuwanie użytkowników

Możesz usunąć użytkownika z urządzenia, przechodząc do konta Ustawienia  >    >  **inne osoby.** Ta akcja odzyskuje również miejsce, usuwając wszystkie dane aplikacji tego użytkownika z urządzenia.  

## <a name="using-single-sign-on-within-an-app"></a>Korzystanie z logowania pojedynczego w aplikacji

Jako deweloper aplikacji możesz korzystać z połączonych tożsamości na HoloLens przy użyciu interfejsów API menedżera kont usługi [Windows,](/uwp/api/Windows.Security.Authentication.Web.Core)tak jak na innych urządzeniach Windows kont. Przykłady kodu dla tych interfejsów API są dostępne na stronie GitHub: [Przykład zarządzania kontami internetowymi.](https://go.microsoft.com/fwlink/p/?LinkId=620621)

Wszelkie przerwania konta, które mogą wystąpić, takie jak żądanie zgody użytkownika na informacje o koncie, uwierzytelnianie dwuskładnikowe itd., muszą być obsługiwane, gdy aplikacja zażąda tokenu uwierzytelniania.

Jeśli aplikacja wymaga określonego typu konta, które nie zostało wcześniej połączone, aplikacja może poprosić system o monit o dodanie konta przez użytkownika. To żądanie wyzwala uruchomienie okienka ustawień konta jako modalnego dziecka aplikacji. W przypadku aplikacji 2D to okno jest renderowane bezpośrednio na środku aplikacji. W przypadku aplikacji aparatu Unity to żądanie krótko pobiera użytkownika z aplikacji holograficznej w celu renderowania okna podrzędnego. Aby uzyskać informacje o dostosowywaniu poleceń i akcji w tym okienku, zobacz [WebAccountCommand, klasa](/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## <a name="enterprise-and-other-authentication"></a>Enterprise i inne uwierzytelnianie

Jeśli aplikacja używa innych typów uwierzytelniania, takich jak NTLM, Basic lub Kerberos, możesz użyć interfejsu użytkownika poświadczeń usługi [Windows](/uwp/api/Windows.Security.Credentials.UI) do zbierania, przetwarzania i przechowywania poświadczeń użytkownika. Środowisko użytkownika do zbierania tych poświadczeń jest podobne do innych przerwań konta opartego na chmurze i jest wyświetlane jako aplikacja podrzędna w górnej części aplikacji 2D lub krótko wstrzymuje aplikację aparatu Unity w celu pokazania interfejsu użytkownika.

## <a name="deprecated-apis"></a>Przestarzałe interfejsy API

Jednym ze sposobów tworzenia aplikacji dla HoloLens dla komputerów stacjonarnych jest to, że interfejs API [OnlineIDAuthenticator](/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) nie jest w pełni obsługiwany. Mimo że interfejs API zwraca token, jeśli konto podstawowe jest w dobrej stanie, przerwania, takie jak opisane w tym artykule, nie wyświetlają żadnego interfejsu użytkownika dla użytkownika i nie mogą poprawnie uwierzytelnić konta.

## <a name="frequently-asked-questions"></a>Często zadawane pytania

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>Czy Windows Hello dla firm jest obsługiwana HoloLens (1. generacji)?

Windows Hello for Business (która obsługuje logowanie przy użyciu numeru PIN) jest obsługiwana HoloLens (1. generacji). Aby zezwolić Windows Hello na logowanie przy HoloLens PIN dla firm:

1. Urządzenie HoloLens musi być zarządzane [przez rozwiązanie MDM.](hololens-enroll-mdm.md)
1. Musisz włączyć Windows Hello dla firm dla urządzenia. (Zobacz[instrukcje dotyczące Microsoft Intune.](/intune/windows-hello))
1. Na HoloLens skonfigurować numer PIN użytkownik może następnie użyć opcji logowania Ustawienia Dodaj numer  >    >   PIN.

> [!NOTE]
> Użytkownicy, którzy logują się przy użyciu konta konto Microsoft mogą również skonfigurować numer PIN w Ustawienia  >  **logowania Dodaj** numer  >  **PIN.** Ten numer PIN jest skojarzony [z Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello), a nie Windows Hello [for Business.](/windows/security/identity-protection/hello-for-business/hello-overview)

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>W jaki sposób uwierzytelnianie biometryczne irysów jest implementowane HoloLens 2?

HoloLens 2 obsługuje uwierzytelnianie irysów. Iris jest oparty na technologii Windows Hello i jest obsługiwany do użytku zarówno przez Azure Active Directory jak i konta Microsoft. Irysy są implementowane w taki sam sposób jak inne Windows Hello i osiągają zabezpieczenia biometryczne FAR na [1/100 tys.](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#has-microsoft-set-any-device-requirements-for-windows-hello)

Zobacz wymagania [biometryczne i specyfikacje dotyczące Windows Hello,](/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) aby uzyskać więcej informacji. Dowiedz się więcej [o Windows Hello](/windows-hardware/design/device-experiences/windows-hello) i Windows Hello [dla firm.](/windows/security/identity-protection/hello-for-business/hello-identity-verification) 

### <a name="where-is-iris-biometric-information-stored"></a>Gdzie są przechowywane informacje biometryczne irysów?

Informacje biometryczne irysów są przechowywane lokalnie na HoloLens danych [Windows Hello specyfikacji](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#where-is-windows-hello-data-stored). Nie jest ona udostępniana i chroniona przez dwie warstwy szyfrowania. Nie jest ona dostępna dla innych użytkowników, nawet administratorów, ponieważ nie ma konta administratora w HoloLens.

### <a name="do-i-have-to-use-iris-authentication"></a>Czy muszę używać uwierzytelniania irysów?
Nie, możesz pominąć ten krok podczas instalacji. 

![Konfigurowanie irysów.](./images/setup-iris.png)

HoloLens 2 udostępnia wiele różnych opcji uwierzytelniania, w tym klucze zabezpieczeń FIDO2.

### <a name="can-iris-information-be-removed-from-the-hololens"></a>Czy informacje o irysach można usunąć z HoloLens?
Tak, można usunąć ją ręcznie w Ustawienia.


### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>Jak typ konta wpływa na zachowanie logowania?

Jeśli zastosujesz zasady do logowania, zasady będą zawsze przestrzegane. Jeśli nie są stosowane żadne zasady logowania, są to domyślne zachowania dla każdego typu konta:

- **Usługa Azure AD:** domyślnie prosi o uwierzytelnienie i można go **skonfigurować** Ustawienia nie pyta o uwierzytelnianie.
- **konto Microsoft:** zachowanie blokady różni się, umożliwiając automatyczne odblokowywanie, jednak uwierzytelnianie logowania jest nadal wymagane podczas ponownego uruchamiania.
- **Konto lokalne:** zawsze pyta o uwierzytelnienie w postaci hasła, nie można go skonfigurować w **Ustawienia**

> [!NOTE]
> Czasomierze nieaktywności nie są obecnie obsługiwane, co oznacza, że zasady **AllowIdleReturnWithoutPassword** są przestrzegane tylko wtedy, gdy urządzenie przejdzie do trybu StandBy.

## <a name="additional-resources"></a>Dodatkowe zasoby

Przeczytaj o wiele więcej na temat ochrony tożsamości użytkowników i uwierzytelniania w [dokumentacji Windows 10 zabezpieczeń i tożsamości.](/windows/security/identity-protection/)

Dowiedz się więcej na temat konfigurowania infrastruktury tożsamości hybrydowej dokładnie z [dokumentacji tożsamości hybrydowej platformy Azure.](/azure/active-directory/hybrid/)