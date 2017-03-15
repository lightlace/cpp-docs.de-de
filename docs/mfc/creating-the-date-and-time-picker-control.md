---
title: "Erstellen des Steuerelements f&#252;r Datum und Uhrzeit | Microsoft Docs"
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
  - "CDateTimeCtrl-Klasse, Erstellen"
  - "DateTimePicker-Steuerelement [MFC], Erstellen"
ms.assetid: 764ec2fb-98cd-478b-a5f2-d63f0bb12279
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Erstellen des Steuerelements f&#252;r Datum und Uhrzeit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wie das Steuerelement für die Datums\- und Zeitauswahl erstellt wird, hängt davon ab, ob Sie das Steuerelement in einem Dialogfeld verwenden oder in einem nondialog Fenster erstellen.  
  
### So CDateTimeCtrl direkt in einem Dialogfeld verwendet werden  
  
1.  Im Dialog\-Editor fügen Sie einem Steuerelement für die Datums\- und Zeitauswahl der Dialogfeldvorlagen\-Ressource hinzu.  Geben Sie an seiner Steuerelement\-ID  
  
2.  Geben Sie alle erforderlichen Formaten, mithilfe des Eigenschaftendialogfelds des Steuerelements für die Datums\- und Zeitauswahl an.  
  
3.  Verwenden Sie [Assistent zum Hinzufügen von Membervariablen](../ide/adding-a-member-variable-visual-cpp.md), um eine Membervariable vom Typ [CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md) mit der Steuerelementeigenschaft hinzuzufügen.  Sie können diesen Member verwenden, um `CDateTimeCtrl`\-Memberfunktionen aufrufen.  
  
4.  Verwenden Sie das Eigenschaftenfenster, die Handlerfunktionen in Dialogklasse für alle Datum\-Zeit \- Auswahlsteuer\- [Benachrichtigung](../mfc/processing-notification-messages-in-date-and-time-picker-controls.md) Meldungen zuzuordnen, die Sie bearbeiten müssen \(siehe [Zuordnungs\-Meldungen auf Funktionen](../mfc/reference/mapping-messages-to-functions.md)\).  
  
5.  In [OnInitDialog](../Topic/CDialog::OnInitDialog.md) legen Sie alle überzähligen Stile für das `CDateTimeCtrl`\-Objekt fest.  
  
### So CDateTimeCtrl in einem nondialog Fenster verwenden  
  
1.  Deklarieren Sie das Steuerelement in der Ansicht oder der Fensterklasse.  
  
2.  Rufen Sie die Memberfunktion [Erstellen](../Topic/CTabCtrl::Create.md) des Steuerelements, möglicherweise in [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md), möglicherweise schon in der [OnCreate](../Topic/CWnd::OnCreate.md)\-Handlerfunktion des übergeordneten Fensters auf \(wenn Sie das Steuerelement unterordnen\).  Legen Sie die Stile für das Steuerelement fest.  
  
## Siehe auch  
 [Verwenden von CDateTimeCtrl](../mfc/using-cdatetimectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)