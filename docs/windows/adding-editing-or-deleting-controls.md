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
- controls [C++], troubleshooting
- Dialog Editor [C++], troubleshooting
- dialog boxes [C++], troubleshooting
- InitCommonControls
- RichEdit 1.0 control
- rich edit controls [C++], RichEdit 1.0
ms.assetid: 73cef03f-5c8c-456a-87d1-1458dff185cf
ms.openlocfilehash: 648ac3329409ba221881f75eaa51e1779091b0f0
ms.sourcegitcommit: eb2b34a24e6edafb727e87b138499fa8945f981e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2019
ms.locfileid: "56264867"
---
# <a name="adding-editing-or-deleting-controls"></a>Hinzufügen, Bearbeiten oder Löschen von Steuerelementen

Mithilfe der **Dialogfeld** -Editor die Größe ändern, bearbeiten und löschen Sie die Steuerelemente in Dialogfeldern hinzufügen. Sie können auch die Eigenschaften eines Steuerelements, z. B. die ID, bearbeiten oder ob es sichtbare zur Laufzeit ist.

Die **Dialog-Editor** Registerkarte wird angezeigt, der [Fenster "Toolbox"](/visualstudio/ide/reference/toolbox) beim Arbeiten der **Dialogfeld** Editor. Sie können auch anpassen, die **Toolbox** Fenster zur einfacheren Verwendung. Weitere Informationen finden Sie unter [mithilfe der Toolbox](/visualstudio/ide/using-the-toolbox) und [ein- oder Ausblenden der Fenster "Toolbox"](showing-or-hiding-the-dialog-editor-toolbar.md).

Können Sie das Kontextmenü in der **Dialogfeld** -Editor, um schnell hinzufügen registriert ActiveX-Steuerelemente in einem Dialogfeld aus, und Sie können ActiveX-Steuerelemente zum Hinzufügen der **Toolbox** für den Schnellzugriff.

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

## <a name="known-issue"></a>Bekannte Probleme

Nach dem Hinzufügen einer allgemeinen Steuerelements oder rich-Edit-Steuerelement in einem Dialogfeld an, nicht es angezeigt, wenn Sie Sie das Dialogfeld Testen oder das Dialogfeld selbst wird nicht angezeigt.

Um ein Beispiel für das Problem finden Sie unter:

1. Erstellen Sie eine Win32-Projekts, das die Anwendungseinstellungen ändern, damit Sie eine Windows-Anwendung (keine Konsolen-app erstellen).

1. In [Ressourcenansicht](../windows/resource-view-window.md), doppelklicken Sie auf die RC-Datei.

1. Doppelklicken Sie unter der Dialogfeldoption auf die **zu** Feld.

1. Hinzufügen einer **IP-Adressensteuerelement** auf das Dialogfeld.

1. Speichern und **alles neu erstellen**.

1. Führen Sie das Programm an.

1. In des Dialogfelds **helfen** im Menü klicken Sie auf die **zu** Befehl, kein Dialogfeld angezeigt wird.

Derzeit den **Dialogfeld** Editor nicht Code automatisch zu Ihrem Projekt hinzugefügt werden, wenn Drag & drop die folgenden allgemeinen Steuerelemente oder Rich--Steuerelemente in einem Dialogfeld Edit. Auch Visual Studio bietet Fehler oder Warnung, wenn dieses Problem auftritt. Um das Problem zu beheben, fügen Sie den Code für das Steuerelement manuell hinzu.

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
> Möglicherweise verwenden Sie die aktuelle [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) Klasse mit dem älteren RichEdit 1.0-Steuerelement, aber `CRichEditCtrl` dient nur zur Unterstützung des RichEdit-2.0-Steuerelements. Da RichEdit 1.0 und 2.0 des RichEdit ähnlich sind, funktionieren die meisten Methoden. Beachten Sie jedoch, dass es gibt einige Unterschiede zwischen den Steuerelementen 1.0 und 2.0, sodass einige Methoden möglicherweise nicht ordnungsgemäß oder überhaupt nicht funktionsfähig.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Dialog-Editor](../windows/dialog-editor.md)<br/>
[Steuerelemente in Dialogfeldern](controls-in-dialog-boxes.md)<br/>
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