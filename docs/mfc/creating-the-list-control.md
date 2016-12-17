---
title: "Erstellen des Listensteuerelements"
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
  - "CListCtrl-Klasse, creating-Steuerelement"
  - "List-Steuerelemente"
ms.assetid: a4cb1729-31b6-4d2b-a44b-367474848a39
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Erstellen des Listensteuerelements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wie das Listensteuerelement \([Verwendung](../mfc/reference/clistctrl-class.md)\) erstellt wird, hängt davon ab, ob Sie das Steuerelement direkt verwenden oder Klasse stattdessen [CListView](../mfc/reference/clistview-class.md) verwenden.  Wenn Sie `CListView` verwenden, erstellt das Framework die Ansicht als Teil seiner Dokument\/Ansichts\-Erstellungssequenz.  Die Listenansicht erstellt, erstellt das Listensteuerelement auch \(die beiden sind dieselben Fakten\).  Das Steuerelement wird in der [OnCreate](../Topic/CWnd::OnCreate.md)\-Handlerfunktion der Ansicht erstellt.  In diesem Fall ist das Steuerelement bereit Ihnen, Elemente, über einen Aufruf [GetListCtrl](../Topic/CListView::GetListCtrl.md) hinzufügen.  
  
### So CListCtrl direkt in einem Dialogfeld verwendet werden  
  
1.  Im Dialog\-Editor fügen Sie einem Listensteuerelement der Dialogfeldvorlagen\-Ressource hinzu.  Geben Sie an seiner Steuerelement\-ID  
  
2.  Verwenden Sie [Assistent zum Hinzufügen von Membervariablen](../ide/adding-a-member-variable-visual-cpp.md), um eine Membervariable vom Typ `CListCtrl` mit der Steuerelementeigenschaft hinzuzufügen.  Sie können diesen Member verwenden, um `CListCtrl`\-Memberfunktionen aufrufen.  
  
3.  Verwenden Sie das Eigenschaftenfenster, die Handlerfunktionen in Dialogklasse für alle Listensteuerelementbenachrichtigungsmeldungen zuzuordnen, die Sie bearbeiten müssen \(siehe [Zuordnungs\-Meldungen auf Funktionen](../mfc/reference/mapping-messages-to-functions.md)\).  
  
4.  In [OnInitDialog](../Topic/CDialog::OnInitDialog.md) legen Sie die Stile für `CListCtrl` fest.  Siehe [Ändern von Listensteuerelement\-Formaten](../mfc/changing-list-control-styles.md).  Damit bestimmen die Art "Ansicht,", das Sie im Steuerelement abrufen, obwohl Sie die Ansicht später ändern können.  
  
### So CListCtrl in einem nondialog Fenster verwenden  
  
1.  Definieren Sie das Steuerelement in der Ansicht oder der Fensterklasse.  
  
2.  Rufen Sie die Memberfunktion [Erstellen](../Topic/CListCtrl::Create.md) des Steuerelements, möglicherweise in [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md), möglicherweise schon in der [OnCreate](../Topic/CWnd::OnCreate.md)\-Handlerfunktion des übergeordneten Fensters auf \(wenn Sie das Steuerelement unterordnen\).  Legen Sie die Stile für das Steuerelement fest.  
  
## Siehe auch  
 [Verwenden von CListCtrl](../mfc/using-clistctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)