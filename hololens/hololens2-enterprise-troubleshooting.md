---
title: Rozwiązywanie problemów z implementacją urządzenia HoloLens 2 i urządzeniem zarządzanym
description: Rozwiązywanie problemów z urządzeniami HoloLens 2 w środowisku przedsiębiorstwa
author: JoyJaz
ms.author: v-jjaswinski
ms.date: 6/22/2021
ms.topic: article
keywords: rozwiązywanie problemów
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 911e5b9494eae00ace8007ee6a29b30e6aaf98dd
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961640"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a>Rozwiązywanie problemów z implementacją i urządzeniami zarządzanymi 

W tym artykule opisano sposób rozwiązywania kilku problemów lub odpowiadania na pytania dotyczące implementacji urządzenia HoloLens 2 i zarządzania nim.

>[!IMPORTANT]
> Przed rozpoczęciem procedury rozwiązywania problemów upewnij się, że urządzenie jest obciążane od **20 do 40%** pojemności baterii, jeśli jest to możliwe. Wskaźniki [naładowania baterii znajdujące](hololens2-setup.md#lights-that-indicate-the-battery-level) się pod przyciskiem zasilania to szybki sposób na sprawdzenie pojemności baterii bez logowania się do urządzenia.


<a id="list"></a>
- [Rozwiązywanie problemów z protokołu EAP](#eap-troubleshooting)
- [Rozwiązywanie problemów z siecią Wi-Fi](#wi-fi-troubleshooting)
- [Rozwiązywanie problemów z siecią](#network-troubleshooting)
- [Nie można zalogować się do wcześniej skonfigurować urządzenia HoloLens](#cant-sign-in-to-a-previously-setup-hololens-device)
- [Nie można zalogować się po zaktualizowaniu do systemu Windows Holographic 21H1](#cant-login-after-updating-to-windows-holographic-21h1)
- [Rozwiązywanie problemów z rozwiązaniem Autopilot](#autopilot-troubleshooting)
- [Zarządzane urządzenia HoloLens : często zadawane pytania](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a>Rozwiązywanie problemów z protokołu EAP
1. Sprawdź, Wi-Fi profil ma odpowiednie ustawienia:
    - Typ protokołu EAP jest poprawnie skonfigurowany, typowe typy protokołu EAP: EAP-TLS (13), EAP-TTLS (21) i PEAP (25).
    - Wi-Fi nazwa SSID jest właściwa i pasuje do ciągu HEX.
    - W przypadku protokołu EAP-TLS wartość TrustedRootCA zawiera skrót SHA-1 zaufanego certyfikatu głównego urzędu certyfikacji serwera. Na komputerze z systemem Windows "certutil.exe -dump cert_file_name" polecenie spowoduje pokazanie ciągu skrótu SHA-1 certyfikatu.
2. Zbierz przechwytywanie pakietów sieciowych w dziennikach punktu dostępu, kontrolera lub serwera usługi AAA, aby dowiedzieć się, gdzie sesja protokołu EAP kończy się niepowodzeniem.
    - Jeśli tożsamość protokołu EAP dostarczana przez urządzenie HoloLens nie jest oczekiwana, sprawdź, czy tożsamość została poprawnie aprowizowana za pośrednictwem Wi-Fi lub certyfikatu klienta.
    - Jeśli serwer odrzuci certyfikat klienta urządzenia HoloLens, sprawdź, czy wymagany certyfikat klienta został zaaprowizowany na urządzeniu.
    - Jeśli urządzenie HoloLens odrzuci certyfikat serwera, sprawdź, czy certyfikat głównego urzędu certyfikacji serwera został aprowowany na urządzeniach HoloLens.
3. Jeśli profil przedsiębiorstwa jest aprowowany za pośrednictwem Wi-Fi aprowizowania, rozważ zastosowanie pakietu aprowizowania na Windows 10 PC. Jeśli na komputerze Windows 10 również nie powiedzie się, postępuj zgodnie z przewodnikiem rozwiązywania problemów z uwierzytelnianiem klienta systemu Windows 802.1X.
4. Prześlij nam opinię za pośrednictwem Centrum opinii.

[Powrót do listy](#list)

## <a name="wi-fi-troubleshooting"></a>Wi-Fi rozwiązywania problemów

Oto kilka rzeczy do wypróbowania, jeśli nie można połączyć urządzenia HoloLens z Wi-Fi siecią:

1. Upewnij się, Wi-Fi jest włączona. Aby to sprawdzić, użyj gestu Start, a następnie wybierz pozycję Ustawienia > Sieci & Internet > Wi-Fi. Jeśli Wi-Fi jest wł., spróbuj go wyłączyć, a następnie ponownie wł.
2. Umieść komputer bliżej routera lub punktu dostępu.
3. Uruchom ponownie router Wi-Fi, a następnie ponownie uruchom urządzenie HoloLens. Spróbuj ponownie nałączyć połączenie.
4. Jeśli żadna z tych czynności nie działa, upewnij się, że router korzysta z najnowszego oprogramowania układowego. Te informacje można znaleźć w witrynie internetowej producenta.

Po zalogowaniu się do konta przedsiębiorstwa lub organizacji na urządzeniu może również zostać stosowane zasady usługi Mobile Zarządzanie urządzeniami (MDM), jeśli zasady zostały skonfigurowane przez administratora IT.

## <a name="network-troubleshooting"></a>Rozwiązywanie problemów z siecią
Jeśli problemy z siecią są przeszkodą dla pomyślnego wdrożenia i używania urządzenia HoloLens 2 w organizacji, dowiedz się, w jaki sposób dwa dobrze znane narzędzia diagnostyczne sieci — Fiddler i Wireshark — mogą pomóc w skanowaniu, diagnozowaniu i identyfikowaniu problemów. Aby uzyskać więcej [informacji, zapoznaj](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) się z tym blogiem.

[Powrót do listy](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>Nie można zalogować się do wcześniej skonfigurować urządzenia HoloLens

Jeśli urządzenie zostało wcześniej ustawione dla kogoś innego , dla klienta lub dla byłego pracownika i nie masz hasła do [](https://docs.microsoft.com/intune/remote-actions/devices-wipe) odblokowania urządzenia, możesz użyć usługi Intune do zdalnego wyczyszczenia urządzenia. Następnie urządzenie zostanie ponownie flashe.  
> [!IMPORTANT]
> Podczas czyszczenia urządzenia upewnij się, że pole Zachowaj stan rejestracji i **konto użytkownika nie** jest zaznaczone.
[Powrót do listy](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a>Nie można zalogować się po zaktualizowaniu do systemu Windows Holographic 21H1

### <a name="symptoms"></a>Objawy
- Logowanie przy użyciu numeru PIN nie powiedzie się po wprowadzeniu poprawnego numeru PIN.
- Użycie metody logowania do sieci Web zakończy się niepowodzeniem po pomyślnym zalogowaniu się na stronie internetowej.
- Urządzenie nie jest wyświetlane jako "Azure AD joined" w Azure Portal [-> Azure Active Directory](https://portal.azure.com/) -> Devices.

### <a name="cause"></a>Przyczyna
Urządzenie, na które ma to wpływ, zostało usunięte z dzierżawy usługi Azure AD. Na przykład może się to zdarzyć, ponieważ:

- Administrator lub użytkownik usunął urządzenie w Azure Portal lub przy użyciu programu PowerShell.
- Urządzenie zostało usunięte z dzierżawy usługi Azure AD z powodu braku aktywności. W przypadku wydajnie zarządzanego środowiska zwykle zalecamy administratorom IT usunięcie nieaktywnych, nieaktywnych urządzeń [ze swojej dzierżawy usługi Azure AD.](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices)

Gdy urządzenie, na które ma to wpływ, spróbuje ponownie skontaktować się z dzierżawą usługi Azure AD po jej usunięciu, uwierzytelnianie w usłudze Azure AD nie powiedzie się. Ten efekt jest często niewidoczny dla użytkownika urządzenia, ponieważ logowanie z pamięci podręcznej przy użyciu numeru PIN będzie nadal zezwalać użytkownikowi na logowanie.

### <a name="mitigation"></a>Ograniczanie ryzyka
Obecnie nie ma możliwości dodania usuniętego urządzenia HoloLens z powrotem do usługi Azure AD. Należy wyczyścić reflashed urządzeń, zgodnie z instrukcjami [dotyczącymi reflashing ich urządzenia.](hololens-recovery.md#clean-reflash-the-device)

## <a name="autopilot-troubleshooting"></a>Rozwiązywanie problemów z rozwiązaniem Autopilot

Następujące artykuły mogą być przydatnym zasobem, aby dowiedzieć się więcej i rozwiązać problemy z rozwiązaniem Autopilot, jednak należy pamiętać, że te artykuły są oparte na programie Windows 10 Desktop i nie wszystkie informacje mogą dotyczyć urządzenia HoloLens:

- [Windows Autopilot — znane problemy](https://docs.microsoft.com/mem/autopilot/known-issues)
- [Rozwiązywanie problemów dotyczących rejestrowania urządzeń z systemem Windows w usłudze Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot — konflikty zasad](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a>Zarządzane urządzenia HoloLens : często zadawane pytania

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>Czy mogę używać System Center Menedżer konfiguracji (SCCM) do zarządzania urządzeniami HoloLens?

Nie. Do zarządzania urządzeniami HoloLens należy użyć systemu MDM.

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>Czy mogę używać Active Directory Domain Services (AD DS) do zarządzania kontami użytkowników urządzenia HoloLens?

Nie. Aby zarządzać kontami użytkowników urządzeń HoloLens, musisz użyć usługi Azure Active Directory (Azure AD).

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>Czy urządzenie HoloLens jest w stanie automatycznie ująć w rejestrację zautomatyzowane systemy przechwytywania danych (ADCS)?

Nie.

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>Czy urządzenie HoloLens może uczestniczyć w Integrated Windows Authentication?

Nie.

### <a name="does-hololens-support-branding"></a>Czy urządzenie HoloLens obsługuje znakowanie?

Nie. Ten problem można jednak ominić przy użyciu jednej z następujących metod:

- Utwórz aplikację niestandardową, a następnie włącz [tryb kiosku.](hololens-kiosk.md) Aplikacja niestandardowa może mieć znakowanie i może uruchamiać inne aplikacje (takie jak Remote Assist).  
- Zmień wszystkie obrazy profilu użytkownika w usłudze Azure AD na logo firmy. Jednak może to nie być pożądane we wszystkich scenariuszach.

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>Jakie możliwości rejestrowania oferuje urządzenie HoloLens 2?

Rejestrowanie jest ograniczone do śladów, które mogą być przechwytywane w scenariuszach tworzenia lub rozwiązywania problemów, lub danych telemetrycznych, które urządzenia wysyłają do serwerów firmy Microsoft.

## <a name="questions-about-securing-hololens-devices"></a>Pytania dotyczące zabezpieczania urządzeń HoloLens

Zobacz [nasze informacje o zabezpieczeniach urządzenia HoloLens 2.](security-overview.md)
W przypadku urządzeń HoloLens 1. generacji zapoznaj się z często [zadawanymi pytaniami.](hololens1-faq-security.md)

[Powrót do listy](#list)
