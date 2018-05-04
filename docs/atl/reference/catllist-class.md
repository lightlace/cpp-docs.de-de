---
title: CAtlList Klasse | Microsoft Docs
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
ms.openlocfilehash: 4bfe961ef3ac02a0ed068b8cc2b74f2a6cce22ae
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="catllist-class"></a>CAtlList-Klasse
Diese Klasse stellt Methoden zum Erstellen und Verwalten eines List-Objekts.  
  
## <a name="syntax"></a>Syntax  
  
```
template<typename E, class ETraits = CElementTraits<E>>  
class CAtlList
```  
  
#### <a name="parameters"></a>Parameter  
 `E`  
 Der Elementtyp.  
  
 `ETraits`  
 Der Code verwendet, um die Elemente kopiert oder verschoben. Finden Sie unter [CElementTraits Klasse](../../atl/reference/celementtraits-class.md) Weitere Details.  
  
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
|[CAtlList::AddHead](#addhead)|Rufen Sie diese Methode, um den Anfang der Liste ein Element hinzuzufügen.|  
|[CAtlList::AddHeadList](#addheadlist)|Rufen Sie diese Methode, um eine vorhandene Liste an den Anfang der Liste hinzuzufügen.|  
|[CAtlList::AddTail](#addtail)|Rufen Sie diese Methode, um das Ende dieser Liste ein Element hinzuzufügen.|  
|[CAtlList::AddTailList](#addtaillist)|Rufen Sie diese Methode, um das Ende dieser Liste eine vorhandene Liste hinzuzufügen.|  
|[CAtlList::AssertValid](#assertvalid)|Rufen Sie diese Methode, um zu bestätigen, dass die Liste gültig ist.|  
|[CAtlList::Find](#find)|Rufen Sie diese Methode, um die Liste für das angegebene Element zu suchen.|  
|[CAtlList::FindIndex](#findindex)|Rufen Sie diese Methode, um die Position eines Elements zu erhalten, einen Indexwert angegeben.|  
|[CAtlList::GetAt](#getat)|Rufen Sie diese Methode, um das Element an einer angegebenen Position in der Liste zurückzugeben.|  
|[CAtlList::GetCount](#getcount)|Rufen Sie diese Methode, um die Anzahl der Objekte in der Liste zurückgeben.|  
|[CAtlList::GetHead](#gethead)|Rufen Sie diese Methode, um das Element am Anfang der Liste zurückzugeben.|  
|[CAtlList::GetHeadPosition](#getheadposition)|Rufen Sie diese Methode, um die Position der den Anfang der Liste abzurufen.|  
|[CAtlList::GetNext](#getnext)|Rufen Sie diese Methode, um das nächste Element aus der Liste zurückgeben.|  
|[CAtlList::GetPrev](#getprev)|Rufen Sie diese Methode, um das vorherige Element aus der Liste zurückgeben.|  
|[CAtlList::GetTail](#gettail)|Rufen Sie diese Methode, um das Element am Ende der Liste zurückzugeben.|  
|[CAtlList::GetTailPosition](#gettailposition)|Rufen Sie diese Methode, um die Position der das Ende der Liste abzurufen.|  
|[CAtlList::InsertAfter](#insertafter)|Rufen Sie diese Methode, um ein neues Element in der Liste nach der angegebenen Position eingefügt.|  
|[CAtlList::InsertBefore](#insertbefore)|Rufen Sie diese Methode, um ein neues Element in der Liste vor der angegebenen Position eingefügt.|  
|[CAtlList::IsEmpty](#isempty)|Rufen Sie diese Methode, um zu bestimmen, ob die Liste leer ist.|  
|[CAtlList::MoveToHead](#movetohead)|Rufen Sie diese Methode, um das angegebene Element an den Anfang der Liste zu verschieben.|  
|[CAtlList::MoveToTail](#movetotail)|Rufen Sie diese Methode, um das angegebene Element an das Ende der Liste zu verschieben.|  
|[CAtlList::RemoveAll](#removeall)|Rufen Sie diese Methode, um alle Elemente aus der Liste zu entfernen.|  
|[CAtlList::RemoveAt](#removeat)|Rufen Sie diese Methode, um ein einzelnes Element aus der Liste zu entfernen.|  
|[CAtlList::RemoveHead](#removehead)|Rufen Sie diese Methode, um das Element am Anfang der Liste zu entfernen.|  
|[CAtlList::RemoveHeadNoReturn](#removeheadnoreturn)|Rufen Sie diese Methode, um das Element am Anfang der Liste zu entfernen, ohne einen Wert zurückgeben.|  
|[CAtlList::RemoveTail](#removetail)|Rufen Sie diese Methode, um das Element am Ende der Liste zu entfernen.|  
|[CAtlList::RemoveTailNoReturn](#removetailnoreturn)|Rufen Sie diese Methode, um das Element am Ende der Liste zu entfernen, ohne einen Wert zurückgeben.|  
|[CAtlList::SetAt](#setat)|Rufen Sie diese Methode, um den Wert des Elements an einer bestimmten Position in der Liste festzulegen.|  
|[CAtlList::SwapElements](#swapelements)|Rufen Sie diese Methode zum Wechseln von Elementen in der Liste.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CAtlList` -Klasse unterstützt sortierte Listen mit Objekten zugegriffen werden kann, nicht eindeutig, sequenziell oder über den Wert. `CAtlList` Listen Verhalten sich wie doppelt verknüpfte Listen. Jede Liste enthält eine Anfangs- und Endwert, und neue Elemente (oder Listen in einigen Fällen) an beiden Enden der Liste hinzugefügt, oder eingefügt werden können vor oder nach bestimmten Elementen.  
  
 Die meisten der `CAtlList` ermöglichen das Erstellen eines Werts Position verwenden. Dieser Wert wird von den Methoden verwendet, um die tatsächliche Speicheradresse verweisen, in denen die Elemente gespeichert sind, und sollte nicht berechnet oder direkt vorhergesagt. Bei Bedarf für den Zugriff auf die *n*th-Element in der Liste, die Methode [CAtlList::FindIndex](#findindex) gibt den Wert für die entsprechende Position für einen bestimmten Index zurück. Die Methoden [CAtlList::GetNext](#getnext) und [CAtlList::GetPrev](#getprev) können verwendet werden, um die Objekte in der Liste zu durchlaufen.  
  
 Weitere Informationen zu den verfügbaren mit ATL-Auflistungsklassen, finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="addhead"></a>  CAtlList::AddHead  
 Rufen Sie diese Methode, um den Anfang der Liste ein Element hinzuzufügen.  
  
```
POSITION AddHead();
POSITION AddHead(INARGTYPE element);
```  
  
### <a name="parameters"></a>Parameter  
 `element`  
 Das neue Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Position des neu hinzugefügten Elements zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die erste Version verwendet wird, wird ein leeres Element erstellt, mit seinem Standardkonstruktor, anstatt den Kopierkonstruktor.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#13](../../atl/codesnippet/cpp/catllist-class_1.cpp)]  
  
##  <a name="addheadlist"></a>  CAtlList::AddHeadList  
 Rufen Sie diese Methode, um eine vorhandene Liste an den Anfang der Liste hinzuzufügen.  
  
```
void AddHeadList(const CAtlList<E, ETraits>* plNew);
```  
  
### <a name="parameters"></a>Parameter  
 `plNew`  
 Die Liste hinzugefügt werden.  
  
### <a name="remarks"></a>Hinweise  
 Die Liste verweist `plNew` wird zu Beginn der vorhandenen Liste eingefügt. Debug-Builds wird ein Assertionsfehler auftreten, wenn `plNew` gleich NULL.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#14](../../atl/codesnippet/cpp/catllist-class_2.cpp)]  
  
##  <a name="addtail"></a>  CAtlList::AddTail  
 Rufen Sie diese Methode, um das Ende dieser Liste ein Element hinzuzufügen.  
  
```
POSITION AddTail();
POSITION AddTail(INARGTYPE element);
```  
  
### <a name="parameters"></a>Parameter  
 `element`  
 Das hinzuzufügende Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die POSITION des neu hinzugefügten Elements zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die erste Version verwendet wird, wird ein leeres Element erstellt, mit seinem Standardkonstruktor, anstatt den Kopierkonstruktor. Das Element am Ende der Liste hinzugefügt wird, und daher wird es nun das Protokollfragment. Diese Methode kann mit einer leeren Liste verwendet werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#15](../../atl/codesnippet/cpp/catllist-class_3.cpp)]  
  
##  <a name="addtaillist"></a>  CAtlList::AddTailList  
 Rufen Sie diese Methode, um das Ende dieser Liste eine vorhandene Liste hinzuzufügen.  
  
```
void AddTailList(const CAtlList<E, ETraits>* plNew);
```  
  
### <a name="parameters"></a>Parameter  
 `plNew`  
 Die Liste hinzugefügt werden.  
  
### <a name="remarks"></a>Hinweise  
 Die Liste verweist `plNew` eingefügt hinter dem letzten Element (sofern vorhanden) in der Liste. Das letzte Element in der `plNew` Liste aus diesem Grund wird das Protokollfragment. Debug-Builds wird ein Assertionsfehler auftreten, wenn *PlNew* ist gleich NULL.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#16](../../atl/codesnippet/cpp/catllist-class_4.cpp)]  
  
##  <a name="assertvalid"></a>  CAtlList::AssertValid  
 Rufen Sie diese Methode, um zu bestätigen, dass die Liste gültig ist.  
  
```
void AssertValid() const;
```  
  
### <a name="remarks"></a>Hinweise  
 Debug-Builds erfolgt ein Assertionsfehler ausgelöst, wenn das Listenobjekt nicht gültig ist. Um gültig zu sein, eine leere Liste benötigen sowohl Anfang und Ende auf NULL muss, und eine Liste, die nicht leer ist sowohl Anfang und Ende auf gültige Adressen verweist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#17](../../atl/codesnippet/cpp/catllist-class_5.cpp)]  
  
##  <a name="catllist"></a>  CAtlList::CAtlList  
 Der Konstruktor.  
  
```
CAtlList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nBlockSize`  
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
 Gibt alle zugeordnete Ressourcen, einschließlich eines Aufrufs von [CAtlList::RemoveAll](#removeall) auf alle Elemente aus der Liste zu entfernen.  
  
 Debug-Builds wird ein Assertionsfehler ausgelöst auftreten, wenn die Liste immer noch einige Elemente nach dem Aufruf von enthält `RemoveAll`.  
  
##  <a name="find"></a>  CAtlList::Find  
 Rufen Sie diese Methode, um die Liste für das angegebene Element zu suchen.  
  
```
POSITION Find(INARGTYPE element, POSITION posStartAfter = NULL) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `element`  
 Das Element in der Liste gefunden werden.  
  
 `posStartAfter`  
 Die Startposition für die Suche. Wenn kein Wert angegeben wird, beginnt die Suche mit dem Head-Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert für die POSITION des Elements zurück, wenn gefunden, andernfalls gibt NULL zurück.  
  
### <a name="remarks"></a>Hinweise  
 Debug-Builds wird ein Assertionsfehler auftreten, wenn das Listenobjekt nicht gültig ist, oder wenn die `posStartAfter` liegt außerhalb des gültigen Bereichs.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#19](../../atl/codesnippet/cpp/catllist-class_7.cpp)]  
  
##  <a name="findindex"></a>  CAtlList::FindIndex  
 Rufen Sie diese Methode, um die Position eines Elements zu erhalten, einen Indexwert angegeben.  
  
```
POSITION FindIndex(size_t iElement) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `iElement`  
 Der nullbasierte Index des Elements required-Liste.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert der entsprechenden POSITION oder NULL zurück, wenn `iElement` liegt außerhalb des gültigen Bereichs.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt die POSITION auf einen bestimmten Indexwert entspricht den Zugriff auf die *n*th-Element in der Liste.  
  
 Debug-Builds erfolgt ein Assertionsfehler ausgelöst, wenn das Listenobjekt nicht gültig ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#20](../../atl/codesnippet/cpp/catllist-class_8.cpp)]  
  
##  <a name="getat"></a>  CAtlList::GetAt  
 Rufen Sie diese Methode, um das Element an einer angegebenen Position in der Liste zurückzugeben.  
  
```
E& GetAt(POSITION pos) throw();
const E& GetAt(POSITION pos) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Der Positionswert, der ein bestimmtes Element angeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf oder eine Kopie des Elements.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Liste **const**, `GetAt` gibt eine Kopie des Elements zurück. Dadurch können die Methode, die nur auf der rechten Seite einer zuweisungsanweisung verwendet werden und die Liste vor Änderungen schützt.  
  
 Wenn die Liste nicht **const**, `GetAt` gibt einen Verweis auf das Element zurück. Dadurch können die Methode, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und somit Einträge in der Liste geändert werden kann.  
  
 Debug-Builds wird ein Assertionsfehler auftreten, wenn `pos` gleich NULL.  
  
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
 Rufen Sie diese Methode, um das Element am Anfang der Liste zurückzugeben.  
  
```
E& GetHead() throw();
const E& GetHead() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf oder eine Kopie des Elements am Anfang der Liste zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Liste **const**, `GetHead` gibt eine Kopie des Elements am Anfang der Liste zurück. Dadurch können die Methode, die nur auf der rechten Seite einer zuweisungsanweisung verwendet werden und die Liste vor Änderungen schützt.  
  
 Wenn die Liste nicht **const**, `GetHead` gibt einen Verweis auf das Element am Anfang der Liste zurück. Dadurch können die Methode, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und somit Einträge in der Liste geändert werden kann.  
  
 Debug-Builds ein Assertionsfehler geschieht, wenn der Anfang der Liste auf NULL verweist.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlList::AddHead](#addhead).  
  
##  <a name="getheadposition"></a>  CAtlList::GetHeadPosition  
 Rufen Sie diese Methode, um die Position der den Anfang der Liste abzurufen.  
  
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
 `pos`  
 Ein Positionswert, von einem vorherigen Aufruf zurückgegebene `GetNext`, [CAtlList::GetHeadPosition](#getheadposition), oder andere `CAtlList` Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Liste **const**, `GetNext` gibt eine Kopie des nächsten Elements der Liste zurück. Dadurch können die Methode, die nur auf der rechten Seite einer zuweisungsanweisung verwendet werden und die Liste vor Änderungen schützt.  
  
 Wenn die Liste nicht **const**, `GetNext` gibt einen Verweis auf das nächste Element der Liste zurück. Dadurch können die Methode, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und somit Einträge in der Liste geändert werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Der Zähler POSITION `pos`, wird aktualisiert und zeigen Sie auf das nächste Element in der Liste aus, oder NULL, wenn keine Elemente mehr vorhanden sind. Debug-Builds wird ein Assertionsfehler auftreten, wenn `pos` gleich NULL.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlList::GetHeadPosition](#getheadposition).  
  
##  <a name="getprev"></a>  CAtlList::GetPrev  
 Rufen Sie diese Methode, um das vorherige Element aus der Liste zurückgeben.  
  
```
E& GetPrev(POSITION& pos) throw();
const E& GetPrev(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Ein Positionswert, von einem vorherigen Aufruf zurückgegebene `GetPrev`, [CAtlList::GetTailPosition](#gettailposition), oder andere `CAtlList` Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Liste **const**, `GetPrev` gibt eine Kopie eines Elements in der Liste zurück. Dadurch können die Methode, die nur auf der rechten Seite einer zuweisungsanweisung verwendet werden und die Liste vor Änderungen schützt.  
  
 Wenn die Liste nicht **const**, `GetPrev` gibt einen Verweis auf ein Element der Liste zurück. Dadurch können die Methode, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und somit Einträge in der Liste geändert werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Der Zähler POSITION `pos`, wird aktualisiert und zeigen Sie auf das vorherige Element in der Liste aus, oder NULL, wenn keine Elemente mehr vorhanden sind. Debug-Builds wird ein Assertionsfehler auftreten, wenn `pos` gleich NULL.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlList::GetTailPosition](#gettailposition).  
  
##  <a name="gettail"></a>  CAtlList::GetTail  
 Rufen Sie diese Methode, um das Element am Ende der Liste zurückzugeben.  
  
```
E& GetTail() throw();
const E& GetTail() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf oder eine Kopie des Elements am Ende der Liste zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Liste **const**, `GetTail` gibt eine Kopie des Elements am Anfang der Liste zurück. Dadurch können die Methode, die nur auf der rechten Seite einer zuweisungsanweisung verwendet werden und die Liste vor Änderungen schützt.  
  
 Wenn die Liste nicht **const**, `GetTail` gibt einen Verweis auf das Element am Anfang der Liste zurück. Dadurch können die Methode, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und somit Einträge in der Liste geändert werden kann.  
  
 Debug-Builds erfolgt ein Assertionsfehler ausgelöst, wenn das Ende der Liste auf NULL zeigt.  
  
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
 Der Typ verwendet, wenn ein Element als Eingabeargument übergeben wird.  
  
```
typedef ETraits::INARGTYPE INARGTYPE;
```  
  
##  <a name="insertafter"></a>  CAtlList::InsertAfter  
 Rufen Sie diese Methode, um ein neues Element in der Liste nach der angegebenen Position eingefügt.  
  
```
POSITION InsertAfter(POSITION pos, INARGTYPE element);
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Der Positionswert, nach dem das neue Element eingefügt werden soll.  
  
 `element`  
 Das Element eingefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert für die POSITION des neuen Elements zurück.  
  
### <a name="remarks"></a>Hinweise  
 Debug-Builds erfolgt ein Assertionsfehler ausgelöst, wenn die Liste nicht gültig ist, wenn der Vorgang schlägt fehl oder wird ein Versuch unternommen, um das Element nach den Listenanfang einzufügen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#23](../../atl/codesnippet/cpp/catllist-class_11.cpp)]  
  
##  <a name="insertbefore"></a>  CAtlList::InsertBefore  
 Rufen Sie diese Methode, um ein neues Element in der Liste vor der angegebenen Position eingefügt.  
  
```
POSITION InsertBefore(POSITION pos, INARGTYPE element);
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Das neue Element wird in der Liste vor dieser Positionswert eingefügt werden.  
  
 `element`  
 Das Element eingefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert für die POSITION des neuen Elements zurück.  
  
### <a name="remarks"></a>Hinweise  
 Debug-Builds erfolgt ein Assertionsfehler ausgelöst, wenn die Liste nicht gültig ist, wenn der Vorgang schlägt fehl, oder wenn versucht wird, legen Sie das Element vor dem Anfang.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#24](../../atl/codesnippet/cpp/catllist-class_12.cpp)]  
  
##  <a name="isempty"></a>  CAtlList::IsEmpty  
 Rufen Sie diese Methode, um zu bestimmen, ob die Liste leer ist.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die Liste keine Objekte enthalten ist, andernfalls "false" enthält.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#25](../../atl/codesnippet/cpp/catllist-class_13.cpp)]  
  
##  <a name="movetohead"></a>  CAtlList::MoveToHead  
 Rufen Sie diese Methode, um das angegebene Element an den Anfang der Liste zu verschieben.  
  
```
void MoveToHead(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Der Wert der POSITION des Elements verschoben.  
  
### <a name="remarks"></a>Hinweise  
 Das angegebene Element wird an den Anfang der Liste aus seiner aktuellen Position verschoben. Debug-Builds wird ein Assertionsfehler auftreten, wenn `pos` gleich NULL.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#26](../../atl/codesnippet/cpp/catllist-class_14.cpp)]  
  
##  <a name="movetotail"></a>  CAtlList::MoveToTail  
 Rufen Sie diese Methode, um das angegebene Element an das Ende der Liste zu verschieben.  
  
```
void MoveToTail(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Der Wert der POSITION des Elements verschoben.  
  
### <a name="remarks"></a>Hinweise  
 Das angegebene Element wird aus der aktuellen Position in das Ende der Liste verschoben. Debug-Builds wird ein Assertionsfehler auftreten, wenn `pos` gleich NULL.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlList::MoveToHead](#movetohead).  
  
##  <a name="removeall"></a>  CAtlList::RemoveAll  
 Rufen Sie diese Methode, um alle Elemente aus der Liste zu entfernen.  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode entfernt alle Elemente aus der Liste, und gibt den belegten Arbeitsspeicher frei. In Builds den Debugger, wird ein ATLASSERT ausgelöst, wenn alle Elemente gelöscht, es sei oder der richtigen Listenstruktur beschädigt wurde.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlList::IsEmpty](#isempty).  
  
##  <a name="removeat"></a>  CAtlList::RemoveAt  
 Rufen Sie diese Methode, um ein einzelnes Element aus der Liste zu entfernen.  
  
```
void RemoveAt(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Der Wert der POSITION des zu entfernenden Elements.  
  
### <a name="remarks"></a>Hinweise  
 Das Element verweist `pos` wird entfernt, und der Arbeitsspeicher freigegeben wird. Es ist zulässig, verwenden Sie `RemoveAt` der Kopf oder das Ende der Liste zu entfernen.  
  
 Debug-Builds erfolgt ein Assertionsfehler ausgelöst, wenn die Liste nicht gültig ist oder entfernen das Element die Liste auf den Speicher verursacht werden, die nicht Teil der richtigen Listenstruktur ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#27](../../atl/codesnippet/cpp/catllist-class_15.cpp)]  
  
##  <a name="removehead"></a>  CAtlList::RemoveHead  
 Rufen Sie diese Methode, um das Element am Anfang der Liste zu entfernen.  
  
```
E RemoveHead();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Element am Anfang der Liste zurück.  
  
### <a name="remarks"></a>Hinweise  
 Das Head-Element aus der Liste gelöscht wird, und Arbeitsspeicher freigegeben wird. Eine Kopie des Elements wird zurückgegeben. In Debugbuilds erfolgt ein Assertionsfehler ausgelöst, wenn die Liste leer ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#28](../../atl/codesnippet/cpp/catllist-class_16.cpp)]  
  
##  <a name="removeheadnoreturn"></a>  CAtlList::RemoveHeadNoReturn  
 Rufen Sie diese Methode, um das Element am Anfang der Liste zu entfernen, ohne einen Wert zurückgeben.  
  
```
void RemoveHeadNoReturn() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Head-Element aus der Liste gelöscht wird, und Arbeitsspeicher freigegeben wird. In Debugbuilds erfolgt ein Assertionsfehler ausgelöst, wenn die Liste leer ist.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlList::IsEmpty](#isempty).  
  
##  <a name="removetail"></a>  CAtlList::RemoveTail  
 Rufen Sie diese Methode, um das Element am Ende der Liste zu entfernen.  
  
```
E RemoveTail();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Element am Ende der Liste zurück.  
  
### <a name="remarks"></a>Hinweise  
 Tail-Element aus der Liste gelöscht wird, und Arbeitsspeicher freigegeben wird. Eine Kopie des Elements wird zurückgegeben. In Debugbuilds erfolgt ein Assertionsfehler ausgelöst, wenn die Liste leer ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#29](../../atl/codesnippet/cpp/catllist-class_17.cpp)]  
  
##  <a name="removetailnoreturn"></a>  CAtlList::RemoveTailNoReturn  
 Rufen Sie diese Methode, um das Element am Ende der Liste zu entfernen, ohne einen Wert zurückgeben.  
  
```
void RemoveTailNoReturn() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Tail-Element aus der Liste gelöscht wird, und Arbeitsspeicher freigegeben wird. In Debugbuilds erfolgt ein Assertionsfehler ausgelöst, wenn die Liste leer ist.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlList::IsEmpty](#isempty).  
  
##  <a name="setat"></a>  CAtlList::SetAt  
 Rufen Sie diese Methode, um den Wert des Elements an einer bestimmten Position in der Liste festzulegen.  
  
```
void SetAt(POSITION pos, INARGTYPE element);
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Der Positionswert entspricht, um das Element zu ändern.  
  
 `element`  
 Der neue Elementwert.  
  
### <a name="remarks"></a>Hinweise  
 Ersetzt den vorhandenen Wert durch `element`. Debug-Builds wird ein Assertionsfehler auftreten, wenn `pos` gleich NULL.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#30](../../atl/codesnippet/cpp/catllist-class_18.cpp)]  
  
##  <a name="swapelements"></a>  CAtlList::SwapElements  
 Rufen Sie diese Methode zum Wechseln von Elementen in der Liste.  
  
```
void SwapElements(POSITION pos1, POSITION pos2) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *POS1*  
 Die erste POSITION-Wert.  
  
 *pos2*  
 Die zweite POSITION-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Vertauscht die Elemente bei der zwei angegebenen Positionen. Debug-Builds erfolgt ein Assertionsfehler ausgelöst, wenn entweder Positionswert gleich NULL ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#31](../../atl/codesnippet/cpp/catllist-class_19.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CList-Klasse](../../mfc/reference/clist-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
