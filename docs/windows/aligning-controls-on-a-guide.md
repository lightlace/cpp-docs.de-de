---
title: "Aligning Controls on a Guide | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLUs (dialog units)"
  - "controls [C++], aligning"
  - "Dialog editor, snap to guides"
  - "guides, tick mark interval"
  - "dialog box controls, placement"
  - "guides, aligning controls"
  - "dialog units (DLUs)"
  - "snap to guides (Dialog editor)"
  - "controls [C++], sizing"
  - "tick mark interval in Dialog editor"
  - "controls [C++], snap to guides/grid"
ms.assetid: 17db84ba-5288-4478-be57-afa748aa6447
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Aligning Controls on a Guide
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Ziehpunkte von Steuerelementen werden an Führungslinien ausgerichtet, wenn die Steuerelemente verschoben werden. Führungslinien werden wiederum an Steuerelementen ausgerichtet \(sofern zuvor an der Führungslinie keine Steuerelemente ausgerichtet wurden\).  Wenn Sie eine Führungslinie verschieben, werden die daran ausgerichteten Steuerelemente ebenfalls verschoben.  Bei Steuerelementen, die an mehreren Führungslinien ausgerichtet sind, wird die Größe geändert, sobald eine der Führungslinien verschoben wird.  
  
 Die Teilstriche auf den Linealen, die die Abstände für Führungslinien und Steuerelemente bestimmen, werden in Dialogeinheiten \(DLUs\) definiert.  Eine DLU basiert auf dem im Dialogfeld verwendeten Schriftgrad, normalerweise 8 Punkt MS Shell Dlg.  Eine horizontale DLU entspricht der durchschnittlichen Breite der Dialogfeld\-Schriftart geteilt durch Vier.  Eine vertikale DLU entspricht der durchschnittlichen Höhe der Schriftart geteilt durch Acht.  
  
### So legen Sie die Größe einer Gruppe von Steuerelementen mithilfe von Führungslinien fest  
  
1.  Richten Sie eine Seite des Steuerelements \(bzw. der Steuerelemente\) an einer Führungslinie aus.  
  
2.  Ziehen Sie eine Führungslinie auf die andere Seite des Steuerelements \(bzw. der Steuerelemente\).  
  
     Bei mehreren Steuerelementen passen Sie die Größe der einzelnen Steuerelemente ggf. an, um sie an der zweiten Führungslinie auszurichten.  
  
3.  Verschieben Sie eine der beiden Führungslinien, um die Steuerelementgröße anzupassen.  
  
### So ändern Sie die Abstände von Teilstrichen  
  
1.  Wählen Sie im Menü **Format** die Option **Führungslinieneinstellungen**.  
  
2.  Legen Sie im [Dialogfeld "Führungslinieneinstellungen"](../mfc/guide-settings-dialog-box.md) im Feld **Rasterweite** eine neue Breite und Höhe in Dialogeinheiten \(DLUs\) fest.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Anforderungen  
  
 Win32  
  
## Siehe auch  
 [Dialog Editor States \(Guides and Grids\)](../mfc/dialog-editor-states-guides-and-grids.md)   
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)