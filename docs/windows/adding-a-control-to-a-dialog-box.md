---
title: Hinzufügen eines Steuerelements zu einem Dialogfeld (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.dialog.dialog
helpviewer_keywords:
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
ms.assetid: b2a26d19-093f-49ca-93da-fef00dfbb381
ms.openlocfilehash: 92b644769bcbe2649d00ba68437bd474ee06dfcc
ms.sourcegitcommit: b488462a6e035131121e6f32d8f3b108cc798b5e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55293623"
---
# <a name="adding-a-control-to-a-dialog-box-c"></a>Hinzufügen eines Steuerelements zu einem Dialogfeld (C++)

Die **Dialog-Editor** Registerkarte wird angezeigt, der [Fenster "Toolbox"](/visualstudio/ide/reference/toolbox) beim Arbeiten der **Dialogfeld** Editor. Um dem neuen Dialogfeld Steuerelemente hinzuzufügen, ziehen Sie Steuerelemente aus der **Toolbox** an das Dialogfeld, das Sie erstellen. Sie können Sie die Steuerelemente beliebig verschieben oder ihre Größe und Form ändern.

Die Standardsteuerelemente sind in der **Toolbox** sind:

- [Schaltflächen-Steuerelement](../mfc/reference/cbutton-class.md)

- [Kontrollkästchen-Steuerelement](../mfc/reference/styles-used-by-mfc.md#button-styles)

- [Kombinationsfeld-Steuerelement](../mfc/reference/ccombobox-class.md)

- [Steuerelement bearbeiten](../mfc/reference/cedit-class.md)

- Gruppenfeld

- [Listenfeld-Steuerelement](../mfc/reference/clistbox-class.md)

- [Optionsfeld-Steuerelement](../mfc/reference/styles-used-by-mfc.md#button-styles)

- [Statischer Text-Steuerelement](../mfc/reference/cstatic-class.md)

- [Bildsteuerelement](../mfc/reference/cpictureholder-class.md)

- [Rich Edit 2.0-Steuerelement](../mfc/using-cricheditctrl.md)

- [Bildlaufleisten-Steuerelement](../mfc/reference/cscrollbar-class.md)

Die [Windows-Standardsteuerelemente](../mfc/controls-mfc.md) zur Verfügung, in der **Toolbox** bieten gesteigerte Funktionalität in Ihrer Anwendung. Dazu zählen:

- [Schieberegler-Steuerelement](../mfc/slider-control-styles.md)

- [Drehfeld-Steuerelement](../mfc/using-cspinbuttonctrl.md)

- [Statuskontrolle](../mfc/styles-for-the-progress-control.md)

- [Abkürzungstasten-Steuerelement](../mfc/using-a-hot-key-control.md)

- [Listensteuerelement](../mfc/list-control-and-list-view.md)

- [Strukturansicht-Steuerelement](../mfc/tree-control-styles.md)

- [Registerkarten-Steuerelement](../mfc/tab-controls-and-property-sheets.md)

- [Animation-Steuerelement](../mfc/using-an-animation-control.md)

- [Datums-/ Zeitauswahl-Steuerelement](../mfc/creating-the-date-and-time-picker-control.md)

- [Monatskalender-Steuerelement](../mfc/month-calendar-control-examples.md)

- [IP-Adressensteuerelement](../mfc/reference/cipaddressctrl-class.md)

- [Erweitertes Kombinationsfeld-Steuerelement](../mfc/creating-an-extended-combo-box-control.md)

- [Benutzerdefiniertes Steuerelement](custom-controls-in-the-dialog-editor.md)

Sie können benutzerdefinierte Steuerelemente zum Dialogfeld hinzufügen, durch Auswählen der **benutzerdefiniertes Steuerelement** Symbol in der **Toolbox** und ziehen diesen an das Dialogfeld. Hinzufügen einer **Syslink** steuern, fügen Sie ein benutzerdefiniertes Steuerelement hinzu, und Ändern des Steuerelements **Klasse** Eigenschaft **Syslink**. Dies bewirkt, dass die Eigenschaften aktualisieren und Anzeigen der **Syslink** Steuerelementeigenschaften. Informationen zur MFC-Wrapperklasse finden Sie unter [CLinkCtrl](../mfc/reference/clinkctrl-class.md).

Sie können außerdem [ActiveX-Steuerelemente hinzufügen, um das Dialogfeld](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md).

Sie können auch anpassen, die **Toolbox** Fenster zur einfacheren Verwendung. Weitere Informationen finden Sie unter [Verwenden der Toolbox](/visualstudio/ide/using-the-toolbox).

Weitere Informationen zur Verwendung der **RichEdit 1.0** mit MFC zu steuern, finden Sie unter [Verwenden des RichEdit 1.0-Steuerelements mit MFC](../windows/using-the-richedit-1-0-control-with-mfc.md)

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="to-add-a-control-to-a-dialog-box"></a>So fügen Sie ein Steuerelement zu einem Dialogfeld hinzu

1. Stellen Sie sicher, dass das Dialogfeld im Registerkartenformat das aktuelle Dokument im Editor-Fenster darstellt. Wenn ein Dialogfeld mit dem aktuellen Dokument nicht ist, werden Sie nicht angezeigt der **Registerkarte "Dialog-Editor"** in die **Toolbox**.

1. Auf der **Dialog-Editor** Registerkarte die [Fenster "Toolbox"](/visualstudio/ide/reference/toolbox), wählen Sie das Steuerelement, Sie, klicken Sie dann möchten:

   - Wählen Sie im Dialogfeld auf den Speicherort, an der Sie das Steuerelement platzieren möchten. Das Steuerelement wird angezeigt, in dem Sie ausgewählt haben.

       \- oder –

   - Ziehen Sie aus, und legen Sie das Steuerelement aus der **Toolbox** Fenster aus, um den Speicherort in Ihrem Dialogfeld.

       \- oder –

   - Doppelklicken Sie auf das Steuerelement in der **Toolbox** Fenster (es wird im Dialogfeld angezeigt) und dann neu positionieren das Steuerelement, das die gewünschte Position.

## <a name="to-add-multiple-controls"></a>Hinzufügen mehrerer Steuerelemente

1. Halten Sie die **STRG** Schlüssel, wählen Sie ein Steuerelement in der [Fenster "Toolbox"](/visualstudio/ide/reference/toolbox).

1. Version der **STRG** gedrückt, und wählen Sie das Dialogfeld so häufig wie das jeweilige Steuerelement hinzugefügt werden soll.

1. Drücken Sie **Esc** zum Platzieren von Steuerelementen zu beenden.

## <a name="to-size-a-control-while-you-add-it"></a>Die Größe eines Steuerelements, beim Hinzufügen

1. Wählen Sie ein Steuerelement in der [Fenster "Toolbox"](/visualstudio/ide/reference/toolbox).

1. Platzieren Sie den Cursor (die Form eines Fadenkreuzes angezeigt), möchten Sie die linke obere Ecke des neuen Steuerelements auf das Dialogfeld.

1. Wählen Sie aus, halten Sie die Maustaste gedrückt, verankern Sie die linke obere Ecke des Steuerelements im Dialogfeld, und ziehen Sie den Cursor nach rechts und nach unten, bis die gewünschte Größe hat.

   > [!NOTE]
   > Sie können tatsächlich eine der vier Ecken des Steuerelements verankern, die Sie zeichnen können. Dieses Verfahren verwendet die oberen linken Ecke als Beispiel.

1. Lassen Sie die Maustaste los. Das Steuerelement ist in der angegebenen Größe im Dialogfeld angelegt.

   > [!TIP]
   > Sie können die Größe des Steuerelements nach dem Ablegen im Dialogfeld durch das Verschieben der Ziehpunkte am Rand des Steuerelements. Weitere Informationen finden Sie unter [Festlegen der Größe der einzelnen Steuerelementen](../windows/sizing-individual-controls.md).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)<br/>
[Hinzufügen von Ereignishandlern für Dialogfeld-Steuerelemente](../windows/adding-event-handlers-for-dialog-box-controls.md)<br/>
[Dialogfeld-Steuerelemente und Variablentypen](../ide/dialog-box-controls-and-variable-types.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)<br/>
[Steuerelementklassen](../mfc/control-classes.md)<br/>
[Dialogfeldklassen](../mfc/dialog-box-classes.md)<br/>
[Stile des Schiebeleisten-Steuerelements](../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles)<br/>
[Beispiele für RichEdit-Steuerelemente](../mfc/rich-edit-control-examples.md)<br/>
