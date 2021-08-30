---
title: Ograniczanie użycia hasła
description: ograniczenie użycia hasła dla HoloLens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, limit password use, password, hololens password, sign-in, signing in, windows hello, hello, windows account manager, FIDO2 sign in, FIDO 2, WEBAUTHN, local account, hololens security
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 24cd9b81d0d99afaa0479787b846b423310c6739
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190467"
---
# <a name="limiting-password-use"></a>Ograniczanie użycia hasła

Obecnie większość systemów komputerowych wykorzystuje poświadczenia użytkownika jako podstawę zabezpieczeń, co czyni je zależnym od haseł wielokrotnego użytku utworzonych przez użytkownika. W rezultacie hasła stają się również najczęstszą przyczyną naruszeń zabezpieczeń konta i danych. Na przykład hasła mogą zostać przechwycone podczas transmisji lub kradzieży serwera (przez wyłudzanie informacji lub ataki z atakiem typu "rozsyłanie hasła") i naruszone w celu uzyskania dostępu do konta użytkownika.

Aby zwiększyć bezpieczeństwo i ochronę kont, program HoloLens 2 ma możliwość włączenia silnych, sprzętowych poświadczeń bez hasła (w tym Windows Hello) do logowania się na urządzeniu, co zapewnia bezproblemowy dostęp do chmury firmy Microsoft.

## <a name="signing-in-from-another-device"></a>Logowanie z innego urządzenia

HoloLens 2 oferuje opcje zdalnego logowania urządzeń dla kont służbowych usługi Azure Active Directory podczas początkowej konfiguracji urządzenia i logowania użytkowników, aby ograniczyć potrzebę wpisywania złożonych haseł i zminimalizować potrzebę hasła jako poświadczeń. Użytkownicy i organizacje używające kart inteligentnych do uwierzytelniania mają trudności z używaniem tych poświadczeń na urządzeniach takich jak HoloLens 2, a często organizacje opracowują skomplikowane systemy i kosztowne procesy, aby rozwiązać problem. Aby rozwiązać ten problem, usługa Azure AD oferuje dwie opcje logowania bez hasła na HoloLens 2.

Pierwsza metoda uwierzytelniania korzysta z nowych możliwości w aplikacji Microsoft Authenticator w celu zapewnienia uwierzytelniania opartego na kluczach, które umożliwia poświadczenie użytkownika powiązane z urządzeniem. Po włączeniu w dzierżawie przez administratora podczas konfigurowania urządzenia HoloLens zostanie wyświetlony komunikat z informacją o naciśnięciu numeru w aplikacji. Aby kontynuować, muszą oni dopasować numer w aplikacji wystawcy uwierzytelnienia, wybrać pozycję Zatwierdź, podać numer PIN lub uwierzytelnianie biometryczne i HoloLens konfiguracji. Opisano to bardziej szczegółowo w te [tematach logowania bez hasła.](/azure/active-directory/authentication/howto-authentication-passwordless-phone)

Drugi to przepływ kodu urządzenia, który jest intuicyjny dla użytkowników i nie wymaga dodatkowej infrastruktury.  To zdalne zachowanie logowania opiera się na innym zaufanym urządzeniu, które obsługuje preferowany mechanizm uwierzytelniania organizacji, a po zakończeniu tokeny są wystawiane z powrotem do usługi HoloLens w celu ukończenia logowania lub konfiguracji urządzenia. Kroki tego przepływu są następujące:

  1. Użytkownik przechodzący przez początkową konfigurację urządzenia lub przepływy logowania w ramach programu OOBE ma link "Zaloguj się z innego urządzenia" i naciska go. Powoduje to zainicjowanie sesji logowania zdalnego.
  1. Następnie zostanie pokazana strona sondowania zawierająca krótki identyfikator URI (), który wskazuje punkt końcowy uwierzytelniania urządzenia w usłudze [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin) Azure AD Secure Token Service (STS). Użytkownik jest również prezentowany za pomocą kodu, który jest bezpiecznie generowany w chmurze i ma maksymalny okres istnienia 15 minut. Oprócz generowania kodu usługa Azure AD tworzy również zaszyfrowaną sesję po zainicjowaniu żądania logowania zdalnego w poprzednim kroku, a razem do zatwierdzenia żądania zdalnego logowania jest używany kod i URI.
  1. Następnie użytkownik przechodzi do identyfikator URI z innego urządzenia i jest monitowany o wprowadzenie kodu wyświetlanego na urządzeniu HoloLens 2.
  1. Gdy użytkownik wprowadzi kod, usługa Azure AD STS wyświetli stronę wskazującą urządzenie użytkownika z systemem HoloLens 2, które wyzwoliło żądanie zdalnego logowania i zażądało generacji kodu. Następnie użytkownik jest monitowany o potwierdzenie, aby zapobiec atakom wyłudzania informacji.
  1. Jeśli użytkownik zdecyduje się na dalsze logowanie do wyświetlanej "aplikacji", usługa Azure AD STS wyświetli monit o podanie poświadczeń. Po pomyślnym uwierzytelnieniu usługa Azure AD STS aktualizuje buforowane sesje zdalne jako "zatwierdzone" wraz z kodem autoryzacji.
  1. Na koniec strona sondowania na urządzeniu użytkownika z systemem HoloLens 2 otrzymuje odpowiedź "Autoryzowane" z usługi Azure AD i kontynuuje walidację kodu użytkownika, skojarzonego z nim przechowywanego kodu autoryzacji i generuje tokeny OAuth zgodnie z żądaniem ukończenia konfiguracji urządzenia. Utworzony token uwierzytelniania jest ważny przez 1 godzinę, a token odświeżania ma okres istnienia 90 dni.

Algorytmy generowania kodu i szyfrowania używane w tym przepływie są zgodne ze standardem FIPS. HoloLens 2 urządzenia korzystają z modułu TPM do zabezpieczania kluczy urządzeń i szyfrowania tokenów wygenerowanych po uwierzytelnieniu użytkownika przy użyciu kluczy chronionych sprzętowo. Więcej informacji na temat zabezpieczeń tokenów HoloLens 2 znajduje się w tece Co to jest [podstawowy token odświeżania (PRT).](/azure/active-directory/devices/concept-primary-refresh-token)

## <a name="device-sign-in-with-windows-hello"></a>Logowanie urządzenia przy użyciu Windows Hello

[Windows Hello](/windows/security/identity-protection/hello-for-business/hello-identity-verification) oferuje opcje bez hasła wbudowane bezpośrednio w system operacyjny, które pozwalają użytkownikom logować się do urządzenia przy użyciu irysów lub numeru PIN. Numer PIN jest zawsze dostępny jako poświadczenie i jest wymagany do konfiguracji urządzenia, natomiast irys jest opcjonalny i można go pominąć. Użytkownicy mogą logować się do urządzeń HoloLens przy użyciu osobistego konto Microsoft lub Azure Active Directory konta służbowego bez [wprowadzania hasła.  ](/azure/active-directory/authentication/concept-authentication-passwordless) Takie opcje zapewniają użytkownikom szybki, bezpieczny dostęp do pełnego Windows, aplikacji, danych, witryn internetowych i usług. Strategia firmy Microsoft mająca na celu środowisko bez hasła jest tutaj szczegółowo opisywna.

Utworzenie poświadczeń Windows Hello powoduje ustanowienie zaufanej relacji z dostawcą tożsamości i utworzenie asymetrycznej pary kluczy do uwierzytelniania. Gest Windows Hello (taki jak irys lub numer PIN) zapewnia entropię do odszyfrowywania klucza prywatnego z mikroukładu Trusted Platform Module (TPM) urządzenia. Ten klucz prywatny jest następnie używany do podpisywania żądań wysyłanych do serwera uwierzytelniania, a po pomyślnym uwierzytelnieniu użytkownik uzyskuje dostęp do poczty e-mail, zdjęć i innych ustawień konta.

Aby uzyskać więcej informacji, zobacz następującą infografikę:

  ![Windows Hello Zaloguj się.](images/security-hello-sign-in.png)
  
Na ilustracji przedstawionej powyżej należy zauważyć, że element nonce oznacza "liczba raz" i jest liczbą losową lub częściowo losową wygenerowaną. Po Windows Hello biometrycznego lub numeru PIN nigdy nie opuszcza urządzenia, na którym zostało aprowowane. Nawet jeśli numer PIN użytkownika Windows Hello skradziony, na przykład w ramach ataku wyłudzania informacji, jest on bezużyteczny bez [fizycznego urządzenia użytkownika.](/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password)

Aby zapewnić dodatkowe zabezpieczenia, poświadczenia usługi Windows Hello są chronione przez moduł Trusted Platform Module (TPM), aby zapewnić, że poświadczenia będą odporne na naruszenia i uzupełnione o zabezpieczenia przed wieloma nieprawidłowymi wpisami i ochronę przed złośliwym oprogramowaniem w celu uniknięcia zagrożenia. Aby uzyskać więcej informacji na Sign-On single Sign-On (SSO), przeczytaj to [omówienie metod logowania jednokrotnego.](/azure/active-directory/manage-apps/what-is-single-sign-on)

Uwierzytelnianie irysów powraca do numeru PIN. Aby skonfigurować nowy numer PIN (silny wystawca uwierzytelnienia) na urządzeniu, użytkownik musi niedawno przejść przez uwierzytelnianie wieloskładnikowe [(MFA)](/azure/active-directory/authentication/concept-mfa-howitworks) w celu ukończenia procesu.

## <a name="single-sign-on-with-web-account-manager"></a>Logowanie się za pomocą Menedżer kont internetowych

Logowanie jednokrotne umożliwia użytkownikom bez hasła logowanie się do urządzenia przy użyciu osobistego konta użytkownika lub jego konta służbowego. Użytkownik jest automatycznie autoryzowany za pomocą logowania jednokrotnego we wszystkich zintegrowanych aplikacjach i usługach za pośrednictwem [Menedżer kont internetowych API.](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)

Po dodaniu tożsamości za pośrednictwem jednej aplikacji może ona, za zgodą użytkownika, stać się dostępna dla wszystkich aplikacji i usług przy użyciu integracji na poziomie systemu. Znacznie zmniejsza to obciążenie związane z logowaniem do aplikacji i zapewnia użytkownikom bezproblemowe środowisko obsługi tożsamości.

Aby uzyskać więcej informacji na temat implementowania Menedżer kont internetowych API, przejdź do [tematu Implementing Menedżer kont internetowych APIs (Implementowanie interfejsów API Menedżer kont internetowych).](/windows/uwp/security/web-account-manager)

  ![interfejs API Zabezpieczenia.](images/security-api-img.png)
  
W przypadku pakietów aplikacji o specjalistycznych wymaganiach dotyczących uwierzytelniania Menedżer kont internetowych (CI) można rozszerzać na niestandardowych dostawców tożsamości. Użytkownicy mogą pobrać niestandardowego dostawcę tożsamości spakowanego jako aplikacja platformy uniwersalnej Windows Platform (UWP) z usługi Microsoft Store, aby włączyć logowanie jednokrotne w innych aplikacjach zintegrowanych z tym dostawcą tożsamości.

Aby uzyskać więcej informacji na temat implementowania niestandardowych dostawców tożsamości CI, zobacz Dokumentacja interfejsu [API niestandardowego dostawcy tożsamości DLA](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true).

## <a name="windows-hello-and-fido2-sign-in-with-webauthn"></a>Windows Hello i FIDO2 przy użyciu protokołu WebAuthn

HoloLens 2 można używać poświadczeń użytkownika bez hasła (takich jak klucze zabezpieczeń Windows Hello lub FIDO2) do bezpiecznego logowania się w Internecie za pośrednictwem usługi Microsoft Edge i witryn internetowych, które obsługują webAuthn. Standard FIDO2 umożliwia poświadczeniom użytkownika korzystanie z urządzeń opartych na standardach w celu uwierzytelniania Usługi online.

> [!Note]
> Specyfikacje [WebAuthn](https://www.w3.org/TR/webauthn/) i FIDO2 [CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html) są implementowane w usługach. Podpisane metadane określone przez webauthn i FIDO2 zawierają informacje — na przykład informacje o tym, czy użytkownik był obecny — i weryfikują uwierzytelnianie za pomocą gestu lokalnego.

Podobnie jak Windows Hello, gdy użytkownik tworzy i rejestruje poświadczenia FIDO2, urządzenie (klucz zabezpieczeń HoloLens 2 lub FIDO2) generuje na urządzeniu klucz prywatny i publiczny. Klucz prywatny jest bezpiecznie przechowywany na urządzeniu i można go używać tylko po odblokowaniu przy użyciu lokalnego gestu, takiego jak biometria lub numer PIN. Gdy klucz prywatny jest przechowywany, klucz publiczny jest wysyłany do systemu konto Microsoft w chmurze i rejestrowany przy użyciu skojarzonego konta użytkownika.

Po zalogowaniu się przy użyciu konta MSA i konta usługi Azure AD system wysyła wygenerowany numer lub zmienną danych do urządzenia HoloLens 2 lub FIDO2. Urządzenie HoloLens 2 lub używa klucza prywatnego do podpisania identyfikacji. Podpisana identyfikacja i metadane są wysyłane z powrotem do konto Microsoft i weryfikowane przy użyciu klucza publicznego.

Windows Hello i FIDO2 implementują poświadczenia na podstawie urządzenia HoloLens, w szczególności wbudowanej Trusted Platform Module bezpiecznej enklawy. Enklawa modułu TPM przechowuje klucz prywatny i wymaga klucza biometrycznego lub numeru PIN, aby go odblokować. Podobnie klucz zabezpieczeń FIDO2 to małe urządzenie zewnętrzne z wbudowaną bezpieczną enklawą, która przechowuje klucz prywatny i wymaga użycia biometrii lub numeru PIN do jego odblokowania.

Obie opcje oferują uwierzytelnianie dwuskładnikowe w jednym kroku, co wymaga pomyślnego zalogowania zarówno zarejestrowanego urządzenia, jak i numeru PIN lub biometrycznego. Aby uzyskać więcej informacji, zobacz ilustrację i proces silnego uwierzytelniania za pomocą klucza zabezpieczeń FIDO2.

### <a name="strong-authentication-with-fido2-security-key"></a>Silne uwierzytelnianie za pomocą klucza zabezpieczeń FIDO2

  ![FIDO img.](images/security-fido2-whfb-smaller.png)

1. Użytkownik podłącza klucz zabezpieczeń FIDO2 do HoloLens 2
1. Windows wykrywa klucz zabezpieczeń FIDO2
1. HoloLens wysyła żądanie uwierzytelnienia
1. Usługa Azure AD wysyła z powrotem nonce
1. Użytkownik kończy gest odblokowania magazynów kluczy prywatnych w bezpiecznej enklawie klucza zabezpieczeń
1. Klucz zabezpieczeń FIDO2 podpisuje element nonce za pomocą klucza prywatnego
1. Żądanie tokenu PRT ze podpisanym nonce jest wysyłane do usługi Azure AD
1. Usługa Azure AD weryfikuje klucz FIDO
1. Usługa Azure AD zwraca prt i TGT, aby umożliwić dostęp do zasobów

Usługi MSA i Azure AD są jednymi z pierwszych baz danych, które obsługują uwierzytelnianie bez hasła dzięki implementacji protokołu WebAuthn.

Aby uzyskać więcej informacji na temat używania protokołu WebAuthn z aplikacjami i/lub zestawami SDK, przejdź do tematu [WebAuthn APIs for password-less authentication on Windows 10](/windows/security/identity-protection/hello-for-business/webauthnapis)(Interfejsy API usługi WebAuthn służące do uwierzytelniania bez hasła w Windows 10 .

HoloLens 2 obsługuje urządzenia zabezpieczeń FIDO2, które są implementowane w celu specyfikacji i spełnienia wymagań wymienionych na Azure Active Directory logowania bez hasła — klucze zabezpieczeń [FIDO2](/azure/active-directory/authentication/concept-authentication-passwordless#fido2-security-keys) powinny być obsługiwane.

## <a name="local-accounts"></a>Konta lokalne

Dla wdrożeń w trybie offline można skonfigurować jedno konto lokalne. Konta lokalne nie są domyślnie włączone i należy je skonfigurować podczas aprowizowania urządzeń. Muszą oni zalogować się przy użyciu hasła i nie obsługują alternatywnych metod uwierzytelniania (takich jak [Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-overview) lub [Windows Hello).](/windows-hardware/design/device-experiences/windows-hello)

Więcej szczegółów na HoloLens kont użytkowników można znaleźć na stronie [HoloLens Identity](hololens-identity.md).

Administratorzy IT dostosowują, czy użytkownik może używać konta MSA do uwierzytelniania połączeń i usług niezwiązanych z pocztą e-mail za pośrednictwem [programu AllowMicrosoftAccountConnection.](/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection) Aby uzyskać informacje na temat zasad konfiguracji haseł, zasad nienadmiernych i zasad ekranu blokady, zobacz [Temat Device Lock .](/windows/client-management/mdm/policy-csp-devicelock)
