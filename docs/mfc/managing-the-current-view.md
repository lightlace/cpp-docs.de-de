---
title: "Verwalten der aktuellen Ansicht"
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
  - "aktuelle Ansicht im Rahmenfenster"
  - "deaktivieren von Ansichten"
  - "Rahmenfenster, Aktuelle Ansicht"
  - "OnActivateView-Methode"
  - "Ansichten, Aktivieren"
  - "Ansichten, und OnActivateView-Methode"
  - "Ansichten, Aktuell"
  - "Ansichten, Deaktivieren"
ms.assetid: 0a1cc22d-d646-4536-9ad2-3cb6d7092e4a
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Verwalten der aktuellen Ansicht
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Als Teil der Standardimplementierung von Rahmenfenstern, behält ein Rahmenfenster aktive Ansicht die momentan nachverfolgt.  Wenn das Rahmenfenster mehr als Ansicht enthält, wie beispielsweise in einem unterteilten, ist die aktuelle Ansicht die letzte Ansicht in Verwendung.  Die aktiven Ansicht ist unabhängig des aktiven Fensters in Windows oder im aktuellen Eingabefokus.  
  
 Wenn die aktive Ansicht ändert, benachrichtigt das Framework die aktuelle Ansicht, indem er die [OnActivateView](../Topic/CView::OnActivateView.md)\-Memberfunktion aufruft.  Sie können feststellen, ob die Ansicht aktiviert oder deaktiviert wird, indem `OnActivateView``bActivate`\-Parameter überprüft.  Standardmäßig legt `OnActivateView` den Fokus auf die aktuelle Ansicht auf Aktivierung fest.  Sie können `OnActivateView` überschreiben, um ein spezielles auszuführen, Verarbeitung, wenn die Ansicht deaktiviert oder reaktiviert wird.  Beispielsweise sollten Sie besondere visuelle Hinweise bereitstellen, um die aktive Ansicht von anderen unterscheiden, inaktive Ansichten.  
  
 Ein Rahmenfenster werden Befehle an die aktuelle \(aktive\) Ansicht weiter, wie in [Befehls\-Routing](../mfc/command-routing.md), als Teil des Standardbefehlsroutings beschrieben.  
  
## Siehe auch  
 [Verwenden von Rahmenfenstern](../mfc/using-frame-windows.md)