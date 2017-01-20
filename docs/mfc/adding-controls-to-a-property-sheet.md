---
title: "Hinzuf&#252;gen von Steuerelementen zu einem Eigenschaftenblatt"
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
  - "Steuerelemente [MFC], Hinzufügen zu Eigenschaftenblättern"
  - "Eigenschaftenblätter, Hinzufügen von Steuerelementen"
ms.assetid: 24ad4c0b-c1db-4850-b9f0-34aae8d74571
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Hinzuf&#252;gen von Steuerelementen zu einem Eigenschaftenblatt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Standardmäßig ordnet einem Eigenschatenblatt Fensterbereich für die Eigenschaftenseiten, den Registerkartenindex und OK, Löschen zu und wendet Schaltflächen. \(Nicht modale Eigenschaftenblatt A hat nicht OK, bricht ab und wendet Schaltflächen.\) Sie können andere Steuerelemente dem Eigenschaftenblatt hinzu.  Dem Benutzer anzuzeigen Sie können beispielsweise ein Aktualisierung auf der rechten Seite des Eigenschaftenseitenbereichs hinzufügen, um, wie die aktuellen Einstellungen angezeigt würden, wie wenn sie zu einem externen Objekt angewendet werden.  
  
 Sie können Steuerelemente zum Eigenschaftenblattdialogfeld im `OnCreate`\-Handler hinzufügen.  Zuvorkommende zusätzliche Steuerelemente erfordert normalerweise zum Erweitern der Größe des Eigenschaftenblattdialogfelds.  Nach Abruf der Basisklasse **CPropertySheet::OnCreate** aufgerufen hat, erweitern Sie [GetWindowRect](../Topic/CWnd::GetWindowRect.md) aufrufen, um die Breite und die Höhe des derzeit zugeordneten Eigenschaftenblattfensters abzurufen, die Abmessungen des Rechtecks und rufen [MoveWindow](../Topic/CWnd::MoveWindow.md) auf, um die Größe des Eigenschaftenblattfensters zu ändern.  
  
## Siehe auch  
 [Eigenschaftenblätter](../mfc/property-sheets-mfc.md)   
 [CPropertyPage Class](../mfc/reference/cpropertypage-class.md)   
 [CPropertySheet Class](../mfc/reference/cpropertysheet-class.md)