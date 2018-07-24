---
title: '&lt;functional&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- functional/std::bind
- xfunctional/std::bind1st
- xfunctional/std::bind2nd
- xfunctional/std::bit_and
- xfunctional/std::bit_not
- xfunctional/std::bit_or
- xfunctional/std::bit_xor
- functional/std::cref
- type_traits/std::cref
- xfunctional/std::mem_fn
- xfunctional/std::mem_fun_ref
- xfunctional/std::not1
- xfunctional/std::not2
- xfunctional/std::ptr_fun
- functional/std::ref
- functional/std::swap
dev_langs:
- C++
helpviewer_keywords:
- std::bind [C++]
- std::bind1st
- std::bind2nd
- std::bit_and [C++]
- std::bit_not [C++]
- std::bit_or [C++]
- std::bit_xor [C++]
- std::cref [C++]
ms.assetid: c34d0b45-50a7-447a-9368-2210d06339a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8a2b776fb155d8927b610de38bdd79370f4c0803
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2018
ms.locfileid: "39208649"
---
# <a name="ltfunctionalgt-functions"></a>&lt;functional&gt;-Funktionen

||||
|-|-|-|
|[bind](#bind)|[bind1st](#bind1st)|[bind2nd](#bind2nd)|
|[bit_and](#bit_and)|[bit_not](#bit_not)|[bit_or](#bit_or)|
|[bit_xor](#bit_xor)|[cref](#cref)|[mem_fn](#mem_fn)|
|[mem_fun](#mem_fun)|[mem_fun_ref](#mem_fun_ref)|[not1](#not1)|
|[not2](#not2)|[ptr_fun](#ptr_fun)|[ref](#ref)|
|[swap](#swap)|

## <a name="bind"></a> bind

Bindet Argumente an ein aufrufbares Objekt.

```cpp
template <class Fty, class T1, class T2, ..., class TN>
unspecified bind(Fty fn, T1 t1, T2 t2, ..., TN tN);

template <class Ret, class Fty, class T1, class T2, ..., class TN>
unspecified bind(Fty fn, T1 t1, T2 t2, ..., TN tN);
```

### <a name="parameters"></a>Parameter

*Fty* den Typ des aufzurufenden Objekts.

*TN* den Typ des der n-te Aufrufargument.

*fn* aufzurufenden Objekts.

*tN* der n-te Aufrufargument.

### <a name="remarks"></a>Hinweise

Die Typen `Fty, T1, T2, ..., TN` müssen über eine Kopie erstellbar sein, und `INVOKE(fn, t1, ..., tN)` muss ein gültiger Ausdruck für einige `w1, w2, ..., wN`-Werte sein.

Die erste Vorlagenfunktion gibt einen weiterleitenden Aufrufwrapper `g` mit einem schwachen Ergebnistyp zurück. Die Auswirkungen der `g(u1, u2, ..., uM)` ist `INVOKE(f, v1, v2, ..., vN, ` [Result_of](../standard-library/result-of-class.md)`<Fty cv (V1, V2, ..., VN)>::type)`, wobei `cv` ist der cv-Qualifizierer von `g` und die Werte und die Typen der gebundenen Argumente `v1, v2, ..., vN` wie bestimmt werden unten angegeben. Damit binden Sie Argumente an aufrufbare Objekte, um aufrufbare Objekte mit einer angepassten Argumentliste zu erhalten.

Die zweite Vorlagenfunktion gibt einen weiterleitenden Aufrufwrapper `g` mit einem geschachtelten Typ `result_type` zurück, der ein Synonym für `Ret` darstellt. `g(u1, u2, ..., uM)` bewirkt `INVOKE(f, v1, v2, ..., vN, Ret)`, wo `cv` der CV-Qualifizierer von `g` ist, und die Werte und Typen der gebundenen Argumente `v1, v2, ..., vN` wie unten beschrieben bestimmt werden. Damit binden Sie Argumente an aufrufbare Objekte, um aufrufbare Objekte mit einer angepassten Argumentliste und einem angegebenen Rückgabetypen zu erhalten.

Die Werte des gebundenen Arguments `v1, v2, ..., vN` und ihre entsprechenden Typen `V1, V2, ..., VN` hängen folgendermaßen vom Typ `Ti` des entsprechenden Arguments `ti` im Aufruf an `bind` und an die CV-Qualifizierern`cv` des Aufrufwrappers `g` ab:

wenn `ti` Typ `reference_wrapper<T>` ist, ist das Argument `vi` `ti.get()`, und sein Typ `Vi` ist `T&`;

Wenn der Wert des `std::is_bind_expression<Ti>::value` ist **"true"** Arguments `vi` ist `ti(u1, u2, ..., uM)` und dessen Typ `Vi` ist `result_of<Ti` `cv` `(U1&, U2&, ..., UN&>::type`;

wenn der Wert `j` von `std::is_placeholder<Ti>::value` ungleich null ist, ist das Argument `vi` `uj`, und sein Typ `Vi` ist `Uj&`;

andernfalls ist das Argument `vi` `ti`, und sein Typ `Vi` ist `Ti` `cv` `&`.

Hat man beispielsweise eine Funktion `f(int, int)`, gibt der Ausdruck `bind(f, _1, 0)` einen weiterleitenden Aufrufwrapper `cw` zurück, sodass `cw(x)` `f(x, 0)` aufruft. Der Ausdruck `bind(f, 0, _1)` gibt einen weiterleitenden Aufrufwrapper `cw` zurück, sodass `cw(x)` `f(0, x)` aufruft.

Die Anzahl von Argumenten in einem Aufruf an `bind` müssen, zusammen mit dem Argument `fn`, der Anzahl von Argumenten entsprechen, die an ein aufrufbares Objekt `fn` übergeben werden können. Deshalb ist `bind(cos, 1.0)` richtig, und sowohl `bind(cos)` als auch `bind(cos, _1, 0.0)` sind falsch.

Die Anzahl von Argumenten in dem Funktionsaufruf an den Aufrufwrapper, der von `bind` zurückgegeben wurde, muss mindestens so hoch sein wie der höchste nummerierte Wert von `is_placeholder<PH>::value` für alle Platzhalterargumente in dem Aufruf an `bind`. Deshalb ist `bind(cos, _2)(0.0, 1.0)` richtig (und gibt `cos(1.0)` zurück), und `bind(cos, _2)(0.0)` ist falsch.

### <a name="example"></a>Beispiel

```cpp
// std__functional__bind.cpp
// compile with: /EHsc
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std::placeholders;

void square(double x)
{
    std::cout << x << "^2 == " << x * x << std::endl;
}

void product(double x, double y)
{
    std::cout << x << "*" << y << " == " << x * y << std::endl;
}

int main()
{
    double arg[] = { 1, 2, 3 };

    std::for_each(&arg[0], arg + 3, square);
    std::cout << std::endl;

    std::for_each(&arg[0], arg + 3, std::bind(product, _1, 2));
    std::cout << std::endl;

    std::for_each(&arg[0], arg + 3, std::bind(square, _1));

    return (0);
}

```

```Output
1^2 == 1
2^2 == 4
3^2 == 9

1*2 == 2
2*2 == 4
3*2 == 6

1^2 == 1
2^2 == 4
3^2 == 9
```

## <a name="bind1st"></a> bind1st

Eine Hilfevorlagenfunktion, mit der ein Adapter erstellt wird, um ein binäres Funktionsobjekt in ein unäres Funktionsobjekt zu konvertieren, indem das erste Argument der binären Funktion an einen angegebenen Wert gebunden wird.

```cpp
template <class Operation, class Type>
binder1st <Operation> bind1st (const Operation& func, const Type& left);
```

### <a name="parameters"></a>Parameter

*Func* die binäres Funktionsobjekt in ein unäres Funktionsobjekt konvertiert werden.

*linken* den Wert, ist das erste Argument des binären Funktionsobjekts gebunden werden soll.

### <a name="return-value"></a>Rückgabewert

Das unäre Funktionsobjekt, das Binden des ersten Arguments des binären Funktionsobjekts an den Wert ergibt *linken*.

### <a name="remarks"></a>Hinweise

Funktionsbinder sind eine Form von Funktionsadaptern, die in bestimmten Typen von Funktionskompositionen dazu verwendet werden können, komplexere und leistungsstärkere Ausdrücke zu konstruieren; dies ist möglich, weil sie Funktionsobjekte zurückgeben.

Wenn *Func* ist ein Objekt des Typs `Operation` und `c` ist eine Konstante ist, dann `bind1st` ( `func`, `c`) entspricht der [binder1st](../standard-library/binder1st-class.md) Klassenkonstruktor `binder1st` <  `Operation`> ( `func`, `c`) und ist komfortabler.

### <a name="example"></a>Beispiel

```cpp
// functional_bind1st.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

// Creation of a user-defined function object
// that inherits from the unary_function base class
class greaterthan5: unary_function<int, bool>
{
public:
    result_type operator()(argument_type i)
    {
        return (result_type)(i > 5);
    }
};

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 5; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( " ;
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    // Count the number of integers > 10 in the vector
    vector<int>::iterator::difference_type result1a;
    result1a = count_if(v1.begin(), v1.end(), bind1st(less<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1a << "." << endl;

    // Compare: counting the number of integers > 5 in the vector
    // with a user defined function object
    vector<int>::iterator::difference_type result1b;
    result1b = count_if(v1.begin(), v1.end(), greaterthan5());
    cout << "The number of elements in v1 greater than 5 is: "
         << result1b << "." << endl;

    // Count the number of integers < 10 in the vector
    vector<int>::iterator::difference_type result2;
    result2 = count_if(v1.begin(), v1.end(), bind2nd(less<int>(), 10));
    cout << "The number of elements in v1 less than 10 is: "
         << result2 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
The number of elements in v1 greater than 5 is: 4.
The number of elements in v1 less than 10 is: 2.
```

## <a name="bind2nd"></a> bind2nd

Eine Hilfevorlagenfunktion, mit der ein Adapter erstellt wird, um ein binäres Funktionsobjekt in ein unäres Funktionsobjekt zu konvertieren, indem das zweite Argument der binären Funktion an einen angegebenen Wert gebunden wird.

```cpp
template <class Operation, class Type>
binder2nd <Operation> bind2nd(const Operation& func, const Type& right);
```

### <a name="parameters"></a>Parameter

*Func* die binäres Funktionsobjekt in ein unäres Funktionsobjekt konvertiert werden.

*richtige* den Wert, ist das zweite Argument des binären Funktionsobjekts gebunden werden soll.

### <a name="return-value"></a>Rückgabewert

Das unäre Funktionsobjekt, das Binden des zweiten Arguments des binären Funktionsobjekts an den Wert ergibt *rechten*.

### <a name="remarks"></a>Hinweise

Funktionsbinder sind eine Form von Funktionsadaptern, die in bestimmten Typen von Funktionskompositionen dazu verwendet werden können, komplexere und leistungsstärkere Ausdrücke zu konstruieren; dies ist möglich, weil sie Funktionsobjekte zurückgeben.

Wenn *Func* ist ein Objekt des Typs `Operation` und `c` ist eine Konstante ist, dann `bind2nd` ( `func`, `c` ) entspricht der [binder2nd](../standard-library/binder2nd-class.md) Klassenkonstruktor **binder2nd\<Vorgang >** ( `func`, `c` ) und Benutzerfreundlicher.

### <a name="example"></a>Beispiel

```cpp
// functional_bind2nd.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

// Creation of a user-defined function object
// that inherits from the unary_function base class
class greaterthan15: unary_function<int, bool>
{
public:
    result_type operator()(argument_type i)
    {
        return (result_type)(i > 15);
    }
};

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
    vector<int>::iterator::difference_type result1a;
    result1a = count_if(v1.begin(), v1.end(), bind2nd(greater<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1a << "." << endl;

    // Compare counting the number of integers > 15 in the vector
    // with a user-defined function object
    vector<int>::iterator::difference_type result1b;
    result1b = count_if(v1.begin(), v1.end(), greaterthan15());
    cout << "The number of elements in v1 greater than 15 is: "
         << result1b << "." << endl;

    // Count the number of integers < 10 in the vector
    vector<int>::iterator::difference_type result2;
    result2 = count_if(v1.begin(), v1.end(), bind1st(greater<int>(), 10));
    cout << "The number of elements in v1 less than 10 is: "
         << result2 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
The number of elements in v1 greater than 15 is: 2.
The number of elements in v1 less than 10 is: 2.
```

## <a name="bit_and"></a> bit_and

Ein vordefiniertes Funktionsobjekt, mit dem der bitweise AND-Vorgang (binäres `operator&`) auf den Argumenten ausführt wird.

```cpp
template <class Type = void>
struct bit_and : public binary_function<Type, Type, Type> {
    Type operator()(
    const Type& Left,
    const Type& Right) const;
 };

// specialized transparent functor for operator&
template <>
struct bit_and<void>
{
    template <class T, class U>
    auto operator()(T&& Left, U&& Right) const  ->
        decltype(std::forward<T>(Left) & std::forward<U>(Right));
};
```

### <a name="parameters"></a>Parameter

*Typ*, *T*, *U* jeder Typ, unterstützt eine `operator&` , das Operanden angegebener oder abgeleiteter Typen akzeptiert.

*Links* der linke Operand des bitweisen AND-Operation. Die nicht spezialisierte Vorlage besitzt ein Lvalue-Verweisargument vom Typ *Typ*. Die spezialisierte Vorlage vervollkommnet die Weiterleitung von Lvalue und Rvalue-verweisargumenten des abgeleiteten Typs *T*.

*Rechts* der Rechte Operand des bitweisen AND-Operation. Die nicht spezialisierte Vorlage besitzt ein Lvalue-Verweisargument vom Typ *Typ*. Die spezialisierte Vorlage vervollkommnet die Weiterleitung von Lvalue und Rvalue-verweisargumenten des abgeleiteten Typs *U*.

### <a name="return-value"></a>Rückgabewert

Das Ergebnis von `Left & Right`. Die spezialisierte Vorlage vervollkommnet die Weiterleitung des Ergebnisses mit dem von `operator&` zurückgegebenen Typs.

### <a name="remarks"></a>Hinweise

Das `bit_and`-Funktionselement wird auf Ganzzahltypen für die grundlegenden Datentypen oder benutzerdefinierte Typen beschränkt, die das binäre `operator&`-Element implementieren.

## <a name="bit_not"></a> bit_not

Ein vordefiniertes Funktionsobjekt, mit dem der bitweise komplementäre (NOT) Vorgang (unäres `operator~`-Element) auf dem Argument ausgeführt wird.

```cpp
template <class Type = void>
struct bit_not : public unary_function<Type, Type>
 {
    Type operator()(const Type& Right) const;
 };

// specialized transparent functor for operator~
template <>
struct bit_not<void>
 {
    template <class Type>
    auto operator()(Type&& Right) const  ->  decltype(~std::forward<Type>(Right));
 };
```

### <a name="parameters"></a>Parameter

*Typ* ein Typ, der ein unäres unterstützt `operator~`.

*Rechts* der Operand des bitweisen komplementären Vorgangs. Die nicht spezialisierte Vorlage besitzt ein Lvalue-Verweisargument vom Typ *Typ*. Die spezialisierte Vorlage vervollkommnet die Weiterleitung von eines Lvalue- oder eines Rvalue-Verweis-Arguments des abgeleiteten Typs *Typ*.

### <a name="return-value"></a>Rückgabewert

Das Ergebnis von `~ Right`. Die spezialisierte Vorlage vervollkommnet die Weiterleitung des Ergebnisses mit dem von `operator~` zurückgegebenen Typs.

### <a name="remarks"></a>Hinweise

Das `bit_not`-Funktionselement wird auf Ganzzahltypen für die grundlegenden Datentypen oder benutzerdefinierte Typen beschränkt, die das binäre `operator~`-Element implementieren.

## <a name="bit_or"></a> bit_or

Ein vordefiniertes Funktionsobjekt, mit dem der bitweise OR-Vorgang (`operator|`) auf den Argumenten ausführt wird.

```cpp
template <class Type = void>
struct bit_or : public binary_function<Type, Type, Type> {
    Type operator()(
    const Type& Left,
    const Type& Right) const;
 };

// specialized transparent functor for operator|
template <>
struct bit_or<void>
{
    template <class T, class U>
    auto operator()(T&& Left, U&& Right) const
        ->  decltype(std::forward<T>(Left) | std::forward<U>(Right));
};
```

### <a name="parameters"></a>Parameter

*Typ*, *T*, *U* jeder Typ, unterstützt eine `operator|` , das Operanden angegebener oder abgeleiteter Typen akzeptiert.

*Links* der linke Operand des bitweisen OR-Operation. Die nicht spezialisierte Vorlage besitzt ein Lvalue-Verweisargument vom Typ *Typ*. Die spezialisierte Vorlage vervollkommnet die Weiterleitung von Lvalue und Rvalue-verweisargumenten des abgeleiteten Typs *T*.

*Rechts* der Rechte Operand des bitweisen OR-Operation. Die nicht spezialisierte Vorlage besitzt ein Lvalue-Verweisargument vom Typ *Typ*. Die spezialisierte Vorlage vervollkommnet die Weiterleitung von Lvalue und Rvalue-verweisargumenten des abgeleiteten Typs *U*.

### <a name="return-value"></a>Rückgabewert

Das Ergebnis von `Left | Right`. Die spezialisierte Vorlage vervollkommnet die Weiterleitung des Ergebnisses mit dem von `operator|` zurückgegebenen Typs.

### <a name="remarks"></a>Hinweise

Das `bit_or`-Funktionselement wird auf Ganzzahltypen für die grundlegenden Datentypen oder benutzerdefinierte Typen beschränkt, die `operator|` implementieren.

## <a name="bit_xor"></a> bit_xor

Ein vordefiniertes Funktionsobjekt, mit dem der bitweise XOR-Vorgang (binäres `operator^`) auf den Argumenten ausführt wird.

```cpp
template <class Type = void>
struct bit_xor : public binary_function<Type, Type, Type> {
    Type operator()(
    const Type& Left,
    const Type& Right) const;
 };

// specialized transparent functor for operator^
template <>
struct bit_xor<void>
{
    template <class T, class U>
    auto operator()(T&& Left, U&& Right) const
        -> decltype(std::forward<T>(Left) ^ std::forward<U>(Right));
};
```

### <a name="parameters"></a>Parameter

*Typ*, *T*, *U* jeder Typ, unterstützt eine `operator^` , das Operanden angegebener oder abgeleiteter Typen akzeptiert.

*Links* der linke Operand des bitweisen XOR-Operation. Die nicht spezialisierte Vorlage besitzt ein Lvalue-Verweisargument vom Typ *Typ*. Die spezialisierte Vorlage vervollkommnet die Weiterleitung von Lvalue und Rvalue-verweisargumenten des abgeleiteten Typs *T*.

*Rechts* der Rechte Operand des bitweisen XOR-Operation. Die nicht spezialisierte Vorlage besitzt ein Lvalue-Verweisargument vom Typ *Typ*. Die spezialisierte Vorlage vervollkommnet die Weiterleitung von Lvalue und Rvalue-verweisargumenten des abgeleiteten Typs *U*.

### <a name="return-value"></a>Rückgabewert

Das Ergebnis von `Left ^ Right`. Die spezialisierte Vorlage vervollkommnet die Weiterleitung des Ergebnisses mit dem von `operator^` zurückgegebenen Typs.

### <a name="remarks"></a>Hinweise

Das `bit_xor`-Funktionselement wird auf Ganzzahltypen für die grundlegenden Datentypen oder benutzerdefinierte Typen beschränkt, die das binäre `operator^`-Element implementieren.

## <a name="cref"></a> cref

Erstellt ein konstantes `reference_wrapper`-Element aus einem Argument.

```cpp
template <class Ty>
reference_wrapper<const Ty> cref(const Ty& arg);

template <class Ty>
reference_wrapper<const Ty> cref(const reference_wrapper<Ty>& arg);
```

### <a name="parameters"></a>Parameter

*Ty* den Typ des zu umschließenden Arguments.

*Arg* zu umschließenden Arguments.

### <a name="remarks"></a>Hinweise

Diese erste Funktion gibt `reference_wrapper<const Ty>(arg.get())` zurück. Damit können Sie einen const-Verweis umschließen. Die zweite Funktion gibt `reference_wrapper<const Ty>(arg)` zurück. Damit können Sie einen bereits umschlossenen Verweis erneut als const-Verweis umschließen.

### <a name="example"></a>Beispiel

```cpp
// std__functional__cref.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    int i = 1;

    std::cout << "i = " << i << std::endl;
    std::cout << "cref(i) = " << std::cref(i) << std::endl;
    std::cout << "cref(neg)(i) = "
        << std::cref(&neg)(i) << std::endl;

    return (0);
    }

```

```Output
i = 1
cref(i) = 1
cref(neg)(i) = -1
```

## <a name="mem_fn"></a> mem_fn

Generiert einen einfachen Aufrufwrapper.

```cpp
template <class Ret, class Ty>
unspecified mem_fn(Ret Ty::*pm);
```

### <a name="parameters"></a>Parameter

*Ret* der Rückgabetyp der umschlossenen Funktion.

*Ty* den Typ des memberfunktionszeigers.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion gibt einen einfachen Aufrufwrapper `cw` mit einem schwachen Ergebnistyp zurück, sodass der Ausdruck `cw(t, a2, ..., aN)` `INVOKE(pm, t, a2, ..., aN)` entspricht. Sie löst keine Ausnahmen aus.

Der zurückgegebene Wrapper wird abgeleitet `std::unary_function<cv Ty*, Ret>` (somit definiert es den geschachtelten Typ `result_type` als Synonym für *Ret* und den geschachtelten Typ `argument_type` als Synonym für `cv Ty*`) nur, wenn der Typ  *Ty* ist ein Zeiger auf eine Memberfunktion mit dem cv-Qualifizierer `cv` , die keine Argumente akzeptiert.

Der zurückgegebene Wrapper wird abgeleitet `std::binary_function<cv Ty*, T2, Ret>` (somit definiert es den geschachtelten Typ `result_type` als Synonym für *Ret*, geschachtelter Typ `first argument_type` als Synonym für `cv Ty*`, und der geschachtelte Typ `second argument_type`als Synonym für `T2`) nur, wenn der Typ *Ty* ist ein Zeiger auf eine Memberfunktion mit dem cv-Qualifizierer `cv` , akzeptiert ein Argument des Typs `T2`.

### <a name="example"></a>Beispiel

```cpp
// std__functional__mem_fn.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

class Funs
    {
public:
    void square(double x)
        {
        std::cout << x << "^2 == " << x * x << std::endl;
        }

    void product(double x, double y)
        {
        std::cout << x << "*" << y << " == " << x * y << std::endl;
        }
    };

int main()
    {
    Funs funs;

    std::mem_fn(&Funs::square)(funs, 3.0);
    std::mem_fn(&Funs::product)(funs, 3.0, 2.0);

    return (0);
    }

```

```Output
3^2 == 9
3*2 == 6
```

## <a name="mem_fun"></a> mem_fun

Hilfevorlagenfunktionen, die verwendet werden, um Funktionsobjektadapter für Memberfunktionen zu konstruieren, wenn Sie mit Zeigerargumenten initialisiert werden.

```cpp
template <class Result, class Type>
mem_fun_t<Result, Type> mem_fun (Result(Type::* pmem)());

template <class Result, class Type, class Arg>
mem_fun1_t<Result, Type, Arg> mem_fun(Result (Type::* pmem)(Arg));

template <class Result, class Type>
const_mem_fun_t<Result, Type> mem_fun(Result (Type::* pmem)() const);

template <class Result, class Type, class Arg>
const_mem_fun1_t<Result, Type, Arg> mem_fun(Result (Type::* pmem)(Arg) const);
```

### <a name="parameters"></a>Parameter

*pMem* ein Zeiger auf die Memberfunktion der Klasse `Type` in ein Funktionsobjekt konvertiert werden.

### <a name="return-value"></a>Rückgabewert

Ein **const**- oder **non_const**-Funktionsobjekt des Typs `mem_fun_t` oder `mem_fun1_t`.

### <a name="example"></a>Beispiel

```cpp
// functional_mem_fun.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

class StoreVals
{
    int val;
public:
    StoreVals() { val = 0; }
    StoreVals(int j) { val = j; }

    bool display() { cout << val << " "; return true; }
    int squareval() { val *= val; return val; }
    int lessconst(int k) {val -= k; return val; }
};

int main( )
{
    vector<StoreVals *> v1;

    StoreVals sv1(5);
    v1.push_back(&sv1);
    StoreVals sv2(10);
    v1.push_back(&sv2);
    StoreVals sv3(15);
    v1.push_back(&sv3);
    StoreVals sv4(20);
    v1.push_back(&sv4);
    StoreVals sv5(25);
    v1.push_back(&sv5);

    cout << "The original values stored are: " ;
    for_each(v1.begin(), v1.end(), mem_fun<bool, StoreVals>(&StoreVals::display));
    cout << endl;

    // Use of mem_fun calling member function through a pointer
    // square each value in the vector using squareval ()
    for_each(v1.begin(), v1.end(), mem_fun<int, StoreVals>(&StoreVals::squareval));
    cout << "The squared values are: " ;
    for_each(v1.begin(), v1.end(), mem_fun<bool, StoreVals>(&StoreVals::display));
    cout << endl;

    // Use of mem_fun1 calling member function through a pointer
    // subtract 5 from each value in the vector using lessconst ()
    for_each(v1.begin(), v1.end(),
        bind2nd (mem_fun1<int, StoreVals,int>(&StoreVals::lessconst), 5));
    cout << "The squared values less 5 are: " ;
    for_each(v1.begin(), v1.end(), mem_fun<bool, StoreVals>(&StoreVals::display));
    cout << endl;
}
```

## <a name="mem_fun_ref"></a> mem_fun_ref

Hilfevorlagenfunktionen, die verwendet werden, um Funktionsobjektadapter für Memberfunktionen zu konstruieren, indem Sie mit Verweisargumenten initialisiert werden.

```cpp
template <class Result, class Type>
mem_fun_ref_t<Result, Type> mem_fun_ref(Result (Type::* pmem)());

template <class Result, class Type, class Arg>
mem_fun1_ref_t<Result, Type, Arg> mem_fun_ref(Result (Type::* pmem)(Arg));

template <class Result, class Type>
const_mem_fun_ref_t<Result, Type> mem_fun_ref(Result Type::* pmem)() const);

template <class Result, class Type, class Arg>
const_mem_fun1_ref_t<Result, Type, Arg> mem_fun_ref(Result (T::* pmem)(Arg) const);
```

### <a name="parameters"></a>Parameter

*pMem* ein Zeiger auf die Memberfunktion der Klasse `Type` in ein Funktionsobjekt konvertiert werden.

### <a name="return-value"></a>Rückgabewert

Ein **const** oder `non_const` Funktionsobjekt vom Typ `mem_fun_ref_t` oder `mem_fun1_ref_t`.

### <a name="example"></a>Beispiel

```cpp
// functional_mem_fun_ref.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

class NumVals
   {
   int val;
   public:
   NumVals ( ) { val = 0; }
   NumVals ( int j ) { val = j; }

   bool display ( ) { cout << val << " "; return true; }
   bool isEven ( ) { return ( bool )  !( val %2 ); }
   bool isPrime( )
   {
      if (val < 2) { return true; }
      for (int i = 2; i <= val / i; ++i)
      {
         if (val % i == 0) { return false; }
      }
      return true;
   }
};

int main( )
{
   vector <NumVals> v1 ( 13 ), v2 ( 13 );
   vector <NumVals>::iterator v1_Iter, v2_Iter;
   int i, k;

   for ( i = 0; i < 13; i++ ) v1 [ i ] = NumVals ( i+1 );
   for ( k = 0; k < 13; k++ ) v2 [ k ] = NumVals ( k+1 );

   cout << "The original values stored in v1 are: " ;
   for_each( v1.begin( ), v1.end( ),
   mem_fun_ref ( &NumVals::display ) );
   cout << endl;

   // Use of mem_fun_ref calling member function through a reference
   // remove the primes in the vector using isPrime ( )
   v1_Iter = remove_if ( v1.begin( ),  v1.end( ),
      mem_fun_ref ( &NumVals::isPrime ) );
   cout << "With the primes removed, the remaining values in v1 are: " ;
   for_each( v1.begin( ), v1_Iter,
   mem_fun_ref ( &NumVals::display ) );
   cout << endl;

   cout << "The original values stored in v2 are: " ;
   for_each( v2.begin( ), v2.end( ),
   mem_fun_ref ( &NumVals::display ) );
   cout << endl;

   // Use of mem_fun_ref calling member function through a reference
   // remove the even numbers in the vector v2 using isEven ( )
   v2_Iter = remove_if ( v2.begin( ),  v2.end( ),
      mem_fun_ref ( &NumVals::isEven ) );
   cout << "With the even numbers removed, the remaining values are: " ;
   for_each( v2.begin( ),  v2_Iter,
   mem_fun_ref ( &NumVals::display ) );
   cout << endl;
}
```

```Output
The original values stored in v1 are: 1 2 3 4 5 6 7 8 9 10 11 12 13
With the primes removed, the remaining values in v1 are: 4 6 8 9 10 12
The original values stored in v2 are: 1 2 3 4 5 6 7 8 9 10 11 12 13
With the even numbers removed, the remaining values are: 1 3 5 7 9 11 13
```

## <a name="not1"></a> not1

Gibt das Komplement eines unären Prädikats zurück.

```cpp
template <class UnaryPredicate>
unary_negate<UnaryPredicate> not1(const UnaryPredicate& pred);
```

### <a name="parameters"></a>Parameter

*Pred* der zu negierende unäre Prädikat.

### <a name="return-value"></a>Rückgabewert

Ein unäres Prädikat, das die Negation des modifizierten unären Prädikats ist.

### <a name="remarks"></a>Hinweise

Wenn `unary_negate` aus einem unären Prädikat **Pred** (*x*) konstruiert wurde, gibt es **!Pred** (*x*) zurück.

### <a name="example"></a>Beispiel

```cpp
// functional_not1.cpp
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
    for (i = 0; i <= 7; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( ";
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    vector<int>::iterator::difference_type result1;
    // Count the elements greater than 10
    result1 = count_if(v1.begin(), v1.end(), bind2nd(greater<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1 << "." << endl;

    vector<int>::iterator::difference_type result2;
    // Use the negator to count the elements less than or equal to 10
    result2 = count_if(v1.begin(), v1.end(),
        not1(bind2nd(greater<int>(), 10)));

    cout << "The number of elements in v1 not greater than 10 is: "
         << result2 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 30 35 )
The number of elements in v1 greater than 10 is: 5.
The number of elements in v1 not greater than 10 is: 3.
```

## <a name="not2"></a> not2

Gibt das Komplement eines binären Prädikats zurück.

```cpp
template <class BinaryPredicate>
binary_negate<BinaryPredicate> not2(const BinaryPredicate& func);
```

### <a name="parameters"></a>Parameter

*Func* das binäre Prädikat, das negiert werden soll.

### <a name="return-value"></a>Rückgabewert

Ein binäres Prädikat, das die Negation des modifizierten binären Prädikats ist.

### <a name="remarks"></a>Hinweise

Wenn `binary_negate` aus einem binären Prädikat **BinPred** (*x*, *y*) konstruiert wurde, gibt es ! zurück **BinPred** (*x*, *y*).

### <a name="example"></a>Beispiel

```cpp
// functional_not2.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>
#include <cstdlib>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   v1.push_back( 6262 );
   v1.push_back( 6262 );
   for ( i = 0 ; i < 5 ; i++ )
   {
      v1.push_back( rand( ) );
   }

   cout << "Original vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in ascending order,
   // use default binary predicate less<int>( )
   sort( v1.begin( ), v1.end( ) );
   cout << "Sorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in descending order,
   // use the binary_negate helper function not2
   sort( v1.begin( ), v1.end( ), not2(less<int>( ) ) );
   cout << "Resorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;
}
```

```Output
Original vector v1 = ( 6262 6262 41 18467 6334 26500 19169 )
Sorted vector v1 = ( 41 6262 6262 6334 18467 19169 26500 )
Resorted vector v1 = ( 26500 19169 18467 6334 6262 6262 41 )
```

## <a name="ptr_fun"></a> ptr_fun

Hilfevorlagenfunktionen, die verwendet werden, um die jeweiligen unären und binären Funktionszeiger in die unären und binären anwendbaren Funktionen zu konvertieren.

```cpp
template <class Arg, class Result>
pointer_to_unary_function<Arg, Result, Result (*)(Arg)> ptr_fun(Result (*pfunc)(Arg));

template <class Arg1, class Arg2, class Result>
pointer_to_binary_function<Arg1, Arg2, Result, Result (*)(Arg1, Arg2)> ptr_fun(Result (*pfunc)(Arg1, Arg2));
```

### <a name="parameters"></a>Parameter

*Pfunc* der unäre oder binäre Funktionszeiger in eine anwendbare Funktion konvertiert werden soll.

### <a name="return-value"></a>Rückgabewert

Die erste Vorlagenfunktion gibt die unäre Funktion [Pointer_to_unary_function](../standard-library/pointer-to-unary-function-class.md) < `Arg`, **Ergebnis**> (\* `pfunc`).

Die zweite Vorlagenfunktion gibt die unäre Funktion [Pointer_to_binary_function](../standard-library/pointer-to-binary-function-class.md) \< **Arg1**, **Arg2**, **Ergebnis**> (\* `pfunc`).

### <a name="remarks"></a>Hinweise

Ein Funktionszeiger ist ein Funktionsobjekt und kann an alle C++-Standardbibliotheksalgorithmen übergeben werden, die eine Funktion als Parameter erwarten, aber er kann nicht angepasst werden. Für die Verwendung mit einem Adapter, z.B. um einen Wert zuzuordnen oder ihn mit einer Negator zu verwenden, müssen die geschachtelten Typen angegeben werden, die eine solche Anpassung möglich machen. Durch die Konvertierung von unären und binären Funktionszeigern mithilfe der Hilfsfunktion `ptr_fun` können die Funktionsadapter mit unären und binären Funktionszeigern arbeiten.

### <a name="example"></a>Beispiel

[!code-cpp[functional_ptr_fun#1](../standard-library/codesnippet/CPP/functional-functions_1.cpp)]

## <a name="ref"></a> ref

Konstruiert ein `reference_wrapper` aus einem Argument.

```cpp
template <class Ty>
reference_wrapper<Ty> ref(Ty& arg);

template <class Ty>
reference_wrapper<Ty> ref(reference_wrapper<Ty>& arg);
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf ein `arg`; insbesondere `reference_wrapper<Ty>(arg)`.

### <a name="example"></a>Beispiel

Im folgenden Beispiel werden zwei Funktionen definiert: eine, die an eine Zeichenfolgenvariable gebunden ist, die andere, die an einen Verweis der Zeichenfolgenvariablen gebunden ist, der durch einen Aufruf von `ref`berechnet wurde. Wenn sich der Wert der Variablen ändert, verwendet die erste Funktion weiterhin den alten Wert, und die zweite Version verwendet den neuen Wert.

```cpp
#include <algorithm>
#include <functional>
#include <iostream>
#include <iterator>
#include <ostream>
#include <string>
#include <vector>
using namespace std;
using namespace std;
using namespace std::placeholders;

bool shorter_than(const string& l, const string& r) {
    return l.size() < r.size();
}

int main() {
    vector<string> v_original;
    v_original.push_back("tiger");
    v_original.push_back("cat");
    v_original.push_back("lion");
    v_original.push_back("cougar");

    copy(v_original.begin(), v_original.end(), ostream_iterator<string>(cout, " "));
    cout << endl;

    string s("meow");

    function<bool (const string&)> f = bind(shorter_than, _1, s);
    function<bool (const string&)> f_ref = bind(shorter_than, _1, ref(s));

    vector<string> v;

    // Remove elements that are shorter than s ("meow")

    v = v_original;
    v.erase(remove_if(v.begin(), v.end(), f), v.end());

    copy(v.begin(), v.end(), ostream_iterator<string>(cout, " "));
    cout << endl;

    // Now change the value of s.
    // f_ref, which is bound to ref(s), will use the
    // new value, while f is still bound to the old value.

    s = "kitty";

    // Remove elements that are shorter than "meow" (f is bound to old value of s)

    v = v_original;
    v.erase(remove_if(v.begin(), v.end(), f), v.end());

    copy(v.begin(), v.end(), ostream_iterator<string>(cout, " "));
    cout << endl;

    // Remove elements that are shorter than "kitty" (f_ref is bound to ref(s))

    v = v_original;
    v.erase(remove_if(v.begin(), v.end(), f_ref), v.end());

    copy(v.begin(), v.end(), ostream_iterator<string>(cout, " "));
    cout << endl;
}
```

```Output
tiger cat lion cougar
tiger lion cougar
tiger lion cougar
tiger cougar
```

## <a name="swap"></a>  swap

Tauscht zwei `function`-Objekte.

```cpp
template <class Fty>
void swap(function<Fty>& f1, function<Fty>& f2);
```

### <a name="parameters"></a>Parameter

*Fty* der vom Funktionsobjekt gesteuerte Typ.

*F1* das erste Funktionsobjekt.

*F2* das zweite Funktionsobjekt.

### <a name="remarks"></a>Hinweise

Die Funktion gibt `f1.swap(f2)` zurück.

### <a name="example"></a>Beispiel

```cpp
// std__functional__swap.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    std::function<int (int)> fn0(neg);
    std::cout << std::boolalpha << "empty == " << !fn0 << std::endl;
    std::cout << "val == " << fn0(3) << std::endl;

    std::function<int (int)> fn1;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << std::endl;

    swap(fn0, fn1);
    std::cout << std::boolalpha << "empty == " << !fn0 << std::endl;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << "val == " << fn1(3) << std::endl;

    return (0);
    }

```

```Output
empty == false
val == -3
empty == true

empty == true
empty == false
val == -3
```

## <a name="see-also"></a>Siehe auch

[\<functional>](../standard-library/functional.md)<br/>
