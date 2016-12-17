---
title: "POINT-Struktur"
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
  - "POINT"
  - "LPPOINT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LPPOINT-Struktur"
  - "POINT-Struktur"
ms.assetid: 965736d8-4e53-41b6-9b8b-6961992dd21f
caps.latest.revision: 13
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# POINT-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die **POINT**\-Struktur definiert die x*\-* und y\-Koordinaten eines Punkts.  
  
## Syntax  
  
```  
  
      typedef struct tagPOINT {  
   LONG x;  
   LONG y;  
} POINT;  
```  
  
#### Parameter  
 *x*  
 Gibt die x\-Koordinate eines Punkts an.  
  
 *y*  
 Gibt die y\-Koordinate eines Punkts an.  
  
## Beispiel  
 [!CODE [NVC_MFC_Utilities#37](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_Utilities#37)]  
  
## Anforderungen  
 **Header:** windef.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPoint Class](../../atl-mfc-shared/reference/cpoint-class.md)