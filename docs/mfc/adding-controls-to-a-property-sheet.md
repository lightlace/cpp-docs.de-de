---
title: "Hinzuf&#252;gen von Steuerelementen zu einem Eigenschaftenblatt | Microsoft Docs"
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
  - "Steuerelemente [MFC], Hinzufügen zu Eigenschaftenblättern"
  - "Eigenschaftenblätter, Hinzufügen von Steuerelementen"
ms.assetid: 24ad4c0b-c1db-4850-b9f0-34aae8d74571
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Hinzuf&#252;gen von Steuerelementen zu einem Eigenschaftenblatt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Standardmäßig ordnet einem Eigenschatenblatt Fensterbereich für die Eigenschaftenseiten, den Registerkartenindex und OK, Löschen zu und wendet Schaltflächen. \(Nicht modale Eigenschaftenblatt A hat nicht OK, bricht ab und wendet Schaltflächen.\) Sie können andere Steuerelemente dem Eigenschaftenblatt hinzu.  Dem Benutzer anzuzeigen Sie können beispielsweise ein Aktualisierung auf der rechten Seite des Eigenschaftenseitenbereichs hinzufügen, um, wie die aktuellen Einstellungen angezeigt würden, wie wenn sie zu einem externen Objekt angewendet werden.  
  
 Sie können Steuerelemente zum Eigenschaftenblattdialogfeld im `OnCreate`\-Handler hinzufügen.  Zuvorkommende zusätzliche Steuerelemente erfordert normalerweise zum Erweitern der Größe des Eigenschaftenblattdialogfelds.  Nach Abruf der Basisklasse **CPropertySheet::OnCreate** aufgerufen hat, erweitern Sie [GetWindowRect](../Topic/CWnd::GetWindowRect.md) aufrufen, um die Breite und die Höhe des derzeit zugeordneten Eigenschaftenblattfensters abzurufen, die Abmessungen des Rechtecks und rufen [MoveWindow](../Topic/CWnd::MoveWindow.md) auf, um die Größe des Eigenschaftenblattfensters zu ändern.  
  
## Siehe auch  
 [Eigenschaftenblätter](../mfc/property-sheets-mfc.md)   
 [CPropertyPage Class](../mfc/reference/cpropertypage-class.md)   
 [CPropertySheet Class](../mfc/reference/cpropertysheet-class.md)