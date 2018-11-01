---
title: CPtrList-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPtrList
dev_langs:
- C++
helpviewer_keywords:
- lists, generic
- CPtrList class [MFC]
- generic lists
ms.assetid: 4139a09c-4338-4f42-9eea-51336120b43c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 97eeeaaa2eea237eebda4f945f2c810268f406cd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46384961"
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
