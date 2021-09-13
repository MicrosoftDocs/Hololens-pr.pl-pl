---
title: Jak ładować bezpośrednio i instalować aplikacje za pośrednictwem HoloLens 2 Instalator aplikacji
description: Dowiedz się, jak instalować aplikacje i rozwiązywać problemy z aplikacjami za pomocą instalatora aplikacji oraz ładować bezpośrednio i instalować aplikacje za pomocą interfejsu użytkownika.
keywords: zarządzanie aplikacją, aplikacja, hololens, instalator aplikacji
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 071dfb3b211928c561fc84754dd7ed4d64886f61
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/13/2021
ms.locfileid: "126033073"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a>Instalowanie aplikacji na HoloLens 2 za pośrednictwem Instalator aplikacji

> [!NOTE]
> Ta funkcja została dostępna na Windows Holographic w wersji [20H2 – aktualizacja z grudnia 2020 r.](hololens-release-notes.md). Upewnij się, że urządzenie [zostało zaktualizowane do](hololens-update-hololens.md) korzystania z tej funkcji.

Dodaliśmy **nową funkcję (Instalator aplikacji),** aby umożliwić bezproblemowe instalowanie aplikacji na urządzeniach z HoloLens 2. Ta funkcja będzie domyślnie **włączona dla urządzeń nieza pomocą programu**. Aby zapobiec zakłóceniom pracy przedsiębiorstw, instalator aplikacji nie **będzie w** tej chwili dostępny dla zarządzanych urządzeń.  

Urządzenie jest uznawane za "zarządzane", **jeśli** spełnione są dowolne z następujących czynności:

- Zarejestrowane w usłudze ZARZĄDZANIA [urządzeniami przenośnymi](hololens-enroll-mdm.md)
- Skonfigurowano przy użyciu [pakietu aprowizowania](hololens-provisioning.md)
- Tożsamość [użytkownika to](hololens-identity.md) usługa Azure AD

Teraz możesz instalować aplikacje bez konieczności włączania trybu dewelopera ani korzystania z Portal urządzeń.  Pobierz (za pośrednictwem portu USB lub za pośrednictwem Microsoft Edge) pakiet Appx na urządzenie i przejdź do pakietu Appx w Eksplorator plików, aby zostać poproszony o rozpoczynanie instalacji.  Alternatywnie [zainicjuj instalację ze strony internetowej](/windows/msix/app-installer/installing-windows10-apps-web). Podobnie jak aplikacje, które instalujesz z usługi Microsoft Store lub ładować bezpośrednio przy użyciu funkcji wdrażania [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) aplikacji LOB [](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) rozwiązania MDM, aplikacje muszą być podpisane cyfrowo przy użyciu narzędzia podpisywania, a certyfikat używany do podpisywania musi być zaufany przez urządzenie HoloLens, zanim będzie można wdrożyć aplikację.

## <a name="requirements"></a>Wymagania

### <a name="for-your-devices"></a>Dla urządzeń:

Ta funkcja jest obecnie dostępna w kompilacjach Windows Holographic 20H2 dla HoloLens 2. Upewnij się, że wszystkie urządzenia korzystające z tej metody zostały [zaktualizowane.](hololens-update-hololens.md)

### <a name="for-your-apps"></a>Dla aplikacji:

Konfiguracja rozwiązania aplikacji musi mieć wersję **master** lub **wydanie,** ponieważ Instalator aplikacji będzie używać zależności ze sklepu. Zobacz więcej na [temat tworzenia pakietów aplikacji.](/windows/msix/app-installer/create-appinstallerfile-vs)

Aplikacje instalowane za pomocą tej metody muszą być podpisane cyfrowo. Do podpisania aplikacji będzie konieczne użycie certyfikatu. Certyfikat można pobrać z listy zaufanych urzędu certyfikacji firmy [MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT). W takim przypadku nie trzeba będzie podjąć żadnych dodatkowych działań. Możesz też podpisać własny certyfikat, jednak ten certyfikat będzie musiał zostać wypchnięty na urządzenie.

- Jak podpisywać aplikacje [przy użyciu narzędzia do podpisywania.](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Opcje certyfikatów:**

- [Lista zaufanych urzędu certyfikacji MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Wybierz metodę wdrażania certyfikatu.**

- [Pakiety aprowizowania](hololens-provisioning.md) można stosować do urządzeń lokalnych.
- Rozwiązanie MDM może służyć do [stosowania certyfikatów z konfiguracjami urządzeń.](/mem/intune/protect/certificates-configure)
- Użyj menedżera certyfikatów [na urządzeniu](certificate-manager.md).

## <a name="installation-method"></a>Metoda instalacji

1. Sprawdź, czy urządzenie nie jest uznawane za zarządzane.
1. Sprawdź, czy urządzenie HoloLens 2 jest włączone i że użytkownik jest zalogowany.
1. Na komputerze przejdź do aplikacji niestandardowej i skopiuj plik yourapp.appxbundle do katalogu yourdevicename\Internal Storage\Downloads.
    Po zakończeniu kopiowania pliku możesz rozłączyć urządzenie i zakończyć instalację później.
1. Na urządzeniu HoloLens 2 Otwórz **menu Start**, wybierz pozycję **Wszystkie aplikacje** i uruchom **Eksplorator plików** aplikację.
1. Przejdź do folderu Pobrane. W lewym panelu aplikacji może być konieczne wybranie najpierw opcji **To urządzenie,** a następnie przejście do sekcji Pliki do pobrania.
1. Wybierz plik yourapp.appxbundle.
1. Zostanie Instalator aplikacji. Wybierz przycisk **Zainstaluj,** aby zainstalować aplikację.

Zainstalowana aplikacja zostanie automatycznie uruchamiana po zakończeniu instalacji.

![Instalowanie przykładów mrTK za pośrednictwem Instalator aplikacji.](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a>Rozwiązywanie problemów z instalacjami

Jeśli instalacja aplikacji nie powiodła się, sprawdź następujące kwestie, aby rozwiązać problem:

- Twoja aplikacja jest kompilacją master lub kompilacją wydania.
- Urządzenie zostanie zaktualizowane do kompilacji, na której ta funkcja jest dostępna.
- Masz połączenie [z Internetem.](hololens-network.md)
- Punkty [końcowe dla Microsoft Store](hololens-offline.md) są poprawnie skonfigurowane.  

## <a name="web-installer"></a>Instalator sieci Web

Użytkownicy mogą instalować aplikację bezpośrednio z serwera internetowego. Ten przepływ korzysta z Instalator aplikacji w połączeniu z łatwą metodą pobierania i instalowania dystrybucji.

### <a name="how-to-set-up-web-install"></a>Jak skonfigurować instalację internetową:

1. Upewnij się, że aplikacja jest poprawnie skonfigurowana do instalacji.
1. Wykonaj następujące [kroki, aby włączyć instalację ze strony internetowej](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).

### <a name="end-user-experience"></a>Środowisko użytkownika końcowego:

1. Użytkownik odbiera i instaluje certyfikat na urządzeniu przy użyciu metody wybranej wcześniej.
1. Użytkownik odwiedzi adres URL utworzony w powyższym kroku.

Aplikacja zostanie teraz instalowana na urządzeniu. Aby znaleźć aplikację, otwórz menu Start **i** wybierz  przycisk Wszystkie aplikacje, aby znaleźć aplikację.

- Aby uzyskać więcej pomocy dotyczącej rozwiązywania problemów z metodą instalacji instalatora aplikacji, odwiedź [stronę rozwiązywanie problemów z instalatorem aplikacji.](/windows/msix/app-installer/troubleshoot-appinstaller-issues)

> [!NOTE]
> Interfejs użytkownika podczas procesu aktualizacji nie jest obsługiwany. Dlatego opcja ShowPrompt na [tej stronie](/windows/msix/app-installer/update-settings) i powiązane opcje nie są obsługiwane.

## <a name="sample-apps"></a>Przykładowe aplikacje

Wypróbuj te Instalator aplikacji jedną z naszych dostępnych przykładowych aplikacji. 
> [!div class="nextstepaction"]
> [Przykładowe aplikacje](/windows/mixed-reality/develop/features-and-samples)
