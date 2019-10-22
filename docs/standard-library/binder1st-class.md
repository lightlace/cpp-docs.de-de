---
title: binder1st-Klasse
ms.date: 02/21/2019
f1_keywords:
- functional/std::binder1st
helpviewer_keywords:
- binder1st class
ms.assetid: 6b8ee343-c82f-48f8-867d-06f9d1d324c0
ms.openlocfilehash: 15b704134d47b7bf7d8857bf380c756b0b03a1b0
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688385"
---
# <a name="binder1st-class"></a>binder1st-Klasse

Eine Klassen Vorlage, die einen Konstruktor bereitstellt, der ein binäres Funktions Objekt in ein unäres Funktions Objekt konvertiert, indem das erste Argument der binären Funktion an einen angegebenen Wert gebunden wird. In c++ 11 als veraltet [markiert und in](functional-functions.md#bind)c++ 17 entfernt.

## <a name="syntax"></a>Syntax

```cpp
template <class Operation>
class binder1st
    : public unaryFunction <typename Operation::second_argument_type,
                             typename Operation::result_type>
{
public:
    typedef typename Operation::argument_type argument_type;
    typedef typename Operation::result_type result_type;
    binder1st(
        const Operation& binary_fn,
        const typename Operation::first_argument_type& left);

    result_type operator()(const argument_type& right) const;
    result_type operator()(const argument_type& right) const;

protected:
    Operation op;
    typename Operation::first_argument_type value;
};
```

### <a name="parameters"></a>Parameter

*binary_fn* \
Das binäre Funktionsobjekt, das in ein unäres Funktionsobjekt konvertiert werden soll.

*Linker* \
Der Wert, an den das erste Argument des binären Funktionsobjekts gebunden werden soll.

*Rechte* \
Der Wert des Arguments, den das angepasste binäre Objekt mit dem festen Wert des zweiten Arguments vergleicht.

## <a name="return-value"></a>Rückgabewert

Das unäre Funktions Objekt, das sich aus der Bindung des ersten Arguments des binären Funktions Objekts an den *linken*Wert ergibt.

## <a name="remarks"></a>Hinweise

Die Klassen Vorlage speichert eine Kopie eines binären Funktions Objekts *binary_fn* in `op` und eine Kopie von *left* in `value`. Er definiert seine Member-Funktion `operator()` als Rückgabe `op(value, right)`.

Wenn *binary_fn* ein Objekt vom Typ `Operation` und `c` eine Konstante ist, ist `bind1st(binary_fn, c)` eine bequemere Entsprechung zu `binder1st<Operation>(binary_fn, c)`. Weitere Informationen finden Sie unter [bind1st](../standard-library/functional-functions.md#bind1st).

## <a name="example"></a>Beispiel

```cpp
// functional_binder1st.cpp
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
        binder1st<less<int> >(less<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1 << "." << endl;

    // Compare use of binder2nd fixing 2nd argument:
    // count the number of integers < 10 in the vector
    vector<int>::iterator::difference_type result2;
    result2 = count_if(v1.begin(), v1.end(),
        binder2nd<less<int> >(less<int>(), 10));
    cout << "The number of elements in v1 less than 10 is: "
         << result2 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
The number of elements in v1 less than 10 is: 2.
```
