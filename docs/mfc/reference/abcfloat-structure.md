---
title: "ABCFLOAT-Struktur"
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
  - "ABCFLOAT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ABCFLOAT-Struktur"
ms.assetid: 338e7e15-9d2c-42d0-aa80-273acfde5cc5
caps.latest.revision: 11
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# ABCFLOAT-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `ABCFLOAT`\-Struktur enthält die A, B und C\-Breiten eines Schriftartzeichens.  
  
## Syntax  
  
```  
  
      typedef struct _ABCFLOAT { /* abcf */  
   FLOAT abcfA;  
   FLOAT abcfB;  
   FLOAT abcfC;  
} ABCFLOAT;  
```  
  
#### Parameter  
 *abcfA*  
 Gibt den a\-Abstand des Zeichens an.  Der a\-Abstand entspricht dem Abstand, um die aktuelle Position hinzuzufügen, bevor er die Zeichensymbol angezeigt.  
  
 *abcfB*  
 Gibt den B\-Abstand des Zeichens an.  Der B\-Abstand ist die Breite des gezeichneten Teils der Zeichensymbol angezeigt.  
  
 *abcfC*  
 Gibt den C\-Abstand des Zeichens an.  Der C\-Abstand entspricht dem Abstand, um die aktuelle Position hinzuzufügen, Leerstellen auf der rechten Seite der Zeichensymbol angezeigt bereitzustellen.  
  
## Hinweise  
 Die Ebenen A, B und C\-Breiten werden die Basislinie nach der Schriftart gemessen.  Das Zeicheninkrement \(gesamte Breite\) eines Zeichens ist die Summe der A, B und C\-Leerzeichen.  Über das A oder das C\-Leerzeichen negativ sein können, underhangs oder Überhängen anzugeben.  
  
## Anforderungen  
 **Header:** wingdi.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../Topic/CDC::GetCharABCWidths.md)