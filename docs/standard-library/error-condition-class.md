---
title: error_condition-Klasse
ms.date: 11/04/2016
f1_keywords:
- system_error/std::error_condition
- system_error/std::error_condition::value_type
- system_error/std::error_condition::assign
- system_error/std::error_condition::category
- system_error/std::error_condition::clear
- system_error/std::error_condition::message
- system_error/std::error_condition::operator bool
helpviewer_keywords:
- std::error_condition
- std::error_condition::value_type
- std::error_condition::assign
- std::error_condition::category
- std::error_condition::clear
- std::error_condition::message
ms.assetid: 6690f481-97c9-4554-a0ff-851dc96b7a06
ms.openlocfilehash: cbadf6a22871cc9a23d37c095a398490c8a4c72c
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245799"
---
# <a name="errorcondition-class"></a>error_condition-Klasse

Stellt benutzerdefinierte Fehlercodes dar.

## <a name="syntax"></a>Syntax

```cpp
class error_condition;
```

## <a name="remarks"></a>Hinweise

Ein Objekt vom Typ `error_condition` enthält einen Fehlercodewert und einen Zeiger auf ein Objekt, das eine [category (Kategorie)](../standard-library/error-category-class.md) von Fehlercodes darstellt, die für berichtete benutzerdefinierte Fehlercodes verwendet werden.

## <a name="members"></a>Member

### <a name="constructors"></a>Konstruktoren

|||
|-|-|
|[error_condition](#error_condition)|Konstruiert ein Objekt vom Typ `error_condition`.|

### <a name="typedefs"></a>Typedefs

|||
|-|-|
|[value_type](#value_type)|Ein Typ, der den gespeicherten Fehlercodewert darstellt.|

### <a name="functions"></a>Funktionen

|||
|-|-|
|[assign](#assign)|Weist einen Fehlercodewert und die Kategorie an eine Fehlerbedingung zurück.|
|[category](#category)|Gibt die Fehlerkategorie zurück.|
|[clear](#clear)|Löscht den Fehlercodewert und die Kategorie.|
|[message](#message)|Gibt den Namen des Fehlercodes zurück.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[operator==](#op_eq_eq)|Prüft auf Gleichheit zwischen `error_condition`-Objekten.|
|[Operator!=](#op_neq)|Prüft auf Ungleichheit zwischen `error_condition`-Objekten.|
|[operator<](#op_lt)|Testet, ob das `error_condition`-Objekt kleiner ist als das `error_code`-Objekt, das für den Vergleich übergeben wurde.|
|[operator=](#op_eq)|Weist dem `error_condition`-Objekt einen neuen Enumerationswert zu.|
|[operator bool](#op_bool)|Wandelt eine Variable vom Typ `error_condition` um.|

### <a name="assign"></a> Weisen Sie

Weist einen Fehlercodewert und die Kategorie an eine Fehlerbedingung zurück.

```cpp
void assign(value_type val, const error_category& _Cat);
```

#### <a name="parameters"></a>Parameter

*val*\
Der Fehlercodewert, der in `error_code` gespeichert werden soll.

*_Cat*\
Die Fehlerkategorie, die in `error_code` gespeichert werden soll.

#### <a name="remarks"></a>Hinweise

Die Memberfunktion speichert *Val* als Fehlercodewert und einen Zeiger auf *_Cat*.

### <a name="category"></a> Kategorie

Gibt die Fehlerkategorie zurück.

```cpp
const error_category& category() const;
```

#### <a name="return-value"></a>Rückgabewert

Ein Verweis auf die gespeicherte Fehlerkategorie.

#### <a name="remarks"></a>Hinweise

### <a name="clear"></a> Deaktivieren

Löscht den Fehlercodewert und die Kategorie.

```cpp
clear();
```

#### <a name="remarks"></a>Hinweise

Die Memberfunktion speichert einen Fehlercodewert „Null“ und einen Zeiger auf das Objekt [generic_category](../standard-library/system-error-functions.md#generic_category).

### <a name="error_condition"></a> error_condition

Konstruiert ein Objekt vom Typ `error_condition`.

```cpp
error_condition();

error_condition(value_type val, const error_category& _Cat);

template <class _Enum>
error_condition(_Enum _Errcode,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    error_code>::type* = 0);
```

#### <a name="parameters"></a>Parameter

*val*\
Der Fehlercodewert, der in `error_condition` gespeichert werden soll.

*_Cat*\
Die Fehlerkategorie, die in `error_condition` gespeichert werden soll.

*_Errcode*\
Der Enumerationswert, der in `error_condition` gespeichert werden soll.

#### <a name="remarks"></a>Hinweise

Der erste Konstruktor speichert einen Fehlercodewert „Null“ und einen Zeiger auf [generic_category](../standard-library/system-error-functions.md#generic_category).

Der zweite Konstruktor speichert *Val* als Fehlercodewert und einen Zeiger auf [Error_category](../standard-library/error-category-class.md).

Der dritte Konstruktor speichert `(value_type)_Errcode` als Fehlercodewert und einen Zeiger auf [generic_category](../standard-library/system-error-functions.md#generic_category).

### <a name="message"></a> Nachricht

Gibt den Namen des Fehlercodes zurück.

```cpp
string message() const;
```

#### <a name="return-value"></a>Rückgabewert

Ein `string`, der den Namen des Fehlercodes darstellt.

#### <a name="remarks"></a>Hinweise

Diese Memberfunktion gibt `category().message(value())` zurück.

### <a name="op_eq_eq"></a> Operator ==

Prüft auf Gleichheit zwischen `error_condition`-Objekten.

```cpp
bool operator==(const error_condition& right) const;
```

#### <a name="parameters"></a>Parameter

*Richting*\
Die Objekte, die auf Gleichheit getestet werden sollen.

#### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Objekte gleich sind; **FALSE**, wenn die Objekte nicht gleich sind.

#### <a name="remarks"></a>Hinweise

Der Memberoperator gibt `category() == right.category() && value == right.value()`zurück.

### <a name="op_neq"></a> Operator! =

Prüft auf Ungleichheit zwischen `error_condition`-Objekten.

```cpp
bool operator!=(const error_condition& right) const;
```

#### <a name="parameters"></a>Parameter

*Richting*\
Das Objekt, das auf Ungleichheit geprüft werden soll.

#### <a name="return-value"></a>Rückgabewert

**"true"** Wenn die `error_condition` Objekt ist nicht gleich der `error_condition` Objekt übergebenen *rechten*; andernfalls **"false"** .

#### <a name="remarks"></a>Hinweise

Der Memberoperator gibt `!(*this == right)`zurück.

### <a name="op_lt"></a>-Operator&lt;

Testet, ob das `error_condition`-Objekt kleiner ist als das `error_code`-Objekt, das für den Vergleich übergeben wurde.

```cpp
bool operator<(const error_condition& right) const;
```

#### <a name="parameters"></a>Parameter

*Richting*\
Das zu vergleichende `error_condition`-Objekt.

#### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn das Objekt, das an `error_condition` übergeben wird, kleiner ist als das an `error_condition` übergebene Objekt; andernfalls **FALSE**.

#### <a name="remarks"></a>Hinweise

Der Memberoperator gibt `category() < right.category() || category() == right.category() && value < right.value()`zurück.

### <a name="op_eq"></a> Operator =

Weist dem `error_condition`-Objekt einen neuen Enumerationswert zu.

```cpp
template <class _Enum>
error_condition(_Enum error,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    error_condition>::type&
    operator=(Enum _Errcode);
```

#### <a name="parameters"></a>Parameter

*_Errcode*\
Der Enumerationswert, der dem `error_condition`-Objekt zugewiesen wird.

#### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das `error_condition`-Objekt, dem der neue Enumerationswert durch die Memberfunktion zugewiesen wird.

#### <a name="remarks"></a>Hinweise

Der Memberoperator speichert `(value_type)error` als Fehlercodewert und einen Zeiger auf [generic_category](../standard-library/system-error-functions.md#generic_category). Er gibt `*this` zurück.

### <a name="op_bool"></a> Operator bool

Wandelt eine Variable vom Typ `error_condition` um.

```cpp
explicit operator bool() const;
```

#### <a name="return-value"></a>Rückgabewert

Der boolesche Wert des Objekts `error_condition`.

#### <a name="remarks"></a>Hinweise

Der Operator gibt einen Wert konvertiert werden kann, um **"true"** nur, wenn [Wert](#value) ist nicht gleich 0 (null). Der Rückgabetyp ist in nur **"bool"** , nicht zu `void *` oder anderen bekannten skalaren Typen.

### <a name="value"></a> Wert

Gibt den gespeicherten Fehlercodewert zurück.

```cpp
value_type value() const;
```

#### <a name="return-value"></a>Rückgabewert

Der gespeicherte Fehlercodewert vom Typ [value_type](#value_type).

#### <a name="remarks"></a>Hinweise

### <a name="value_type"></a> value_type

Ein Typ, der den gespeicherten Fehlercodewert darstellt.

```cpp
typedef int value_type;
```

#### <a name="remarks"></a>Hinweise

Die Typdefinition ist ein Synonym für **Int**.
