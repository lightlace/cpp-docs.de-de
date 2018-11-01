---
title: POINT-Struktur
ms.date: 10/12/2018
f1_keywords:
- POINT
- LPPOINT
helpviewer_keywords:
- LPPOINT structure [MFC]
- POINT structure [MFC]
ms.assetid: 965736d8-4e53-41b6-9b8b-6961992dd21f
ms.openlocfilehash: c53f250b714c66e74a12432b879cbc4bcc1fd88d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50646900"
---
# <a name="point-structure"></a>POINT-Struktur

Die `POINT` Struktur definiert, das "X"*-* und y-Koordinaten eines Punkts.

## <a name="syntax"></a>Syntax

```
typedef struct tagPOINT {
    LONG x;
    LONG y;
} POINT;
```

#### <a name="parameters"></a>Parameter

*w*<br/>
Gibt die x-Koordinate eines Punkts an.

*y*<br/>
Gibt die y-Koordinate eines Punkts an.

## <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#37](../../mfc/codesnippet/cpp/point-structure1_1.cpp)]

## <a name="requirements"></a>Anforderungen

**Header:** windef.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CPoint-Klasse](../../atl-mfc-shared/reference/cpoint-class.md)
