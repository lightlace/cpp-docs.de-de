---
title: RGNDATA-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- RGNDATA
dev_langs:
- C++
helpviewer_keywords:
- RGNDATA structure
ms.assetid: 72257c00-f440-4dca-979e-9b6b5b2d5f2f
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 93a7c79f175e22dcb0b40cb39b157cfe21a98e93
ms.lasthandoff: 02/24/2017

---
# <a name="rgndata-structure"></a>RGNDATA-Struktur
Die `RGNDATA` Struktur enthält einen Header und ein Array von Rechtecken, die einen Bereich zu bilden. Diese Rechtecke, sortiert nach oben, links, rechts, unten überlappen nicht.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct _RGNDATA { /* rgnd */  
    RGNDATAHEADER rdh;  
    char Buffer[1];  
} RGNDATA;  
```  
  
#### <a name="parameters"></a>Parameter  
 *rdh*  
 Gibt eine [RGNDATAHEADER](http://msdn.microsoft.com/library/windows/desktop/dd162941) Struktur. (Weitere Informationen zu dieser Struktur finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].) Die Mitglieder dieser Struktur Geben Sie die Region (ob es rechteckigen oder trapezoidförmiger ist), die Anzahl der Rechtecke, aus denen die Region, die Größe des Puffers, die die Strukturen Rechteck enthält und so weiter.  
  
 `Buffer`  
 Gibt einen beliebiger Größe Puffer mit der [RECT](../../mfc/reference/rect-structure1.md) Strukturen, die den Bereich bilden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** wingdi.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)   
 [CRgn::GetRegionData](../../mfc/reference/crgn-class.md#getregiondata)


