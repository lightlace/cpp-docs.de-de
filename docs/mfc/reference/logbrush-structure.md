---
title: LOGBRUSH-Struktur | Microsoft Docs
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
- LOGBRUSH structure [MFC]
ms.assetid: 1bf96768-52c5-4444-9bb8-d41ba2e27e68
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ec6cc9b61f837db4c9766c077fa60f4d9c2b95bd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="logbrush-structure"></a>LOGBRUSH-Struktur
Die `LOGBRUSH` Struktur definiert die Formatvorlage, die Farbe und die Muster von einem physischen Pinsel. Er wird von Windows verwendet [CreateBrushIndirect](http://msdn.microsoft.com/library/windows/desktop/dd183487) und [ExtCreatePen](http://msdn.microsoft.com/library/windows/desktop/dd162705) Funktionen.  
  
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
 Gibt das Pinsel-Format an. Der `lbStyle` Member muss eines der folgenden Formate:  
  
- **BS_DIBPATTERN** Muster Pinsels durch eine geräteunabhängige Bitmap (DIB)-Spezifikation definiert. Wenn `lbStyle` ist **BS_DIBPATTERN**, **LbHatch** Element enthält ein Handle für eine gepackte DIB.  
  
- **BS_DIBPATTERNPT** Muster Pinsels durch eine geräteunabhängige Bitmap (DIB)-Spezifikation definiert. Wenn `lbStyle` ist **BS_DIBPATTERNPT**, **LbHatch** Member enthält einen Zeiger auf eine gepackte DIB.  
  
- **BS_HATCHED** Pinsel eingestellt.  
  
- **BS_HOLLOW** leeres Pinsel.  
  
- **BS_NULL** wie **BS_HOLLOW**.  
  
- **BS_PATTERN** Muster Pinsel, die durch ein Speicher-Bitmap definiert.  
  
- **BS_SOLID** Pinsels in Volltonfarbe.  
  
 `lbColor`  
 Gibt die Farbe, in der ist der Pinsel, gezeichnet werden soll. Wenn `lbStyle` ist die **BS_HOLLOW** oder **BS_PATTERN** Stil **LbColor** wird ignoriert. Wenn `lbStyle` ist **BS_DIBPATTERN** oder **BS_DIBPATTERNBT**, das niederwertige Wort von **LbColor** gibt an, ob die **BmiColors**Mitglied der [BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md) Struktur enthalten explizite Rot, Grün, Blau)-Werte (oder Indizes in der aktuell realisierte logische Palette. Die **LbColor** Element muss einen der folgenden Werte sein:  
  
- **DIB_PAL_COLORS** die Farbtabelle besteht aus einem Array von 16-Bit-Indizes in der aktuell realisierte logische Palette.  
  
- **DIB_RGB_COLORS** der Farbtabelle enthält Literale RGB-Werte.  
  
 *lbHatch*  
 Gibt eine Schraffurart an. Die Bedeutung hängt von den Pinselstil definiert wird, indem Sie `lbStyle`. Wenn `lbStyle` ist **BS_DIBPATTERN**, **LbHatch** Element enthält ein Handle für eine gepackte DIB. Wenn `lbStyle` ist **BS_DIBPATTERNPT**, **LbHatch** Member enthält einen Zeiger auf eine gepackte DIB. Wenn `lbStyle` ist **BS_HATCHED**, **LbHatch** Element gibt die Ausrichtung der Zeilen verwendet, um die Schraffur zu erstellen. Die folgenden Werte sind möglich:  
  
- `HS_BDIAGONAL`Eine 45-Grad nach oben, links-nach-rechts-Schraffur  
  
- `HS_CROSS`Horizontale und vertikale Schraffur  
  
- `HS_DIAGCROSS`45-Grad-Schraffur  
  
- `HS_FDIAGONAL`Eine 45-Grad nach unten, links-nach-rechts-Schraffur  
  
- `HS_HORIZONTAL`Horizontale Schraffur  
  
- `HS_VERTICAL`Vertikale Schraffur  
  
 Wenn `lbStyle` ist **BS_PATTERN**, **LbHatch** ist ein Handle für die Bitmap, die das Muster definiert. Wenn `lbStyle` ist **BS_SOLID** oder **BS_HOLLOW**, **LbHatch** wird ignoriert.  
  
## <a name="remarks"></a>Hinweise  
 Obwohl **LbColor** steuert die Vordergrundfarbe des ein Schraffurpinsel der [CDC::SetBkMode](../../mfc/reference/cdc-class.md#setbkmode) und [CDC::SetBkColor](../../mfc/reference/cdc-class.md#setbkcolor) Funktionen steuern die Farbe des Hintergrunds.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** wingdi.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)

