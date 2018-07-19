---
title: Hilfsprogramm (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- <cliext/utility>
- cliext::pair
- cliext::pair::pair
- cliext::pair::first
- cliext::pair::first_type
- cliext::pair::second
- cliext::pair::second_type
- cliext::pair::swap
- cliext::make_pair
- cliext::pair::operator=
- cliext::pair::operator==
- cliext::pair::operator>=
- cliext::pair::operator>
- cliext::pair::operator!=
- cliext::pair::operator<=
- cliext::pair::operator<
dev_langs:
- C++
helpviewer_keywords:
- <utility> header [STL/CLR]
- utility header [STL/CLR]
- <cliext/utility> header [STL/CLR]
- first member [STL/CLR]
- first_type member [STL/CLR]
- second member [STL/CLR]
- second_type member [STL/CLR]
- swap member [STL/CLR]
- make_pair function [STL/CLR]
- pair class [STL/CLR]
- pair member [STL/CLR]
- operator== member [STL/CLR]
- operator= member [STL/CLR]
- operator>= member [STL/CLR]
- operator> member [STL/CLR]
- operator!= member [STL/CLR]
- operator<= member [STL/CLR]
- operator< member [STL/CLR]
ms.assetid: fb48cb75-d5ef-47ce-b526-bf60dc86c552
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fcc97e5037898b3a9c39a6c72ed21b2c19a4c777
ms.sourcegitcommit: 301bb19056e5bae84ff50f7d1df1e546efe225ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/21/2018
ms.locfileid: "36306020"
---
# <a name="utility-stlclr"></a>utility (STL/CLR)
Fügen Sie den STL/CLR-Header `<cliext/utility>` definiert die Vorlagenklasse `pair` und mehrere unterstützende Vorlagenfunktionen.  
  
## <a name="syntax"></a>Syntax  
  
```  
#include <utility>  
```

## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext-Hilfsprogramm >  
  
 **Namespace:** Cliext  
  
## <a name="declarations"></a>Deklarationen  
  
|Klasse|Beschreibung|  
|-----------|-----------------|  
|[pair (STL/CLR)](#pair)|Ein Paar von Elementen zu umschließen.|  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[operator== (pair) (STL/CLR)](#op_eq)|Paar gleich Vergleich.|  
|[operator!= (pair) (STL/CLR)](#op_neq)|Kombinieren Sie nicht gleich Vergleich.|  
|[operator< (pair) (STL/CLR)](#op_lt)|Paar kleiner-als-Vergleich.|  
|[Operator\<= (Paar) (STL/CLR)](#op_lteq)|Koppeln Sie kleiner oder gleich Vergleich.|  
|[operator> (pair) (STL/CLR)](#op_gt)|Das Paar ist größer als-Vergleich.|  
|[operator>= (pair) (STL/CLR)](#op_gteq)|Paar größer als oder gleich Vergleich.|  
  
|Funktion|Beschreibung|  
|--------------|-----------------|  
|[make_pair (STL/CLR)](#make_pair)|Stellen Sie ein Paar aus einem Paar von Werten.|  

## <a name="members"></a>Member

##<a name="pair"></a> Paar (STL/CLR)
Die Vorlagenklasse beschreibt ein Objekt, das ein Wertepaar umschließt.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<typename Value1,  
    typename Value2>  
    ref class pair;  
```  
  
#### <a name="parameters"></a>Parameter  
 Wert1  
 Der Typ des ersten einem Wrapper versehene Wert.  
  
 Value2  
 Der Typ des zweiten einem Wrapper versehene Wert.  
  
## <a name="members"></a>Member  
  
|Typdefinition|Beschreibung|  
|---------------------|-----------------|  
|[pair::first_type (STL/CLR)](#first_type)|Der Typ des ersten umschlossene Werts.|  
|[pair::second_type (STL/CLR)](#second_type)|Der Typ des umschlossenen Sekundenwert.|  
  
|Member-Objekt|Beschreibung|  
|-------------------|-----------------|  
|[pair::first (STL/CLR)](#first)|Der erste gespeicherte Wert.|  
|[pair::second (STL/CLR)](#second)|Der zweite gespeicherte Wert.|  
  
|Memberfunktion|Beschreibung|  
|---------------------|-----------------|  
|[pair::pair (STL/CLR)](#pair_pair)|Erstellt ein paarobjekt.|  
|[pair::swap (STL/CLR)](#swap)|Vertauscht den Inhalt von zwei Wertepaaren.|  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[pair::operator= (STL/CLR)](#op_as)|Ersetzt das gespeicherte Paar von Werten an.|  
  
## <a name="remarks"></a>Hinweise  
 Das Objekt speichert ein Paar von Werten. Um zwei Werte zu einem einzigen Objekt kombiniert werden. verwenden Sie diese Vorlagenklasse. Darüber hinaus das Objekt `cliext::pair` (hier beschriebenen) speichert nur von verwalteten Typen; verwenden Sie zum Speichern von ein Paar von nicht verwalteten Typen `std::pair`, die im deklariert `<utility>`.  


## <a name="first"></a> Pair::First (STL/CLR)
Der erste umschlossene Wert.  
  
### <a name="syntax"></a>Syntax  
  
```  
Value1 first;  
```  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt speichert den ersten Wert des umschlossenen.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_pair_first.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    cliext::pair<wchar_t, int>::first_type first_val = c1.first;   
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;   
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
```  

## <a name="first_type"></a> Pair::first_type (STL/CLR)
Der Typ des ersten umschlossene Werts.  
  
### <a name="syntax"></a>Syntax  
  
```  
typedef Value1 first_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Type stellt ein Synonym für den Vorlagenparameter `Value1` dar.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_pair_first_type.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    cliext::pair<wchar_t, int>::first_type first_val = c1.first;   
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;   
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
```  

## <a name="op_as"></a> Pair:: Operator = (STL/CLR)
Ersetzt das gespeicherte Paar von Werten an.  
  
### <a name="syntax"></a>Syntax  
  
```  
pair<Value1, Value2>% operator=(pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 Rechts  
 Paar kopiert.  
  
### <a name="remarks"></a>Hinweise  
 Die Member-Operator Kopien `right` klicken Sie dann auf das Objekt gibt `*this`. Sie nutzen, um das gespeicherte Paar von Werten mit einer Kopie der gespeicherten Wertpaar in ersetzen `right`.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_pair_operator_as.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
// assign to a new pair   
    cliext::pair<wchar_t, int> c2;   
    c2 = c1;   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 3]  
```  

## <a name="pair_pair"></a> Pair:: Pair (STL/CLR)
Erstellt ein paarobjekt.  
  
### <a name="syntax"></a>Syntax  
  
```  
pair();  
pair(pair<Coll>% right);  
pair(pair<Coll>^ right);  
pair(Value1 val1, Value2 val2);  
```  
  
#### <a name="parameters"></a>Parameter  
 Rechts  
 Paar zu speichern.  
  
 val1  
 Erste der zu speichernden Werts.  
  
 Wert2  
 Zweiter Wert, zu speichern.  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor:  
  
 `pair();`  
  
 Initialisiert die gespeicherte Paar mit den Standardwerten erstellt.  
  
 Der Konstruktor:  
  
 `pair(pair<Value1, Value2>% right);`  
  
 Initialisiert den gespeicherten-Paar mit `right.` [pair::first (STL/CLR)](../dotnet/pair-first-stl-clr.md) und `right.` [Pair:: Second (STL/CLR)](../dotnet/pair-second-stl-clr.md).  
  
 `pair(pair<Value1, Value2>^ right);`  
  
 Initialisiert den gespeicherten-Paar mit `right->` [pair::first (STL/CLR)](../dotnet/pair-first-stl-clr.md) und `right>` [Pair:: Second (STL/CLR)](../dotnet/pair-second-stl-clr.md).  
  
 Der Konstruktor:  
  
 `pair(Value1 val1, Value2 val2);`  
  
 Initialisiert die gespeicherte Paar mit mit `val1` und `val2`.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_pair_construct.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
// construct an empty container   
    cliext::pair<wchar_t, int> c1;   
    System::Console::WriteLine("[{0}, {1}]",   
        c1.first == L'\0' ? "\\0" : "??", c1.second);   
  
// construct with a pair of values   
    cliext::pair<wchar_t, int> c2(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
// construct by copying another pair   
    cliext::pair<wchar_t, int> c3(c2);   
    System::Console::WriteLine("[{0}, {1}]", c3.first, c3.second);   
  
// construct by copying a pair handle   
    cliext::pair<wchar_t, int> c4(%c3);   
    System::Console::WriteLine("[{0}, {1}]", c4.first, c4.second);   
  
    return (0);   
    }  
  
```  
  
```Output  
[\0, 0]  
[x, 3]  
[x, 3]  
[x, 3]  
```  

## <a name="second"></a> Pair:: Second (STL/CLR)
Die zweite umschlossen Wert.  
  
### <a name="syntax"></a>Syntax  
  
```  
Value2 second;  
```  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt speichert die umschlossenen Sekundenwert.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_pair_second.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    cliext::pair<wchar_t, int>::first_type first_val = c1.first;   
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;   
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
```  

## <a name="second_type"></a> Pair::second_type (STL/CLR)
Der Typ des umschlossenen Sekundenwert.  
  
### <a name="syntax"></a>Syntax  
  
```  
typedef Value2 second_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Type stellt ein Synonym für den Vorlagenparameter `Value2` dar.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_pair_second_type.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    cliext::pair<wchar_t, int>::first_type first_val = c1.first;   
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;   
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
```    

## <a name="swap"></a> Pair:: Swap (STL/CLR)
Vertauscht den Inhalt von zwei Wertepaaren.  
  
### <a name="syntax"></a>Syntax  
  
```  
void swap(pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 Rechts  
 Paar, das Inhalt mit austauschen.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion tauscht den gespeicherten Wertepaar zwischen `*this` und `right`.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_pair_swap.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    cliext::deque<wchar_t> d2(5, L'x');   
    Mycoll c2(%d2);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// swap and redisplay   
    c1.swap(c2);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
x x x x x  
x x x x x  
a b c  
```  

## <a name="make_pair"></a> Make_pair (STL/CLR)
Stellen Sie eine `pair` aus einem Paar von Werten.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<typename Value1,  
    typename Value2>  
    pair<Value1, Value2> make_pair(Value1 first, Value2 second);  
```  
  
#### <a name="parameters"></a>Parameter  
 `Value1`  
 Der Typ des ersten umschlossene Werts.  
  
 `Value2`  
 Der Typ des umschlossenen Sekundenwert.  
  
 `first`  
 Erste der zu umschließende Wert.  
  
 `second`  
 Zweiter Wert, zu umschließen.  
  
### <a name="remarks"></a>Hinweise  
 Die Vorlagenfunktion gibt `pair<Value1, Value2>(first, second)` zurück. Sie verwenden sie zum Erstellen einer `pair<Value1, Value2>` Objekt aus einem Paar von Werten.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_make_pair.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    c1 = cliext::make_pair(L'y', 4);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[y, 4]  
```  

## <a name="op_neq"></a> Operator! = (Paar) (STL/CLR)
Kombinieren Sie nicht gleich Vergleich.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator!=(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 links  
 Linke Paar, das verglichen werden soll.  
  
 Rechts  
 Rechts-Paar, das verglichen werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Gibt die Operatorfunktion `!(left == right)`. Sie zum Testen verwenden, ob `left` nicht sortiert wird, ist identisch mit `right` bei der beiden Paare verglichenen elementweise sind.  
  
### <a name="example"></a>Beispiel  
  
```cpp
// cliext_pair_operator_ne.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] != [x 3] is {0}",   
        c1 != c1);   
    System::Console::WriteLine("[x 3] != [x 4] is {0}",   
        c1 != c2);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] != [x 3] is False  
[x 3] != [x 4] is True  
```  
  
## <a name="op_lt"></a> Operator&lt; (Paar) (STL/CLR)
Paar kleiner-als-Vergleich.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator<(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 links  
 Linke Paar, das verglichen werden soll.  
  
 Rechts  
 Rechts-Paar, das verglichen werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Gibt die Operatorfunktion `left.first <` `right.first || !(right.first <` `left.first &&` `left.second <` `right.second`. Sie zum Testen verwenden, ob `left` sortiert wird, ist die vor dem `right` bei der beiden Paare verglichenen elementweise sind.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_pair_operator_lt.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] < [x 3] is {0}",   
        c1 < c1);   
    System::Console::WriteLine("[x 3] < [x 4] is {0}",   
        c1 < c2);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] < [x 3] is False  
[x 3] < [x 4] is True  
```  

## <a name="op_lteq"></a> Operator&lt;= (Paar) (STL/CLR)
Koppeln Sie kleiner oder gleich Vergleich.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator<=(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 links  
 Linke Paar, das verglichen werden soll.  
  
 Rechts  
 Rechts-Paar, das verglichen werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Gibt die Operatorfunktion `!(right < left)`. Sie zum Testen verwenden, ob `left` ist nicht geordnet nach `right` bei der beiden Paare verglichenen elementweise sind.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_pair_operator_le.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] <= [x 3] is {0}",   
        c1 <= c1);   
    System::Console::WriteLine("[x 4] <= [x 3] is {0}",   
        c2 <= c1);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] <= [x 3] is True  
[x 4] <= [x 3] is False  
```  
  
## <a name="op_eq"></a> Operator == (Paar) (STL/CLR)
Paar gleich Vergleich.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator==(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 links  
 Linke Paar, das verglichen werden soll.  
  
 Rechts  
 Rechts-Paar, das verglichen werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Gibt die Operatorfunktion `left.first ==` `right.first &&` `left.second ==` `right.second`. Verwenden sie zum Testen, ob `left` sortiert wird, ist identisch mit `right` bei der beiden Paare verglichenen elementweise sind.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_pair_operator_eq.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] == [x 3] is {0}",   
        c1 == c1);   
    System::Console::WriteLine("[x 3] == [x 4] is {0}",   
        c1 == c2);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] == [x 3] is True  
[x 3] == [x 4] is False  
```  

## <a name="op_gt"></a> Operator&gt; (Paar) (STL/CLR)
Das Paar ist größer als-Vergleich.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator>(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 links  
 Linke Paar, das verglichen werden soll.  
  
 Rechts  
 Rechts-Paar, das verglichen werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Gibt die Operatorfunktion `right` `<` `left`. Sie zum Testen verwenden, ob `left` sortiert wird, ist nach `right` bei der beiden Paare verglichenen elementweise sind.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_pair_operator_gt.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] > [x 3] is {0}",   
        c1 > c1);   
    System::Console::WriteLine("[x 4] > [x 3] is {0}",   
        c2 > c1);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] > [x 3] is False  
[x 4] > [x 3] is True  
```  

## <a name="op_gteq"></a> Operator&gt;= (Paar) (STL/CLR)
Paar größer als oder gleich Vergleich.  
  
### <a name="syntax"></a>Syntax  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator>=(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>Parameter  
 links  
 Linke Paar, das verglichen werden soll.  
  
 Rechts  
 Rechts-Paar, das verglichen werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Gibt die Operatorfunktion `!(left < right)`. Sie verwenden es, um zu testen, ob `left` nicht sortiert ist `right` bei der beiden Paare verglichenen elementweise sind.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// cliext_pair_operator_ge.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] >= [x 3] is {0}",   
        c1 >= c1);   
    System::Console::WriteLine("[x 3] >= [x 4] is {0}",   
        c1 >= c2);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] >= [x 3] is True  
[x 3] >= [x 4] is False  
```  
