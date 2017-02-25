---
title: "RECT-Structure1 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LPRECT"
  - "RECT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RECT-Struktur"
  - "LPRECT-Struktur"
ms.assetid: 1b3160de-64e9-40d1-89eb-af3e0fd6acf0
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# RECT-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `RECT`\-Struktur definiert die Koordinaten der oberen linken und der unteren rechten Ecke eines Rechtecks.  
  
## Syntax  
  
```  
  
      typedef struct tagRECT {   
   LONG left;  
   LONG top;  
   LONG right;  
   LONG bottom;  
} RECT;  
```  
  
## Member  
 `left`  
 Gibt die X\-Koordinate der oberen linken Ecke eines Rechtecks an.  
  
 `top`  
 Gibt die Y\-Koordinate der oberen linken Ecke eines Rechtecks an.  
  
 `right`  
 Gibt die X\-Koordinate der unteren rechten Ecke eines Rechtecks an.  
  
 `bottom`  
 Gibt die Y\-Koordinate der unteren rechten Ecke eines Rechtecks an.  
  
## Beispiel  
 [!CODE [NVC_MFC_Utilities#38](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_Utilities#38)]  
  
## Anforderungen  
 **Header:** windef.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRect Class](../../atl-mfc-shared/reference/crect-class.md)