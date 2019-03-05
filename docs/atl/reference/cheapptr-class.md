---
title: CHeapPtr-Klasse
ms.date: 11/04/2016
f1_keywords:
- CHeapPtr
- ATLCORE/ATL::CHeapPtr
- ATLCORE/ATL::CHeapPtr::CHeapPtr
- ATLCORE/ATL::CHeapPtr::Allocate
- ATLCORE/ATL::CHeapPtr::Reallocate
helpviewer_keywords:
- CHeapPtr class
ms.assetid: e5c5bfd4-9bf1-4164-8a83-8155fe253454
ms.openlocfilehash: 8cb35139e707d81a53edb762a2b7fc2ab41ff247
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57296058"
---
# <a name="cheapptr-class"></a>CHeapPtr-Klasse

Eine intelligente Zeiger-Klasse für die Verwaltung von Heap-Zeiger.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template<typename T, class Allocator=CCRTAllocator>
class CHeapPtr : public CHeapPtrBase<T, Allocator>
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Objekttyp, auf dem Heap gespeichert werden.

*Allocator*<br/>
Die Speicher-Allocation-Klasse verwenden.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CHeapPtr::CHeapPtr](#cheapptr)|Der Konstruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CHeapPtr::Allocate](#allocate)|Rufen Sie diese Methode, um die speicherbelegung auf dem Heap, Objekte zu speichern.|
|[CHeapPtr::Reallocate](#reallocate)|Rufen Sie diese Methode, um den Arbeitsspeicher auf dem Heap neu zuzuordnen.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CHeapPtr::operator =](#operator_eq)|Der Zuweisungsoperator.|

## <a name="remarks"></a>Hinweise

`CHeapPtr` stammt aus [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) und verwendet Sie standardmäßig die CRT-Routinen (in [CCRTAllocator](../../atl/reference/ccrtallocator-class.md)) zum Zuordnen und Freigeben von Arbeitsspeicher. Die Klasse [CHeapPtrList](../../atl/reference/cheapptrlist-class.md) kann verwendet werden, um eine Liste von Heap Zeigern zu erstellen. Siehe auch [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), die COM-Arbeitsspeicher speicherbelegungsroutinen verwendet.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)

`CHeapPtr`

## <a name="requirements"></a>Anforderungen

**Header:** atlcore.h

##  <a name="allocate"></a>  CHeapPtr::Allocate

Rufen Sie diese Methode, um die speicherbelegung auf dem Heap, Objekte zu speichern.

```
bool Allocate(size_t nElements = 1) throw();
```

### <a name="parameters"></a>Parameter

*nElements*<br/>
Die Anzahl der Elemente, die zum Berechnen der Menge an Arbeitsspeicher zugeordnet werden soll. Der Standardwert ist 1.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn der Speicher wurde erfolgreich zugeordnet, "false" bei einem Fehler.

### <a name="remarks"></a>Hinweise

Die Allocator-Routinen dienen, reservieren ausreichend Arbeitsspeicher auf dem Heap zum Speichern von *nElement* Objekte eines Typs, die im Konstruktor definiert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#77](../../atl/codesnippet/cpp/cheapptr-class_1.cpp)]

##  <a name="cheapptr"></a>  CHeapPtr::CHeapPtr

Der Konstruktor.

```
CHeapPtr() throw();
explicit CHeapPtr(T* p) throw();
CHeapPtr(CHeapPtr<T, Allocator>& p) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
Einem vorhandenen Heapzeiger oder `CHeapPtr`.

### <a name="remarks"></a>Hinweise

Der Heapzeiger kann optional mithilfe eines bestehenden Zeigers, erstellt werden oder ein `CHeapPtr` Objekt. Wenn dies der Fall ist, die neue `CHeapPtr` Objekt übernimmt die Verantwortung für die Verwaltung der neue Zeiger und Ressourcen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#78](../../atl/codesnippet/cpp/cheapptr-class_2.cpp)]

##  <a name="operator_eq"></a>  CHeapPtr::operator =

Zuweisungsoperator.

```
CHeapPtr<T, Allocator>& operator=(
    CHeapPtr<T, Allocator>& p) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
Ein vorhandenes `CHeapPtr`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt einen Verweis auf die aktualisierte `CHeapPtr`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#80](../../atl/codesnippet/cpp/cheapptr-class_3.cpp)]

##  <a name="reallocate"></a>  CHeapPtr::Reallocate

Rufen Sie diese Methode, um den Arbeitsspeicher auf dem Heap neu zuzuordnen.

```
bool Reallocate(size_t nElements) throw();
```

### <a name="parameters"></a>Parameter

*nElements*<br/>
Die neue Anzahl von Elementen, die zum Berechnen der Menge an Arbeitsspeicher zugeordnet werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn der Speicher wurde erfolgreich zugeordnet, "false" bei einem Fehler.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#79](../../atl/codesnippet/cpp/cheapptr-class_4.cpp)]

## <a name="see-also"></a>Siehe auch

[CHeapPtrBase-Klasse](../../atl/reference/cheapptrbase-class.md)<br/>
[CCRTAllocator-Klasse](../../atl/reference/ccrtallocator-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
