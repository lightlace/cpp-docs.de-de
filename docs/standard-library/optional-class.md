---
title: Optionale-Klasse
ms.date: 11/04/2016
f1_keywords:
- optional/std::optional
- optional/std::optional::has_value
- optional/std::optional::reset
- optional/std::optional::value
- optional/std::optional::value_or
helpviewer_keywords:
- optional/std::optional
- optional/std::optional::has_value
- optional/std::optional::reset
- optional/std::optional::value
- optional/std::optional::value_or
ms.assetid: 89a3b805-ab60-4858-b772-5855130c11b1
ms.openlocfilehash: 414b3e608e915ec06dbdf90726151a1c33ea4c60
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68269202"
---
# <a name="optional-class"></a>Optionale-Klasse

Beschreibt ein Objekt, die möglicherweise keinen Wert enthalten kann.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
class optional
{
    using value_type = T;
};

template<class T> optional(T) -> optional<T>;
```

## <a name="members"></a>Member

### <a name="constructors"></a>Konstruktoren

|||
|-|-|
|[optional](#optional)|Konstruiert ein Objekt vom Typ `optional`.|

### <a name="functions"></a>Funktionen

|||
|-|-|
|[has_value](#has_value)|Gibt **"true"** Wenn `optional` Wert enthält.|
|[reset](#reset)|Setzt die `optional`.|
|[value](#value)|Wertet die `optional` Wert.|
|[value_or](#value_or)|Wertet die `optional` Wert.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[operator=](#op_eq)|Ersetzt die `optional` mit einer Kopie eines anderen `optional`.|
|[operator->](#op_as)|Weisen Sie Wert auf `optional`.|
|[operator*](#op_mem)|Verweisen auf den Arbeitsspeicher der `optional`.|
|[operator bool](#op_bool)|Boolescher Wert, der zurückgegeben `optional` Wert.|

### <a name="has_value"></a> has_value

```cpp
constexpr bool has_value() const noexcept;
```

### <a name="optional"></a> Optionale

Konstruiert ein Objekt vom Typ `optional`. Enthält auch einen Destruktor.

```cpp
constexpr optional() noexcept;
constexpr optional(nullopt_t) noexcept;
constexpr optional(const optional&);
constexpr optional(optional&&) noexcept(see below);

template <class... Args>
    constexpr explicit optional(in_place_t, Args&&...);
template <class U, class... Args>
    constexpr explicit optional(in_place_t, initializer_list<U>, Args&&...);
template <class U = T>
    explicit constexpr optional(U&&);
template <class U>
    explicit optional(const optional<U>&);
template <class U>
    explicit optional(optional<U>&&);

~optional();
```

### <a name="op_eq"></a> Operator =

Ersetzt die `optional` mit einer Kopie eines anderen `optional`.

```cpp
optional& operator=(nullopt_t) noexcept;
optional& operator=(const optional&);
optional& operator=(optional&&) noexcept(see below);

template <class U = T>
    optional& operator=(U&&); template <class U> optional& operator=(const optional<U>&);
template <class U>
    optional& operator=(optional<U>&&); template <class... Args> T& emplace(Args&&...);
template <class U, class... Args>
    T& emplace(initializer_list<U>, Args&&...);
```

### <a name="op_as"></a> Operator ->

```cpp
constexpr const T* operator->() const;
constexpr T* operator->();
```

### <a name="op_mem"></a> Operator *

```cpp
constexpr const T& operator*() const&;
constexpr T& operator*() &;
constexpr T&& operator*() &&;
constexpr const T&& operator*() const&&;
```

### <a name="op_bool"></a> Operator bool

```cpp
constexpr explicit operator bool() const noexcept;
```

### <a name="reset"></a> Zurücksetzen

```cpp
void reset() noexcept;
```

### <a name="value"></a> Wert

```cpp
constexpr const T& value() const&;
constexpr T& value() &;
constexpr T&& value() &&;
constexpr const T&& value() const&&;
```

### <a name="value_or"></a> value_or

```cpp
template <class U>
    constexpr T value_or(U&&) const&;
template <class U>
    constexpr T value_or(U&&) &&;
```
