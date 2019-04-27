---
title: '&lt;forward_list&gt;-Operatoren'
ms.date: 11/04/2016
f1_keywords:
- forward_list/std::operator!=
- forward_list/std::operator==
- forward_list/std::operatoroperator&gt;
- forward_list/std::operatoroperator&gt=;
- forward_list/std::operatoroperator&lt;
- forward_list/std::operatoroperator&lt;=
ms.assetid: 57492e09-3836-4dbc-9ae5-78ecf506c190
helpviewer_keywords:
- std::operator!= (forward_list)
- std::operator== (forward_list)
- std::operatoroperator&gt; (forward_list)
- std::operatoroperator&gt=; (forward_list)
- std::operatoroperator&lt; (forward_list)
- std::operatoroperator&lt;= (forward_list)
ms.openlocfilehash: 4126b81f61bd37a7a12e0621c323ec832c5b2ab7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159430"
---
# <a name="ltforwardlistgt-operators"></a>&lt;forward_list&gt;-Operatoren

||||
|-|-|-|
|[Operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[operator&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|

## <a name="op_eq_eq"></a> operator==

Testet, ob das Listenobjekt links vom Operator gleich dem Listenobjekt rechts vom Operator ist

```cpp
bool operator==(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*left*|Ein Objekt vom Typ `forward_list`.|
|*right*|Ein Objekt vom Typ `forward_list`.|

### <a name="remarks"></a>Hinweise

Diese Vorlagenfunktion überlädt `operator==`, um zwei Objekte der Vorlagenklasse `forward_list` zu vergleichen. Die Funktion gibt `distance(left.begin(), end()) == distance(right.begin(),right.end()) && equal(left. begin(),left. end(),right.begin())` zurück.

## <a name="op_neq"></a> operator!=

Testet, ob das Listenobjekt links vom Operator ungleich dem Listenobjekt rechts vom Operator ist

```cpp
bool operator!=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*left*|Ein Objekt vom Typ `forward_list`.|
|*right*|Ein Objekt vom Typ `forward_list`.|

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Listen ungleich sind; **FALSE**, wenn die Listen gleich sind.

### <a name="remarks"></a>Hinweise

Diese Vorlagenfunktion gibt `!(left == right)` zurück.

## <a name="op_lt"></a> operator&lt;

Testet, ob das Listenobjekt links vom Operator kleiner als das Listenobjekt auf der rechten Seite ist

```cpp
bool operator<(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*left*|Ein Objekt vom Typ `forward_list`.|
|*right*|Ein Objekt vom Typ `forward_list`.|

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Liste links vom Operator kleiner als, aber ungleich der Liste rechts vom Operator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Diese Vorlagenfunktion überlädt `operator<`, um zwei Objekte der Vorlagenklasse `forward_list` zu vergleichen. Die Funktion gibt `lexicographical_compare(lhs. begin(), lhs. end(), rhs.begin(), rhs.end())` zurück.

## <a name="op_lt_eq"></a> operator&lt;=

Testet, ob das Listenobjekt links vom Operator kleiner als oder gleich dem Listenobjekt rechts vom Operator ist

```cpp
bool operator<=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*left*|Ein Objekt vom Typ `forward_list`.|
|*right*|Ein Objekt vom Typ `forward_list`.|

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Liste links vom Operator kleiner als oder gleich der Liste rechts vom Operator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Diese Vorlagenfunktion gibt `!(right < left)` zurück.

## <a name="op_gt"></a> operator&gt;

Testet, ob das Listenobjekt links vom Operator größer als das Listenobjekt auf der rechten Seite ist

```cpp
bool operator>(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*left*|Ein Objekt vom Typ `forward_list`.|
|*right*|Ein Objekt vom Typ `forward_list`.|

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Liste links vom Operator größer als die Liste rechts vom Operator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Die dritte Vorlagenfunktion gibt `right < left` zurück.

## <a name="op_gt_eq"></a> operator&gt;=

Testet, ob das Listenobjekt links vom Operator größer als oder gleich dem Listenobjekt rechts vom Operator ist

```cpp
bool operator>=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*left*|Ein Objekt vom Typ `forward_list`.|
|*right*|Ein Objekt vom Typ `forward_list`.|

### <a name="return-value"></a>Rückgabewert

**"true"** ist die Liste links vom Operator größer als oder gleich der Liste rechts vom Operator ist; andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion gibt `!(left < right)` zurück.

## <a name="see-also"></a>Siehe auch

[<forward_list>](../standard-library/forward-list.md)<br/>
