---
title: HoloLens 2 i rozwiązywanie problemów z urządzeniami zarządzanymi
description: Rozwiązywanie problemów HoloLens 2 urządzeń w Enterprise środowisku
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
ms.openlocfilehash: 9f3950de51e4bfa2a76431a2a070d87aa81ed443
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636881"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a>Rozwiązywanie problemów z implementacją i urządzeniami zarządzanymi 

W tym artykule opisano sposób rozwiązywania kilku problemów lub odpowiadania na pytania dotyczące implementacji i zarządzania HoloLens 2.

>[!IMPORTANT]
> Przed rozpoczęciem procedury rozwiązywania problemów upewnij się, że urządzenie jest obciążane od **20 do 40%** pojemności baterii, jeśli jest to możliwe. Wskaźniki [naładowania baterii znajdujące](hololens2-setup.md#lights-that-indicate-the-battery-level) się pod przyciskiem zasilania to szybki sposób na sprawdzenie pojemności baterii bez logowania się do urządzenia.


<a id="list"></a>
- [Rozwiązywanie problemów z protokołu EAP](#eap-troubleshooting)
- [Rozwiązywanie problemów z siecią Wi-Fi](#wi-fi-troubleshooting)
- [Rozwiązywanie problemów z siecią](#network-troubleshooting)
- [Nie można zalogować się do wcześniej HoloLens urządzenia](#cant-sign-in-to-a-previously-setup-hololens-device)
- [Nie można zalogować się po aktualizacji do Windows Holographic 21H1](#cant-login-after-updating-to-windows-holographic-21h1)
- [Rozwiązywanie problemów z rozwiązaniem Autopilot](#autopilot-troubleshooting)
- [Często zadawane pytania HoloLens urządzeń zarządzanych](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a>Rozwiązywanie problemów z protokołu EAP
1. Sprawdź, Wi-Fi profil ma odpowiednie ustawienia:
    - Typ protokołu EAP jest poprawnie skonfigurowany, typowe typy protokołu EAP: EAP-TLS (13), EAP-TTLS (21) i PEAP (25).
    - Wi-Fi SSID jest właściwa i pasuje do ciągu HEX.
    - W przypadku protokołu EAP-TLS wartość TrustedRootCA zawiera skrót SHA-1 certyfikatu zaufanego głównego urzędu certyfikacji serwera. Na Windows pc "certutil.exe -dump cert_file_name" będzie wyświetlać ciąg skrótu SHA-1 certyfikatu.
2. Zbierz przechwytywanie pakietów sieciowych w dziennikach punktu dostępu, kontrolera lub serwera usługi AAA, aby dowiedzieć się, gdzie sesja protokołu EAP kończy się niepowodzeniem.
    - Jeśli tożsamość EAP dostarczana przez HoloLens jest oczekiwana, sprawdź, czy tożsamość została poprawnie aprowizowana za pośrednictwem profilu Wi-Fi certyfikatu klienta.
    - Jeśli serwer odrzuci HoloLens klienta, sprawdź, czy wymagany certyfikat klienta został aprowowany na urządzeniu.
    - Jeśli HoloLens certyfikat serwera, sprawdź, czy certyfikat głównego urzędu certyfikacji serwera został aprowowany na HoloLens.
3. Jeśli profil przedsiębiorstwa jest aprowowany za pośrednictwem Wi-Fi aprowizowania, rozważ zastosowanie pakietu aprowizowania na komputerze Windows 10 PC. Jeśli na komputerze nie powiedzie się Windows 10, postępuj zgodnie z Windows rozwiązywania problemów z uwierzytelnianiem klienta 802.1X.
4. Prześlij nam opinię za pośrednictwem Centrum opinii.

[Powrót do listy](#list)

## <a name="wi-fi-troubleshooting"></a>Wi-Fi rozwiązywania problemów

Oto kilka rzeczy, które należy wypróbować, jeśli nie można połączyć HoloLens z Wi-Fi siecią:

1. Upewnij się, Wi-Fi jest włączona. Aby to sprawdzić, użyj gestu Uruchom, a następnie wybierz pozycję Ustawienia > Network & Internet > Wi-Fi. Jeśli Wi-Fi jest wł., spróbuj go wyłączyć, a następnie ponownie wł.
2. Umieść komputer bliżej routera lub punktu dostępu.
3. Uruchom ponownie Wi-Fi, a następnie uruchom ponownie HoloLens. Spróbuj ponownie nałączyć połączenie.
4. Jeśli żadna z tych czynności nie działa, upewnij się, że router korzysta z najnowszego oprogramowania układowego. Te informacje można znaleźć w witrynie internetowej producenta.

Po zalogowaniu się do konta przedsiębiorstwa lub organizacji na urządzeniu może również zostać stosowane zasady usługi Mobile Zarządzanie urządzeniami (MDM), jeśli zasady zostały skonfigurowane przez administratora IT.

[Powrót do listy](#list)

## <a name="network-troubleshooting"></a>Rozwiązywanie problemów z siecią
Jeśli problemy z siecią są przeszkodą dla pomyślnego wdrożenia i używania programu HoloLens 2 w organizacji, skonfiguruj program Fiddler i/lub Wireshark, aby przechwytywać i analizować ruch HTTP/HTTPS. 

### <a name="configure-fiddler-to-capture-http-traffic"></a>Konfigurowanie programu Fiddler do przechwytywania ruchu HTTP
Program Fiddler to internetowy serwer proxy debugowania, który służy do rozwiązywania problemów z protokołu HTTP(S). Przechwytuje każde żądanie HTTP, które komputer wykonuje, i rejestruje wszystkie skojarzone z nim dane. Odkrywanie problemów z uwierzytelnianiem użytkowników końcowych dla aplikacji HTTPS zwiększa produktywność i wydajność dla docelowych HoloLens 2 przypadków użycia. 

#### <a name="prerequisites"></a>Wymagania wstępne
 
- HoloLens 2 i komputer musi znajdować się w tej samej sieci
- Zanotuj adres IP komputera

#### <a name="install-and-configure-fiddler"></a>Instalowanie i konfigurowanie programu Fiddler

1. Na komputerze — zainstaluj [i](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) uruchom program Fiddler.  
1. Na komputerze — skonfiguruj program Fiddler tak, aby zezwalał komputerom zdalnym na nawiązywanie połączenia.
    1. Przejdź do fiddler Ustawienia -> Connections
    1. Zwróć uwagę na port nasłuchiwania dla programu Fiddler (wartość domyślna to 8866)
    1. Zaznacz pole wyboru Zezwalaj komputerom zdalnym na nawiązywanie połączeń
    1. Klikanie pozycji Zapisz.
3. Na komputerze HoloLens 2 — skonfiguruj program Fiddler jako serwer proxy<sup>1:</sup>
    1. Otwórz okno menu Start i wybierz pozycję Ustawienia
    1. Wybierz pozycję Sieć & Internet, a następnie pozycję Serwer proxy w menu po lewej stronie
    1. Przewiń w dół do ręcznej konfiguracji serwera proxy i przełącz ustawienie Użyj serwera proxy na Wł.
    1. Wprowadź adres IP komputera, na którym zainstalowano program Fiddler
    1. Wprowadź numer portu zanotowyny powyżej (wartość domyślna to 8866)
    1. Klikanie pozycji Zapisz.

<sup>1</sup> W przypadku kompilacji 20279.1006+ (niejawni testerzy i nadchodzące wydanie) użyj następujących kroków, aby skonfigurować serwer proxy:
1. Otwórz menu Start i przejdź do strony właściwości Wi-Fi sieci wirtualnej 
1. Przewiń w dół do serwera proxy
1. Zmiana na konfigurację ręczną
1. Wprowadź adres IP komputera, na którym zainstalowano program Fiddler
1. Wprowadź numer portu zanotowyny powyżej. (wartość domyślna to 8866)
1. Kliknij przycisk Zastosuj
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a>Odszyfrowywanie ruchu HTTPS z HoloLens 2

1. Na komputerze — wyeksportuj certyfikat fiddler.
    1. Przejdź do strony Fiddler Ustawienia -> HTTPS i rozwiń Ustawienia
    2. Kliknij pozycję Eksportuj certyfikat fiddler. Spowoduje to zapisanie na pulpicie
    3. Przenieś certyfikat do folderu Pobrane na komputerze HoloLens 2

2.  Na komputerze HoloLens 2 — zaimportuj certyfikat fiddler.
    1. Przejdź do Ustawienia -> Update i Security -> Certificates
    2. Kliknij pozycję Zainstaluj certyfikat, przejdź do folderu Pobrane i wybierz certyfikat programu Fiddler.
    3. Zmień lokalizację magazynu na Komputer lokalny
    4. Zmienianie magazynu certyfikatów na główny
    5. Wybierz pozycję Zainstaluj
    6. Upewnij się, że certyfikat jest pokazywany na liście certyfikatów. Jeśli nie, powtórz powyższe kroki

#### <a name="inspect-https-sessions"></a>Inspekcja sesji HTTP(S)

Na komputerze program Fiddler będzie wyświetlać HoloLens http(S) na żywo w wersji 2. Panel Inspektorzy w programie Fiddler może wyświetlać żądania/odpowiedzi HTTP(S) w różnych widokach — na przykład widok "Nieprzetworzone" wyświetla nieprzetworzone żądanie lub odpowiedź w postaci zwykłego tekstu. 

### <a name="configure-wireshark-to-capture-network-traffic"></a>Konfigurowanie aplikacji Wireshark do przechwytywania ruchu sieciowego
Wireshark to analizator protokołu sieciowego, który służy do sprawdzania ruchu TCP/UDP z i do urządzeń HoloLens 2. Dzięki temu można łatwo określić, jaki ruch jest przekraczany przez sieć do sieci HoloLens 2, jaka jest jej część, jak często występuje opóźnienie między określonymi przeskokami itd.

#### <a name="prerequisites"></a>Wymagania wstępne:
- Komputer musi mieć dostęp do Internetu i obsługiwać udostępnianie Internetu za pośrednictwem Wi-Fi

#### <a name="install-and-configure-wireshark"></a>Instalowanie i konfigurowanie programu Wireshark
1. Na komputerze — zainstaluj program [Wireshark](https://www.wireshark.org/#download) 
1. Na komputerze — włącz opcję Mobilny hotspot, aby udostępnić połączenie internetowe z sieci Wi-Fi.
1. Na komputerze — uruchom program Wireshark i przechwyć ruch z interfejsu mobilnego hotspotu. 
1. Na komputerze HoloLens 2 — zmień sieć Wi-Fi na hotspot mobilny komputera. HoloLens 2 ruch IP będzie pokazywany w programie Wireshark.

#### <a name="analyze-wireshark-logs"></a>Analizowanie dzienników wireshark
Filtry Wireshark mogą pomóc w odfiltrowyniu pakietów zainteresowania. 

Zapoznaj się z oryginalnym [blogiem](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458).

[Powrót do listy](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>Nie można zalogować się do wcześniej HoloLens urządzenia

Jeśli urządzenie zostało wcześniej ustawione dla kogoś innego , dla klienta lub dla byłego pracownika i nie masz hasła do [](/intune/remote-actions/devices-wipe) odblokowania urządzenia, możesz użyć usługi Intune do zdalnego wyczyszczenia urządzenia. Następnie urządzenie zostanie ponownie flashe.  
> [!IMPORTANT]
> Podczas czyszczenia urządzenia upewnij się, że pole Zachowaj stan rejestracji i **konto użytkownika nie** jest zaznaczone.

[Powrót do listy](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a>Nie można zalogować się po aktualizacji do Windows Holographic 21H1

### <a name="symptoms"></a>Objawy
- Logowanie przy użyciu numeru PIN nie powiedzie się po wprowadzeniu poprawnego numeru PIN.
- Użycie metody logowania do sieci Web zakończy się niepowodzeniem po pomyślnym zalogowaniu się na stronie internetowej.
- Urządzenie nie jest wyświetlane jako "Azure AD joined" w Azure Portal [-> Azure Active Directory](https://portal.azure.com/) -> Devices.

### <a name="cause"></a>Przyczyna
Urządzenie, na które ma to wpływ, zostało usunięte z dzierżawy usługi Azure AD. Na przykład może się to zdarzyć, ponieważ:

- Administrator lub użytkownik usunął urządzenie w Azure Portal lub przy użyciu programu PowerShell.
- Urządzenie zostało usunięte z dzierżawy usługi Azure AD z powodu braku aktywności. W przypadku wydajnie zarządzanego środowiska zwykle zalecamy administratorom IT usunięcie nieaktywnych, nieaktywnych urządzeń [ze swojej dzierżawy usługi Azure AD.](/azure/active-directory/devices/manage-stale-devices)

Gdy urządzenie, na które ma to wpływ, spróbuje ponownie skontaktować się z dzierżawą usługi Azure AD po jej usunięciu, uwierzytelnianie w usłudze Azure AD nie powiedzie się. Ten efekt jest często niewidoczny dla użytkownika urządzenia, ponieważ logowanie z pamięci podręcznej przy użyciu numeru PIN będzie nadal zezwalać użytkownikowi na logowanie.

### <a name="mitigation"></a>Ograniczanie ryzyka
Obecnie nie ma możliwości dodania usuniętego urządzenia HoloLens z powrotem do usługi Azure AD. Należy wyczyścić reflashed urządzeń, zgodnie z instrukcjami [dotyczącymi reflashing ich urządzenia.](hololens-recovery.md#clean-reflash-the-device)

[Powrót do listy](#list)

## <a name="autopilot-troubleshooting"></a>Rozwiązywanie problemów z rozwiązaniem Autopilot

Następujące artykuły mogą być przydatnym zasobem, który pozwala uzyskać więcej informacji i rozwiązywać problemy z rozwiązaniem Autopilot, należy jednak pamiętać, że te artykuły są oparte na programie Windows 10 Desktop i nie wszystkie informacje mogą mieć zastosowanie do HoloLens:

- [Windows Autopilot — znane problemy](/mem/autopilot/known-issues)
- [Rozwiązywanie problemów dotyczących rejestrowania urządzeń z systemem Windows w usłudze Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot — konflikty zasad](/mem/autopilot/policy-conflicts)

[Powrót do listy](#list)

## <a name="managed-hololens-devices-faqs"></a>Często zadawane pytania HoloLens urządzeń zarządzanych

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>Czy mogę używać System Center Configuration Manager (SCCM) do zarządzania HoloLens urządzeniami?

Nie. Do zarządzania urządzeniami przenośnymi należy używać HoloLens MDM.

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>Czy mogę używać Active Directory Domain Services (AD DS) do zarządzania HoloLens kontami użytkowników?

Nie. Aby zarządzać kontami użytkowników Azure Active Directory (Azure AD), należy użyć usługi HoloLens urządzeń.

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>Czy HoloLens automatyczne rejestrowanie w systemach automatycznego przechwytywania danych (ADCS)?

Nie.

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>Czy HoloLens uczestniczyć w zintegrowanym Windows uwierzytelniania?

Nie.

### <a name="does-hololens-support-branding"></a>Czy HoloLens znakowanie?

Nie. Ten problem można jednak ominić przy użyciu jednej z następujących metod:

- Utwórz aplikację niestandardową, a następnie włącz [tryb kiosku.](hololens-kiosk.md) Aplikacja niestandardowa może mieć znakowanie i może uruchamiać inne aplikacje (takie jak Remote Assist).  
- Zmień wszystkie obrazy profilu użytkownika w usłudze Azure AD na logo firmy. Jednak może to nie być pożądane we wszystkich scenariuszach.

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>Jakie możliwości rejestrowania oferuje HoloLens 2?

Rejestrowanie jest ograniczone do śladów, które mogą być przechwytywane w scenariuszach tworzenia lub rozwiązywania problemów, lub danych telemetrycznych, które urządzenia wysyłają do serwerów firmy Microsoft.

## <a name="questions-about-securing-hololens-devices"></a>Pytania dotyczące zabezpieczania urządzeń HoloLens sieciowych

Zobacz [nasze HoloLens zabezpieczeń 2.](security-overview.md)
Aby HoloLens 1. generacji, zapoznaj się z często [zadawanymi pytaniami.](hololens1-faq-security.yml)

[Powrót do listy](#list)
