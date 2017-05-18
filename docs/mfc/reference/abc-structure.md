---
title: ABC-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ABC
dev_langs:
- C++
helpviewer_keywords:
- ABC structure
ms.assetid: 32663839-c3b7-4f47-896c-b15329c96bc8
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
ms.openlocfilehash: c8b49cd8a94c5ff580393814be08b1819a1eca52
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="abc-structure"></a>ABC-Struktur
Die **ABC** Struktur enthält die Breite eines Zeichens in eine TrueType-Schriftart.  
  
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
 Gibt den Abstand ein, der das Zeichen. Der Abstand ein ist der Abstand und die aktuelle Position vor dem Zeichnen des Symbols Zeichen hinzuzufügen.  
  
 *abcB*  
 Gibt den Abstand B des Zeichens. Der Abstand B ist die Breite des gezeichneten Teils des Symbols für das Zeichen.  
  
 *abcC*  
 Gibt den Abstand C des Zeichens. Der Abstand C ist der Abstand der aktuellen Position, Leerraum auf der rechten Seite des Symbols für das Zeichen bereitzustellen hinzu.  
  
## <a name="remarks"></a>Hinweise  
 Die Gesamtbreite der ein Zeichen ist die Summe der Leerzeichen A, B und C. A- oder der C-Raum kann an Underhangs oder Überhängen negativ sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** wingdi.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)



