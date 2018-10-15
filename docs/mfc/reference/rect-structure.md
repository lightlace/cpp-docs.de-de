---
title: RECT-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- LPRECT
- RECT
dev_langs:
- C++
helpviewer_keywords:
- RECT structure [MFC]
- LPRECT structure [MFC]
ms.assetid: 1b3160de-64e9-40d1-89eb-af3e0fd6acf0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eae2b248f4aa4586bf6453dcc37b521387327d25
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2018
ms.locfileid: "49334535"
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
