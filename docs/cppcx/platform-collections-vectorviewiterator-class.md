---
title: Platform::Collections::VectorViewIterator-Klasse
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorViewIterator::VectorViewIterator
helpviewer_keywords:
- VectorViewIterator Class
ms.assetid: be3aa1ae-e6ba-4a06-8d6b-86d8128026f7
ms.openlocfilehash: 0de4ffb8e72c21490f07ae164aa23ffcd524c2b8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62161406"
---
# <a name="platformcollectionsvectorviewiterator-class"></a>Platform::Collections::VectorViewIterator-Klasse

Stellt einen standardvorlagenbibliotheksiterator für die Windows-Runtime abgeleitete Objekte`IVectorView` Schnittstelle.

`ViewVectorIterator` ist ein Proxyiterator, der Elemente des Typs `VectorProxy<T>`speichert. Allerdings ist das Proxyobjekt fast nie für Benutzercode sichtbar. Weitere Informationen finden Sie unter [Auflistungen (C++/CX)](../cppcx/collections-c-cx.md).

## <a name="syntax"></a>Syntax

```
template <typename T>
class VectorViewIterator;
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Typname der VectorViewIterator-Vorlagenklasse.

### <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`difference_type`|Ein Zeigerunterschied (ptrdiff_t).|
|`iterator_category`|Die Kategorie eines direkten Iterators (::std::random_access_iterator_tag).|
|`pointer`|Ein Zeiger auf einen internen Typ, der für die Implementierung von VectorViewIterator erforderlich ist.|
|`reference`|Ein Verweis auf einen internen Typ, der für die Implementierung von VectorViewIterator erforderlich ist.|
|`value_type`|Der `T` -Typname.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[VectorViewIterator::VectorViewIterator](#ctor)|Initialisiert eine neue Instanz der VectorViewIterator-Klasse.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[VectorViewIterator::operator[]-Operator](#operator-minus)|Subtrahiert entweder eine angegebene Anzahl von Elementen vom aktuellen Iterator und bildet einen neuen Iterator, oder subtrahiert einen angegebenen Iterator vom aktuellen Iterator, und gibt die Anzahl von Elementen zwischen den Iteratoren zurück.|
|[VectorViewIterator::operator[]-Operator](#operator-decrement)|Dekrementiert den aktuellen VectorViewIterator.|
|[VectorViewIterator::operator!=-Operator](#operator-inequality)|Gibt an, ob der aktuelle VectorViewIterator ungleich einem angegebenen VectorViewIterator ist.|
|[VectorViewIterator::operator[]-Operator](#operator-dereference)|Ruft einen Verweis auf das Element ab, das vom aktuellen VectorViewIterator angegeben wird.|
|[VectorViewIterator::operator\[\]](#operator-at)|Ruft einen Verweis auf das Element ab, das eine angegebene Verschiebung vom aktuellen VectorViewIterator ist.|
|[VectorViewIterator::operator+-Operator](#operator-plus)|Gibt einen VectorViewIterator zurück, der auf das Element an der angegebenen Verschiebung von dem angegebenen VectorViewIterator verweist.|
|[VectorViewIterator::operator++-Operator](#operator-increment)|Inkrementiert den aktuellen VectorViewIterator.|
|[VectorViewIterator::operator+=-Operator](#operator-plus-equals)|Inkrementiert den aktuellen VectorViewIterator um die angegebene Verschiebung.|
|[VectorViewIterator::operator<-Operator](#operator-less-than)|Gibt an, ob der aktuelle VectorViewIterator kleiner einem angegebenen VectorViewIterator ist.|
|[Vectorviewiterator::\<Operator =-Operator](#operator-less-than-or-equals)|Gibt an, ob der aktuelle VectorViewIterator kleiner oder gleich einem angegebenen VectorViewIterator ist.|
|[VectorViewIterator::operator-=-Operator](#operator-minus-assign)|Dekrementiert den aktuellen VectorViewIterator durch die angegebene Verschiebung.|
|[VectorViewIterator::operator==-Operator](#operator-equality)|Gibt an, ob der aktuelle VectorViewIterator gleich einem angegebenen VectorViewIterator ist.|
|[VectorViewIterator::operator>-Operator](#operator-greater-than)|Gibt an, ob der aktuelle VectorViewIterator größer einem angegebenen VectorViewIterator ist.|
|[VectorViewIterator::operator->-Operator](#operator-arrow)|Ruft die Adresse des Elements ab, auf das vom aktuellen VectorViewIterator verwiesen wird.|
|[VectorViewIterator::operator>=-Operator](#operator-greater-than-or-equals)|Gibt an, ob der aktuelle VectorViewIterator größer oder gleich einem angegebenen VectorViewIterator ist.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`VectorViewIterator`

### <a name="requirements"></a>Anforderungen

**Header:** collection.h

**Namespace:** Platform::Collections

## <a name="operator-arrow"></a>  Vectorviewiterator:: -&gt; Operator

Ruft die Adresse des Elements ab, auf das vom aktuellen VectorViewIterator verwiesen wird.

### <a name="syntax"></a>Syntax

```
Detail::ArrowProxy<T> operator->() const;
```

### <a name="return-value"></a>Rückgabewert

Der Wert des Elements, auf das vom aktuellen VectorViewIterator verwiesen wird.

Der Typ des Rückgabewerts ist ein nicht angegebener interner Typ, der für die Implementierung dieses Operators erforderlich ist.

## <a name="operator-decrement"></a>  Vectorviewiterator:: – Operator

Dekrementiert den aktuellen VectorViewIterator.

### <a name="syntax"></a>Syntax

```
VectorViewIterator& operator--();
VectorViewIterator operator--(int);
```

### <a name="return-value"></a>Rückgabewert

Die erste Syntax dekrementiert den aktuellen VectorViewIterator und gibt ihn dann zurück. Die zweite Syntax gibt eine Kopie des aktuellen VectorViewIterator zurück und dekrementiert dann den aktuellen VectorViewIterator.

### <a name="remarks"></a>Hinweise

In der ersten VectorViewIterator-Syntax wird der aktuelle VectorViewIterator vordekrementiert.

In der zweiten Syntax wird der aktuelle VectorViewIterator nachdekrementiert. Der Typ `int` in der zweiten Syntax gibt eine Nach-Dekrementierungsoperation an, keinen tatsächlichen ganzzahligen Operanden.

## <a name="operator-dereference"></a>  Vectorviewiterator::\* Operator

Ruft einen Verweis auf das Element ab, das vom aktuellen VectorViewIterator angegeben wird.

### <a name="syntax"></a>Syntax

```
reference operator*() const;
```

### <a name="return-value"></a>Rückgabewert

Das vom aktuellen VectorViewIterator angegebene Element.

## <a name="operator-equality"></a>  Vectorviewiterator:: Operator ==-Operator

Gibt an, ob der aktuelle VectorViewIterator gleich einem angegebenen VectorViewIterator ist.

### <a name="syntax"></a>Syntax

```
bool operator==(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parameter

*other*<br/>
Ein weiterer VectorViewIterator.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn die aktuelle `VectorViewIterator` gleich *andere*ist, andernfalls **"false"**.

## <a name="operator-greater-than"></a>  Vectorviewiterator::&gt; Operator

Gibt an, ob der aktuelle VectorViewIterator größer einem angegebenen VectorViewIterator ist.

### <a name="syntax"></a>Syntax

```

bool operator>(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parameter

*other*<br/>
Ein weiterer VectorViewIterator.

### <a name="return-value"></a>Rückgabewert

**"true"** ist der aktuelle VectorViewIterator größer als *andere*ist, andernfalls **"false"**.

## <a name="operator-greater-than-or-equals"></a>  Vectorviewiterator::&gt;Operator =-Operator

Gibt an, ob die aktuelle `VectorViewIterator` ist größer als oder gleich der angegebenen `VectorViewIterator`.

### <a name="syntax"></a>Syntax

```

bool operator>=(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parameter

*other*<br/>
Ein weiterer VectorViewIterator.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn die aktuelle `VectorViewIterator` ist größer als oder gleich *andere*ist, andernfalls **"false"**.

## <a name="operator-increment"></a>  Vectorviewiterator:: Operator++-Operator

Inkrementiert den aktuellen VectorViewIterator.

### <a name="syntax"></a>Syntax

```

VectorViewIterator& operator++();
VectorViewIterator operator++(int);
```

### <a name="return-value"></a>Rückgabewert

Die erste Syntax inkrementiert den aktuellen VectorViewIterator und gibt ihn dann zurück. Die zweite Syntax gibt eine Kopie des aktuellen VectorViewIterator zurück und inkrementiert dann den aktuellen VectorViewIterator.

### <a name="remarks"></a>Hinweise

In der ersten VectorViewIterator-Syntax wird der aktuelle VectorViewIterator vorinkrementiert.

In der zweiten Syntax wird der aktuelle VectorViewIterator nachinkrementiert. Der Typ `int` in der zweiten Syntax gibt eine Nach-Inkrementierungsoperation an, keinen tatsächlichen ganzzahligen Operanden.

## <a name="operator-inequality"></a>  Vectorviewiterator::! =-Operator

Gibt an, ob der aktuelle VectorViewIterator ungleich einem angegebenen VectorViewIterator ist.

### <a name="syntax"></a>Syntax

```
bool operator!=(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parameter

*other*<br/>
Ein weiterer VectorViewIterator.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn die aktuelle `VectorViewIterator` ist nicht gleich *andere*ist, andernfalls **"false"**.

## <a name="operator-less-than"></a>  Vectorviewiterator::&lt; Operator

Gibt an, ob der aktuelle VectorIterator kleiner einem angegebenen VectorIterator ist.

### <a name="syntax"></a>Syntax

```
bool operator<(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parameter

*other*<br/>
Eine andere `VectorIterator`.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn die aktuelle `VectorIterator` ist kleiner als *andere*ist, andernfalls **"false"**.

## <a name="operator-less-than-or-equals"></a>  Vectorviewiterator::&lt;Operator =-Operator

Gibt an, ob die aktuelle `VectorIterator` ist kleiner als oder gleich einem angegebenen `VectorIterator`.

### <a name="syntax"></a>Syntax

```

bool operator<=(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parameter

*other*<br/>
Eine andere `VectorIterator`.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn die aktuelle `VectorIterator` ist kleiner als oder gleich *andere*ist, andernfalls **"false"**.

## <a name="operator-minus"></a>  Vectorviewiterator:: Operator-

Subtrahiert entweder eine angegebene Anzahl von Elementen vom aktuellen Iterator und bildet einen neuen Iterator, oder subtrahiert einen angegebenen Iterator vom aktuellen Iterator, und gibt die Anzahl von Elementen zwischen den Iteratoren zurück.

### <a name="syntax"></a>Syntax

```

VectorViewIterator operator-(difference_type n) const;

difference_type operator-(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parameter

*n*<br/>
Eine Anzahl von Elementen.

*other*<br/>
Ein weiterer VectorViewIterator.

### <a name="return-value"></a>Rückgabewert

Die erste Operatorsyntax gibt ein VectorViewIterator-Objekt zurück, das `n` Elemente kleiner ist, als der aktuelle VectorViewIterator. Die zweite Operatorsyntax gibt die Anzahl von Elementen zwischen dem aktuellen und dem `other` VectorViewIterator zurück.

## <a name="operator-plus-equals"></a>  Vectorviewiterator:: Operator +=-Operator

Inkrementiert den aktuellen VectorViewIterator um die angegebene Verschiebung.

### <a name="syntax"></a>Syntax

```
VectorViewIterator& operator+=(difference_type n);
```

### <a name="parameters"></a>Parameter

*n*<br/>
Eine ganzzahlige Verschiebung.

### <a name="return-value"></a>Rückgabewert

Der aktualisierte VectorViewIterator.

## <a name="operator-plus"></a>  Vectorviewiterator:: +-Operator

Gibt einen VectorViewIterator zurück, der auf das Element an der angegebenen Verschiebung von dem angegebenen VectorViewIterator verweist.

### <a name="syntax"></a>Syntax

```

VectorViewIterator operator+(difference_type n) const;

template <typename T>
inline VectorViewIterator<T> operator+
   (ptrdiff_t n,
   const VectorViewIterator<T>& i);
```

### <a name="parameters"></a>Parameter

*T*<br/>
In der zweiten Syntax der Typname vom VectorViewIterator.

*n*<br/>
Eine ganzzahlige Verschiebung.

*i*<br/>
In der zweiten Syntax ein VectorViewIterator.

### <a name="return-value"></a>Rückgabewert

In der ersten Syntax ein VectorViewIterator, der auf das Element an der angegebenen Verschiebung vom aktuellen VectorViewIterator verweist.

In der zweiten Syntax ein VectorViewIterator, der auf das Element an der angegebenen Verschiebung vom Anfang des Parameters `i` verweist.

## <a name="operator-minus-assign"></a>  Vectorviewiterator:: Operator-=-Operator

Dekrementiert den aktuellen VectorIterator um die angegebene Verschiebung.

### <a name="syntax"></a>Syntax

```
VectorViewIterator& operator-=(difference_type n);
```

### <a name="parameters"></a>Parameter

*n*<br/>
Eine ganzzahlige Verschiebung.

### <a name="return-value"></a>Rückgabewert

Der aktualisierte VectorIterator.

## <a name="operator-at"></a>  Vectorviewiterator::\[\]

Ruft einen Verweis auf das Element ab, das eine angegebene Verschiebung vom aktuellen VectorViewIterator ist.

### <a name="syntax"></a>Syntax

```
reference operator[](difference_type n) const;
```

### <a name="parameters"></a>Parameter

*n*<br/>
Eine ganzzahlige Verschiebung.

### <a name="return-value"></a>Rückgabewert

Das Element, das vom aktuellen VectorViewIterator um `n` Elemente verschoben wird.

## <a name="ctor"></a>  Vectorviewiterator:: Vectorviewiterator-Konstruktor

Initialisiert eine neue Instanz der VectorViewIterator-Klasse.

### <a name="syntax"></a>Syntax

```

VectorViewIterator();

explicit VectorViewIterator(
   Windows::Foundation::Collections::IVectorView<T>^ v
);
```

### <a name="parameters"></a>Parameter

*v*<br/>
Ein IVectorView\<T > Objekt.

### <a name="remarks"></a>Hinweise

Das erste Syntaxbeispiel ist der Standardkonstruktor. Das zweite Syntaxbeispiel ist ein expliziter Konstruktor, der verwendet wird, erstellen Sie einen VectorViewIterator aus einem IVectorView\<T > Objekt.

## <a name="see-also"></a>Siehe auch

[Plattform-Namespace](platform-namespace-c-cx.md)
