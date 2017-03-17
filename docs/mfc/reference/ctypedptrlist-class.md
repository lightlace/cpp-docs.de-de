---
title: CTypedPtrList-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
- CTypedPtrList class
- type-safe collections
- lists [C++]
- template classes, CTypedPtrList class
- linked lists [C++]
- pointer lists
ms.assetid: c273096e-1756-4340-864b-4a08b674a65e
caps.latest.revision: 24
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
ms.openlocfilehash: ca8d868333aa977710e387fc1bb13271dc8f99fa
ms.lasthandoff: 02/24/2017

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
 Die Basisklasse der typisierten Zeigers List-Klasse; muss eine Zeiger List-Klasse ( `CObList` oder `CPtrList`).  
  
 `TYPE`  
 Der Typ der Elemente in der Liste der Basisklassen gespeichert.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTypedPtrList::AddHead](#addhead)|Fügt ein Element (oder alle Elemente in einer anderen Liste) an den Anfang der Liste (wird eine neue Head).|  
|[CTypedPtrList::AddTail](#addtail)|Fügt ein Element (oder alle Elemente in einer anderen Liste) an das Ende der Liste (wird eine neue Erweiterung).|  
|[CTypedPtrList::GetAt](#getat)|Ruft das Element an einer angegebenen Position ab.|  
|[CTypedPtrList::GetHead](#gethead)|Gibt das Head-Element der Liste (darf nicht leer sein).|  
|[CTypedPtrList::GetNext](#getnext)|Ruft das nächste Element durchlaufen werden können.|  
|[CTypedPtrList::GetPrev](#getprev)|Ruft das vorherige Element durchlaufen werden können.|  
|[CTypedPtrList::GetTail](#gettail)|Gibt das Ende der Liste (darf nicht leer sein) zurück.|  
|[CTypedPtrList::RemoveHead](#removehead)|Entfernt das Element am Anfang der Liste.|  
|[CTypedPtrList::RemoveTail](#removetail)|Entfernt das Element dem Ende der Liste aus.|  
|[CTypedPtrList::SetAt](#setat)|Legt das Element an einer bestimmten Position fest.|  
  
## <a name="remarks"></a>Hinweise  
 Bei Verwendung `CTypedPtrList` statt `CObList` oder `CPtrList`, die C++-Typprüfung-Funktion hilft Fehler aufgrund eines nicht übereinstimmenden Zeigertypen zu vermeiden.  
  
 Darüber hinaus die `CTypedPtrList` Wrapper führt ein Großteil der Umwandlung von Typen, die erforderlich sein würde, wenn Sie verwendet `CObList` oder `CPtrList`.  
  
 Da alle `CTypedPtrList` Funktionen sind Inline, die Verwendung dieser Vorlage erheblich wirkt sich nicht die Größe oder Geschwindigkeit Ihres Codes.  
  
 Listen von abgeleiteten `CObList` serialisiert werden kann, aber die von abgeleiteten `CPtrList` nicht möglich.  
  
 Wenn ein `CTypedPtrList`-Objekt gelöscht wird oder dessen Elemente entfernt werden, werden nur die Zeiger, und nicht die Entitäten, auf die sie verweisen, entfernt.  
  
 Weitere Informationen zur Verwendung von `CTypedPtrList`, finden Sie in den Artikeln [Sammlungen](../../mfc/collections.md) und [Vorlagen basierende Klassen](../../mfc/template-based-classes.md).  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel erstellt eine Instanz des `CTypedPtrList`, fügt ein Objekt, serialisiert die Liste auf den Datenträger und löscht dann das Objekt:  
  
 [!code-cpp[NVC_MFCCollections&#110;](../../mfc/codesnippet/cpp/ctypedptrlist-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCCollections&#111;](../../mfc/codesnippet/cpp/ctypedptrlist-class_2.cpp)]  
  
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
 *TYP*  
 Der Typ der Elemente in der Liste der Basisklassen gespeichert.  
  
 `newElement`  
 Der Zeiger des Objekts zu dieser Liste hinzugefügt werden. Ein **NULL** Wert zulässig ist.  
  
 `BASE_CLASS`  
 Die Basisklasse der typisierten Zeigers List-Klasse; muss eine Zeiger List-Klasse ( [CObList](../../mfc/reference/coblist-class.md) oder [CPtrList](../../mfc/reference/cptrlist-class.md)).  
  
 `pNewList`  
 Ein Zeiger auf einen anderen [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) Objekt. Die Elemente in `pNewList` wird zu dieser Liste hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die erste Version der **POSITION** Wert des neu eingefügten Element.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Version fügt vor den Anfang der Liste ein neues Element hinzu. Die zweite Version Fügt eine andere Liste von Elementen vor dem.  
  
##  <a name="addtail"></a>CTypedPtrList::AddTail  
 Diese Memberfunktion ruft `BASE_CLASS` **:: AddTail**.  
  
```  
POSITION AddTail(TYPE newElement);  
void AddTail(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```  
  
### <a name="parameters"></a>Parameter  
 *TYP*  
 Der Typ der Elemente in der Liste der Basisklassen gespeichert.  
  
 `newElement`  
 Der Zeiger des Objekts zu dieser Liste hinzugefügt werden. Ein **NULL** Wert zulässig ist.  
  
 `BASE_CLASS`  
 Die Basisklasse der typisierten Zeigers List-Klasse; muss eine Zeiger List-Klasse ( [CObList](../../mfc/reference/coblist-class.md) oder [CPtrList](../../mfc/reference/cptrlist-class.md)).  
  
 `pNewList`  
 Ein Zeiger auf einen anderen [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) Objekt. Die Elemente in `pNewList` wird zu dieser Liste hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die erste Version der **POSITION** Wert des neu eingefügten Element.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Version fügt nach dem Ende der Liste ein neues Element hinzu. Die zweite Version Fügt eine andere Liste von Elementen nach dem Ende der Liste hinzu.  
  
##  <a name="getat"></a>CTypedPtrList::GetAt  
 Eine Variable vom Typ **POSITION** ist ein Schlüssel für die Liste.  
  
```  
TYPE& GetAt(POSITION position);  
TYPE GetAt(POSITION position) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *TYP*  
 Der Vorlagenparameter, die den Typ der Elemente in der Liste gespeichert.  
  
 *Position*  
 Ein **POSITION** von einem vorherigen zurückgegebene Wert `GetHeadPosition` oder **suchen** Member-Funktionsaufruf.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Zugriff auf die Liste durch einen Zeiger auf eine **const CTypedPtrList**, dann `GetAt` gibt einen Zeiger des Typs mit dem Vorlagenparameter angegebenen *Typ*. Dies kann die Funktion nur auf der rechten Seite einer zuweisungsanweisung verwendet werden, und schützt folglich aus die Liste.  
  
 Wenn die Liste zugegriffen wird, direkt oder über einen Zeiger auf eine `CTypedPtrList`, dann `GetAt` gibt einen Verweis auf einen Zeiger des Typs mit dem Vorlagenparameter angegebenen *Typ*. Dadurch können die Funktion, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und daher Einträge in der Liste geändert werden.  
  
### <a name="remarks"></a>Hinweise  
 Es ist nicht identisch mit einem Index, und Sie können nicht ausgeführt werden, auf eine **POSITION** Wert selbst. `GetAt`Ruft die `CObject` Zeiger, die einer bestimmten Position zugeordnet.  
  
 Sie müssen sicherstellen, dass Ihre **POSITION** Wert eine gültige Position in der Liste darstellt. Wenn sie ungültig ist, überprüft dann die Debugversion der Microsoft Foundation Class-Bibliothek.  
  
 Diese Inline-Funktionsaufrufe `BASE_CLASS` **:: GetAt**.  
  
##  <a name="gethead"></a>CTypedPtrList::GetHead  
 Ruft die Zeiger, der das Head-Element der Liste darstellt.  
  
```  
TYPE& GetHead();  
TYPE GetHead() const;  
```  
  
### <a name="parameters"></a>Parameter  
 *TYP*  
 Der Vorlagenparameter, die den Typ der Elemente in der Liste gespeichert.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Zugriff auf die Liste durch einen Zeiger auf eine **const CTypedPtrList**, dann `GetHead` gibt einen Zeiger des Typs mit dem Vorlagenparameter angegebenen *Typ*. Dies kann die Funktion nur auf der rechten Seite einer zuweisungsanweisung verwendet werden, und schützt folglich aus die Liste.  
  
 Wenn die Liste zugegriffen wird, direkt oder über einen Zeiger auf eine `CTypedPtrList`, dann `GetHead` gibt einen Verweis auf einen Zeiger des Typs mit dem Vorlagenparameter angegebenen *Typ*. Dadurch können die Funktion, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und daher Einträge in der Liste geändert werden.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen sicherstellen, dass die Liste nicht leer ist, bevor der Aufruf von `GetHead`. Wenn die Liste leer ist, überprüft dann die Version der Microsoft Foundation Class-Bibliothek. Verwendung [IsEmpty](../../mfc/reference/coblist-class.md#isempty) zu überprüfen, ob die Liste Elemente enthält.  
  
##  <a name="getnext"></a>CTypedPtrList::GetNext  
 Ruft das Listenelement identifizierten `rPosition`, dann wird `rPosition` an der **POSITION** Wert des nächsten Eintrag in der Liste.  
  
```  
TYPE& GetNext(POSITION& rPosition);  
TYPE GetNext(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *TYP*  
 Der Vorlagenparameter, die den Typ der Elemente in dieser Liste enthalten sind.  
  
 `rPosition`  
 Ein Verweis auf eine **POSITION** von einem vorherigen zurückgegebene Wert `GetNext`, `GetHeadPosition`, oder andere Member-Funktionsaufruf.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Zugriff auf die Liste durch einen Zeiger auf eine **const CTypedPtrList**, dann `GetNext` gibt einen Zeiger des Typs mit dem Vorlagenparameter angegebenen *Typ*. Dies kann die Funktion nur auf der rechten Seite einer zuweisungsanweisung verwendet werden, und schützt folglich aus die Liste.  
  
 Wenn die Liste zugegriffen wird, direkt oder über einen Zeiger auf eine `CTypedPtrList`, dann `GetNext` gibt einen Verweis auf einen Zeiger des Typs mit dem Vorlagenparameter angegebenen *Typ*. Dadurch können die Funktion, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und daher Einträge in der Liste geändert werden.  
  
### <a name="remarks"></a>Hinweise  
 Sie können `GetNext` in einer Iterationsschleife forward, wenn Sie die ursprüngliche Position mit einem Aufruf von einrichten `GetHeadPosition` oder [CPtrList::Find](../../mfc/reference/coblist-class.md#find).  
  
 Sie müssen sicherstellen, dass Ihre **POSITION** Wert eine gültige Position in der Liste darstellt. Wenn sie ungültig ist, überprüft dann die Debugversion der Microsoft Foundation Class-Bibliothek.  
  
 Wenn das abgerufene Element das letzte Element in der Liste der neue Wert des ist `rPosition` Wert **NULL**.  
  
 Es ist möglich, ein Element während einer Iteration zu entfernen. Siehe das Beispiel für [CObList::RemoveAt](../../mfc/reference/coblist-class.md#removeat).  
  
##  <a name="getprev"></a>CTypedPtrList::GetPrev  
 Ruft das Listenelement identifizierten `rPosition`, dann wird `rPosition` an der **POSITION** Wert des vorherigen Eintrags in der Liste.  
  
```  
TYPE& GetPrev(POSITION& rPosition);  
TYPE GetPrev(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *TYP*  
 Der Vorlagenparameter, die den Typ der Elemente in dieser Liste enthalten sind.  
  
 `rPosition`  
 Ein Verweis auf eine **POSITION** von einem vorherigen zurückgegebene Wert `GetPrev` oder anderer Member-Funktionsaufruf.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Zugriff auf die Liste durch einen Zeiger auf eine **const CTypedPtrList**, dann `GetPrev` gibt einen Zeiger des Typs mit dem Vorlagenparameter angegebenen *Typ*. Dies kann die Funktion nur auf der rechten Seite einer zuweisungsanweisung verwendet werden, und schützt folglich aus die Liste.  
  
 Wenn die Liste zugegriffen wird, direkt oder über einen Zeiger auf eine `CTypedPtrList`, dann `GetPrev` gibt einen Verweis auf einen Zeiger des Typs mit dem Vorlagenparameter angegebenen *Typ*. Dadurch können die Funktion, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und daher Einträge in der Liste geändert werden.  
  
### <a name="remarks"></a>Hinweise  
 Sie können `GetPrev` in einer Schleife umgekehrte Iteration, wenn Sie die ursprüngliche Position mit einem Aufruf von einrichten `GetTailPosition` oder **suchen**.  
  
 Sie müssen sicherstellen, dass Ihre **POSITION** Wert eine gültige Position in der Liste darstellt. Wenn sie ungültig ist, überprüft dann die Debugversion der Microsoft Foundation Class-Bibliothek.  
  
 Wenn das abgerufene Element der erste in der Liste dann den neuen Wert der `rPosition` Wert **NULL**.  
  
##  <a name="gettail"></a>CTypedPtrList::GetTail  
 Ruft die Zeiger, der das Head-Element der Liste darstellt.  
  
```  
TYPE& GetTail();  
TYPE GetTail() const;  
```  
  
### <a name="parameters"></a>Parameter  
 *TYP*  
 Der Vorlagenparameter, die den Typ der Elemente in der Liste gespeichert.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Zugriff auf die Liste durch einen Zeiger auf eine **const CTypedPtrList**, dann `GetTail` gibt einen Zeiger des Typs mit dem Vorlagenparameter angegebenen *Typ*. Dies kann die Funktion nur auf der rechten Seite einer zuweisungsanweisung verwendet werden, und schützt folglich aus die Liste.  
  
 Wenn die Liste zugegriffen wird, direkt oder über einen Zeiger auf eine `CTypedPtrList`, dann `GetTail` gibt einen Verweis auf einen Zeiger des Typs mit dem Vorlagenparameter angegebenen *Typ*. Dadurch können die Funktion, die auf beiden Seiten einer zuweisungsanweisung verwendet werden und daher Einträge in der Liste geändert werden.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen sicherstellen, dass die Liste nicht leer ist, bevor der Aufruf von `GetTail`. Wenn die Liste leer ist, überprüft dann die Version der Microsoft Foundation Class-Bibliothek. Verwendung [IsEmpty](../../mfc/reference/coblist-class.md#isempty) zu überprüfen, ob die Liste Elemente enthält.  
  
##  <a name="removehead"></a>CTypedPtrList::RemoveHead  
 Entfernt das Element am Anfang der Liste, und gibt es zurück.  
  
```  
TYPE RemoveHead();
```  
  
### <a name="parameters"></a>Parameter  
 *TYP*  
 Der Vorlagenparameter, die den Typ der Elemente in der Liste gespeichert.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Zeiger bereits am Anfang der Liste. Dieser Zeiger ist vom Typ vom Vorlagenparameter angegeben *Typ*.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen sicherstellen, dass die Liste nicht leer ist, bevor der Aufruf von `RemoveHead`. Wenn die Liste leer ist, überprüft dann die Version der Microsoft Foundation Class-Bibliothek. Verwendung [IsEmpty](../../mfc/reference/coblist-class.md#isempty) zu überprüfen, ob die Liste Elemente enthält.  
  
##  <a name="removetail"></a>CTypedPtrList::RemoveTail  
 Entfernt das Element, das Ende der Liste aus, und gibt es zurück.  
  
```  
TYPE RemoveTail();
```  
  
### <a name="parameters"></a>Parameter  
 *TYP*  
 Der Vorlagenparameter, die den Typ der Elemente in der Liste gespeichert.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Zeiger bereits am Ende der Liste. Dieser Zeiger ist vom Typ vom Vorlagenparameter angegeben *Typ*.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen sicherstellen, dass die Liste nicht leer ist, bevor der Aufruf von `RemoveTail`. Wenn die Liste leer ist, überprüft dann die Version der Microsoft Foundation Class-Bibliothek. Verwendung [IsEmpty](../../mfc/reference/coblist-class.md#isempty) zu überprüfen, ob die Liste Elemente enthält.  
  
##  <a name="setat"></a>CTypedPtrList::SetAt  
 Diese Memberfunktion ruft `BASE_CLASS` **:: SetAt**.  
  
```  
void SetAt(POSITION pos, TYPE newElement);
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Die **POSITION** des Elements festgelegt werden.  
  
 *TYP*  
 Der Typ der Elemente in der Liste der Basisklassen gespeichert.  
  
 `newElement`  
 Der Zeiger des Objekts in der Liste geschrieben werden.  
  
### <a name="remarks"></a>Hinweise  
 Eine Variable vom Typ **POSITION** ist ein Schlüssel für die Liste. Es ist nicht identisch mit einem Index, und Sie können nicht ausgeführt werden, auf eine **POSITION** Wert selbst. `SetAt`Schreibt den Zeiger auf die angegebene Position in der Liste.  
  
 Sie müssen sicherstellen, dass Ihre **POSITION** Wert eine gültige Position in der Liste darstellt. Wenn sie ungültig ist, überprüft dann die Debugversion der Microsoft Foundation Class-Bibliothek.  
  
 Weitere Hinweise finden Sie unter [CObList::SetAt](../../mfc/reference/coblist-class.md#setat).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel COLLECT](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CPtrList-Klasse](../../mfc/reference/cptrlist-class.md)   
 [CObList-Klasse](../../mfc/reference/coblist-class.md)

