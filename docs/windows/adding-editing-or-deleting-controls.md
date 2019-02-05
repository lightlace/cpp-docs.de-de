---
title: Hinzufügen, Bearbeiten oder Löschen von Steuerelementen
ms.date: 11/04/2016
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
ms.assetid: 73cef03f-5c8c-456a-87d1-1458dff185cf
ms.openlocfilehash: b4edb5b7a51e4f6d368759ebc2e05a1cc585f19a
ms.sourcegitcommit: 52c05e10b503e834c443ef11e7ca1987e332f876
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2019
ms.locfileid: "55742751"
---
# <a name="adding-editing-or-deleting-controls"></a>Hinzufügen, Bearbeiten oder Löschen von Steuerelementen

Mithilfe der **Dialogfeld** -Editor die Größe ändern, bearbeiten und löschen Sie die Steuerelemente in Dialogfeldern hinzufügen. Sie können auch die Eigenschaften eines Steuerelements, z. B. die ID, bearbeiten oder ob es sichtbare zur Laufzeit ist.

Die **Dialog-Editor** Registerkarte wird angezeigt, der [Fenster "Toolbox"](/visualstudio/ide/reference/toolbox) beim Arbeiten der **Dialogfeld** Editor. Sie können auch anpassen, die **Toolbox** Fenster zur einfacheren Verwendung. Weitere Informationen finden Sie unter [mithilfe der Toolbox](/visualstudio/ide/using-the-toolbox) und [ein- oder Ausblenden der Fenster "Toolbox"](showing-or-hiding-the-dialog-editor-toolbar.md).

Können Sie das Kontextmenü in der **Dialogfeld** -Editor, um schnell hinzufügen registriert ActiveX-Steuerelemente in einem Dialogfeld aus, und Sie können ActiveX-Steuerelemente zum Hinzufügen der **Toolbox** für den Schnellzugriff.

Die Standardsteuerelemente sind in der **Toolbox** Standardwert Ereignisse sind:

|Steuerelementname|Standardereignis|
|---|---|
|[Schaltflächen-Steuerelement](../mfc/reference/cbutton-class.md)|BN_CLICKED|
|[Kontrollkästchen-Steuerelement](../mfc/reference/styles-used-by-mfc.md#button-styles)|BN_CLICKED|
|[Kombinationsfeld-Steuerelement](../mfc/reference/ccombobox-class.md)|CBN_SELCHANGE|
|[Steuerelement bearbeiten](../mfc/reference/cedit-class.md)|EN_CHANGE-EREIGNIS|
|Gruppenfeld|(Nicht zutreffend)|
|[Listenfeld-Steuerelement](../mfc/reference/clistbox-class.md)|LBN_SELCHANGE|
|[Optionsfeld-Steuerelement](../mfc/reference/styles-used-by-mfc.md#button-styles)|BN_CLICKED|
|[Statischer Text-Steuerelement](../mfc/reference/cstatic-class.md)|(Nicht zutreffend)|
|[Bildsteuerelement](../mfc/reference/cpictureholder-class.md)|(Nicht zutreffend)|
|[Rich Edit 2.0-Steuerelement](../mfc/using-cricheditctrl.md)|EN_CHANGE-EREIGNIS|
|[Bildlaufleisten-Steuerelement](../mfc/reference/cscrollbar-class.md)|NM_THEMECHANGED|

Weitere Informationen zur Verwendung der **RichEdit 1.0** mit MFC zu steuern, finden Sie unter [Verwenden des RichEdit 1.0-Steuerelements mit MFC](../windows/using-the-richedit-1-0-control-with-mfc.md) und [Rich bearbeiten Beispiele für](../mfc/rich-edit-control-examples.md).

Die [Windows-Standardsteuerelemente](../mfc/controls-mfc.md) zur Verfügung, in der **Toolbox** bieten gesteigerte Funktionalität in Ihrer Anwendung. Dazu zählen:

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
|[Benutzerdefiniertes Steuerelement](custom-controls-in-the-dialog-editor.md)|TTN_GETDISPINFO|

Weitere Informationen finden Sie unter [Steuerelementklassen](../mfc/control-classes.md), [Dialogfeldklassen](../mfc/dialog-box-classes.md), und [Stile des Schiebeleisten Steuerelements](../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles).

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="to-add-a-control"></a>Hinzufügen des Steuerelements

Um dem neuen Dialogfeld Steuerelemente hinzuzufügen, ziehen Sie Steuerelemente aus der **Toolbox** an das Dialogfeld, das Sie erstellen. Sie können Sie die Steuerelemente beliebig verschieben oder ihre Größe und Form ändern.

Sie können benutzerdefinierte Steuerelemente zum Dialogfeld hinzufügen, durch Auswählen der **benutzerdefiniertes Steuerelement** Symbol in der **Toolbox** und ziehen diesen an das Dialogfeld. Hinzufügen einer **Syslink** steuern, fügen Sie ein benutzerdefiniertes Steuerelement hinzu, und Ändern des Steuerelements **Klasse** Eigenschaft **Syslink**. Diese Aktion führt dazu, dass die Eigenschaften aktualisieren und Anzeigen der **Syslink** Steuerelementeigenschaften. Informationen zur MFC-Wrapperklasse finden Sie unter [CLinkCtrl](../mfc/reference/clinkctrl-class.md).

### <a name="to-add-a-control-to-a-dialog-box"></a>So fügen Sie ein Steuerelement zu einem Dialogfeld hinzu

1. Stellen Sie sicher, dass das Dialogfeld im Registerkartenformat das aktuelle Dokument im Editor-Fenster darstellt. Wenn ein Dialogfeld mit dem aktuellen Dokument nicht ist, werden Sie nicht angezeigt der **Registerkarte "Dialog-Editor"** in die **Toolbox**.

1. Auf der **Dialog-Editor** Registerkarte die **Toolbox** Fenster, wählen Sie das Steuerelement, Sie, klicken Sie dann möchten:

   Wählen Sie im Dialogfeld auf den Speicherort, an der Sie das Steuerelement platzieren möchten. Das Steuerelement wird angezeigt, in dem Sie ausgewählt haben.

   \- oder –

   Ziehen Sie aus, und legen Sie das Steuerelement aus der **Toolbox** Fenster aus, um den Speicherort in Ihrem Dialogfeld.

   \- oder –

   Doppelklicken Sie auf das Steuerelement in der **Toolbox** Fenster (es wird im Dialogfeld angezeigt) und dann neu positionieren das Steuerelement, das die gewünschte Position.

### <a name="to-add-multiple-controls"></a>Hinzufügen mehrerer Steuerelemente

1. Halten Sie die **STRG** Schlüssel, wählen Sie ein Steuerelement in der **Toolbox** Fenster.

1. Version der **STRG** gedrückt, und wählen Sie das Dialogfeld so häufig wie das jeweilige Steuerelement hinzugefügt werden soll.

1. Drücken Sie **Esc** zum Platzieren von Steuerelementen zu beenden.

### <a name="to-size-a-control-while-you-add-it"></a>Die Größe eines Steuerelements, beim Hinzufügen

1. Wählen Sie ein Steuerelement in der **Toolbox** Fenster.

1. Platzieren Sie den Cursor (die Form eines Fadenkreuzes angezeigt), möchten Sie die linke obere Ecke des neuen Steuerelements auf das Dialogfeld.

1. Wählen Sie aus, halten Sie die Maustaste gedrückt, verankern Sie die linke obere Ecke des Steuerelements im Dialogfeld, und ziehen Sie den Cursor nach rechts und nach unten, bis die gewünschte Größe hat.

   > [!NOTE]
   > Sie können tatsächlich eine der vier Ecken des Steuerelements verankern, die Sie zeichnen können. Dieses Verfahren verwendet die oberen linken Ecke als Beispiel.

1. Lassen Sie die Maustaste los. Das Steuerelement ist in der angegebenen Größe im Dialogfeld angelegt.

   > [!TIP]
   > Sie können die Größe des Steuerelements nach dem Ablegen im Dialogfeld durch das Verschieben der Ziehpunkte am Rand des Steuerelements. Weitere Informationen finden Sie unter [Festlegen der Größe der einzelnen Steuerelementen](../windows/sizing-individual-controls.md).

### <a name="to-add-an-activex-control"></a>Ein ActiveX-Steuerelement hinzufügen

Visual Studio ermöglicht Ihnen das Einfügen von ActiveX-Steuerelementen in Ihr Dialogfeld. Weitere Informationen finden Sie unter [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md) und [ActiveX-Steuerelementcontainer](../mfc/activex-control-containers.md).

Die **ActiveX-Steuerelement einfügen** Dialogfeld können Sie zum Einfügen von ActiveX-Steuerelemente in einem Dialogfeld bei der Verwendung der [Dialog-Editor](../windows/dialog-editor.md). Dieses Dialogfeld enthält die folgenden Eigenschaften:

|Eigenschaft|Beschreibung|
|---|---|
|**ActiveX-Steuerelement**|Zeigt eine Liste von ActiveX-Steuerelementen. Einfügen eines Steuerelements in diesem Dialogfeld keine Wrapperklasse nicht generieren. Wenn Sie eine Wrapperklasse benötigen, verwenden Sie [Klassenansicht](/visualstudio/ide/viewing-the-structure-of-code) erstellen (Weitere Informationen finden Sie unter [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md)). Ein ActiveX-Steuerelement in diesem Dialogfeld angezeigt werden, versuchen Sie die Installation des Steuerelements entsprechend des Anbieters Anweisungen.|
|**Pfad**|Zeigt die Datei, die in der das ActiveX-Steuerelement gefunden wird.|

#### <a name="to-see-the-activex-controls-available"></a>Um die verfügbaren ActiveX-Steuerelemente finden Sie unter

1. Öffnen Sie ein Dialogfeld im Dialog-Editor.

1. Mit der rechten Maustaste an einer beliebigen Stelle im Text des Dialogfelds.

1. Wählen Sie im Kontextmenü den Befehl **ActiveX-Steuerelement einfügen**.

   Die **ActiveX-Steuerelement einfügen** Dialogfeld angezeigt wird, stellt alle ActiveX-Steuerelemente auf Ihrem System. Unten im Dialogfeld wird der Pfad der Datei des ActiveX-Steuerelements angezeigt.

#### <a name="to-add-an-activex-control-to-a-dialog-box"></a>So fügen Sie einem Dialogfeld ein Active X-Steuerelement hinzu

1. In der **ActiveX-Steuerelement einfügen** Dialogfeld Wählen Sie das gewünschte Steuerelement Ihrem Dialogfeld hinzufügen, und wählen Sie **OK**.

   Das Steuerelement wird im Dialogfeld angezeigt, wo Sie es bearbeiten oder Handler für es erstellen können, ganz wie bei jedem anderen Steuerelement.

   > [!NOTE]
   > Sie können ActiveX-Steuerelemente zum Hinzufügen der **Toolbox** Fenster für den leichteren Zugriff.

   > [!CAUTION]
   > Der Vertrieb ist möglicherweise nicht für alle ActiveX-Steuerelemente auf Ihrem System rechtlich zulässig. Informieren Sie sich im Lizenzvertrag für die Software, die die Steuerelemente installiert hat, oder wenden Sie sich an den Hersteller der Software.

## <a name="to-edit-a-control"></a>So bearbeiten Sie ein Steuerelement

### <a name="to-edit-the-properties-of-a-control-or-controls"></a>So bearbeiten Sie die Eigenschaften eines Steuerelements oder-Steuerelemente

1. Wählen Sie das Steuerelement, die, das Sie ändern möchten, klicken Sie im Dialogfeld.

   > [!NOTE]
   > Wenn Sie mehrere Steuerelemente auswählen, können nur die Eigenschaften, die die ausgewählten Steuerelemente gemeinsam bearbeitet werden.

1. In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), ändern Sie die Eigenschaften des Steuerelements.

   > [!NOTE]
   > Beim Festlegen der **Bitmap** -Eigenschaft für eine Schaltfläche, Optionsfeld oder Kontrollkästchen-Steuerelement gleich **"true"**, den Stil BS_BITMAP für das Steuerelement implementiert wird. Weitere Informationen finden Sie unter [Button-Stile](../mfc/reference/styles-used-by-mfc.md#button-styles). Ein Beispiel für eine Bitmap mit einem Steuerelement zuordnen, finden Sie unter [CButton:: SetBitmap](../mfc/reference/cbutton-class.md#setbitmap). Bitmaps werden nicht auf das Steuerelement angezeigt, während Sie auf die **Dialogfeld** Ressourcen-Editor.

### <a name="to-undo-changes-to-the-properties-of-a-control"></a>Um Änderungen an den Eigenschaften eines Steuerelements rückgängig zu machen.

1. Stellen Sie sicher, dass das Steuerelement den Fokus besitzt, der **Dialogfeld** Editor.

1. Wählen Sie **rückgängig zu machen** aus der **bearbeiten** Menü (wenn der Fokus auf das Steuerelement ist nicht die **rückgängig zu machen** Befehl nicht verfügbar).

### <a name="to-edit-properties-for-an-activex-control"></a>So bearbeiten Sie Eigenschaften für ein ActiveX-Steuerelement

ActiveX-Steuerelemente von unabhängigen Softwareanbietern stammen möglicherweise mit eigenen Eigenschaften und Merkmale. Eigenschaften für ActiveX-Steuerelemente werden angezeigt, der **Eigenschaften** Fenster. Darüber hinaus werden alle von den Schreibern, der das ActiveX-Steuerelement erstellten Eigenschaftenseiten angezeigt, der **Eigenschaftenseiten** (Dialogfeld) (Anzeigen der **Eigenschaftenseite** für ein bestimmtes ActiveX-Steuerelement, klicken Sie auf die **Eigenschaftenseite** Schaltfläche der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window)).

Auf der Eigenschaftenseite für ein ActiveX-Steuerelement, je nach den Eigenschaftenblättern, die als Teil des ActiveX-Steuerelements enthalten sind, werden verschiedene Registerkarten angezeigt.

> [!NOTE]
> Das folgende Verfahren gilt für die Verwendung von auf der Seite der zum Bearbeiten von ActiveX-Steuerelemente. Sie können auch navigieren und Bearbeiten von ActiveX-Eigenschaften in der neuen **Eigenschaften** Fenster.

1. Wählen Sie die **ActiveX** Steuerelement.

1. Auf der **Ansicht** , wählen Sie im Menü **Eigenschaftenseite** und ihre Eigenschaften anzuzeigen.

1. Nehmen Sie Änderungen an, nach Bedarf auf der Eigenschaftenseite.

### <a name="to-define-a-member-variable-for-a-non-button-dialog-box-control"></a>So definieren Sie eine Membervariable für ein Dialogfeld-Steuerelement (kein Schaltflächen-Steuerelement)

Mit der folgenden Methode können Sie eine Membervariable für beliebige Dialogfenster-Steuerelemente außer Schaltflächen definieren.

> [!NOTE]
> Dieser Vorgang gilt nur für Dialogfeld-Steuerelemente in einem MFC-Projekt. ATL-Projekte verwenden, sollten die **neue Windows-Meldungen und Ereignishandler** Dialogfeld. Weitere Informationen finden Sie unter [Nachricht Typen Benutzeroberflächen-Objekten zugeordneten](../mfc/reference/message-types-associated-with-user-interface-objects.md), [Bearbeiten eines Meldungshandlers](../mfc/reference/editing-a-message-handler.md), und [Definieren eines Meldungshandlers für eine Nachricht wiedergegeben](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md).

1. In der [Dialog-Editor](../windows/dialog-editor.md), wählen Sie ein Steuerelement.

1. Beim Drücken der **STRG** Schlüssel, doppelklicken Sie auf das Dialogfeld-Steuerelement.

   Die [Assistenten zum Hinzufügen von Membervariablen](../ide/add-member-variable-wizard.md) angezeigt wird.

1. Geben Sie die entsprechende Informationen in den **Hinzufügen von Membervariablen** Assistenten. Weitere Informationen finden Sie unter [Dialogdatenaustausch](../mfc/dialog-data-exchange.md).

1. Wählen Sie **OK** zum Zurückgeben der **Dialogfeld** Editor.

   > [!TIP]
   > Doppelklicken Sie auf das Steuerelement, um von einem Dialogfeld-Steuerelement zu seinem vorhandenen Handler zu wechseln.

Sie können auch die **Membervariablen** Registerkarte die [MFC-Klassenassistent](../mfc/reference/mfc-class-wizard.md) neue Membervariablen für eine angegebene Klasse hinzufügen und Anzeigen der Membervariablen, die bereits definiert wurden.

## <a name="to-delete-a-control"></a>So löschen Sie ein Steuerelement

Wählen Sie in das Dialogfeld, das Steuerelement, und drücken Sie die **löschen** Schlüssel.

   \- oder –

Auf der **bearbeiten** , wählen Sie im Menü **löschen**.

   > [!TIP]
   > Bei der Verwendung der **Dialogfeld** -Editor in vielen Fällen können Sie die rechte Maustaste gedrückt, um ein Kontextmenü mit häufig verwendeten Befehlen anzuzeigen klicken.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Steuerelemente in Dialogfeldern](controls-in-dialog-boxes.md)<br/>
[Dialogfeld-Steuerelemente und Variablentypen](../ide/dialog-box-controls-and-variable-types.md)<br/>
[Ressourcendateien](../windows/resource-files-visual-studio.md)<br/>

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
