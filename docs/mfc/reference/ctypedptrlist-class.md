---
title: CTypedPtrList-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTypedPtrList
- AFXTEMPL/CTypedPtrList
- AFXTEMPL/CTypedPtrList::AddHead
- AFXTEMPL/CTypedPtrList::AddTail
- AFXTEMPL/CTypedPtrList::GetAt
- AFXTEMPL/CTypedPtrList::GetHead
- AFXTEMPL/CTypedPtrList::GetNext
- AFXTEMPL/CTypedPtrList::GetPrev
- AFXTEMPL/CTypedPtrList::GetTail
- AFXTEMPL/CTypedPtrList::RemoveHead
- AFXTEMPL/CTypedPtrList::RemoveTail
- AFXTEMPL/CTypedPtrList::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CTypedPtrList [MFC], AddHead
- CTypedPtrList [MFC], AddTail
- CTypedPtrList [MFC], GetAt
- CTypedPtrList [MFC], GetHead
- CTypedPtrList [MFC], GetNext
- CTypedPtrList [MFC], GetPrev
- CTypedPtrList [MFC], GetTail
- CTypedPtrList [MFC], RemoveHead
- CTypedPtrList [MFC], RemoveTail
- CTypedPtrList [MFC], SetAt
ms.assetid: c273096e-1756-4340-864b-4a08b674a65e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 758be6cfec0c4d70ebf632eaf90e3623632ffbe5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417513"
---
# <a name="ctypedptrlist-class"></a>CTypedPtrList-Klasse

Stellt einen typsicheren Wrapper für Objekte der Klasse `CPtrList`bereit.

## <a name="syntax"></a>Syntax

```
template<class BASE_CLASS, class TYPE>
class CTypedPtrList : public BASE_CLASS
```

#### <a name="parameters"></a>Parameter

*BASE_CLASS*<br/>
Die Basisklasse der typisierter Zeiger List-Klasse; muss eine Zeiger-List-Klasse ( `CObList` oder `CPtrList`).

*TYPE*<br/>
Der Typ der Elemente in der Basisklasse-Liste gespeichert.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CTypedPtrList::AddHead](#addhead)|Fügt ein Element (oder alle Elemente in einer anderen Liste) an den Anfang der Liste (macht eines neuen kopfteils) an.|
|[CTypedPtrList::AddTail](#addtail)|Fügt ein Element (oder alle Elemente in einer anderen Liste) am Ende der Liste (wird einem neuen Ende) an.|
|[CTypedPtrList::GetAt](#getat)|Ruft das Element an einer bestimmten Position.|
|[CTypedPtrList::GetHead](#gethead)|Gibt zurück, das Head-Element der Liste (darf nicht leer sein).|
|[CTypedPtrList::GetNext](#getnext)|Ruft das nächste Element durchlaufen werden können.|
|[CTypedPtrList::GetPrev](#getprev)|Ruft das vorherige Element durchlaufen werden können.|
|[CTypedPtrList::GetTail](#gettail)|Gibt das Ende-Element der Liste (darf nicht leer sein).|
|[CTypedPtrList::RemoveHead](#removehead)|Entfernt das Element vom Anfang der Liste.|
|[CTypedPtrList::RemoveTail](#removetail)|Entfernt das Element vom Ende der Liste.|
|[CTypedPtrList::SetAt](#setat)|Legt das Element an einer bestimmten Position fest.|

## <a name="remarks"></a>Hinweise

Bei Verwendung von `CTypedPtrList` statt `CObList` oder `CPtrList`, die Typprüfung C++-Funktion hilft, Fehler aufgrund nicht übereinstimmender Zeigertypen zu vermeiden.

Darüber hinaus die `CTypedPtrList` Wrapper Großteil der Umwandlung, die erforderlich sein würde, wenn Sie verwendet haben, führt `CObList` oder `CPtrList`.

Da alle `CTypedPtrList` Funktionen werden Inline, die Verwendung dieser Vorlage erheblich wirkt sich nicht die Größe oder Geschwindigkeit Ihres Codes.

Listen von abgeleiteten `CObList` serialisiert werden kann, aber die von abgeleiteten `CPtrList` nicht möglich.

Wenn ein `CTypedPtrList`-Objekt gelöscht wird oder dessen Elemente entfernt werden, werden nur die Zeiger, und nicht die Entitäten, auf die sie verweisen, entfernt.

Weitere Informationen zur Verwendung von `CTypedPtrList`, finden Sie in den Artikeln [Sammlungen](../../mfc/collections.md) und [vorlagenbasierte Klassen](../../mfc/template-based-classes.md).

## <a name="example"></a>Beispiel

In diesem Beispiel erstellt eine Instanz des `CTypedPtrList`, fügt ein Objekt, serialisiert die Liste auf den Datenträger und löscht dann das Objekt:

[!code-cpp[NVC_MFCCollections#110](../../mfc/codesnippet/cpp/ctypedptrlist-class_1.cpp)]

[!code-cpp[NVC_MFCCollections#111](../../mfc/codesnippet/cpp/ctypedptrlist-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`BASE_CLASS`

`_CTypedPtrList`

`CTypedPtrList`

## <a name="requirements"></a>Anforderungen

**Header:** afxtempl.h

##  <a name="addhead"></a>  CTypedPtrList::AddHead

Diese Memberfunktion ruft `BASE_CLASS` **:: AddHead**.

```
POSITION AddHead(TYPE newElement);
void AddHead(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```

### <a name="parameters"></a>Parameter

*TYPE*<br/>
Der Typ der Elemente in der Basisklasse-Liste gespeichert.

*newElement*<br/>
Der Objektzeiger zu dieser Liste hinzugefügt werden. Es ist ein NULL-Wert zulässig.

*BASE_CLASS*<br/>
Die Basisklasse der typisierter Zeiger List-Klasse; muss eine Zeiger-List-Klasse ( [CObList](../../mfc/reference/coblist-class.md) oder [CPtrList](../../mfc/reference/cptrlist-class.md)).

*pNewList*<br/>
Ein Zeiger auf einen anderen [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) Objekt. Die Elemente im *pNewList* wird zu dieser Liste hinzugefügt werden.

### <a name="return-value"></a>Rückgabewert

Die erste Version gibt den Wert für die POSITION des neu eingefügten Elements zurück.

### <a name="remarks"></a>Hinweise

Die erste Version Fügt ein neues Element vor dem Anfang der Liste hinzu. Die zweite Version Fügt eine andere Liste von Elementen vor dem hinzu.

##  <a name="addtail"></a>  CTypedPtrList::AddTail

Diese Memberfunktion ruft `BASE_CLASS` **:: AddTail**.

```
POSITION AddTail(TYPE newElement);
void AddTail(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```

### <a name="parameters"></a>Parameter

*TYPE*<br/>
Der Typ der Elemente in der Basisklasse-Liste gespeichert.

*newElement*<br/>
Der Objektzeiger zu dieser Liste hinzugefügt werden. Es ist ein NULL-Wert zulässig.

*BASE_CLASS*<br/>
Die Basisklasse der typisierter Zeiger List-Klasse; muss eine Zeiger-List-Klasse ( [CObList](../../mfc/reference/coblist-class.md) oder [CPtrList](../../mfc/reference/cptrlist-class.md)).

*pNewList*<br/>
Ein Zeiger auf einen anderen [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) Objekt. Die Elemente im *pNewList* wird zu dieser Liste hinzugefügt werden.

### <a name="return-value"></a>Rückgabewert

Die erste Version gibt den Wert für die POSITION des neu eingefügten Elements zurück.

### <a name="remarks"></a>Hinweise

Die erste Version Fügt ein neues Element nach dem Ende der Liste hinzu. Die zweite Version Fügt eine andere Liste von Elementen nach dem Ende der Liste hinzu.

##  <a name="getat"></a>  CTypedPtrList::GetAt

Eine Variable vom Typ POSITION ist ein Schlüssel für die Liste.

```
TYPE& GetAt(POSITION position);
TYPE GetAt(POSITION position) const;
```

### <a name="parameters"></a>Parameter

*TYPE*<br/>
Der Vorlagenparameter, die den Typ der Elemente in der Liste gespeichert.

*Position*<br/>
Eine Positionswert, der von einem vorherigen zurückgegebene `GetHeadPosition` oder `Find` Aufruf der Memberfunktion.

### <a name="return-value"></a>Rückgabewert

Wenn die Liste zugegriffen wird, über einen Zeiger auf eine `const CTypedPtrList`, klicken Sie dann `GetAt` gibt einen Zeiger des Typs, die vom Vorlagenparameter angegeben *Typ*. Dadurch können die Funktion, die nur auf der rechten Seite einer zuweisungsanweisung verwendet werden und daher die Liste vor Änderungen schützt.

Wenn die Liste direkt oder über einen Zeiger zugegriffen wird eine `CTypedPtrList`, klicken Sie dann `GetAt` gibt einen Verweis auf einen Zeiger des Typs durch die Template-Parameter angegebenen *Typ*. Dadurch können die Funktion, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und dadurch die Einträge in der Liste geändert werden kann.

### <a name="remarks"></a>Hinweise

Es ist nicht identisch mit einem Index, und Sie können nicht für ein Positionswert selbst. `GetAt` Ruft die `CObject` Zeiger, die einer bestimmten Position zugeordnet.

Sie müssen sicherstellen, dass Ihre POSITION-Wert eine gültige Position in der Liste darstellt. Wenn er ungültig ist, bestätigt Sie dann die Debugversion der Microsoft Foundation Class-Bibliothek.

Diese Inlinefunktion ruft `BASE_CLASS` **:: GetAt**.

##  <a name="gethead"></a>  CTypedPtrList::GetHead

Ruft ab, der Zeiger, der das Head-Element dieser Liste darstellt.

```
TYPE& GetHead();
TYPE GetHead() const;
```

### <a name="parameters"></a>Parameter

*TYPE*<br/>
Der Vorlagenparameter, die den Typ der Elemente in der Liste gespeichert.

### <a name="return-value"></a>Rückgabewert

Wenn die Liste zugegriffen wird, über einen Zeiger auf eine `const CTypedPtrList`, klicken Sie dann `GetHead` gibt einen Zeiger des Typs, die vom Vorlagenparameter angegeben *Typ*. Dadurch können die Funktion, die nur auf der rechten Seite einer zuweisungsanweisung verwendet werden und daher die Liste vor Änderungen schützt.

Wenn die Liste direkt oder über einen Zeiger zugegriffen wird eine `CTypedPtrList`, klicken Sie dann `GetHead` gibt einen Verweis auf einen Zeiger des Typs durch die Template-Parameter angegebenen *Typ*. Dadurch können die Funktion, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und dadurch die Einträge in der Liste geändert werden kann.

### <a name="remarks"></a>Hinweise

Sie müssen sicherstellen, dass die Liste nicht leer ist, bevor der Aufruf ist `GetHead`. Wenn die Liste leer ist, bestätigt Sie dann die Debugversion der Microsoft Foundation Class-Bibliothek. Verwendung ["isEmpty"](../../mfc/reference/coblist-class.md#isempty) um sicherzustellen, dass die Liste Elemente enthält.

##  <a name="getnext"></a>  CTypedPtrList::GetNext

Ruft das List-Element identifizierte *rposition zurück*, legt dann *rposition zurück* auf den Wert für die POSITION des nächsten Eintrag in der Liste.

```
TYPE& GetNext(POSITION& rPosition);
TYPE GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parameter

*TYPE*<br/>
Der Vorlagenparameter, die den Typ der Elemente in dieser Liste enthalten sind.

*rposition zurück*<br/>
Ein Verweis auf eine Positionswert, der von einem vorherigen zurückgegebene `GetNext`, `GetHeadPosition`, oder anderer Aufruf der Memberfunktion.

### <a name="return-value"></a>Rückgabewert

Wenn die Liste zugegriffen wird, über einen Zeiger auf eine `const CTypedPtrList`, klicken Sie dann `GetNext` gibt einen Zeiger des Typs, die vom Vorlagenparameter angegeben *Typ*. Dadurch können die Funktion, die nur auf der rechten Seite einer zuweisungsanweisung verwendet werden und daher die Liste vor Änderungen schützt.

Wenn die Liste direkt oder über einen Zeiger zugegriffen wird eine `CTypedPtrList`, klicken Sie dann `GetNext` gibt einen Verweis auf einen Zeiger des Typs durch die Template-Parameter angegebenen *Typ*. Dadurch können die Funktion, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und dadurch die Einträge in der Liste geändert werden kann.

### <a name="remarks"></a>Hinweise

Sie können `GetNext` in einer Schleife Vorwärtsiteration, wenn Sie die ursprüngliche Position mit einem Aufruf von einrichten `GetHeadPosition` oder [CPtrList::Find](../../mfc/reference/coblist-class.md#find).

Sie müssen sicherstellen, dass Ihre POSITION-Wert eine gültige Position in der Liste darstellt. Wenn er ungültig ist, bestätigt Sie dann die Debugversion der Microsoft Foundation Class-Bibliothek.

Ist das abgerufene Element das letzte Element in der Liste aus, klicken Sie dann den neuen Wert des *rposition zurück* auf NULL festgelegt ist.

Es ist möglich, ein Element innerhalb einer Iteration zu entfernen. Siehe das Beispiel für [CObList::RemoveAt](../../mfc/reference/coblist-class.md#removeat).

##  <a name="getprev"></a>  CTypedPtrList::GetPrev

Ruft das List-Element identifizierte *rposition zurück*, legt dann *rposition zurück* auf den Wert für die POSITION des vorherigen Eintrags in der Liste.

```
TYPE& GetPrev(POSITION& rPosition);
TYPE GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parameter

*TYPE*<br/>
Der Vorlagenparameter, die den Typ der Elemente in dieser Liste enthalten sind.

*rposition zurück*<br/>
Ein Verweis auf eine Positionswert, der von einem vorherigen zurückgegebene `GetPrev` oder anderen Aufruf der Memberfunktion.

### <a name="return-value"></a>Rückgabewert

Wenn die Liste zugegriffen wird, über einen Zeiger auf eine `const CTypedPtrList`, klicken Sie dann `GetPrev` gibt einen Zeiger des Typs, die vom Vorlagenparameter angegeben *Typ*. Dadurch können die Funktion, die nur auf der rechten Seite einer zuweisungsanweisung verwendet werden und daher die Liste vor Änderungen schützt.

Wenn die Liste direkt oder über einen Zeiger zugegriffen wird eine `CTypedPtrList`, klicken Sie dann `GetPrev` gibt einen Verweis auf einen Zeiger des Typs durch die Template-Parameter angegebenen *Typ*. Dadurch können die Funktion, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und dadurch die Einträge in der Liste geändert werden kann.

### <a name="remarks"></a>Hinweise

Sie können `GetPrev` in einer umgekehrte Iteration-Schleife, wenn Sie die ursprüngliche Position mit einem Aufruf von einrichten `GetTailPosition` oder `Find`.

Sie müssen sicherstellen, dass Ihre POSITION-Wert eine gültige Position in der Liste darstellt. Wenn er ungültig ist, bestätigt Sie dann die Debugversion der Microsoft Foundation Class-Bibliothek.

Wenn das abgerufene Element der erste in der Liste aus, klicken Sie dann der neue Wert des ist *rposition zurück* auf NULL festgelegt ist.

##  <a name="gettail"></a>  CTypedPtrList::GetTail

Ruft ab, der Zeiger, der das Head-Element dieser Liste darstellt.

```
TYPE& GetTail();
TYPE GetTail() const;
```

### <a name="parameters"></a>Parameter

*TYPE*<br/>
Der Vorlagenparameter, die den Typ der Elemente in der Liste gespeichert.

### <a name="return-value"></a>Rückgabewert

Wenn die Liste zugegriffen wird, über einen Zeiger auf eine `const CTypedPtrList`, klicken Sie dann `GetTail` gibt einen Zeiger des Typs, die vom Vorlagenparameter angegeben *Typ*. Dadurch können die Funktion, die nur auf der rechten Seite einer zuweisungsanweisung verwendet werden und daher die Liste vor Änderungen schützt.

Wenn die Liste direkt oder über einen Zeiger zugegriffen wird eine `CTypedPtrList`, klicken Sie dann `GetTail` gibt einen Verweis auf einen Zeiger des Typs durch die Template-Parameter angegebenen *Typ*. Dadurch können die Funktion, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und dadurch die Einträge in der Liste geändert werden kann.

### <a name="remarks"></a>Hinweise

Sie müssen sicherstellen, dass die Liste nicht leer ist, bevor der Aufruf ist `GetTail`. Wenn die Liste leer ist, bestätigt Sie dann die Debugversion der Microsoft Foundation Class-Bibliothek. Verwendung ["isEmpty"](../../mfc/reference/coblist-class.md#isempty) um sicherzustellen, dass die Liste Elemente enthält.

##  <a name="removehead"></a>  CTypedPtrList::RemoveHead

Entfernt das Element vom Anfang der Liste aus, und gibt sie zurück.

```
TYPE RemoveHead();
```

### <a name="parameters"></a>Parameter

*TYPE*<br/>
Der Vorlagenparameter, die den Typ der Elemente in der Liste gespeichert.

### <a name="return-value"></a>Rückgabewert

Der Zeiger bereits am Anfang der Liste. This-Zeiger ist, vom durch die Template-Parameter angegebenen Typ *Typ*.

### <a name="remarks"></a>Hinweise

Sie müssen sicherstellen, dass die Liste nicht leer ist, bevor der Aufruf ist `RemoveHead`. Wenn die Liste leer ist, bestätigt Sie dann die Debugversion der Microsoft Foundation Class-Bibliothek. Verwendung ["isEmpty"](../../mfc/reference/coblist-class.md#isempty) um sicherzustellen, dass die Liste Elemente enthält.

##  <a name="removetail"></a>  CTypedPtrList::RemoveTail

Entfernt das Element aus das Ende der Liste aus, und gibt sie zurück.

```
TYPE RemoveTail();
```

### <a name="parameters"></a>Parameter

*TYPE*<br/>
Der Vorlagenparameter, die den Typ der Elemente in der Liste gespeichert.

### <a name="return-value"></a>Rückgabewert

Der Zeiger bereits am Ende der Liste. This-Zeiger ist, vom durch die Template-Parameter angegebenen Typ *Typ*.

### <a name="remarks"></a>Hinweise

Sie müssen sicherstellen, dass die Liste nicht leer ist, bevor der Aufruf ist `RemoveTail`. Wenn die Liste leer ist, bestätigt Sie dann die Debugversion der Microsoft Foundation Class-Bibliothek. Verwendung ["isEmpty"](../../mfc/reference/coblist-class.md#isempty) um sicherzustellen, dass die Liste Elemente enthält.

##  <a name="setat"></a>  CTypedPtrList::SetAt

Diese Memberfunktion ruft `BASE_CLASS` **:: SetAt**.

```
void SetAt(POSITION pos, TYPE newElement);
```

### <a name="parameters"></a>Parameter

*POS*<br/>
Die POSITION des Elements festgelegt werden.

*TYPE*<br/>
Der Typ der Elemente in der Basisklasse-Liste gespeichert.

*newElement*<br/>
Der Objektzeiger in der Liste geschrieben werden sollen.

### <a name="remarks"></a>Hinweise

Eine Variable vom Typ POSITION ist ein Schlüssel für die Liste. Es ist nicht identisch mit einem Index, und Sie können nicht für ein Positionswert selbst. `SetAt` Schreibt den Objektzeiger, der angegebenen Position in der Liste.

Sie müssen sicherstellen, dass Ihre POSITION-Wert eine gültige Position in der Liste darstellt. Wenn er ungültig ist, bestätigt Sie dann die Debugversion der Microsoft Foundation Class-Bibliothek.

Weitere Hinweise finden Sie unter [CObList::SetAt](../../mfc/reference/coblist-class.md#setat).

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel erfassen](../../visual-cpp-samples.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CPtrList-Klasse](../../mfc/reference/cptrlist-class.md)<br/>
[CObList-Klasse](../../mfc/reference/coblist-class.md)
