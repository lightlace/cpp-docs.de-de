---
title: CTypedPtrArray-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTypedPtrArray
- AFXTEMPL/CTypedPtrArray
- AFXTEMPL/CTypedPtrArray::Add
- AFXTEMPL/CTypedPtrArray::Append
- AFXTEMPL/CTypedPtrArray::Copy
- AFXTEMPL/CTypedPtrArray::ElementAt
- AFXTEMPL/CTypedPtrArray::GetAt
- AFXTEMPL/CTypedPtrArray::InsertAt
- AFXTEMPL/CTypedPtrArray::SetAt
- AFXTEMPL/CTypedPtrArray::SetAtGrow
dev_langs:
- C++
helpviewer_keywords:
- pointer arrays
- CTypedPtrArray class
ms.assetid: e3ecdf1a-a889-4156-92dd-ddbd36ccd919
caps.latest.revision: 22
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
ms.openlocfilehash: 24b21d017d46cc88d7e243aff75ccf6383d2c870
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="ctypedptrarray-class"></a>CTypedPtrArray-Klasse
Stellt einen typsicheren Wrapper für Objekte der Klasse `CPtrArray` oder `CObArray`bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class BASE_CLASS, class TYPE>  
class CTypedPtrArray : public BASE_CLASS  
```  
  
#### <a name="parameters"></a>Parameter  
 `BASE_CLASS`  
 Die Basisklasse der typisierten Zeigers Array-Klasse; eine Array-Klasse ( `CObArray` oder `CPtrArray`).  
  
 `TYPE`  
 Der Typ der Elemente im Array Basisklasse gespeichert.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTypedPtrArray::Add](#add)|Fügt ein neues Element am Ende eines Arrays. Vergrößert das Array bei Bedarf|  
|[CTypedPtrArray::Append](#append)|Fügt den Inhalt eines Arrays an das Ende eines anderen. Vergrößert das Array bei Bedarf|  
|[CTypedPtrArray::Copy](#copy)|Kopiert ein anderes Array in das Array; vergrößert das Array bei Bedarf.|  
|[CTypedPtrArray::ElementAt](#elementat)|Gibt einen temporären Verweis auf den Elementzeiger innerhalb des Arrays zurück.|  
|[CTypedPtrArray::GetAt](#getat)|Gibt den Wert an einem bestimmten Index zurück.|  
|[CTypedPtrArray::InsertAt](#insertat)|Fügt ein Element (oder alle Elemente in einem anderen Array) am angegebenen Index ein.|  
|[CTypedPtrArray::SetAt](#setat)|Legt den Wert für einen bestimmten Index fest; Array darf nicht vergrößert werden.|  
|[CTypedPtrArray::SetAtGrow](#setatgrow)|Legt den Wert für einen bestimmten Index fest; vergrößert das Array bei Bedarf.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTypedPtrArray::operator]](#operator_at)|Legt das Element am angegebenen Index fest oder ruft es ab.|  
  
## <a name="remarks"></a>Hinweise  
 Bei Verwendung `CTypedPtrArray` statt `CPtrArray` oder `CObArray`, die C++-Typprüfung-Funktion hilft Fehler aufgrund eines nicht übereinstimmenden Zeigertypen zu vermeiden.  
  
 Darüber hinaus die `CTypedPtrArray` Wrapper führt ein Großteil der Umwandlung von Typen, die erforderlich sein würde, wenn Sie verwendet `CObArray` oder `CPtrArray`.  
  
 Da alle `CTypedPtrArray` Funktionen sind Inline, die Verwendung dieser Vorlage erheblich wirkt sich nicht die Größe oder Geschwindigkeit Ihres Codes.  
  
 Weitere Informationen zur Verwendung von `CTypedPtrArray`, finden Sie in den Artikeln [Sammlungen](../../mfc/collections.md) und [Vorlagen basierende Klassen](../../mfc/template-based-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `BASE_CLASS`  
  
 `CTypedPtrArray`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtempl.h  
  
##  <a name="add"></a>CTypedPtrArray::Add  
 Diese Memberfunktion ruft `BASE_CLASS` **:: Hinzufügen**.  
  
```  
INT_PTR Add(TYPE newElement);
```  
  
### <a name="parameters"></a>Parameter  
 *TYP*  
 Der Vorlagenparameter, die den Typ des Elements, das dem Array hinzugefügt werden.  
  
 `newElement`  
 Das Element, das in diesem Array hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des hinzugefügten Elements.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Hinweise finden Sie unter [CObArray::Add](../../mfc/reference/cobarray-class.md#add).  
  
##  <a name="append"></a>CTypedPtrArray::Append  
 Diese Memberfunktion ruft `BASE_CLASS` **:: Append**.  
  
```  
INT_PTR Append(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```  
  
### <a name="parameters"></a>Parameter  
 `BASE_CLASS`  
 Die Basisklasse der typisierten Zeigers Array-Klasse; eine Array-Klasse ( [CObArray](../../mfc/reference/cobarray-class.md) oder [CPtrArray](../../mfc/reference/cptrarray-class.md)).  
  
 *TYP*  
 Der Typ der Elemente im Array Basisklasse gespeichert.  
  
 *src*  
 Die Quelle der Elemente, die einem Array hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des ersten Elements angefügt.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Hinweise finden Sie unter [CObArray::Append](../../mfc/reference/cobarray-class.md#append).  
  
##  <a name="copy"></a>CTypedPtrArray::Copy  
 Diese Memberfunktion ruft `BASE_CLASS` **:: Copy**.  
  
```  
void Copy(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```  
  
### <a name="parameters"></a>Parameter  
 `BASE_CLASS`  
 Die Basisklasse der typisierten Zeigers Array-Klasse; eine Array-Klasse ( [CObArray](../../mfc/reference/cobarray-class.md) oder [CPtrArray](../../mfc/reference/cptrarray-class.md)).  
  
 *TYP*  
 Der Typ der Elemente im Array Basisklasse gespeichert.  
  
 *src*  
 Die Quelle der Elemente, die in ein Array kopiert werden.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Hinweise finden Sie unter [CObArray::Copy](../../mfc/reference/cobarray-class.md#copy).  
  
##  <a name="elementat"></a>CTypedPtrArray::ElementAt  
 Diese Inline-Funktionsaufrufe `BASE_CLASS` **:: ElementAt**.  
  
```  
TYPE& ElementAt(INT_PTR nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 *TYP*  
 Der Vorlagenparameter, die den Typ der Elemente im Array gespeichert.  
  
 `nIndex`  
 Eine ganzzahlige Index, der größer als oder gleich 0 und kleiner oder gleich der von zurückgegebene Wert `BASE_CLASS` **:: GetUpperBound**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einen temporären Verweis auf das Element am angegebenen Speicherort `nIndex`. Dieses Element ist vom Typ vom Vorlagenparameter angegeben *Typ*.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Hinweise finden Sie unter [CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat).  
  
##  <a name="getat"></a>CTypedPtrArray::GetAt  
 Diese Inline-Funktionsaufrufe `BASE_CLASS` **:: GetAt**.  
  
```  
TYPE GetAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *TYP*  
 Der Vorlagenparameter, die den Typ der Elemente im Array gespeichert.  
  
 `nIndex`  
 Eine ganzzahlige Index, der größer als oder gleich 0 und kleiner oder gleich der von zurückgegebene Wert `BASE_CLASS` **:: GetUpperBound**.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kopie des Elements am angegebenen Speicherort `nIndex`. Dieses Element ist vom Typ vom Vorlagenparameter angegeben *Typ*.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Hinweise finden Sie unter [CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)  
  
##  <a name="insertat"></a>CTypedPtrArray::InsertAt  
 Diese Memberfunktion ruft `BASE_CLASS` **:: InsertAt**.  
  
```  
void InsertAt(
    INT_PTR nIndex,  
    TYPE newElement,  
    INT_PTR nCount = 1);

 
void InsertAt(
    INT_PTR nStartIndex,  
    CTypedPtrArray<BASE_CLASS, TYPE>* pNewArray);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Eine ganzzahlige Index, der größer als der zurückgegebene Wert möglicherweise [CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound).  
  
 *TYP*  
 Der Typ der Elemente im Array Basisklasse gespeichert.  
  
 `newElement`  
 Der Zeiger des Objekts in diesem Array platziert werden. Ein `newElement` des Werts **NULL** ist zulässig.  
  
 `nCount`  
 Wie oft dieses Element liegen eingefügt (Standardwert: 1).  
  
 `nStartIndex`  
 Eine ganzzahlige Index, der größer als der zurückgegebene Wert möglicherweise `CObArray::GetUpperBound`.  
  
 `BASE_CLASS`  
 Die Basisklasse der typisierten Zeigers Array-Klasse; eine Array-Klasse ( [CObArray](../../mfc/reference/cobarray-class.md) oder [CPtrArray](../../mfc/reference/cptrarray-class.md)).  
  
 `pNewArray`  
 Ein anderes Array mit Elementen in diesem Array hinzugefügt werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Hinweise finden Sie unter [CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat).  
  
##  <a name="operator_at"></a>CTypedPtrArray::operator]  
 Diese Operatoren Inline Aufrufen `BASE_CLASS` **:: Operator []**.  
  
```  
TYPE& operator[ ](int_ptr nindex);  
TYPE operator[ ](int_ptr nindex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *TYP*  
 Der Vorlagenparameter, die den Typ der Elemente im Array gespeichert.  
  
 `nIndex`  
 Eine ganzzahlige Index, der größer als oder gleich 0 und kleiner oder gleich der von zurückgegebene Wert `BASE_CLASS` **:: GetUpperBound**.  
  
### <a name="remarks"></a>Hinweise  
 Der first-Operator für Arrays, bei denen aufgerufen **const**, kann rechts (r) und Links (l-Wert) einer zuweisungsanweisung verwendet werden. Für die zweite aufgerufen **const** Arrays, können nur auf der rechten Seite verwendet werden.  
  
 Die Debugversion der Bibliothek bestätigt, wenn der Index (entweder auf der linken oder rechten Seite einer zuweisungsanweisung) außerhalb des gültigen Bereichs ist.  
  
##  <a name="setat"></a>CTypedPtrArray::SetAt  
 Diese Memberfunktion ruft `BASE_CLASS` **:: SetAt**.  
  
```  
void SetAt(
    INT_PTR nIndex,  
    TYPE ptr);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Eine ganzzahlige Index, der größer als oder gleich 0 und kleiner oder gleich der von zurückgegebene Wert [CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound).  
  
 *TYP*  
 Der Typ der Elemente im Array Basisklasse gespeichert.  
  
 *PTR*  
 Ein Zeiger auf das Element im Array, an der nIndex eingefügt werden. Ein NULL-Wert ist zulässig.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Hinweise finden Sie unter [CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat).  
  
##  <a name="setatgrow"></a>CTypedPtrArray::SetAtGrow  
 Diese Memberfunktion ruft `BASE_CLASS` **:: SetAtGrow**.  
  
```  
void SetAtGrow(
    INT_PTR nIndex,  
    TYPE newElement);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Eine ganzzahlige Index, der größer als oder gleich 0 ist.  
  
 *TYP*  
 Der Typ der Elemente im Array Basisklasse gespeichert.  
  
 `newElement`  
 Der Zeiger dieses Array hinzugefügt werden. Ein **NULL** Wert zulässig ist.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Hinweise finden Sie unter [CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel COLLECT](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CPtrArray-Klasse](../../mfc/reference/cptrarray-class.md)   
 [CObArray-Klasse](../../mfc/reference/cobarray-class.md)

