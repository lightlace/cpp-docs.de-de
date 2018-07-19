---
title: ABC-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- ABC
dev_langs:
- C++
helpviewer_keywords:
- ABC structure [MFC]
ms.assetid: 32663839-c3b7-4f47-896c-b15329c96bc8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2c9aac181edb12df8904a2bc6d891d59c0067ecc
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37339318"
---
# <a name="abc-structure"></a>ABC-Struktur
Die `ABC` Struktur enthält die Breite eines Zeichens in eine TrueType-Schriftart.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct _ABC { /* abc */  
    int abcA;  
    UINT abcB;  
    int abcC;  
} ABC;  
```  
  
#### <a name="parameters"></a>Parameter  
 *abcA*  
 Gibt den Abstand ein des Zeichens. Der Abstand ein ist der Abstand und die aktuelle Position vor dem Zeichnen des Symbols Zeichen hinzuzufügen.  
  
 *abcB*  
 Gibt den Abstand B des Zeichens. Der Abstand B ist die Breite des gezeichneten Bereich des Symbols für das Zeichen an.  
  
 *abcC*  
 Gibt den Abstand C des Zeichens. Der C-Abstand wird der Abstand der aktuellen Position Leerraum auf der rechten Seite des Symbols für das Zeichen zu hinzu.  
  
## <a name="remarks"></a>Hinweise  
 Die gesamte Breite eines Zeichens ist die Summe der Leerzeichen A, B und C. A- oder der C-Space kann an Underhangs oder Überhängen negativ sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** wingdi.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)


