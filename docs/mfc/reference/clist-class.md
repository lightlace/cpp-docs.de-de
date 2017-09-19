---
title: CList-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- lists
- lists, base class for
- CList class
ms.assetid: 6f6273c3-c8f6-47f5-ac2a-0a950379ae5d
caps.latest.revision: 23
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 05d35419f70ab039e6981938c516201b252878d4
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="clist-class"></a>CList-Klasse
Unterstützt sortierte Listen mit Objekten, die nicht eindeutig sein müssen, und auf die sequenziell oder über den Wert zugegriffen werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class TYPE, class ARG_TYPE = const TYPE&>  
class CList : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CList::CList](#clist)|Erstellt eine leere sortierte Liste.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CList::AddHead](#addhead)|Fügt ein Element (oder alle Elemente in einer anderen Liste) an den Anfang der Liste (wird eine neue Head).|  
|[CList::AddTail](#addtail)|Fügt ein Element (oder alle Elemente in einer anderen Liste) an das Ende der Liste (wird eine neue Erweiterung).|  
|[CList::Find](#find)|Ruft die Position eines Elements durch Zeigerwert angegeben.|  
|[CList::FindIndex](#findindex)|Ruft die Position eines Elements durch einen nullbasierten Index angegeben.|  
|[CList::GetAt](#getat)|Ruft das Element an einer angegebenen Position ab.|  
|[CList::GetCount](#getcount)|Gibt die Anzahl der Elemente in dieser Liste zurück.|  
|[CList::GetHead](#gethead)|Gibt das Head-Element der Liste (darf nicht leer sein).|  
|[CList::GetHeadPosition](#getheadposition)|Gibt die Position des Head-Element der Liste zurück.|  
|[CList::GetNext](#getnext)|Ruft das nächste Element durchlaufen werden können.|  
|[CList::GetPrev](#getprev)|Ruft das vorherige Element durchlaufen werden können.|  
|[CList::GetSize](#getsize)|Gibt die Anzahl der Elemente in dieser Liste zurück.|  
|[CList::GetTail](#gettail)|Gibt das Ende der Liste (darf nicht leer sein) zurück.|  
|[CList::GetTailPosition](#gettailposition)|Gibt die Position des Elements Ende der Liste.|  
|[CList::InsertAfter](#insertafter)|Fügt ein neues Element nach einer angegebenen Position ein.|  
|[CList::InsertBefore](#insertbefore)|Fügt vor einer angegebenen Position ein neues Element.|  
|[CList::IsEmpty](#isempty)|Tests für die leere Liste Bedingung (keine Elemente).|  
|[CList::RemoveAll](#removeall)|Entfernt alle Elemente aus dieser Liste.|  
|[CList::RemoveAt](#removeat)|Entfernt ein Element aus dieser Liste anhand der Position angegeben.|  
|[CList::RemoveHead](#removehead)|Entfernt das Element am Anfang der Liste.|  
|[CList::RemoveTail](#removetail)|Entfernt das Element dem Ende der Liste aus.|  
|[CList::SetAt](#setat)|Legt das Element an einer bestimmten Position fest.|  
  
#### <a name="parameters"></a>Parameter  
 `TYPE`  
 Typ des Objekts in der Liste gespeichert.  
  
 `ARG` *_* `TYPE`  
 Typ, der in der Liste gespeicherte Objekte zu verweisen. Ein Verweis kann sein.  
  
## <a name="remarks"></a>Hinweise  
 `CList`Listen Verhalten sich wie doppelt verknüpfte Listen.  
  
 Eine Variable vom Typ **POSITION** ist ein Schlüssel für die Liste. Sie können eine **POSITION** Variable als ein Iterator eine Liste sequenziell zu durchlaufen und ein Lesezeichen an einen Ort zu speichern. Eine Position ist identisch mit einem Index jedoch nicht.  
  
 Element einfügen ist sehr schnell an den Listenanfang am Ende und an einem bekannten **POSITION**. Eine sequenzielle Suche ist erforderlich, um ein Element nach Wert oder Index zu suchen. Diese Suche kann lange dauern, wenn die Liste lang ist.  
  
 Wenn Sie ein Abbild der einzelnen Elemente in der Liste benötigen, müssen Sie die Tiefe des sicherungskontexts auf 1 oder größer festlegen.  
  
 Bestimmte Memberfunktionen dieser Klasse rufen globale Hilfsfunktionen, die angepasst werden müssen, für die meisten Verwendungen von der `CList` Klasse. Finden Sie unter [Auflistungsklasse](../../mfc/reference/collection-class-helpers.md) im Abschnitt "Makros und Globals".  
  
 Weitere Informationen zur Verwendung von `CList`, finden Sie im Artikel [Sammlungen](../../mfc/collections.md).  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#35;](../../mfc/codesnippet/cpp/clist-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CList`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtempl.h  
  
##  <a name="addhead"></a>CList::AddHead  
 Fügt ein neues Element oder eine Liste von Elementen an den Anfang der Liste.  
  
```  
POSITION AddHead(ARG_TYPE newElement);  
void AddHead(CList* pNewList);
```  
  
### <a name="parameters"></a>Parameter  
 `ARG_TYPE`  
 Vorlagenparameter, der den Typ des Listenelements angibt (kann ein Verweis sein).  
  
 `newElement`  
 Das neue Element.  
  
 `pNewList`  
 Ein Zeiger auf einen anderen `CList` Liste. Die Elemente in `pNewList` wird zu dieser Liste hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die erste Version der **POSITION** Wert des neu eingefügten Element.  
  
### <a name="remarks"></a>Hinweise  
 Die Liste kann leer ist, bevor der Vorgang sein.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections Nr.&36;](../../mfc/codesnippet/cpp/clist-class_2.cpp)]  
  
##  <a name="addtail"></a>CList::AddTail  
 Fügt ein neues Element oder eine Liste von Elementen an das Ende der Liste.  
  
```  
POSITION AddTail(ARG_TYPE newElement);  
void AddTail(CList* pNewList);
```  
  
### <a name="parameters"></a>Parameter  
 `ARG_TYPE`  
 Vorlagenparameter, der den Typ des Listenelements angibt (kann ein Verweis sein).  
  
 `newElement`  
 Das Element, das der Liste hinzugefügt werden soll.  
  
 `pNewList`  
 Ein Zeiger auf einen anderen `CList` Liste. Die Elemente in `pNewList` wird zu dieser Liste hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die erste Version der **POSITION** Wert des neu eingefügten Element.  
  
### <a name="remarks"></a>Hinweise  
 Die Liste kann leer ist, bevor der Vorgang sein.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#37;](../../mfc/codesnippet/cpp/clist-class_3.cpp)]  
  
##  <a name="clist"></a>CList::CList  
 Erstellt eine leere sortierte Liste.  
  
```  
CList(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>Parameter  
 `nBlockSize`  
 Die Granularität der speicherbelegung zum Erweitern der Liste.  
  
### <a name="remarks"></a>Hinweise  
 Je umfangreicher die Liste wird in Einheiten von Arbeitsspeicher zugeordnet `nBlockSize` Einträge.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#38;](../../mfc/codesnippet/cpp/clist-class_4.cpp)]  
  
##  <a name="find"></a>CList::Find  
 Sucht die Liste sequenziell nach dem ersten Element mit dem angegebenen `searchValue`.  
  
```  
POSITION Find(
    ARG_TYPE searchValue,  
    POSITION startAfter = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `ARG_TYPE`  
 Vorlagenparameter, der den Typ des Listenelements angibt (kann ein Verweis sein).  
  
 `searchValue`  
 Der Wert in der Liste gefunden werden.  
  
 `startAfter`  
 Die Startposition für die Suche. Wenn kein Wert angegeben wird, beginnt die Suche mit der Head-Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **POSITION** -Wert, der für die Iteration oder Abrufen von Objekten Zeiger; verwendet werden kann **NULL** , wenn das Objekt nicht gefunden wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections Nr.&39;](../../mfc/codesnippet/cpp/clist-class_5.cpp)]  
  
##  <a name="findindex"></a>CList::FindIndex  
 Verwendet den Wert der `nIndex` als Index in der Liste.  
  
```  
POSITION FindIndex(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der nullbasierte Index des Listenelements gefunden werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **POSITION** -Wert, der für die Iteration oder Abrufen von Objekten Zeiger; verwendet werden kann **NULL** Wenn `nIndex` ist negativ oder zu groß.  
  
### <a name="remarks"></a>Hinweise  
 Am Anfang der Liste beenden auf einen sequenziellen Scan Starten der *n*th-Element.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#40;](../../mfc/codesnippet/cpp/clist-class_6.cpp)]  
  
##  <a name="getat"></a>CList::GetAt  
 Ruft das Listenelement an einer angegebenen Position ab.  
  
```  
TYPE& GetAt(POSITION position);  
const TYPE& GetAt(POSITION position) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *TYP*  
 Template-Parameter, die den Typ des Objekts in der Liste angibt.  
  
 *Position*  
 Die Position in der Liste des Elements, das abgerufen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert Beschreibung finden Sie `GetHead`.  
  
### <a name="remarks"></a>Hinweise  
 `GetAt`Gibt das Element (oder ein Verweis auf das Element) mit einer bestimmten Position zugeordnet. Es ist nicht identisch mit einem Index, und Sie können nicht ausgeführt werden, auf eine **POSITION** Wert selbst. Eine Variable vom Typ **POSITION** ist ein Schlüssel für die Liste.  
  
 Sie müssen sicherstellen, dass Ihre **POSITION** Wert eine gültige Position in der Liste darstellt. Wenn sie ungültig ist, überprüft dann die Debugversion der Microsoft Foundation Class-Bibliothek.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CList::GetHeadPosition](#getheadposition).  
  
##  <a name="getcount"></a>CList::GetCount  
 Ruft die Anzahl der Elemente in dieser Liste.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine ganze Zahl, die die Anzahl der Elemente enthält.  
  
### <a name="remarks"></a>Hinweise  
 Das Aufrufen dieser Methode generiert das gleiche Ergebnis wie die [CList::GetSize](#getsize) Methode.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CList::RemoveHead](#removehead).  
  
##  <a name="gethead"></a>CList::GetHead  
 Ruft das Head-Element (oder einen Verweis auf das Anfangselement) dieser Liste ab.  
  
```  
const TYPE& GetHead() const;  
  
TYPE& GetHead();
```  
  
### <a name="parameters"></a>Parameter  
 *TYP*  
 Template-Parameter, die den Typ des Objekts in der Liste angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Liste **const**, `GetHead` gibt eine Kopie des Elements am Anfang der Liste zurück. Dies kann die Funktion nur auf der rechten Seite einer zuweisungsanweisung verwendet werden und die Liste vor Manipulationen geschützt.  
  
 Wenn die Liste nicht **const**, `GetHead` gibt einen Verweis auf das Element am Anfang der Liste zurück. Dadurch können die Funktion, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und daher Einträge in der Liste geändert werden.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen sicherstellen, dass die Liste nicht leer ist, bevor der Aufruf von `GetHead`. Wenn die Liste leer ist, überprüft dann die Version der Microsoft Foundation Class-Bibliothek. Verwendung [IsEmpty](#isempty) zu überprüfen, ob die Liste Elemente enthält.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#41;](../../mfc/codesnippet/cpp/clist-class_7.cpp)]  
  
##  <a name="getheadposition"></a>CList::GetHeadPosition  
 Ruft die Position des Head-Element der Liste ab.  
  
```  
POSITION GetHeadPosition() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **POSITION** -Wert, der für die Iteration oder Abrufen von Objekten Zeiger; verwendet werden kann **NULL** , wenn die Liste leer ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#42;](../../mfc/codesnippet/cpp/clist-class_8.cpp)]  
  
##  <a name="getnext"></a>CList::GetNext  
 Ruft das Listenelement identifizierten `rPosition`, dann wird `rPosition` an der **POSITION** Wert des nächsten Eintrag in der Liste.  
  
```  
TYPE& GetNext(POSITION& rPosition);  
const TYPE& GetNext(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *TYP*  
 Template-Parameter, die den Typ der Elemente in der Liste angibt.  
  
 `rPosition`  
 Ein Verweis auf eine **POSITION** von einem vorherigen zurückgegebene Wert `GetNext`, [GetHeadPosition](#getheadposition), oder andere Member-Funktionsaufruf.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Liste **const**, `GetNext` gibt eine Kopie eines Elements in der Liste zurück. Dies kann die Funktion nur auf der rechten Seite einer zuweisungsanweisung verwendet werden und die Liste vor Manipulationen geschützt.  
  
 Wenn die Liste nicht **const**, `GetNext` gibt einen Verweis auf ein Element der Liste zurück. Dadurch können die Funktion, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und daher Einträge in der Liste geändert werden.  
  
### <a name="remarks"></a>Hinweise  
 Sie können `GetNext` in einer Iterationsschleife forward, wenn Sie die ursprüngliche Position mit einem Aufruf von einrichten `GetHeadPosition` oder **suchen**.  
  
 Sie müssen sicherstellen, dass Ihre **POSITION** Wert eine gültige Position in der Liste darstellt. Wenn sie ungültig ist, überprüft dann die Debugversion der Microsoft Foundation Class-Bibliothek.  
  
 Wenn das abgerufene Element das letzte Element in der Liste der neue Wert des ist `rPosition` Wert **NULL**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#43;](../../mfc/codesnippet/cpp/clist-class_9.cpp)]  
  
##  <a name="getprev"></a>CList::GetPrev  
 Ruft das Listenelement identifizierten `rPosition`, dann wird `rPosition` an der **POSITION** Wert des vorherigen Eintrags in der Liste.  
  
```  
TYPE& GetPrev(POSITION& rPosition);  
const TYPE& GetPrev(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *TYP*  
 Template-Parameter, die den Typ der Elemente in der Liste angibt.  
  
 `rPosition`  
 Ein Verweis auf eine **POSITION** von einem vorherigen zurückgegebene Wert `GetPrev` oder anderer Member-Funktionsaufruf.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Liste **const**, `GetPrev` gibt eine Kopie des Elements am Anfang der Liste zurück. Dies kann die Funktion nur auf der rechten Seite einer zuweisungsanweisung verwendet werden und die Liste vor Manipulationen geschützt.  
  
 Wenn die Liste nicht **const**, `GetPrev` gibt einen Verweis auf ein Element der Liste zurück. Dadurch können die Funktion, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und daher Einträge in der Liste geändert werden.  
  
### <a name="remarks"></a>Hinweise  
 Sie können `GetPrev` in einer Schleife umgekehrte Iteration, wenn Sie die ursprüngliche Position mit einem Aufruf von einrichten `GetTailPosition` oder **suchen**.  
  
 Sie müssen sicherstellen, dass Ihre **POSITION** Wert eine gültige Position in der Liste darstellt. Wenn sie ungültig ist, überprüft dann die Debugversion der Microsoft Foundation Class-Bibliothek.  
  
 Wenn das abgerufene Element der erste in der Liste dann den neuen Wert der `rPosition` Wert **NULL**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#44;](../../mfc/codesnippet/cpp/clist-class_10.cpp)]  
  
##  <a name="getsize"></a>CList::GetSize  
 Gibt die Anzahl der Elemente zurück.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in der Liste.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Anzahl der Elemente in der Liste abzurufen.  Das Aufrufen dieser Methode generiert das gleiche Ergebnis wie die [CList::GetCount](#getcount) Methode.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#45;](../../mfc/codesnippet/cpp/clist-class_11.cpp)]  
  
##  <a name="gettail"></a>CList::GetTail  
 Ruft die `CObject` Zeiger, der das Ende Element dieser Liste darstellt.  
  
```  
TYPE& GetTail();  
const TYPE& GetTail() const;  
```  
  
### <a name="parameters"></a>Parameter  
 *TYP*  
 Der Vorlagenparameter, den Typ der Elemente in der Liste angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Finden Sie in der Beschreibung Rückgabewert [GetHead](../../mfc/reference/coblist-class.md#gethead).  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen sicherstellen, dass die Liste nicht leer ist, bevor der Aufruf von `GetTail`. Wenn die Liste leer ist, überprüft dann die Version der Microsoft Foundation Class-Bibliothek. Verwendung [IsEmpty](../../mfc/reference/coblist-class.md#isempty) zu überprüfen, ob die Liste Elemente enthält.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#46;](../../mfc/codesnippet/cpp/clist-class_12.cpp)]  
  
##  <a name="gettailposition"></a>CList::GetTailPosition  
 Ruft die Position des Elements Ende dieser Liste. **NULL** , wenn die Liste leer ist.  
  
```  
POSITION GetTailPosition() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **POSITION** -Wert, der für die Iteration oder Abrufen von Objekten Zeiger; verwendet werden kann **NULL** , wenn die Liste leer ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#47;](../../mfc/codesnippet/cpp/clist-class_13.cpp)]  
  
##  <a name="insertafter"></a>CList::InsertAfter  
 Fügt ein Element dieser Liste nach dem Element an der angegebenen Position.  
  
```  
POSITION InsertAfter(POSITION position, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Parameter  
 *Position*  
 Ein von einem früheren **,** oder einem Aufruf der `GetNext`Find `GetPrev`-Memberfunktion zurückgegebener Wert für **POSITION** .  
  
 `ARG_TYPE`  
 Der Vorlagenparameter, der den List-Element angibt.  
  
 `newElement`  
 Das Element, das der Liste hinzugefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **POSITION** -Wert, der zur Iteration oder zum Abruf von Listenelementen verwendet werden kann.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#48;](../../mfc/codesnippet/cpp/clist-class_14.cpp)]  
  
##  <a name="insertbefore"></a>CList::InsertBefore  
 Fügt dieser Liste ein Element vor dem Element an der angegebenen Position hinzu.  
  
```  
POSITION InsertBefore(POSITION position, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Parameter  
 *Position*  
 Ein von einem früheren **,** oder einem Aufruf der `GetNext`Find `GetPrev`-Memberfunktion zurückgegebener Wert für **POSITION** .  
  
 `ARG_TYPE`  
 Vorlagenparameter, der den Typ des Listenelements angibt (kann ein Verweis sein).  
  
 `newElement`  
 Das Element, das der Liste hinzugefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **POSITION** -Wert, der zur Iteration oder zum Abruf von Listenelementen verwendet werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Bei einem *position* -Wert von **NULL**wird das Element am Anfang der Liste eingefügt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections Nr.&49;](../../mfc/codesnippet/cpp/clist-class_15.cpp)]  
  
##  <a name="isempty"></a>CList::IsEmpty  
 Gibt an, ob die Liste keine Elemente enthält.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn diese Liste ist leer. andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#50;](../../mfc/codesnippet/cpp/clist-class_16.cpp)]  
  
##  <a name="removeall"></a>CList::RemoveAll  
 Entfernt alle Elemente aus dieser Liste aus, und gibt den zugeordneten Arbeitsspeicher frei.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie bereits die Liste leer ist, wird kein Fehler generiert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&51;](../../mfc/codesnippet/cpp/clist-class_17.cpp)]  
  
##  <a name="removeat"></a>CList::RemoveAt  
 Entfernt das angegebene Element aus dieser Liste.  
  
```  
void RemoveAt(POSITION position);
```  
  
### <a name="parameters"></a>Parameter  
 *Position*  
 Die Position des Elements, das aus der Liste entfernt werden.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen sicherstellen, dass Ihre **POSITION** Wert eine gültige Position in der Liste darstellt. Wenn sie ungültig ist, überprüft dann die Debugversion der Microsoft Foundation Class-Bibliothek.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&52;](../../mfc/codesnippet/cpp/clist-class_18.cpp)]  
  
##  <a name="removehead"></a>CList::RemoveHead  
 Entfernt das Element am Anfang der Liste, und gibt einen Zeiger darauf zurück.  
  
```  
TYPE RemoveHead();
```  
  
### <a name="parameters"></a>Parameter  
 *TYP*  
 Der Vorlagenparameter, den Typ der Elemente in der Liste angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Element zuvor am Anfang der Liste.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen sicherstellen, dass die Liste nicht leer ist, bevor der Aufruf von `RemoveHead`. Wenn die Liste leer ist, überprüft dann die Version der Microsoft Foundation Class-Bibliothek. Verwendung [IsEmpty](#isempty) zu überprüfen, ob die Liste Elemente enthält.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#53;](../../mfc/codesnippet/cpp/clist-class_19.cpp)]  
  
##  <a name="removetail"></a>CList::RemoveTail  
 Entfernt das Element, das Ende der Liste aus, und gibt einen Zeiger darauf zurück.  
  
```  
TYPE RemoveTail();
```  
  
### <a name="parameters"></a>Parameter  
 *TYP*  
 Der Vorlagenparameter, den Typ der Elemente in der Liste angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Element, das am Ende der Liste wurde.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen sicherstellen, dass die Liste nicht leer ist, bevor der Aufruf von `RemoveTail`. Wenn die Liste leer ist, überprüft dann die Version der Microsoft Foundation Class-Bibliothek. Verwendung [IsEmpty](#isempty) zu überprüfen, ob die Liste Elemente enthält.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#54;](../../mfc/codesnippet/cpp/clist-class_20.cpp)]  
  
##  <a name="setat"></a>CList::SetAt  
 Eine Variable vom Typ **POSITION** ist ein Schlüssel für die Liste.  
  
```  
void SetAt(POSITION pos, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Die **POSITION** des Elements festgelegt werden.  
  
 `ARG_TYPE`  
 Vorlagenparameter, der den Typ des Listenelements angibt (kann ein Verweis sein).  
  
 `newElement`  
 Das Element der Liste hinzugefügt werden.  
  
### <a name="remarks"></a>Hinweise  
 Es ist nicht identisch mit einem Index, und Sie können nicht ausgeführt werden, auf eine **POSITION** Wert selbst. `SetAt`Schreibt das Element an der angegebenen Position in der Liste.  
  
 Sie müssen sicherstellen, dass Ihre **POSITION** Wert eine gültige Position in der Liste darstellt. Wenn sie ungültig ist, überprüft dann die Debugversion der Microsoft Foundation Class-Bibliothek.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCCollections&#55;](../../mfc/codesnippet/cpp/clist-class_21.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel COLLECT](../../visual-cpp-samples.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CMap-Klasse](../../mfc/reference/cmap-class.md)   
 [CArray-Klasse](../../mfc/reference/carray-class.md)

