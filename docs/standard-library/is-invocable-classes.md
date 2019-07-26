---
title: is_invocable-, is_invocable_r-, is_nothrow_invocable-, is_nothrow_invocable_r-Klassen
ms.date: 02/21/2019
f1_keywords:
- type_traits/std::is_invocable
- type_traits/std::is_invocable_r
- type_traits/std::is_nothrow_invocable
- type_traits/std::is_nothrow_invocable_r
helpviewer_keywords:
- is_invocable class
- is_invocable
- is_invocable_r class
- is_invocable_r
- is_nothrow_invocable class
- is_nothrow_invocable
- is_nothrow_invocable_r class
- is_nothrow_invocable_r
ms.openlocfilehash: 20fec55fc3ad1924ee85db3b2f78812e4847f447
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456229"
---
# <a name="isinvocable-isinvocabler-isnothrowinvocable-isnothrowinvocabler-classes"></a>is_invocable-, is_invocable_r-, is_nothrow_invocable-, is_nothrow_invocable_r-Klassen

Diese Vorlagen bestimmen, ob ein Typ mit den angegebenen Argument Typen aufgerufen werden kann. `is_invocable_r`und `is_nothrow_invocable_r` auch bestimmen, ob das Ergebnis des aufzurufenden aufzurufenden in einen bestimmten Typ konvertiert werden kann. `is_nothrow_invocable`und `is_nothrow_invocable_r` legen außerdem fest, ob der Aufruf keine Ausnahmen auslöst. Hinzugefügt in c++ 17.

## <a name="syntax"></a>Syntax

```cpp
template <class Callable, class... Args>
struct is_invocable;

template <class Convertible, class Callable, class... Args>
struct is_invocable_r;

template <class Callable, class... Args>
struct is_nothrow_invocable;

template <class Convertible, class Callable, class... Args>
struct is_nothrow_invocable_r;

// Helper templates
template <class Callable, class... Args>
inline constexpr bool is_invocable_v =
    std::is_invocable<Callable, Args...>::value;

template <class Convertible, class Callable, class... Args>
inline constexpr bool is_invocable_r_v =
    std::is_invocable_r<Convertible, Callable, Args...>::value;

template <class Callable, class... Args>
inline constexpr bool is_nothrow_invocable_v =
    std::is_nothrow_invocable<Callable, Args...>::value;

template <class Convertible, class Callable, class... Args>
inline constexpr bool is_nothrow_invocable_r_v =
    std::is_nothrow_invocable_r<Convertible, Callable, Args...>::value;
```

### <a name="parameters"></a>Parameter

*Callable*\
Der abzufragende, aufgerufene Typ.

*Args*\
Die abzufragende Argument Typen.

*Ver*\
Der Typ, in den das Ergebnis von *Callable* konvertiert werden kann.

## <a name="remarks"></a>Hinweise

Das `is_invocable` typprädikat ist true, wenn der Aufruf Bare Aufruf Bare Typ mithilfe *der Argumente Argumente* in einem nicht ausgewerteten Kontext aufgerufen *werden kann.*

Das `is_invocable_r` typprädikat ist true, wenn der Aufruf Bare Aufruf Bare Typ mithilfe *der Argumente Argumente* in einem nicht ausgewerteten Kontext aufgerufen *werden kann,* um einen Ergebnistyp zu konvertieren, der in *konvertierbar*konvertiert werden kann.

Das `is_nothrow_invocable` typprädikat ist true, wenn der Aufruf Bare Aufruf *Bare* Typ mithilfe *der Argumente Argumente* in einem nicht ausgewerteten Kontext aufgerufen werden kann, und dass ein solcher Aufruf bekanntermaßen keine Ausnahme auslöst.

Das `is_nothrow_invocable_r` typprädikat ist true, wenn der Aufruf Bare Aufruf *Bare* Typ mithilfe *der Argumente Argumente* in einem nicht ausgewerteten Kontext aufgerufen werden kann, um einen Ergebnistyp zu konvertieren, der in *konvertierbar*konvertiert werden kann, und dass ein solcher Aufruf bekanntermaßen nicht ausgelöst wird. eine Ausnahme.

Alle Typen, die *konvertiert, aufgerufen*werden *können*, und die Typen in den Parametern des *Parameter Pakets müssen* ein vollständiger Typ, ein Array mit unbekannter Grenze oder eine möglicherweise CV qualifizierte **void**sein. Andernfalls ist das Verhalten des Prädikats nicht definiert.

## <a name="example"></a>Beispiel

```cpp
// std__type_traits__is_invocable.cpp
// compile using: cl /EHsc /std:c++17 std__type_traits__is_invocable.cpp
#include <type_traits>

auto test1(int) noexcept -> int (*)()
{
    return nullptr;
}

auto test2(int) -> int (*)()
{
    return nullptr;
}

int main()
{
    static_assert( std::is_invocable<decltype(test1), short>::value );

    static_assert( std::is_invocable_r<int(*)(), decltype(test1), int>::value ); 
    static_assert( std::is_invocable_r<long(*)(), decltype(test1), int>::value ); // fails

    static_assert( std::is_nothrow_invocable<decltype(test1), int>::value );
    static_assert( std::is_nothrow_invocable<decltype(test2), int>::value ); // fails

    static_assert( std::is_nothrow_invocable_r<int(*)(), decltype(test1), int>::value );
    static_assert( std::is_nothrow_invocable_r<int(*)(), decltype(test2), int>::value ); // fails
}
```

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)\
[invoke](functional-functions.md#invoke)
