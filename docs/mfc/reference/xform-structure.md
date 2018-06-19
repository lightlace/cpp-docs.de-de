---
title: XFORM-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- XFORM
dev_langs:
- C++
helpviewer_keywords:
- XFORM structure [MFC]
ms.assetid: 4fb4ef5b-05d2-4884-82d1-1cb8f7be6302
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1a1c3a8abd39f7f190f36a18e7691475d951cab8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379485"
---
# <a name="xform-structure"></a>XFORM-Struktur
Die `XFORM` Struktur weist folgende Form:  
  
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
 Die `XFORM` Struktur gibt an, ein World-Leerzeichen zur Seite "+ LEERTASTE-Transformation. Die **eDx** und **eDy** Mitglieder die horizontalen und vertikalen Übersetzung Komponenten bzw. angeben. Die folgende Tabelle zeigt, wie die anderen Member abhängig vom Vorgang verwendet werden:  
  
|Vorgang|eM11|eM12|eM21|eM22|  
|---------------|----------|----------|----------|----------|  
|`Rotation`|Kosinus von Drehwinkel für Bezeichnungen|Sinus von Drehwinkel für Bezeichnungen|Negative Sinus Drehwinkel für Bezeichnungen|Kosinus von Drehwinkel für Bezeichnungen|  
|**Skalierung**|Horizontale Skalierung-Komponente|Nothing|Nothing|Vertikale Skalierung-Komponente|  
|**Scheren von**|Nothing|Horizontale Verhältnismäßigkeit-Konstante|Vertikale Verhältnismäßigkeit-Konstante|Nothing|  
|**Reflexion**|Horizontale Reflektion-Komponente|Nothing|Nothing|Vertikale Reflektion-Komponente|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** wingdi.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)

