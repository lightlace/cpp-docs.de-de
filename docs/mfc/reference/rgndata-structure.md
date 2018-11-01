---
title: RGNDATA-Struktur
ms.date: 11/04/2016
f1_keywords:
- RGNDATA
helpviewer_keywords:
- RGNDATA structure [MFC]
ms.assetid: 72257c00-f440-4dca-979e-9b6b5b2d5f2f
ms.openlocfilehash: d6ee25b490aa5c7055b4e8ccf63939fbdd8dd4ac
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638138"
---
# <a name="rgndata-structure"></a>RGNDATA-Struktur

Die `RGNDATA` Struktur enthält eine Kopfzeile und ein Array von Rechtecken, die zu eine Region gehören. Dieser Rechtecke, sortierte oben links nach rechts und nach unten überlappen nicht.

## <a name="syntax"></a>Syntax

```
typedef struct _RGNDATA { /* rgnd */
    RGNDATAHEADER rdh;
    char Buffer[1];
} RGNDATA;
```

#### <a name="parameters"></a>Parameter

*Element angezeigt*<br/>
Gibt an, eine [RGNDATAHEADER](/windows/desktop/api/wingdi/ns-wingdi-_rgndataheader) Struktur. (Weitere Informationen zu dieser Struktur finden Sie im Windows SDK.) Die Elemente dieser Struktur Geben Sie den Typ des Bereichs (gibt an, ob es rechteckigen oder trapezoidförmiger ist), die Anzahl der Rechtecke, aus denen die Region, die Größe des Puffers, die die Rechteck-Strukturen enthält, und so weiter.

*Buffer*<br/>
Gibt an, einen Puffer von beliebiger Größe, enthält die [RECT](../../mfc/reference/rect-structure1.md) Strukturen, die der Region bilden.

## <a name="requirements"></a>Anforderungen

**Header:** wingdi.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)<br/>
[CRgn::GetRegionData](../../mfc/reference/crgn-class.md#getregiondata)

