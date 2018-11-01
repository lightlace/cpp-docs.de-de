---
title: ABCFLOAT-Struktur
ms.date: 11/04/2016
f1_keywords:
- ABCFLOAT
helpviewer_keywords:
- ABCFLOAT structure [MFC]
ms.assetid: 338e7e15-9d2c-42d0-aa80-273acfde5cc5
ms.openlocfilehash: b9e3923e8c70e38fe5efe959db8da43118cc6445
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50443658"
---
# <a name="abcfloat-structure"></a>ABCFLOAT-Struktur

Die `ABCFLOAT` Struktur enthält, die A, B und C die Breite eines Zeichens der Schriftart.

## <a name="syntax"></a>Syntax

```
typedef struct _ABCFLOAT { /* abcf */
    FLOAT abcfA;
    FLOAT abcfB;
    FLOAT abcfC;
} ABCFLOAT;
```

#### <a name="parameters"></a>Parameter

*abcfA*<br/>
Gibt den Abstand ein des Zeichens. Der Abstand ein ist der Abstand und die aktuelle Position vor dem Zeichnen des Symbols Zeichen hinzuzufügen.

*abcfB*<br/>
Gibt den Abstand B des Zeichens. Der Abstand B ist die Breite des gezeichneten Bereich des Symbols für das Zeichen an.

*abcfC*<br/>
Gibt den Abstand C des Zeichens. Der C-Abstand wird der Abstand der aktuellen Position Leerraum auf der rechten Seite des Symbols für das Zeichen zu hinzu.

## <a name="remarks"></a>Hinweise

Die Breite A, B und C werden auf der Basis-Linie der Schriftart gemessen. Das Inkrement Zeichen (Gesamtbreite), der ein Zeichen ist die Summe der Leerzeichen A, B und C. A- oder der C-Space kann an Underhangs oder Überhängen negativ sein.

## <a name="requirements"></a>Anforderungen

**Header:** wingdi.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)

