---
title: "Von MFC verwendete R&#252;ckruffunktionen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
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
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Von MFC verwendete R&#252;ckruffunktionen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Drei Rückruffunktionen werden auf der Microsoft Foundation Class\-Bibliothek.  Eine Beschreibung von Rückruffunktionen, die an [CDC::EnumObjects](../Topic/CDC::EnumObjects.md) übergeben werden, [CDC::GrayString](../Topic/CDC::GrayString.md) und [CDC::SetAbortProc](../Topic/CDC::SetAbortProc.md) folgt diesem Thema.  Für die allgemeine Verwendung von Rückruffunktionen, finden Sie im Abschnitt Hinweise dieser Memberfunktionen.  Beachten Sie, dass alle MFC\-Ausnahmen Rückruffunktionen auffangen müssen, bevor diese an Windows zurückkehren, da Ausnahmen nicht über Rückrufgrenzen ausgelöst werden können.  Weitere Informationen zu Ausnahmen, finden Sie im Artikel [Ausnahmen](../../mfc/exception-handling-in-mfc.md).  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)