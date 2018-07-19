---
title: LOGPEN-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- LOGPEN
dev_langs:
- C++
helpviewer_keywords:
- LOGPEN structure [MFC]
ms.assetid: a89e8690-6b61-4af5-990c-7c82da24f3b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c677f86a44d24e0d0d2742d47ee1534532001528
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37338531"
---
# <a name="logpen-structure"></a>LOGPEN-Struktur
Die `LOGPEN` Struktur definiert, der Stil, Breite und Farbe eines Stiftes, ein Zeichnungsobjekt, die zum Zeichnen von Linien und Rahmen. Die [CPen::CreatePenIndirect](../../mfc/reference/cpen-class.md#createpenindirect) Funktion verwendet die `LOGPEN` Struktur.  
  
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
  
- PS_SOLID erstellt einen soliden Stift.  
  
- PS_DASH erstellt eine gestrichelt. (Nur gültig, wenn der Stift 1 ist.)  
  
- PS_DOT erstellt eine gepunktet. (Nur gültig, wenn der Stift 1 ist.)  
  
- PS_DASHDOT erstellt, ein Stift mit abwechselnden Striche und Punkte. (Nur gültig, wenn der Stift 1 ist.)  
  
- PS_DASHDOTDOT erstellt ein Stift, mit der abwechselnden Striche und doppelte Punkte. (Nur gültig, wenn der Stift 1 ist.)  
  
- PS_NULL erstellt einen null-Stift.  
  
- PS_INSIDEFRAME erstellt ein Stift, der eine Zeile innerhalb des Rahmens der geschlossene Formen zeichnet erstellt, indem GDI a-Funktionen, die ein umschließendes Rechteck angeben (z. B. die `Ellipse`, `Rectangle`, `RoundRect`, `Pie`, und `Chord` Member -Funktionen). Wenn dieses Format verwendet wird, mit GDI a-Funktionen, die ein umschließendes Rechteck nicht angeben (z. B. die `LineTo` Member-Funktion), der Zeichnungsbereich des Stifts wird nicht von einem Frame beschränkt.  
  
     Wenn ein Stift verfügt der PS_INSIDEFRAME-Stil und eine Farbe, die nicht mit eine Farbe in der logischen Farbtabelle übereinstimmt, wird der Stift mit einer geditherte Farbe gezeichnet. Styl Stift PS_SOLID kann nicht zum Erstellen eines Stifts mit einer geditherte Farbe verwendet werden. Styl PS_INSIDEFRAME ist identisch mit PS_SOLID, wenn der Stift kleiner als oder gleich 1 ist.  
  
     Wenn der Stil PS_INSIDEFRAME mit GDI-Objekte verwendet wird außer von Funktionen erstellt `Ellipse`, `Rectangle`, und `RoundRect`, die Linie möglicherweise nicht vollständig innerhalb des angegebenen Rahmens.  
  
 *lopnWidth*  
 Gibt die Stiftbreite, in logischen Einheiten. Wenn die `lopnWidth` Members ist 0, der Stift ist 1 Pixel breit auf Raster-Geräten unabhängig von der aktuellen Zuordnungsmodus.  
  
 *lopnColor*  
 Gibt die Stiftfarbe.  
  
## <a name="remarks"></a>Hinweise  
 Die `y` Wert in der [Punkt](../../mfc/reference/point-structure1.md) -Struktur für die `lopnWidth` Element wird nicht verwendet.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** wingdi.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPen::CreatePenIndirect](../../mfc/reference/cpen-class.md#createpenindirect)

