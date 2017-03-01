---
title: CAtlList Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CAtlList
- CAtlList
- ATL::CAtlList
dev_langs:
- C++
helpviewer_keywords:
- CAtlList class
ms.assetid: 09e98053-64b2-4efa-99ab-d0542caaf981
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b1ed350da625695f610980f9f48a6ae11394d3c8
ms.lasthandoff: 02/24/2017

---
# <a name="catllist-class"></a>CAtlList-Klasse
Diese Klasse stellt Methoden zum Erstellen und verwalten ein List-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<typename E, class ETraits = CElementTraits<E>>  
class CAtlList
```  
  
#### <a name="parameters"></a>Parameter  
 `E`  
 Der Elementtyp.  
  
 `ETraits`  
 Der Code verwendet, um die Elemente kopiert oder verschoben. Finden Sie unter [CElementTraits Klasse](../../atl/reference/celementtraits-class.md) für weitere Details.  
  
## <a name="members"></a>Mitglieder  
  
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
|[CAtlList::AddHead](#addhead)|Rufen Sie diese Methode, um den Anfang der Liste ein Element hinzugefügt.|  
|[CAtlList::AddHeadList](#addheadlist)|Rufen Sie diese Methode, um eine vorhandene Liste an den Anfang der Liste hinzufügen.|  
|[CAtlList::AddTail](#addtail)|Rufen Sie diese Methode, um das Ende der Liste ein Element hinzugefügt.|  
|[CAtlList::AddTailList](#addtaillist)|Rufen Sie diese Methode, um das Ende der Liste eine vorhandene Liste hinzugefügt.|  
|[CAtlList::AssertValid](#assertvalid)|Rufen Sie diese Methode, um zu bestätigen, dass die Liste gültig ist.|  
|[CAtlList::Find](#find)|Rufen Sie diese Methode, um die Liste für das angegebene Element zu suchen.|  
|[CAtlList::FindIndex](#findindex)|Rufen Sie diese Methode, um die Position eines Elements zu erhalten, erhält einen Indexwert.|  
|[CAtlList::GetAt](#getat)|Rufen Sie diese Methode, um das Element an der angegebenen Position in der Liste zurück.|  
|[CAtlList::GetCount](#getcount)|Rufen Sie diese Methode, um die Anzahl der Objekte in der Liste zurück.|  
|[CAtlList::GetHead](#gethead)|Rufen Sie diese Methode, um das Element am Anfang der Liste zurück.|  
|[CAtlList::GetHeadPosition](#getheadposition)|Rufen Sie diese Methode, um die Position der den Anfang der Liste abzurufen.|  
|[CAtlList::GetNext](#getnext)|Rufen Sie diese Methode, um das nächste Element aus der Liste zurück.|  
|[CAtlList::GetPrev](#getprev)|Rufen Sie diese Methode, um das vorherige Element in der Liste zurück.|  
|[CAtlList::GetTail](#gettail)|Rufen Sie diese Methode, um das Element am Ende der Liste zurück.|  
|[CAtlList::GetTailPosition](#gettailposition)|Rufen Sie diese Methode, um die Position der das Ende der Liste abzurufen.|  
|[CAtlList::InsertAfter](#insertafter)|Rufen Sie diese Methode, um ein neues Element in der Liste nach der angegebenen Position eingefügt.|  
|[CAtlList::InsertBefore](#insertbefore)|Rufen Sie diese Methode, um ein neues Element in der Liste vor der angegebenen Position eingefügt.|  
|[CAtlList::IsEmpty](#isempty)|Rufen Sie diese Methode, um zu bestimmen, ob die Liste leer ist.|  
|[CAtlList::MoveToHead](#movetohead)|Rufen Sie diese Methode, um das angegebene Element an den Anfang der Liste zu verschieben.|  
|[CAtlList::MoveToTail](#movetotail)|Rufen Sie diese Methode, um das angegebene Element an das Ende der Liste zu verschieben.|  
|[CAtlList::RemoveAll](#removeall)|Rufen Sie diese Methode, um alle Elemente aus der Liste zu entfernen.|  
|[CAtlList::RemoveAt](#removeat)|Rufen Sie diese Methode, um ein einzelnes Element aus der Liste zu entfernen.|  
|[CAtlList::RemoveHead](#removehead)|Rufen Sie diese Methode, um das Element am Anfang der Liste zu entfernen.|  
|[CAtlList::RemoveHeadNoReturn](#removeheadnoreturn)|Rufen Sie diese Methode, um das Element am Anfang der Liste zu entfernen, ohne einen Wert zurückzugeben.|  
|[CAtlList::RemoveTail](#removetail)|Rufen Sie diese Methode, um das Element am Ende der Liste zu entfernen.|  
|[CAtlList::RemoveTailNoReturn](#removetailnoreturn)|Rufen Sie diese Methode, um das Element am Ende der Liste zu entfernen, ohne einen Wert zurückzugeben.|  
|[CAtlList::SetAt](#setat)|Rufen Sie diese Methode, um den Wert des Elements an einer bestimmten Position in der Liste fest.|  
|[CAtlList::SwapElements](#swapelements)|Rufen Sie diese Methode, um Elemente in der Liste austauschen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CAtlList` -Klasse unterstützt sortierte Listen mit Objekten zugegriffen werden kann, nicht eindeutig, sequenziell oder über den Wert. `CAtlList`Listen Verhalten sich wie doppelt verknüpfte Listen. Jede Liste verfügt über eine Anfangs- und Endwert und neue Elemente (oder Listen in einigen Fällen) an einem Ende der Liste hinzugefügt, oder eingefügt werden können vor oder nach bestimmten Elementen.  
  
 Die meisten der `CAtlList` Methoden stellen einen Positionswert verwenden. Dieser Wert wird von den Methoden verwendet, um die tatsächliche Speicheradresse verweisen, in dem die Elemente gespeichert sind, und nicht berechnet oder direkt vorhergesagt. Bei Bedarf für den Zugriff auf die *n*th-Element in der Liste der Methode [CAtlList::FindIndex](#findindex) gibt den Wert für die entsprechende Position für einen bestimmten Index zurück. Die Methoden [CAtlList::GetNext](#getnext) und [CAtlList::GetPrev](#getprev) kann zum Durchlaufen der Objekte in der Liste verwendet werden.  
  
 Weitere Informationen zu den verfügbaren mit ATL-Auflistungsklassen, finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="a-nameaddheada--catllistaddhead"></a><a name="addhead"></a>CAtlList::AddHead  
 Rufen Sie diese Methode, um den Anfang der Liste ein Element hinzugefügt.  
  
```
POSITION AddHead();
POSITION AddHead(INARGTYPE element);
```  
  
### <a name="parameters"></a>Parameter  
 `element`  
 Das neue Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Position des hinzugefügten Elements.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die erste Version verwendet wird, wird ein leeres Element erstellt, mit seinem Standardkonstruktor und nicht mit den Kopierkonstruktor.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#13;](../../atl/codesnippet/cpp/catllist-class_1.cpp)]  
  
##  <a name="a-nameaddheadlista--catllistaddheadlist"></a><a name="addheadlist"></a>CAtlList::AddHeadList  
 Rufen Sie diese Methode, um eine vorhandene Liste an den Anfang der Liste hinzufügen.  
  
```
void AddHeadList(const CAtlList<E, ETraits>* plNew);
```  
  
### <a name="parameters"></a>Parameter  
 `plNew`  
 Die Liste hinzugefügt werden.  
  
### <a name="remarks"></a>Hinweise  
 Die Liste zeigt `plNew` wird zu Beginn der vorhandenen Liste eingefügt. Debug-Builds wird ein Assertionsfehler auftreten, wenn `plNew` gleich NULL ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&14;](../../atl/codesnippet/cpp/catllist-class_2.cpp)]  
  
##  <a name="a-nameaddtaila--catllistaddtail"></a><a name="addtail"></a>CAtlList::AddTail  
 Rufen Sie diese Methode, um das Ende der Liste ein Element hinzugefügt.  
  
```
POSITION AddTail();
POSITION AddTail(INARGTYPE element);
```  
  
### <a name="parameters"></a>Parameter  
 `element`  
 Das hinzuzufügende Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die POSITION des hinzugefügten Elements.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die erste Version verwendet wird, wird ein leeres Element erstellt, mit seinem Standardkonstruktor und nicht mit den Kopierkonstruktor. Das Element wird am Ende der Liste hinzugefügt, und daher wird es nun das Ende. Diese Methode kann mit einer leeren Liste verwendet werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#15;](../../atl/codesnippet/cpp/catllist-class_3.cpp)]  
  
##  <a name="a-nameaddtaillista--catllistaddtaillist"></a><a name="addtaillist"></a>CAtlList::AddTailList  
 Rufen Sie diese Methode, um das Ende der Liste eine vorhandene Liste hinzugefügt.  
  
```
void AddTailList(const CAtlList<E, ETraits>* plNew);
```  
  
### <a name="parameters"></a>Parameter  
 `plNew`  
 Die Liste hinzugefügt werden.  
  
### <a name="remarks"></a>Hinweise  
 Die Liste zeigt `plNew` wird eingefügt, nachdem das letzte Element (sofern vorhanden) in der Liste. Das letzte Element in der `plNew` -Liste wird daher die Tail. Debug-Builds wird ein Assertionsfehler auftreten, wenn *PlNew* gleich NULL ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities Nr.&16;](../../atl/codesnippet/cpp/catllist-class_4.cpp)]  
  
##  <a name="a-nameassertvalida--catllistassertvalid"></a><a name="assertvalid"></a>CAtlList::AssertValid  
 Rufen Sie diese Methode, um zu bestätigen, dass die Liste gültig ist.  
  
```
void AssertValid() const;
```  
  
### <a name="remarks"></a>Hinweise  
 In Debugbuilds treten eine Assertionsfehler ausgelöst, wenn das Listenobjekt nicht gültig ist. Um gültig zu sein, eine leere Liste benötigen sowohl Anfang und Ende auf NULL muss, und eine Liste, die nicht leer ist sowohl Anfang und Ende gültige Adressen auf.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&17;](../../atl/codesnippet/cpp/catllist-class_5.cpp)]  
  
##  <a name="a-namecatllista--catllistcatllist"></a><a name="catllist"></a>CAtlList::CAtlList  
 Der Konstruktor.  
  
```
CAtlList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nBlockSize`  
 Die Blockgröße.  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor für die `CAtlList` Objekt. Die Blockgröße ist ein Maß für die Menge des Arbeitsspeichers, wenn ein neues Element erforderlich ist. Größere Blöcke reduziert Aufrufe an Arbeitsspeicher, aber mehr Ressourcen verwenden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&18;](../../atl/codesnippet/cpp/catllist-class_6.cpp)]  
  
##  <a name="a-namedtora--catllistcatllist"></a><a name="dtor"></a>CAtlList:: ~ CAtlList  
 Der Destruktor.  
  
```
~CAtlList() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Alle zugeordnete Ressourcen freigegeben, einschließlich eines Aufrufs von [CAtlList::RemoveAll](#removeall) alle Elemente aus der Liste entfernt.  
  
 Debug-Builds wird ein Assertionsfehler auftreten, enthält die Liste weiterhin einige Elemente nach dem Aufruf von `RemoveAll`.  
  
##  <a name="a-namefinda--catllistfind"></a><a name="find"></a>CAtlList::Find  
 Rufen Sie diese Methode, um die Liste für das angegebene Element zu suchen.  
  
```
POSITION Find(INARGTYPE element, POSITION posStartAfter = NULL) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `element`  
 Das Element in der Liste gefunden werden.  
  
 `posStartAfter`  
 Die Startposition für die Suche. Wenn kein Wert angegeben wird, beginnt die Suche mit der Head-Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert für die POSITION des Elements zurück, wenn gefunden, andernfalls NULL.  
  
### <a name="remarks"></a>Hinweise  
 In Debugbuilds wird ein Assertionsfehler auftreten, wenn das List-Objekt ungültig ist oder wenn der `posStartAfter` Wert liegt außerhalb des Bereichs.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities Nr.&19;](../../atl/codesnippet/cpp/catllist-class_7.cpp)]  
  
##  <a name="a-namefindindexa--catllistfindindex"></a><a name="findindex"></a>CAtlList::FindIndex  
 Rufen Sie diese Methode, um die Position eines Elements zu erhalten, erhält einen Indexwert.  
  
```
POSITION FindIndex(size_t iElement) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `iElement`  
 Der nullbasierte Index des Listenelements erforderlichen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert der entsprechenden POSITION oder NULL zurück, wenn `iElement` liegt außerhalb des Bereichs.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt die POSITION in einen angegebenen Index entspricht, die Zugriff auf die *n*th-Element in der Liste.  
  
 In Debugbuilds treten eine Assertionsfehler ausgelöst, wenn das Listenobjekt nicht gültig ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&20;](../../atl/codesnippet/cpp/catllist-class_8.cpp)]  
  
##  <a name="a-namegetata--catllistgetat"></a><a name="getat"></a>CAtlList::GetAt  
 Rufen Sie diese Methode, um das Element an der angegebenen Position in der Liste zurück.  
  
```
E& GetAt(POSITION pos) throw();
const E& GetAt(POSITION pos) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Der Wert für ein bestimmtes Element angeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf oder eine Kopie des Elements.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Liste **const**, `GetAt` gibt eine Kopie des Elements zurück. Dadurch können die Methode, die nur auf der rechten Seite einer zuweisungsanweisung verwendet werden und die Liste vor Manipulationen geschützt.  
  
 Wenn die Liste nicht **const**, `GetAt` gibt einen Verweis auf das Element zurück. Dadurch können die Methode, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und daher Einträge in der Liste geändert werden.  
  
 Debug-Builds wird ein Assertionsfehler auftreten, wenn `pos` gleich NULL ist.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlList::FindIndex](#findindex).  
  
##  <a name="a-namegetcounta--catllistgetcount"></a><a name="getcount"></a>CAtlList::GetCount  
 Rufen Sie diese Methode, um die Anzahl der Objekte in der Liste zurück.  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl von Elementen in der Liste zurück.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlList::Find](#find).  
  
##  <a name="a-namegetheada--catllistgethead"></a><a name="gethead"></a>CAtlList::GetHead  
 Rufen Sie diese Methode, um das Element am Anfang der Liste zurück.  
  
```
E& GetHead() throw();
const E& GetHead() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf oder eine Kopie des Elements am Anfang der Liste zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Liste **const**, `GetHead` gibt eine Kopie des Elements am Anfang der Liste zurück. Dadurch können die Methode, die nur auf der rechten Seite einer zuweisungsanweisung verwendet werden und die Liste vor Manipulationen geschützt.  
  
 Wenn die Liste nicht **const**, `GetHead` gibt einen Verweis auf das Element am Anfang der Liste zurück. Dadurch können die Methode, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und daher Einträge in der Liste geändert werden.  
  
 In Debugbuilds treten eine Assertionsfehler ausgelöst, wenn der Anfang der Liste auf NULL zeigt.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlList::AddHead](#addhead).  
  
##  <a name="a-namegetheadpositiona--catllistgetheadposition"></a><a name="getheadposition"></a>CAtlList::GetHeadPosition  
 Rufen Sie diese Methode, um die Position der den Anfang der Liste abzurufen.  
  
```
POSITION GetHeadPosition() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert für die POSITION für das Element am Anfang der Liste zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Liste leer ist, ist der Rückgabewert NULL.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&21;](../../atl/codesnippet/cpp/catllist-class_9.cpp)]  
  
##  <a name="a-namegetnexta--catllistgetnext"></a><a name="getnext"></a>CAtlList::GetNext  
 Rufen Sie diese Methode, um das nächste Element aus der Liste zurück.  
  
```
E& GetNext(POSITION& pos) throw();
const E& GetNext(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Ein Positionswert, von einem vorherigen Aufruf zurückgegebene `GetNext`, [CAtlList::GetHeadPosition](#getheadposition), oder andere `CAtlList` Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Liste **const**, `GetNext` gibt eine Kopie das nächste Element der Liste zurück. Dadurch können die Methode, die nur auf der rechten Seite einer zuweisungsanweisung verwendet werden und die Liste vor Manipulationen geschützt.  
  
 Wenn die Liste nicht **const**, `GetNext` gibt einen Verweis auf das nächste Element der Liste zurück. Dadurch können die Methode, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und daher Einträge in der Liste geändert werden.  
  
### <a name="remarks"></a>Hinweise  
 Der Zähler POSITION `pos`, wird aktualisiert, um auf das nächste Element in der Liste, oder NULL, wenn keine Elemente mehr vorhanden sind. Debug-Builds wird ein Assertionsfehler auftreten, wenn `pos` gleich NULL ist.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlList::GetHeadPosition](#getheadposition).  
  
##  <a name="a-namegetpreva--catllistgetprev"></a><a name="getprev"></a>CAtlList::GetPrev  
 Rufen Sie diese Methode, um das vorherige Element in der Liste zurück.  
  
```
E& GetPrev(POSITION& pos) throw();
const E& GetPrev(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Ein Positionswert, von einem vorherigen Aufruf zurückgegebene `GetPrev`, [CAtlList::GetTailPosition](#gettailposition), oder andere `CAtlList` Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Liste **const**, `GetPrev` gibt eine Kopie eines Elements in der Liste zurück. Dadurch können die Methode, die nur auf der rechten Seite einer zuweisungsanweisung verwendet werden und die Liste vor Manipulationen geschützt.  
  
 Wenn die Liste nicht **const**, `GetPrev` gibt einen Verweis auf ein Element der Liste zurück. Dadurch können die Methode, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und daher Einträge in der Liste geändert werden.  
  
### <a name="remarks"></a>Hinweise  
 Der Zähler POSITION `pos`, wird aktualisiert, um auf das vorherige Element in der Liste, oder NULL, wenn keine Elemente mehr vorhanden sind. Debug-Builds wird ein Assertionsfehler auftreten, wenn `pos` gleich NULL ist.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlList::GetTailPosition](#gettailposition).  
  
##  <a name="a-namegettaila--catllistgettail"></a><a name="gettail"></a>CAtlList::GetTail  
 Rufen Sie diese Methode, um das Element am Ende der Liste zurück.  
  
```
E& GetTail() throw();
const E& GetTail() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf oder eine Kopie des Elements am Ende der Liste zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Liste **const**, `GetTail` gibt eine Kopie des Elements am Anfang der Liste zurück. Dadurch können die Methode, die nur auf der rechten Seite einer zuweisungsanweisung verwendet werden und die Liste vor Manipulationen geschützt.  
  
 Wenn die Liste nicht **const**, `GetTail` gibt einen Verweis auf das Element am Anfang der Liste zurück. Dadurch können die Methode, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und daher Einträge in der Liste geändert werden.  
  
 In Debugbuilds treten eine Assertionsfehler ausgelöst, wenn das Ende der Liste auf NULL verweist.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlList::AddTail](#addtail).  
  
##  <a name="a-namegettailpositiona--catllistgettailposition"></a><a name="gettailposition"></a>CAtlList::GetTailPosition  
 Rufen Sie diese Methode, um die Position der das Ende der Liste abzurufen.  
  
```
POSITION GetTailPosition() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert für die POSITION für das Element am Ende der Liste zurück.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Liste leer ist, ist der Rückgabewert NULL.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#22;](../../atl/codesnippet/cpp/catllist-class_10.cpp)]  
  
##  <a name="a-nameinargtypea--catllistinargtype"></a><a name="inargtype"></a>CAtlList::INARGTYPE  
 -Typ, wenn ein Element als Eingabeargument übergeben wird.  
  
```
typedef ETraits::INARGTYPE INARGTYPE;
```  
  
##  <a name="a-nameinsertaftera--catllistinsertafter"></a><a name="insertafter"></a>CAtlList::InsertAfter  
 Rufen Sie diese Methode, um ein neues Element in der Liste nach der angegebenen Position eingefügt.  
  
```
POSITION InsertAfter(POSITION pos, INARGTYPE element);
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Der Wert nach dem das neue Element eingefügt wird.  
  
 `element`  
 Das Element eingefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert für die POSITION des neuen Elements zurück.  
  
### <a name="remarks"></a>Hinweise  
 In Debugbuilds treten eine Assertionsfehler ausgelöst, wenn die Liste nicht gültig ist, schlägt das Einfügen, oder wenn versucht wird, legen Sie das Element nach unten.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&23;](../../atl/codesnippet/cpp/catllist-class_11.cpp)]  
  
##  <a name="a-nameinsertbeforea--catllistinsertbefore"></a><a name="insertbefore"></a>CAtlList::InsertBefore  
 Rufen Sie diese Methode, um ein neues Element in der Liste vor der angegebenen Position eingefügt.  
  
```
POSITION InsertBefore(POSITION pos, INARGTYPE element);
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Das neue Element wird in der Liste vor dieser POSITION eingefügt werden.  
  
 `element`  
 Das Element eingefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert für die POSITION des neuen Elements zurück.  
  
### <a name="remarks"></a>Hinweise  
 In Debugbuilds treten eine Assertionsfehler ausgelöst, wenn die Liste nicht gültig ist, schlägt das Einfügen, oder wenn versucht wird, das Element vor dem Einfügen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#24;](../../atl/codesnippet/cpp/catllist-class_12.cpp)]  
  
##  <a name="a-nameisemptya--catllistisempty"></a><a name="isempty"></a>CAtlList::IsEmpty  
 Rufen Sie diese Methode, um zu bestimmen, ob die Liste leer ist.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn die Liste keine Objekte enthalten ist, andernfalls "false" enthält.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#25;](../../atl/codesnippet/cpp/catllist-class_13.cpp)]  
  
##  <a name="a-namemovetoheada--catllistmovetohead"></a><a name="movetohead"></a>CAtlList::MoveToHead  
 Rufen Sie diese Methode, um das angegebene Element an den Anfang der Liste zu verschieben.  
  
```
void MoveToHead(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Der Wert des Elements verschoben.  
  
### <a name="remarks"></a>Hinweise  
 Das angegebene Element wird von der aktuellen Position an den Anfang der Liste verschoben. Debug-Builds wird ein Assertionsfehler auftreten, wenn `pos` gleich NULL ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#26;](../../atl/codesnippet/cpp/catllist-class_14.cpp)]  
  
##  <a name="a-namemovetotaila--catllistmovetotail"></a><a name="movetotail"></a>CAtlList::MoveToTail  
 Rufen Sie diese Methode, um das angegebene Element an das Ende der Liste zu verschieben.  
  
```
void MoveToTail(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Der Wert des Elements verschoben.  
  
### <a name="remarks"></a>Hinweise  
 Das angegebene Element wird von der aktuellen Position an das Ende der Liste verschoben. Debug-Builds wird ein Assertionsfehler auftreten, wenn `pos` gleich NULL ist.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlList::MoveToHead](#movetohead).  
  
##  <a name="a-nameremovealla--catllistremoveall"></a><a name="removeall"></a>CAtlList::RemoveAll  
 Rufen Sie diese Methode, um alle Elemente aus der Liste zu entfernen.  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode entfernt alle Elemente aus der Liste und den reservierten Speicher frei. In debuggt wird wird ein ATLASSERT ausgelöst, wenn alle Elemente gelöscht werden oder wenn die Listenstruktur beschädigt wurde.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlList::IsEmpty](#isempty).  
  
##  <a name="a-nameremoveata--catllistremoveat"></a><a name="removeat"></a>CAtlList::RemoveAt  
 Rufen Sie diese Methode, um ein einzelnes Element aus der Liste zu entfernen.  
  
```
void RemoveAt(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Der Wert des zu entfernenden Elements.  
  
### <a name="remarks"></a>Hinweise  
 Das Element, auf die verwiesen wird `pos` wird entfernt, und der Speicher freigegeben wird. Es ist akzeptabel, verwenden Sie `RemoveAt` an den Anfang oder das Ende der Liste zu entfernen.  
  
 Debug-Builds wird ein Assertionsfehler auftreten, wenn die Liste nicht gültig ist oder Entfernen des Elements wird die Liste auf den Speicher verursacht, die nicht Teil der Listenstruktur ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#27;](../../atl/codesnippet/cpp/catllist-class_15.cpp)]  
  
##  <a name="a-nameremoveheada--catllistremovehead"></a><a name="removehead"></a>CAtlList::RemoveHead  
 Rufen Sie diese Methode, um das Element am Anfang der Liste zu entfernen.  
  
```
E RemoveHead();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Element am Anfang der Liste.  
  
### <a name="remarks"></a>Hinweise  
 Das Head-Element aus der Liste gelöscht wird, und Speicher freigegeben wird. Eine Kopie des Elements wird zurückgegeben. In Debugbuilds treten eine Assertionsfehler ausgelöst, wenn die Liste leer ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#28;](../../atl/codesnippet/cpp/catllist-class_16.cpp)]  
  
##  <a name="a-nameremoveheadnoreturna--catllistremoveheadnoreturn"></a><a name="removeheadnoreturn"></a>CAtlList::RemoveHeadNoReturn  
 Rufen Sie diese Methode, um das Element am Anfang der Liste zu entfernen, ohne einen Wert zurückzugeben.  
  
```
void RemoveHeadNoReturn() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Head-Element aus der Liste gelöscht wird, und Speicher freigegeben wird. In Debugbuilds treten eine Assertionsfehler ausgelöst, wenn die Liste leer ist.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlList::IsEmpty](#isempty).  
  
##  <a name="a-nameremovetaila--catllistremovetail"></a><a name="removetail"></a>CAtlList::RemoveTail  
 Rufen Sie diese Methode, um das Element am Ende der Liste zu entfernen.  
  
```
E RemoveTail();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Element am Ende der Liste.  
  
### <a name="remarks"></a>Hinweise  
 Das Tail-Element wird aus der Liste gelöscht, und Speicher freigegeben wird. Eine Kopie des Elements wird zurückgegeben. In Debugbuilds treten eine Assertionsfehler ausgelöst, wenn die Liste leer ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#29;](../../atl/codesnippet/cpp/catllist-class_17.cpp)]  
  
##  <a name="a-nameremovetailnoreturna--catllistremovetailnoreturn"></a><a name="removetailnoreturn"></a>CAtlList::RemoveTailNoReturn  
 Rufen Sie diese Methode, um das Element am Ende der Liste zu entfernen, ohne einen Wert zurückzugeben.  
  
```
void RemoveTailNoReturn() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Tail-Element wird aus der Liste gelöscht, und Speicher freigegeben wird. In Debugbuilds treten eine Assertionsfehler ausgelöst, wenn die Liste leer ist.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CAtlList::IsEmpty](#isempty).  
  
##  <a name="a-namesetata--catllistsetat"></a><a name="setat"></a>CAtlList::SetAt  
 Rufen Sie diese Methode, um den Wert des Elements an einer bestimmten Position in der Liste fest.  
  
```
void SetAt(POSITION pos, INARGTYPE element);
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Der Wert für das Element zu ändern.  
  
 `element`  
 Der neue Elementwert.  
  
### <a name="remarks"></a>Hinweise  
 Ersetzt den vorhandenen Wert mit `element`. Debug-Builds wird ein Assertionsfehler auftreten, wenn `pos` gleich NULL ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#30;](../../atl/codesnippet/cpp/catllist-class_18.cpp)]  
  
##  <a name="a-nameswapelementsa--catllistswapelements"></a><a name="swapelements"></a>CAtlList::SwapElements  
 Rufen Sie diese Methode, um Elemente in der Liste austauschen.  
  
```
void SwapElements(POSITION pos1, POSITION pos2) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *POS1*  
 Der erste Wert.  
  
 *pos2*  
 Der zweite Wert.  
  
### <a name="remarks"></a>Hinweise  
 Tauscht die Elemente bei der zwei angegebenen Positionen. In Debugbuilds treten eine Assertionsfehler ausgelöst, wenn entweder Positionswert gleich NULL ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#31;](../../atl/codesnippet/cpp/catllist-class_19.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CList-Klasse](../../mfc/reference/clist-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

