---
title: ABCFLOAT-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ABCFLOAT
dev_langs:
- C++
helpviewer_keywords:
- ABCFLOAT structure [MFC]
ms.assetid: 338e7e15-9d2c-42d0-aa80-273acfde5cc5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b58871df5a526455297dd6d092f98e9facd901ae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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

