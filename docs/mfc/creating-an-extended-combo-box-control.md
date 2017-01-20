---
title: "Erstellen eines erweiterten Kombinationsfeld-Steuerelements"
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
  - "CComboBoxEx-Klasse, Erstellen erweiterter Kombinationsfeld-Steuerelemente"
  - "Erweiterte Kombinationsfelder"
  - "Erweiterte Kombinationsfelder, Erstellen"
ms.assetid: a964267e-97b6-4e77-9f89-55bb5c68913f
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Erstellen eines erweiterten Kombinationsfeld-Steuerelements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wie das erweiterte Kombinationsfeld\-Steuerelement erstellt wird, hängt davon ab, ob Sie das Steuerelement in einem Dialogfeld verwenden oder in einem nondialog Fenster erstellen.  
  
### So CComboBoxEx direkt in einem Dialogfeld verwendet werden  
  
1.  Im Dialog\-Editor fügen Sie einen erweiterten Kombinationsfeld\-Steuerelement der Dialogfeldvorlagen\-Ressource hinzu.  Geben Sie an seiner Steuerelement\-ID  
  
2.  Geben Sie alle erforderlichen Formaten, mithilfe des Eigenschaftendialogfelds des erweiterten Kombinationsfeldsteuerelements an.  
  
3.  Verwenden Sie [Assistent zum Hinzufügen von Membervariablen](../ide/adding-a-member-variable-visual-cpp.md), um eine Membervariable vom Typ [CComboBoxEx](../mfc/reference/ccomboboxex-class.md) mit der Steuerelementeigenschaft hinzuzufügen.  Sie können diesen Member verwenden, um `CComboBoxEx`\-Memberfunktionen aufrufen.  
  
4.  Verwenden Sie das Eigenschaftenfenster, die Handlerfunktionen in Dialogklasse für alle erweiterten Kombinationsfeld\-Steuerelement\-Benachrichtigungsmeldungen zuzuordnen, die Sie bearbeiten müssen \(siehe [Zuordnungs\-Meldungen auf Funktionen](../mfc/reference/mapping-messages-to-functions.md)\).  
  
5.  In [OnInitDialog](../Topic/CDialog::OnInitDialog.md) legen Sie alle überzähligen Stile für das `CComboBoxEx`\-Objekt fest.  
  
### So CComboBoxEx in einem nondialog Fenster verwenden  
  
1.  Definieren Sie das Steuerelement in der Ansicht oder der Fensterklasse.  
  
2.  Rufen Sie die Memberfunktion [Erstellen](../Topic/CTabCtrl::Create.md) des Steuerelements, möglicherweise in [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md), möglicherweise schon in der [OnCreate](../Topic/CWnd::OnCreate.md)\-Handlerfunktion des übergeordneten Fensters auf.  Legen Sie die Stile für das Steuerelement fest.  
  
## Siehe auch  
 [Verwenden von CComboBoxEx](../mfc/using-ccomboboxex.md)   
 [Steuerelemente](../mfc/controls-mfc.md)