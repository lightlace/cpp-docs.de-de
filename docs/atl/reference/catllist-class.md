---
title: CAtlList-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlList
- ATLCOLL/ATL::CAtlList
- ATLCOLL/ATL::CAtlList::INARGTYPE
- ATLCOLL/ATL::CAtlList::CAtlList
- ATLCOLL/ATL::CAtlList::AddHead
- ATLCOLL/ATL::CAtlList::AddHeadList
- ATLCOLL/ATL::CAtlList::AddTail
- ATLCOLL/ATL::CAtlList::AddTailList
- ATLCOLL/ATL::CAtlList::AssertValid
- ATLCOLL/ATL::CAtlList::Find
- ATLCOLL/ATL::CAtlList::FindIndex
- ATLCOLL/ATL::CAtlList::GetAt
- ATLCOLL/ATL::CAtlList::GetCount
- ATLCOLL/ATL::CAtlList::GetHead
- ATLCOLL/ATL::CAtlList::GetHeadPosition
- ATLCOLL/ATL::CAtlList::GetNext
- ATLCOLL/ATL::CAtlList::GetPrev
- ATLCOLL/ATL::CAtlList::GetTail
- ATLCOLL/ATL::CAtlList::GetTailPosition
- ATLCOLL/ATL::CAtlList::InsertAfter
- ATLCOLL/ATL::CAtlList::InsertBefore
- ATLCOLL/ATL::CAtlList::IsEmpty
- ATLCOLL/ATL::CAtlList::MoveToHead
- ATLCOLL/ATL::CAtlList::MoveToTail
- ATLCOLL/ATL::CAtlList::RemoveAll
- ATLCOLL/ATL::CAtlList::RemoveAt
- ATLCOLL/ATL::CAtlList::RemoveHead
- ATLCOLL/ATL::CAtlList::RemoveHeadNoReturn
- ATLCOLL/ATL::CAtlList::RemoveTail
- ATLCOLL/ATL::CAtlList::RemoveTailNoReturn
- ATLCOLL/ATL::CAtlList::SetAt
- ATLCOLL/ATL::CAtlList::SwapElements
dev_langs:
- C++
helpviewer_keywords:
- CAtlList class
ms.assetid: 09e98053-64b2-4efa-99ab-d0542caaf981
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c5a24a98e7780a98726df29452a9878c8abf3d81
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43756443"
---
# <a name="catllist-class"></a>CAtlList-Klasse

Diese Klasse stellt Methoden zum Erstellen und verwalten ein List-Objekt.

## <a name="syntax"></a>Syntax

```
template<typename E, class ETraits = CElementTraits<E>>  
class CAtlList
```

#### <a name="parameters"></a>Parameter

*E*  
Der Elementtyp.

*ETraits*  
Der Code verwendet, um die Elemente kopiert oder verschoben wird. Finden Sie unter [CElementTraits-Klasse](../../atl/reference/celementtraits-class.md) Weitere Details.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|[CAtlList::INARGTYPE](#inargtype)||

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAtlList::CAtlList](#catllist)|Der Konstruktor.|
|[CAtlList:: ~ CAtlList](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAtlList::AddHead](#addhead)|Rufen Sie diese Methode, um ein Element an den Anfang der Liste hinzufügen.|
|[CAtlList::AddHeadList](#addheadlist)|Rufen Sie diese Methode, um eine vorhandene Liste an den Anfang der Liste hinzufügen.|
|[CAtlList::AddTail](#addtail)|Rufen Sie diese Methode, um ein Element am Ende dieser Liste hinzufügen.|
|[CAtlList::AddTailList](#addtaillist)|Rufen Sie diese Methode, um eine vorhandene Liste am Ende dieser Liste hinzufügen.|
|[CAtlList::AssertValid](#assertvalid)|Rufen Sie diese Methode, um zu bestätigen, dass die Liste gültig ist.|
|[CAtlList::Find](#find)|Rufen Sie diese Methode, um die Liste für das angegebene Element zu suchen.|
|[CAtlList::FindIndex](#findindex)|Rufen Sie diese Methode, um die Position eines Elements zu erhalten, einen Indexwert angegeben.|
|[CAtlList::GetAt](#getat)|Rufen Sie diese Methode, um das Element an einer angegebenen Position in der Liste zurückgeben.|
|[CAtlList::GetCount](#getcount)|Rufen Sie diese Methode, um die Anzahl der Objekte in der Liste zurückgeben.|
|[CAtlList::GetHead](#gethead)|Rufen Sie diese Methode, um das Element am Anfang der Liste zurückgeben.|
|[CAtlList::GetHeadPosition](#getheadposition)|Rufen Sie diese Methode, um die Position der Anfang der Liste abzurufen.|
|[CAtlList::GetNext](#getnext)|Rufen Sie diese Methode, um das nächste Element aus der Liste zurückgeben.|
|[CAtlList::GetPrev](#getprev)|Rufen Sie diese Methode, um das vorherige Element in der Liste zurückgeben.|
|[CAtlList::GetTail](#gettail)|Rufen Sie diese Methode, um das Element am Ende der Liste zurückgeben.|
|[CAtlList::GetTailPosition](#gettailposition)|Rufen Sie diese Methode, um die Position der das Ende der Liste abzurufen.|
|[CAtlList::InsertAfter](#insertafter)|Rufen Sie diese Methode, um ein neues Element in der Liste nach der angegebenen Position eingefügt.|
|[CAtlList::InsertBefore](#insertbefore)|Rufen Sie diese Methode, um ein neues Element in der Liste vor der angegebenen Position einfügen.|
|[CAtlList::IsEmpty](#isempty)|Rufen Sie diese Methode, um zu bestimmen, ob die Liste leer ist.|
|[CAtlList::MoveToHead](#movetohead)|Rufen Sie diese Methode, um das angegebene Element an den Anfang der Liste zu verschieben.|
|[CAtlList::MoveToTail](#movetotail)|Rufen Sie diese Methode, um das angegebene Element am Ende der Liste zu verschieben.|
|[CAtlList::RemoveAll](#removeall)|Rufen Sie diese Methode, um alle Elemente aus der Liste zu entfernen.|
|[CAtlList::RemoveAt](#removeat)|Rufen Sie diese Methode, um ein einzelnes Element aus der Liste zu entfernen.|
|[CAtlList::RemoveHead](#removehead)|Rufen Sie diese Methode, um das Element am Anfang der Liste zu entfernen.|
|[CAtlList::RemoveHeadNoReturn](#removeheadnoreturn)|Rufen Sie diese Methode, um das Element am Anfang der Liste zu entfernen, ohne einen Wert zurückgibt.|
|[CAtlList::RemoveTail](#removetail)|Rufen Sie diese Methode, um das Element am Ende der Liste zu entfernen.|
|[CAtlList::RemoveTailNoReturn](#removetailnoreturn)|Rufen Sie diese Methode, um das Element am Ende der Liste zu entfernen, ohne einen Wert zurückgibt.|
|[CAtlList::SetAt](#setat)|Rufen Sie diese Methode aus, um den Wert des Elements an einer bestimmten Position in der Liste festzulegen.|
|[CAtlList::SwapElements](#swapelements)|Rufen Sie diese Methode, um Elemente in der Liste zu wechseln.|

## <a name="remarks"></a>Hinweise

Die `CAtlList` Klasse unterstützt sortierte Listen von Objekten nicht eindeutig, zugegriffen werden, sequenziell oder über den Wert. `CAtlList` Listen Verhalten sich wie doppelt verknüpfte Listen. Jede Liste enthält eine Anfangs- und Endwert, und neue Elemente (oder Listen in einigen Fällen) an beiden Enden der Liste hinzugefügt, oder eingefügt werden können vor oder nach bestimmten Elementen.

Die meisten der `CAtlList` Methoden eines Werts Position verwenden. Dieser Wert wird von den Methoden verwendet, um auf um die tatsächliche Speicheradresse zu verweisen, in dem die Elemente gespeichert sind, und nicht berechnet oder werden direkt vorhergesagt. Erforderlich für den Zugriff auf die *n*th-Element in der Liste, die Methode [CAtlList::FindIndex](#findindex) gibt den Wert für die entsprechende Position für einen bestimmten Index zurück. Die Methoden [CAtlList::GetNext](#getnext) und [CAtlList::GetPrev](#getprev) können verwendet werden, um die Objekte in der Liste zu durchlaufen.

Weitere Informationen zu den verfügbaren mit ATL-Auflistungsklassen, finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Anforderungen

**Header:** atlcoll.h

##  <a name="addhead"></a>  CAtlList::AddHead

Rufen Sie diese Methode, um ein Element an den Anfang der Liste hinzufügen.

```
POSITION AddHead();
POSITION AddHead(INARGTYPE element);
```

### <a name="parameters"></a>Parameter

*Element*  
Das neue Element.

### <a name="return-value"></a>Rückgabewert

Gibt die Position des neu hinzugefügten Elements zurück.

### <a name="remarks"></a>Hinweise

Wenn die erste Version verwendet wird, wird ein leeres Element erstellt, mit seinem Standardkonstruktor, anstatt der Kopierkonstruktor.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#13](../../atl/codesnippet/cpp/catllist-class_1.cpp)]

##  <a name="addheadlist"></a>  CAtlList::AddHeadList

Rufen Sie diese Methode, um eine vorhandene Liste an den Anfang der Liste hinzufügen.

```
void AddHeadList(const CAtlList<E, ETraits>* plNew);
```

### <a name="parameters"></a>Parameter

*plNew*  
Die Liste hinzugefügt werden.

### <a name="remarks"></a>Hinweise

Die Liste zeigt *PlNew* am Anfang der vorhandenen Liste eingefügt wird. Debug-Builds wird ein Assertionsfehler auftreten, wenn *PlNew* gleich NULL ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#14](../../atl/codesnippet/cpp/catllist-class_2.cpp)]

##  <a name="addtail"></a>  CAtlList::AddTail

Rufen Sie diese Methode, um ein Element am Ende dieser Liste hinzufügen.

```
POSITION AddTail();
POSITION AddTail(INARGTYPE element);
```

### <a name="parameters"></a>Parameter

*Element*  
Das hinzuzufügende Element.

### <a name="return-value"></a>Rückgabewert

Gibt die POSITION des neu hinzugefügten Elements zurück.

### <a name="remarks"></a>Hinweise

Wenn die erste Version verwendet wird, wird ein leeres Element erstellt, mit seinem Standardkonstruktor, anstatt der Kopierkonstruktor. Das Element am Ende der Liste hinzugefügt wird, und daher wird sie jetzt das Ende. Diese Methode kann mit einer leeren Liste verwendet werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#15](../../atl/codesnippet/cpp/catllist-class_3.cpp)]

##  <a name="addtaillist"></a>  CAtlList::AddTailList

Rufen Sie diese Methode, um eine vorhandene Liste am Ende dieser Liste hinzufügen.

```
void AddTailList(const CAtlList<E, ETraits>* plNew);
```

### <a name="parameters"></a>Parameter

*plNew*  
Die Liste hinzugefügt werden.

### <a name="remarks"></a>Hinweise

Die Liste zeigt *PlNew* eingefügt hinter dem letzten Element (sofern vorhanden) in der Liste. Das letzte Element in der *PlNew* Liste, daher ist das Protokollfragment. Debug-Builds wird ein Assertionsfehler auftreten, wenn *PlNew* gleich NULL ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#16](../../atl/codesnippet/cpp/catllist-class_4.cpp)]

##  <a name="assertvalid"></a>  CAtlList::AssertValid

Rufen Sie diese Methode, um zu bestätigen, dass die Liste gültig ist.

```
void AssertValid() const;
```

### <a name="remarks"></a>Hinweise

In Debugbuilds erfolgt ein Assertionsfehler ausgelöst, wenn das Listenobjekt nicht gültig ist. Um gültig zu sein, eine leere Liste benötigen sowohl Anfang und Ende auf NULL muss, und eine Liste, die nicht leer ist Haupt- und Tail gültige Adressen auf.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#17](../../atl/codesnippet/cpp/catllist-class_5.cpp)]

##  <a name="catllist"></a>  CAtlList::CAtlList

Der Konstruktor.

```
CAtlList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parameter

*nBlockSize*  
Die Blockgröße.

### <a name="remarks"></a>Hinweise

Der Konstruktor für die `CAtlList` Objekt. Die Blockgröße ist ein Maß für die Speichermenge belegt werden, wenn ein neues Element erforderlich ist. Größere Blöcke reduzieren Sie Aufrufe von Reservierungsroutinen Arbeitsspeicher jedoch mehr Ressourcen verwenden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#18](../../atl/codesnippet/cpp/catllist-class_6.cpp)]

##  <a name="dtor"></a>  CAtlList:: ~ CAtlList

Der Destruktor.

```
~CAtlList() throw();
```

### <a name="remarks"></a>Hinweise

Alle zugeordnete Ressourcen freigegeben, einschließlich von einem Aufruf von [CAtlList::RemoveAll](#removeall) auf alle Elemente aus der Liste zu entfernen.

In Debugbuilds wird ein Assertionsfehler ausgelöst auftreten, wenn die Liste weiterhin einige Elemente nach dem Aufruf enthält `RemoveAll`.

##  <a name="find"></a>  CAtlList::Find

Rufen Sie diese Methode, um die Liste für das angegebene Element zu suchen.

```
POSITION Find(INARGTYPE element, POSITION posStartAfter = NULL) const throw();
```

### <a name="parameters"></a>Parameter

*Element*  
Das Element, in der Liste gefunden werden.

*posStartAfter*  
Die Startposition für die Suche. Wenn kein Wert angegeben wird, beginnt die Suche, mit dem Head-Element.

### <a name="return-value"></a>Rückgabewert

Gibt den Wert für die POSITION des Elements zurück, wenn gefunden, andernfalls wird NULL zurückgegeben.

### <a name="remarks"></a>Hinweise

In Debugbuilds wird ein Assertionsfehler ausgelöst auftreten, wenn das List-Objekt ungültig ist oder wenn die *PosStartAfter* Wert liegt außerhalb des Bereichs.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#19](../../atl/codesnippet/cpp/catllist-class_7.cpp)]

##  <a name="findindex"></a>  CAtlList::FindIndex

Rufen Sie diese Methode, um die Position eines Elements zu erhalten, einen Indexwert angegeben.

```
POSITION FindIndex(size_t iElement) const throw();
```

### <a name="parameters"></a>Parameter

*"IElement"*  
Der nullbasierte Index des Listenelements erforderlich.

### <a name="return-value"></a>Rückgabewert

Gibt zurück, der entsprechenden Positionswert oder NULL, wenn *"IElement"* liegt außerhalb des Bereichs.

### <a name="remarks"></a>Hinweise

Diese Methode gibt die POSITION für einen bestimmten Index-Wert, den Zugriff auf die *n*th-Element in der Liste.

In Debugbuilds erfolgt ein Assertionsfehler ausgelöst, wenn das Listenobjekt nicht gültig ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#20](../../atl/codesnippet/cpp/catllist-class_8.cpp)]

##  <a name="getat"></a>  CAtlList::GetAt

Rufen Sie diese Methode, um das Element an einer angegebenen Position in der Liste zurückgeben.

```
E& GetAt(POSITION pos) throw();
const E& GetAt(POSITION pos) const throw();
```

### <a name="parameters"></a>Parameter

*POS*  
Der Wert der POSITION ein bestimmtes Elements angeben.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf, oder eine Kopie des Elements.

### <a name="remarks"></a>Hinweise

Wenn die Liste **const**, `GetAt` gibt eine Kopie des Elements zurück. Dadurch können die Methode, die nur auf der rechten Seite einer zuweisungsanweisung verwendet werden, und die Liste vor Änderungen schützt.

Wenn die Liste nicht **const**, `GetAt` gibt einen Verweis auf das Element zurück. Dadurch können die Methode, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und dadurch die Einträge in der Liste geändert werden kann.

Debug-Builds wird ein Assertionsfehler auftreten, wenn *pos* gleich NULL ist.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlList::FindIndex](#findindex).

##  <a name="getcount"></a>  CAtlList::GetCount

Rufen Sie diese Methode, um die Anzahl der Objekte in der Liste zurückgeben.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl von Elementen in der Liste zurück.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlList::Find](#find).

##  <a name="gethead"></a>  CAtlList::GetHead

Rufen Sie diese Methode, um das Element am Anfang der Liste zurückgeben.

```
E& GetHead() throw();
const E& GetHead() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Verweis auf, oder eine Kopie davon das Element am Anfang der Liste zurück.

### <a name="remarks"></a>Hinweise

Wenn die Liste **const**, `GetHead` gibt eine Kopie des Elements am Anfang der Liste zurück. Dadurch können die Methode, die nur auf der rechten Seite einer zuweisungsanweisung verwendet werden, und die Liste vor Änderungen schützt.

Wenn die Liste nicht **const**, `GetHead` gibt einen Verweis auf das Element am Anfang der Liste zurück. Dadurch können die Methode, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und dadurch die Einträge in der Liste geändert werden kann.

In Debugbuilds erfolgt ein Assertionsfehler ausgelöst, wenn der Anfang der Liste auf NULL verweist.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlList::AddHead](#addhead).

##  <a name="getheadposition"></a>  CAtlList::GetHeadPosition

Rufen Sie diese Methode, um die Position der Anfang der Liste abzurufen.

```
POSITION GetHeadPosition() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt den Wert für die POSITION für das Element am Anfang der Liste zurück.

### <a name="remarks"></a>Hinweise

Wenn die Liste leer ist, ist der zurückgegebene Wert NULL.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#21](../../atl/codesnippet/cpp/catllist-class_9.cpp)]

##  <a name="getnext"></a>  CAtlList::GetNext

Rufen Sie diese Methode, um das nächste Element aus der Liste zurückgeben.

```
E& GetNext(POSITION& pos) throw();
const E& GetNext(POSITION& pos) const throw();
```

### <a name="parameters"></a>Parameter

*POS*  
Ein Positionswert, von einem vorherigen Aufruf zurückgegebene `GetNext`, [CAtlList::GetHeadPosition](#getheadposition), oder andere `CAtlList` Methode.

### <a name="return-value"></a>Rückgabewert

Wenn die Liste **const**, `GetNext` gibt eine Kopie des nächsten Elements der Liste zurück. Dadurch können die Methode, die nur auf der rechten Seite einer zuweisungsanweisung verwendet werden, und die Liste vor Änderungen schützt.

Wenn die Liste nicht **const**, `GetNext` gibt einen Verweis auf das nächste Element der Liste zurück. Dadurch können die Methode, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und dadurch die Einträge in der Liste geändert werden kann.

### <a name="remarks"></a>Hinweise

Der Zähler, der POSITION *pos*, wird aktualisiert und zeigen Sie auf das nächste Element in der Liste aus, oder NULL, wenn keine Elemente mehr vorhanden sind. Debug-Builds wird ein Assertionsfehler auftreten, wenn *pos* gleich NULL ist.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlList::GetHeadPosition](#getheadposition).

##  <a name="getprev"></a>  CAtlList::GetPrev

Rufen Sie diese Methode, um das vorherige Element in der Liste zurückgeben.

```
E& GetPrev(POSITION& pos) throw();
const E& GetPrev(POSITION& pos) const throw();
```

### <a name="parameters"></a>Parameter

*POS*  
Ein Positionswert, von einem vorherigen Aufruf zurückgegebene `GetPrev`, [CAtlList::GetTailPosition](#gettailposition), oder andere `CAtlList` Methode.

### <a name="return-value"></a>Rückgabewert

Wenn die Liste **const**, `GetPrev` gibt eine Kopie eines Elements der Liste zurück. Dadurch können die Methode, die nur auf der rechten Seite einer zuweisungsanweisung verwendet werden, und die Liste vor Änderungen schützt.

Wenn die Liste nicht **const**, `GetPrev` gibt einen Verweis auf ein Element der Liste zurück. Dadurch können die Methode, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und dadurch die Einträge in der Liste geändert werden kann.

### <a name="remarks"></a>Hinweise

Der Zähler, der POSITION *pos*, wird aktualisiert und zeigen Sie auf das vorherige Element in der Liste aus, oder NULL, wenn keine Elemente mehr vorhanden sind. Debug-Builds wird ein Assertionsfehler auftreten, wenn *pos* gleich NULL ist.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlList::GetTailPosition](#gettailposition).

##  <a name="gettail"></a>  CAtlList::GetTail

Rufen Sie diese Methode, um das Element am Ende der Liste zurückgeben.

```
E& GetTail() throw();
const E& GetTail() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Verweis auf, oder eine Kopie davon das Element am Ende der Liste zurück.

### <a name="remarks"></a>Hinweise

Wenn die Liste **const**, `GetTail` gibt eine Kopie des Elements am Anfang der Liste zurück. Dadurch können die Methode, die nur auf der rechten Seite einer zuweisungsanweisung verwendet werden, und die Liste vor Änderungen schützt.

Wenn die Liste nicht **const**, `GetTail` gibt einen Verweis auf das Element am Anfang der Liste zurück. Dadurch können die Methode, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und dadurch die Einträge in der Liste geändert werden kann.

In Debugbuilds erfolgt ein Assertionsfehler ausgelöst, wenn das Ende der Liste auf NULL verweist.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlList::AddTail](#addtail).

##  <a name="gettailposition"></a>  CAtlList::GetTailPosition

Rufen Sie diese Methode, um die Position der das Ende der Liste abzurufen.

```
POSITION GetTailPosition() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt den Wert für die POSITION für das Element am Ende der Liste zurück.

### <a name="remarks"></a>Hinweise

Wenn die Liste leer ist, ist der zurückgegebene Wert NULL.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#22](../../atl/codesnippet/cpp/catllist-class_10.cpp)]

##  <a name="inargtype"></a>  CAtlList::INARGTYPE

-Typ, wenn ein Element als ein Eingabe-Argument übergeben wird.

```
typedef ETraits::INARGTYPE INARGTYPE;
```

##  <a name="insertafter"></a>  CAtlList::InsertAfter

Rufen Sie diese Methode, um ein neues Element in der Liste nach der angegebenen Position eingefügt.

```
POSITION InsertAfter(POSITION pos, INARGTYPE element);
```

### <a name="parameters"></a>Parameter

*POS*  
Der Wert der POSITION nach dem das neue Element eingefügt wird.

*Element*  
Das Element eingefügt werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt den Wert für die POSITION des neuen Elements zurück.

### <a name="remarks"></a>Hinweise

In Debugbuilds erfolgt ein Assertionsfehler ausgelöst, wenn die Liste ungültig ist, wenn der Vorgang schlägt fehl, oder wenn versucht wird, fügen Sie das Element nach dem Ende.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#23](../../atl/codesnippet/cpp/catllist-class_11.cpp)]

##  <a name="insertbefore"></a>  CAtlList::InsertBefore

Rufen Sie diese Methode, um ein neues Element in der Liste vor der angegebenen Position einfügen.

```
POSITION InsertBefore(POSITION pos, INARGTYPE element);
```

### <a name="parameters"></a>Parameter

*POS*  
Das neue Element wird in der Liste vor dieser Positionswert eingefügt werden.

*Element*  
Das Element eingefügt werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt den Wert für die POSITION des neuen Elements zurück.

### <a name="remarks"></a>Hinweise

In Debugbuilds erfolgt ein Assertionsfehler ausgelöst, wenn die Liste ungültig ist, wenn der Vorgang schlägt fehl, oder wenn versucht wird, die das Element vor dem Einfügen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#24](../../atl/codesnippet/cpp/catllist-class_12.cpp)]

##  <a name="isempty"></a>  CAtlList::IsEmpty

Rufen Sie diese Methode, um zu bestimmen, ob die Liste leer ist.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Liste keine Objekte enthalten ist, andernfalls "false" enthält.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#25](../../atl/codesnippet/cpp/catllist-class_13.cpp)]

##  <a name="movetohead"></a>  CAtlList::MoveToHead

Rufen Sie diese Methode, um das angegebene Element an den Anfang der Liste zu verschieben.

```
void MoveToHead(POSITION pos) throw();
```

### <a name="parameters"></a>Parameter

*POS*  
Der Wert der POSITION des Elements zu verschieben.

### <a name="remarks"></a>Hinweise

Das angegebene Element wird aus der aktuellen Position an den Anfang der Liste verschoben. Debug-Builds wird ein Assertionsfehler auftreten, wenn *pos* gleich NULL ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#26](../../atl/codesnippet/cpp/catllist-class_14.cpp)]

##  <a name="movetotail"></a>  CAtlList::MoveToTail

Rufen Sie diese Methode, um das angegebene Element am Ende der Liste zu verschieben.

```
void MoveToTail(POSITION pos) throw();
```

### <a name="parameters"></a>Parameter

*POS*  
Der Wert der POSITION des Elements zu verschieben.

### <a name="remarks"></a>Hinweise

Das angegebene Element wird aus der aktuellen Position am Ende der Liste verschoben. Debug-Builds wird ein Assertionsfehler auftreten, wenn *pos* gleich NULL ist.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlList::MoveToHead](#movetohead).

##  <a name="removeall"></a>  CAtlList::RemoveAll

Rufen Sie diese Methode, um alle Elemente aus der Liste zu entfernen.

```
void RemoveAll() throw();
```

### <a name="remarks"></a>Hinweise

Diese Methode entfernt alle Elemente aus der Liste und gibt den zugeordneten Arbeitsspeicher frei. In debuggt-Builds wird ein ATLASSERT ausgelöst, wenn alle Elemente nicht gelöscht werden, oder die Listenstruktur beschädigt wurde.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlList::IsEmpty](#isempty).

##  <a name="removeat"></a>  CAtlList::RemoveAt

Rufen Sie diese Methode, um ein einzelnes Element aus der Liste zu entfernen.

```
void RemoveAt(POSITION pos) throw();
```

### <a name="parameters"></a>Parameter

*POS*  
Der Wert der POSITION des zu entfernenden Elements.

### <a name="remarks"></a>Hinweise

Das Element verweist *pos* wird entfernt, und der Speicher wird freigegeben. Es ist akzeptabel, verwenden Sie `RemoveAt` der Kopf oder das Ende der Liste zu entfernen.

In Debugbuilds erfolgt ein Assertionsfehler ausgelöst, wenn die Liste nicht gültig ist oder wenn das Element entfernt die Liste auf den Speicher bewirkt, dass die nicht Teil der Listenstruktur.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#27](../../atl/codesnippet/cpp/catllist-class_15.cpp)]

##  <a name="removehead"></a>  CAtlList::RemoveHead

Rufen Sie diese Methode, um das Element am Anfang der Liste zu entfernen.

```
E RemoveHead();
```

### <a name="return-value"></a>Rückgabewert

Gibt das Element am Anfang der Liste.

### <a name="remarks"></a>Hinweise

Das Head-Element aus der Liste gelöscht wird, und Speicher freigegeben wird. Es wird eine Kopie des Elements zurückgegeben. In Debugbuilds erfolgt ein Assertionsfehler ausgelöst, wenn die Liste leer ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#28](../../atl/codesnippet/cpp/catllist-class_16.cpp)]

##  <a name="removeheadnoreturn"></a>  CAtlList::RemoveHeadNoReturn

Rufen Sie diese Methode, um das Element am Anfang der Liste zu entfernen, ohne einen Wert zurückgibt.

```
void RemoveHeadNoReturn() throw();
```

### <a name="remarks"></a>Hinweise

Das Head-Element aus der Liste gelöscht wird, und Speicher freigegeben wird. In Debugbuilds erfolgt ein Assertionsfehler ausgelöst, wenn die Liste leer ist.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlList::IsEmpty](#isempty).

##  <a name="removetail"></a>  CAtlList::RemoveTail

Rufen Sie diese Methode, um das Element am Ende der Liste zu entfernen.

```
E RemoveTail();
```

### <a name="return-value"></a>Rückgabewert

Gibt das Element am Ende der Liste.

### <a name="remarks"></a>Hinweise

Das Protokollfragment-Element aus der Liste gelöscht wird, und Speicher freigegeben wird. Es wird eine Kopie des Elements zurückgegeben. In Debugbuilds erfolgt ein Assertionsfehler ausgelöst, wenn die Liste leer ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#29](../../atl/codesnippet/cpp/catllist-class_17.cpp)]

##  <a name="removetailnoreturn"></a>  CAtlList::RemoveTailNoReturn

Rufen Sie diese Methode, um das Element am Ende der Liste zu entfernen, ohne einen Wert zurückgibt.

```
void RemoveTailNoReturn() throw();
```

### <a name="remarks"></a>Hinweise

Das Protokollfragment-Element aus der Liste gelöscht wird, und Speicher freigegeben wird. In Debugbuilds erfolgt ein Assertionsfehler ausgelöst, wenn die Liste leer ist.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlList::IsEmpty](#isempty).

##  <a name="setat"></a>  CAtlList::SetAt

Rufen Sie diese Methode aus, um den Wert des Elements an einer bestimmten Position in der Liste festzulegen.

```
void SetAt(POSITION pos, INARGTYPE element);
```

### <a name="parameters"></a>Parameter

*POS*  
Der Wert der POSITION für das Element ändern.

*Element*  
Der neue Elementwert.

### <a name="remarks"></a>Hinweise

Ersetzt den vorhandenen Wert durch *Element*. Debug-Builds wird ein Assertionsfehler auftreten, wenn *pos* gleich NULL ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#30](../../atl/codesnippet/cpp/catllist-class_18.cpp)]

##  <a name="swapelements"></a>  CAtlList::SwapElements

Rufen Sie diese Methode, um Elemente in der Liste zu wechseln.

```
void SwapElements(POSITION pos1, POSITION pos2) throw();
```

### <a name="parameters"></a>Parameter

*POS1*  
Der erste Wert der POSITION.

*pos2*  
Der zweite Wert der POSITION.

### <a name="remarks"></a>Hinweise

Tauscht die Elemente bei der zwei angegebenen Positionen. In Debugbuilds erfolgt ein Assertionsfehler ausgelöst, wenn entweder Positionswert gleich NULL ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#31](../../atl/codesnippet/cpp/catllist-class_19.cpp)]

## <a name="see-also"></a>Siehe auch

[CList-Klasse](../../mfc/reference/clist-class.md)   
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
