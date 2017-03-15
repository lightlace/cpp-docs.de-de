---
title: LOGPEN-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LOGPEN
dev_langs:
- C++
helpviewer_keywords:
- LOGPEN structure
ms.assetid: a89e8690-6b61-4af5-990c-7c82da24f3b0
caps.latest.revision: 12
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
ms.openlocfilehash: f3868d2ac6a7b18cfe43f7da8865aed0a3ecf88d
ms.lasthandoff: 02/24/2017

---
# <a name="logpen-structure"></a>LOGPEN-Struktur
Die `LOGPEN` Struktur definiert die Art, Breite und Farbe eines Stiftes, ein Objekt zum Zeichnen von Linien und Rahmen. Die [CPen::CreatePenIndirect](../../mfc/reference/cpen-class.md#createpenindirect) -Funktion verwendet die `LOGPEN` Struktur.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct tagLOGPEN {  /* lgpn */  
    UINT lopnStyle;  
    POINT lopnWidth;  
    COLORREF lopnColor;  
} LOGPEN;  
```  
  
#### <a name="parameters"></a>Parameter  
 *lopnStyle*  
 Gibt den Stift. Dieser Member kann einen der folgenden Werte sein:  
  
- **PS_SOLID** eine durchgehend erstellt.  
  
- **PS_DASH** einen gestrichelten Stift erstellt. (Nur gültig, wenn die Stiftbreite 1 ist.)  
  
- **PS_DOT** erstellt eine gepunktet. (Nur gültig, wenn die Stiftbreite 1 ist.)  
  
- **PS_DASHDOT** erstellt einen Stift mit abwechselnden Striche und Punkte. (Nur gültig, wenn die Stiftbreite 1 ist.)  
  
- **PS_DASHDOTDOT** erstellt einen Stift mit abwechselnden Striche und doppelte Punkte. (Nur gültig, wenn die Stiftbreite 1 ist.)  
  
- **PS_NULL** erstellt einen Stift null.  
  
- **PS_INSIDEFRAME** erstellt einen Stift, der zeichnet eine Linie innerhalb des Rahmens der geschlossene Formen erzeugte Ausgabe GDI-Funktionen, die ein umschließendes Rechteck angeben (z. B. die **Ellipse**, **Rechteck**, `RoundRect`, `Pie`, und `Chord` Memberfunktionen). Wenn dieses Format verwendet wird, mit GDI a-Funktionen, die ein umschließendes Rechteck nicht angeben (z. B. die `LineTo` Member-Funktion), die Zeichenfläche des Stifts wird nicht von einem Frame beschränkt.  
  
     Besitzt ein Stift der **PS_INSIDEFRAME** Stil und eine Farbe, die nicht mit eine Farbe in der logischen Farbtabelle übereinstimmt der Stift, der mit einem geditherte Farbe gezeichnet wird. Die **PS_SOLID** Pen-Stil kann nicht verwendet werden, um einen Stift mit einer geditherte Farbe zu erstellen. Die **PS_INSIDEFRAME** Format ist identisch mit **PS_SOLID** Wenn die Stiftbreite kleiner oder gleich 1 ist.  
  
     Wenn die **PS_INSIDEFRAME** Stil wird mit GDI-Objekte, die von Funktionen als erzeugt verwendet **Ellipse**, **Rechteck**, und `RoundRect`, die Linie möglicherweise nicht vollständig innerhalb des angegebenen Rahmens.  
  
 *lopnWidth*  
 Gibt die Stiftbreite in logischen Einheiten. Wenn die **LopnWidth** Member 0, wird der Stift ist 1 Pixel breit auf Raster Geräten unabhängig von der aktuellen Zuordnungsmodus.  
  
 *lopnColor*  
 Gibt die Farbe des Stifts.  
  
## <a name="remarks"></a>Hinweise  
 Die **y** -Wert in der [Punkt](../../mfc/reference/point-structure1.md) Struktur für die **LopnWidth** Element wird nicht verwendet.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** wingdi.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPen::CreatePenIndirect](../../mfc/reference/cpen-class.md#createpenindirect)


