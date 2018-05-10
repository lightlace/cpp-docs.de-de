---
title: Dialog-Editor | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.dialog.dialog
- vc.editors.dialog.F1
dev_langs:
- C++
helpviewer_keywords:
- resource editors, Dialog editor
- editors, dialog boxes
- Dialog editor
- dialog boxes, editing
ms.assetid: d94884ef-2cca-49d8-9b58-775f34848134
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7b8cb99b2002dab3fb04ffa8c5b117a49d23adc1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="dialog-editor"></a>Dialog-Editor
Mit dem Dialog-Editor ist die Bearbeitung und Erstellung von Dialogfeldressourcen möglich. Sie öffnen den Dialog-Editor durch Doppelklicken auf ein Dialogfeld RC-Datei in das Fenster "Ressourcenansicht" (**Ansicht &#124; Ressourcenansicht**). Beachten Sie, dass die Ressourcenansicht in Express-Editionen nicht verfügbar ist.  
  
 Einer der ersten Schritte beim Erstellen eines neuen Dialogfelds (oder einer Dialogfeldvorlage) ist das Hinzufügen von Steuerelementen zum Dialogfeld. Steuerelemente lassen sich im Dialog-Editor so anordnen, dass sie einer bestimmten Größe, Form oder Ausrichtung entsprechen. Außerdem können sie bei der Arbeit innerhalb des Dialogfelds verschoben werden. Steuerelemente lassen sich darüber hinaus problemlos löschen.  
  
 Um ein Dialogfeld später wiederzuverwenden, können Sie es als Vorlage speichern. Auch das Wechseln zwischen dem Entwurf des Dialogfelds und dem Bearbeiten des Codes, mit dem das Feld implementiert wird, ist denkbar einfach.  
  
 Der Dialog-Editor bietet zusätzlich die Möglichkeit, die Eigenschaften einzelner oder mehrerer Steuerelemente zu bearbeiten. Sie können die Aktivierreihenfolge ändern, d. h., die Reihenfolge, in der die Steuerelemente beim Drücken der TAB-TASTE den Fokus erhalten, oder Sie definieren eine Zugriffstaste (Tastenkombination), mit der der Benutzer ein Steuerelement über die Tastatur auswählen kann. Eine Liste der vordefinierten Zugriffstasten finden Sie unter [Zugriffstasten für den Dialog-Editor](../windows/accelerator-keys-for-the-dialog-editor.md).  
  
 Im Dialog-Editor wird außerdem die Verwendung benutzerdefinierter Steuerelemente einschließlich ActiveX-Steuerelementen unterstützt. Außerdem können [Formularansichten](../mfc/reference/cformview-class.md), [Datensatzansichten](../data/record-views-mfc-data-access.md)oder [Dialogleisten](../mfc/dialog-bars.md)bearbeitet werden.  
  
 Beginnend mit Visual Studio 2015, können Dialog-Editor Sie dynamische Layouts definieren, die angeben, wie die Steuerelemente verschoben und Größe ändern, wenn der Benutzer die Größe eines Dialogfelds ändert. Weitere Informationen finden Sie unter [Dynamic Layout](../mfc/dynamic-layout.md).  
  
-   [Erstellen eines neuen Dialogfelds](../windows/creating-a-new-dialog-box.md)  
  
-   [Erstellen eines Dialogfelds, das zur Laufzeit vom Benutzer nicht beendet werden kann](../windows/creating-a-dialog-box-that-users-cannot-exit.md)  
  
-   [Ein- oder Ausblenden der Symbolleiste des Dialog-Editors](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)  
  
-   [Umschalten zwischen Dialogfeld-Editor und Code](../windows/switching-between-dialog-box-controls-and-code.md)  
  
-   [Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)  
  
-   [Hinzufügen von Ereignishandlern für Dialogfeld-Steuerelemente](../windows/adding-event-handlers-for-dialog-box-controls.md)  
  
-   [Testen eines Dialogfelds](../windows/testing-a-dialog-box.md)  
  
-   [Zugriffstasten für den Dialog-Editor](../windows/accelerator-keys-for-the-dialog-editor.md)  
  
-   [Problembehandlung beim Dialog-Editor](../windows/troubleshooting-the-dialog-editor.md)  
  
    > [!TIP]
    >  Im Dialog-Editor können Sie in vielen Fällen durch Klicken mit der rechten Maustaste ein Kontextmenü aufrufen, das die gängigsten Befehle enthält.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Ressourcen-Editoren](../windows/resource-editors.md)   
 [Steuerelemente](../mfc/controls-mfc.md)   
 [Steuerelementklassen](../mfc/control-classes.md)   
 [Dialogfeldklassen](../mfc/dialog-box-classes.md)   
 [Dialogfeld-Steuerelemente und Variablentypen](../ide/dialog-box-controls-and-variable-types.md)

