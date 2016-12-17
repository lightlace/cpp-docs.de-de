---
title: "Methoden zum Erstellen einer Statusleiste"
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
  - "CStatusBar-Klasse, kontra CStatusBarCtrl"
  - "CStatusBarCtrl-Klasse, Erstellen"
  - "CStatusBarCtrl-Klasse, kontra CStatusBar"
  - "Methoden [MFC]"
  - "Methoden [MFC], Erstellen von Statusleisten"
  - "Statusleisten, Erstellen"
ms.assetid: 9aeaf290-7099-4762-a5ba-9c26705333c9
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Methoden zum Erstellen einer Statusleiste
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC stellt zwei Klassen, um Statusleisten zu erstellen: [CStatusBar](../mfc/reference/cstatusbar-class.md) und [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) \(das die API des allgemeinen Windows\-Steuerelements umschließt\).  `CStatusBar` werden alle Funktionen der Statusleistengemeinsamen allgemeinen ToolTip\-Steuerelement, interagiert diese automatisch in Menüs und Symbolleisten ein, und sie behandelt viele der erforderlichen Einstellungen und Strukturen der allgemeinen Steuerelement für Sie; Allerdings ist die resultierende ausführbare Datei größer normalerweise als die, die mit `CStatusBarCtrl` erstellt wird, verwendet.  
  
 `CStatusBarCtrl` führt i eine kleinere ausführbare Datei, und ziehen Sie es möglicherweise vor, eine `CStatusBarCtrl` zu verwenden, wenn Sie nicht beabsichtigen, die Statusleiste in die MFC\-Architektur zu integrieren.  Wenn Sie planen, `CStatusBarCtrl` verwenden und die Statusleiste in die MFC\-Architektur zu integrieren, müssen Sie zusätzliche darauf achten, um StatusBar\-Steuerelement\-Manipulationen zu MFC mitzuteilen.  Diese Kommunikation ist nicht schwierig; ist es jedoch weitere Arbeitschritte, die nicht erforderlich ist, wenn Sie `CStatusBar` verwenden.  
  
 Visual C\+\+ bietet zwei Möglichkeiten, die Statusleistengemeinsame allgemeinen ToolTip\-Steuerelement zu nutzen.  
  
-   Erstellen Sie die Statusleiste mit `CStatusBar`, und rufen Sie anschließend [CStatusBar::GetStatusBarCtrl](../Topic/CStatusBar::GetStatusBarCtrl.md) auf, um den Zugriff auf den `CStatusBarCtrl`\-Memberfunktionen abzurufen.  
  
-   Erstellen Sie die Statusleiste mit [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)\-Konstruktors.  
  
 Jede Methode gibt Ihnen Zugriff zu Memberfunktionen des StatusBar\-Steuerelements.  Wenn Sie `CStatusBar::GetStatusBarCtrl` aufrufen, wird ein Verweis auf ein `CStatusBarCtrl`\-Objekt zurück, sodass Sie alle verwenden festlegen von Memberfunktionen.  Siehe [CStatusBar](../mfc/reference/cstatusbar-class.md) zu Informationen über das Erstellen und das Erstellen einer Statusleiste mit `CStatusBar`.  
  
## Siehe auch  
 [Verwenden von CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)