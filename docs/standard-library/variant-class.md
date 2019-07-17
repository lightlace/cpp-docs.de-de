---
title: Variant-Klasse
ms.date: 04/04/2019
f1_keywords:
- variant/std::variant
- variant/std::variant::emplace
- variant/std::variant::index
- variant/std::variant::valueless_by_exception
helpviewer_keywords:
- variant/std::variant
- variant/std::variant::emplace
- variant/std::variant::index
- variant/std::variant::valueless_by_exception
ms.openlocfilehash: 9bfdf644374a0b825fd0ca02bf4164a766cb42a3
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68269302"
---
# <a name="variant-class"></a>Variant-Klasse

Jede Instanz von Variant-Wert zu jedem Zeitpunkt enthält entweder einen Wert von einem der anderen Typen, oder sie keinen Wert enthält.

## <a name="syntax"></a>Syntax

```cpp
template <class... Types>
    class variant
```

## <a name="members"></a>Member

### <a name="constructors"></a>Konstruktoren

|||
|-|-|
|[Variant](#variant)|Konstruiert ein Objekt vom Typ `variant`.|

### <a name="functions"></a>Funktionen

|||
|-|-|
|[emplace](#emplace)|Erstellt einen neuen enthaltenen Wert.|
|[index](#index)|Gibt den Index eines enthaltenen Werts.|
|[swap](#swap)||
|[valueless_by_exception](#emplace)|Gibt **"false"** , wenn die Variante einen Wert enthält.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[operator=](#op_eq)|Ersetzt die Variante mit einer Kopie einer anderen Variante.|

## <a name="emplace"></a> emplace-

Erstellt einen neuen enthaltenen Wert.

```cpp
template <class T, class... Args>
    T& emplace(Args&&...);
template <class T, class U, class... Args>
    T& emplace(initializer_list<U>, Args&&...);
template <size_t I, class... Args>
    variant_alternative_t<I, variant<Types...>>& emplace(Args&&...);
template <size_t I, class U, class... Args>
    variant_alternative_t<I, variant<Types...>>& emplace(initializer_list<U>, Args&&...);
```

## <a name="index"></a> Index

Gibt den Index eines enthaltenen Werts.

```cpp
constexpr size_t index() const noexcept;
```

## <a name="variant"></a> Variant

Konstruiert ein Objekt vom Typ `variant`. Enthält auch einen Destruktor.

```cpp
constexpr variant() noexcept(see below);
variant(const variant&);
variant(variant&&) noexcept(see below);
template <class T>
    constexpr variant(T&&) noexcept(see below);
template <class T, class... Args>
    constexpr explicit variant(in_place_type_t<T>, Args&&...);
template <class T, class U, class... Args>
    constexpr explicit variant(in_place_type_t<T>, initializer_list<U>, Args&&...);
template <size_t I, class... Args>
    constexpr explicit variant(in_place_index_t<I>, Args&&...);
template <size_t I, class U, class... Args>
    constexpr explicit variant(in_place_index_t<I>, initializer_list<U>, Args&&...);

template <class Alloc>
    variant(allocator_arg_t, const Al&);
template <class Alloc>
    variant(allocator_arg_t, const Al&, const variant&);
template <class Alloc>
    variant(allocator_arg_t, const Al&, variant&&);
template <class Alloc, class T>
    variant(allocator_arg_t, const Al&, T&&);
template <class Alloc, class T, class... Args>
    variant(allocator_arg_t, const Al&, in_place_type_t<T>, Args&&...);
template <class Alloc, class T, class U, class... Args>
    variant(allocator_arg_t, const Al&, in_place_type_t<T>, initializer_list<U>, Args&&...);
template <class Alloc, size_t I, class... Args>
    variant(allocator_arg_t, const Al&, in_place_index_t<I>, Args&&...);
template <class Alloc, size_t I, class U, class... Args>
    variant(allocator_arg_t, const Al&, in_place_index_t<I>, initializer_list<U>, Args&&...);

~variant();
```

### <a name="parameters"></a>Parameter

*Al*\
Die mit diesem Objekt zu verwendende Zuweisungsklasse.

## <a name="op_eq"></a> Operator =

Ersetzt die Variante mit einer Kopie einer anderen Variante.

```cpp
variant& operator=(const variant&);
variant& operator=(variant&&) noexcept(see below);
template <class T>
    variant& operator=(T&&) noexcept(see below);
```

## <a name="swap"></a> Swap

```cpp
void swap(variant&) noexcept(see below);
```

## <a name="valueless"></a> valueless_by_exception

Gibt **"false"** , wenn die Variante einen Wert enthält.

```cpp
constexpr bool valueless_by_exception() const noexcept;
```
