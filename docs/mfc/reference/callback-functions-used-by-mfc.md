---
title: "Von MFC verwendete R&#252;ckruffunktionen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.functions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Rückruffunktionen"
  - "Rückruffunktionen, MFC"
  - "Funktionen [C++], Rückruf"
  - "MFC, Rückruffunktionen"
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Von MFC verwendete R&#252;ckruffunktionen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Drei Rückruffunktionen werden auf der Microsoft Foundation Class\-Bibliothek.  Eine Beschreibung von Rückruffunktionen, die an [CDC::EnumObjects](../Topic/CDC::EnumObjects.md) übergeben werden, [CDC::GrayString](../Topic/CDC::GrayString.md) und [CDC::SetAbortProc](../Topic/CDC::SetAbortProc.md) folgt diesem Thema.  Für die allgemeine Verwendung von Rückruffunktionen, finden Sie im Abschnitt Hinweise dieser Memberfunktionen.  Beachten Sie, dass alle MFC\-Ausnahmen Rückruffunktionen auffangen müssen, bevor diese an Windows zurückkehren, da Ausnahmen nicht über Rückrufgrenzen ausgelöst werden können.  Weitere Informationen zu Ausnahmen, finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)