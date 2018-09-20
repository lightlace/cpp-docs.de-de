---
title: ABC-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- ABC
dev_langs:
- C++
helpviewer_keywords:
- ABC structure [MFC]
ms.assetid: 32663839-c3b7-4f47-896c-b15329c96bc8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6a977e3f0efd763ee416348f11e3c6b016c0d42e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373711"
---
# <a name="abc-structure"></a>ABC-Struktur

Die `ABC` Struktur enthält die Breite eines Zeichens in eine TrueType-Schriftart.

## <a name="syntax"></a>Syntax

```
typedef struct _ABC { /* abc */
    int abcA;
    UINT abcB;
    int abcC;
} ABC;
```

#### <a name="parameters"></a>Parameter

*abcA*<br/>
Gibt den Abstand ein des Zeichens. Der Abstand ein ist der Abstand und die aktuelle Position vor dem Zeichnen des Symbols Zeichen hinzuzufügen.

*abcB*<br/>
Gibt den Abstand B des Zeichens. Der Abstand B ist die Breite des gezeichneten Bereich des Symbols für das Zeichen an.

*abcC*<br/>
Gibt den Abstand C des Zeichens. Der C-Abstand wird der Abstand der aktuellen Position Leerraum auf der rechten Seite des Symbols für das Zeichen zu hinzu.

## <a name="remarks"></a>Hinweise

Die gesamte Breite eines Zeichens ist die Summe der Leerzeichen A, B und C. A- oder der C-Space kann an Underhangs oder Überhängen negativ sein.

## <a name="requirements"></a>Anforderungen

**Header:** wingdi.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)


