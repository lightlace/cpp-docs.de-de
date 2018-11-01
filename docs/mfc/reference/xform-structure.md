---
title: XFORM-Struktur
ms.date: 11/04/2016
f1_keywords:
- XFORM
helpviewer_keywords:
- XFORM structure [MFC]
ms.assetid: 4fb4ef5b-05d2-4884-82d1-1cb8f7be6302
ms.openlocfilehash: 621a01accf3c323f8098da68667f06f48b9d169b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50457252"
---
# <a name="xform-structure"></a>XFORM-Struktur

Die `XFORM` Struktur weist folgende Form:

## <a name="syntax"></a>Syntax

```
typedef struct  tagXFORM {  /* xfrm */
    FLOAT eM11;
    FLOAT eM12;
    FLOAT eM21;
    FLOAT eM22;
    FLOAT eDx;
    FLOAT eDy;
} XFORM;
```

## <a name="remarks"></a>Hinweise

Die `XFORM` Struktur gibt an, einen Raum, um die Seite-Space-Transformation. Die `eDx` und `eDy` Member geben die horizontalen und vertikalen Translation-Komponenten. Die folgende Tabelle zeigt, wie die anderen Mitglieder abhängig vom Vorgang verwendet werden:

|Vorgang|eM11|eM12|eM21|eM22|
|---------------|----------|----------|----------|----------|
|`Rotation`|Kosinus der Drehwinkel für Bezeichnungen|Sinus von Drehwinkel für Bezeichnungen|Negative Sinus der Drehwinkel für Bezeichnungen|Kosinus der Drehwinkel für Bezeichnungen|
|`Scaling`|Horizontale Skalierung-Komponente|Nothing|Nothing|Vertikale Skalierung-Komponente|
|`Shear`|Nothing|Horizontale Verhältnismäßigkeit-Konstante|Vertikale Verhältnismäßigkeit-Konstante|Nothing|
|`Reflection`|Horizontale Reflektion-Komponente|Nothing|Nothing|Vertikale Reflektion-Komponente|

## <a name="requirements"></a>Anforderungen

**Header:** wingdi.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)

