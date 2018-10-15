---
title: POINT-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- POINT
- LPPOINT
dev_langs:
- C++
helpviewer_keywords:
- LPPOINT structure [MFC]
- POINT structure [MFC]
ms.assetid: 965736d8-4e53-41b6-9b8b-6961992dd21f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1d2aaafe65b742ded6c0adf49fac430679e24380
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2018
ms.locfileid: "49334529"
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
