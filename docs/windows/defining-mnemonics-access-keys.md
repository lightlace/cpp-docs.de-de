---
title: "Defining Mnemonics (Access Keys)"
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
  - "access keys [C++], adding"
  - "keyboard shortcuts [C++], controls"
  - "dialog box controls, mnemonics"
  - "access keys [C++], checking"
  - "mnemonics, checking for duplicate"
  - "mnemonics"
  - "mnemonics, dialog box controls"
  - "keyboard shortcuts [C++], uniqueness checking"
  - "Check Mnemonics command"
  - "controls [C++], access keys"
  - "access keys [C++]"
ms.assetid: 60a85435-aa30-4c5c-98b6-42fb045b9eb2
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Defining Mnemonics (Access Keys)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Normalerweise wird der Eingabefokus von einem Benutzer mithilfe der TAB\-TASTE und der PFEILTASTEN der Tastatur in einem Dialogfeld versetzt.  Sie können jedoch eine Zugriffstaste \(einen mnemonischen oder einprägsamen Namen\) definieren, mit der der Benutzer ein Steuerelement durch einen Tastendruck aufrufen kann.  
  
### So definieren Sie eine Zugriffstaste für ein Steuerelement mit einer sichtbaren Beschriftung \(Schaltflächen, Kontrollkästchen und Optionsfelder\)  
  
1.  Wählen Sie das Steuerelement im Dialogfeld aus.  
  
2.  Geben Sie im [Eigenschaftenfenster](../Topic/Properties%20Window.md) unter der Eigenschaft **Beschriftung** einen neuen Namen für das Steuerelement ein, wobei Sie dem Buchstaben, der als Zugriffstaste für das Steuerelement eingesetzt werden soll, ein kaufmännisches Und\-Zeichen \(**&**\) voranstellen.  Beispielsweise `&Radio1`.  
  
3.  Drücken Sie die **EINGABETASTE**.  
  
     Die angezeigte Beschriftung enthält nun einen Unterstrich, der die Zugriffstaste kennzeichnet, z. B. **R**adio1.  
  
### So definieren Sie eine Zugriffstaste für ein Steuerelement ohne sichtbare Beschriftung  
  
1.  Erstellen Sie eine Beschriftung für das Steuerelement, indem Sie ein Steuerelement **Statischer Text** aus der [Toolbox](../Topic/Toolbox.md) verwenden.  
  
2.  Stellen Sie dem Buchstaben, der in der Textfeldbeschriftung als Zugriffstaste fungieren soll, ein kaufmännisches Und\-Zeichen \(**&**\) voran.  
  
3.  Stellen Sie sicher, dass sich das Steuerelement **Statischer Text** in der Aktivierreihenfolge unmittelbar vor dem Steuerelement befindet, das beschriftet werden soll.  
  
 Alle Zugriffstasten innerhalb eines Dialogfelds müssen eindeutig sein.  
  
#### So suchen Sie doppelt vergebene Zugriffstasten  
  
1.  Klicken Sie im Menü **Format** auf **Mnemonik überprüfen**.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
### Anforderungen  
 Win32  
  
## Siehe auch  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [Steuerelemente](../mfc/controls-mfc.md)