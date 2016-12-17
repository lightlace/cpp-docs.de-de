---
title: "XFORM-Struktur"
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
  - "XFORM"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "XFORM-Struktur"
ms.assetid: 4fb4ef5b-05d2-4884-82d1-1cb8f7be6302
caps.latest.revision: 11
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# XFORM-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `XFORM`\-Struktur hat das folgende Format:  
  
## Syntax  
  
```  
  
      typedef struct  tagXFORM {  /* xfrm */  
    FLOAT eM11;  
    FLOAT eM12;  
    FLOAT eM21;  
    FLOAT eM22;  
    FLOAT eDx;  
    FLOAT eDy;  
} XFORM;  
```  
  
## Hinweise  
 Die `XFORM`\-Struktur gibt eine Worldspace\-SeiteLeerzeichentransformation an.  Die **eDx** und **eDy** geben Member den horizontalen und vertikalen Übersetzungskomponenten, bzw. an.  Die folgende Tabelle zeigt, wie die anderen Member verwendet werden, abhängig von den Vorgang an:  
  
|Vorgang|eM11|eM12|eM21|eM22|  
|-------------|----------|----------|----------|----------|  
|`Rotation`|Kosinus des Drehungswinkels|Sinus des Drehungswinkels|Negativer Sinus des Drehungswinkels|Kosinus des Drehungswinkels|  
|**Skalieren**|Horizontale Skalierungskomponente|Nothing|Nothing|Vertikale Skalierungskomponente|  
|**Schneiden**|Nothing|Horizontale Proportionalitätskonstante|Vertikale Proportionalitätskonstante|Nothing|  
|**Reflektion**|Horizontale Reflektionskomponente|Nothing|Nothing|Vertikale Reflektionskomponente|  
  
## Anforderungen  
 **Header:** wingdi.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../Topic/CRgn::CreateFromData.md)