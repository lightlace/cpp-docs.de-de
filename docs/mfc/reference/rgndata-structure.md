---
title: RGNDATA-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- RGNDATA
dev_langs:
- C++
helpviewer_keywords:
- RGNDATA structure [MFC]
ms.assetid: 72257c00-f440-4dca-979e-9b6b5b2d5f2f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1d40cd86cff4c3e58e88f9d17a551dc789bd1db4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398210"
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

