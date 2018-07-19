---
title: '&lt;system_error&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- system_error/std::operator!=
- system_error/std::operator==
dev_langs:
- C++
ms.assetid: c14edefb-bd8a-4e90-88d3-c59c98e6f73c
ms.openlocfilehash: 974b1294f8ef23936d79e64926595779a9019368
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38963692"
---
# <a name="ltsystemerrorgt-operators"></a>&lt;system_error&gt;-Operatoren

||||
|-|-|-|
|[operator!=](#op_neq)|[operator&lt;](#op_lt)|[operator==](#op_eq_eq)|

## <a name="op_eq_eq"></a> operator==

Testet, ob das Objekt links vom Operator gleich dem Objekt rechts vom Operator ist.

```cpp
bool operator==(const error_code& left,
    const error_condition& right);

bool operator==(const error_condition& left,
    const error_code& right);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*left*|Das Objekt, das auf Gleichheit getestet werden soll.|
|*right*|Das Objekt, das auf Gleichheit getestet werden soll.|

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Objekte gleich sind; **FALSE**, wenn die Objekte nicht gleich sind.

### <a name="remarks"></a>Hinweise

Die Funktion gibt `left.category() == right.category() && left.value() == right.value()`zurück.

## <a name="op_neq"></a> operator!=

Testet, ob das Objekt links vom Operator ungleich dem Objekt rechts vom Operator ist.

```cpp
bool operator!=(const error_code& left,
    const error_condition& right);

bool operator!=(const error_condition& left,
    const error_code& right);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*left*|Das Objekt, das auf Ungleichheit geprüft werden soll.|
|*right*|Das Objekt, das auf Ungleichheit geprüft werden soll.|

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn das übergebene Objekt *linken* ist nicht gleich dem übergebenen Objekt *rechten*andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Die Funktion gibt `!(left == right)`zurück.

## <a name="op_lt"></a> operator&lt;

Testet, ob ein Objekt kleiner ist als das Objekt, das für den Vergleich übergeben wurde.

```cpp
template <class _Enum>
inline bool operator<(
    _Enum left,
    typename enable_if<is_error_code_enum<_Enum>::value,
    const error_code&>::type right);

template <class _Enum>
inline bool operator<(
    typename enable_if<is_error_code_enum<_Enum>::value,
    const error_code&>::type left, _Enum right);

template <class _Enum>
inline bool operator<(
    _Enum left,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    const error_condition&>::type right);

template <class _Enum>
inline bool operator<(
    typename enable_if<is_error_condition_enum<_Enum>::value,
    const error_condition&>::type left, _Enum right);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*left*|Das zu vergleichende Objekt.|
|*right*|Das zu vergleichende Objekt.|

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn das übergebene Objekt *linken* ist kleiner als das übergebene Objekt *rechten*; Andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Mit dieser Funktion wird die Fehlerreihenfolge getestet.

## <a name="see-also"></a>Siehe auch

[<system_error>](../standard-library/system-error.md)<br/>
