---
title: error_code-Klasse
ms.date: 11/04/2016
f1_keywords:
- system_error/std::error_code
- system_error/std::error_code::value_type
- system_error/std::error_code::assign
- system_error/std::error_code::category
- system_error/std::error_code::clear
- system_error/std::error_code::default_error_condition
- system_error/std::error_code::message
- system_error/std::error_code::operator bool
helpviewer_keywords:
- std::error_code
- std::error_code::value_type
- std::error_code::assign
- std::error_code::category
- std::error_code::clear
- std::error_code::default_error_condition
- std::error_code::message
ms.assetid: c09b4a96-cb14-4281-a319-63543f9b2b4a
ms.openlocfilehash: 919a2a81c66de9adf15deeae8cf8ff3dea08762e
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245821"
---
# <a name="errorcode-class"></a>error_code-Klasse

Stellt Systemfehler auf niedriger Ebene dar, die spezifisch für die Implementierung sind.

## <a name="syntax"></a>Syntax

```cpp
class error_code;
```

## <a name="remarks"></a>Hinweise

Ein Objekt vom Typ `error_code`-Klasse enthält einen Fehlercodewert und einen Zeiger auf ein Objekt, das eine [Kategorie](../standard-library/error-category-class.md) von Fehlercodes darstellt, die gemeldete Systemfehler auf niedriger Ebene beschreiben.

## <a name="members"></a>Member

### <a name="constructors"></a>Konstruktoren

|||
|-|-|
|[error_code](#error_code)|Konstruiert ein Objekt vom Typ `error_code`.|

### <a name="typedefs"></a>Typedefs

|||
|-|-|
|[value_type](#value_type)|Ein Typ, der den gespeicherten Fehlercodewert darstellt.|

### <a name="functions"></a>Funktionen

|||
|-|-|
|[assign](#assign)|Weist einen Fehlercodewert und die Kategorie an einen Fehlercode zu.|
|[category](#category)|Gibt die Fehlerkategorie zurück.|
|[clear](#clear)|Löscht den Fehlercodewert und die Kategorie.|
|[default_error_condition](#default_error_condition)|Gibt die Standardfehlerbedingung zurück.|
|[message](#message)|Gibt den Namen des Fehlercodes zurück.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[operator==](#op_eq_eq)|Prüft auf Gleichheit zwischen `error_code`-Objekten.|
|[Operator!=](#op_neq)|Prüft auf Ungleichheit zwischen `error_code`-Objekten.|
|[operator<](#op_lt)|Testet, ob das `error_code`-Objekt kleiner ist als das `error_code`-Objekt, das für den Vergleich übergeben wurde.|
|[operator=](#op_eq)|Weist dem `error_code`-Objekt einen neuen Enumerationswert zu.|
|[operator bool](#op_bool)|Wandelt eine Variable vom Typ `error_code` um.|

### <a name="assign"></a> Weisen Sie

Weist einen Fehlercodewert und die Kategorie an einen Fehlercode zu.

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

#### <a name="remarks"></a>Hinweise

### <a name="clear"></a> Deaktivieren

Löscht den Fehlercodewert und die Kategorie.

```cpp
clear();
```

#### <a name="remarks"></a>Hinweise

Die Memberfunktion speichert einen Fehlercodewert „Null“ und einen Zeiger auf das Objekt [generic_category](../standard-library/system-error-functions.md#generic_category).

### <a name="default_error_condition"></a> default_error_condition

Gibt die Standardfehlerbedingung zurück.

```cpp
error_condition default_error_condition() const;
```

#### <a name="return-value"></a>Rückgabewert

Die von [default_error_condition](../standard-library/error-category-class.md#default_error_condition) angegebene Funktion [error_condition](../standard-library/error-condition-class.md).

#### <a name="remarks"></a>Hinweise

Diese Memberfunktion gibt `category().default_error_condition(value())` zurück.

### <a name="error_code"></a> error_code

Konstruiert ein Objekt vom Typ `error_code`.

```cpp
error_code();

error_code(value_type val, const error_category& _Cat);

template <class _Enum>
error_code(_Enum _Errcode,
    typename enable_if<is_error_code_enum<_Enum>::value,
    error_code>::type* = 0);
```

#### <a name="parameters"></a>Parameter

*val*\
Der Fehlercodewert, der in `error_code` gespeichert werden soll.

*_Cat*\
Die Fehlerkategorie, die in `error_code` gespeichert werden soll.

*_Errcode*\
Der Enumerationswert, der in `error_code` gespeichert werden soll.

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

Prüft auf Gleichheit zwischen `error_code`-Objekten.

```cpp
bool operator==(const error_code& right) const;
```

#### <a name="parameters"></a>Parameter

*Richting*\
Das Objekt, das auf Gleichheit getestet werden soll.

#### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Objekte gleich sind; **FALSE**, wenn die Objekte nicht gleich sind.

#### <a name="remarks"></a>Hinweise

Der Memberoperator gibt `category() == right.category() && value == right.value()`zurück.

### <a name="op_neq"></a> Operator! =

Prüft auf Ungleichheit zwischen `error_code`-Objekten.

```cpp
bool operator!=(const error_code& right) const;
```

#### <a name="parameters"></a>Parameter

*Richting*\
Das Objekt, das auf Ungleichheit geprüft werden soll.

#### <a name="return-value"></a>Rückgabewert

**"true"** Wenn die `error_code` Objekt ist nicht gleich der `error_code` Objekt übergebenen *rechten*; andernfalls **"false"** .

#### <a name="remarks"></a>Hinweise

Der Memberoperator gibt `!(*this == right)`zurück.

### <a name="op_lt"></a>-Operator&lt;

Testet, ob das `error_code`-Objekt kleiner ist als das `error_code`-Objekt, das für den Vergleich übergeben wurde.

```cpp
bool operator<(const error_code& right) const;
```

#### <a name="parameters"></a>Parameter

*Richting*\
Das zu vergleichende error_code-Objekt.

#### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn das Objekt, das an `error_code` übergeben wird, kleiner ist als das an `error_code` übergebene Objekt; andernfalls **FALSE**.

#### <a name="remarks"></a>Hinweise

Der Memberoperator gibt `category() < right.category() || category() == right.category() && value < right.value()`zurück.

### <a name="op_eq"></a> Operator =

Weist dem `error_code`-Objekt einen neuen Enumerationswert zu.

```cpp
template <class _Enum>
typename enable_if<is_error_code_enum<_Enum>::value, error_code>::type&
    operator=(_Enum _Errcode);
```

#### <a name="parameters"></a>Parameter

*_Errcode*\
Der Enumerationswert, der dem `error_code`-Objekt zugewiesen wird.

#### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das `error_code`-Objekt, dem der neue Enumerationswert durch die Memberfunktion zugewiesen wird.

#### <a name="remarks"></a>Hinweise

Der Memberoperator speichert `(value_type)_Errcode` als Fehlercodewert und einen Zeiger auf [generic_category](../standard-library/system-error-functions.md#generic_category). Er gibt `*this` zurück.

### <a name="op_bool"></a> Operator bool

Wandelt eine Variable vom Typ `error_code` um.

```cpp
explicit operator bool() const;
```

#### <a name="return-value"></a>Rückgabewert

Der boolesche Wert des Objekts `error_code`.

#### <a name="remarks"></a>Hinweise

Der Operator gibt einen Wert konvertiert werden kann, um **"true"** nur, wenn [Wert](#value) ist nicht gleich 0 (null). Der Rückgabetyp ist in nur **"bool"** , nicht zu `void *` oder anderen bekannten skalaren Typen.

### <a name="value"></a> Wert

Gibt den gespeicherten Fehlercodewert zurück.

```cpp
value_type value() const;
```

### <a name="return-value"></a>Rückgabewert

Der gespeicherte Fehlercodewert vom Typ [value_type](#value_type).

### <a name="value_type"></a> value_type

Ein Typ, der den gespeicherten Fehlercodewert darstellt.

```cpp
typedef int value_type;
```

#### <a name="remarks"></a>Hinweise

Diese Typdefinition ist ein Synonym für **Int**.
