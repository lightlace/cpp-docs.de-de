---
title: Dialogfeld-Steuerelemente (C++) | Microsoft-Dokumentation
ms.date: 02/15/2019
f1_keywords:
- Custom Control
helpviewer_keywords:
- controls [C++], dialog boxes
- dialog box controls [C++], about dialog box controls
- dialog box controls
- controls [C++], templates
- custom controls [C++], dialog boxes
- custom controls [C++]
- dialog box controls [C++], custom (user) controls
- Dialog Editor [C++], custom controls
ms.assetid: e216c4f9-2fd4-429d-889a-8ebce7bad177
ms.openlocfilehash: 568754bc514ae017293805fab1b25849d5ffe5f8
ms.sourcegitcommit: 8bb2bea1384b290b7570b01608a86c7488ae7a02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2019
ms.locfileid: "67400882"
---
# <a name="dialog-box-controls-c"></a>Dialogfeld-Steuerelemente (C++)

Sie können Steuerelemente hinzufügen, um ein Dialogfeld unter Verwendung der **Dialog-Editor** Registerkarte die [Fenster "Toolbox"](/visualstudio/ide/reference/toolbox) , wählen Sie das Steuerelement, Sie möchten, und ziehen Sie es in das Dialogfeld ermöglicht. In der Standardeinstellung die **Toolbox** Fenster automatisch im Hintergrund festgelegt ist. Sie wird als eine Registerkarte am linken Rand Ihrer Lösung bei der **Dialog-Editor** geöffnet ist. Allerdings können Sie anheften der **Toolbox** Fenster an Position durch Auswählen der **automatisch im Hintergrund** Schaltfläche in der oberen rechten Ecke des Fensters. Weitere Informationen zum Steuern des Verhaltens des in diesem Fenster finden Sie unter [Fensterverwaltung](/visualstudio/ide/customizing-window-layouts-in-visual-studio).

Die schnellste Möglichkeit zum Hinzufügen von Steuerelementen zu einem Dialogfeld, vorhandene Steuerelemente neu positionieren oder verschieben Sie die Steuerelemente in einem Dialogfeld in eine andere ist die Verwendung die Drag & Drop-Methode. Die Position des Steuerelements wird in einer gepunkteten Linie beschrieben werden, bis sie in das Dialogfeld gelöscht wird. Wenn Sie ein Steuerelement an ein Dialogfeld mit der Drag & Drop-Methode hinzufügen, erhält das Steuerelement eine Standardhöhe für diese Art von Steuerelement geeignet.

Wenn Sie ein Dialogfeld, das ein Steuerelement hinzufügen oder ihn neu anzuordnen, möglicherweise die endgültige Position von Führungslinien oder Ränder bestimmt werden oder ob Sie das Layoutraster aktiviert haben.

Nachdem Sie das Dialogfeld ein Steuerelement hinzugefügt haben, können Sie Eigenschaften wie z. B. die Beschriftung, im Ändern der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window). Sie können auch mehrere Steuerelemente auswählen und alle gleichzeitig, ihre Eigenschaften ändern.

Weitere Informationen zu den **Dialog-Editor**, finden Sie unter Vorgehensweise [hinzufügen, bearbeiten oder Löschen von Steuerelementen](adding-editing-or-deleting-controls.md), [Layout-Steuerelemente](../windows/arrangement-of-controls-on-dialog-boxes.md), und [Steuern des Zugriffs definieren und Werte](../windows/defining-mnemonics-access-keys.md).

Weitere Informationen zu Steuerelementen und Dialogfelder, finden Sie unter [Steuerelementklassen](../mfc/control-classes.md), [Dialogfeldklassen](../mfc/dialog-box-classes.md), und [Stile des Schiebeleisten Steuerelements](../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles).

Die Standardsteuerelemente sind in der **Toolbox** Standardwert Ereignisse sind:

|Steuerelementname|Standardereignis|
|---|---|
|[Schaltflächen-Steuerelement](../mfc/reference/cbutton-class.md)|BN_CLICKED|
|[Kontrollkästchen-Steuerelement](../mfc/reference/styles-used-by-mfc.md#button-styles)|BN_CLICKED|
|[Kombinationsfeld-Steuerelement](../mfc/reference/ccombobox-class.md)|CBN_SELCHANGE|
|[Steuerelement bearbeiten](../mfc/reference/cedit-class.md)|EN_CHANGE-EREIGNIS|
|Gruppenfeld|(nicht zutreffend)|
|[Listenfeld-Steuerelement](../mfc/reference/clistbox-class.md)|LBN_SELCHANGE|
|[Optionsfeld-Steuerelement](../mfc/reference/styles-used-by-mfc.md#button-styles)|BN_CLICKED|
|[Statischer Text-Steuerelement](../mfc/reference/cstatic-class.md)|(nicht zutreffend)|
|[Bildsteuerelement](../mfc/reference/cpictureholder-class.md)|(nicht zutreffend)|
|[Rich Edit 2.0-Steuerelement](../mfc/using-cricheditctrl.md)|EN_CHANGE-EREIGNIS|
|[Bildlaufleisten-Steuerelement](../mfc/reference/cscrollbar-class.md)|NM_THEMECHANGED|

> [!NOTE]
> Weitere Informationen zur Verwendung der **RichEdit 1.0** mit MFC zu steuern, finden Sie unter [Verwenden des RichEdit 1.0-Steuerelements mit MFC](../windows/using-the-richedit-1-0-control-with-mfc.md) und [Rich bearbeiten Beispiele für](../mfc/rich-edit-control-examples.md).

Die [Windows-Standardsteuerelemente](../mfc/controls-mfc.md) zur Verfügung, in der **Toolbox** angeben, werden umfangreichere Funktionen:

|Steuerelementname|Standardereignis|
|---|---|
|[Schieberegler-Steuerelement](../mfc/slider-control-styles.md)|NM_CUSTOMDRAW|
|[Drehfeld-Steuerelement](../mfc/using-cspinbuttonctrl.md)|UDN_DELTAPOS|
|[Statuskontrolle](../mfc/styles-for-the-progress-control.md)|NM_CUSTOMDRAW|
|[Abkürzungstasten-Steuerelement](../mfc/using-a-hot-key-control.md)|NM_OUTOFMEMORY|
|[Listensteuerelement](../mfc/list-control-and-list-view.md)|LVN_ITEMCHANGE|
|[Strukturansicht-Steuerelement](../mfc/tree-control-styles.md)|TVN_SELCHANGE|
|[Registerkarten-Steuerelement](../mfc/tab-controls-and-property-sheets.md)|TCN_SELCHANGE|
|[Animation-Steuerelement](../mfc/using-an-animation-control.md)|ACN_START|
|[Datums-/ Zeitauswahl-Steuerelement](../mfc/creating-the-date-and-time-picker-control.md)|DTN_DATETIMECHANGE|
|[Monatskalender-Steuerelement](../mfc/month-calendar-control-examples.md)|MCN_SELCHANGE|
|[IP-Adressensteuerelement](../mfc/reference/cipaddressctrl-class.md)|IPN_FIELDCHANGED|
|[Erweitertes Kombinationsfeld-Steuerelement](../mfc/creating-an-extended-combo-box-control.md)||
|Benutzerdefiniertes Steuerelement|TTN_GETDISPINFO|

## <a name="custom-controls"></a>Benutzerdefinierte Steuerelemente

Die **Dialog-Editor** können Sie vorhandene benutzerdefinierte oder Benutzersteuerelemente in einer Dialogfeldvorlage.

> [!NOTE]
> Benutzerdefinierte Steuerelemente in diesem Zusammenhang sind nicht zu verwechseln mit ActiveX-Steuerelementen. ActiveX-Steuerelemente wurden benutzerdefinierte OLE-Steuerelemente bezeichnet. Verwechseln Sie nicht auch diese Steuerelemente mit den ownerdrawn-Steuerelementen in Windows.

Diese Funktion dient als die vom Windows-Steuerelemente verwenden zu können. Zur Laufzeit für das Steuerelement eine Fensterklasse (nicht die gleiche als C++-Klasse) zugeordnet ist. Eine allgemeinere Möglichkeit zum Ausführen der gleichen Aufgabe besteht darin Kontrolle, z. B. ein statisches Steuerelement in einem Dialogfeld zu installieren. Klicken Sie dann zur Laufzeit in die [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) funktionieren, entfernen Sie das Steuerelement aus, und durch Ihr eigenes benutzerdefiniertes Steuerelement ersetzen.

> [!NOTE]
> Dies ist eine alte Technik. Noch heute in den meisten Fällen sollten Sie ein ActiveX-Steuerelement oder eine Unterklasse eines allgemeinen Steuerelements von Windows zu schreiben.

Für benutzerdefinierte Steuerelemente sind Sie auf:

- Festlegen des Speicherorts im Dialogfeld an.

- Eingeben einer Beschriftung.

- Identifizieren den Namen der Windows-Klasse des Steuerelements aus, da Anwendungscode, damit er das Steuerelement mit diesem Namen registrieren muss.

- Geben einen 32-Bit-Hexadezimalwert, das Format des Steuerelements legt diese fest.

- Wenn den erweiterten Stil.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Dialog-Editor](../windows/dialog-editor.md)

<!--
[Adding Event Handlers for Dialog Box Controls](../windows/adding-event-handlers-for-dialog-box-controls.md)<br/>
[Dialog Box Controls and Variable Types](../ide/dialog-box-controls-and-variable-types.md)<br/>
[Controls](../mfc/controls-mfc.md)<br/>-->