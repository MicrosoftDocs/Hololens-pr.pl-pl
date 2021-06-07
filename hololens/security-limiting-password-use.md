---
title: Ograniczanie użycia hasła
description: ograniczanie użycia hasła dla urządzenia HoloLens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, limiting password use, password, hololens password, sign-in, signing in, windows hello, hello, windows account manager, FIDO2 sign in, FIDO 2, WEBAUTHN, local account, hololens security
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 6233e9f422022dc3fb4f3e615261504b9686f501
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379712"
---
# <a name="limiting-password-use"></a>Ograniczanie użycia hasła

Obecnie większość systemów komputerowych wykorzystuje poświadczenia użytkownika jako podstawę zabezpieczeń, co czyni je zależnym od haseł wielokrotnego użytku utworzonych przez użytkownika. W rezultacie hasła stają się również najczęstszą przyczyną naruszeń zabezpieczeń konta i danych. Na przykład hasła mogą być przechwytywane w przypadku transmisji lub kradzieży z serwera (przez wyłudzanie informacji lub ataki z atakiem typu "rozsyłanie haseł") i mogą zostać naruszone w celu uzyskania dostępu do konta użytkownika.

Aby zwiększyć bezpieczeństwo i ochronę kont, urządzenie HoloLens 2 ma możliwość włączenia silnych, sprzętowych poświadczeń bez hasła (w tym Windows Hello) do logowania się na urządzeniu, co zapewnia bezproblemowy dostęp do chmury firmy Microsoft.

## <a name="signing-in-from-another-device"></a>Logowanie z innego urządzenia

Urządzenie HoloLens 2 oferuje opcje zdalnego logowania urządzeń dla kont służbowych usługi Azure Active Directory podczas początkowej konfiguracji urządzenia i logowania użytkowników, aby ograniczyć potrzebę wpisywania złożonych haseł i zminimalizować potrzebę haseł jako poświadczeń. Użytkownicy i organizacje, które używają kart inteligentnych do uwierzytelniania, mają trudności z używaniem tych poświadczeń na urządzeniach takich jak HoloLens 2, a często organizacje opracowują skomplikowane systemy i kosztowne procesy, aby rozwiązać problem. Aby rozwiązać ten problem, usługa Azure AD oferuje dwie opcje logowania bez hasła na urządzeniach HoloLens 2.

Pierwsza metoda uwierzytelniania opiera się na nowych możliwościach w aplikacji Microsoft Authenticator w celu zapewnienia uwierzytelniania opartego na kluczach, które umożliwia poświadczenie użytkownika powiązane z urządzeniem. Po włączeniu dzierżawy przez administratora podczas konfigurowania urządzenia HoloLens zostanie wyświetlony komunikat z informacją o naciśnięciu numeru w aplikacji. Aby kontynuować konfigurację urządzenia HoloLens, muszą oni dopasować numer w aplikacji wystawcy uwierzytelnienia, wybrać pozycję Zatwierdź, podać numer PIN lub uwierzytelnianie biometryczne i pełne. Opisano to bardziej szczegółowo w te [tematach logowania bez hasła.](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)

Drugi to przepływ kodu urządzenia, który jest intuicyjny dla użytkowników i nie wymaga dodatkowej infrastruktury.  To zdalne zachowanie logowania opiera się na innym zaufanym urządzeniu, które obsługuje preferowany mechanizm uwierzytelniania organizacji. Po zakończeniu tokeny są wydawane z powrotem do urządzenia HoloLens w celu ukończenia logowania lub konfiguracji urządzenia. Kroki w tym przepływie są następujące:

  1. Użytkownik przechodzący przez początkową konfigurację urządzenia lub przepływy logowania w ramach OOBE ma link "Zaloguj się z innego urządzenia" i naciska go. Powoduje to zainicjowanie sesji logowania zdalnego.
  1. Następnie zostanie pokazana strona sondowania zawierająca krótki identyfikator URI (), który wskazuje punkt końcowy uwierzytelniania urządzenia usługi [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin) Azure AD Secure Token Service (STS). Użytkownik jest również prezentowany z kodem jednokierunkowym, który jest bezpiecznie generowany w chmurze i ma maksymalny okres istnienia 15 minut. Oprócz generowania kodu usługa Azure AD tworzy również zaszyfrowaną sesję po zainicjowaniu żądania logowania zdalnego w poprzednim kroku i razem, a także do zatwierdzenia zdalnego żądania logowania jest używany kod i URI.
  1. Następnie użytkownik przechodzi do identyfikatorów URI z innego urządzenia i jest monitowany o wprowadzenie kodu wyświetlanego na urządzeniu HoloLens 2.
  1. Gdy użytkownik wprowadzi kod, usługa Azure AD STS wyświetli stronę wskazującą urządzenie HoloLens 2 użytkownika, które wyzwoliło żądanie zdalnego logowania i zażądało generacji kodu. Następnie użytkownik jest monitowany o potwierdzenie, aby zapobiec atakom wyłudzania informacji.
  1. Jeśli użytkownik zdecyduje się na dalsze logowanie do wyświetlanej "aplikacji", usługa Azure AD STS wyświetli monit o podanie poświadczeń. Po pomyślnym uwierzytelnieniu usługa Azure AD STS aktualizuje buforowane sesje zdalne jako "zatwierdzone" wraz z kodem autoryzacji.
  1. Na koniec strona sondowania na urządzeniu HoloLens 2 użytkownika otrzymuje odpowiedź "Autoryzowane" z usługi Azure AD i kontynuuje walidację kodu użytkownika, skojarzonego z nim przechowywanego kodu autoryzacji i generuje tokeny OAuth zgodnie z żądaniem ukończenia konfiguracji urządzenia. Utworzony token uwierzytelniania jest ważny przez 1 godzinę, a token odświeżania ma okres istnienia 90 dni.

Algorytmy generowania kodu i szyfrowania używane w tym przepływie są zgodne ze standardem FIPS. Urządzenia HoloLens 2 wykorzystują moduł TPM do zabezpieczania kluczy urządzeń i szyfrowania tokenów wygenerowanych po uwierzytelnieniu użytkownika przy użyciu kluczy chronionych sprzętowo. Więcej informacji na temat zabezpieczeń tokenów na urządzeniach HoloLens 2 znajduje się w tece Co to jest [podstawowy token odświeżania (PRT).](https://docs.microsoft.com/azure/active-directory/devices/concept-primary-refresh-token)

## <a name="device-sign-in-with-windows-hello"></a>Logowanie urządzenia przy użyciu Windows Hello

[Windows Hello](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) oferuje opcje bez hasła wbudowane bezpośrednio w system operacyjny, które pozwalają użytkownikom logować się do urządzenia przy użyciu irysów lub numeru PIN. Numer PIN jest zawsze dostępny jako poświadczenie i jest wymagany do konfiguracji urządzenia, natomiast irysy są opcjonalne i mogą być pomijane. Użytkownicy mogą logować się na urządzeniach HoloLens przy użyciu osobistego konto Microsoft lub Azure Active Directory konta służbowego bez [wprowadzania hasła.  ](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless) Takie opcje zapewniają użytkownikom szybki, bezpieczny dostęp do pełnego systemu Windows, aplikacji, danych, witryn internetowych i usług. Strategia firmy Microsoft mająca na celu środowisko bez hasła jest szczegółowo opisane tutaj.

Po utworzeniu Windows Hello ustanawiana jest zaufana relacja z dostawcą tożsamości i tworzona jest asymetryczna para kluczy do uwierzytelniania. Gest Windows Hello (taki jak irys lub numer PIN) zapewnia entropię do odszyfrowywania klucza prywatnego z mikroukładu Trusted Platform Module (TPM) urządzenia. Ten klucz prywatny jest następnie używany do podpisywania żądań wysyłanych do serwera uwierzytelniania, a po pomyślnym uwierzytelnieniu użytkownik uzyskuje dostęp do poczty e-mail, zdjęć i innych ustawień konta.

Aby uzyskać więcej informacji, zobacz następującą infografikę:

  ![Windows Hello logowania](images/security-hello-sign-in.png)
  
Na ilustracji przedstawionej powyżej należy zauważyć, że element nonce oznacza "liczba raz" i jest liczbą losową lub częściowo losową wygenerowaną. Po skonfigurowaniu Windows Hello biometrycznego lub numeru PIN nigdy nie opuszcza urządzenia, na którym zostało aprowowane. Nawet jeśli numer PIN Windows Hello użytkownika zostanie skradziony, na przykład w ramach ataku wyłudzania informacji, będzie on bezużyteczny bez fizycznego [urządzenia użytkownika.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password)

Aby zapewnić dodatkowe zabezpieczenia, poświadczenia usługi Windows Hello są chronione przez moduł Trusted Platform Module (TPM) w celu zabezpieczenia poświadczeń przed naruszeniami i uzupełnienia ochrony przed wieloma nieprawidłowymi wpisami oraz ochrony przed złośliwym oprogramowaniem w celu uniknięcia zagrożenia. Aby uzyskać więcej informacji na temat logowania jednokrotnego (SSO, Single Sign-On), przeczytaj [to omówienie metod logowania jednokrotnego.](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on)

Uwierzytelnianie irysów powraca do numeru PIN. Aby skonfigurować nowy numer PIN (silny wystawca uwierzytelnienia) na urządzeniu, użytkownik musi niedawno przejść przez uwierzytelnianie wieloskładnikowe [(MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) w celu ukończenia procesu.

## <a name="single-sign-on-with-web-account-manager"></a>Logowanie pojedyncze z Menedżer kont internetowych

Logowanie jednokrotne umożliwia użytkownikom bez hasła logowanie się do urządzenia przy użyciu osobistego konta użytkownika lub konta służbowego. Użytkownik jest automatycznie autoryzowany za pomocą logowania jednokrotnego we wszystkich zintegrowanych aplikacjach i usługach za [pośrednictwem Menedżer kont internetowych API.](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)

Po dodaniu tożsamości za pośrednictwem jednej aplikacji może ona, za zgodą użytkownika, stać się dostępna dla wszystkich aplikacji i usług przy użyciu integracji na poziomie systemu. Znacznie zmniejsza to obciążenie związane z logowaniem do aplikacji i zapewnia użytkownikom bezproblemowe środowisko obsługi tożsamości.

Aby uzyskać więcej informacji na temat implementowania Menedżer kont internetowych API, przejdź do [tematu Implementowanie](https://docs.microsoft.com/windows/uwp/security/web-account-manager)Menedżer kont internetowych API.

  ![interfejs API Zabezpieczenia](images/security-api-img.png)
  
W przypadku pakietów aplikacji o specjalnych wymaganiach dotyczących uwierzytelniania Menedżer kont internetowych (CI) można rozszerzać dla niestandardowych dostawców tożsamości. Użytkownicy mogą pobrać niestandardowego dostawcę tożsamości spakowanego jako aplikacja platformy platforma uniwersalna systemu Windows (UWP) z usługi Microsoft Store, aby włączyć logowanie jednokrotne w innych aplikacjach zintegrowanych z tym dostawcą tożsamości.

Aby uzyskać więcej informacji na temat implementowania niestandardowych dostawców tożsamości PODMIOTu, zobacz Dokumentacja interfejsu [API niestandardowego dostawcy tożsamości DLA](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true).

## <a name="windows-hello-and-fido2-sign-in-with-webauthn"></a>Windows Hello i FIDO2 przy użyciu protokołu WebAuthn

Urządzenie HoloLens 2 może używać poświadczeń użytkownika bez haseł (takich jak klucze zabezpieczeń Windows Hello lub FIDO2) do bezpiecznego logowania się w Internecie za pośrednictwem usługi Microsoft Edge i witryn internetowych, które obsługują webAuthn. FiDO2 umożliwia poświadczeniom użytkownika korzystanie z urządzeń opartych na standardach w celu uwierzytelniania w Usługi online.

> [!Note]
> Specyfikacje [WebAuthn](https://www.w3.org/TR/webauthn/) i FIDO2 [CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html) są implementowane w usługach. Podpisane metadane określone przez webauthn i FIDO2 zawierają informacje , takie jak to, czy użytkownik był obecny, i weryfikują uwierzytelnianie za pomocą gestu lokalnego.

Podobnie jak Windows Hello, gdy użytkownik tworzy i rejestruje poświadczenia FIDO2, urządzenie (HoloLens 2 lub klucz zabezpieczeń FIDO2) generuje na urządzeniu klucz prywatny i publiczny. Klucz prywatny jest bezpiecznie przechowywany na urządzeniu i można go używać tylko po odblokowaniu przy użyciu lokalnego gestu, takiego jak biometryczny lub numer PIN. Gdy klucz prywatny jest przechowywany, klucz publiczny jest wysyłany do systemu konto Microsoft w chmurze i rejestrowany przy użyciu skojarzonego konta użytkownika.

Po zalogowaniu się przy użyciu konta MSA i usługi Azure AD system wysyła wygenerowany numer lub zmienną danych do urządzenia HoloLens 2 lub FIDO2. Urządzenie HoloLens 2 lub urządzenie podpisuje identyfikację za pomocą klucza prywatnego. Podpisana identyfikacja i metadane są wysyłane z powrotem do konto Microsoft i weryfikowane przy użyciu klucza publicznego.

Windows Hello i FIDO2 implementują poświadczenia oparte na urządzeniu HoloLens, w szczególności wbudowanej Trusted Platform Module bezpiecznej enklawy. Enklawa modułu TPM przechowuje klucz prywatny i wymaga do jego odblokowania klucza biometrycznego lub numeru PIN. Podobnie klucz zabezpieczeń FIDO2 to małe urządzenie zewnętrzne z wbudowaną bezpieczną enklawą, która przechowuje klucz prywatny i wymaga użycia danych biometrycznych lub numeru PIN do jego odblokowania.

Obie opcje oferują uwierzytelnianie dwuskładnikowe w jednym kroku, co wymaga zarówno zarejestrowanego urządzenia, jak i danych biometrycznych lub numeru PIN w celu pomyślnego zalogowania się. Aby uzyskać więcej informacji, zobacz grafice i proces silnego uwierzytelniania za pomocą klucza zabezpieczeń FIDO2.

### <a name="strong-authentication-with-fido2-security-key"></a>Silne uwierzytelnianie przy użyciu klucza zabezpieczeń FIDO2

  ![FIDO img](images/security-fido2-whfb-smaller.png)

1. Użytkownik podłącza klucz zabezpieczeń FIDO2 do urządzenia HoloLens 2
1. System Windows wykrywa klucz zabezpieczeń FIDO2
1. Urządzenie HoloLens wysyła żądanie uwierzytelnienia
1. Usługa Azure AD wysyła z powrotem wiadomość e-mail
1. Użytkownik kończy gest odblokowania magazynów kluczy prywatnych w bezpiecznej enklawie klucza zabezpieczeń
1. Klucz zabezpieczeń FIDO2 podpisuje element nonce za pomocą klucza prywatnego
1. Żądanie tokenu PRT ze podpisanym nonce jest wysyłane do usługi Azure AD
1. Usługa Azure AD weryfikuje klucz FIDO
1. Usługa Azure AD zwraca prt i TGT, aby umożliwić dostęp do zasobów

Usługi MSA i Azure AD są jednymi z pierwszych baz danych, które obsługują uwierzytelnianie bez hasła przez zaimplementowanie protokołu WebAuthn.

Aby uzyskać więcej informacji na temat używania uwierzytelniania WebAuthn z aplikacjami i/lub zestawami SDK, przejdź do tematu [WebAuthn APIs for password-less authentication on Windows 10](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/webauthnapis)(Interfejsy API webAuthn do uwierzytelniania bez hasła w Windows 10 .

Urządzenie HoloLens 2 obsługuje urządzenia zabezpieczające FIDO2, które są implementowane w celu specyfikacji i spełnienia wymagań wymienionych w te Azure Active Directory logowania bez hasła — klucze zabezpieczeń [FIDO2](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless#fido2-security-keys) powinny być obsługiwane.

## <a name="local-accounts"></a>Konta lokalne

Dla wdrożeń w trybie offline można skonfigurować jedno konto lokalne. Konta lokalne nie są domyślnie włączone i należy je skonfigurować podczas aprowizowania urządzeń. Muszą się zalogować przy użyciu hasła i nie obsługują alternatywnych metod uwierzytelniania (takich jak Windows Hello dla firm [lub Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)). [](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)

Więcej szczegółów na temat kont użytkowników urządzenia HoloLens można znaleźć na stronie [Tożsamość urządzenia HoloLens.](https://docs.microsoft.com/hololens/hololens-identity)

Administratorzy IT dostosowują, czy użytkownik może używać konta MSA do uwierzytelniania połączeń i usług niezwiązanych z pocztą e-mail za pośrednictwem [usługi AllowMicrosoftAccountConnection.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection) Aby uzyskać informacje na temat zasad konfiguracji haseł, zasad idling i zasad ekranu blokady, zobacz [Device Lock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock).
