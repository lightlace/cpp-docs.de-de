---
title: CPtrList-Klasse
ms.date: 11/04/2016
f1_keywords:
- CPtrList
helpviewer_keywords:
- lists, generic
- CPtrList class [MFC]
- generic lists
ms.assetid: 4139a09c-4338-4f42-9eea-51336120b43c
ms.openlocfilehash: 5b88b0950b3b46f9738bd26080883c00d46f8555
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372438"
---
# <a name="cptrlist-class"></a>CPtrList-Klasse

Unterstützt Listen void-Zeigern.

## <a name="syntax"></a>Syntax

```
class CPtrList : public CObject
```

## <a name="members"></a>Member

Die Memberfunktionen der `CPtrList` ähneln den Memberfunktionen der Klasse [CObList](../../mfc/reference/coblist-class.md). Aufgrund dieser Ähnlichkeit können Sie die `CObList`-Referenzdokumentation für Memberfunktionsbesonderheiten verwenden. Immer dort, wo ein `CObject` Zeiger als Funktionsparameter oder Rückgabewert, ersetzen Sie durch einen Zeiger auf **"void"**.

`CObject*& CObList::GetHead() const;`

Beispielsweise übersetzt zu

`void*& CPtrList::GetHead() const;`

## <a name="remarks"></a>Hinweise

`CPtrList` enthält das IMPLEMENT_DYNAMIC-Makro, um die Laufzeit laufzeittypenzugriff und zum unterstützen einer `CDumpContext` Objekt. Wenn Sie eine Sicherung einzelner Zeigerlistenelemente benötigen, müssen Sie die Tiefe des Sicherungskontexts auf 1 oder größer festlegen.

Zeigerlisten können nicht serialisiert werden.

Wenn ein `CPtrList`-Objekt gelöscht wird oder dessen Elemente entfernt werden, werden nur die Zeiger, und nicht die Entitäten, auf die sie verweisen, entfernt.

Weitere Informationen zur Verwendung von `CPtrList`, finden Sie im Artikel [Sammlungen](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CPtrList`

## <a name="requirements"></a>Anforderungen

**Header:** afxcoll.h

## <a name="see-also"></a>Siehe auch

[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CObList-Klasse](../../mfc/reference/coblist-class.md)
