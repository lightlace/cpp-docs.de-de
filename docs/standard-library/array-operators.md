---
title: '&lt;array&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- array/std::array::operator!=
- array/std::array::operator<
- array/std::array::operator<=
- array/std::array::operator>
- array/std::array::operator>=
- array/std::array::operator==
dev_langs:
- C++
ms.assetid: c8f46282-f179-4909-9a01-639cb8e18c27
ms.openlocfilehash: 4c4db60d3573629447bbf675c408586feec61f12
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107122"
---
# <a name="ltarraygt-operators"></a>&lt;array&gt;-Operatoren

Die \<Array >-Header enthält diese **Array** nicht-Member den vorlagenvergleich.

||||
|-|-|-|
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[operator&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a> operator!=

Array-Vergleich, ungleich.

```cpp
template <Ty, std::size_t N>
bool operator!=(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>Parameter

*Ty*<br/>
Der Typ eines Elements.

*N*<br/>
Die Größe des Arrays.

*left*<br/>
Linker zu vergleichender Container.

*right*<br/>
Rechter zu vergleichender Container.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion gibt `!(left == right)` zurück.

### <a name="example"></a>Beispiel

```cpp
// std__array__operator_ne.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1 = {4, 5, 6, 7};

// display contents " 4 5 6 7"
    for (Myarray::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 != c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c0 != c1);
    std::cout << std::endl;

    return (0);
    }
```

```Output
0 1 2 3
4 5 6 7
false
true
```

## <a name="op_lt"></a> operator&lt;

Array-Vergleich, kleiner als.

```cpp
template <Ty, std::size_t N>
bool operator<(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>Parameter

*Ty*<br/>
Der Typ eines Elements.

*N*<br/>
Die Größe des Arrays.

*left*<br/>
Linker zu vergleichender Container.

*right*<br/>
Rechter zu vergleichender Container.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion überlädt `operator<`, um zwei Objekte der Vorlagenklasse [Array-Klasse](../standard-library/array-class-stl.md) zu vergleichen. Die Funktion gibt `lexicographical_compare(left.begin(), left.end(), right.begin())` zurück.

### <a name="example"></a>Beispiel

```cpp
// std__array__operator_lt.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1 = {4, 5, 6, 7};

// display contents " 4 5 6 7"
    for (Myarray::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 < c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c0 < c1);
    std::cout << std::endl;

    return (0);
    }

```

```Output
0 1 2 3
4 5 6 7
false
true
```

## <a name="op_lt_eq"></a> operator&lt;=

Array-Vergleich, kleiner als oder gleich.

```cpp
template <Ty, std::size_t N>
bool operator<=(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>Parameter

*Ty*<br/>
Der Typ eines Elements.

*N*<br/>
Die Größe des Arrays.

*left*<br/>
Linker zu vergleichender Container.

*right*<br/>
Rechter zu vergleichender Container.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion gibt `!(right < left)` zurück.

### <a name="example"></a>Beispiel

```cpp
// std__array__operator_le.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1 = {4, 5, 6, 7};

// display contents " 4 5 6 7"
    for (Myarray::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 <= c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c1 <= c0);
    std::cout << std::endl;

    return (0);
    }

```

```Output
0 1 2 3
4 5 6 7
true
false
```

## <a name="op_eq_eq"></a> operator==

Array-Vergleich, gleich.

```cpp
template <Ty, std::size_t N>
bool operator==(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>Parameter

*Ty*<br/>
Der Typ eines Elements.

*N*<br/>
Die Größe des Arrays.

*left*<br/>
Linker zu vergleichender Container.

*right*<br/>
Rechter zu vergleichender Container.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion überlädt `operator==`, um zwei Objekte der Vorlagenklasse [Array-Klasse](../standard-library/array-class-stl.md) zu vergleichen. Die Funktion gibt `equal(left.begin(), left.end(), right.begin())` zurück.

### <a name="example"></a>Beispiel

```cpp
// std__array__operator_eq.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1 = {4, 5, 6, 7};

// display contents " 4 5 6 7"
    for (Myarray::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 == c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c0 == c1);
    std::cout << std::endl;

    return (0);
    }

```

```Output
0 1 2 3
4 5 6 7
true
false
```

## <a name="op_gt"></a> operator&gt;

Array-Vergleich, größer als.

```cpp
template <Ty, std::size_t N>
bool operator>(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>Parameter

*Ty*<br/>
Der Typ eines Elements.

*N*<br/>
Die Größe des Arrays.

*left*<br/>
Linker zu vergleichender Container.

*right*<br/>
Rechter zu vergleichender Container.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion gibt `(right < left)` zurück.

### <a name="example"></a>Beispiel

```cpp
// std__array__operator_gt.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1 = {4, 5, 6, 7};

// display contents " 4 5 6 7"
    for (Myarray::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 > c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c1 > c0);
    std::cout << std::endl;

    return (0);
    }

```

```Output
0 1 2 3
4 5 6 7
false
true
```

## <a name="op_gt_eq"></a> operator&gt;=

Array-Vergleich, größer als oder gleich.

```cpp
template <Ty, std::size_t N>
bool operator>=(
    const array<Ty, N>& left,
    const array<Ty, N>& right);
```

### <a name="parameters"></a>Parameter

*Ty*<br/>
Der Typ eines Elements.

*N*<br/>
Die Größe des Arrays.

*left*<br/>
Linker zu vergleichender Container.

*right*<br/>
Rechter zu vergleichender Container.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion gibt `!(left < right)` zurück.

### <a name="example"></a>Beispiel

```cpp
// std__array__operator_ge.cpp
// compile with: /EHsc
#include <array>
#include <iostream>

typedef std::array<int, 4> Myarray;
int main()
    {
    Myarray c0 = {0, 1, 2, 3};

// display contents " 0 1 2 3"
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1 = {4, 5, 6, 7};

// display contents " 4 5 6 7"
    for (Myarray::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 >= c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c0 >= c1);
    std::cout << std::endl;

    return (0);
    }

```

```Output
0 1 2 3
4 5 6 7
true
false
```

## <a name="see-also"></a>Siehe auch

[\<array>](../standard-library/array.md)<br/>
