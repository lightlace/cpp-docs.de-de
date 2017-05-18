---
title: LOGBRUSH-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LOGBRUSH
dev_langs:
- C++
helpviewer_keywords:
- LOGBRUSH structure
ms.assetid: 1bf96768-52c5-4444-9bb8-d41ba2e27e68
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
ms.openlocfilehash: eea7caf6139fd43dd77163271701d170c7a744e2
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="logbrush-structure"></a>LOGBRUSH-Struktur
Die `LOGBRUSH` Struktur definiert die Art, Farbe und Muster von einem physischen Pinsel. Es wird von Windows verwendet [CreateBrushIndirect](http://msdn.microsoft.com/library/windows/desktop/dd183487) und [ExtCreatePen](http://msdn.microsoft.com/library/windows/desktop/dd162705) Funktionen.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct tag LOGBRUSH { /* lb */  
    UINT lbStyle;  
    COLORREF lbColor;  
    LONG lbHatch;  
} LOGBRUSH;  
```  
  
#### <a name="parameters"></a>Parameter  
 `lbStyle`  
 Gibt den Pinselstil. Der `lbStyle` Member muss eines der folgenden Formate:  
  
- **BS_DIBPATTERN** Muster Pinsels, der durch eine geräteunabhängige Bitmap (DIB)-Spezifikation definiert. Wenn `lbStyle` ist **BS_DIBPATTERN**, **LbHatch** Element enthält ein Handle für eine gepackte DIB.  
  
- **BS_DIBPATTERNPT** Muster Pinsels, der durch eine geräteunabhängige Bitmap (DIB)-Spezifikation definiert. Wenn `lbStyle` ist **BS_DIBPATTERNPT**, **LbHatch** Member enthält einen Zeiger auf eine gepackte DIB.  
  
- **BS_HATCHED** ausgebrütet Pinsel.  
  
- **BS_HOLLOW** leeres Pinsel.  
  
- **BS_NULL** wie **BS_HOLLOW**.  
  
- **BS_PATTERN** Pinsel definiert ein Speicher-Bitmap-Muster.  
  
- **BS_SOLID** Pinsel.  
  
 `lbColor`  
 Gibt die Farbe der Pinsel ist, in der gezeichnet werden. Wenn `lbStyle` ist die **BS_HOLLOW** oder **BS_PATTERN** Stil **LbColor** wird ignoriert. Wenn `lbStyle` ist **BS_DIBPATTERN** oder **BS_DIBPATTERNBT**, das niederwertige Wort von **LbColor** gibt an, ob die **BmiColors** Mitglieder der [BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md) Struktur explizite Rot, Grün, Blau)-Werte (oder Indizes in der aktuell realisierte logische Palette enthalten. Die **LbColor** -Element muss einen der folgenden Werte sein:  
  
- **DIB_PAL_COLORS** die Farbtabelle besteht aus einem Array von 16-Bit-Indizes in der aktuell realisierte logische Palette.  
  
- **DIB_RGB_COLORS** die Farbtabelle Literale RGB-Werte enthält.  
  
 *lbHatch*  
 Gibt eine Schraffurart. Die Bedeutung hängt von den Pinselstil definiert `lbStyle`. Wenn `lbStyle` ist **BS_DIBPATTERN**, **LbHatch** Element enthält ein Handle für eine gepackte DIB. Wenn `lbStyle` ist **BS_DIBPATTERNPT**, **LbHatch** Member enthält einen Zeiger auf eine gepackte DIB. Wenn `lbStyle` ist **BS_HATCHED**, **LbHatch** Element gibt die Ausrichtung der Zeilen verwendet, um die Schraffur zu erstellen. Die folgenden Werte sind möglich:  
  
- `HS_BDIAGONAL`Eine Schraffur an 45 Grad nach oben, links-nach-rechts  
  
- `HS_CROSS`Horizontale und vertikale Schraffur  
  
- `HS_DIAGCROSS`45-Grad-Schraffur  
  
- `HS_FDIAGONAL`Eine Schraffur an 45 Grad nach unten, links-nach-rechts  
  
- `HS_HORIZONTAL`Horizontale Schraffur  
  
- `HS_VERTICAL`Vertikale schraffierte  
  
 Wenn `lbStyle` ist **BS_PATTERN**, **LbHatch** ist ein Handle für die Bitmap, die das Muster definiert. Wenn `lbStyle` ist **BS_SOLID** oder **BS_HOLLOW**, **LbHatch** wird ignoriert.  
  
## <a name="remarks"></a>Hinweise  
 Obwohl **LbColor** steuert die Vordergrundfarbe für ein Schraffurpinsel der [CDC::SetBkMode](../../mfc/reference/cdc-class.md#setbkmode) und [CDC::SetBkColor](../../mfc/reference/cdc-class.md#setbkcolor) Funktionen steuern die Farbe des Hintergrunds.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** wingdi.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)


