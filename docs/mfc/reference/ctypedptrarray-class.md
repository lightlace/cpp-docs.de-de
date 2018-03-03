---
title: CTypedPtrArray-Klasse | Microsoft Docs
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
- CTypedPtrArray [MFC], Add
- CTypedPtrArray [MFC], Append
- CTypedPtrArray [MFC], Copy
- CTypedPtrArray [MFC], ElementAt
- CTypedPtrArray [MFC], GetAt
- CTypedPtrArray [MFC], InsertAt
- CTypedPtrArray [MFC], SetAt
- CTypedPtrArray [MFC], SetAtGrow
ms.assetid: e3ecdf1a-a889-4156-92dd-ddbd36ccd919
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6e08749341bd7865c89e397e36aeff3a6ccc0d71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
 Die Basisklasse der typisierten Zeiger Array-Klasse; muss eine Array-Klasse ( `CObArray` oder `CPtrArray`).  
  
 `TYPE`  
 Typ der Elemente in der Basisklasse Array gespeichert.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTypedPtrArray::Add](#add)|Fügt ein neues Element am Ende eines Arrays an. Vergrößert das Array bei Bedarf|  
|[CTypedPtrArray::Append](#append)|Fügt den Inhalt eines Arrays an das Ende einer anderen. Vergrößert das Array bei Bedarf|  
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
 Bei Verwendung von `CTypedPtrArray` statt `CPtrArray` oder `CObArray`, Typprüfung-Funktion für C++ hilft Fehler aufgrund nicht übereinstimmender Zeigertypen zu vermeiden.  
  
 Darüber hinaus die `CTypedPtrArray` Wrapper führt ein Großteil der Umwandlung von Typen, die bei Verwendung erforderlich wäre `CObArray` oder `CPtrArray`.  
  
 Da alle `CTypedPtrArray` Funktionen sind Inline, die Verwendung dieser Vorlage erheblich wirkt sich nicht die Größe oder Geschwindigkeit Ihres Codes.  
  
 Weitere Informationen zur Verwendung von `CTypedPtrArray`, finden Sie in den Artikeln [Sammlungen](../../mfc/collections.md) und [Template-basierten Klassen](../../mfc/template-based-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `BASE_CLASS`  
  
 `CTypedPtrArray`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtempl.h  
  
##  <a name="add"></a>CTypedPtrArray::Add  
 Diese Memberfunktion ruft `BASE_CLASS` **:: Add**.  
  
```  
INT_PTR Add(TYPE newElement);
```  
  
### <a name="parameters"></a>Parameter  
 *DATENTYP*  
 Der Vorlagenparameter Angabe des Typs des Elements des Arrays hinzugefügt werden.  
  
 `newElement`  
 Das Element mit diesem Array hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des hinzugefügten Elements.  
  
### <a name="remarks"></a>Hinweise  
 Ausführlichere Hinweise finden Sie unter [CObArray::Add](../../mfc/reference/cobarray-class.md#add).  
  
##  <a name="append"></a>CTypedPtrArray::Append  
 Diese Memberfunktion ruft `BASE_CLASS` **:: Append**.  
  
```  
INT_PTR Append(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```  
  
### <a name="parameters"></a>Parameter  
 `BASE_CLASS`  
 Die Basisklasse der typisierten Zeiger Array-Klasse; muss eine Array-Klasse ( [CObArray](../../mfc/reference/cobarray-class.md) oder [CPtrArray](../../mfc/reference/cptrarray-class.md)).  
  
 *DATENTYP*  
 Typ der Elemente in der Basisklasse Array gespeichert.  
  
 *src*  
 Die Quelle der Elemente, die ein Array angefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des ersten Elements angefügt.  
  
### <a name="remarks"></a>Hinweise  
 Ausführlichere Hinweise finden Sie unter [CObArray::Append](../../mfc/reference/cobarray-class.md#append).  
  
##  <a name="copy"></a>CTypedPtrArray::Copy  
 Diese Memberfunktion ruft `BASE_CLASS` **:: Copy**.  
  
```  
void Copy(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```  
  
### <a name="parameters"></a>Parameter  
 `BASE_CLASS`  
 Die Basisklasse der typisierten Zeiger Array-Klasse; muss eine Array-Klasse ( [CObArray](../../mfc/reference/cobarray-class.md) oder [CPtrArray](../../mfc/reference/cptrarray-class.md)).  
  
 *DATENTYP*  
 Typ der Elemente in der Basisklasse Array gespeichert.  
  
 *src*  
 Die Quelle der Elemente in ein Array kopiert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Ausführlichere Hinweise finden Sie unter [CObArray::Copy](../../mfc/reference/cobarray-class.md#copy).  
  
##  <a name="elementat"></a>CTypedPtrArray::ElementAt  
 Diese Inlinefunktion ruft `BASE_CLASS` **:: ElementAt**.  
  
```  
TYPE& ElementAt(INT_PTR nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 *DATENTYP*  
 Der Vorlagenparameter Angabe des Typs der Elemente im Array gespeichert.  
  
 `nIndex`  
 Eine ganzzahlige Index, der größer als oder gleich 0 ist und kleiner oder gleich den Rückgabewert von `BASE_CLASS` **:: GetUpperBound**.  
  
### <a name="return-value"></a>Rückgabewert  
 Einen temporären Verweis auf das Element an der vom angegebenen Position `nIndex`. Dieses Element ist vom Typ mit dem Vorlagenparameter angegebene *Typ*.  
  
### <a name="remarks"></a>Hinweise  
 Ausführlichere Hinweise finden Sie unter [CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat).  
  
##  <a name="getat"></a>CTypedPtrArray::GetAt  
 Diese Inlinefunktion ruft `BASE_CLASS` **:: GetAt**.  
  
```  
TYPE GetAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *DATENTYP*  
 Der Vorlagenparameter Angabe des Typs der Elemente im Array gespeichert.  
  
 `nIndex`  
 Eine ganzzahlige Index, der größer als oder gleich 0 ist und kleiner oder gleich den Rückgabewert von `BASE_CLASS` **:: GetUpperBound**.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kopie des Elements an der vom angegebenen Position `nIndex`. Dieses Element ist vom Typ mit dem Vorlagenparameter angegebene *Typ*.  
  
### <a name="remarks"></a>Hinweise  
 Ausführlichere Hinweise finden Sie unter [CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)  
  
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
 Eine ganzzahlige Index, die größer als der zurückgegebene Wert möglicherweise [CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound).  
  
 *DATENTYP*  
 Typ der Elemente in der Basisklasse Array gespeichert.  
  
 `newElement`  
 Der Zeiger in diesem Array platziert werden soll. Ein `newElement` des Werts **NULL** ist zulässig.  
  
 `nCount`  
 Die Anzahl der Häufigkeit, mit die dieses Element liegen eingefügt (Standardwert: 1).  
  
 `nStartIndex`  
 Eine ganzzahlige Index, die größer als der zurückgegebene Wert möglicherweise `CObArray::GetUpperBound`.  
  
 `BASE_CLASS`  
 Die Basisklasse der typisierten Zeiger Array-Klasse; muss eine Array-Klasse ( [CObArray](../../mfc/reference/cobarray-class.md) oder [CPtrArray](../../mfc/reference/cptrarray-class.md)).  
  
 `pNewArray`  
 Ein anderes Array mit Elementen mit diesem Array hinzugefügt werden.  
  
### <a name="remarks"></a>Hinweise  
 Ausführlichere Hinweise finden Sie unter [CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat).  
  
##  <a name="operator_at"></a>CTypedPtrArray::operator]  
 Diese Operatoren Inline Aufrufen `BASE_CLASS` **:: Operator []**.  
  
```  
TYPE& operator[ ](int_ptr nindex);  
TYPE operator[ ](int_ptr nindex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *DATENTYP*  
 Der Vorlagenparameter Angabe des Typs der Elemente im Array gespeichert.  
  
 `nIndex`  
 Eine ganzzahlige Index, der größer als oder gleich 0 ist und kleiner oder gleich den Rückgabewert von `BASE_CLASS` **:: GetUpperBound**.  
  
### <a name="remarks"></a>Hinweise  
 Der erste Operator aufgerufen für Arrays, die nicht **const**, auf der rechten Seite (r) oder linken (l-Wert) einer zuweisungsanweisung verwendet werden können. Die zweite für aufgerufene **const** Arrays können nur auf der rechten Seite verwendet werden.  
  
 Die Debugversion der Bibliothek wird bestätigt, wenn der Index (entweder auf der linken oder rechten Seite einer zuweisungsanweisung) außerhalb des gültigen Bereichs ist.  
  
##  <a name="setat"></a>CTypedPtrArray::SetAt  
 Diese Memberfunktion ruft `BASE_CLASS` **:: SetAt**.  
  
```  
void SetAt(
    INT_PTR nIndex,  
    TYPE ptr);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Eine ganzzahlige Index, der größer als oder gleich 0 ist und kleiner oder gleich den Rückgabewert von [CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound).  
  
 *DATENTYP*  
 Typ der Elemente in der Basisklasse Array gespeichert.  
  
 *ptr*  
 Ein Zeiger auf das Element im Array, ab der nIndex eingefügt werden. Es ist ein NULL-Wert zulässig.  
  
### <a name="remarks"></a>Hinweise  
 Ausführlichere Hinweise finden Sie unter [CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat).  
  
##  <a name="setatgrow"></a>CTypedPtrArray::SetAtGrow  
 Diese Memberfunktion ruft `BASE_CLASS` **:: SetAtGrow**.  
  
```  
void SetAtGrow(
    INT_PTR nIndex,  
    TYPE newElement);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Ein Integer-Index, der größer als oder gleich 0 ist.  
  
 *DATENTYP*  
 Typ der Elemente in der Basisklasse Array gespeichert.  
  
 `newElement`  
 Die Objektzeiger dieses Array hinzugefügt werden. Ein **NULL** Wert ist zulässig.  
  
### <a name="remarks"></a>Hinweise  
 Ausführlichere Hinweise finden Sie unter [CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel erfassen](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CPtrArray-Klasse](../../mfc/reference/cptrarray-class.md)   
 [CObArray-Klasse](../../mfc/reference/cobarray-class.md)
