---
title: "Erstellen des Headersteuerelements | Microsoft Docs"
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
  - "CHeaderCtrl-Klasse, Erstellen"
  - "Headersteuerelemente, Erstellen"
ms.assetid: 7864d9d2-4a2c-4622-b58b-7b110a1e28d2
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Erstellen des Headersteuerelements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Header\-Steuerelement ist nicht direkt im Dialog\-Editor verfügbar \(obwohl Sie kein Listensteuerelement hinzufügen können, das ein Header\-Steuerelement enthält\).  
  
### So ein Header\-Steuerelement in einem Dialogfeld ablegen  
  
1.  Betten Sie manuell eine Membervariable des Typs [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md) in der Dialogfeldklasse ein.  
  
2.  In [OnInitDialog](../Topic/CDialog::OnInitDialog.md) erstellen Sie und legen Sie die Stile für `CHeaderCtrl` fest, positionieren Sie es und zeigen Sie sie an.  
  
3.  Fügen Sie Elemente dem Header\-Steuerelement hinzu.  
  
4.  Verwenden Sie das Eigenschaftenfenster, die Handlerfunktionen in Dialogklasse für alle Header\-Steuerelement\-Benachrichtigungsmeldungen zuzuordnen, die Sie bearbeiten müssen \(siehe [Zuordnungs\-Meldungen auf Funktionen](../mfc/reference/mapping-messages-to-functions.md)\).  
  
### So ein Header\-Steuerelement in eine Ansicht \(kein\) ablegen CListView  
  
1.  Betten [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md) Sie ein Objekt in der Ansichtsklasse ein.  
  
2.  Formatieren Sie, positionieren Sie und zeigen Sie das Header\-Steuerelement\-Fenster in der Memberfunktion [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) der Ansicht an.  
  
3.  Fügen Sie Elemente dem Header\-Steuerelement hinzu.  
  
4.  Verwenden Sie das Eigenschaftenfenster, die Handlerfunktionen in der Ansichtsklasse für alle Header\-Steuerelement\-Benachrichtigungsmeldungen zuzuordnen, die Sie bearbeiten müssen \(siehe [Zuordnungs\-Meldungen auf Funktionen](../mfc/reference/mapping-messages-to-functions.md)\).  
  
 In jedem Fall ist das eingebettete Steuerelementobjekt erstellt, wenn die Ansicht oder das gleichzeitig erstellt wird.  Anschließend müssen Sie [CHeaderCtrl::Create](../Topic/CHeaderCtrl::Create.md) aufrufen, um das Steuerfenster zu erstellen.  Um das Steuerelement zu positionieren, rufen Sie [CHeaderCtrl::Layout](../Topic/CHeaderCtrl::Layout.md) auf die ursprüngliche Größe des Steuerelements und positionieren und [SetWindowPos](../Topic/CWnd::SetWindowPos.md) zu ermitteln um die Position festlegen, die Sie benötigen.  Fügen Sie dann Elemente hinzu, wie in [Hinzufügen von Elementen zum Header\-Steuerelement](../mfc/adding-items-to-the-header-control.md) beschrieben.  
  
 Weitere Informationen finden Sie im [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] unter [Erstellen eines Header\-Steuerelements](http://msdn.microsoft.com/library/windows/desktop/bb775238).  
  
## Siehe auch  
 [Verwenden von CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)