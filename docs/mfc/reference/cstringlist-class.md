---
title: CStringList-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStringList
- AFXCOLL/CStringList
- AFXCOLL/CObList::CObList
- AFXCOLL/CObList::AddHead
- AFXCOLL/CObList::AddTail
- AFXCOLL/CObList::Find
- AFXCOLL/CObList::FindIndex
- AFXCOLL/CObList::GetAt
- AFXCOLL/CObList::GetCount
- AFXCOLL/CObList::GetHead
- AFXCOLL/CObList::GetHeadPosition
- AFXCOLL/CObList::GetNext
- AFXCOLL/CObList::GetPrev
- AFXCOLL/CObList::GetSize
- AFXCOLL/CObList::GetTail
- AFXCOLL/CObList::GetTailPosition
- AFXCOLL/CObList::InsertAfter
- AFXCOLL/CObList::InsertBefore
- AFXCOLL/CObList::IsEmpty
- AFXCOLL/CObList::RemoveAll
- AFXCOLL/CObList::RemoveAt
- AFXCOLL/CObList::RemoveHead
- AFXCOLL/CObList::RemoveTail
- AFXCOLL/CObList::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CObList [MFC], CObList
- CObList [MFC], AddHead
- CObList [MFC], AddTail
- CObList [MFC], Find
- CObList [MFC], FindIndex
- CObList [MFC], GetAt
- CObList [MFC], GetCount
- CObList [MFC], GetHead
- CObList [MFC], GetHeadPosition
- CObList [MFC], GetNext
- CObList [MFC], GetPrev
- CObList [MFC], GetSize
- CObList [MFC], GetTail
- CObList [MFC], GetTailPosition
- CObList [MFC], InsertAfter
- CObList [MFC], InsertBefore
- CObList [MFC], IsEmpty
- CObList [MFC], RemoveAll
- CObList [MFC], RemoveAt
- CObList [MFC], RemoveHead
- CObList [MFC], RemoveTail
- CObList [MFC], SetAt
ms.assetid: 310a7edb-263c-4bd2-ac43-0bfbfddc5a33
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3182a9f5a53c2f086800eb0eccb7d61e423e591
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439184"
---
# <a name="cstringlist-class"></a>CStringList-Klasse

Unterstützt Listen von `CString` -Objekten.

## <a name="syntax"></a>Syntax

```
class CStringList : public CObject
```

## <a name="members"></a>Member

Die Memberfunktionen der `CStringList` ähneln den Memberfunktionen der Klasse [CObList](../../mfc/reference/coblist-class.md). Aufgrund dieser Ähnlichkeit können Sie die `CObList`-Referenzdokumentation für Memberfunktionsbesonderheiten verwenden. Immer dort, wo ein `CObject` Zeiger als Rückgabewert, ersetzen Sie durch eine `CString` (keinen `CString` Zeiger). Immer dort, wo ein `CObject` Zeiger als Funktionsparameter, ersetzen Sie durch eine `LPCTSTR`.

`CObject*& CObList::GetHead() const;`

Beispielsweise übersetzt zu

`CString& CStringList::GetHead() const;`

und

`POSITION AddHead( CObject* <newElement> );`

wird übersetzt in

`POSITION AddHead( LPCTSTR <newElement> );`

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CObList::CObList](../../mfc/reference/coblist-class.md#coblist)|Erstellt eine leere Liste.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CObList::AddHead](../../mfc/reference/coblist-class.md#addhead)|Fügt ein Element (oder alle Elemente in einer anderen Liste) an den Anfang der Liste (macht eines neuen kopfteils) an.|
|[CObList::AddTail](../../mfc/reference/coblist-class.md#addtail)|Fügt ein Element (oder alle Elemente in einer anderen Liste) am Ende der Liste (wird einem neuen Ende) an.|
|[CObList::Find](../../mfc/reference/coblist-class.md#find)|Ruft die Position eines Elements durch Zeigerwert angegeben werden.|
|[CObList::FindIndex](../../mfc/reference/coblist-class.md#findindex)|Ruft die Position eines Elements durch einen nullbasierten Index angegeben.|
|[CObList::GetAt](../../mfc/reference/coblist-class.md#getat)|Ruft das Element an einer bestimmten Position.|
|[CObList::GetCount](../../mfc/reference/coblist-class.md#getcount)|Gibt die Anzahl der Elemente in der Liste zurück.|
|[CObList::GetHead](../../mfc/reference/coblist-class.md#gethead)|Gibt zurück, das Head-Element der Liste (darf nicht leer sein).|
|[CObList::GetHeadPosition](../../mfc/reference/coblist-class.md#getheadposition)|Gibt die Position der Head-Element der Liste zurück.|
|[CObList::GetNext](../../mfc/reference/coblist-class.md#getnext)|Ruft das nächste Element durchlaufen werden können.|
|[CObList::GetPrev](../../mfc/reference/coblist-class.md#getprev)|Ruft das vorherige Element durchlaufen werden können.|
|[CObList::GetSize](../../mfc/reference/coblist-class.md#getsize)|Gibt die Anzahl der Elemente in der Liste zurück.|
|[CObList::GetTail](../../mfc/reference/coblist-class.md#gettail)|Gibt das Ende-Element der Liste (darf nicht leer sein).|
|[CObList::GetTailPosition](../../mfc/reference/coblist-class.md#gettailposition)|Gibt die Position des Elements das Ende der Liste zurück.|
|[CObList::InsertAfter](../../mfc/reference/coblist-class.md#insertafter)|Fügt ein neues Element nach einer angegebenen Position ein.|
|[CObList::InsertBefore](../../mfc/reference/coblist-class.md#insertbefore)|Fügt ein neues Element vor einer angegebenen Position ein.|
|[CObList::IsEmpty](../../mfc/reference/coblist-class.md#isempty)|Testet, ob die Bedingung der leeren Liste (keine Elemente).|
|[CObList::RemoveAll](../../mfc/reference/coblist-class.md#removeall)|Entfernt alle Elemente aus dieser Liste.|
|[CObList::RemoveAt](../../mfc/reference/coblist-class.md#removeat)|Entfernt ein Element aus dieser Liste anhand der Position angegeben.|
|[CObList::RemoveHead](../../mfc/reference/coblist-class.md#removehead)|Entfernt das Element vom Anfang der Liste.|
|[CObList::RemoveTail](../../mfc/reference/coblist-class.md#removetail)|Entfernt das Element vom Ende der Liste.|
|[CObList::SetAt](../../mfc/reference/coblist-class.md#setat)|Legt das Element an einer bestimmten Position fest.|

## <a name="remarks"></a>Hinweise

Alle Vergleiche erfolgen nach Wert, was bedeutet, dass die Zeichen in der Zeichenfolge anstelle der Adressen, die Zeichenfolgen verglichen werden.

`CStringList` enthält das IMPLEMENT_SERIAL-Makro, um Serialisierung und die Sicherung der Elemente zu unterstützen. Wenn eine Liste der `CString` Objekte befindet sich in ein Archiv, das entweder mit einem überladenen Operator zum Einfügen oder mit der `Serialize` Memberfunktion jedes `CString` Element der Reihe nach serialisiert.

Wenn Sie eine Sicherung einzelner benötigen `CString` Elemente müssen Sie die Tiefe des sicherungskontexts auf 1 oder größer festlegen.

Weitere Informationen zur Verwendung von `CStringList`, finden Sie im Artikel [Sammlungen](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CStringList`

## <a name="requirements"></a>Anforderungen

**Header:** afxcoll.h

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel erfassen](../../visual-cpp-samples.md)<br/>
[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)



