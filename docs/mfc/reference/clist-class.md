---
title: CList-Klasse
ms.date: 11/04/2016
f1_keywords:
- CList
- AFXTEMPL/CList
- AFXTEMPL/CList::CList
- AFXTEMPL/CList::AddHead
- AFXTEMPL/CList::AddTail
- AFXTEMPL/CList::Find
- AFXTEMPL/CList::FindIndex
- AFXTEMPL/CList::GetAt
- AFXTEMPL/CList::GetCount
- AFXTEMPL/CList::GetHead
- AFXTEMPL/CList::GetHeadPosition
- AFXTEMPL/CList::GetNext
- AFXTEMPL/CList::GetPrev
- AFXTEMPL/CList::GetSize
- AFXTEMPL/CList::GetTail
- AFXTEMPL/CList::GetTailPosition
- AFXTEMPL/CList::InsertAfter
- AFXTEMPL/CList::InsertBefore
- AFXTEMPL/CList::IsEmpty
- AFXTEMPL/CList::RemoveAll
- AFXTEMPL/CList::RemoveAt
- AFXTEMPL/CList::RemoveHead
- AFXTEMPL/CList::RemoveTail
- AFXTEMPL/CList::SetAt
helpviewer_keywords:
- CList [MFC], CList
- CList [MFC], AddHead
- CList [MFC], AddTail
- CList [MFC], Find
- CList [MFC], FindIndex
- CList [MFC], GetAt
- CList [MFC], GetCount
- CList [MFC], GetHead
- CList [MFC], GetHeadPosition
- CList [MFC], GetNext
- CList [MFC], GetPrev
- CList [MFC], GetSize
- CList [MFC], GetTail
- CList [MFC], GetTailPosition
- CList [MFC], InsertAfter
- CList [MFC], InsertBefore
- CList [MFC], IsEmpty
- CList [MFC], RemoveAll
- CList [MFC], RemoveAt
- CList [MFC], RemoveHead
- CList [MFC], RemoveTail
- CList [MFC], SetAt
ms.assetid: 6f6273c3-c8f6-47f5-ac2a-0a950379ae5d
ms.openlocfilehash: 10991745fb5ccdac145f4b1d589e7d59c6ed6f4e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50513957"
---
# <a name="clist-class"></a>CList-Klasse

Unterstützt sortierte Listen mit Objekten, die nicht eindeutig sein müssen, und auf die sequenziell oder über den Wert zugegriffen werden kann.

## <a name="syntax"></a>Syntax

```
template<class TYPE, class ARG_TYPE = const TYPE&>
class CList : public CObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CList::CList](#clist)|Erstellt eine leere sortierte Liste an.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CList::AddHead](#addhead)|Fügt ein Element (oder alle Elemente in einer anderen Liste) an den Anfang der Liste (macht eines neuen kopfteils) an.|
|[CList::AddTail](#addtail)|Fügt ein Element (oder alle Elemente in einer anderen Liste) am Ende der Liste (wird einem neuen Ende) an.|
|[CList::Find](#find)|Ruft die Position eines Elements durch Zeigerwert angegeben werden.|
|[CList::FindIndex](#findindex)|Ruft die Position eines Elements durch einen nullbasierten Index angegeben.|
|[CList::GetAt](#getat)|Ruft das Element an einer bestimmten Position.|
|[CList::GetCount](#getcount)|Gibt die Anzahl der Elemente in der Liste zurück.|
|[CList::GetHead](#gethead)|Gibt zurück, das Head-Element der Liste (darf nicht leer sein).|
|[CList::GetHeadPosition](#getheadposition)|Gibt die Position der Head-Element der Liste zurück.|
|[CList::GetNext](#getnext)|Ruft das nächste Element durchlaufen werden können.|
|[CList::GetPrev](#getprev)|Ruft das vorherige Element durchlaufen werden können.|
|[CList::GetSize](#getsize)|Gibt die Anzahl der Elemente in der Liste zurück.|
|[CList::GetTail](#gettail)|Gibt das Ende-Element der Liste (darf nicht leer sein).|
|[CList::GetTailPosition](#gettailposition)|Gibt die Position des Elements das Ende der Liste zurück.|
|[CList::InsertAfter](#insertafter)|Fügt ein neues Element nach einer angegebenen Position ein.|
|[CList::InsertBefore](#insertbefore)|Fügt ein neues Element vor einer angegebenen Position ein.|
|[CList::IsEmpty](#isempty)|Testet, ob die Bedingung der leeren Liste (keine Elemente).|
|[CList::RemoveAll](#removeall)|Entfernt alle Elemente aus dieser Liste.|
|[CList::RemoveAt](#removeat)|Entfernt ein Element aus dieser Liste anhand der Position angegeben.|
|[CList::RemoveHead](#removehead)|Entfernt das Element vom Anfang der Liste.|
|[CList::RemoveTail](#removetail)|Entfernt das Element vom Ende der Liste.|
|[CList::SetAt](#setat)|Legt das Element an einer bestimmten Position fest.|

#### <a name="parameters"></a>Parameter

*TYPE*<br/>
Typ des Objekts in der Liste gespeichert.

*ARG_TYPE*<br/>
Der Typ, der in der Liste gespeicherten Objekte zu verweisen. Dies kann ein Verweis sein.

## <a name="remarks"></a>Hinweise

`CList` Listen Verhalten sich wie doppelt verknüpfte Listen.

Eine Variable vom Typ POSITION ist ein Schlüssel für die Liste. Sie können eine positionsvariable als Iterator verwenden, eine Liste eines Lesezeichens zu einen Ort zu speichern und sequenziell zu durchlaufen. Eine Position ist identisch mit einem Index jedoch nicht.

Element einfügen erfolgt sehr schnell, an der Spitze der Liste am Ende und an einer bekannten POSITION. Eine sequenzielle Suche ist erforderlich, um ein Element nach Wert oder Index zu suchen. Diese Suche möglich langsam, wenn die Liste lang ist.

Wenn Sie eine Sicherung der einzelnen Elemente in der Liste benötigen, müssen Sie die Tiefe des sicherungskontexts auf 1 oder größer festlegen.

Bestimmte Memberfunktionen dieser Klasse rufen globale Hilfsfunktionen, die angepasst werden müssen, für die meisten Verwendungen von der `CList` Klasse. Finden Sie unter [Auflistungsklasse](../../mfc/reference/collection-class-helpers.md) im Abschnitt "Makros und Globals".

Weitere Informationen zur Verwendung von `CList`, finden Sie im Artikel [Sammlungen](../../mfc/collections.md).

## <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#35](../../mfc/codesnippet/cpp/clist-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CList`

## <a name="requirements"></a>Anforderungen

**Header:** afxtempl.h

##  <a name="addhead"></a>  CList::AddHead

Fügt ein neues Element oder eine Liste der Elemente an den Anfang der Liste hinzu.

```
POSITION AddHead(ARG_TYPE newElement);
void AddHead(CList* pNewList);
```

### <a name="parameters"></a>Parameter

*ARG_TYPE*<br/>
Vorlagenparameter, der den Typ des Listenelements angibt (kann ein Verweis sein).

*newElement*<br/>
Das neue Element.

*pNewList*<br/>
Ein Zeiger auf einen anderen `CList` Liste. Die Elemente im *pNewList* wird zu dieser Liste hinzugefügt werden.

### <a name="return-value"></a>Rückgabewert

Die erste Version gibt den Wert für die POSITION des neu eingefügten Elements zurück.

### <a name="remarks"></a>Hinweise

Die Liste kann leer ist, bevor der Vorgang sein.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#36](../../mfc/codesnippet/cpp/clist-class_2.cpp)]

##  <a name="addtail"></a>  CList::AddTail

Fügt ein neues Element oder eine Liste von Elementen am Ende dieser Liste an.

```
POSITION AddTail(ARG_TYPE newElement);
void AddTail(CList* pNewList);
```

### <a name="parameters"></a>Parameter

*ARG_TYPE*<br/>
Vorlagenparameter, der den Typ des Listenelements angibt (kann ein Verweis sein).

*newElement*<br/>
Das Element, das der Liste hinzugefügt werden soll.

*pNewList*<br/>
Ein Zeiger auf einen anderen `CList` Liste. Die Elemente im *pNewList* wird zu dieser Liste hinzugefügt werden.

### <a name="return-value"></a>Rückgabewert

Die erste Version gibt den Wert für die POSITION des neu eingefügten Elements zurück.

### <a name="remarks"></a>Hinweise

Die Liste kann leer ist, bevor der Vorgang sein.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#37](../../mfc/codesnippet/cpp/clist-class_3.cpp)]

##  <a name="clist"></a>  CList::CList

Erstellt eine leere sortierte Liste an.

```
CList(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>Parameter

*nBlockSize*<br/>
Die Granularität der speicherbelegung zum Erweitern der Liste.

### <a name="remarks"></a>Hinweise

Wenn die Liste wächst, wird in Einheiten von Arbeitsspeicher zugeordnet *nBlockSize* Einträge.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#38](../../mfc/codesnippet/cpp/clist-class_4.cpp)]

##  <a name="find"></a>  CList::Find

Sucht die Liste sequenziell nach dem ersten Element der angegebenen übereinstimmenden *Suchwert*.

```
POSITION Find(
    ARG_TYPE searchValue,
    POSITION startAfter = NULL) const;
```

### <a name="parameters"></a>Parameter

*ARG_TYPE*<br/>
Vorlagenparameter, der den Typ des Listenelements angibt (kann ein Verweis sein).

*Suchwert*<br/>
Der Wert, der in der Liste gefunden werden.

*startAfter*<br/>
Die Startposition für die Suche. Wenn kein Wert angegeben wird, beginnt die Suche, mit dem Head-Element.

### <a name="return-value"></a>Rückgabewert

Ein Positionswert, der für die Iteration oder Abrufen von Objekten Zeiger verwendet werden kann. NULL, wenn das Objekt nicht gefunden wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#39](../../mfc/codesnippet/cpp/clist-class_5.cpp)]

##  <a name="findindex"></a>  CList::FindIndex

Verwendet den Wert der *nIndex* als Index in der Liste.

```
POSITION FindIndex(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der nullbasierte Index des Listenelements gefunden werden.

### <a name="return-value"></a>Rückgabewert

Ein Positionswert, der für die Iteration oder Abrufen von Objekten Zeiger verwendet werden kann. NULL, wenn *nIndex* ist negativ oder zu groß.

### <a name="remarks"></a>Hinweise

Es startet eine sequenzielle Überprüfung vom Anfang der Liste aus, beenden Sie alle in der *n*th-Element.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#40](../../mfc/codesnippet/cpp/clist-class_6.cpp)]

##  <a name="getat"></a>  CList::GetAt

Ruft das List-Element an einer angegebenen Position ab.

```
TYPE& GetAt(POSITION position);
const TYPE& GetAt(POSITION position) const;
```

### <a name="parameters"></a>Parameter

*TYPE*<br/>
Der Vorlagenparameter, den Typ des Objekts in der Liste angibt.

*Position*<br/>
Die Position in der Liste des abzurufenden Elements.

### <a name="return-value"></a>Rückgabewert

Finden Sie unter der Beschreibung des Rückgabewerts für `GetHead`.

### <a name="remarks"></a>Hinweise

`GetAt` Gibt das Element (oder einen Verweis auf das Element) mit einer bestimmten Position zugeordnet. Es ist nicht identisch mit einem Index, und Sie können nicht für ein Positionswert selbst. Eine Variable vom Typ POSITION ist ein Schlüssel für die Liste.

Sie müssen sicherstellen, dass Ihre POSITION-Wert eine gültige Position in der Liste darstellt. Wenn er ungültig ist, bestätigt Sie dann die Debugversion der Microsoft Foundation Class-Bibliothek.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CList::GetHeadPosition](#getheadposition).

##  <a name="getcount"></a>  CList::GetCount

Ruft die Anzahl der Elemente in dieser Liste ab.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Rückgabewert

Ein ganzzahliger-Wert, der die Anzahl der Elemente enthält.

### <a name="remarks"></a>Hinweise

Das Aufrufen dieser Methode generiert das gleiche Ergebnis wie die [CList::GetSize](#getsize) Methode.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CList::RemoveHead](#removehead).

##  <a name="gethead"></a>  CList::GetHead

Ruft ab, das Head-Element (oder einen Verweis auf das Anfangselement) dieser Liste.

```
const TYPE& GetHead() const;

TYPE& GetHead();
```

### <a name="parameters"></a>Parameter

*TYPE*<br/>
Der Vorlagenparameter, den Typ des Objekts in der Liste angibt.

### <a name="return-value"></a>Rückgabewert

Wenn die Liste **const**, `GetHead` gibt eine Kopie des Elements am Anfang der Liste zurück. Dadurch können die Funktion, die nur auf der rechten Seite einer zuweisungsanweisung verwendet werden, und die Liste vor Änderungen schützt.

Wenn die Liste nicht **const**, `GetHead` gibt einen Verweis auf das Element am Anfang der Liste zurück. Dadurch können die Funktion, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und dadurch die Einträge in der Liste geändert werden kann.

### <a name="remarks"></a>Hinweise

Sie müssen sicherstellen, dass die Liste nicht leer ist, bevor der Aufruf ist `GetHead`. Wenn die Liste leer ist, bestätigt Sie dann die Debugversion der Microsoft Foundation Class-Bibliothek. Verwendung ["isEmpty"](#isempty) um sicherzustellen, dass die Liste Elemente enthält.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#41](../../mfc/codesnippet/cpp/clist-class_7.cpp)]

##  <a name="getheadposition"></a>  CList::GetHeadPosition

Ruft die Position der Head-Element dieser Liste ab.

```
POSITION GetHeadPosition() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Positionswert, der für die Iteration oder Abrufen von Objekten Zeiger verwendet werden kann. NULL, wenn die Liste leer ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#42](../../mfc/codesnippet/cpp/clist-class_8.cpp)]

##  <a name="getnext"></a>  CList::GetNext

Ruft das List-Element identifizierte *rposition zurück*, legt dann *rposition zurück* auf den Wert für die POSITION des nächsten Eintrag in der Liste.

```
TYPE& GetNext(POSITION& rPosition);
const TYPE& GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parameter

*TYPE*<br/>
Der Vorlagenparameter, der Typ der Elemente in der Liste angibt.

*rposition zurück*<br/>
Ein Verweis auf eine Positionswert, der von einem vorherigen zurückgegebene `GetNext`, [GetHeadPosition](#getheadposition), oder anderer Aufruf der Memberfunktion.

### <a name="return-value"></a>Rückgabewert

Wenn die Liste **const**, `GetNext` gibt eine Kopie eines Elements der Liste zurück. Dadurch können die Funktion, die nur auf der rechten Seite einer zuweisungsanweisung verwendet werden, und die Liste vor Änderungen schützt.

Wenn die Liste nicht **const**, `GetNext` gibt einen Verweis auf ein Element der Liste zurück. Dadurch können die Funktion, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und dadurch die Einträge in der Liste geändert werden kann.

### <a name="remarks"></a>Hinweise

Sie können `GetNext` in einer Schleife Vorwärtsiteration, wenn Sie die ursprüngliche Position mit einem Aufruf von einrichten `GetHeadPosition` oder `Find`.

Sie müssen sicherstellen, dass Ihre POSITION-Wert eine gültige Position in der Liste darstellt. Wenn er ungültig ist, bestätigt Sie dann die Debugversion der Microsoft Foundation Class-Bibliothek.

Ist das abgerufene Element das letzte Element in der Liste aus, klicken Sie dann den neuen Wert des `rPosition` auf NULL festgelegt ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#43](../../mfc/codesnippet/cpp/clist-class_9.cpp)]

##  <a name="getprev"></a>  CList::GetPrev

Ruft das List-Element identifizierte `rPosition`, legt dann `rPosition` auf den Wert für die POSITION des vorherigen Eintrags in der Liste.

```
TYPE& GetPrev(POSITION& rPosition);
const TYPE& GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parameter

*TYPE*<br/>
Der Vorlagenparameter, der Typ der Elemente in der Liste angibt.

*rposition zurück*<br/>
Ein Verweis auf eine Positionswert, der von einem vorherigen zurückgegebene `GetPrev` oder anderen Aufruf der Memberfunktion.

### <a name="return-value"></a>Rückgabewert

Wenn die Liste **const**, `GetPrev` gibt eine Kopie des Elements am Anfang der Liste zurück. Dadurch können die Funktion, die nur auf der rechten Seite einer zuweisungsanweisung verwendet werden, und die Liste vor Änderungen schützt.

Wenn die Liste nicht **const**, `GetPrev` gibt einen Verweis auf ein Element der Liste zurück. Dadurch können die Funktion, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und dadurch die Einträge in der Liste geändert werden kann.

### <a name="remarks"></a>Hinweise

Sie können `GetPrev` in einer umgekehrte Iteration-Schleife, wenn Sie die ursprüngliche Position mit einem Aufruf von einrichten `GetTailPosition` oder `Find`.

Sie müssen sicherstellen, dass Ihre POSITION-Wert eine gültige Position in der Liste darstellt. Wenn er ungültig ist, bestätigt Sie dann die Debugversion der Microsoft Foundation Class-Bibliothek.

Wenn das abgerufene Element der erste in der Liste aus, klicken Sie dann der neue Wert des ist *rposition zurück* auf NULL festgelegt ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#44](../../mfc/codesnippet/cpp/clist-class_10.cpp)]

##  <a name="getsize"></a>  CList::GetSize

Gibt die Anzahl der Listenelemente zurück.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente in der Liste.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode, um die Anzahl der Elemente in der Liste abzurufen.  Das Aufrufen dieser Methode generiert das gleiche Ergebnis wie die [CList::GetCount](#getcount) Methode.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#45](../../mfc/codesnippet/cpp/clist-class_11.cpp)]

##  <a name="gettail"></a>  CList::GetTail

Ruft die `CObject` Zeiger, der das Ende Element dieser Liste darstellt.

```
TYPE& GetTail();
const TYPE& GetTail() const;
```

### <a name="parameters"></a>Parameter

*TYPE*<br/>
Der Vorlagenparameter, den Typ der Elemente in der Liste angibt.

### <a name="return-value"></a>Rückgabewert

Finden Sie unter der Beschreibung des Rückgabewerts für [GetHead](../../mfc/reference/coblist-class.md#gethead).

### <a name="remarks"></a>Hinweise

Sie müssen sicherstellen, dass die Liste nicht leer ist, bevor der Aufruf ist `GetTail`. Wenn die Liste leer ist, bestätigt Sie dann die Debugversion der Microsoft Foundation Class-Bibliothek. Verwendung ["isEmpty"](../../mfc/reference/coblist-class.md#isempty) um sicherzustellen, dass die Liste Elemente enthält.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#46](../../mfc/codesnippet/cpp/clist-class_12.cpp)]

##  <a name="gettailposition"></a>  CList::GetTailPosition

Ruft die Position des Elements Ende dieser Liste. NULL, wenn die Liste leer ist.

```
POSITION GetTailPosition() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Positionswert, der für die Iteration oder Abrufen von Objekten Zeiger verwendet werden kann. NULL, wenn die Liste leer ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#47](../../mfc/codesnippet/cpp/clist-class_13.cpp)]

##  <a name="insertafter"></a>  CList::InsertAfter

Fügt ein Element zu dieser Liste nach dem Element an der angegebenen Position an.

```
POSITION InsertAfter(POSITION position, ARG_TYPE newElement);
```

### <a name="parameters"></a>Parameter

*Position*<br/>
Eine Positionswert, der von einem vorherigen zurückgegebene `GetNext`, `GetPrev`, oder `Find` Aufruf der Memberfunktion.

*ARG_TYPE*<br/>
Der Vorlagenparameter, der den Typ des Listenelements angibt.

*newElement*<br/>
Das Element, das der Liste hinzugefügt werden soll.

### <a name="return-value"></a>Rückgabewert

Eine Positionswert, der zur Iteration oder ein Abruf von Listenelementen verwendet werden kann.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#48](../../mfc/codesnippet/cpp/clist-class_14.cpp)]

##  <a name="insertbefore"></a>  CList::InsertBefore

Fügt dieser Liste ein Element vor dem Element an der angegebenen Position hinzu.

```
POSITION InsertBefore(POSITION position, ARG_TYPE newElement);
```

### <a name="parameters"></a>Parameter

*Position*<br/>
Eine Positionswert, der von einem vorherigen zurückgegebene `GetNext`, `GetPrev`, oder `Find` Aufruf der Memberfunktion.

*ARG_TYPE*<br/>
Vorlagenparameter, der den Typ des Listenelements angibt (kann ein Verweis sein).

*newElement*<br/>
Das Element, das der Liste hinzugefügt werden soll.

### <a name="return-value"></a>Rückgabewert

Eine Positionswert, der zur Iteration oder ein Abruf von Listenelementen verwendet werden kann.

### <a name="remarks"></a>Hinweise

Wenn *Position* NULL ist, das Element am Anfang der Liste eingefügt wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#49](../../mfc/codesnippet/cpp/clist-class_15.cpp)]

##  <a name="isempty"></a>  CList::IsEmpty

Gibt an, ob diese Liste keine Elemente enthält.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn diese Liste ist leer. andernfalls 0.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#50](../../mfc/codesnippet/cpp/clist-class_16.cpp)]

##  <a name="removeall"></a>  CList::RemoveAll

Entfernt alle Elemente aus dieser Liste, und den zugeordneten Arbeitsspeicher frei.

```
void RemoveAll();
```

### <a name="remarks"></a>Hinweise

Es wird kein Fehler erzeugt, wenn die Liste noch leer ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#51](../../mfc/codesnippet/cpp/clist-class_17.cpp)]

##  <a name="removeat"></a>  CList::RemoveAt

Entfernt das angegebene Element aus dieser Liste.

```
void RemoveAt(POSITION position);
```

### <a name="parameters"></a>Parameter

*Position*<br/>
Die Position des Elements, das aus der Liste entfernt werden.

### <a name="remarks"></a>Hinweise

Sie müssen sicherstellen, dass Ihre POSITION-Wert eine gültige Position in der Liste darstellt. Wenn er ungültig ist, bestätigt Sie dann die Debugversion der Microsoft Foundation Class-Bibliothek.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#52](../../mfc/codesnippet/cpp/clist-class_18.cpp)]

##  <a name="removehead"></a>  CList::RemoveHead

Entfernt das Element vom Anfang der Liste aus, und gibt einen Zeiger darauf zurück.

```
TYPE RemoveHead();
```

### <a name="parameters"></a>Parameter

*TYPE*<br/>
Der Vorlagenparameter, den Typ der Elemente in der Liste angibt.

### <a name="return-value"></a>Rückgabewert

Das Element zuvor am Anfang der Liste.

### <a name="remarks"></a>Hinweise

Sie müssen sicherstellen, dass die Liste nicht leer ist, bevor der Aufruf ist `RemoveHead`. Wenn die Liste leer ist, bestätigt Sie dann die Debugversion der Microsoft Foundation Class-Bibliothek. Verwendung ["isEmpty"](#isempty) um sicherzustellen, dass die Liste Elemente enthält.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#53](../../mfc/codesnippet/cpp/clist-class_19.cpp)]

##  <a name="removetail"></a>  CList::RemoveTail

Entfernt das Element aus das Ende der Liste aus, und gibt einen Zeiger darauf zurück.

```
TYPE RemoveTail();
```

### <a name="parameters"></a>Parameter

*TYPE*<br/>
Der Vorlagenparameter, den Typ der Elemente in der Liste angibt.

### <a name="return-value"></a>Rückgabewert

Das Element, das am Ende der Liste wurde.

### <a name="remarks"></a>Hinweise

Sie müssen sicherstellen, dass die Liste nicht leer ist, bevor der Aufruf ist `RemoveTail`. Wenn die Liste leer ist, bestätigt Sie dann die Debugversion der Microsoft Foundation Class-Bibliothek. Verwendung ["isEmpty"](#isempty) um sicherzustellen, dass die Liste Elemente enthält.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#54](../../mfc/codesnippet/cpp/clist-class_20.cpp)]

##  <a name="setat"></a>  CList::SetAt

Eine Variable vom Typ POSITION ist ein Schlüssel für die Liste.

```
void SetAt(POSITION pos, ARG_TYPE newElement);
```

### <a name="parameters"></a>Parameter

*POS*<br/>
Die POSITION des Elements festgelegt werden.

*ARG_TYPE*<br/>
Vorlagenparameter, der den Typ des Listenelements angibt (kann ein Verweis sein).

*newElement*<br/>
Das Element der Liste hinzugefügt werden.

### <a name="remarks"></a>Hinweise

Es ist nicht identisch mit einem Index, und Sie können nicht für ein Positionswert selbst. `SetAt` Schreibt das Element in der angegebenen Position in der Liste.

Sie müssen sicherstellen, dass Ihre POSITION-Wert eine gültige Position in der Liste darstellt. Wenn er ungültig ist, bestätigt Sie dann die Debugversion der Microsoft Foundation Class-Bibliothek.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCCollections#55](../../mfc/codesnippet/cpp/clist-class_21.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel erfassen](../../visual-cpp-samples.md)<br/>
[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CMap-Klasse](../../mfc/reference/cmap-class.md)<br/>
[CArray-Klasse](../../mfc/reference/carray-class.md)
