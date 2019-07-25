---
title: vector&lt;bool&gt;::reference::operator=
ms.date: 11/04/2016
f1_keywords:
- =
- operator=
- vector<bool>::reference::operator=
- std::vector<bool>::reference::operator=
helpviewer_keywords:
- = operator, with specific C++ Standard Library objects
- reference::operator=
ms.assetid: eed20d81-36b9-40b2-a3b6-340ed0bb4f34
ms.openlocfilehash: 738f86bd6163a827b43d78f29c6e3a7124400fb7
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452161"
---
# <a name="vectorltboolgtreferenceoperator"></a>vector&lt;bool&gt;::reference::operator=

Weist einen booleschen Wert einem Bit zu oder weist den Wert, der in einem Element enthalten ist, auf das verwiesen wird, einem Bit zu.

## <a name="syntax"></a>Syntax

```cpp
reference& operator=(const reference& Right);

reference& operator=(bool Val);
```

### <a name="parameters"></a>Parameter

*Richting*\
Der Elementverweis, dessen Wert dem Bit zugewiesen werden soll.

*Ster*\
Der boolesche Wert, der dem Bit zugewiesen werden soll.

## <a name="example"></a>Beispiel

```cpp
// vector_bool_ref_op_assign.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>
#include <string>

using namespace std;

template <typename C> void print(const string& s, const C& c) {
    cout << s;

    for (const auto& e : c) {
        cout << e << " ";
    }

    cout << endl;
}

int main()
{
    cout << boolalpha;

    vector<bool> vb = { true, false, false, true, true };

    print("The vector is: ", vb);

    // Invoke vector<bool>::reference::operator=()
    vector<bool>::reference refelem1 = vb[0];
    vector<bool>::reference refelem2 = vb[1];
    vector<bool>::reference refelem3 = vb[2];

    bool b1 = refelem1;
    bool b2 = refelem2;
    bool b3 = refelem3;
    cout << "The original value of the 1st element stored in a bool: " << b1 << endl;
    cout << "The original value of the 2nd element stored in a bool: " << b2 << endl;
    cout << "The original value of the 3rd element stored in a bool: " << b3 << endl;
    cout << endl;

    refelem2 = refelem1;

    print("The vector after assigning refelem1 to refelem2 is now: ", vb);

    refelem3 = true;

    print("The vector after assigning false to refelem1 is now: ", vb);

    // The initial values are still stored in the bool variables and remained unchanged
    cout << "The original value of the 1st element still stored in a bool: " << b1 << endl;
    cout << "The original value of the 2nd element still stored in a bool: " << b2 << endl;
    cout << "The original value of the 3rd element still stored in a bool: " << b3 << endl;
    cout << endl;
}
```

## <a name="output"></a>Ausgabe

```Output
The vector is: true false false true true
The original value of the 1st element stored in a bool: true
The original value of the 2nd element stored in a bool: false
The original value of the 3rd element stored in a bool: false

The vector after assigning refelem1 to refelem2 is now: true true false true true
The vector after assigning false to refelem1 is now: true true true true true
The original value of the 1st element still stored in a bool: true
The original value of the 2nd element still stored in a bool: false
The original value of the 3rd element still stored in a bool: false
```

## <a name="requirements"></a>Anforderungen

**Header:** \<vector>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[vector\<bool>::reference-Klasse](../standard-library/vector-bool-reference-class.md)\
[C++ Standard Library Reference (C++-Standardbibliotheksreferenz)](../standard-library/cpp-standard-library-reference.md)
