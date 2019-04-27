---
title: CSimpleArray-Klasse
ms.date: 11/04/2016
f1_keywords:
- CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray::CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray::Add
- ATLSIMPCOLL/ATL::CSimpleArray::Find
- ATLSIMPCOLL/ATL::CSimpleArray::GetData
- ATLSIMPCOLL/ATL::CSimpleArray::GetSize
- ATLSIMPCOLL/ATL::CSimpleArray::Remove
- ATLSIMPCOLL/ATL::CSimpleArray::RemoveAll
- ATLSIMPCOLL/ATL::CSimpleArray::RemoveAt
- ATLSIMPCOLL/ATL::CSimpleArray::SetAtIndex
helpviewer_keywords:
- CSimpleArray class
ms.assetid: ee0c9f39-b61c-4c18-bc43-4eada21dca3a
ms.openlocfilehash: 8c050002549fc6b7a18acb34f0e4f9a2f278db82
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62278006"
---
# <a name="csimplearray-class"></a>CSimpleArray-Klasse

Diese Klasse stellt Methoden zum Verwalten von einem einfachen Array an.

## <a name="syntax"></a>Syntax

```
template <class T, class TEqual = CSimpleArrayEqualHelper<T>>
class CSimpleArray
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ der Daten, die im Array gespeichert.

*TEqual*<br/>
Ein Merkmal-Objekt, und definieren den Gleichheitstest auf für Elemente des Typs *T*.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CSimpleArray::CSimpleArray](#csimplearray)|Der Konstruktor für den einfachen Array.|
|[CSimpleArray::~CSimpleArray](#dtor)|Der Destruktor für das einfache Array.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSimpleArray::Add](#add)|Fügt ein neues Element in das Array an.|
|[CSimpleArray::Find](#find)|Sucht ein Element im Array.|
|[CSimpleArray::GetData](#getdata)|Gibt einen Zeiger auf die Daten im Array gespeichert.|
|[CSimpleArray::GetSize](#getsize)|Gibt die Anzahl der Elemente im Array gespeichert.|
|[CSimpleArray::Remove](#remove)|Entfernt ein angegebenes Element aus dem Array.|
|[CSimpleArray::RemoveAll](#removeall)|Entfernt alle Elemente aus dem Array.|
|[CSimpleArray::RemoveAt](#removeat)|Entfernt das angegebene Element aus dem Array.|
|[CSimpleArray::SetAtIndex](#setatindex)|Legt das angegebene Element im Array fest.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CSimpleArray::operator\[\]](#operator_at)|Ruft ein Element aus dem Array ab.|
|[CSimpleArray::operator =](#operator_eq)|Zuweisungsoperator.|

## <a name="remarks"></a>Hinweise

`CSimpleArray` Stellt Methoden zum Erstellen und Verwalten von einem einfachen Array, eines Typs `T`.

Der Parameter `TEqual` bietet eine Möglichkeit zum Definieren einer Gleichheitsfunktion auf für zwei Elemente des Typs `T`. Durch Erstellen einer Klasse ähnelt [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md), es ist möglich, die das Verhalten des Tests auf Gleichheit für alle angegebenen Arrays zu ändern. Beispielsweise kann beim Umgang mit der ein Array von Zeigern es hilfreich sein, abhängig von den Werten auf Gleichheit als zu definieren, die Zeiger für das Verweisen auf. Die Standardimplementierung verwendet **operator=()**.

Beide `CSimpleArray` und [CSimpleMap](../../atl/reference/csimplemap-class.md) sind für eine kleine Anzahl von Elementen konzipiert. [CAtlArray](../../atl/reference/catlarray-class.md) und [CAtlMap](../../atl/reference/catlmap-class.md) sollte verwendet werden, wenn das Array eine große Anzahl von Elementen enthält.

## <a name="requirements"></a>Anforderungen

**Header:** atlsimpcoll.h

## <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#86](../../atl/codesnippet/cpp/csimplearray-class_1.cpp)]

##  <a name="add"></a>  CSimpleArray::Add

Fügt ein neues Element in das Array an.

```
BOOL Add(const T& t);
```

### <a name="parameters"></a>Parameter

*t*<br/>
Das Element, das dem Array hinzugefügt.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn das Element erfolgreich andernfalls in das Array, "false" hinzugefügt wurde.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#87](../../atl/codesnippet/cpp/csimplearray-class_2.cpp)]

##  <a name="csimplearray"></a>  CSimpleArray::CSimpleArray

Der Konstruktor für das Array-Objekt.

```
CSimpleArray(const CSimpleArray<T, TEqual>& src);
CSimpleArray();
```

### <a name="parameters"></a>Parameter

*src*<br/>
Ein vorhandenes `CSimpleArray`-Objekt.

### <a name="remarks"></a>Hinweise

Initialisiert die Datenmember, erstellen ein neues leeres `CSimpleArray` Objekt oder eine Kopie eines vorhandenen `CSimpleArray` Objekt.

##  <a name="dtor"></a>  CSimpleArray:: ~ CSimpleArray

Der Destruktor.

```
~CSimpleArray();
```

### <a name="remarks"></a>Hinweise

Gibt alle zugeordnete Ressourcen frei.

##  <a name="find"></a>  CSimpleArray::Find

Sucht ein Element im Array.

```
int Find(const T& t) const;
```

### <a name="parameters"></a>Parameter

*t*<br/>
Das Element nach dem gesucht werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt den Index des gefundenen Elements oder -1 zurück, wenn das Element nicht gefunden wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#88](../../atl/codesnippet/cpp/csimplearray-class_3.cpp)]

##  <a name="getdata"></a>  CSimpleArray::GetData

Gibt einen Zeiger auf die Daten im Array gespeichert.

```
T* GetData() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die Daten im Array zurück.

##  <a name="getsize"></a>  CSimpleArray::GetSize

Gibt die Anzahl der Elemente im Array gespeichert.

```
int GetSize() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der Elemente im Array gespeichert.

##  <a name="operator_at"></a>  CSimpleArray::operator \[\]

Ruft ein Element aus dem Array ab.

```
T& operator[](int nindex);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Elementindex.

### <a name="return-value"></a>Rückgabewert

Gibt das Element des Arrays verwiesen *nIndex*.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#89](../../atl/codesnippet/cpp/csimplearray-class_4.cpp)]

##  <a name="operator_eq"></a>  CSimpleArray::operator =

Zuweisungsoperator.

```
CSimpleArray<T, TEqual>
& operator=(
    const CSimpleArray<T, TEqual>& src);
```

### <a name="parameters"></a>Parameter

*src*<br/>
Das Array, das kopiert werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die aktualisierte `CSimpleArray` Objekt.

### <a name="remarks"></a>Hinweise

Kopiert alle Elemente aus der `CSimpleArray` Objekt, auf *Src* in das aktuelle Arrayobjekt, und Ersetzen Sie dabei alle vorhandene Daten.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#90](../../atl/codesnippet/cpp/csimplearray-class_5.cpp)]

##  <a name="remove"></a>  CSimpleArray::Remove

Entfernt ein angegebenes Element aus dem Array.

```
BOOL Remove(const T& t);
```

### <a name="parameters"></a>Parameter

*t*<br/>
Das Element, aus dem Array entfernt.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn das Element gefunden und entfernt, andernfalls FALSE ist.

### <a name="remarks"></a>Hinweise

Wenn ein Element entfernt wird, werden die übrigen Elemente im Array neu nummeriert, um Lücken zu füllen.

##  <a name="removeall"></a>  CSimpleArray::RemoveAll

Entfernt alle Elemente aus dem Array.

```
void RemoveAll();
```

### <a name="remarks"></a>Hinweise

Entfernt alle Elemente, die derzeit im Array gespeichert.

##  <a name="removeat"></a>  CSimpleArray::RemoveAt

Entfernt das angegebene Element aus dem Array.

```
BOOL RemoveAtint nIndex);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Indizieren Sie die zu entfernenden Elements auf.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn das Element wurde entfernt, FALSE, wenn der Index ungültig war.

### <a name="remarks"></a>Hinweise

Wenn ein Element entfernt wird, werden die übrigen Elemente im Array neu nummeriert, um Lücken zu füllen.

##  <a name="setatindex"></a>  CSimpleArray::SetAtIndex

Legen Sie das angegebene Element im Array.

```
BOOL SetAtIndex(
    int nIndex,
    const T& t);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index des Elements zu ändern.

*t*<br/>
Der dem angegebenen Element zuzuweisende Wert.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn erfolgreich, FALSE, wenn der Index ungültig war.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
