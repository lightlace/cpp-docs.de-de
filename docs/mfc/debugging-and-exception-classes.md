---
title: "Debugging- und Ausnahmeklassen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.debug"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Debuggen [MFC], Klassen zum Debuggen"
  - "Debuggen [MFC], Ausnahmeklassen"
ms.assetid: 0d158efd-2e62-452e-9d2a-d3c30dfee7f9
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Debugging- und Ausnahmeklassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Diese Klassen bieten Unterstützung zum Debuggen der dynamische Speicherbelegung und beim Übergeben von Ausnahmeinformationen von der Funktion, in der die Ausnahme zur Funktion ausgelöst wird, in der sie erfasst wird.  
  
 Verwenden Sie Klassen [CDumpContext](../mfc/reference/cdumpcontext-class.md) und [CMemoryState](../mfc/reference/cmemorystate-structure.md) während der Entwicklung, um mit dem Debuggen zu unterstützen, wie in [Debuggings\-MFC\-Anwendungen](../Topic/MFC%20Debugging%20Techniques.md) beschrieben.  Verwenden Sie [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md), um die Klasse eines Objekts zur Laufzeit zu bestimmen, wie im Artikel [Zugreifen auf Ablaufklasseninformationen](../mfc/accessing-run-time-class-information.md) beschrieben.  Die Objekte verwenden `CRuntimeClass`, einer bestimmten Klasse dynamisch zu erstellen.  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)