---
title: RGNDATA-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- RGNDATA
dev_langs:
- C++
helpviewer_keywords:
- RGNDATA structure [MFC]
ms.assetid: 72257c00-f440-4dca-979e-9b6b5b2d5f2f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d4170b3590cc841f3edc10d4767045a4fede9782
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="rgndata-structure"></a>RGNDATA-Struktur
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
 Gibt eine [RGNDATAHEADER](http://msdn.microsoft.com/library/windows/desktop/dd162941) Struktur. (Weitere Informationen zu dieser Struktur finden Sie in das Windows SDK). Die Elemente dieser Struktur Geben Sie die Region (gibt an, ob er rechteckigen oder trapezoidförmiger befindet), die Anzahl der Rechtecke, aus denen die Region, die Größe des Puffers, der die Rechteck-Strukturen enthält, und so weiter.  
  
 `Buffer`  
 Gibt einen beliebiger Größe Puffer, enthält die [RECT](../../mfc/reference/rect-structure1.md) Strukturen, aus denen der Bereich besteht.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** wingdi.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)   
 [CRgn::GetRegionData](../../mfc/reference/crgn-class.md#getregiondata)

