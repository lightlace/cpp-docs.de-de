---
title: 'Vorgehensweise: Hinzufügen, bearbeiten oder Löschen von Steuerelementen (C++)'
ms.date: 02/15/2019
f1_keywords:
- vc.editors.dialog.dialog
- vc.controls.activex
- vc.editors.dialog.insertActiveXControls
helpviewer_keywords:
- Dialog Editor [C++], creating controls
- dialog boxes [C++], adding controls to
- Toolbox [C++], Dialog Editor tab
- controls [C++], types
- syslink controls in dialog boxes
- custom controls [C++], dialog boxes
- controls [C++], standard
- Dialog Editor [C++], creating controls
- controls [C++], adding to dialog boxes
- controls [C++], adding multiple
- dialog box controls [C++], size
- controls [C++], sizing
- dialog boxes [C++], adding ActiveX controls
- ActiveX controls [C++], adding to dialog boxes
- Insert ActiveX Control dialog box [C++]
- controls [C++], editing properties
- ActiveX controls [C++], properties
- controls [C++], undoing changes
- controls [C++], editing properties
- dialog box controls [C++], editing properties
- dialog box controls [C++], deleting
- controls [C++], deleting
- Dialog Editor [C++], default control events
- controls [C++], default control events
- events [C++], controls
- dialog box controls [C++], events
- member variables, defining for controls
- variables, dialog box control member variables
- controls [C++], member variables
- Dialog Editor [C++], defining member variables for controls
- controls [C++], troubleshooting
- Dialog Editor [C++], troubleshooting
- dialog boxes [C++], troubleshooting
- InitCommonControls
- RichEdit 1.0 control
- rich edit controls [C++], RichEdit 1.0
ms.assetid: 73cef03f-5c8c-456a-87d1-1458dff185cf
ms.openlocfilehash: 2e3e671cd92313ad120d2cd6aae3f7e815e09e65
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59025363"
---
# <a name="how-to-add-edit-or-delete-controls-c"></a>Vorgehensweise: Hinzufügen, bearbeiten oder Löschen von Steuerelementen (C++)

Mithilfe der **Dialog-Editor**hinzufügen Größe ändern, bearbeiten und löschen Sie die Steuerelemente in Dialogfeldern. Sie können auch die Eigenschaften eines Steuerelements, z. B. die ID, bearbeiten oder ob es sichtbare zur Laufzeit ist.

Die **Dialog-Editor** Registerkarte wird angezeigt, der [Fenster "Toolbox"](/visualstudio/ide/reference/toolbox) beim Arbeiten der **Dialog-Editor**. Sie können auch anpassen, die **Toolbox** Fenster zur einfacheren Verwendung. Weitere Informationen finden Sie unter [mithilfe der Toolbox](/visualstudio/ide/using-the-toolbox) und [ein- oder Ausblenden der Fenster "Toolbox"](showing-or-hiding-the-dialog-editor-toolbar.md).

> [!TIP]
> Bei der Verwendung der **Dialog-Editor**, in vielen Fällen können Sie auswählen, der rechten Maustaste auf ein Kontextmenü mit häufig verwendeten Befehlen anzuzeigen.

## <a name="add-controls"></a>Hinzufügen von Steuerelementen

### <a name="to-add-a-control"></a>Hinzufügen des Steuerelements

1. Stellen Sie sicher, dass das Dialogfeld im Registerkartenformat das aktuelle Dokument im Editor-Fenster darstellt. Wenn ein Dialogfeld mit dem aktuellen Dokument nicht ist, werden Sie nicht angezeigt der **Registerkarte "Dialog-Editor"** in die **Toolbox**.

1. Auf der **Dialog-Editor** Registerkarte die **Toolbox** Fenster, wählen Sie das Steuerelement werden sollen, klicken Sie dann entweder:

   - Wählen Sie im Dialogfeld auf den Speicherort, an der Sie das Steuerelement platzieren möchten, und das Steuerelement angezeigt wird, in dem Sie ausgewählt haben.

   - Ziehen Sie aus, und legen Sie das Steuerelement aus der **Toolbox** Fenster aus, um den Speicherort für das Dialogfeld, und Sie können dann die Steuerelemente beliebig verschieben oder ändern ihre Größe und Form.

   - Doppelklicken Sie auf das Steuerelement in der **Toolbox** Fenster und wird im Dialogfeld angezeigt, klicken Sie dann verschieben Sie das Steuerelement, zu dem Speicherort, die Sie bevorzugen.

### <a name="to-add-multiple-controls"></a>Hinzufügen mehrerer Steuerelemente

1. Halten Sie die **STRG** Schlüssel, wählen Sie ein Steuerelement in der **Toolbox** Fenster.

1. Version der **STRG** gedrückt, und wählen Sie das Dialogfeld so häufig wie das jeweilige Steuerelement hinzugefügt werden soll.

1. Drücken Sie **Esc** zum Platzieren von Steuerelementen zu beenden.

### <a name="to-size-a-control-while-you-add-it"></a>Die Größe eines Steuerelements, beim Hinzufügen

1. Wählen Sie ein Steuerelement in der **Toolbox** Fenster.

1. Platzieren Sie den Cursor, der als Fadenkreuz, der oberen linken Ecke des neuen Steuerelements erscheint auf das Dialogfeld erstellt werden sollen.

1. Wählen Sie aus, halten Sie die Maustaste gedrückt, verankern Sie die linke obere Ecke des Steuerelements im Dialogfeld, und ziehen Sie den Cursor nach rechts und nach unten, bis die gewünschte Größe hat.

   > [!NOTE]
   > Sie können eine der vier Ecken des Steuerelements verankern, die Sie zeichnen können. Dieses Verfahren verwendet die oberen linken Ecke als Beispiel.

1. Lassen Sie die Maustaste los. Das Steuerelement ist in der angegebenen Größe im Dialogfeld angelegt.

> [!TIP]
> Sie können die Größe des Steuerelements nach dem Ablegen im Dialogfeld durch das Verschieben der Ziehpunkte am Rand des Steuerelements. Weitere Informationen finden Sie unter [Festlegen der Größe der einzelnen Steuerelementen](../windows/sizing-individual-controls.md).

### <a name="to-add-a-custom-control"></a>So fügen Sie ein benutzerdefiniertes Steuerelement hinzu

Sie können benutzerdefinierte Steuerelemente zum Dialogfeld hinzufügen, durch Auswählen der **benutzerdefiniertes Steuerelement** Symbol in der **Toolbox** und ziehen diesen an das Dialogfeld. Hinzufügen einer **Syslink** steuern, fügen Sie ein benutzerdefiniertes Steuerelement hinzu, und Ändern des Steuerelements **Klasse** Eigenschaft **Syslink**. Diese Aktion führt dazu, dass die Eigenschaften aktualisieren und Anzeigen der **Syslink** Steuerelementeigenschaften. Informationen zur MFC-Wrapperklasse finden Sie unter [CLinkCtrl](../mfc/reference/clinkctrl-class.md).

## <a name="edit-controls"></a>Edit-Steuerelemente

### <a name="to-edit-the-properties-of-a-control-or-controls"></a>So bearbeiten Sie die Eigenschaften eines Steuerelements oder-Steuerelemente

1. Wählen Sie das Steuerelement, die, das Sie ändern möchten, klicken Sie im Dialogfeld.

   > [!NOTE]
   > Wenn Sie mehrere Steuerelemente auswählen, können nur die Eigenschaften, die die ausgewählten Steuerelemente gemeinsam bearbeitet werden.

1. In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), ändern Sie die Eigenschaften des Steuerelements.

   > [!NOTE]
   > Beim Festlegen der **Bitmap** -Eigenschaft für eine Schaltfläche, Optionsfeld oder Kontrollkästchen-Steuerelement gleich **"true"**, den Stil BS_BITMAP für das Steuerelement implementiert wird. Weitere Informationen finden Sie unter [Button-Stile](../mfc/reference/styles-used-by-mfc.md#button-styles). Ein Beispiel für eine Bitmap mit einem Steuerelement zuordnen, finden Sie unter [CButton:: SetBitmap](../mfc/reference/cbutton-class.md#setbitmap). Bitmaps werden nicht auf das Steuerelement angezeigt, während Sie auf die **Dialog-Editor**.

### <a name="to-undo-changes-to-the-properties-of-a-control"></a>Um Änderungen an den Eigenschaften eines Steuerelements rückgängig zu machen.

1. Stellen Sie sicher, dass das Steuerelement den Fokus besitzt, der **Dialog-Editor**.

1. Wechseln Sie zum Menü **bearbeiten** > **Rückgängig**. Wenn der Fokus auf das Steuerelement ist nicht die **Rückgängig** Befehl nicht verfügbar.

### <a name="to-define-a-member-variable-for-a-non-button-dialog-box-control"></a>So definieren Sie eine Membervariable für ein Dialogfeld-Steuerelement (kein Schaltflächen-Steuerelement)

> [!NOTE]
> Dieser Vorgang gilt nur für Dialogfeld-Steuerelemente in einem MFC-Projekt. ATL-Projekte verwenden, sollten die **neue Windows-Meldungen und Ereignishandler** Dialogfeld. Weitere Informationen finden Sie unter [Nachricht Typen Benutzeroberflächen-Objekten zugeordneten](../mfc/reference/message-types-associated-with-user-interface-objects.md), [Bearbeiten eines Meldungshandlers](../mfc/reference/editing-a-message-handler.md), und [Definieren eines Meldungshandlers für eine Nachricht wiedergegeben](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md).

1. In der [Dialog-Editor](../windows/dialog-editor.md), wählen Sie ein Steuerelement.

1. Beim Drücken der **STRG** Schlüssel, doppelklicken Sie auf das Dialogfeld-Steuerelement.

   Die [Assistenten zum Hinzufügen von Membervariablen](../ide/add-member-variable-wizard.md) angezeigt wird.

1. Geben Sie die entsprechende Informationen in den **Hinzufügen von Membervariablen** Assistenten. Weitere Informationen finden Sie unter [Dialogdatenaustausch](../mfc/dialog-data-exchange.md).

1. Wählen Sie **OK** zum Zurückgeben der **Dialog-Editor**.

> [!TIP]
> Doppelklicken Sie auf das Steuerelement, um von einem Dialogfeld-Steuerelement zu seinem vorhandenen Handler zu wechseln.

Sie können auch die **Membervariablen** Registerkarte die [MFC-Klassenassistent](../mfc/reference/mfc-class-wizard.md) neue Membervariablen für eine angegebene Klasse hinzufügen und Anzeigen der Membervariablen, die bereits definiert wurden.

## <a name="delete-controls"></a>Löschen von Steuerelementen

Wählen Sie im Dialogfeld, das Steuerelement aus, drücken Sie dann die **löschen** Taste, oder wechseln Sie zum Menü **bearbeiten** > **löschen**.

## <a name="other-issues"></a>Andere Probleme

### <a name="troubleshooting"></a>Problembehandlung

Nach dem Hinzufügen einer allgemeinen Steuerelements oder rich-Edit-Steuerelement in einem Dialogfeld an, nicht es angezeigt, wenn Sie Sie das Dialogfeld testen, oder das Dialogfeld selbst wird nicht, z. B. angezeigt:

1. Erstellen Sie eine Win32-Projekts, das die Anwendungseinstellungen ändern, damit Sie eine Windows-Anwendung (keine Konsolen-app erstellen).

1. In [Ressourcenansicht](how-to-create-a-resource-script-file.md#create-resources), doppelklicken Sie auf die *RC* Datei.

1. Doppelklicken Sie unter der Dialogfeldoption auf die **zu** Feld.

1. Hinzufügen einer **IP-Adressensteuerelement** auf das Dialogfeld.

1. Speichern und **alles neu erstellen**.

1. Führen Sie das Programm an.

1. In des Dialogfelds **Hilfe** , wählen Sie im Menü der **zu** -Befehl aus, und beobachten Sie das Dialogfeld nicht angezeigt wird.

Derzeit den **Dialog-Editor** nicht automatisch zu Ihrem Projekt Code hinzugefügt, wenn Drag & drop die folgenden allgemeinen Steuerelemente oder Rich--Steuerelemente in einem Dialogfeld Edit. Auch Visual Studio bietet Fehler oder Warnung, wenn dieses Problem auftritt. Um das Problem zu beheben, fügen Sie den Code für das Steuerelement manuell hinzu.

||||
|-|-|-|
|Schiebereglersteuerung|Strukturansicht-Steuerelement|Datums-/Zeitauswahl|
|Drehfeld-Steuerelement|Registerkarten-Steuerelement|Monatskalender|
|Statuskontrolle|Animation-Steuerelement|IP-Adressensteuerelement|
|Abkürzungstaste|Rich Edit-Steuerelements|Erweitertes Kombinationsfeld|
|Listensteuerelement|Rich Edit 2.0-Steuerelements|Benutzerdefiniertes Steuerelement|

Um allgemeine Steuerelemente in einem Dialogfeld verwenden zu können, müssen Sie zum Aufrufen [InitCommonControlsEx](/windows/desktop/api/commctrl/nf-commctrl-initcommoncontrolsex) oder `AFXInitCommonControls` vor der Erstellung des Dialogfelds.

Um RichEdit-Steuerelemente verwenden, rufen Sie `LoadLibrary`. Weitere Informationen finden Sie unter [über Rich-Edit-Steuerelemente](/windows/desktop/Controls/about-rich-edit-controls) im Windows SDK und [Überblick über das RichEdit-Steuerelement](../mfc/overview-of-the-rich-edit-control.md).

> [!NOTE]
> Um ein RichEdit-Steuerelement mit MFC verwenden zu können, müssen Sie zuerst Aufrufen [AfxInitRichEdit2](../mfc/reference/application-information-and-management.md#afxinitrichedit2) beim Laden des RichEdit-2.0-Steuerelements (RICHED20. DLL), oder rufen Sie [AfxInitRichEdit](../mfc/reference/application-information-and-management.md#afxinitrichedit) beim Laden des älteren RichEdit 1.0-Steuerelements (RICHED32. (DLL).
>
> Möglicherweise verwenden Sie die aktuelle [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) Klasse mit dem älteren RichEdit 1.0-Steuerelement, aber `CRichEditCtrl` dient nur zur Unterstützung des RichEdit-2.0-Steuerelements. Da RichEdit 1.0 und 2.0 des RichEdit ähnlich sind, funktionieren die meisten Methoden. Es gibt jedoch einige Unterschiede zwischen den Steuerelementen 1.0 und 2.0, sodass einige Methoden möglicherweise nicht ordnungsgemäß oder überhaupt nicht funktionsfähig.

### <a name="activex-controls"></a>ActiveX-Steuerelemente

Visual Studio ermöglicht Ihnen das Einfügen von ActiveX-Steuerelementen in Ihr Dialogfeld. Weitere Informationen finden Sie unter [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md) und [ActiveX-Steuerelementcontainer](../mfc/activex-control-containers.md).

Die **ActiveX-Steuerelement einfügen** Dialogfeld können Sie zum Einfügen von ActiveX-Steuerelemente in einem Dialogfeld bei der Verwendung der [Dialog-Editor](../windows/dialog-editor.md). Dieses Dialogfeld enthält die folgenden Eigenschaften:

|Eigenschaft|Beschreibung|
|---|---|
|**ActiveX-Steuerelement**|Zeigt eine Liste von ActiveX-Steuerelementen.<br/><br/>Einfügen eines Steuerelements in diesem Dialogfeld keine Wrapperklasse nicht generieren. Wenn Sie eine Wrapperklasse benötigen, verwenden Sie [Klassenansicht](/visualstudio/ide/viewing-the-structure-of-code) zum Erstellen finden Sie unter [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md).<br/><br/>Ein ActiveX-Steuerelement in diesem Dialogfeld angezeigt werden, versuchen Sie die Installation des Steuerelements entsprechend des Anbieters Anweisungen.|
|**Pfad**|Zeigt die Datei, die in der das ActiveX-Steuerelement gefunden wird.|

> [!CAUTION]
> Der Vertrieb ist möglicherweise nicht für alle ActiveX-Steuerelemente auf Ihrem System rechtlich zulässig. Informieren Sie sich im Lizenzvertrag für die Software, die die Steuerelemente installiert hat, oder wenden Sie sich an den Hersteller der Software.

#### <a name="to-add-an-activex-control"></a>Ein ActiveX-Steuerelement hinzufügen

1. Öffnen ein Dialogfeld der **Dialog-Editor**.

1. Mit der rechten Maustaste an einer beliebigen Stelle im Text des Dialogfelds, und wählen Sie **ActiveX-Steuerelement einfügen**.

   Die **ActiveX-Steuerelement einfügen** Dialogfeld angezeigt wird, stellt alle ActiveX-Steuerelemente auf Ihrem System. Unten im Dialogfeld wird der Pfad der Datei des ActiveX-Steuerelements angezeigt.

1. Wählen Sie das Steuerelement, das Sie verwenden möchten, fügen Sie Ihrem Dialogfeld hinzu, und wählen **OK**.

   Das Steuerelement wird im Dialogfeld angezeigt, wo Sie es bearbeiten oder Handler für es erstellen können, ganz wie bei jedem anderen Steuerelement.

> [!TIP]
> Können Sie das Kontextmenü in der **Dialog-Editor** schnell registrierten ActiveX-Steuerelemente zum Dialogfeld hinzufügen, oder versuchen Sie es Hinzufügen von ActiveX-Steuerelementen zu den **Toolbox** Fenster für den leichteren Zugriff.

#### <a name="to-edit-properties-for-an-activex-control"></a>So bearbeiten Sie Eigenschaften für ein ActiveX-Steuerelement

ActiveX-Steuerelemente von unabhängigen Softwareanbietern stammen möglicherweise mit eigenen Eigenschaften und Merkmale. Diese Eigenschaften werden angezeigt, der **Eigenschaften** Fenster, einschließlich jede Eigenschaft, die von den Schreibern, der das ActiveX-Steuerelement erstellte Seiten, in angezeigt werden der **Eigenschaftenseiten** Dialogfelds (zum Anzeigen der  **Eigenschaftenseite** wählen Sie für ein bestimmtes ActiveX-Steuerelement, das **Eigenschaftenseite** Schaltfläche der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window)).

- Wählen Sie die **ActiveX** steuern, und wechseln Sie zum Menü **Ansicht** > **Eigenschaftenseite** zum Anzeigen der Eigenschaften. Nehmen Sie Änderungen an, nach Bedarf auf der Eigenschaftenseite.

   Auf der Eigenschaftenseite für ein ActiveX-Steuerelement, je nach den Eigenschaftenblättern, die als Teil des ActiveX-Steuerelements enthalten sind, werden verschiedene Registerkarten angezeigt.

> [!NOTE]
> Dieses Verfahren gilt für die Verwendung von auf der Seite der zum Bearbeiten von ActiveX-Steuerelemente. Sie können auch navigieren und Bearbeiten von ActiveX-Eigenschaften in der neuen **Eigenschaften** Fenster.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Verwalten von Dialogfeld-Steuerelemente](controls-in-dialog-boxes.md)<br/>
[How To: Layoutsteuerelemente](arrangement-of-controls-on-dialog-boxes.md)<br/>
[Vorgehensweise: Definieren von Zugriffssteuerung und Werten](defining-mnemonics-access-keys.md)<br/>

<!-- excluded links
[Mapping Messages to Functions](../mfc/reference/mapping-messages-to-functions.md)<br/>
[Adding Functionality with Code Wizards](../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Adding a Class](../ide/adding-a-class-visual-cpp.md)<br/>
[Adding a Member Function](../ide/adding-a-member-function-visual-cpp.md)<br/>
[Adding a Member Variable](../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Overriding a Virtual Function](../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC Message Handler](../mfc/reference/adding-an-mfc-message-handler.md)
[Declaring a Variable Based on Your New Control Class](../mfc/reference/declaring-a-variable-based-on-your-new-control-class.md)<br/>
-->