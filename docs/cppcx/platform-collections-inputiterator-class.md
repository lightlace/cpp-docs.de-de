---
title: Platform::Collections::InputIterator-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::InputIterator::InputIterator
dev_langs:
- C++
helpviewer_keywords:
- InputIterator Class
ms.assetid: ef72eea4-32a9-42b9-8119-ce87dbdcd3be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a0aa56c511ac5f7b98ffdd75aebd7f71ef9f21ac
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49162021"
---
# <a name="platformcollectionsinputiterator-class"></a>Platform::Collections::InputIterator-Klasse

Stellt einen InputIterator der Standardvorlagenbibliothek für Auflistungen, die von der Windows-Runtime abgeleitet.

## <a name="syntax"></a>Syntax

```
template <typename X>
class InputIterator;
```

#### <a name="parameters"></a>Parameter

*X*<br/>
Der Typname der InputIterator-Vorlagenklasse.

### <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`difference_type`|Ein Zeigerunterschied (ptrdiff_t).|
|`iterator_category`|Die Kategorie eines Eingabeiterators (::std::input_iterator_tag).|
|`pointer`|Ein Zeiger auf eine `const X`|
|`reference`|Ein Verweis auf eine `const X`|
|`value_type`|Der `X` -Typname.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[InputIterator::InputIterator](#ctor)|Initialisiert eine neue Instanz der InputIterator-Klasse.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[InputIterator::operator!=-Operator](#operator-inequality)|Gibt an, ob der aktuelle InputIterator ungleich einem angegebenen InputIterator ist.|
|[InputIterator::operator*-Operator](#operator-decrement)|Ruft einen Verweis auf das Element ab, das vom aktuellen InputIterator angegeben wird.|
|[InputIterator::operator++-Operator](#operator-increment)|Inkrementiert den aktuellen InputIterator.|
|[InputIterator::operator==-Operator](#operator-equality)|Gibt an, ob der aktuelle InputIterator gleich einem angegebenen InputIterator ist.|
|[InputIterator::operator->-Operator](#operator-arrow)|Ruft die Adresse des Elements ab, auf das vom aktuellen InputIterator verwiesen wird.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`InputIterator`

### <a name="requirements"></a>Anforderungen

**Header:** collection.h

**Namespace:** Platform::Collections

## <a name="ctor"></a>  Inputiterator:: Inputiterator-Konstruktor

Initialisiert eine neue Instanz der InputIterator-Klasse.

### <a name="syntax"></a>Syntax

```
InputIterator();
explicit InputIterator(Windows::Foundation::Collections<X>^ iter);
```

### <a name="parameters"></a>Parameter

*Iter*<br/>
Ein Iteratorobjekt.

## <a name="operator-arrow"></a>  Inputiterator:: -&gt; Operator

Ruft die Adresse des Elements ab, das vom aktuellen InputIterator angegeben wird.

### <a name="syntax"></a>Syntax

```
pointer operator->() const;
```

### <a name="return-value"></a>Rückgabewert

Die Adresse des Elements, das vom aktuellen InputIterator angegeben wird.

## <a name="operator-dereference"></a>  Inputiterator::\* Operator

Ruft einen Verweis auf das Element ab, das vom aktuellen InputIterator angegeben wird.

### <a name="syntax"></a>Syntax

```
reference operator*() const;
```

### <a name="return-value"></a>Rückgabewert

Das Element, das durch den aktuellen InputIterator angegeben wird.

## <a name="operator-equality"></a>  Inputiterator:: Operator ==-Operator

Gibt an, ob der aktuelle InputIterator gleich einem angegebenen InputIterator ist.

### <a name="syntax"></a>Syntax

```
bool operator== (const InputIterator& other) const;
```

### <a name="parameters"></a>Parameter

*other*<br/>
Ein weiterer InputIterator.

### <a name="return-value"></a>Rückgabewert

**"true"** ist der aktuelle InputIterator gleich *andere*ist, andernfalls **"false"**.

## <a name="operator-increment"></a>  Inputiterator:: Operator++-Operator

Inkrementiert den aktuellen InputIterator.

### <a name="syntax"></a>Syntax

```
InputIterator& operator++();
InputIterator operator++(int);
```

### <a name="return-value"></a>Rückgabewert

Die erste Syntax inkrementiert den aktuellen InputIterator und gibt ihn dann zurück. Die zweite Syntax gibt eine Kopie des aktuellen InputIterator zurück und inkrementiert dann den aktuellen InputIterator.

### <a name="remarks"></a>Hinweise

Die ersten InputIterator-Syntax vorinkrementiert den aktuellen InputIterator.

Die zweite Syntax nachinkrementiert den aktuellen InputIterator. Der Typ `int` in der zweiten Syntax gibt eine Nach-Inkrementierungsoperation an, keinen tatsächlichen ganzzahligen Operanden.

## <a name="operator-inequality"></a>  Inputiterator::! =-Operator

Gibt an, ob der aktuelle InputIterator ungleich einem angegebenen InputIterator ist.

### <a name="syntax"></a>Syntax

```
bool operator!=(const InputIterator& other) const;
```

### <a name="parameters"></a>Parameter

*other*<br/>
Ein weiterer InputIterator.

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn der aktuelle InputIterator ungleich ist *andere*ist, andernfalls **"false"**.

## <a name="see-also"></a>Siehe auch

[Plattform-Namespace](platform-namespace-c-cx.md)