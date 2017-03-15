---
title: "Methoden zum Erstellen einer Symbolleiste | Microsoft Docs"
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
  - "CToolBar-Klasse, Erstellen von Symbolleisten"
  - "CToolBarCtrl-Klasse, und CToolBar-Klasse"
  - "CToolBarCtrl-Klasse, Erstellen von Symbolleisten"
  - "MFC-Symbolleisten"
  - "Symbolleisten-Steuerelemente [MFC]"
  - "Symbolleisten-Steuerelemente [MFC], Erstellen"
ms.assetid: f19d8d65-d49f-445c-abe8-d47d3e4101c8
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Methoden zum Erstellen einer Symbolleiste
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC stellt zwei Klassen, um Symbolleisten zu erstellen: [CToolBar](../mfc/reference/ctoolbar-class.md) und [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) \(das die API des allgemeinen Windows\-Steuerelements umschließt\).  `CToolBar` werden alle Funktionen der Symbolleistengemeinsamen allgemeinen ToolTip\-Steuerelement, und sie behandelt viele der erforderlichen Einstellungen und Strukturen der allgemeinen Steuerelement für Sie; Allerdings ist die resultierende ausführbare Datei größer normalerweise als die, die mit `CToolBarCtrl` erstellt wird, verwendet.  
  
 `CToolBarCtrl` führt i eine kleinere ausführbare Datei, und ziehen Sie es möglicherweise vor, eine `CToolBarCtrl` zu verwenden, wenn Sie nicht beabsichtigen, Symbolleiste in die MFC\-Architektur zu integrieren.  Wenn Sie planen, `CToolBarCtrl` verwenden und die Symbolleiste in die MFC\-Architektur zu integrieren, müssen Sie zusätzliche darauf achten, um Symbolleisten\-Steuerelement\-Manipulationen zu MFC mitzuteilen.  Diese Kommunikation ist nicht schwierig; ist es jedoch weitere Arbeitschritte, die nicht erforderlich ist, wenn Sie `CToolBar` verwenden.  
  
 Visual C\+\+ bietet zwei Möglichkeiten, die Symbolleistengemeinsame allgemeinen ToolTip\-Steuerelement zu nutzen.  
  
-   Stellen Sie die Symbolleiste mit `CToolBar`, und rufen Sie anschließend [CToolBar::GetToolBarCtrl](../Topic/CToolBar::GetToolBarCtrl.md) auf, um den Zugriff auf den `CToolBarCtrl`\-Memberfunktionen abzurufen.  
  
-   Stellen Sie die Symbolleiste mit [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)\-Konstruktors erstellt.  
  
 Jede Methode gibt Ihnen Zugriff in Memberfunktionen des Symbolleisten\-Steuerelements.  Wenn Sie `CToolBar::GetToolBarCtrl` aufrufen, wird ein Verweis auf ein `CToolBarCtrl`\-Objekt zurück, sodass Sie alle verwenden festlegen von Memberfunktionen.  Siehe [CToolBar](../mfc/reference/ctoolbar-class.md) zu Informationen zum Erstellen und zum Erstellen eine Symbolleiste mit `CToolBar`.  
  
## Siehe auch  
 [Verwenden von CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)