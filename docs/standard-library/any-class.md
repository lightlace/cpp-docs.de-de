---
title: Jede Klasse
ms.date: 04/04/2019
f1_keywords:
- any/std::any
- any/std::any::emplace
- any/std::any::has_value
- any/std::any::reset
- any/std::any::swap
- any/std::any::type
helpviewer_keywords:
- any/std::any
- any/std::any::emplace
- any/std::any::has_value
- any/std::any::reset
- any/std::any::swap
- any/std::any::type
ms.openlocfilehash: 050276da665ab6ed3eb53d9e65bfea06b88bcbea
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268752"
---
# <a name="any-class"></a>Jede Klasse

Speichert, die eine Instanz eines beliebigen Typs, das erfüllt die Anforderungen der Konstruktor oder es wurde kein Wert, der angibt bezeichnet den Zustand der Klasse ein Objekt.

Die gespeicherte Instanz wird den enthaltenen Wert aufgerufen werden. Zwei Zustände sind identisch, wenn entweder beide keinen Wert haben oder jeweils einen Wert und die enthaltenen Werte identisch sind.

## <a name="syntax"></a>Syntax

```cpp
class any
```

## <a name="members"></a>Member

### <a name="constructors"></a>Konstruktoren

|||
|-|-|
|[any](#any)|Konstruiert ein Objekt vom Typ `any`.|

### <a name="functions"></a>Funktionen

|||
|-|-|
|[emplace](#emplace)|Legt einen beliebiger Wert fest.|
|[has_value](#has_value)|Gibt **"true"** , wenn einen Wert vorhanden.|
|[reset](#reset)|Setzt ein alle.|
|[swap](#swap)|Tauscht zwei Objekte.|
|[Typ](#type)|Gibt den Typ any zurück.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[operator=](#op_eq)|Alle mit einer Kopie eines anderen alle ersetzt werden.|

## <a name="any"></a> Alle

Konstruiert ein Objekt vom Typ `any`. Enthält auch einen Destruktor.

```cpp
constexpr any() noexcept;
any(const any& other);
any(any&& other) noexcept;
template <class T>
    any(T&& value);
template <class T, class... Args>
    explicit any(in_place_type_t<T>, Args&&...);
template <class T, class U, class... Args>
    explicit any(in_place_type_t<T>, initializer_list<U>, Args&&...);

~any();
```

## <a name="emplace"></a> emplace-

Legt einen beliebiger Wert fest.

```cpp
template <class T, class... Args>
    decay_t<T>& emplace(Args&& ...);
template <class T, class U, class... Args>
    decay_t<T>& emplace(initializer_list<U>, Args&&...);
```

## <a name="has_value"></a> has_value

Gibt **"true"** , wenn einen Wert vorhanden.

```cpp
bool has_value() const noexcept;
```

## <a name="op_eq"></a> Operator =

Alle mit einer Kopie eines anderen alle ersetzt werden.

```cpp
any& operator=(const any& right);
any& operator=(any&& right) noexcept;
template <class T>
    any& operator=(T&& right);
```

### <a name="parameters"></a>Parameter

*Richting*\
Alle in einem kopiert wird.

## <a name="reset"></a> Zurücksetzen

Setzt ein alle.

```cpp
void reset() noexcept;
```

## <a name="swap"></a> Swap

Tauscht zwei Objekte.

```cpp
void swap(any& rhs) noexcept;
```

## <a name="type"></a> Typ

Gibt den Typ any zurück.

```cpp
const type_info& type() const noexcept;
```
