---
title: "Changing the Tab Order of Controls"
ms.custom: na
ms.date: "12/14/2016"
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
  - "controls [C++], tab order"
  - "focus, tab order"
  - "tab controls, tab order"
  - "Tabstop property for controls"
  - "controls [C++], focus"
  - "dialog box controls, tab order"
ms.assetid: e2cee764-4367-42d7-9563-65a68f76f5ff
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Changing the Tab Order of Controls
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Aktivierreihenfolge ist die Reihenfolge, in der der Eingabefokus durch Drücken der TAB\-TASTE innerhalb des Dialogfelds von einem Steuerelement zum nächsten versetzt wird.  Die Aktivierreihenfolge verläuft in einem Dialogfeld in der Regel von links nach rechts und von oben nach unten.  Jedes Steuerelement verfügt über eine Eigenschaft **Tabstopp**, über die festgelegt wird, ob ein Steuerelement den Eingabefokus erhält.  
  
### So legen Sie den Eingabefokus für ein Steuerelement fest  
  
1.  Wählen Sie im [Eigenschaftenfenster](../Topic/Properties%20Window.md) in der **Tabstop**\-Eigenschaft **True** oder **False** aus.  
  
 Auch Steuerelemente, deren Tabstop\-Eigenschaft nicht auf True festgelegt ist, müssen in der Aktivierreihenfolge enthalten sein.  Dies ist z. B. bei der [Definition von Zugriffstasten](../mfc/defining-mnemonics-access-keys.md) für Steuerelemente von Bedeutung, die keine Beschriftung haben.  Statischer Text mit einer Zugriffstaste für ein zugehöriges Steuerelement muss sich in der Aktivierreihenfolge unmittelbar vor dem zugehörigen Steuerelement befinden.  
  
> [!NOTE]
>  Wenn das Dialogfeld überlappende Steuerelemente enthält, kann sich beim Ändern der Aktivierreihenfolge die Anzeige der Steuerelemente ändern.  Steuerelemente, die weiter hinten in der Aktivierreihenfolge aufgeführt sind, werden immer im Vordergrund vor eventuell überlappenden Steuerelementen angezeigt, die sich weiter vorne in der Aktivierreihenfolge befinden.  
  
#### So zeigen Sie die aktuelle Aktivierreihenfolge für alle Steuerelemente in einem Dialogfeld an  
  
1.  Klicken Sie im Menü **Format** auf **Aktivierreihenfolge**.  
  
 \- oder \-  
  
-   Drücken Sie STRG\+D.  
  
#### So ändern Sie die Aktivierreihenfolge für alle Steuerelemente in einem Dialogfeld  
  
1.  Klicken Sie im Menü **Format** auf **Aktivierreihenfolge**.  
  
     Die Position eines Steuerelements in der aktuellen Aktivierreihenfolge ist anhand einer Zahl in der oberen linken Ecke des Steuerelements erkennbar.  
  
2.  Legen Sie die Aktivierreihenfolge fest, indem Sie in der Reihenfolge auf die einzelnen Steuerelemente klicken, in der sie durch Drücken der TAB\-TASTE aufgerufen werden sollen.  
  
3.  Drücken Sie die **EINGABETASTE**, um den Modus **Aktivierreihenfolge** zu beenden.  
  
    > [!TIP]
    >  Nachdem Sie diesen Modus aufgerufen haben, können Sie die Änderungsfunktion für die Aktivierreihenfolge durch Drücken der ESC\- oder EINGABETASTE wieder deaktivieren.  
  
#### So ändern Sie die Aktivierreihenfolge für zwei oder mehrere Steuerelemente  
  
1.  Wählen Sie im Menü **Format** die Option **Aktivierreihenfolge**.  
  
2.  Geben Sie an, ab welchem Steuerelement die Reihenfolge geändert werden soll.  Halten Sie dazu die **STRG**\-TASTE gedrückt, und klicken Sie auf das Steuerelement, das sich vor dem ersten Steuerelement befindet, dessen Reihenfolge geändert werden soll.  
  
     Wenn Sie z. B. die Reihenfolge der Steuerelemente 7 bis 9 ändern möchten, halten Sie STRG gedrückt und markieren zuerst Steuerelement 6.  
  
    > [!NOTE]
    >  Um ein bestimmtes Steuerelement auf Nummer 1 \(erstes Steuerelement in der Aktivierreihenfolge\) festzulegen, doppelklicken Sie auf das Steuerelement.  
  
3.  Lassen Sie die STRG\-TASTE los, und klicken Sie dann in der Reihenfolge auf die Steuerelemente, in der der Fokus durch Drücken der TAB\-TASTE versetzt werden soll.  
  
4.  Drücken Sie die **EINGABETASTE**, um den Modus **Aktivierreihenfolge** zu beenden.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
### Anforderungen  
 Win32  
  
## Siehe auch  
 [Arrangement of Controls on Dialog Boxes](../mfc/arrangement-of-controls-on-dialog-boxes.md)   
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [Steuerelemente](../mfc/controls-mfc.md)