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
ms.openlocfilehash: d9c4bf5356e6ff163ecdf7e1a80bc55453d59003
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689150"
---
# <a name="optional-class"></a>optionale Klasse

Die Klassen Vorlage `optional<T>` beschreibt ein Objekt, das einen Wert vom Typ `T`enthalten kann, der als *enthaltener Wert*bezeichnet wird.

Wenn eine Instanz von `optional<T>` einen Wert enthält, wird der enthaltene Wert im Speicher des `optional` Objekts in einem Bereich zugeordnet, der für den Typ `T`entsprechend ausgerichtet ist. Wenn eine `optional<T>` in `bool`konvertiert wird, wird das Ergebnis `true`, wenn das Objekt einen Wert enthält. Andernfalls ist es `false`.

Der enthaltene Objekttyp `T` darf nicht [in_place_t](in-place-t-struct.md) oder [nullopt_t](nullopt-t-structure.md)sein. `T` muss dekonstruiert werden, d. h *., der*Dekonstruktor muss alle im Besitz befindlichen Ressourcen freigeben und kann keine Ausnahmen auslösen.

Die `optional`-Klasse ist neu in c++ 17.

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
| [swap](#swap) | Vertauscht den enthaltenen Wert oder den leeren Zustand mit einem anderen `optional`. |
| **Ent** | |
| [has_value](#has_value) | Gibt zurück, ob ein `optional`-Objekt einen Wert enthält. |
| [Wert](#value) | Gibt den enthaltenen Wert zurück. |
| [value_or](#value_or) | Gibt den enthaltenen Wert oder eine Alternative zurück, wenn kein Wert vorhanden ist. |
| [operator->](#op_as) | Verweist auf den enthaltenen Wert eines `optional` Objekts. |
| [operator*](#op_mem) | Verweist auf den enthaltenen Wert eines `optional` Objekts. |
| [operator bool](#op_bool) | Gibt zurück, ob ein `optional`-Objekt einen Wert enthält. |
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

*RHS* -\
Das `optional`, das kopiert oder verschoben werden soll, aus dem enthaltenen Wert.

*I_list*\
Die Initialisiererliste, aus der der enthaltene Wert erstellt werden soll.

*args*\
Die Argumentliste, aus der der enthaltene Wert erstellt werden soll.

### <a name="remarks"></a>Hinweise

`constexpr optional() noexcept;`
`constexpr optional(nullopt_t nullopt) noexcept;` diese Konstruktoren ein `optional` erstellen, das keinen Wert enthält.

`constexpr optional(const optional& rhs);` der Kopierkonstruktor den enthaltenen Wert aus dem enthaltenen Wert des Arguments initialisiert. Es ist als **gelöscht** definiert, es sei denn, `is_copy_constructible_v<T>` ist true, und es ist trivial, wenn `is_trivially_copy_constructible_v<T>` true ist.

`constexpr optional(optional&& rhs) noexcept;` der bewegungskonstruktor den enthaltenen Wert initialisiert, indem er vom enthaltenen Wert des Arguments bewegt wird. Es ist nicht an der Überladungs Auflösung beteiligt, es sei denn, `is_move_constructible_v<T>` ist true, und es ist trivial, wenn `is_trivially_move_constructible_v<T>` true ist.

`template <class... Args> constexpr explicit optional(in_place_t, Args&&... args);` Direct initialisiert den enthaltenen Wert als, wenn die Argumente `std::forward<Args>(args)`verwendet werden. Dieser Konstruktor ist `constexpr`, wenn der verwendete `T` Konstruktor `constexpr`ist. Es ist nicht an der Überladungs Auflösung beteiligt, es sei denn, `is_constructible_v<T, Args...>` true

`template <class U, class... Args> constexpr explicit optional(in_place_t, initializer_list<U> i_list, Args&&... args);` Direct initialisiert den enthaltenen Wert als, wenn die Argumente `i_list, std::forward<Args>(args)`verwendet werden. Dieser Konstruktor ist `constexpr`, wenn der verwendete `T` Konstruktor `constexpr`ist. Es ist nicht an der Überladungs Auflösung beteiligt, es sei denn, `is_constructible_v<T, initializer_list<U>&, Args&&...>` true

`template <class U = T> explicit constexpr optional(U&& rhs);` Direct initialisiert den enthaltenen Wert so, als ob er `std::forward<U>(v)`verwendet. Dieser Konstruktor ist `constexpr`, wenn der verwendete `T` Konstruktor `constexpr`ist. Sie ist nicht an der Überladungs Auflösung beteiligt, es sei denn, `is_constructible_v<T, U&&>` ist true, und `is_same_v<remove_cvref_t<U>, in_place_t>` und `is_same_v<remove_cvref_t<U>, optional>` sind false.

`template <class U> explicit optional(const optional<U>& rhs);` Wenn *RHS* einen Wert enthält, initialisiert Direct den enthaltenen Wert aus dem enthaltenen Wert des Arguments. Sie ist nicht an der Überladungs Auflösung beteiligt, es sei denn, `is_constructible_v<T, const U&>` ist true, und `is_constructible_v<T, optional<U>&>`, `is_constructible_v<T, optional<U>&&>`, `is_constructible_v<T, const optional<U>&>`, `is_constructible_v<T, const optional<U>&&>`, `is_convertible_v<optional<U>&, T>`, `is_convertible_v<optional<U>&&, T>`, `is_convertible_v<const optional<U>&, T>`und `is_convertible_v<const optional<U>&&, T>` sind alle falsch.

`template <class U> explicit optional(optional<U>&& rhs);` Wenn *RHS* einen Wert enthält, initialisiert Direct den enthaltenen Wert so, als ob er `std::move(*rhs)`verwendet. Sie ist nicht an der Überladungs Auflösung beteiligt, es sei denn, `is_constructible_v<T, U&&>` ist true, und `is_constructible_v<T, optional<U>&>`, `is_constructible_v<T, optional<U>&&>`, `is_constructible_v<T, const optional<U>&>`, `is_constructible_v<T, const optional<U>&&>`, `is_convertible_v<optional<U>&, T>`, `is_convertible_v<optional<U>&&, T>`, `is_convertible_v<const optional<U>&, T>`und `is_convertible_v<const optional<U>&&, T>` sind alle falsch.

## <a name="optional-destructor"></a>~ Optionaler Dekonstruktor

Zerstört alle nicht triviell deerbaren enthaltenen Werte, sofern vorhanden, durch Aufrufen des Dekonstruktors.

```cpp
~optional();
```

### <a name="remarks"></a>Hinweise

Wenn `T` trivial zerstört werden kann, ist `optional<T>` auch trivial zerstörbar.

## <a name="op_eq"></a>Operator =

Ersetzt den enthaltenen Wert eines `optional` durch einen Kopier-oder verschiebe Vorgang von einem anderen `optional` enthaltenen Wert.

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

Meldet, ob das `optional` Objekt über einen enthaltenen Wert verfügt.

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

[\<optional >](optional.md)
