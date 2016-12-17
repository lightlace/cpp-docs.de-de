---
title: "Testing a Dialog Box"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "Test Dialog command"
  - "testing, dialog boxes"
  - "dialog boxes, testing"
ms.assetid: 45034ee9-c554-4f4b-8c46-6ddefdee8951
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Testing a Dialog Box
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beim Entwerfen eines Dialogfelds können Sie dessen Laufzeitverhalten simulieren und testen, ohne das Programm zu kompilieren. In diesem Modus können Sie folgende Aufgaben ausführen:  
  
-   Texteingabe, Auswahl aus Kombinationsfeldlisten, Aktivieren oder Deaktivieren von Optionen sowie Auswahl von Befehlen.  
  
-   Testen der Aktivierreihenfolge.  
  
-   Testen der Steuerelementgruppierung \(z. B. von Optionsfeldern und Kontrollkästchen\).  
  
-   Testen der Tastenkombinationen für Steuerelemente im Dialogfeld.  
  
    > [!NOTE]
    >  Verbindungen mit Dialogfeldcode, die mithilfe des Assistenten hergestellt wurden, sind nicht Teil der Simulation.  
  
 Während des Testverfahrens wird ein Dialogfeld normalerweise relativ zum Hauptprogrammfenster angezeigt. Wenn die Dialogfeldeigenschaft "Absolute Ausrichtung" auf "True" gesetzt ist, wird das Dialogfeld relativ zur oberen linken Bildschirmecke angezeigt.  
  
### So testen Sie ein Dialogfeld  
  
1.  Wenn der Dialog\-Editor das aktuelle Fenster ist, wählen Sie in der Menüleiste **Testdialogfeld**, **Format** aus.  
  
2.  Drücken Sie zum Beenden der Simulation ESC, oder wählen Sie in dem von Ihnen getesteten Dialogfeld die Schaltfläche **Schließen** aus.  
  
 Informationen über das Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop\-Apps](../Topic/Resources%20in%20Desktop%20Apps.md).  
  
 Anforderungen  
  
 Win32  
  
## Siehe auch  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [Dialog Editor](../mfc/dialog-editor.md)   
 [Ein\- oder Ausblenden der Symbolleiste des Dialog\-Editors](../mfc/showing-or-hiding-the-dialog-editor-toolbar.md)