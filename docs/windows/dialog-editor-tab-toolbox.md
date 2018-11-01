---
title: Registerkarte "Dialog-Editor", Toolbox (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- Toolbox [C++], Dialog Editor tab
- controls [C++], types
- syslink controls in dialog boxes
- custom controls [C++], dialog boxes
- controls [C++], standard
- Dialog Editor [C++], creating controls
- controls [C++], adding to dialog boxes
ms.assetid: 253885c2-dcb9-4d8e-ac9b-805ea31cbf5e
ms.openlocfilehash: ee5ee95f22c9cbcbde1d6c8b9ba1646f979697a6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515231"
---
# <a name="dialog-editor-tab-toolbox-c"></a>Registerkarte "Dialog-Editor", Toolbox (C++)

Die **Dialog-Editor** Registerkarte wird angezeigt, der [Fenster "Toolbox"](/visualstudio/ide/reference/toolbox) beim Arbeiten der **Dialogfeld** Editor. Um dem neuen Dialogfeld Steuerelemente hinzuzufügen, ziehen Sie Steuerelemente aus der **Toolbox** an das Dialogfeld, das Sie erstellen (Weitere Informationen finden Sie unter [Hinzufügen eines Steuerelements zu einem Dialogfeld](adding-a-control-to-a-dialog-box.md)). Sie können Sie die Steuerelemente beliebig verschieben oder ihre Größe und Form ändern.

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

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Steuerelemente](../mfc/controls-mfc.md)<br/>
[Steuerelementklassen](../mfc/control-classes.md)<br/>
[Dialogfeldklassen](../mfc/dialog-box-classes.md)<br/>
[Stile des Schiebeleisten-Steuerelements](../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles)<br/>
[Beispiele für RichEdit-Steuerelemente](../mfc/rich-edit-control-examples.md)<br/>
[Hinzufügen von Ereignishandlern für Dialogfeld-Steuerelemente](../windows/adding-event-handlers-for-dialog-box-controls.md)<br/>
[Dialogfeld-Steuerelemente und Variablentypen](../ide/dialog-box-controls-and-variable-types.md)