---
title: optionale Klasse
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
ms.openlocfilehash: f664df6493a7ee20361d49531a930aeb810d3d2a
ms.sourcegitcommit: 16c0392fc8d96e814c3a40b0c5346d7389aeb525
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/12/2019
ms.locfileid: "68957149"
---
# <a name="optional-class"></a>optionale Klasse

Die Vorlagen Klasse `optional<T>` beschreibt ein Objekt, das möglicherweise einen Wert vom Typ `T`enthält, der als *enthaltener Wert*bezeichnet wird.

Wenn eine Instanz von `optional<T>` einen Wert enthält, wird der enthaltene Wert innerhalb der Speicherung des Objekts in `optional` einem Bereich zugeordnet, der für den Typ `T`entsprechend ausgerichtet ist. Wenn ein `optional<T>` `bool`in konvertiert wird, ist `true` das Ergebnis, wenn das-Objekt einen- `false`Wert enthält, andernfalls.

Der enthaltene Objekttyp `T` darf nicht [in_place_t](in-place-t-struct.md) oder [nullopt_t](nullopt-t-structure.md)sein. `T`muss dekonstruiert werden können, d. h., der Dekonstruktor muss alle eigenen Ressourcen freigeben und kann keine Ausnahmen auslösen.

Die `optional` -Klasse ist neu in c++ 17.

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
| **Konstruktoren und Dekonstruktor** | |
|[optional](#optional) | Konstruiert ein Objekt vom Typ `optional`. |
|[~ optional](#optional-destructor) | Zerstört ein Objekt vom Typ `optional`. |
| **Zuweisung** | |
| [operator=](#op_eq) | Ersetzt den `optional` durch eine Kopie eines anderen `optional`. |
| [emplace](#op_eq) | Initialisiert den enthaltenen Wert mit den angegebenen Argumenten. |
| **Swap** | |
| [swap](#swap) | Vertauscht den enthaltenen Wert oder den leeren Zustand mit `optional`einem anderen. |
| **Ent** | |
| [has_value](#has_value) | Gibt zurück, `optional` ob ein-Objekt einen Wert enthält. |
| [value](#value) | Gibt den enthaltenen Wert zurück. |
| [value_or](#value_or) | Gibt den enthaltenen Wert oder eine Alternative zurück, wenn kein Wert vorhanden ist. |
| [operator->](#op_as) | Verweist auf den enthaltenen Wert eines `optional` Objekts. |
| [operator*](#op_mem) | Verweist auf den enthaltenen Wert eines `optional` Objekts. |
| [operator bool](#op_bool) | Gibt zurück, `optional` ob ein-Objekt einen Wert enthält. |
| **Modifizierer** | |
| [reset](#reset) | Setzt den `optional` zurück, indem alle enthaltenen Werte zerstört werden. |

## <a name="has_value"></a>has_value

```cpp
constexpr bool has_value() const noexcept;
```

## <a name="optional"></a>Optionaler Konstruktor

Konstruiert ein Objekt vom Typ `optional`.

```cpp
constexpr optional() noexcept;
constexpr optional(nullopt_t nullopt) noexcept;
constexpr optional(const optional& rhs);
constexpr optional(optional&& rhs) noexcept;

template <class... Args>
constexpr explicit optional(in_place_t, Args&&... args);

template <class U, class... Args>
constexpr explicit optional(in_place_t, initializer_list<U> i_list, Args&&... args);

template <class U = T>
explicit constexpr optional(U&& rhs);

template <class U>
explicit optional(const optional<U>& rhs);

template <class U>
explicit optional(optional<U>&& rhs);
```

### <a name="parameters"></a>Parameter

*RHS*\
Beim `optional` kopieren oder Verschieben von wird der enthaltene Wert aus erstellt.

*i_list*\
Die Initialisiererliste, aus der der enthaltene Wert erstellt werden soll.

*args*\
Die Argumentliste, aus der der enthaltene Wert erstellt werden soll.

### <a name="remarks"></a>Hinweise

`constexpr optional() noexcept;`
`constexpr optional(nullopt_t nullopt) noexcept;`Diese Konstruktoren erstellen einen `optional` , der keinen Wert enthält.

`constexpr optional(const optional& rhs);`Der Kopierkonstruktor Initialisiert den enthaltenen Wert aus dem enthaltenen Wert des Arguments. Es ist als **gelöscht** definiert, `is_copy_constructible_v<T>` es sei denn, ist true, und `is_trivially_copy_constructible_v<T>` es ist trivial, wenn true ist.

`constexpr optional(optional&& rhs) noexcept;`Mit dem bewegungskonstruktor wird der enthaltene Wert initialisiert, indem vom enthaltenen Wert des Arguments gewechselt wird. Es ist nicht an der Überladungs `is_move_constructible_v<T>` Auflösung beteiligt, es sei denn, ist `is_trivially_move_constructible_v<T>` true, und es ist trivial, wenn true ist

`template <class... Args> constexpr explicit optional(in_place_t, Args&&... args);`Direct initialisiert den enthaltenen Wert als, wenn die Argumente `std::forward<Args>(args)`verwendet werden. Dieser Konstruktor ist `constexpr` , wenn `T` der verwendete Konstruktor `constexpr`ist. Es ist nicht an der Überladungs `is_constructible_v<T, Args...>` Auflösung beteiligt, es sei denn, ist

`template <class U, class... Args> constexpr explicit optional(in_place_t, initializer_list<U> i_list, Args&&... args);`Direct initialisiert den enthaltenen Wert als, wenn die Argumente `i_list, std::forward<Args>(args)`verwendet werden. Dieser Konstruktor ist `constexpr` , wenn `T` der verwendete Konstruktor `constexpr`ist. Es ist nicht an der Überladungs `is_constructible_v<T, initializer_list<U>&, Args&&...>` Auflösung beteiligt, es sei denn, ist

`template <class U = T> explicit constexpr optional(U&& rhs);`Direct initialisiert den enthaltenen Wert als, wenn `std::forward<U>(v)`verwendet wird. Dieser Konstruktor ist `constexpr` , wenn `T` der verwendete Konstruktor `constexpr`ist. Sie ist nicht an der Überladungs `is_constructible_v<T, U&&>` Auflösung beteiligt, es `is_same_v<remove_cvref_t<U>, in_place_t>` sei `is_same_v<remove_cvref_t<U>, optional>` denn, ist true, und und sind false.

`template <class U> explicit optional(const optional<U>& rhs);`Wenn *RHS* einen Wert enthält, initialisiert Direct den enthaltenen Wert aus dem enthaltenen Wert des Arguments. Sie ist nicht an der Überladungs `is_constructible_v<T, const U&>` Auflösung beteiligt, es sei denn `is_constructible_v<T, const optional<U>&>`, `is_constructible_v<T, const optional<U>&&>`ist `is_convertible_v<optional<U>&, T>`true `is_convertible_v<optional<U>&&, T>`, `is_convertible_v<const optional<U>&, T>`und `is_constructible_v<T, optional<U>&>`, `is_convertible_v<const optional<U>&&, T>` `is_constructible_v<T, optional<U>&&>`,,,,, und sind alle false.

`template <class U> explicit optional(optional<U>&& rhs);`Wenn *RHS* einen Wert enthält, initialisiert Direct den enthaltenen Wert wie bei Verwendung `std::move(*rhs)`von. Sie ist nicht an der Überladungs `is_constructible_v<T, U&&>` Auflösung beteiligt, es sei denn `is_constructible_v<T, const optional<U>&>`, `is_constructible_v<T, const optional<U>&&>`ist `is_convertible_v<optional<U>&, T>`true `is_convertible_v<optional<U>&&, T>`, `is_convertible_v<const optional<U>&, T>`und `is_constructible_v<T, optional<U>&>`, `is_convertible_v<const optional<U>&&, T>` `is_constructible_v<T, optional<U>&&>`,,,,, und sind alle false.

## <a name="optional-destructor"></a>~ Optionaler Dekonstruktor

Zerstört alle nicht triviell deerbaren enthaltenen Werte, sofern vorhanden, durch Aufrufen des Dekonstruktors.

```cpp
~optional();
```

### <a name="remarks"></a>Hinweise

Wenn `T` triviell deierbar ist `optional<T>` , ist auch trivial deierbar.

## <a name="op_eq"></a>Operator =

Ersetzt den enthaltenen Wert eines `optional` durch ein Kopieren oder Verschieben aus einem anderen `optional` enthaltenen Wert.

```cpp
optional& operator=(nullopt_t) noexcept;
optional& operator=(const optional& rhs);
optional& operator=(optional&&) noexcept( /* see below */ );

template <class U = T>
    optional& operator=(U&&);

template <class U>
optional& operator=(const optional<U>&);

template <class U>
    optional& operator=(optional<U>&&);

template <class... Args>
T& emplace(Args&&...);

template <class U, class... Args>
T& emplace(initializer_list<U>, Args&&...);
```

## <a name="op_as"></a>Operator->

Dereferenziert den enthaltenen Wert eines `optional` Objekts.

```cpp
constexpr const T* operator->() const;
constexpr T* operator->();
```

## <a name="op_mem"></a>KOM

Dereferenziert den enthaltenen Wert eines `optional` Objekts.

```cpp
constexpr const T& operator*() const&;
constexpr T& operator*() &;
constexpr T&& operator*() &&;
constexpr const T&& operator*() const&&;
```

## <a name="op_bool"></a>Operator bool

Meldet, ob `optional` das Objekt über einen enthaltenen Wert verfügt.

```cpp
constexpr explicit operator bool() const noexcept;
```

## <a name="reset"></a>Festlegen

Effektiv ruft den Dekonstruktor des enthaltenen Objekts auf, sofern vorhanden, und legt ihn auf einen nicht initialisierten Zustand fest.

```cpp
void reset() noexcept;
```

## <a name="swap"></a>Wechsel

```cpp
template<class T>
void swap(optional<T>&, optional<T>&) noexcept;
```

## <a name="value"></a>Wert

```cpp
constexpr const T& value() const&;
constexpr T& value() &;
constexpr T&& value() &&;
constexpr const T&& value() const&&;
```

## <a name="value_or"></a>value_or

```cpp
template <class U>
    constexpr T value_or(U&&) const&;
template <class U>
    constexpr T value_or(U&&) &&;
```

## <a name="see-also"></a>Siehe auch

[\<optionale >](optional.md)
