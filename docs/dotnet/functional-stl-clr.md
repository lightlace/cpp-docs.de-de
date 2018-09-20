---
title: funktionale (STL/CLR) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- <cliext/functional>
- cliext::binary_delegate
- cliext::binary_delegate_noreturn
- cliext::binary_negate
- cliext::bind1st
- cliext::bind2nd
- cliext::binder1st
- cliext::binder2nd
- cliext::divides
- cliext::equal_to
- cliext::greater
- cliext::greater_equal
- cliext::less
- cliext::less_equal
- cliext::logical_and
- cliext::logical_not
- cliext::logical_or
- cliext::minus
- cliext::modulus
- cliext::multiplies
- cliext::negate
- cliext::not_equal_to
- cliext::not1
- cliext::not2
- cliext::plus
- cliext::unary_delegate
- cliext::unary_delegate_noreturn
- cliext::unary_negate
dev_langs:
- C++
helpviewer_keywords:
- <functional> header [STL/CLR]
- <cliext/functional> header [STL/CLR]
- functional functions [STL/CLR]
- binary_delegate function [STL/CLR]
- binary_delegate_noreturn function [STL/CLR]
- binary_negate function [STL/CLR]
- bind1st function [STL/CLR]
- bind2nd function [STL/CLR]
- binder1st function [STL/CLR]
- binder2nd function [STL/CLR]
- divides function [STL/CLR]
- equal_to function [STL/CLR]
- greater function [STL/CLR]
- greater_equal function [STL/CLR]
- less function [STL/CLR]
- less_equal function [STL/CLR]
- logical_and function [STL/CLR]
- logical_not function [STL/CLR]
- logical_or function [STL/CLR]
- minus function [STL/CLR]
- modulus function [STL/CLR]
- multiplies function [STL/CLR]
- negate function [STL/CLR]
- not_equal_to function [STL/CLR]
- not1 function [STL/CLR]
- not2 function [STL/CLR]
- plus function [STL/CLR]
- unary_delegate function [STL/CLR]
- unary_delegate_noreturn function [STL/CLR]
- unary_negate function [STL/CLR]
ms.assetid: 88738b8c-5d37-4375-970e-a4442bf5efde
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 996e0f4bcf515d7bc38f89c291927a5444f5654b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423537"
---
# <a name="functional-stlclr"></a>functional (STL/CLR)

Fügen Sie den STL/CLR-Header `<cliext/functional>` zu definieren, die eine Reihe von Vorlagenklassen und verwandten Vorlage Delegaten und Funktionen.

## <a name="syntax"></a>Syntax

```
#include <functional>
```

## <a name="requirements"></a>Anforderungen

**Header:** \<Cliext/functional >

**Namespace:** Cliext

## <a name="declarations"></a>Deklarationen

|delegate|Beschreibung|
|--------------|-----------------|
|[binary_delegate (STL/CLR)](#binary_delegate)|Delegaten mit zwei Argumenten.|
|[binary_delegate_noreturn (STL/CLR)](#binary_delegate_noreturn)|Zurückgeben von Delegaten mit zwei Argumenten **"void"**.|
|[unary_delegate (STL/CLR)](#unary_delegate)|Delegaten mit einem Argument.|
|[unary_delegate_noreturn (STL/CLR)](#unary_delegate_noreturn)|Zurückgeben von Delegaten mit einem Argument **"void"**.|

|Klasse|Beschreibung|
|-----------|-----------------|
|[binary_negate (STL/CLR)](#binary_negate)|Funktionselement ein Funktionselement ist zwei Argumenten zu negieren.|
|[binder1st (STL/CLR)](#binder1st)|Funktionselement erstes Argument an ein Funktionselement ist zwei Argumenten gebunden.|
|[binder2nd (STL/CLR)](#binder2nd)|Funktionselement zweites Argument an ein Funktionselement ist zwei Argumenten gebunden.|
|[divides (STL/CLR)](#divides)|Teilen Sie Funktionselement.|
|[equal_to (STL/CLR)](#equal_to)|Gleich-Vergleich Funktionselement.|
|[greater (STL/CLR)](#greater)|Größere Vergleich Funktionselement.|
|[greater_equal (STL/CLR)](#greater_equal)|Größer oder gleich-Vergleich Funktionselement.|
|[less (STL/CLR)](#less)|Weniger Funktionselement Vergleich.|
|[less_equal (STL/CLR)](#less_equal)|Kleiner als oder gleich-Vergleich Funktionselement.|
|[logical_and (STL/CLR)](#logical_and)|Logischer AND-Funktionselement.|
|[logical_not (STL/CLR)](#logical_not)|Logisches nicht Funktionselement.|
|[logical_or (STL/CLR)](#logical_or)|Logisches OR Functor.|
|[minus (STL/CLR)](#minus)|Subtrahieren Sie Funktionselement.|
|[modulus (STL/CLR)](#modulus)|Modulus-Funktionselement.|
|[multiplies (STL/CLR)](#multiplies)|Multiplizieren Sie Funktionselement.|
|[negate (STL/CLR)](#negate)|Funktionselement zurückzugebenden Arguments negiert.|
|[not_equal_to (STL/CLR)](#not_equal_to)|Funktionselement ist nicht gleich-Vergleich.|
|[plus (STL/CLR)](#plus)|Fügen Sie Funktionselement hinzu.|
|[unary_negate (STL/CLR)](#unary_negate)|Funktionselement zu negierende ein Funktionselement ist einem Argument.|

|Funktion|Beschreibung|
|--------------|-----------------|
|[bind1st (STL/CLR)](#bind1st)|Generiert eine binder1st für ein Argument und ein Funktionselement ist.|
|[bind2nd (STL/CLR)](#bind2nd)|Generiert eine binder2nd für ein Argument und ein Funktionselement ist.|
|[not1 (STL/CLR)](#not1)|Generiert eine Unary_negate für ein Funktionselement ist.|
|[not2 (STL/CLR)](#not2)|Generiert eine Binary_negate für ein Funktionselement ist.|

## <a name="members"></a>Member

## <a name="binary_delegate"></a> Binary_delegate (STL/CLR)

Die Genereic-Klasse beschreibt einen Delegaten mit zwei Argumenten. Sie verwenden, geben Sie einen Delegaten in Bezug auf die Argument- und Rückgabetypen-Typen.

### <a name="syntax"></a>Syntax

```cpp
generic<typename Arg1,
    typename Arg2,
    typename Result>
    delegate Result binary_delegate(Arg1, Arg2);
```

#### <a name="parameters"></a>Parameter

*arg1*<br/>
Der Typ des ersten Arguments.

*Arg2*<br/>
Der Typ des zweiten Arguments.

*Ergebnis*<br/>
Der Rückgabetyp.

### <a name="remarks"></a>Hinweise

Der Delegat Genereic beschreibt eine Funktion mit zwei Argumenten.

Beachten Sie, dass für:

`binary_delegate<int, int, int> Fun1;`

`binary_delegate<int, int, int> Fun2;`

die Typen `Fun1` und `Fun2` sind Synonyme, während er sich für:

`delegate int Fun1(int, int);`

`delegate int Fun2(int, int);`

Sie sind nicht den gleichen Typ.

### <a name="example"></a>Beispiel

```cpp
// cliext_binary_delegate.cpp
// compile with: /clr
#include <cliext/functional>

bool key_compare(wchar_t left, wchar_t right)
    {
    return (left < right);
    }

typedef cliext::binary_delegate<wchar_t, wchar_t, bool> Mydelegate;
int main()
    {
    Mydelegate^ kcomp = gcnew Mydelegate(&key_compare);

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare(L'a', L'a') = False
compare(L'a', L'b') = True
compare(L'b', L'a') = False
```

## <a name="binary_delegate_noreturn"></a> Binary_delegate_noreturn (STL/CLR)

Die Genereic-Klasse beschreibt einen Delegaten mit zwei Argumenten, die zurückgibt **"void"**. Sie verwenden, geben Sie einen Delegaten in Bezug auf das Argument.

### <a name="syntax"></a>Syntax

```cpp
generic<typename Arg1,
    typename Arg2>
    delegate void binary_delegate(Arg1, Arg2);
```

#### <a name="parameters"></a>Parameter

*arg1*<br/>
Der Typ des ersten Arguments.

*Arg2*<br/>
Der Typ des zweiten Arguments.

### <a name="remarks"></a>Hinweise

Der Delegat Genereic beschreibt eine Funktion mit zwei Argumenten, die zurückgibt **"void"**.

Beachten Sie, dass für:

`binary_delegate_noreturn<int, int> Fun1;`

`binary_delegate_noreturn<int, int> Fun2;`

die Typen `Fun1` und `Fun2` sind Synonyme, während er sich für:

`delegate void Fun1(int, int);`

`delegate void Fun2(int, int);`

Sie sind nicht den gleichen Typ.

### <a name="example"></a>Beispiel

```cpp
// cliext_binary_delegate_noreturn.cpp
// compile with: /clr
#include <cliext/functional>

void key_compare(wchar_t left, wchar_t right)
    {
    System::Console::WriteLine("compare({0}, {1}) = {2}",
        left, right, left < right);
    }

typedef cliext::binary_delegate_noreturn<wchar_t, wchar_t> Mydelegate;
int main()
    {
    Mydelegate^ kcomp = gcnew Mydelegate(&key_compare);

    kcomp(L'a', L'a');
    kcomp(L'a', L'b');
    kcomp(L'b', L'a');
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare(a, a) = False
compare(a, b) = True
compare(b, a) = False
```

## <a name="binary_negate"></a> Binary_negate (STL/CLR)

Die Vorlagenklasse beschreibt ein Funktionselement ist, die beim Aufruf gibt die logische nicht von der gespeicherten Funktionselement von zwei Argumenten. Sie verwenden, geben Sie ein Funktionsobjekt im Hinblick auf seine gespeicherten Funktionselement.

### <a name="syntax"></a>Syntax

```cpp
template<typename Fun>
    ref class binary_negate
    { // wrap operator()
public:
    typedef Fun stored_function_type;
    typedef typename Fun::first_argument_type first_argument_type;
    typedef typename Fun::second_argument_type second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    explicit binary_negate(Fun% functor);
    binary_negate(binary_negate<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parameter

*Spaß*<br/>
Der Typ der gespeicherten kennen.

## <a name="member-functions"></a>Memberfunktionen

|Typdefinition|Beschreibung|
|---------------------|-----------------|
|delegate_type|Der Typ des generischen Delegaten.|
|first_argument_type|Der Typ des ersten Arguments Funktionselement.|
|RESULT_TYPE|Der Typ des Ergebnisses Funktionselement.|
|second_argument_type|Der Typ des zweiten Arguments Funktionselement.|
|stored_function_type|Der Typ der zu kennen.|

|Member|Beschreibung|
|------------|-----------------|
|binary_negate|Erstellt das Funktionselement.|

|Operator|Beschreibung|
|--------------|-----------------|
|Operator()|Berechnet die gewünschte Funktion.|
|Operator delegate_type^()|Wandelt das Funktionselement in einen Delegaten an.|

### <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Funktionselement von zwei Argumenten, die einen anderen zwei Argumenten Funktionselement speichert. Der Memberoperator definiert `operator()` , wenn das Objekt als eine Funktion aufgerufen wird, gibt die logische nicht von der gespeicherten Funktionselement aufgerufen werden soll, mit zwei Argumenten.

Sie können auch das Objekt übergeben, als Funktionsargument, dessen Typ `delegate_type^` und werden entsprechend konvertiert werden.

### <a name="example"></a>Beispiel

```cpp
// cliext_binary_negate.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::less<int> less_op;

    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(),
        cliext::binary_negate<cliext::less<int> >(less_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::not2(less_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
1 0
1 0
```

## <a name="bind1st"></a> bind1st (STL/CLR)

Generiert eine `binder1st` für ein Argument und ein Funktionselement ist.

### <a name="syntax"></a>Syntax

```cpp
template<typename Fun,
    typename Arg>
    binder1st<Fun> bind1st(Fun% functor,
        Arg left);
```

#### <a name="template-parameters"></a>Vorlagenparameter

*arg*<br/>
Der Typ des Arguments.

*Spaß*<br/>
Der Typ der zu kennen.

#### <a name="function-parameters"></a>Funktionsparameter

*Funktionselement*<br/>
Das Funktionselement umschlossen werden soll.

*left*<br/>
Das erste Argument umschlossen werden soll.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion gibt [binder1st (STL/CLR)](../dotnet/binder1st-stl-clr.md)`<Fun>(functor, left)`. Sie verwenden es als eine einfache Möglichkeit, ein Funktionselement ist zwei Argumenten und sein erstes Argument ein Funktionselement ist einem Argument umschließen, den sie mit einem zweiten Argument aufruft.

### <a name="example"></a>Beispiel

```cpp
// cliext_bind1st.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::minus<int> sub_op;
    cliext::binder1st<cliext::minus<int> > subfrom3(sub_op, 3);

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        subfrom3);
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        bind1st(sub_op, 3));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
-1 0
-1 0
```

## <a name="bind2nd"></a> bind2nd (STL/CLR)

Generiert eine `binder2nd` für ein Argument und ein Funktionselement ist.

### <a name="syntax"></a>Syntax

```cpp
template<typename Fun,
    typename Arg>
    binder2nd<Fun> bind2nd(Fun% functor,
        Arg right);
```

#### <a name="template-parameters"></a>Vorlagenparameter

*arg*<br/>
Der Typ des Arguments.

*Spaß*<br/>
Der Typ der zu kennen.

#### <a name="function-parameters"></a>Funktionsparameter

*Funktionselement*<br/>
Das Funktionselement umschlossen werden soll.

*right*<br/>
Das zweite Argument umschlossen werden soll.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion gibt [binder2nd (STL/CLR)](../dotnet/binder2nd-stl-clr.md)`<Fun>(functor, right)`. Sie verwenden es als eine einfache Möglichkeit, ein Funktionselement ist zwei Argumenten und das zweite Argument ein Funktionselement ist einem Argument umschließen, den sie mit dem ersten Argument aufruft.

### <a name="example"></a>Beispiel

```cpp
// cliext_bind2nd.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::minus<int> sub_op;
    cliext::binder2nd<cliext::minus<int> > sub4(sub_op, 4);

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        sub4);
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        bind2nd(sub_op, 4));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
0 -1
0 -1
```

## <a name="binder1st"></a> binder1st (STL/CLR)

Die Vorlagenklasse beschreibt ein Funktionselement ist einem Argument, wenn aufgerufen, gibt die gespeicherten zwei Argumenten Funktionselement mit gespeicherten erstes Argument und das zweite angegebene Argument aufgerufen. Sie verwenden, geben Sie ein Funktionsobjekt im Hinblick auf seine gespeicherten Funktionselement.

### <a name="syntax"></a>Syntax

```cpp
template<typename Fun>
    ref class binder1st
    { // wrap operator()
public:
    typedef Fun stored_function_type;
    typedef typename Fun::first_argument_type first_argument_type;
    typedef typename Fun::second_argument_type second_argument_type;
    typedef typename Fun:result_type result_type;
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<
        second_argument_type, result_type>
        delegate_type;

    binder1st(Fun% functor, first_argument_type left);
    binder1st(binder1st<Arg>% right);

    result_type operator()(second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parameter

*Spaß*<br/>
Der Typ der gespeicherten kennen.

### <a name="member-functions"></a>Memberfunktionen

|Typdefinition|Beschreibung|
|---------------------|-----------------|
|delegate_type|Der Typ des generischen Delegaten.|
|first_argument_type|Der Typ des ersten Arguments Funktionselement.|
|RESULT_TYPE|Der Typ des Ergebnisses Funktionselement.|
|second_argument_type|Der Typ des zweiten Arguments Funktionselement.|
|stored_function_type|Der Typ der zu kennen.|

|Member|Beschreibung|
|------------|-----------------|
|binder1st|Erstellt das Funktionselement.|

|Operator|Beschreibung|
|--------------|-----------------|
|Operator()|Berechnet die gewünschte Funktion.|
|Operator delegate_type^()|Wandelt das Funktionselement in einen Delegaten an.|

### <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Funktionselement ist einem Argument, das ein Funktionselement ist zwei Argumenten und ein erstes Argument gespeichert. Der Memberoperator definiert `operator()` , wenn das Objekt als eine Funktion aufgerufen wird, gibt das Ergebnis des Aufrufs der gespeicherten Funktionselement mit der gespeicherten erstes Argument und das zweite angegebene Argument zurück.

Sie können auch das Objekt übergeben, als Funktionsargument, dessen Typ `delegate_type^` und werden entsprechend konvertiert werden.

### <a name="example"></a>Beispiel

```cpp
// cliext_binder1st.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::minus<int> sub_op;
    cliext::binder1st<cliext::minus<int> > subfrom3(sub_op, 3);

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        subfrom3);
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        bind1st(sub_op, 3));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
-1 0
-1 0
```

## <a name="binder2nd"></a> binder2nd (STL/CLR)

Die Vorlagenklasse beschreibt ein Funktionselement ist einem Argument, wenn aufgerufen, gibt die gespeicherten zwei Argumenten Funktionselement mit dem angegebenen ersten Argument und gespeicherte zweites Argument aufgerufen. Sie verwenden, geben Sie ein Funktionsobjekt im Hinblick auf seine gespeicherten Funktionselement.

### <a name="syntax"></a>Syntax

```cpp
template<typename Fun>
    ref class binder2nd
    { // wrap operator()
public:
    typedef Fun stored_function_type;
    typedef typename Fun::first_argument_type first_argument_type;
    typedef typename Fun::second_argument_type second_argument_type;
    typedef typename Fun:result_type result_type;
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<
        first_argument_type, result_type>
        delegate_type;

    binder2nd(Fun% functor, second_argument_type left);
    binder2nd(binder2nd<Arg>% right);

    result_type operator()(first_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parameter

*Spaß*<br/>
Der Typ der gespeicherten kennen.

## <a name="member-functions"></a>Memberfunktionen

|Typdefinition|Beschreibung|
|---------------------|-----------------|
|delegate_type|Der Typ des generischen Delegaten.|
|first_argument_type|Der Typ des ersten Arguments Funktionselement.|
|RESULT_TYPE|Der Typ des Ergebnisses Funktionselement.|
|second_argument_type|Der Typ des zweiten Arguments Funktionselement.|
|stored_function_type|Der Typ der zu kennen.|

|Member|Beschreibung|
|------------|-----------------|
|binder2nd|Erstellt das Funktionselement.|

|Operator|Beschreibung|
|--------------|-----------------|
|Operator()|Berechnet die gewünschte Funktion.|
|Operator delegate_type^()|Wandelt das Funktionselement in einen Delegaten an.|

### <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Funktionselement ist einem Argument, das ein Funktionselement ist zwei Argumenten und ein zweites Argument gespeichert. Der Memberoperator definiert `operator()` , wenn das Objekt als eine Funktion aufgerufen wird, wird das Ergebnis des Aufrufs der gespeicherten Funktionselement mit dem angegebenen ersten Argument und das zweite gespeicherte Argument zurückgegeben.

Sie können auch das Objekt übergeben, als Funktionsargument, dessen Typ `delegate_type^` und werden entsprechend konvertiert werden.

### <a name="example"></a>Beispiel

```cpp
// cliext_binder2nd.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::minus<int> sub_op;
    cliext::binder2nd<cliext::minus<int> > sub4(sub_op, 4);

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        sub4);
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        bind2nd(sub_op, 4));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
0 -1
0 -1
```

## <a name="divides"></a> dividiert (STL/CLR)

Die Vorlagenklasse beschreibt ein Funktionselement ist, wenn aufgerufen, gibt das erste Argument, das durch den zweiten geteilt. Sie verwenden, geben Sie ein Funktionsobjekt im Hinblick auf den Argumenttyp.

### <a name="syntax"></a>Syntax

```cpp
template<typename Arg>
    ref class divides
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef Arg result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    divides();
    divides(divides<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parameter

*arg*<br/>
Der Typ von den Argumenten und Rückgabewerten.

### <a name="member-functions"></a>Memberfunktionen

|Typdefinition|Beschreibung|
|---------------------|-----------------|
|delegate_type|Der Typ des generischen Delegaten.|
|first_argument_type|Der Typ des ersten Arguments Funktionselement.|
|RESULT_TYPE|Der Typ des Ergebnisses Funktionselement.|
|second_argument_type|Der Typ des zweiten Arguments Funktionselement.|

|Member|Beschreibung|
|------------|-----------------|
|divides|Erstellt das Funktionselement.|

|Operator|Beschreibung|
|--------------|-----------------|
|Operator()|Berechnet die gewünschte Funktion.|
|Operator delegate_type^()|Wandelt das Funktionselement in einen Delegaten an.|

### <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Funktionselement ist zwei Argumenten. Der Memberoperator definiert `operator()` , wenn das Objekt als eine Funktion aufgerufen wird, wird das erste Argument, das durch den zweiten geteilt.

Sie können auch das Objekt übergeben, als Funktionsargument, dessen Typ `delegate_type^` und werden entsprechend konvertiert werden.

### <a name="example"></a>Beispiel

```cpp
// cliext_divides.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(2);
    c2.push_back(1);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 2 1"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::divides<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
2 1
2 3
```

## <a name="equal_to"></a> Equal_to (STL/CLR)

Die Vorlagenklasse beschreibt ein Funktionselement ist, wenn Sie aufgerufen wird, gibt true zurück, nur dann, wenn das erste Argument gleich dem zweiten ist. Sie verwenden, geben Sie ein Funktionsobjekt im Hinblick auf den Argumenttyp.

### <a name="syntax"></a>Syntax

```cpp
template<typename Arg>
    ref class equal_to
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    equal_to();
    equal_to(equal_to<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parameter

*arg*<br/>
Der Typ der Argumente.

### <a name="member-functions"></a>Memberfunktionen

|Typdefinition|Beschreibung|
|---------------------|-----------------|
|delegate_type|Der Typ des generischen Delegaten.|
|first_argument_type|Der Typ des ersten Arguments Funktionselement.|
|RESULT_TYPE|Der Typ des Ergebnisses Funktionselement.|
|second_argument_type|Der Typ des zweiten Arguments Funktionselement.|

|Member|Beschreibung|
|------------|-----------------|
|equal_to|Erstellt das Funktionselement.|

|Operator|Beschreibung|
|--------------|-----------------|
|Operator()|Berechnet die gewünschte Funktion.|
|Operator delegate_type^()|Wandelt das Funktionselement in einen Delegaten an.|

### <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Funktionselement ist zwei Argumenten. Der Memberoperator definiert `operator()` , wenn das Objekt als eine Funktion aufgerufen wird, es gibt nur true zurück, wenn das erste Argument gleich dem zweiten ist.

Sie können auch das Objekt übergeben, als Funktionsargument, dessen Typ `delegate_type^` und werden entsprechend konvertiert werden.

### <a name="example"></a>Beispiel

```cpp
// cliext_equal_to.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::equal_to<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
1 0
```

## <a name="greater"></a> größer (STL/CLR)

Die Vorlagenklasse beschreibt ein Funktionselement ist, wenn aufgerufen, gibt true zurück, nur dann, wenn das erste Argument größer als der zweite ist. Sie verwenden, geben Sie ein Funktionsobjekt im Hinblick auf den Argumenttyp.

### <a name="syntax"></a>Syntax

```cpp
template<typename Arg>
    ref class greater
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    greater();
    greater(greater<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parameter

*arg*<br/>
Der Typ der Argumente.

### <a name="member-functions"></a>Memberfunktionen

|Typdefinition|Beschreibung|
|---------------------|-----------------|
|delegate_type|Der Typ des generischen Delegaten.|
|first_argument_type|Der Typ des ersten Arguments Funktionselement.|
|RESULT_TYPE|Der Typ des Ergebnisses Funktionselement.|
|second_argument_type|Der Typ des zweiten Arguments Funktionselement.|

|Member|Beschreibung|
|------------|-----------------|
|greater|Erstellt das Funktionselement.|

|Operator|Beschreibung|
|--------------|-----------------|
|Operator()|Berechnet die gewünschte Funktion.|
|Operator Delegate_type ^|Wandelt das Funktionselement in einen Delegaten an.|

### <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Funktionselement ist zwei Argumenten. Der Memberoperator definiert `operator()` , wenn das Objekt als eine Funktion aufgerufen wird, es gibt nur true zurück, wenn das erste Argument größer als der zweite ist.

Sie können auch das Objekt übergeben, als Funktionsargument, dessen Typ `delegate_type^` und werden entsprechend konvertiert werden.

### <a name="example"></a>Beispiel

```cpp
// cliext_greater.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(3);
    c2.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 3 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::greater<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
3 3
1 0
```

## <a name="greater_equal"></a> Greater_equal (STL/CLR)

Die Vorlagenklasse beschreibt ein Funktionselement ist, wenn aufgerufen, gibt nur true zurück, wenn das erste Argument größer als oder gleich dem zweiten ist. Sie verwenden, geben Sie ein Funktionsobjekt im Hinblick auf den Argumenttyp.

### <a name="syntax"></a>Syntax

```cpp
template<typename Arg>
    ref class greater_equal
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    greater_equal();
    greater_equal(greater_equal<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parameter

*arg*<br/>
Der Typ der Argumente.

### <a name="member-functions"></a>Memberfunktionen

|Typdefinition|Beschreibung|
|---------------------|-----------------|
|delegate_type|Der Typ des generischen Delegaten.|
|first_argument_type|Der Typ des ersten Arguments Funktionselement.|
|RESULT_TYPE|Der Typ des Ergebnisses Funktionselement.|
|second_argument_type|Der Typ des zweiten Arguments Funktionselement.|

|Member|Beschreibung|
|------------|-----------------|
|greater_equal|Erstellt das Funktionselement.|

|Operator|Beschreibung|
|--------------|-----------------|
|Operator()|Berechnet die gewünschte Funktion.|
|Operator Delegate_type ^|Wandelt das Funktionselement in einen Delegaten an.|

### <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Funktionselement ist zwei Argumenten. Der Memberoperator definiert `operator()` , wenn das Objekt als eine Funktion aufgerufen wird, es gibt nur true zurück, wenn das erste Argument größer als oder gleich dem zweiten ist.

Sie können auch das Objekt übergeben, als Funktionsargument, dessen Typ `delegate_type^` und werden entsprechend konvertiert werden.

### <a name="example"></a>Beispiel

```cpp
// cliext_greater_equal.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::greater_equal<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
1 0
```

## <a name="less"></a> weniger (STL/CLR)

Die Vorlagenklasse beschreibt ein Funktionselement ist, wenn aufgerufen, gibt true zurück, nur dann, wenn das erste Argument kleiner ist als der zweite. Sie verwenden, geben Sie ein Funktionsobjekt im Hinblick auf den Argumenttyp.

### <a name="syntax"></a>Syntax

```cpp
template<typename Arg>
    ref class less
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    less();
    less(less<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parameter

*arg*<br/>
Der Typ der Argumente.

### <a name="member-functions"></a>Memberfunktionen

|Typdefinition|Beschreibung|
|---------------------|-----------------|
|delegate_type|Der Typ des generischen Delegaten.|
|first_argument_type|Der Typ des ersten Arguments Funktionselement.|
|RESULT_TYPE|Der Typ des Ergebnisses Funktionselement.|
|second_argument_type|Der Typ des zweiten Arguments Funktionselement.|

|Member|Beschreibung|
|------------|-----------------|
|less|Erstellt das Funktionselement.|

|Operator|Beschreibung|
|--------------|-----------------|
|Operator()|Berechnet die gewünschte Funktion.|
|Operator Delegate_type ^|Wandelt das Funktionselement in einen Delegaten an.|

### <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Funktionselement ist zwei Argumenten. Der Memberoperator definiert `operator()` , wenn das Objekt als eine Funktion aufgerufen wird, es gibt nur true zurück, wenn das erste Argument kleiner ist als der zweite.

Sie können auch das Objekt übergeben, als Funktionsargument, dessen Typ `delegate_type^` und werden entsprechend konvertiert werden.

### <a name="example"></a>Beispiel

```cpp
// cliext_less.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::less<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
0 1
```

## <a name="less_equal"></a> Less_equal (STL/CLR)

Die Vorlagenklasse beschreibt ein Funktionselement ist, wenn aufgerufen, gibt nur true zurück, wenn das erste Argument kleiner oder gleich dem zweiten ist. Sie verwenden, geben Sie ein Funktionsobjekt im Hinblick auf den Argumenttyp.

### <a name="syntax"></a>Syntax

```cpp
template<typename Arg>
    ref class less_equal
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    less_equal();
    less_equal(less_equal<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parameter

*arg*<br/>
Der Typ der Argumente.

### <a name="member-functions"></a>Memberfunktionen

|Typdefinition|Beschreibung|
|---------------------|-----------------|
|delegate_type|Der Typ des generischen Delegaten.|
|first_argument_type|Der Typ des ersten Arguments Funktionselement.|
|RESULT_TYPE|Der Typ des Ergebnisses Funktionselement.|
|second_argument_type|Der Typ des zweiten Arguments Funktionselement.|

|Member|Beschreibung|
|------------|-----------------|
|less_equal|Erstellt das Funktionselement.|

|Operator|Beschreibung|
|--------------|-----------------|
|Operator()|Berechnet die gewünschte Funktion.|
|Operator Delegate_type ^|Wandelt das Funktionselement in einen Delegaten an.|

### <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Funktionselement ist zwei Argumenten. Der Memberoperator definiert `operator()` , wenn das Objekt als eine Funktion aufgerufen wird, es gibt nur true zurück, wenn das erste Argument kleiner oder gleich dem zweiten ist.

Sie können auch das Objekt übergeben, als Funktionsargument, dessen Typ `delegate_type^` und werden entsprechend konvertiert werden.

### <a name="example"></a>Beispiel

```cpp
// cliext_less_equal.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(3);
    c2.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 3 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::less_equal<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
3 3
0 1
```

## <a name="logical_and"></a> Logical_and (STL/CLR)

Die Vorlagenklasse beschreibt ein Funktionselement ist, wenn aufgerufen, gibt true zurück, nur dann, wenn sowohl das erste Argument und der zweite Test als "true" fest. Sie verwenden, geben Sie ein Funktionsobjekt im Hinblick auf den Argumenttyp.

### <a name="syntax"></a>Syntax

```cpp
template<typename Arg>
    ref class logical_and
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    logical_and();
    logical_and(logical_and<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parameter

*arg*<br/>
Der Typ der Argumente.

### <a name="member-functions"></a>Memberfunktionen

|Typdefinition|Beschreibung|
|---------------------|-----------------|
|delegate_type|Der Typ des generischen Delegaten.|
|first_argument_type|Der Typ des ersten Arguments Funktionselement.|
|RESULT_TYPE|Der Typ des Ergebnisses Funktionselement.|
|second_argument_type|Der Typ des zweiten Arguments Funktionselement.|

|Member|Beschreibung|
|------------|-----------------|
|logical_and|Erstellt das Funktionselement.|

|Operator|Beschreibung|
|--------------|-----------------|
|Operator()|Berechnet die gewünschte Funktion.|
|Operator Delegate_type ^|Wandelt das Funktionselement in einen Delegaten an.|

### <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Funktionselement ist zwei Argumenten. Der Memberoperator definiert `operator()` , wenn das Objekt als eine Funktion aufgerufen wird, es gibt nur true zurück, wenn sowohl das erste Argument und der zweite Test als "true" fest.

Sie können auch das Objekt übergeben, als Funktionsargument, dessen Typ `delegate_type^` und werden entsprechend konvertiert werden.

### <a name="example"></a>Beispiel

```cpp
// cliext_logical_and.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(2);
    c1.push_back(0);
    Myvector c2;
    c2.push_back(3);
    c2.push_back(0);
    Myvector c3(2, 0);

// display initial contents " 1 0" and " 1 0"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::logical_and<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
2 0
3 0
1 0
```

## <a name="logical_not"></a> Logical_not (STL/CLR)

Die Vorlagenklasse beschreibt ein Funktionselement ist, wenn Sie aufgerufen wird, gibt nur dann, wenn entweder "true" Argument "false" überprüft. Sie verwenden, geben Sie ein Funktionsobjekt im Hinblick auf den Argumenttyp.

### <a name="syntax"></a>Syntax

```cpp
template<typename Arg>
    ref class logical_not
    { // wrap operator()
public:
    typedef Arg argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<
        argument_type, result_type>
        delegate_type;

    logical_not();
    logical_not(logical_not<Arg> %right);

    result_type operator()(argument_type left);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parameter

*arg*<br/>
Der Typ der Argumente.

### <a name="member-functions"></a>Memberfunktionen

|Typdefinition|Beschreibung|
|---------------------|-----------------|
|argument_type|Der Typ des Arguments Funktionselement.|
|delegate_type|Der Typ des generischen Delegaten.|
|RESULT_TYPE|Der Typ des Ergebnisses Funktionselement.|

|Member|Beschreibung|
|------------|-----------------|
|logical_not|Erstellt das Funktionselement.|

|Operator|Beschreibung|
|--------------|-----------------|
|Operator()|Berechnet die gewünschte Funktion.|
|Operator Delegate_type ^|Wandelt das Funktionselement in einen Delegaten an.|

### <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Funktionselement ist einem Argument. Der Memberoperator definiert `operator()` , wenn das Objekt als eine Funktion aufgerufen wird, es gibt nur true zurück, wenn das Argument als "false" überprüft.

Sie können auch das Objekt übergeben, als Funktionsargument, dessen Typ `delegate_type^` und werden entsprechend konvertiert werden.

### <a name="example"></a>Beispiel

```cpp
// cliext_logical_not.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(0);
    Myvector c3(2, 0);

// display initial contents " 4 0"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c3.begin(), cliext::logical_not<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 0
0 1
```

## <a name="logical_or"></a> Logical_or (STL/CLR)

Die Vorlagenklasse beschreibt ein Funktionselement ist, wenn aufgerufen, gibt true zurück, nur dann, wenn entweder das erste Argument oder die zweite Tests als "true" fest. Sie verwenden, geben Sie ein Funktionsobjekt im Hinblick auf den Argumenttyp.

### <a name="syntax"></a>Syntax

```cpp
template<typename Arg>
    ref class logical_or
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    logical_or();
    logical_or(logical_or<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parameter

*arg*<br/>
Der Typ der Argumente.

### <a name="member-functions"></a>Memberfunktionen

|Typdefinition|Beschreibung|
|---------------------|-----------------|
|delegate_type|Der Typ des generischen Delegaten.|
|first_argument_type|Der Typ des ersten Arguments Funktionselement.|
|RESULT_TYPE|Der Typ des Ergebnisses Funktionselement.|
|second_argument_type|Der Typ des zweiten Arguments Funktionselement.|

|Member|Beschreibung|
|------------|-----------------|
|logical_or|Erstellt das Funktionselement.|

|Operator|Beschreibung|
|--------------|-----------------|
|Operator()|Berechnet die gewünschte Funktion.|
|Operator Delegate_type ^|Wandelt das Funktionselement in einen Delegaten an.|

### <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Funktionselement ist zwei Argumenten. Der Memberoperator definiert `operator()` , wenn das Objekt als eine Funktion aufgerufen wird, es gibt nur true zurück, wenn entweder das erste Argument oder die zweite Tests als "true" fest.

Sie können auch das Objekt übergeben, als Funktionsargument, dessen Typ `delegate_type^` und werden entsprechend konvertiert werden.

### <a name="example"></a>Beispiel

```cpp
// cliext_logical_or.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(2);
    c1.push_back(0);
    Myvector c2;
    c2.push_back(0);
    c2.push_back(0);
    Myvector c3(2, 0);

// display initial contents " 2 0" and " 0 0"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::logical_or<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
2 0
0 0
1 0
```

## <a name="minus"></a> Minus (STL/CLR)

Die Vorlagenklasse beschreibt ein Funktionselement ist, wenn aufgerufen, gibt das erste Argument minus der zweite. Sie verwenden, geben Sie ein Funktionsobjekt im Hinblick auf den Argumenttyp.

### <a name="syntax"></a>Syntax

```cpp
template<typename Arg>
    ref class minus
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef Arg result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    minus();
    minus(minus<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parameter

*arg*<br/>
Der Typ von den Argumenten und Rückgabewerten.

### <a name="member-functions"></a>Memberfunktionen

|Typdefinition|Beschreibung|
|---------------------|-----------------|
|delegate_type|Der Typ des generischen Delegaten.|
|first_argument_type|Der Typ des ersten Arguments Funktionselement.|
|RESULT_TYPE|Der Typ des Ergebnisses Funktionselement.|
|second_argument_type|Der Typ des zweiten Arguments Funktionselement.|

|Member|Beschreibung|
|------------|-----------------|
|minus|Erstellt das Funktionselement.|

|Operator|Beschreibung|
|--------------|-----------------|
|Operator()|Berechnet die gewünschte Funktion.|
|Operator Delegate_type ^|Wandelt das Funktionselement in einen Delegaten an.|

### <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Funktionselement ist zwei Argumenten. Der Memberoperator definiert `operator()` , wenn das Objekt als eine Funktion aufgerufen wird, wird das erste Argument minus der zweite.

Sie können auch das Objekt übergeben, als Funktionsargument, dessen Typ `delegate_type^` und werden entsprechend konvertiert werden.

### <a name="example"></a>Beispiel

```cpp
// cliext_minus.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(2);
    c2.push_back(1);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 2 1"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::minus<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
2 1
2 2
```

## <a name="modulus"></a> Modulo (STL/CLR)

Die Vorlagenklasse beschreibt ein Funktionselement ist, wenn aufgerufen, gibt das erste Argument modulo das zweite. Sie verwenden, geben Sie ein Funktionsobjekt im Hinblick auf den Argumenttyp.

### <a name="syntax"></a>Syntax

```cpp
template<typename Arg>
    ref class modulus
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef Arg result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    modulus();
    modulus(modulus<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parameter

*arg*<br/>
Der Typ von den Argumenten und Rückgabewerten.

### <a name="member-functions"></a>Memberfunktionen

|Typdefinition|Beschreibung|
|---------------------|-----------------|
|delegate_type|Der Typ des generischen Delegaten.|
|first_argument_type|Der Typ des ersten Arguments Funktionselement.|
|RESULT_TYPE|Der Typ des Ergebnisses Funktionselement.|
|second_argument_type|Der Typ des zweiten Arguments Funktionselement.|

|Member|Beschreibung|
|------------|-----------------|
|modulus|Erstellt das Funktionselement.|

|Operator|Beschreibung|
|--------------|-----------------|
|Operator()|Berechnet die gewünschte Funktion.|
|Operator Delegate_type ^|Wandelt das Funktionselement in einen Delegaten an.|

### <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Funktionselement ist zwei Argumenten. Der Memberoperator definiert `operator()` , wenn das Objekt als eine Funktion aufgerufen wird, wird das erste Argument modulo das zweite.

Sie können auch das Objekt übergeben, als Funktionsargument, dessen Typ `delegate_type^` und werden entsprechend konvertiert werden.

### <a name="example"></a>Beispiel

```cpp
// cliext_modulus.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(2);
    Myvector c2;
    c2.push_back(3);
    c2.push_back(1);
    Myvector c3(2, 0);

// display initial contents " 4 2" and " 3 1"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::modulus<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 2
3 1
1 0
```

## <a name="multiplies"></a> multipliziert (STL/CLR)

Die Vorlagenklasse beschreibt ein Funktionselement ist, wenn aufgerufen, gibt das erste Argument multipliziert die zweite. Sie verwenden, geben Sie ein Funktionsobjekt im Hinblick auf den Argumenttyp.

### <a name="syntax"></a>Syntax

```cpp
template<typename Arg>
    ref class multiplies
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef Arg result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    multiplies();
    multiplies(multiplies<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parameter

*arg*<br/>
Der Typ von den Argumenten und Rückgabewerten.

### <a name="member-functions"></a>Memberfunktionen

|Typdefinition|Beschreibung|
|---------------------|-----------------|
|delegate_type|Der Typ des generischen Delegaten.|
|first_argument_type|Der Typ des ersten Arguments Funktionselement.|
|RESULT_TYPE|Der Typ des Ergebnisses Funktionselement.|
|second_argument_type|Der Typ des zweiten Arguments Funktionselement.|

|Member|Beschreibung|
|------------|-----------------|
|multiplies|Erstellt das Funktionselement.|

|Operator|Beschreibung|
|--------------|-----------------|
|Operator()|Berechnet die gewünschte Funktion.|
|Operator Delegate_type ^|Wandelt das Funktionselement in einen Delegaten an.|

### <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Funktionselement ist zwei Argumenten. Der Memberoperator definiert `operator()` , wenn das Objekt als eine Funktion aufgerufen wird, wird das erste Argument multipliziert die zweite.

Sie können auch das Objekt übergeben, als Funktionsargument, dessen Typ `delegate_type^` und werden entsprechend konvertiert werden.

### <a name="example"></a>Beispiel

```cpp
// cliext_multiplies.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(2);
    c2.push_back(1);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 2 1"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::multiplies<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
2 1
8 3
```

## <a name="negate"></a> Negation (STL/CLR)

Die Vorlagenklasse beschreibt ein Funktionselement ist, die beim Aufruf gibt Arguments negiert. Sie verwenden, geben Sie ein Funktionsobjekt im Hinblick auf den Argumenttyp.

### <a name="syntax"></a>Syntax

```cpp
template<typename Arg>
    ref class negate
    { // wrap operator()
public:
    typedef Arg argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<
        argument_type, result_type>
        delegate_type;

    negate();
    negate(negate<Arg>% right);

    result_type operator()(argument_type left);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parameter

*arg*<br/>
Der Typ der Argumente.

### <a name="member-functions"></a>Memberfunktionen

|Typdefinition|Beschreibung|
|---------------------|-----------------|
|argument_type|Der Typ des Arguments Funktionselement.|
|delegate_type|Der Typ des generischen Delegaten.|
|RESULT_TYPE|Der Typ des Ergebnisses Funktionselement.|

|Member|Beschreibung|
|------------|-----------------|
|negate|Erstellt das Funktionselement.|

|Operator|Beschreibung|
|--------------|-----------------|
|Operator()|Berechnet die gewünschte Funktion.|
|Operator Delegate_type ^|Wandelt das Funktionselement in einen Delegaten an.|

### <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Funktionselement ist einem Argument. Der Memberoperator definiert `operator()` , wenn das Objekt als eine Funktion aufgerufen wird, wird das Argument, das negiert.

Sie können auch das Objekt übergeben, als Funktionsargument, dessen Typ `delegate_type^` und werden entsprechend konvertiert werden.

### <a name="example"></a>Beispiel

```cpp
// cliext_negate.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(-3);
    Myvector c3(2, 0);

// display initial contents " 4 -3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c3.begin(), cliext::negate<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 -3
-4 3
```

## <a name="not_equal_to"></a> Not_Equal_To (STL/CLR)

Die Vorlagenklasse beschreibt ein Funktionselement ist, wenn aufgerufen, gibt "true" fest, wenn das erste Argument nicht gleich dem zweiten. Sie verwenden, geben Sie ein Funktionsobjekt im Hinblick auf den Argumenttyp.

### <a name="syntax"></a>Syntax

```cpp
template<typename Arg>
    ref class not_equal_to
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    not_equal_to();
    not_equal_to(not_equal_to<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parameter

*arg*<br/>
Der Typ der Argumente.

### <a name="member-functions"></a>Memberfunktionen

|Typdefinition|Beschreibung|
|---------------------|-----------------|
|delegate_type|Der Typ des generischen Delegaten.|
|first_argument_type|Der Typ des ersten Arguments Funktionselement.|
|RESULT_TYPE|Der Typ des Ergebnisses Funktionselement.|
|second_argument_type|Der Typ des zweiten Arguments Funktionselement.|

|Member|Beschreibung|
|------------|-----------------|
|not_equal_to|Erstellt das Funktionselement.|

|Operator|Beschreibung|
|--------------|-----------------|
|Operator()|Berechnet die gewünschte Funktion.|
|Operator Delegate_type ^|Wandelt das Funktionselement in einen Delegaten an.|

### <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Funktionselement ist zwei Argumenten. Der Memberoperator definiert `operator()` , wenn das Objekt als eine Funktion aufgerufen wird, es gibt nur true zurück, wenn das erste Argument nicht gleich dem zweiten ist.

Sie können auch das Objekt übergeben, als Funktionsargument, dessen Typ `delegate_type^` und werden entsprechend konvertiert werden.

### <a name="example"></a>Beispiel

```cpp
// cliext_not_equal_to.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::not_equal_to<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
0 1
```

## <a name="not1"></a> not1 (STL/CLR)

Generiert eine `unary_negate` für ein Funktionselement ist.

### <a name="syntax"></a>Syntax

```cpp
template<typename Fun>
    unary_negate<Fun> not1(Fun% functor);
```

#### <a name="template-parameters"></a>Vorlagenparameter

*Spaß*<br/>
Der Typ der zu kennen.

#### <a name="function-parameters"></a>Funktionsparameter

*Funktionselement*<br/>
Das Funktionselement umschlossen werden soll.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion gibt [Unary_negate (STL/CLR)](../dotnet/unary-negate-stl-clr.md)`<Fun>(functor)`. Sie verwenden es als eine einfache Möglichkeit, ein Funktionselement ist einem Argument in ein Funktionselement zu umschließen, die logische nicht bietet.

### <a name="example"></a>Beispiel

```cpp
// cliext_not1.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(0);
    Myvector c3(2, 0);

// display initial contents " 4 0"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::logical_not<int> not_op;

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        cliext::unary_negate<cliext::logical_not<int> >(not_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        cliext::not1(not_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 0
1 0
1 0
```

## <a name="not2"></a> not2 (STL/CLR)

Generiert eine `binary_negate` für ein Funktionselement ist.

### <a name="syntax"></a>Syntax

```cpp
template<typename Fun>
    binary_negate<Fun> not2(Fun% functor);
```

#### <a name="template-parameters"></a>Vorlagenparameter

*Spaß*<br/>
Der Typ der zu kennen.

#### <a name="function-parameters"></a>Funktionsparameter

*Funktionselement*<br/>
Das Funktionselement umschlossen werden soll.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion gibt [Binary_negate (STL/CLR)](../dotnet/binary-negate-stl-clr.md)`<Fun>(functor)`. Sie verwenden es als eine einfache Möglichkeit, ein Funktionselement ist zwei Argumenten in ein Funktionselement zu umschließen, die logische nicht bietet.

### <a name="example"></a>Beispiel

```cpp
// cliext_not2.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::less<int> less_op;

    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(),
        cliext::binary_negate<cliext::less<int> >(less_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::not2(less_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
1 0
1 0
```

## <a name="plus"></a> Plus (STL/CLR)

Die Vorlagenklasse beschreibt ein Funktionselement ist, wenn aufgerufen, gibt das erste Argument und der zweite. Sie verwenden, geben Sie ein Funktionsobjekt im Hinblick auf den Argumenttyp.

### <a name="syntax"></a>Syntax

```cpp
template<typename Arg>
    ref class plus
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef Arg result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    plus();
    plus(plus<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parameter

*arg*<br/>
Der Typ von den Argumenten und Rückgabewerten.

### <a name="member-functions"></a>Memberfunktionen

|Typdefinition|Beschreibung|
|---------------------|-----------------|
|delegate_type|Der Typ des generischen Delegaten.|
|first_argument_type|Der Typ des ersten Arguments Funktionselement.|
|RESULT_TYPE|Der Typ des Ergebnisses Funktionselement.|
|second_argument_type|Der Typ des zweiten Arguments Funktionselement.|

|Member|Beschreibung|
|------------|-----------------|
|plus|Erstellt das Funktionselement.|

|Operator|Beschreibung|
|--------------|-----------------|
|Operator()|Berechnet die gewünschte Funktion.|
|Operator Delegate_type ^|Wandelt das Funktionselement in einen Delegaten an.|

### <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Funktionselement ist zwei Argumenten. Der Memberoperator definiert `operator()` , wenn das Objekt als eine Funktion aufgerufen wird, wird das erste Argument und der zweite.

Sie können auch das Objekt übergeben, als Funktionsargument, dessen Typ `delegate_type^` und werden entsprechend konvertiert werden.

### <a name="example"></a>Beispiel

```cpp
// cliext_plus.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(2);
    c2.push_back(1);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 2 1"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::plus<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
2 1
6 4
```

## <a name="unary_delegate"></a> Unary_delegate (STL/CLR)

Die Genereic-Klasse beschreibt einen Delegaten mit einem Argument. Sie verwenden, geben Sie einen Delegaten in Bezug auf die Argument- und Rückgabetypen-Typen.

### <a name="syntax"></a>Syntax

```cpp
generic<typename Arg,
    typename Result>
    delegate Result unary_delegate(Arg);
```

#### <a name="parameters"></a>Parameter

*arg*<br/>
Der Typ des Arguments.

*Ergebnis*<br/>
Der Rückgabetyp.

### <a name="remarks"></a>Hinweise

Der Delegat Genereic beschreibt eine Funktion von einem Argument.

Beachten Sie, dass für:

`unary_delegare<int, int> Fun1;`

`unary_delegare<int, int> Fun2;`

die Typen `Fun1` und `Fun2` sind Synonyme, während er sich für:

`delegate int Fun1(int);`

`delegate int Fun2(int);`

Sie sind nicht den gleichen Typ.

### <a name="example"></a>Beispiel

```cpp
// cliext_unary_delegate.cpp
// compile with: /clr
#include <cliext/functional>

int hash_val(wchar_t val)
    {
    return ((val * 17 + 31) % 67);
    }

typedef cliext::unary_delegate<wchar_t, int> Mydelegate;
int main()
    {
    Mydelegate^ myhash = gcnew Mydelegate(&hash_val);

    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));
    return (0);
    }
```

```Output
hash(L'a') = 5
hash(L'b') = 22
```

## <a name="unary_delegate_noreturn"></a> Unary_delegate_noreturn (STL/CLR)

Die Genereic-Klasse beschreibt einen Delegaten mit einem Argument, das zurückgibt **"void"**. Sie verwenden, geben Sie einen Delegaten in Bezug auf den Argumenttyp.

### <a name="syntax"></a>Syntax

```cpp
generic<typename Arg>
    delegate void unary_delegate_noreturn(Arg);
```

#### <a name="parameters"></a>Parameter

*arg*<br/>
Der Typ des Arguments.

### <a name="remarks"></a>Hinweise

Der Delegat Genereic beschreibt eine Funktion von einem Argument, zurückgibt **"void"**.

Beachten Sie, dass für:

`unary_delegare_noreturn<int> Fun1;`

`unary_delegare_noreturn<int> Fun2;`

die Typen `Fun1` und `Fun2` sind Synonyme, während er sich für:

`delegate void Fun1(int);`

`delegate void Fun2(int);`

Sie sind nicht den gleichen Typ.

### <a name="example"></a>Beispiel

```cpp
// cliext_unary_delegate_noreturn.cpp
// compile with: /clr
#include <cliext/functional>

void hash_val(wchar_t val)
    {
    System::Console::WriteLine("hash({0}) = {1}",
       val, (val * 17 + 31) % 67);
    }

typedef cliext::unary_delegate_noreturn<wchar_t> Mydelegate;
int main()
    {
    Mydelegate^ myhash = gcnew Mydelegate(&hash_val);

    myhash(L'a');
    myhash(L'b');
    return (0);
    }
```

```Output
hash(a) = 5
hash(b) = 22
```

## <a name="unary_negate"></a> Unary_negate (STL/CLR)

Die Vorlagenklasse beschreibt ein Funktionselement ist, die beim Aufruf gibt die logische nicht von der gespeicherten Funktionselement mit einem Argument. Sie verwenden, geben Sie ein Funktionsobjekt im Hinblick auf seine gespeicherten Funktionselement.

### <a name="syntax"></a>Syntax

```cpp
template<typename Fun>
    ref class unary_negate
    { // wrap operator()
public:
    typedef Fun stored_function_type;
    typedef typename Fun::argument_type argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<
        argument_type, result_type>
        delegate_type;

    unary_negate(Fun% functor);
    unary_negate(unary_negate<Fun>% right);

    result_type operator()(argument_type left);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>Parameter

*Spaß*<br/>
Der Typ der gespeicherten kennen.

### <a name="member-functions"></a>Memberfunktionen

|Typdefinition|Beschreibung|
|---------------------|-----------------|
|argument_type|Der Typ des Arguments Funktionselement.|
|delegate_type|Der Typ des generischen Delegaten.|
|RESULT_TYPE|Der Typ des Ergebnisses Funktionselement.|

|Member|Beschreibung|
|------------|-----------------|
|unary_negate|Erstellt das Funktionselement.|

|Operator|Beschreibung|
|--------------|-----------------|
|Operator()|Berechnet die gewünschte Funktion.|
|Delegate_type ^|Wandelt das Funktionselement in einen Delegaten an.|

### <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Funktionselement ist einem Argument, das eine andere einem Argument Funktionselement speichert. Der Memberoperator definiert `operator()` , wenn das Objekt als eine Funktion aufgerufen wird, gibt die logische nicht der gespeicherten kennen, die mit dem Argument aufgerufen.

Sie können auch das Objekt übergeben, als Funktionsargument, dessen Typ `delegate_type^` und werden entsprechend konvertiert werden.

### <a name="example"></a>Beispiel

```cpp
// cliext_unary_negate.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(0);
    Myvector c3(2, 0);

// display initial contents " 4 0"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::logical_not<int> not_op;

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        cliext::unary_negate<cliext::logical_not<int> >(not_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        cliext::not1(not_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 0
1 0
1 0
```