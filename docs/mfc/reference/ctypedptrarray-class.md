---
title: CTypedPtrArray-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8f8cb8da3eaae08eeb694deaad6c3f4f6a71e7dc
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50054983"
---
# <a name="ctypedptrarray-class"></a>CTypedPtrArray-Klasse

Stellt einen typsicheren Wrapper für Objekte der Klasse `CPtrArray` oder `CObArray`bereit.

## <a name="syntax"></a>Syntax

```
template<class BASE_CLASS, class TYPE>
class CTypedPtrArray : public BASE_CLASS
```

#### <a name="parameters"></a>Parameter

*BASE_CLASS*<br/>
Die Basisklasse der typisierter Zeiger Array-Klasse; muss eine Array-Klasse ( `CObArray` oder `CPtrArray`).

*TYPE*<br/>
Der Typ der Elemente in der Basisklasse-Array gespeichert.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CTypedPtrArray::Add](#add)|Fügt ein neues Element am Ende eines Arrays an. Vergrößert das Array bei Bedarf|
|[CTypedPtrArray::Append](#append)|Fügt den Inhalt eines Arrays am Ende eines anderen hinzu. Vergrößert das Array bei Bedarf|
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

Bei Verwendung von `CTypedPtrArray` statt `CPtrArray` oder `CObArray`, die Typprüfung C++-Funktion hilft, Fehler aufgrund nicht übereinstimmender Zeigertypen zu vermeiden.

Darüber hinaus die `CTypedPtrArray` Wrapper Großteil der Umwandlung, die erforderlich sein würde, wenn Sie verwendet haben, führt `CObArray` oder `CPtrArray`.

Da alle `CTypedPtrArray` Funktionen werden Inline, die Verwendung dieser Vorlage erheblich wirkt sich nicht die Größe oder Geschwindigkeit Ihres Codes.

Weitere Informationen zur Verwendung von `CTypedPtrArray`, finden Sie in den Artikeln [Sammlungen](../../mfc/collections.md) und [vorlagenbasierte Klassen](../../mfc/template-based-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`BASE_CLASS`

`CTypedPtrArray`

## <a name="requirements"></a>Anforderungen

**Header:** afxtempl.h

##  <a name="add"></a>  CTypedPtrArray::Add

Diese Memberfunktion ruft `BASE_CLASS` **:: Add**.

```
INT_PTR Add(TYPE newElement);
```

### <a name="parameters"></a>Parameter

*TYPE*<br/>
Der Vorlagenparameter, die den Typ des Elements, das dem Array hinzugefügt werden.

*newElement*<br/>
Das Element, das in diesem Array hinzugefügt werden.

### <a name="return-value"></a>Rückgabewert

Der Index des hinzugefügten Elements.

### <a name="remarks"></a>Hinweise

Weitere Hinweise finden Sie unter [CObArray::Add](../../mfc/reference/cobarray-class.md#add).

##  <a name="append"></a>  CTypedPtrArray::Append

Diese Memberfunktion ruft `BASE_CLASS`:: Append **.

```
INT_PTR Append(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```

### <a name="parameters"></a>Parameter

*BASE_CLASS*<br/>
Die Basisklasse der typisierter Zeiger Array-Klasse; muss eine Array-Klasse ( [CObArray](../../mfc/reference/cobarray-class.md) oder [CPtrArray](../../mfc/reference/cptrarray-class.md)).

*TYPE*<br/>
Der Typ der Elemente in der Basisklasse-Array gespeichert.

*src*<br/>
Die Quelle der Elemente, die ein Array angefügt werden soll.

### <a name="return-value"></a>Rückgabewert

Der Index des ersten Elements angefügt werden soll.

### <a name="remarks"></a>Hinweise

Weitere Hinweise finden Sie unter [CObArray::Append](../../mfc/reference/cobarray-class.md#append).

##  <a name="copy"></a>  CTypedPtrArray::Copy

Diese Memberfunktion ruft `BASE_CLASS` **:: Copy**.

```
void Copy(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```

### <a name="parameters"></a>Parameter

*BASE_CLASS*<br/>
Die Basisklasse der typisierter Zeiger Array-Klasse; muss eine Array-Klasse ( [CObArray](../../mfc/reference/cobarray-class.md) oder [CPtrArray](../../mfc/reference/cptrarray-class.md)).

*TYPE*<br/>
Der Typ der Elemente in der Basisklasse-Array gespeichert.

*src*<br/>
Die Quelle der Elemente in ein Array kopiert werden sollen.

### <a name="remarks"></a>Hinweise

Weitere Hinweise finden Sie unter [CObArray::Copy](../../mfc/reference/cobarray-class.md#copy).

##  <a name="elementat"></a>  CTypedPtrArray::ElementAt

Diese Inlinefunktion ruft `BASE_CLASS` **:: ElementAt**.

```
TYPE& ElementAt(INT_PTR nIndex);
```

### <a name="parameters"></a>Parameter

*TYPE*<br/>
Der Vorlagenparameter, die den Typ der Elemente im Array gespeichert.

*nIndex*<br/>
Eine ganzzahlige Index, der größer als oder gleich 0 und kleiner als oder gleich den Rückgabewert von `BASE_CLASS` **:: GetUpperBound**.

### <a name="return-value"></a>Rückgabewert

Einen temporären Verweis auf das Element an der vom angegebenen Speicherort *nIndex*. Dieses Element hat den Typ mit dem Vorlagenparameter angegebene *Typ*.

### <a name="remarks"></a>Hinweise

Weitere Hinweise finden Sie unter [CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat).

##  <a name="getat"></a>  CTypedPtrArray::GetAt

Diese Inlinefunktion ruft `BASE_CLASS` **:: GetAt**.

```
TYPE GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Parameter

*TYPE*<br/>
Der Vorlagenparameter, der den Typ der Elemente im Array gespeicherten angibt.

*nIndex*<br/>
Eine ganzzahlige Index, der größer als oder gleich 0 und kleiner als oder gleich den Rückgabewert von `BASE_CLASS` **:: GetUpperBound**.

### <a name="return-value"></a>Rückgabewert

Eine Kopie des Elements an der vom angegebenen Speicherort *nIndex*. Dieses Element hat den Typ mit dem Vorlagenparameter angegebene *Typ*.

### <a name="remarks"></a>Hinweise

Weitere Hinweise finden Sie unter [CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)

##  <a name="insertat"></a>  CTypedPtrArray::InsertAt

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

*nIndex*<br/>
Eine ganzzahlige Index, die größer als der von zurückgegebene Wert möglicherweise [CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound).

*TYPE*<br/>
Der Typ der Elemente in der Basisklasse-Array gespeichert.

*newElement*<br/>
Der Objektzeiger in diesem Array platziert werden. Ein *NewElement* Werts **NULL** ist zulässig.

*nCount*<br/>
Die Anzahl der Male, die dieses Element eingefügt (Standardwert: 1).

*nStartIndex*<br/>
Eine ganzzahlige Index, die größer als der von zurückgegebene Wert möglicherweise `CObArray::GetUpperBound`.

*BASE_CLASS*<br/>
Die Basisklasse der typisierter Zeiger Array-Klasse; muss eine Array-Klasse ( [CObArray](../../mfc/reference/cobarray-class.md) oder [CPtrArray](../../mfc/reference/cptrarray-class.md)).

*pNewArray*<br/>
Ein anderes Array mit Elementen in diesem Array hinzugefügt werden sollen.

### <a name="remarks"></a>Hinweise

Weitere Hinweise finden Sie unter [CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat).

##  <a name="operator_at"></a>  CTypedPtrArray::operator]

Diese Operatoren Inline Aufrufen `BASE_CLASS` **:: Operator []**.

```
TYPE& operator[ ](int_ptr nindex);
TYPE operator[ ](int_ptr nindex) const;
```

### <a name="parameters"></a>Parameter

*TYPE*<br/>
Der Vorlagenparameter, der den Typ der Elemente im Array gespeicherten angibt.

*nIndex*<br/>
Eine ganzzahlige Index, der größer als oder gleich 0 und kleiner als oder gleich den Rückgabewert von `BASE_CLASS` **:: GetUpperBound**.

### <a name="remarks"></a>Hinweise

Der erste Operator aufgerufen wird, für Arrays, die nicht **const**, kann entweder auf der rechten Seite (r) oder auf der linken Seite (l-Wert) einer zuweisungsanweisung verwendet werden. Das zweite für aufgerufen **const** Arrays kann nur auf der rechten Seite verwendet werden.

Die Debugversion der Bibliothek wird bestätigt, den der Feldindex (entweder auf der linken oder rechten Seite einer zuweisungsanweisung) liegt außerhalb des gültigen Bereichs.

##  <a name="setat"></a>  CTypedPtrArray::SetAt

Diese Memberfunktion ruft `BASE_CLASS` **:: SetAt**.

```
void SetAt(
    INT_PTR nIndex,
    TYPE ptr);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Eine ganzzahlige Index, der größer als oder gleich 0 und kleiner als oder gleich den Rückgabewert von [CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound).

*TYPE*<br/>
Der Typ der Elemente in der Basisklasse-Array gespeichert.

*ptr*<br/>
Ein Zeiger auf das Element im Array, an die nIndex eingefügt werden. Es ist ein NULL-Wert zulässig.

### <a name="remarks"></a>Hinweise

Weitere Hinweise finden Sie unter [CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat).

##  <a name="setatgrow"></a>  CTypedPtrArray::SetAtGrow

Diese Memberfunktion ruft `BASE_CLASS` **:: SetAtGrow**.

```
void SetAtGrow(
    INT_PTR nIndex,
    TYPE newElement);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Eine ganze Zahl-Index, der größer als oder gleich 0 ist.

*TYPE*<br/>
Der Typ der Elemente in der Basisklasse-Array gespeichert.

*newElement*<br/>
Der Objektzeiger, die diesem Array hinzugefügt werden. Ein **NULL** Wert ist zulässig.

### <a name="remarks"></a>Hinweise

Weitere Hinweise finden Sie unter [CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow).

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel erfassen](../../visual-cpp-samples.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CPtrArray-Klasse](../../mfc/reference/cptrarray-class.md)<br/>
[CObArray-Klasse](../../mfc/reference/cobarray-class.md)
