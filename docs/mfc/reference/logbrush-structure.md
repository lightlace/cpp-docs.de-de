---
title: LOGBRUSH-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- LOGBRUSH
dev_langs:
- C++
helpviewer_keywords:
- LOGBRUSH structure [MFC]
ms.assetid: 1bf96768-52c5-4444-9bb8-d41ba2e27e68
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 15b904a07eb668a59a269741973424aa30e15877
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336405"
---
# <a name="logbrush-structure"></a>LOGBRUSH-Struktur
Die `LOGBRUSH` Struktur definiert, der Stil, Farbe und Muster von einem physischen Pinsel. Sie wird von der Windows verwendet [CreateBrushIndirect](http://msdn.microsoft.com/library/windows/desktop/dd183487) und [ExtCreatePen](http://msdn.microsoft.com/library/windows/desktop/dd162705) Funktionen.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct tag LOGBRUSH { /* lb */  
    UINT lbStyle;  
    COLORREF lbColor;  
    LONG lbHatch;  
} LOGBRUSH;  
```  
  
#### <a name="parameters"></a>Parameter  
 *lbStyle*  
 Gibt die Art des Pinsels. Die `lbStyle` Member muss eine der folgenden Formate:  
  
- BS_DIBPATTERN ein Musterpinsel, die durch eine geräteunabhängige Bitmap (DIB)-Spezifikation definiert. Wenn *LbStyle* BS_DIBPATTERN, ist die `lbHatch` Member enthält, ein Handle für eine gepackte DIB-Datei.  
  
- BS_DIBPATTERNPT ein Musterpinsel, die durch eine geräteunabhängige Bitmap (DIB)-Spezifikation definiert. Wenn *LbStyle* BS_DIBPATTERNPT, ist die `lbHatch` Member enthält einen Zeiger auf eine gepackte DIB-Datei.  
  
- BS_HATCHED ausgebrütet Pinsel.  
  
- Leerer BS_HOLLOW Pinsel.  
  
- BS_NULL BS_HOLLOW identisch.  
  
- Ein Pinsel, der BS_PATTERN Muster durch eine Arbeitsspeicher-Bitmap definiert.  
  
- BS_SOLID einfarbigen Pinsel.  
  
 *lbColor*  
 Gibt die Farbe der Pinsel ist, in der gezeichnet werden soll. Wenn *LbStyle* entspricht dem Stil BS_HOLLOW oder BS_PATTERN *LbColor* wird ignoriert. Wenn *LbStyle* ist BS_DIBPATTERN oder BS_DIBPATTERNBT, das niederwertige Wort *LbColor* gibt an, ob die `bmiColors` Mitglied der [BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md) Struktur enthalten Sie explizite Rot, Grün, Blau (Werte) oder Indizes in der derzeit realisierten logische Palette an. Die `lbColor` Member muss einen der folgenden Werte sein:  
  
- DIB_PAL_COLORS die Farbtabelle besteht aus einem Array von 16-Bit-Indizes in der derzeit realisierten logische Palette.  
  
- DIB_RGB_COLORS die Farbtabelle enthält Literale RGB-Werte.  
  
 *lbHatch*  
 Gibt eine Schraffurart. Die Bedeutung hängt von den Pinselstil durch definiert *LbStyle*. Wenn *LbStyle* BS_DIBPATTERN, ist die `lbHatch` Member enthält, ein Handle für eine gepackte DIB-Datei. Wenn *LbStyle* BS_DIBPATTERNPT, ist die `lbHatch` Member enthält einen Zeiger auf eine gepackte DIB-Datei. Wenn *LbStyle* BS_HATCHED, ist die `lbHatch` Element gibt die Ausrichtung der Zeilen verwendet, um die Schraffur zu erstellen. Es kann eine der folgenden Werte sein:  
  
- Nach oben, links-nach-rechts-HS_BDIAGONAL ein 45-Grad-Schraffur  
  
- HS_CROSS horizontale und vertikale Schraffur  
  
- HS_DIAGCROSS 45-Grad-Schraffur  
  
- Nach unten, links-nach-rechts-HS_FDIAGONAL ein 45-Grad-Schraffur  
  
- Horizontale HS_HORIZONTAL Schraffur  
  
- Vertikale HS_VERTICAL Schraffur  
  
 Wenn *LbStyle* ist BS_PATTERN, *LbHatch* ist ein Handle für die Bitmap, die das Muster definiert. Wenn *LbStyle* ist BS_SOLID oder BS_HOLLOW, *LbHatch* wird ignoriert.  
  
## <a name="remarks"></a>Hinweise  
 Obwohl *LbColor* steuert die Vordergrundfarbe für ein Schraffurpinsel der [CDC::SetBkMode](../../mfc/reference/cdc-class.md#setbkmode) und [CDC::SetBkColor](../../mfc/reference/cdc-class.md#setbkcolor) Funktionen steuern, die Farbe des Hintergrunds.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** wingdi.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)

