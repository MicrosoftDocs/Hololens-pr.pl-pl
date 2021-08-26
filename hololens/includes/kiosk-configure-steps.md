---
ms.openlocfilehash: 7a7122790d3e0257c07cdd8bc8c7f658b3a0e279
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859428"
---
# <a name="microsoft-intune-single-app-kiosk-template"></a>[Microsoft Intune szablonu kiosku z pojedynczą aplikacją](#tab/uisak)

## <a name="microsoft-intune-single-app-kiosk-template"></a>Microsoft Intune kiosku z pojedynczą aplikacją

1. Tworzenie profilu konfiguracji <br> 
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Wybieranie szablonu kiosku <br> 
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Wybierz, czy kiosk z pojedynczą aplikacją, czy wieloma aplikacjami, a także rodzaj użytkownika przeznaczonego dla trybu kiosku <br> 
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-sa-3.png"/>
</kbd>

<br>

4. Wybieranie aplikacji do uruchomienia w trybie kiosku <br> 
<kbd>
    <img alt="Choose the app" src="../images/kiosk-steps/kiosk-template-sa-4.png"/>
</kbd>

<br>

5. Pozostaw pozostałe opcje bez reszty <br> 
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Wybierz grupy/urządzenia lub użytkowników, do których ma zostać przypisany ten profil konfiguracji <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

7. Przeglądanie i tworzenie w celu zapisania profilu konfiguracji
8. Wykonaj synchronizację zarządzania urządzeniami przenośnymi, zaczynając od urządzenia lub usługi Intune, aby zastosować konfigurację do urządzenia. Synchronizowanie urządzeń z usługi [Intune](/mem/intune/remote-actions/device-sync#sync-a-device) lub na urządzeniu za pośrednictwem konta **usługi Ustawienia -> -> Work or school ->** wybierz połączone konto **-> Info -> Sync**
9. Zaloguj się jako użytkownik docelowy, aby doświadczyć kiosku.

# <a name="microsoft-intune-multi-app-kiosk-template"></a>[Microsoft Intune kiosku z wieloma aplikacjami](#tab/uimak)

## <a name="microsoft-intune-multi-app-kiosk-template"></a>Microsoft Intune szablonu kiosku z wieloma aplikacjami

1. Tworzenie profilu konfiguracji <br> 
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Wybieranie szablonu kiosku <br> 
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Wybierz, czy kiosk z pojedynczą aplikacją, czy wieloma aplikacjami, a także rodzaj użytkownika przeznaczonego dla trybu kiosku <br> 
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-mak-3.png"/>
</kbd>

<br>

4. Wybieranie aplikacji do uruchomienia w trybie kiosku <br> 
<kbd>
    <img alt="Choose the app(s)" src="../images/kiosk-steps/kiosk-template-mak-4.png"/>
</kbd>

<br>

5. Pozostaw pozostałe opcje bez reszty <br> 
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Wybierz grupy/urządzenia lub użytkowników, do których ma zostać przypisany ten profil konfiguracji <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

<br>

7. Przeglądanie i tworzenie w celu zapisania profilu konfiguracji
8. Wykonaj synchronizację zarządzania urządzeniami przenośnymi, zaczynając od urządzenia lub usługi Intune, aby zastosować konfigurację do urządzenia. Synchronizowanie urządzeń z usługi [Intune](/mem/intune/remote-actions/device-sync#sync-a-device) lub na urządzeniu za pośrednictwem konta **usługi Ustawienia -> -> Work or school ->** wybierz połączone konto **-> Info -> Sync**
9. Zaloguj się jako użytkownik docelowy, aby doświadczyć kiosku.

# <a name="microsoft-intune-custom-template"></a>[Microsoft Intune szablonu niestandardowego](#tab/intunecustom)

## <a name="microsoft-intune-custom-template"></a>Microsoft Intune szablon niestandardowy

1. Utwórz konfigurację XML dla żądanego typu kiosku. Aby [rozpocząć,](../hololens-kiosk-reference.md#kiosk-xml-code-samples) zobacz przykłady tutaj.

1. Tworzenie niestandardowego profilu konfiguracji <br>
<kbd>
    <img alt="Create a custom configuration profile" src="../images/kiosk-steps/kiosk-custom-1.png"/>
</kbd>

<br>

3. Określ nazwę niestandardowego profilu konfiguracji i kliknij pozycję "Dodaj" w sekcji "Ustawienia konfiguracji", aby dodać ustawienia OMA-URI. <br>
<kbd>
    <img alt="Name and add" src="../images/kiosk-steps/kiosk-custom-2.png"/>
</kbd>

<br>

4. Określ nazwę ustawień OMA-URI.

    1. W polu tekstowym OMA-URI wprowadź **./Device/Vendor/MSFT/AssignedAccess/Configuration**
    1. Wybierz pozycję Typ danych jako **Ciąg**.
    1. W polu tekstowym value (wartość) skopiuj i wklej kod XML konfiguracji przypisanego dostępu (zobacz linki referencyjne, aby uzyskać przykłady oparte na twoim scenariuszu i zaktualizuj je zgodnie z potrzebami przed wklejonym kopiowaniem).
    1. Wybierz przycisk Zapisz, aby zapisać ustawienie i konfigurację.

    <kbd>
        <img alt="Specify OMA-URI settings" src="../images/kiosk-steps/kiosk-custom-3.png"/>
    </kbd>

<br>

5. Wybierz grupy/urządzenia lub użytkowników, do których ma zostać przypisany ten profil konfiguracji. <br>
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-custom-4.png"/>
</kbd>

<br>

6. Przejrzyj i utwórz plik , aby zapisać profil konfiguracji.
1. Wykonaj synchronizację zarządzania urządzeniami przenośnymi, zaczynając od urządzenia lub usługi Intune, aby zastosować konfigurację do urządzenia. Synchronizowanie urządzeń z usługi [Intune](/mem/intune/remote-actions/device-sync#sync-a-device) lub na urządzeniu za pośrednictwem konta **usługi Ustawienia -> -> Work or school ->** wybierz połączone konto **-> Info -> Sync**
1. Zaloguj się jako użytkownik docelowy, aby doświadczyć kiosku.

# <a name="runtime-provisioning---multi-app"></a>[Aprowizowanie środowiska uruchomieniowego — wiele aplikacji](#tab/ppkgmak)

## <a name="runtime-provisioning---multi-app"></a>Aprowizowanie środowiska uruchomieniowego — wiele aplikacji

1. Utwórz konfigurację XML dla żądanego typu kiosku. Aby [rozpocząć,](../hololens-kiosk-reference.md#kiosk-xml-code-samples) zobacz przykłady tutaj.

1. Otwórz [Windows Configuration Designer.](https://www.microsoft.com/store/apps/9nblggh4tx22)

1. Na stronie Start wybierz pozycję **Aprowizuj HoloLens urządzeń.** <br>
<kbd>
    <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
</kbd>

<br>

4. Wybierz **pozycję HoloLens 2 urządzenia, a** następnie wybierz przycisk Dalej. <br>
<kbd>
    <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
</kbd>

<br>

5. Nazwij projekt. Opcjonalnie napisz opis. Wybierz **pozycję Zakończ,** aby kontynuować.

6. W lewym dolnym rogu ekranu wybierz pozycję **Przełącz do edytora zaawansowanego.** Potwierdź przejście do edytora zaawansowanego, wybierając pozycję **Tak.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

7. Po lewej stronie rozwiń pozycję Ustawienia środowiska uruchomieniowego, AssignedAccess i **wybierz pozycję MultiAppAssignedAccess.** <br>

    <kbd>
        <img alt="select MultiAppAssignedAccess" src="../images/kiosk-steps/kiosk-provision-3.png"/>
    </kbd>

<br>

8. Wybierz przycisk **Przeglądaj…** , aby otworzyć Eksploratora plików. Następnie wybierz skonfigurowany plik XML kiosku.

9. Wybierz **pozycję Eksportuj** , a następnie **pozycję Pakiet aprowizowania.**

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

10. Zmień typ właściciela na **Administrator IT.** <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

11. Trzykrotnie wybierz pozycję **Dalej**. Następnie wybierz pozycję **Build (Kompilacja).**

12. Po skompilowaniu pakietu aprowizowania otwórz folder Lokalizacja wyjściowa. Plik ppkg jest pakietem aprowizymacyjną. Krok opcjonalny: Zapisz projekt.

13. Teraz możesz zastosować pakiet aprowizowania. Możesz zastosować [pakiet aprowizowania do](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) usługi HoloLens instalacji lub zastosować pakiet aprowizowania do usługi HoloLens po [zakończeniu instalacji.](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)

14. Zaloguj się jako użytkownik docelowy, aby doświadczyć kiosku.

# <a name="runtime-provisioning---single-app"></a>[Aprowizowanie środowiska uruchomieniowego — pojedyncza aplikacja](#tab/ppkgsak)

## <a name="runtime-provisioning---single-app"></a>Aprowizowanie środowiska uruchomieniowego — pojedyncza aplikacja

1. Otwórz [Windows Configuration Designer.](https://www.microsoft.com/store/apps/9nblggh4tx22)

1. Na stronie Start wybierz pozycję **Aprowizuj HoloLens urządzeń.** <br>

    <kbd>
        <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
    </kbd>

<br>

3. Wybierz **pozycję HoloLens 2 urządzenia, a** następnie wybierz przycisk Dalej. <br>

    <kbd>
        <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

4. Nazwij projekt. Opcjonalnie napisz opis. Wybierz **pozycję Zakończ,** aby kontynuować.

5. W lewym dolnym rogu ekranu wybierz pozycję **Przełącz do edytora zaawansowanego.** Potwierdź przejście do edytora zaawansowanego, wybierając pozycję **Tak.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

6. Po lewej stronie rozwiń pozycję Ustawienia środowiska uruchomieniowego, AssignedAccess i wybierz pozycję **AssignedAccessSettings.** <br>

    <kbd>
        <img alt="Navigate to assigned access settings" src="../images/kiosk-steps/kiosk-provision-sak-1.png"/>
    </kbd>

<br>

7. Zdefiniuj kiosk w polu tekstowym. Na przykład poniżej przedstawiono sposób tworzenia kiosku z pojedynczą aplikacją dla konta lokalnego o nazwie LocalAccount, które jest aplikacją ustawienia.
```{"Account":"LocalAccount","AUMID":"BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App"}```

8. Wybierz **pozycję Eksportuj** , a następnie **pozycję Pakiet aprowizowania.** <br>

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

9. Zmień typ właściciela na **Administrator IT.** <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

10. Trzykrotnie wybierz pozycję **Dalej**. Następnie wybierz pozycję **Build (Kompilacja).**

11. Po skompilowaniu pakietu aprowizowania otwórz folder Lokalizacja wyjściowa. Plik ppkg jest pakietem aprowizymacyjną. Krok opcjonalny: Zapisz projekt.

12. Teraz możesz zastosować pakiet aprowizowania. Możesz zastosować [pakiet aprowizowania do](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) usługi HoloLens instalacji lub zastosować pakiet aprowizowania do usługi HoloLens po [zakończeniu instalacji.](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)