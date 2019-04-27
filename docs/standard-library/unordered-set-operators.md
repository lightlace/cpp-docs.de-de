---
title: '&lt;unordered_set&gt;-Operatoren'
ms.date: 11/04/2016
f1_keywords:
- unordered_set/std::operator!=
- unordered_set/std::operator==
ms.assetid: 8653eea6-12f2-4dd7-aa2f-db38a71599a0
ms.openlocfilehash: b86dd81a7bc4085c86e87d5d81b59e795ce7ae8a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62185918"
---
# <a name="ltunorderedsetgt-operators"></a>&lt;unordered_set&gt;-Operatoren

|||||
|-|-|-|-|
|[Operator!=](#op_neq)|[operator==](#op_eq_eq)|[Operator!=](#op_neq_unordered_multiset)|[operator==](#op_eq_eq_unordered_multiset)|

## <a name="op_neq"></a> operator!=

Testet, ob das [unordered_set](../standard-library/unordered-set-class.md)-Objekt links vom Operator ungleich dem unordered_set-Objekt rechts vom Operator ist.

```cpp
bool operator!=(const unordered_set <Key, Hash, Pred, Allocator>& left, const unordered_set <Key, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `unordered_set`.

*right*<br/>
Ein Objekt vom Typ `unordered_set`.

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn die unordered_set-Objekte ungleich sind; **"false"** ob diese gleich sind.

### <a name="remarks"></a>Hinweise

Die beliebige Reihenfolge, in der unordered_set-Objekte ihre Elemente speichern, hat keine Auswirkungen auf den Vergleich der Objekte. Zwei unordered_set-Objekte sind gleich, wenn sie dieselbe Anzahl von Elementen aufweisen und die Elemente in einem Container eine Permutation der Elemente im anderen Container sind. Andernfalls sind sie ungleich.

### <a name="example"></a>Beispiel

```cpp
// unordered_set_ne.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_set>
#include <iostream>
#include <ios>

int main()
{
    using namespace std;

    unordered_set<char> c1, c2, c3;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    c2.insert('c');
    c2.insert('a');
    c2.insert('d');

    c3.insert('c');
    c3.insert('a');
    c3.insert('b');

   cout << boolalpha;
   cout << "c1 != c2: " << (c1 != c2) << endl;
   cout << "c1 != c3: " << (c1 != c3) << endl;
   cout << "c2 != c3: " << (c2 != c3) << endl;

    return (0);
}
```

**Ausgabe:**

`c1 != c2: true`

`c1 != c3: false`

`c2 != c3: true`

## <a name="op_eq_eq"></a> operator==

Testet, ob das [unordered_set](../standard-library/unordered-set-class.md)-Objekt links vom Operator gleich dem unordered_set-Objekt rechts vom Operator ist.

```cpp
bool operator==(const unordered_set <Key, Hash, Pred, Allocator>& left, const unordered_set <Key, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `unordered_set`.

*right*<br/>
Ein Objekt vom Typ `unordered_set`.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn die unordered_set-Objekte gleich sind; **"false"** , wenn sie nicht gleich sind.

### <a name="remarks"></a>Hinweise

Die beliebige Reihenfolge, in der unordered_set-Objekte ihre Elemente speichern, hat keine Auswirkungen auf den Vergleich der Objekte. Zwei unordered_set-Objekte sind gleich, wenn sie dieselbe Anzahl von Elementen aufweisen und die Elemente in einem Container eine Permutation der Elemente im anderen Container sind. Andernfalls sind sie ungleich.

### <a name="example"></a>Beispiel

```cpp
// unordered_set_eq.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_set>
#include <iostream>
#include <ios>

int main()
{
    using namespace std;

    unordered_set<char> c1, c2, c3;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    c2.insert('c');
    c2.insert('a');
    c2.insert('d');

    c3.insert('c');
    c3.insert('a');
    c3.insert('b');

   cout << boolalpha;
   cout << "c1 == c2: " << (c1 == c2) << endl;
   cout << "c1 == c3: " << (c1 == c3) << endl;
   cout << "c2 == c3: " << (c2 == c3) << endl;

    return (0);
}
```

**Ausgabe:**

`c1 == c2: false`

`c1 == c3: true`

`c2 == c3: false`

## <a name="op_neq_unordered_multiset"></a> operator!=

Überprüft, ob das [unordered_multiset](../standard-library/unordered-multiset-class.md)-Objekt links vom Operator ungleich dem unordered_multiset-Objekt rechts vom Operator ist.

```cpp
bool operator!=(const unordered_multiset <Key, Hash, Pred, Allocator>& left, const unordered_multiset <Key, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `unordered_multiset`.

*right*<br/>
Ein Objekt vom Typ `unordered_multiset`.

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn die unordered_multiset-Objekte ungleich sind; **"false"** ob diese gleich sind.

### <a name="remarks"></a>Hinweise

Die beliebige Reihenfolge, in der unordered_multiset-Objekte ihre Elemente speichern, hat keine Auswirkungen auf den Vergleich der Objekte. Zwei unordered_multiset-Objekte sind gleich, wenn sie dieselbe Anzahl von Elementen aufweisen und die Elemente in einem Container eine Permutation der Elemente im anderen Container sind. Andernfalls sind sie ungleich.

### <a name="example"></a>Beispiel

```cpp
// unordered_multiset_ne.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_set>
#include <iostream>
#include <ios>

int main()
{
    using namespace std;

    unordered_multiset<char> c1, c2, c3;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');
    c1.insert('c');

    c2.insert('c');
    c2.insert('c');
    c2.insert('a');
    c2.insert('d');

    c3.insert('c');
    c3.insert('c');
    c3.insert('a');
    c3.insert('b');

   cout << boolalpha;
   cout << "c1 != c2: " << (c1 != c2) << endl;
   cout << "c1 != c3: " << (c1 != c3) << endl;
   cout << "c2 != c3: " << (c2 != c3) << endl;

    return (0);
}
```

**Ausgabe:**

`c1 != c2: true`

`c1 != c3: false`

`c2 != c3: true`

## <a name="op_eq_eq_unordered_multiset"></a> operator==

Überprüft, ob das [unordered_multiset](../standard-library/unordered-multiset-class.md)-Objekt links vom Operator gleich dem unordered_multiset-Objekt rechts vom Operator ist.

```cpp
bool operator==(const unordered_multiset <Key, Hash, Pred, Allocator>& left, const unordered_multiset <Key, Hash, Pred, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `unordered_multiset`.

*right*<br/>
Ein Objekt vom Typ `unordered_multiset`.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn die unordered_multiset-Objekte gleich sind; **"false"** , wenn sie nicht gleich sind.

### <a name="remarks"></a>Hinweise

Die beliebige Reihenfolge, in der unordered_multiset-Objekte ihre Elemente speichern, hat keine Auswirkungen auf den Vergleich der Objekte. Zwei unordered_multiset-Objekte sind gleich, wenn sie dieselbe Anzahl von Elementen aufweisen und die Elemente in einem Container eine Permutation der Elemente im anderen Container sind. Andernfalls sind sie ungleich.

### <a name="example"></a>Beispiel

```cpp
// unordered_multiset_eq.cpp
// compile by using: cl.exe /EHsc /nologo /W4 /MTd
#include <unordered_set>
#include <iostream>
#include <ios>

int main()
{
    using namespace std;

    unordered_multiset<char> c1, c2, c3;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');
    c1.insert('c');

    c2.insert('c');
    c2.insert('c');
    c2.insert('a');
    c2.insert('d');

    c3.insert('c');
    c3.insert('c');
    c3.insert('a');
    c3.insert('b');

   cout << boolalpha;
   cout << "c1 == c2: " << (c1 == c2) << endl;
   cout << "c1 == c3: " << (c1 == c3) << endl;
   cout << "c2 == c3: " << (c2 == c3) << endl;

    return (0);
}
```

**Ausgabe:**

`c1 == c2: false`

`c1 == c3: true`

`c2 == c3: false`

## <a name="see-also"></a>Siehe auch

[<unordered_set>](../standard-library/unordered-set.md)<br/>
