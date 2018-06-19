---
title: ABCFLOAT-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- ABCFLOAT
dev_langs:
- C++
helpviewer_keywords:
- ABCFLOAT structure [MFC]
ms.assetid: 338e7e15-9d2c-42d0-aa80-273acfde5cc5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5be39336f3da839dc9b1c7be6a64db54b59f99bd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351614"
---
# <a name="abcfloat-structure"></a>ABCFLOAT-Struktur
Die `ABCFLOAT` Struktur enthält die A, B und C breiten Zeichen ein.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct _ABCFLOAT { /* abcf */  
    FLOAT abcfA;  
    FLOAT abcfB;  
    FLOAT abcfC;  
} ABCFLOAT;  
```  
  
#### <a name="parameters"></a>Parameter  
 *abcfA*  
 Gibt den Abstand ein des Zeichens. Der Abstand ein entspricht dem Abstand, der aktuellen Position vor dem Zeichnen des Symbols Zeichen hinzuzufügen.  
  
 *abcfB*  
 Gibt den Abstand B des Zeichens. Der Abstand B ist die Breite des gezeichneten Teils des Symbols für das Zeichen an.  
  
 *abcfC*  
 Gibt den Abstand C des Zeichens. Der Abstand C entspricht dem Abstand hinzufügen zu der aktuellen Position bis Leerraum auf der rechten Seite des Symbols für das Zeichen bereitzustellen.  
  
## <a name="remarks"></a>Hinweise  
 Die Breite A, B und C werden entlang der Grundlinie der Schriftart gemessen. Das Inkrement Zeichen (Gesamtbreite), der ein Zeichen ist die Summe der Adressbereiche A, B und C. Die oder der C-Raum kann an Underhangs oder Überhängen negativ sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** wingdi.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)

