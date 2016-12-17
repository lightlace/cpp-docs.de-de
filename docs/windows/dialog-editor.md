---
title: "Dialog Editor"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.editors.dialog.dialog"
  - "vc.editors.dialog.F1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resource editors, Dialog editor"
  - "editors, dialog boxes"
  - "Dialog editor"
  - "dialog boxes, editing"
ms.assetid: d94884ef-2cca-49d8-9b58-775f34848134
caps.latest.revision: 15
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Dialog Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit dem Dialog\-Editor ist die Bearbeitung und Erstellung von Dialogfeldressourcen möglich. Sie öffnen den Dialog\-Editor, indem Sie im Fenster "Ressourcenansicht" auf die RC\-Datei eines Dialogfelds doppelklicken \(**Ansicht &#124; Ressourcenansicht**\). Beachten Sie, dass die Ressourcenansicht in Express\-Editionen nicht verfügbar ist.  
  
 Einer der ersten Schritte beim Erstellen eines neuen Dialogfelds \(oder einer Dialogfeldvorlage\) ist das Hinzufügen von Steuerelementen zum Dialogfeld. Steuerelemente lassen sich im Dialog\-Editor so anordnen, dass sie einer bestimmten Größe, Form oder Ausrichtung entsprechen. Außerdem können sie bei der Arbeit innerhalb des Dialogfelds verschoben werden. Steuerelemente lassen sich darüber hinaus problemlos löschen.  
  
 Um ein Dialogfeld später wiederzuverwenden, können Sie es als Vorlage speichern. Auch das Wechseln zwischen dem Entwurf des Dialogfelds und dem Bearbeiten des Codes, mit dem das Feld implementiert wird, ist denkbar einfach.  
  
 Der Dialog\-Editor bietet zusätzlich die Möglichkeit, die Eigenschaften einzelner oder mehrerer Steuerelemente zu bearbeiten. Sie können die Aktivierreihenfolge ändern, d. h., die Reihenfolge, in der die Steuerelemente beim Drücken der TAB\-TASTE den Fokus erhalten, oder Sie definieren eine Zugriffstaste \(Tastenkombination\), mit der der Benutzer ein Steuerelement über die Tastatur auswählen kann. Eine Liste der vordefinierten Zugriffstasten finden Sie unter [Zugriffstasten für den Dialog\-Editor](../mfc/accelerator-keys-for-the-dialog-editor.md).  
  
 Im Dialog\-Editor wird außerdem die Verwendung benutzerdefinierter Steuerelemente einschließlich ActiveX\-Steuerelementen unterstützt. Außerdem können [Formularansichten](../mfc/reference/cformview-class.md), [Datensatzansichten](../data/record-views-mfc-data-access.md) oder [Dialogleisten](../mfc/dialog-bars.md) bearbeitet werden.  
  
 Ab [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)] können Sie mit dem Dialog\-Editor dynamische Layouts definieren, die angeben, wie die Steuerelemente verschoben und vergrößert bzw. verkleinert werden, wenn der Benutzer die Größe eines Dialogfelds ändert. Weitere Informationen finden Sie unter [Dynamisches Layout](../mfc/dynamic-layout.md).  
  
-   [Erstellen eines neuen Dialogfelds](../mfc/creating-a-new-dialog-box.md)  
  
-   [Erstellen eines Dialogfelds, das zur Laufzeit vom Benutzer nicht beendet werden kann](../mfc/creating-a-dialog-box-that-users-cannot-exit.md)  
  
-   [Ein\- oder Ausblenden der Symbolleiste des Dialog\-Editors](../mfc/showing-or-hiding-the-dialog-editor-toolbar.md)  
  
-   [Umschalten zwischen Dialogfeld\-Editor und Code](../mfc/switching-between-dialog-box-controls-and-code.md)  
  
-   [Steuerelemente in Dialogfeldern](../mfc/controls-in-dialog-boxes.md)  
  
-   [Hinzufügen von Ereignishandlern für Dialogfeld\-Steuerelemente](../mfc/adding-event-handlers-for-dialog-box-controls.md)  
  
-   [Testen eines Dialogfelds](../mfc/testing-a-dialog-box.md)  
  
-   [Zugriffstasten für den Dialog\-Editor](../mfc/accelerator-keys-for-the-dialog-editor.md)  
  
-   [Problembehandlung beim Dialog\-Editor](../mfc/troubleshooting-the-dialog-editor.md)  
  
    > [!TIP]
    >  Im Dialog\-Editor können Sie in vielen Fällen durch Klicken mit der rechten Maustaste ein Kontextmenü aufrufen, das die gängigsten Befehle enthält.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Anforderungen  
 Win32  
  
## Siehe auch  
 [Resource Editors](../mfc/resource-editors.md)   
 [Steuerelemente](../mfc/controls-mfc.md)   
 [Steuerelementklassen](../mfc/control-classes.md)   
 [Dialogfeldklassen](../mfc/dialog-box-classes.md)   
 [Dialogfeld\-Steuerelemente und Variablentypen](../ide/dialog-box-controls-and-variable-types.md)