---
title: XFORM-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- XFORM
dev_langs:
- C++
helpviewer_keywords:
- XFORM structure [MFC]
ms.assetid: 4fb4ef5b-05d2-4884-82d1-1cb8f7be6302
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ab1a2fe23f364dc35a2368d325db5e4274fc8e64
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411637"
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

