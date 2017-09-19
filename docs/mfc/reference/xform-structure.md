---
title: XFORM-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- XFORM
dev_langs:
- C++
helpviewer_keywords:
- XFORM structure
ms.assetid: 4fb4ef5b-05d2-4884-82d1-1cb8f7be6302
caps.latest.revision: 11
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 2d23b3838f1e2dcabb2affb96fa6f18942581ff8
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="xform-structure"></a>XFORM-Struktur
Die `XFORM` -Struktur hat folgende Form:  
  
## <a name="syntax"></a>Syntax  
  
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
  
## <a name="remarks"></a>Hinweise  
 Die `XFORM` Struktur gibt eine World-Seite-Space-Transformation. Die **eDx** und **eDy** Elemente geben die horizontalen und vertikalen Translation-Komponenten. Die folgende Tabelle zeigt, wie die anderen Elemente abhängig vom Vorgang verwendet werden:  
  
|Vorgang|eM11|eM12|eM21|eM22|  
|---------------|----------|----------|----------|----------|  
|`Rotation`|Kosinus der Winkel der Drehung|Sinus Drehwinkel|Negative Sinus Drehwinkel|Kosinus der Winkel der Drehung|  
|**Skalierung**|Horizontale Skalierung-Komponente|Nothing|Nothing|Vertikale Skalierung Komponente|  
|**Scheren von**|Nothing|Horizontale Verhältnismäßigkeit-Konstante|Vertikale Verhältnismäßigkeit-Konstante|Nothing|  
|**Reflektion**|Horizontale Reflektion-Komponente|Nothing|Nothing|Vertikale Reflektion-Komponente|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** wingdi.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)


