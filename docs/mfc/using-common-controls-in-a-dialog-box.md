---
title: "Verwenden von Standardsteuerelementen in einem Dialogfeld"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Allgemeine Steuerelemente [C++], in Dialogfeldern"
  - "Dialogfeldsteuerelemente [C++], Allgemeine Steuerelemente"
  - "Allgemeine Windows-Steuerelemente [C++], in Dialogfeldern"
ms.assetid: 17713caf-09f8-484a-bf54-5f48bf09cce9
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden von Standardsteuerelementen in einem Dialogfeld
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die allgemeinen Windows\-Steuerelemente können in [Dialogfelder](../mfc/dialog-boxes.md), in den Formularansichten, mit Datensatzansichten und in jedem anderen Fenster auf einer Dialogfeldvorlage verwendet werden.  In der folgenden Prozedur, unwesentlichen Änderungen, funktioniert auch für Formulare.  
  
## Prozeduren  
  
#### So eine freigegebene Steuerelemente in einem Dialogfeld verwendet werden  
  
1.  Speichern Sie das Steuerelement auf der Dialogfeldvorlage [mithilfe des Dialog\-Editors](../mfc/using-the-dialog-editor-to-add-controls.md).  
  
2.  Fügen Sie der Dialogfeldklasse eine Membervariable hinzu, die das Steuerelement darstellt.  Im Dialogfeld **Membervariable hinzufügen** Überprüfen Sie **Steuerelementvariable** und stellen Sie sicher, dass **Steuerelement** für **Kategorie** ausgewählt wird.  
  
3.  Wenn die Bereitstellung diese sehr häufig vorkommende Steuerelement handelt, die dem Programm typisiert ist, deklarieren Sie zusätzliche Membervariable in Dialogklasse, um diese Eingabewerte zu behandeln.  
  
    > [!NOTE]
    >  Sie können dieser Membervariablen mithilfe des Kontextmenüs in der Klassenansicht hinzu \(siehe [Hinzufügen einer Membervariablen](../ide/adding-a-member-variable-visual-cpp.md)\).  
  
4.  In [OnInitDialog](../Topic/CDialog::OnInitDialog.md) für die Dialogfeldklasse, legen Sie die ursprünglichen Bedingungen für die sehr häufig vorkommende Steuerelement fest.  Verwenden der Membervariable erstellte im vorherigen Schritt, verwendet die Memberfunktionen, um Anfangswert und andere Einstellungen festzulegen.  Siehe die folgenden Beschreibungen der Steuerelemente für Details zu Einstellungen.  
  
     Sie können [Dialogdatenaustausch](../mfc/dialog-data-exchange-and-validation.md) \(DDX\) verwenden um Steuerelemente in einem Dialogfeld zu initialisieren.  
  
5.  In den Handlern für Steuerelemente im Dialogfeld, verwenden Sie die Membervariable, das Steuerelement zu bearbeiten.  Siehe die folgenden Beschreibungen der Steuerelemente Details darüber Methoden.  
  
    > [!NOTE]
    >  Die Membervariable vorhanden, solange nur das Dialogfeld selbst vorhanden ist.  Sie sind nicht in der Lage, das Steuerelement für Eingabewerte abzufragen, nachdem das Dialogfeld geschlossen wurde.  Um mit Eingabewerten eines allgemeinen Steuerelements arbeiten, überschreiben Sie `OnOK` in der Dialogfeldklasse.  In der Überschreibung können Sie das Steuerelement für Eingabewerte ab und speichern Sie diese Werte in die Membervariablen der Dialogfeldklasse.  
  
    > [!NOTE]
    >  Sie können den Dialogdatenaustausch auch verwenden, um Werte von Steuerelementen in einem Dialogfeld abzurufen oder festzulegen.  
  
## Hinweise  
 Die Einführung von einer allgemeinen Steuerelemente zu einem Dialogfeld wird das Dialogfeld, nicht mehr funktionieren.  Siehe [Adding Controls to a Dialog Causes the Dialog to No Longer Function](../mfc/adding-controls-to-a-dialog-causes-the-dialog-to-no-longer-function.md) weitere Informationen über das Behandeln dieser Situation.  
  
## Was möchten Sie tun?  
  
-   [Fügen Sie Steuerelemente einem Dialogfeld von Hand mit anstelle des Dialogfelds hinzu](../mfc/adding-controls-by-hand.md)  
  
-   [Leiten Sie My Steuerelement von einem der Standardallgemeinen windows\-steuerelemente](../mfc/deriving-controls-from-a-standard-control.md)  
  
-   [Verwenden Sie eine sehr häufig vorkommende Steuerelement als untergeordnetes Fenster](../mfc/using-a-common-control-as-a-child-window.md)  
  
-   [Rufen Sie Benachrichtigungsmeldungen von einem Steuerelement](../mfc/receiving-notification-from-common-controls.md)  
  
-   [Verwenden Sie den Dialogdatenaustausch \(DDX\)](../mfc/dialog-data-exchange-and-validation.md)  
  
## Siehe auch  
 [Erstellen und Verwenden von Steuerelementen](../mfc/making-and-using-controls.md)   
 [Steuerelemente](../mfc/controls-mfc.md)