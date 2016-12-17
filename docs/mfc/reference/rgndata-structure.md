---
title: "RGNDATA-Struktur"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "RGNDATA"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RGNDATA-Struktur"
ms.assetid: 72257c00-f440-4dca-979e-9b6b5b2d5f2f
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# RGNDATA-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `RGNDATA` Struktur enthält einen Header und ein Array von Rechtecken, die einen Bereich zu bilden. Diese Rechtecke, sortiert nach oben links nach rechts, unten überlappen nicht.  
  
## <a name="syntax"></a>Syntax  
  
```  
 
    typedef struct _RGNDATA { /* rgnd */  
    RGNDATAHEADER rdh;  
    char Buffer[1];  
} RGNDATA;  
```  
  
#### <a name="parameters"></a>Parameter  
 *Element angezeigt*  
 Gibt eine [RGNDATAHEADER](http://msdn.microsoft.com/library/windows/desktop/dd162941) Struktur. (Weitere Informationen zu dieser Struktur finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].) Die Elemente dieser Struktur Geben Sie die Region (gibt an, ob er rechteckigen oder trapezoidförmiger befindet), die Anzahl der Rechtecke, aus denen die Region, die Größe des Puffers, der die Rechteck-Strukturen enthält, und so weiter.  
  
 `Buffer`  
 Gibt einen beliebiger Größe Puffer, enthält die [RECT](../../mfc/reference/rect-structure1.md) Strukturen, aus denen der Bereich besteht.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** wingdi.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#CreateFromData)   
 [CRgn::GetRegionData](../../mfc/reference/crgn-class.md#GetRegionData)

