---
title: LOGPEN-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: LOGPEN
dev_langs: C++
helpviewer_keywords: LOGPEN structure [MFC]
ms.assetid: a89e8690-6b61-4af5-990c-7c82da24f3b0
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b7bfa598a59f62c11dbda13356559816b5bd47ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="logpen-structure"></a>LOGPEN-Struktur
Die `LOGPEN` Struktur definiert die Art, Breite und Farbe eines Stiftes, ein Objekt zum Zeichnen von Linien und Rahmen. Die [CPen::CreatePenIndirect](../../mfc/reference/cpen-class.md#createpenindirect) Funktion verwendet die `LOGPEN` Struktur.  
  
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
 Gibt den Stifttyp. Dieser Member kann einen der folgenden Werte sein:  
  
- **PS_SOLID** eine durchgehend erstellt.  
  
- **PS_DASH** eine gestrichelt erstellt. (Nur gültig, wenn die Stiftbreite 1 ist.)  
  
- **PS_DOT** erstellt eine gepunktet. (Nur gültig, wenn die Stiftbreite 1 ist.)  
  
- **PS_DASHDOT** erstellt einen Stift mit abwechselnden Striche und Punkte enthalten. (Nur gültig, wenn die Stiftbreite 1 ist.)  
  
- **PS_DASHDOTDOT** erstellt einen Stift mit abwechselnden Striche und doppelte Punkte. (Nur gültig, wenn die Stiftbreite 1 ist.)  
  
- **PS_NULL** erstellt einen null-Stift.  
  
- **PS_INSIDEFRAME** einen Stift, der eine Zeile in den Rahmen des geschlossene Formen von GDI-Ausgabe-Funktionen, die ein umschließendes Rechteck angeben erzeugten zeichnet erstellt (z. B. die **Ellipse**, **Rechteck**, `RoundRect`, `Pie`, und `Chord` Memberfunktionen). Wenn dieses Format verwendet wird, mit GDI ausgabefunktionen, die ein umschließendes Rechteck nicht angeben (z. B. die `LineTo` Memberfunktion), der Zeichnungsbereich des Stifts wird nicht von einem Frame beschränkt.  
  
     Verfügt ein Stift der **PS_INSIDEFRAME** Stil und eine Farbe, die nicht mit eine Farbe in der logischen Farbtabelle übereinstimmt der Stift mit einem Ditheringfarbe gezeichnet wird. Die **PS_SOLID** Stiftstil kann nicht verwendet werden, um mit einer Farbe ein Stiftes erstellen. Die **PS_INSIDEFRAME** Format ist identisch mit **PS_SOLID** , wenn die Stiftbreite kleiner oder gleich 1 ist.  
  
     Wenn die **PS_INSIDEFRAME** Format wird verwendet, mit GDI-Objekte, außer von Funktionen erzeugten **Ellipse**, **Rechteck**, und `RoundRect`, die Linie möglicherweise nicht vollständig innerhalb des angegebenen Rahmens.  
  
 *lopnWidth*  
 Gibt die Stiftbreite in logischen Einheiten. Wenn die **LopnWidth** Member gleich 0 ist, der Stift ist 1 Pixel breit auf Raster Geräten unabhängig von der aktuellen Zuordnungsmodus.  
  
 *lopnColor*  
 Gibt die Stiftfarbe.  
  
## <a name="remarks"></a>Hinweise  
 Die **y** Wert in der [Punkt](../../mfc/reference/point-structure1.md) Struktur für die **LopnWidth** Element wird nicht verwendet.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** wingdi.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPen::CreatePenIndirect](../../mfc/reference/cpen-class.md#createpenindirect)

