---
title: '&lt;system_error&gt;-Operatoren'
ms.date: 11/04/2016
f1_keywords:
- system_error/std::operator!=
- system_error/std::operator==
ms.assetid: c14edefb-bd8a-4e90-88d3-c59c98e6f73c
ms.openlocfilehash: 5cf6a455beb5654ef65f7411db4783a32c71d625
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246209"
---
# <a name="ltsystemerrorgt-operators"></a>&lt;system_error&gt;-Operatoren

## <a name="op_eq_eq"></a> Operator ==

Testet, ob das Objekt links vom Operator gleich dem Objekt rechts vom Operator ist.

```cpp
bool operator==(const error_code& left,
    const error_condition& right);

bool operator==(const error_condition& left,
    const error_code& right);

bool operator==(const error_condition& left,
    const error_condition& right);
```

### <a name="parameters"></a>Parameter

*Links*\
Das Objekt, das auf Gleichheit getestet werden soll.

*Richting*\
Das Objekt, das auf Gleichheit getestet werden soll.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Objekte gleich sind; **FALSE**, wenn die Objekte nicht gleich sind.

### <a name="remarks"></a>Hinweise

Die Funktion gibt `left.category() == right.category() && left.value() == right.value()`zurück.

## <a name="op_neq"></a> Operator! =

Testet, ob das Objekt links vom Operator ungleich dem Objekt rechts vom Operator ist.

```cpp
bool operator!=(const error_code& left, const error_condition& right);
bool operator!=(const error_condition& left, const error_code& right);
bool operator!=(const error_code& left, const error_code& right);
bool operator!=(const error_condition& left, const error_condition& right);
```

### <a name="parameters"></a>Parameter

*Links*\
Das Objekt, das auf Ungleichheit geprüft werden soll.

*Richting*\
Das Objekt, das auf Ungleichheit geprüft werden soll.

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn das übergebene Objekt *linken* ist nicht gleich dem übergebenen Objekt *rechten*andernfalls **"false"** .

### <a name="remarks"></a>Hinweise

Die Funktion gibt `!(left == right)`zurück.

## <a name="op_lt"></a>-Operator&lt;

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

*Links*\
Das zu vergleichende Objekt.

*Richting*\
Das zu vergleichende Objekt.

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn das übergebene Objekt *linken* ist kleiner als das übergebene Objekt *rechten*; Andernfalls **"false"** .

### <a name="remarks"></a>Hinweise

Mit dieser Funktion wird die Fehlerreihenfolge getestet.

## <a name="op_ostream"></a> Operator&lt;&lt;

```cpp
template <class charT, class traits> 
    basic_ostream<charT, traits>& operator<<(basic_ostream<charT, traits>& os, const error_code& ec);
```
