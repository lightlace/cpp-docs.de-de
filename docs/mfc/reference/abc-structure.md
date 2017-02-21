---
title: "ABC-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ABC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ABC-Struktur"
ms.assetid: 32663839-c3b7-4f47-896c-b15329c96bc8
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# ABC-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die **ABC**\-Struktur enthält die Breite eines Zeichens in einer TrueType\-Schriftart.  
  
## Syntax  
  
```  
  
      typedef struct _ABC { /* abc */  
   int abcA;  
   UINT abcB;  
   int abcC;  
} ABC;  
```  
  
#### Parameter  
 *abcA*  
 Gibt den a\-Abstand des Zeichens an.  Der a\-Abstand entspricht dem Abstand, um die aktuelle Position hinzuzufügen, bevor er die Zeichensymbol angezeigt.  
  
 *abcB*  
 Gibt den B\-Abstand des Zeichens an.  Der B\-Abstand ist die Breite des gezeichneten Teils der Zeichensymbol angezeigt.  
  
 *abcC*  
 Gibt den C\-Abstand des Zeichens an.  Der C\-Abstand entspricht dem Abstand, um die aktuelle Position hinzuzufügen, Leerstellen auf der rechten Seite der Zeichensymbol angezeigt bereitzustellen.  
  
## Hinweise  
 Die gesamte Breite eines Zeichens ist die Zusammenfassung der A, B und C\-Leerzeichen.  Über das A oder das C\-Leerzeichen negativ sein können, underhangs oder Überhängen anzugeben.  
  
## Anforderungen  
 **Header:** wingdi.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../Topic/CDC::GetCharABCWidths.md)