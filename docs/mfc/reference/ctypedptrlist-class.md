---
title: CTypedPtrList-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 318373755ff05667d94b051dabf42822b34894b0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ctypedptrlist-class"></a>CTypedPtrList-Klasse
Stellt einen typsicheren Wrapper für Objekte der Klasse `CPtrList`bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class BASE_CLASS, class TYPE>  
class CTypedPtrList : public BASE_CLASS  
```  
  
#### <a name="parameters"></a>Parameter  
 `BASE_CLASS`  
 Die Basisklasse von typisierten Zeiger List-Klasse; muss eine Zeiger List-Klasse ( `CObList` oder `CPtrList`).  
  
 `TYPE`  
 Typ der Elemente in der Basisklassenliste gespeichert.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTypedPtrList::AddHead](#addhead)|Fügt ein Element (oder alle Elemente aus einer anderen Liste) an den Anfang der Liste (eines neuen kopfteils macht).|  
|[CTypedPtrList::AddTail](#addtail)|Fügt ein Element (oder alle Elemente aus einer anderen Liste) auf das Ende der Liste (werden einem neuen Ende).|  
|[CTypedPtrList::GetAt](#getat)|Ruft das Element an einer angegebenen Position ab.|  
|[CTypedPtrList::GetHead](#gethead)|Gibt das Head-Element der Liste (darf nicht leer sein).|  
|[CTypedPtrList::GetNext](#getnext)|Ruft das nächste Element für die Iteration an.|  
|[CTypedPtrList::GetPrev](#getprev)|Ruft das vorherige Element für die Iteration an.|  
|[CTypedPtrList::GetTail](#gettail)|Gibt das Element Ende der Liste (darf nicht leer sein).|  
|[CTypedPtrList::RemoveHead](#removehead)|Entfernt das Element am Anfang der Liste.|  
|[CTypedPtrList::RemoveTail](#removetail)|Entfernt das Element dem Ende der Liste aus.|  
|[CTypedPtrList::SetAt](#setat)|Legt das Element an einer bestimmten Position fest.|  
  
## <a name="remarks"></a>Hinweise  
 Bei Verwendung von `CTypedPtrList` statt `CObList` oder `CPtrList`, Typprüfung-Funktion für C++ hilft Fehler aufgrund nicht übereinstimmender Zeigertypen zu vermeiden.  
  
 Darüber hinaus die `CTypedPtrList` Wrapper führt ein Großteil der Umwandlung von Typen, die bei Verwendung erforderlich wäre `CObList` oder `CPtrList`.  
  
 Da alle `CTypedPtrList` Funktionen sind Inline, die Verwendung dieser Vorlage erheblich wirkt sich nicht die Größe oder Geschwindigkeit Ihres Codes.  
  
 Listen von abgeleiteten `CObList` serialisiert werden können, jedoch die abgeleitet `CPtrList` nicht möglich.  
  
 Wenn ein `CTypedPtrList`-Objekt gelöscht wird oder dessen Elemente entfernt werden, werden nur die Zeiger, und nicht die Entitäten, auf die sie verweisen, entfernt.  
  
 Weitere Informationen zur Verwendung von `CTypedPtrList`, finden Sie in den Artikeln [Sammlungen](../../mfc/collections.md) und [Template-basierten Klassen](../../mfc/template-based-classes.md).  
  
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
  
##  <a name="addhead"></a>CTypedPtrList::AddHead  
 Diese Memberfunktion ruft `BASE_CLASS` **:: AddHead**.  
  
```  
POSITION AddHead(TYPE newElement);  
void AddHead(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```  
  
### <a name="parameters"></a>Parameter  
 *DATENTYP*  
 Typ der Elemente in der Basisklassenliste gespeichert.  
  
 `newElement`  
 Die Objektzeiger zu dieser Liste hinzugefügt werden. Ein **NULL** Wert ist zulässig.  
  
 `BASE_CLASS`  
 Die Basisklasse von typisierten Zeiger List-Klasse; muss eine Zeiger List-Klasse ( [CObList](../../mfc/reference/coblist-class.md) oder [CPtrList](../../mfc/reference/cptrlist-class.md)).  
  
 `pNewList`  
 Ein Zeiger auf eine andere [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) Objekt. Die Elemente in `pNewList` wird zu dieser Liste hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die erste Version der **POSITION** Wert des neu eingefügten Element.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Version fügt vor den Anfang der Liste ein neues Element hinzu. Die zweite Version fügt Elemente vor den Anfang einer anderen Liste.  
  
##  <a name="addtail"></a>CTypedPtrList::AddTail  
 Diese Memberfunktion ruft `BASE_CLASS` **:: AddTail**.  
  
```  
POSITION AddTail(TYPE newElement);  
void AddTail(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```  
  
### <a name="parameters"></a>Parameter  
 *DATENTYP*  
 Typ der Elemente in der Basisklassenliste gespeichert.  
  
 `newElement`  
 Die Objektzeiger zu dieser Liste hinzugefügt werden. Ein **NULL** Wert ist zulässig.  
  
 `BASE_CLASS`  
 Die Basisklasse von typisierten Zeiger List-Klasse; muss eine Zeiger List-Klasse ( [CObList](../../mfc/reference/coblist-class.md) oder [CPtrList](../../mfc/reference/cptrlist-class.md)).  
  
 `pNewList`  
 Ein Zeiger auf eine andere [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) Objekt. Die Elemente in `pNewList` wird zu dieser Liste hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die erste Version der **POSITION** Wert des neu eingefügten Element.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Version Fügt ein neues Element nach dem Ende der Liste hinzu. Die zweite Version Fügt eine andere Liste von Elementen nach dem Ende der Liste hinzu.  
  
##  <a name="getat"></a>CTypedPtrList::GetAt  
 Eine Variable vom Typ **POSITION** ist ein Schlüssel für die Liste.  
  
```  
TYPE& GetAt(POSITION position);  
TYPE GetAt(POSITION position) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *DATENTYP*  
 Der Vorlagenparameter Angabe des Typs der Elemente in der Liste gespeichert.  
  
 *Position*  
 Ein **POSITION** von einem vorherigen zurückgegebene Wert `GetHeadPosition` oder **suchen** Member-Funktionsaufruf.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Zugriff auf die Liste durch einen Zeiger auf eine **const CTypedPtrList**, klicken Sie dann `GetAt` gibt einen Zeiger des Typs mit dem Vorlagenparameter angegebene *Typ*. Dies kann die Funktion nur auf der rechten Seite einer zuweisungsanweisung verwendet werden, und schützt folglich aus die Liste.  
  
 Wenn die Liste zugegriffen wird, direkt oder über einen Zeiger auf eine `CTypedPtrList`, klicken Sie dann `GetAt` gibt einen Verweis auf einen Zeiger des Typs mit dem Vorlagenparameter angegebene *Typ*. Dadurch können die Funktion, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und somit Einträge in der Liste geändert werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Es ist nicht identisch mit einem Index, und Sie können nicht ausgeführt werden, auf eine **POSITION** Wert selbst. `GetAt`Ruft die `CObject` Zeiger, die einer bestimmten Position zugeordnet.  
  
 Sie müssen sicherstellen, dass Ihre **POSITION** Wert stellt eine gültige Position in der Liste dar. Wenn er ungültig ist, bestätigt Sie dann die Debugversion von der Microsoft Foundation Class-Bibliothek.  
  
 Diese Inlinefunktion ruft `BASE_CLASS` **:: GetAt**.  
  
##  <a name="gethead"></a>CTypedPtrList::GetHead  
 Ruft den Zeiger, der das Anfangselement dieser Liste darstellt.  
  
```  
TYPE& GetHead();  
TYPE GetHead() const;  
```  
  
### <a name="parameters"></a>Parameter  
 *DATENTYP*  
 Der Vorlagenparameter Angabe des Typs der Elemente in der Liste gespeichert.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Zugriff auf die Liste durch einen Zeiger auf eine **const CTypedPtrList**, klicken Sie dann `GetHead` gibt einen Zeiger des Typs mit dem Vorlagenparameter angegebene *Typ*. Dies kann die Funktion nur auf der rechten Seite einer zuweisungsanweisung verwendet werden, und schützt folglich aus die Liste.  
  
 Wenn die Liste zugegriffen wird, direkt oder über einen Zeiger auf eine `CTypedPtrList`, klicken Sie dann `GetHead` gibt einen Verweis auf einen Zeiger des Typs mit dem Vorlagenparameter angegebene *Typ*. Dadurch können die Funktion, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und somit Einträge in der Liste geändert werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen sicherstellen, dass die Liste nicht leer ist, bevor der Aufruf ist `GetHead`. Wenn die Liste leer ist, bestätigt Sie dann die Debugversion von der Microsoft Foundation Class-Bibliothek. Verwendung [IsEmpty](../../mfc/reference/coblist-class.md#isempty) um sicherzustellen, dass die Liste Elemente enthält.  
  
##  <a name="getnext"></a>CTypedPtrList::GetNext  
 Ruft das Listenelement identifizierten `rPosition`, legt dann `rPosition` auf die **POSITION** Wert, der den nächsten Eintrag in der Liste.  
  
```  
TYPE& GetNext(POSITION& rPosition);  
TYPE GetNext(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *DATENTYP*  
 Der Vorlagenparameter Angabe des Typs der Elemente in dieser Liste enthalten sind.  
  
 `rPosition`  
 Ein Verweis auf eine **POSITION** von einem vorherigen zurückgegebene Wert `GetNext`, `GetHeadPosition`, oder andere Member-Funktionsaufruf.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Zugriff auf die Liste durch einen Zeiger auf eine **const CTypedPtrList**, klicken Sie dann `GetNext` gibt einen Zeiger des Typs mit dem Vorlagenparameter angegebene *Typ*. Dies kann die Funktion nur auf der rechten Seite einer zuweisungsanweisung verwendet werden, und schützt folglich aus die Liste.  
  
 Wenn die Liste zugegriffen wird, direkt oder über einen Zeiger auf eine `CTypedPtrList`, klicken Sie dann `GetNext` gibt einen Verweis auf einen Zeiger des Typs mit dem Vorlagenparameter angegebene *Typ*. Dadurch können die Funktion, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und somit Einträge in der Liste geändert werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Sie können `GetNext` in einer Schleife vorwärts, wenn Sie die erste Position mit einem Aufruf von einrichten `GetHeadPosition` oder [CPtrList::Find](../../mfc/reference/coblist-class.md#find).  
  
 Sie müssen sicherstellen, dass Ihre **POSITION** Wert stellt eine gültige Position in der Liste dar. Wenn er ungültig ist, bestätigt Sie dann die Debugversion von der Microsoft Foundation Class-Bibliothek.  
  
 Wenn das abgerufene Element das letzte Element in der Liste klicken Sie dann der neue Wert des `rPosition` festgelegt ist, um **NULL**.  
  
 Es ist möglich, ein Element innerhalb einer Iteration zu entfernen. Siehe das Beispiel für [CObList::RemoveAt](../../mfc/reference/coblist-class.md#removeat).  
  
##  <a name="getprev"></a>CTypedPtrList::GetPrev  
 Ruft das Listenelement identifizierten `rPosition`, dann legt `rPosition` auf die **POSITION** Wert des vorherigen Eintrags in der Liste.  
  
```  
TYPE& GetPrev(POSITION& rPosition);  
TYPE GetPrev(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *DATENTYP*  
 Der Vorlagenparameter Angabe des Typs der Elemente in dieser Liste enthalten sind.  
  
 `rPosition`  
 Ein Verweis auf eine **POSITION** von einem vorherigen zurückgegebene Wert `GetPrev` oder andere Member-Funktionsaufruf.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Zugriff auf die Liste durch einen Zeiger auf eine **const CTypedPtrList**, klicken Sie dann `GetPrev` gibt einen Zeiger des Typs mit dem Vorlagenparameter angegebene *Typ*. Dies kann die Funktion nur auf der rechten Seite einer zuweisungsanweisung verwendet werden, und schützt folglich aus die Liste.  
  
 Wenn die Liste zugegriffen wird, direkt oder über einen Zeiger auf eine `CTypedPtrList`, klicken Sie dann `GetPrev` gibt einen Verweis auf einen Zeiger des Typs mit dem Vorlagenparameter angegebene *Typ*. Dadurch können die Funktion, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und somit Einträge in der Liste geändert werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Sie können `GetPrev` in einer Schleife umgekehrte Iteration, wenn Sie die erste Position mit einem Aufruf von einrichten `GetTailPosition` oder **suchen**.  
  
 Sie müssen sicherstellen, dass Ihre **POSITION** Wert stellt eine gültige Position in der Liste dar. Wenn er ungültig ist, bestätigt Sie dann die Debugversion von der Microsoft Foundation Class-Bibliothek.  
  
 Wenn das abgerufene Element die erste Aufgabe in der Liste aus, klicken Sie dann der neue Wert des `rPosition` festgelegt ist, um **NULL**.  
  
##  <a name="gettail"></a>CTypedPtrList::GetTail  
 Ruft den Zeiger, der das Anfangselement dieser Liste darstellt.  
  
```  
TYPE& GetTail();  
TYPE GetTail() const;  
```  
  
### <a name="parameters"></a>Parameter  
 *DATENTYP*  
 Der Vorlagenparameter Angabe des Typs der Elemente in der Liste gespeichert.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Zugriff auf die Liste durch einen Zeiger auf eine **const CTypedPtrList**, klicken Sie dann `GetTail` gibt einen Zeiger des Typs mit dem Vorlagenparameter angegebene *Typ*. Dies kann die Funktion nur auf der rechten Seite einer zuweisungsanweisung verwendet werden, und schützt folglich aus die Liste.  
  
 Wenn die Liste zugegriffen wird, direkt oder über einen Zeiger auf eine `CTypedPtrList`, klicken Sie dann `GetTail` gibt einen Verweis auf einen Zeiger des Typs mit dem Vorlagenparameter angegebene *Typ*. Dadurch können die Funktion, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und somit Einträge in der Liste geändert werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen sicherstellen, dass die Liste nicht leer ist, bevor der Aufruf ist `GetTail`. Wenn die Liste leer ist, bestätigt Sie dann die Debugversion von der Microsoft Foundation Class-Bibliothek. Verwendung [IsEmpty](../../mfc/reference/coblist-class.md#isempty) um sicherzustellen, dass die Liste Elemente enthält.  
  
##  <a name="removehead"></a>CTypedPtrList::RemoveHead  
 Entfernt das Element am Anfang der Liste aus, und gibt es zurück.  
  
```  
TYPE RemoveHead();
```  
  
### <a name="parameters"></a>Parameter  
 *DATENTYP*  
 Der Vorlagenparameter Angabe des Typs der Elemente in der Liste gespeichert.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Zeiger bereits am Anfang der Liste. This-Zeiger entspricht dem Typ, der mit dem Vorlagenparameter angegebene *Typ*.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen sicherstellen, dass die Liste nicht leer ist, bevor der Aufruf ist `RemoveHead`. Wenn die Liste leer ist, bestätigt Sie dann die Debugversion von der Microsoft Foundation Class-Bibliothek. Verwendung [IsEmpty](../../mfc/reference/coblist-class.md#isempty) um sicherzustellen, dass die Liste Elemente enthält.  
  
##  <a name="removetail"></a>CTypedPtrList::RemoveTail  
 Entfernt das Element, das Ende der Liste aus, und gibt es zurück.  
  
```  
TYPE RemoveTail();
```  
  
### <a name="parameters"></a>Parameter  
 *DATENTYP*  
 Der Vorlagenparameter Angabe des Typs der Elemente in der Liste gespeichert.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Zeiger zuvor am Ende der Liste. This-Zeiger entspricht dem Typ, der mit dem Vorlagenparameter angegebene *Typ*.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen sicherstellen, dass die Liste nicht leer ist, bevor der Aufruf ist `RemoveTail`. Wenn die Liste leer ist, bestätigt Sie dann die Debugversion von der Microsoft Foundation Class-Bibliothek. Verwendung [IsEmpty](../../mfc/reference/coblist-class.md#isempty) um sicherzustellen, dass die Liste Elemente enthält.  
  
##  <a name="setat"></a>CTypedPtrList::SetAt  
 Diese Memberfunktion ruft `BASE_CLASS` **:: SetAt**.  
  
```  
void SetAt(POSITION pos, TYPE newElement);
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Die **POSITION** des Elements festgelegt werden.  
  
 *DATENTYP*  
 Typ der Elemente in der Basisklassenliste gespeichert.  
  
 `newElement`  
 Der Zeiger in der Liste geschrieben werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Eine Variable vom Typ **POSITION** ist ein Schlüssel für die Liste. Es ist nicht identisch mit einem Index, und Sie können nicht ausgeführt werden, auf eine **POSITION** Wert selbst. `SetAt`Schreibt die Objektzeiger an der angegebenen Position in der Liste an.  
  
 Sie müssen sicherstellen, dass Ihre **POSITION** Wert stellt eine gültige Position in der Liste dar. Wenn er ungültig ist, bestätigt Sie dann die Debugversion von der Microsoft Foundation Class-Bibliothek.  
  
 Ausführlichere Hinweise finden Sie unter [CObList::SetAt](../../mfc/reference/coblist-class.md#setat).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel erfassen](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CPtrList-Klasse](../../mfc/reference/cptrlist-class.md)   
 [CObList-Klasse](../../mfc/reference/coblist-class.md)
