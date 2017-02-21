---
title: "Punkt-Structure1 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
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
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
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