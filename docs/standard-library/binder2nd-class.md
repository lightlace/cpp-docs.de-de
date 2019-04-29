---
title: binder2nd-Klasse
ms.date: 02/21/2019
f1_keywords:
- functional/std::binder2nd
helpviewer_keywords:
- binder2nd class
ms.assetid: b2a9c1d1-dfc4-4ca9-a10e-ae84e195a62d
ms.openlocfilehash: 8c1ed74da939c5f5cc83a2a109d32b43b5ac7f41
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62414047"
---
# <a name="binder2nd-class"></a>binder2nd-Klasse

Eine Vorlagenklasse, mit der ein Konstruktor bereitgestellt wird, der ein binäres Funktionsobjekt in ein unäres Funktionsobjekt konvertiert, indem das zweite Argument der binären Funktion an einen angegebenen Wert gebunden wird. Veraltet in C ++ 11, C ++ 17 entfernt.

## <a name="syntax"></a>Syntax

```cpp
template <class Operation>
class binder2nd
    : public unaryFunction <typename Operation::first_argument_type,
    typename Operation::result_type>
{
public:
    typedef typename Operation::argument_type argument_type;
    typedef typename Operation::result_type result_type;
    binder2nd(
        const Operation& Func,
        const typename Operation::second_argument_type& right);

    result_type operator()(const argument_type& left) const;
    result_type operator()(argument_type& left) const;

protected:
    Operation op;
    typename Operation::second_argument_type value;
};
```

### <a name="parameters"></a>Parameter

*Func*<br/>
Das binäre Funktionsobjekt, das in ein unäres Funktionsobjekt konvertiert werden soll.

*right*<br/>
Der Wert, an den das zweite Argument des binären Funktionsobjekts gebunden werden soll.

*left*<br/>
Der Wert des Arguments, den das angepasste binäre Objekt mit dem festen Wert des zweiten Arguments vergleicht.

## <a name="return-value"></a>Rückgabewert

Das unäre Funktionsobjekt, das Binden des zweiten Arguments des binären Funktionsobjekts an den Wert ergibt *rechten*.

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse speichert eine Kopie eines binären Funktionsobjekts _ *Func* in `op`, sowie eine Kopie der *rechten* in `value`. Für seine Memberfunktion `operator()` definiert sie die Rückgabe **op**( `left`, **value**).

Wenn `Func` ist ein Objekt des Typs `Operation` und c eine Konstante ist, klicken Sie dann [bind2nd](../standard-library/functional-functions.md#bind2nd) ( `Func`, `c` ) entspricht der `binder2nd` Klassenkonstruktor `binder2nd` \<  **Vorgang**> ( `Func`, `c` ) und Benutzerfreundlicher.

## <a name="example"></a>Beispiel

```cpp
// functional_binder2nd.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 5; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( ";
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    // Count the number of integers > 10 in the vector
    vector<int>::iterator::difference_type result1;
    result1 = count_if(v1.begin(), v1.end(),
        binder2nd<greater<int> >(greater<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1 << "." << endl;

    // Compare using binder1st fixing 1st argument:
    // count the number of integers < 10 in the vector
    vector<int>::iterator::difference_type result2;
    result2 = count_if(v1.begin(), v1.end(),
        binder1st<greater<int> >(greater<int>(), 10));
    cout << "The number of elements in v1 less than 10 is: "
         << result2 << "." << endl;
}
/* Output:
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
The number of elements in v1 less than 10 is: 2.
*/
```

## <a name="requirements"></a>Anforderungen

**Header:** \<functional>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
