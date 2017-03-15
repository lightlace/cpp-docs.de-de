---
title: "Grouping Radio Buttons on a Dialog Box | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.dialog.grouping"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "member variables, adding to radio button groups"
  - "variables, dialog box control member variables"
  - "dialog box controls, grouping radio buttons"
  - "grouping controls"
  - "radio buttons, grouping on dialog boxes"
ms.assetid: 3cc43f9e-56c8-4faa-9930-ce81733c69de
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Grouping Radio Buttons on a Dialog Box
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie einem Dialogfeld Optionsschaltflächen hinzufügen, behandeln Sie sie als Gruppe, indem Sie im Eigenschaftenfenster für die erste Schaltfläche der Gruppe die Eigenschaft „Gruppe“ festlegen. Eine Steuerelement\-ID für das betreffende Optionsfeld wird dann im [Assistent zum Hinzufügen von Membervariablen](../ide/add-member-variable-wizard.md) angezeigt und ermöglicht das Hinzufügen einer Membervariablen zur Gruppe der Optionsfelder.  
  
 Ein Dialogfeld kann mehrere Gruppen von Optionsfeldern enthalten, und jede Gruppe sollte mithilfe der folgenden Prozedur hinzugefügt werden.  
  
### So fügen Sie einem Dialogfeld eine Gruppe von Optionsfeldern hinzu  
  
1.  Wählen Sie das Optionsfeld\-Steuerelement im Fenster [Toolbox](../Topic/Toolbox.md) aus, und klicken Sie an die Stelle im Dialogfeld, an der Sie das Steuerelement platzieren möchten.  
  
2.  Wiederholen Sie Schritt 1, um so viele Optionsfelder hinzuzufügen, wie Sie benötigen. Achten Sie darauf, dass die Optionsfelder in der Gruppe in der Aktivierreihenfolge aufeinander folgen \(weitere Informationen finden Sie unter [Ändern der Aktivierreihenfolge von Steuerelementen](../mfc/changing-the-tab-order-of-controls.md)\).  
  
3.  Legen Sie im Fenster [Eigenschaften](../Topic/Properties%20Window.md) die Eigenschaft **Gruppe** des *ersten* Optionsfelds in der Aktivierreihenfolge auf **Wahr** fest.  
  
     Durch das Ändern der Eigenschaft **Gruppe** auf **Wahr** wird dem Eintrag des Felds im Dialogfeld des Ressourcenscripts die Formatvorlage „WS\_GROUP“ hinzugefügt und so sichergestellt, dass ein Benutzer immer nur ein Optionsfeld in der Feldgruppe aktivieren kann \(wenn der Benutzer auf ein Optionsfeld klickt, werden die anderen in der gleichen Gruppe deaktiviert\).  
  
    > [!NOTE]
    >  Die Eigenschaft **Gruppe** sollte nur für das erste Optionsfeld einer Gruppe auf **Wahr** festgelegt werden. Wenn Sie über weitere Steuerelemente verfügen, die nicht Teil der Optionsfeldgruppe sind, legen Sie die Eigenschaft **Gruppe** des ersten Steuerelements, *das sich außerhalb der Gruppe befindet*, ebenfalls auf **Wahr** fest. Sie können das erste Steuerelement außerhalb der Gruppe schnell ermitteln, indem Sie STRG\+D drücken, um die Aktivierreihenfolge anzuzeigen.  
  
### So fügen Sie eine Membervariable für die Optionsfeldgruppe hinzu  
  
1.  Klicken Sie auf das erste Optionsfeld\-Steuerelement in der Aktivierreihenfolge \(das dominante Steuerelement, dessen Eigenschaft **Gruppe** auf „Wahr“ festgelegt ist\).  
  
2.  Wählen Sie im Kontextmenü **Variable hinzufügen** aus.  
  
3.  Aktivieren Sie im [Assistent zum Hinzufügen von Membervariablen](../ide/add-member-variable-wizard.md) das Kontrollkästchen **Steuerungsvariable**, und aktivieren Sie dann das Optionsfeld **Wert**.  
  
4.  Geben Sie im Feld **Variablenname** einen Namen für die neue Membervariable ein.  
  
5.  Wählen Sie im Listenfeld **Variablentypint** aus, oder geben Sie **int** ein.  
  
6.  Jetzt können Sie Ihren Code ändern, um festzulegen, welches Optionsfeld aus aktiviert angezeigt werden soll. Beispielsweise wählt „m\_radioBox1 \= 0;“ das erste Optionsfeld in der Gruppe aus.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Anforderungen  
  
 Win32  
  
## Siehe auch  
 [Arrangement of Controls on Dialog Boxes](../mfc/arrangement-of-controls-on-dialog-boxes.md)   
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [Steuerelemente](../mfc/controls-mfc.md)