---
title: RECT-Struktur
ms.date: 11/04/2016
f1_keywords:
- LPRECT
- RECT
helpviewer_keywords:
- RECT structure [MFC]
- LPRECT structure [MFC]
ms.assetid: 1b3160de-64e9-40d1-89eb-af3e0fd6acf0
ms.openlocfilehash: 1cb997fc0f1ec89eabf5e4d2c2c5ccb15e3bafec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50549010"
---
# <a name="rect-structure"></a>RECT-Struktur

Die `RECT`-Struktur definiert die Koordinaten der oberen linken und der unteren rechten Ecke eines Rechtecks.

## <a name="syntax"></a>Syntax

```
typedef struct tagRECT {
    LONG left;
    LONG top;
    LONG right;
    LONG bottom;
} RECT;
```

## <a name="members"></a>Member

`left`<br/>
Gibt die X-Koordinate der oberen linken Ecke eines Rechtecks an.

`top`<br/>
Gibt die Y-Koordinate der oberen linken Ecke eines Rechtecks an.

`right`<br/>
Gibt die X-Koordinate der unteren rechten Ecke eines Rechtecks an.

`bottom`<br/>
Gibt die Y-Koordinate der unteren rechten Ecke eines Rechtecks an.

## <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#38](../../mfc/codesnippet/cpp/rect-structure1_1.cpp)]

## <a name="requirements"></a>Anforderungen

**Header:** windef.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CRect-Klasse](../../atl-mfc-shared/reference/crect-class.md)
