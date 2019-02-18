---
title: Steuern des Zugriffs und Werte definieren
ms.date: 02/15/2019
f1_keywords:
- vc.editors.dialog.combo
helpviewer_keywords:
- access keys [C++], adding
- keyboard shortcuts [C++], controls
- dialog box controls [C++], mnemonics
- access keys [C++], checking
- mnemonics [C++], checking for duplicate
- mnemonics
- mnemonics [C++], dialog box controls
- keyboard shortcuts [C++], uniqueness checking
- Check Mnemonics command
- controls [C++], access keys
- access keys [C++]
- combo boxes [C++], Data property
- controls [C++], testing values in combo boxes
- combo boxes [C++], adding values
- combo boxes [C++], previewing values
- Data property
- combo boxes [C++], testing values
ms.assetid: 60a85435-aa30-4c5c-98b6-42fb045b9eb2
ms.openlocfilehash: 20319cd08d6d1e77faef1275e63bf3ffd354356b
ms.sourcegitcommit: 24592ba0a38c7c996ffd3d55fe1024231a59ccc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2019
ms.locfileid: "56336487"
---
# <a name="defining-control-access-and-values"></a>Steuern des Zugriffs und Werte definieren

## <a name="change-the-tab-order-of-controls"></a>Ändern der Aktivierreihenfolge von Steuerelementen

Die Aktivierreihenfolge ist die Reihenfolge, in der **Registerkarte** -Taste wird den Eingabefokus von einem Steuerelement verschoben, an den nächsten in einem Dialogfeld. In der Regel wird die Aktivierreihenfolge auf, von links nach rechts und von oben nach unten in einem Dialogfeld. Jedes Steuerelement verfügt über eine **Tabstop** -Eigenschaft, die bestimmt, ob ein Steuerelement den Eingabefokus erhält.

### <a name="to-set-input-focus-for-a-control"></a>Eingabefokus für ein Steuerelement festgelegt.

In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window)Option **"true"** oder **"false"** in die **Tabstop** Eigenschaft.

Auch Steuerelemente, die nicht die **Tabstop** -Eigenschaftensatz auf **"true"** müssen Teil der Aktivierreihenfolge. Tab-Reihenfolge ist wichtig, z. B., wenn Sie [definieren Sie Zugriffstasten (mnemonischen Zeichen)](../windows/defining-mnemonics-access-keys.md) für Steuerelemente, die keine Beschriftungen haben. Statischer Text, der eine Zugriffstaste für ein verwandtes Steuerelement enthält muss das zugehörige Steuerelement in der Aktivierreihenfolge unmittelbar vorangestellt sein.

> [!NOTE]
> Wenn das Dialogfeld überlappende Steuerelemente enthält, unter Umständen ändern der Aktivierreihenfolge verändern, wie die Steuerelemente angezeigt werden. Steuerelemente, die weiter unten in der Aktivierreihenfolge erläutert werden immer auf überlappende Steuerelemente angezeigt, die ihnen in der Aktivierreihenfolge vorausgehen.

### <a name="to-view-the-current-tab-order-for-all-controls-in-a-dialog-box"></a>Anzeigen die aktuellen Aktivierreihenfolge für alle Steuerelemente in einem Dialogfeld

Wechseln Sie zu der **Format** Menü **Aktivierreihenfolge**, oder drücken Sie **STRG** + **D**.

### <a name="to-change-the-tab-order-for-all-controls-in-a-dialog-box"></a>So ändern Sie die Aktivierreihenfolge für alle Steuerelemente in einem Dialogfeld

1. Auf der **Format** , wählen Sie im Menü **Aktivierreihenfolge**.

   Eine Zahl in der oberen linken Ecke der einzelnen Steuerelemente zeigt seine Position in der aktuellen Aktivierreihenfolge.

1. Festlegen der Aktivierreihenfolge dazu jedes Steuerelement in der Reihenfolge, Sie möchten, die **Registerkarte** Schlüssel folgen.

1. Drücken Sie **EINGABETASTE** beendet **Aktivierreihenfolge** Modus.

   > [!TIP]
   > Nach der Eingabe **Aktivierreihenfolge** -Modus können Sie durch Drücken **Esc** oder **EINGABETASTE** So deaktivieren Sie die Möglichkeit zum Ändern der Aktivierreihenfolge.

### <a name="to-change-the-tab-order-for-two-or-more-controls"></a>So ändern Sie die Aktivierreihenfolge für zwei oder mehr Steuerelementen

1. Von der **Format** Menü wählen **Aktivierreihenfolge**.

1. Geben Sie die Änderung in der Reihenfolge, in denen beginnt. Halten Sie zunächst die **STRG** Schlüssel wählen Sie das Steuerelement, und wählen Sie diejenige aus, die Reihenfolge geänderte werden sollen.

   Z. B., wenn Sie die Reihenfolge der Steuerelemente ändern möchten `7` über `9`, halten Sie die **STRG**, wählen Sie dann das Steuerelement `6` erste.

   > [!NOTE]
   > Für ein bestimmtes Steuerelement festzulegen, Anzahl `1` (zuerst in der Aktivierreihenfolge), doppelklicken Sie auf das Steuerelement.

1. Version der **STRG** Schlüssel aus, und wählen Sie die Steuerelemente in der gewünschten Reihenfolge der **Registerkarte** -Taste, um von diesem Punkt folgen.

1. Drücken Sie **EINGABETASTE** beendet **Aktivierreihenfolge** Modus.

## <a name="define-mnemonics-access-keys"></a>Definieren der mnemonischen Zeichen (Zugriffstasten)

In der Regel Benutzer über die Tastatur verschieben den Eingabefokus von einem Steuerelement zu einem anderen in einem Dialogfeld mit den **Registerkarte** und **Pfeil** Schlüssel. Allerdings können Sie eine Zugriffstaste (ein mnemonisches oder einfach zu merkenden-Name) definieren, die Benutzern ermöglicht, ein Steuerelement auswählen, indem Sie eine Taste zu drücken.

### <a name="to-define-an-access-key-for-a-control-with-a-visible-caption-push-buttons-check-boxes-and-radio-buttons"></a>Definieren Sie eine Zugriffstaste für ein Steuerelement mit einem sichtbaren Titel (Schaltflächen, Kontrollkästchen und Optionsfelder)

1. Wählen Sie das Steuerelement im Dialogfeld ein.

1. In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window)in die **Beschriftung** -Eigenschaft, geben Sie einen neuen Namen für das Steuerelement, ein kaufmännisches (`&`) vor den Buchstaben als Zugriffstaste für dieses Steuerelement werden soll. Beispielsweise `&Radio1`.

1. Drücken Sie die **EINGABETASTE**.

   Ein Unterstrich angezeigt, die angezeigte Beschriftung an den Zugriffsschlüssel, z. B. **R**adio1.

### <a name="to-define-an-access-key-for-a-control-without-a-visible-caption"></a>Definieren Sie eine Zugriffstaste für ein Steuerelement ohne sichtbare Beschriftung

1. Erstellen Sie eine Beschriftung für das Steuerelement mit einem **statischen Text** steuern, der [Toolbox](/visualstudio/ide/reference/toolbox).

1. Geben Sie in der Beschriftung des statischen Text, ein kaufmännisches und-Zeichen (`&`) vor dem Buchstaben als Zugriffstaste verwendet werden sollen.

1. Stellen Sie sicher, dass das Steuerelement statischer Text unmittelbar vor dem Steuerelement befindet, die, das Sie in der Aktivierreihenfolge "Bezeichnungen".

> [!NOTE]
> Alle Zugriffstasten in einem Dialogfeld sollte eindeutig sein. Um doppelte Zugriffstasten finden, wechseln Sie zu der **Format** Menü **Mnemonik**.

## <a name="combo-box-values"></a>Kombinationsfeld-Werte

Sie können Werte an ein Kombinationsfeld-Steuerelement hinzufügen, solange Sie haben die **Dialogfeld** Editor öffnen.

> [!TIP]
> Es ist eine gute Idee, alle Werte im Kombinationsfeld hinzufügen *vor* Sie seine Größe im der **Dialogfeld** -Editor, oder Sie können truncate Text, der im Kombinationsfeld-Steuerelement angezeigt werden soll.

### <a name="to-enter-values-into-a-combo-box-control"></a>Um die Werte in einem Kombinationsfeld-Steuerelement eingeben

1. Wählen Sie das Kombinationsfeld-Steuerelement, indem Sie auswählen.

1. In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), führen Sie einen Bildlauf nach unten, um die **Daten** Eigenschaft.

   > [!NOTE]
   > Wenn Sie Eigenschaften gruppiert nach Typ anzeigen **Daten** wird in der **Verschiedenes** Eigenschaften.

1. Wählen Sie den Wertebereich für die **Daten** Eigenschaft, und geben die Datenwerte, die durch Semikolons getrennt sind.

   > [!NOTE]
   > Leerzeichen Sie keine zwischen den Werten, da behindert werden, dass Leerzeichen in der Dropdown-Liste alphabetisch sortiert.

1. Drücken Sie **EINGABETASTE** Sie abschließend Werte hinzufügen.

Informationen dazu, wie den Dropdown-Teil eines Kombinationsfelds vergrößern, finden Sie unter [Festlegen der Größe des Kombinationsfelds und einem Dropdown-Listenfeld](setting-the-size-of-the-combo-box-and-its-drop-down-list.md).

> [!NOTE]
> Win32-Projekte, die mit dieser Prozedur können keine Werte hinzugefügt (die **Daten** Eigenschaft abgeblendet ist, für die Win32-Projekte). Da Win32-Projekte nicht über Bibliotheken, die diese Funktion hinzuzufügen verfügen, müssen Sie Werte an ein Kombinationsfeld mit einem Win32-Projekt programmgesteuert hinzufügen.

### <a name="to-test-the-appearance-of-values-in-a-combo-box"></a>So testen Sie die Darstellung der Werte in einem Kombinationsfeld

Nach der Eingabe von Werten in der **Daten** -Eigenschaft die Option der **Test** Schaltfläche der [Dialog-Editor-Symbolleiste](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).

   Versuchen Sie es in den gesamten Wert-Liste nach unten scrollen. Werte angezeigt werden, genau wie die Eingabe in die **Daten** -Eigenschaft in der **Eigenschaften** Fenster. Es gibt keine Rechtschreib- oder Großschreibung zu überprüfen.

   Drücken Sie **ESC-Taste** zum Zurückgeben der **Dialogfeld** Editor.

   Jetzt können Sie Ihren Code ändern, um festzulegen, welches Optionsfeld aus aktiviert angezeigt werden soll. Z. B. `m_radioBox1 = 0;` wählt das erste Optionsfeld in der Gruppe.
Jetzt können Sie Ihren Code ändern, um festzulegen, welches Optionsfeld aus aktiviert angezeigt werden soll. Z. B. `m_radioBox1 = 0;` wählt das erste Optionsfeld in der Gruppe.

## <a name="radio-button-values"></a>Optionsfeld ' Werte

Wenn Sie ein Dialogfeld Optionsschaltflächen hinzufügen, behandeln sie als Gruppe durch Festlegen einer **Gruppe** -Eigenschaft in der **Eigenschaften** Fenster für die erste Schaltfläche in der Gruppe. Eine Steuerelement-ID für das betreffende Optionsfeld wird dann im [Assistent zum Hinzufügen von Membervariablen](../ide/add-member-variable-wizard.md)angezeigt und ermöglicht das Hinzufügen einer Membervariablen zur Gruppe der Optionsfelder.

Sie haben mehr als eine Gruppe von Optionsfeldern in einem Dialogfeld. Fügen Sie jeder Gruppe, die mithilfe des folgenden Verfahrens hinzu.

### <a name="to-add-a-group-of-radio-buttons-to-a-dialog-box"></a>So fügen Sie einem Dialogfeld eine Gruppe von Optionsfeldern hinzu

1. Wählen Sie das Optionsfeld-Steuerelement in der [Fenster "Toolbox"](/visualstudio/ide/reference/toolbox) , und wählen Sie dem Speicherort im Dialogfeld den Speicherort zum Platzieren des Steuerelements.

1. Wiederholen Sie den obigen Schritt, um so viele Optionsfelder wie erforderlich hinzuzufügen. Stellen Sie sicher, dass die Optionsfelder in der Gruppe in der Aktivierreihenfolge aufeinander folgen.

1. Legen Sie im Fenster [Eigenschaften](/visualstudio/ide/reference/properties-window)die Eigenschaft **Gruppe** des *ersten* Optionsfelds in der Aktivierreihenfolge auf **Wahr**fest.

   Ändern der **Gruppe** Eigenschaft **"true"** dem Eintrag in das Dialogfeldobjekt, der das Ressourcenskript styl WS_GROUP hinzugefügt, und verhindert, dass die Benutzer kann Sie Sie gleichzeitig in mehr als ein Optionsfeld auswählen der Optionsfeldgruppe (wenn der Benutzer wählt ein Optionsfeld, die anderen in der Gruppe gelöscht werden).

   > [!NOTE]
   > Die Eigenschaft **Gruppe** sollte nur für das erste Optionsfeld einer Gruppe auf **Wahr**festgelegt werden. Wenn Sie über weitere Steuerelemente verfügen, die nicht Teil der Optionsfeldgruppe sind, legen Sie die Eigenschaft **Gruppe** des ersten Steuerelements, *das sich außerhalb der Gruppe befindet* , ebenfalls auf **Wahr** fest. Sie können das erste Steuerelement außerhalb der Gruppe schnell identifizieren, mit **STRG**+**D** auf die Aktivierreihenfolge anzuzeigen.

### <a name="to-add-a-member-variable-for-the-radio-button-group"></a>So fügen Sie eine Membervariable für die Optionsfeldgruppe hinzu

1. Mit der rechten Maustaste in des erste Optionsfeld-Steuerelements in der Aktivierreihenfolge (das dominante Steuerelement, und der Auftrag mit dem die **Gruppe** -Eigenschaft auf festgelegt **"true"**), und wählen Sie **Variable hinzufügen** aus der im Kontextmenü.

1. Aktivieren Sie im [Assistent zum Hinzufügen von Membervariablen](../ide/add-member-variable-wizard.md)das Kontrollkästchen **Steuerungsvariable** , und aktivieren Sie dann das Optionsfeld **Wert** .

1. Geben Sie im Feld **Variablenname** einen Namen für die neue Membervariable ein.

1. Wählen Sie im Listenfeld **Variablentyp** **int** aus, oder geben Sie *int*ein.

   Jetzt können Sie Ihren Code ändern, um festzulegen, welches Optionsfeld aus aktiviert angezeigt werden soll. Z. B. `m_radioBox1 = 0;` wählt das erste Optionsfeld in der Gruppe.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)