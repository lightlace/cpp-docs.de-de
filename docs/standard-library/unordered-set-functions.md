---
title: '&lt;unordered_set&gt;-Funktionen'
ms.date: 11/04/2016
f1_keywords:
- unordered_set/std::swap (set)
- unordered_set/std::swap (unordered_multiset)
ms.assetid: 66b35671-4023-4411-ad50-83786580d8ee
ms.openlocfilehash: 6b6e764acc9fa3410a44a4a11760933328365852
ms.sourcegitcommit: 8414cd91297dea88c480e208c7b5301db9972f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77257766"
---
# <a name="ltunordered_setgt-functions"></a>&lt;unordered_set&gt;-Funktionen

## <a name="swap"></a>austauschen (unordered_set)

Vertauscht den Inhalt von zwei Containern.

```cpp
template <class Key, class Hash, class Pred, class Alloc>
void swap(
   unordered_set <Key, Hash, Pred, Alloc>& left,
   unordered_set <Key, Hash, Pred, Alloc>& right);
```

### <a name="parameters"></a>Parameter

*Schlüssel*\
Der Schlüsseltyp.

*Hash*\
Der Hashfunktionsobjekttyp.

*Pred-* \
Der Gleichheitsvergleich-Funktionsobjekttyp.

*Zuordnung*\
Die Zuweisungsklasse.

*Linker*\
Der erste zu tauschende Container.

*Rechte*\
Der zweite zu tauschende Container.

### <a name="remarks"></a>Bemerkungen

Die Vorlagenfunktion führt `left.`[unordered_set::swap](../standard-library/unordered-set-class.md#swap)`(right)` aus.

### <a name="example"></a>Beispiel

```cpp
#include <unordered_set>
#include <iostream>

typedef std::unordered_set<char> Myset;
int main()
{
Myset c1;

c1.insert('a');
c1.insert('b');
c1.insert('c');

// display contents " [c] [b] [a]"
for (Myset::const_iterator it = c1.begin();
it != c1.end(); ++it)
std::cout << " [" << *it << "]";
std::cout << std::endl;

Myset c2;

c2.insert('d');
c2.insert('e');
c2.insert('f');

c1.swap(c2);

// display contents " [f] [e] [d]"
for (Myset::const_iterator it = c1.begin();
it != c1.end(); ++it)
std::cout << " [" << *it << "]";
std::cout << std::endl;

swap(c1, c2);

// display contents " [c] [b] [a]"
for (Myset::const_iterator it = c1.begin();
it != c1.end(); ++it)
std::cout << " [" << *it << "]";
std::cout << std::endl;

return (0);
}
```

```Output
[c] [b] [a]
[f] [e] [d]
[c] [b] [a]
```

## <a name="swap_unordered_multiset"></a>austauschen (unordered_multiset)

Vertauscht den Inhalt von zwei Containern.

```cpp
template <class Key, class Hash, class Pred, class Alloc>
void swap(
   unordered_multiset <Key, Hash, Pred, Alloc>& left,
   unordered_multiset <Key, Hash, Pred, Alloc>& right);
```

### <a name="parameters"></a>Parameter

*Schlüssel*\
Der Schlüsseltyp.

*Hash*\
Der Hashfunktionsobjekttyp.

*Pred-* \
Der Gleichheitsvergleich-Funktionsobjekttyp.

*Zuordnung*\
Die Zuweisungsklasse.

*Linker*\
Der erste zu tauschende Container.

*Rechte*\
Der zweite zu tauschende Container.

### <a name="remarks"></a>Bemerkungen

Die Vorlagenfunktion führt `left.`[unordered_multiset::swap](../standard-library/unordered-multiset-class.md#swap)`(right)` aus.

### <a name="example"></a>Beispiel

```cpp
// std__unordered_set__u_ms_swap.cpp
// compile with: /EHsc
#include <unordered_set>
#include <iostream>

typedef std::unordered_multiset<char> Myset;
int main()
{
    Myset c1;

    c1.insert('a');
    c1.insert('b');
    c1.insert('c');

    // display contents " [c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << *it << "]";
    std::cout << std::endl;

    Myset c2;

    c2.insert('d');
    c2.insert('e');
    c2.insert('f');

    c1.swap(c2);

    // display contents " [f] [e] [d]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << *it << "]";
    std::cout << std::endl;

    swap(c1, c2);

    // display contents " [c] [b] [a]"
    for (Myset::const_iterator it = c1.begin();
        it != c1.end(); ++it)
        std::cout << " [" << *it << "]";
    std::cout << std::endl;

    return (0);
}
```

```Output
[c] [b] [a]
[f] [e] [d]
[c] [b] [a]
```
