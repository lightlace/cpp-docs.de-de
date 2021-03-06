---
title: '&lt;utility&gt;-Funktionen'
ms.date: 11/04/2016
f1_keywords:
- utility/std::exchange
- utility/std::forward
- utility/std::make_pair
- utility/std::move
- utility/std::swap
ms.assetid: b1df38cd-3a59-4098-9c81-83342eb719a4
helpviewer_keywords:
- std::exchange [C++]
- std::forward [C++]
- std::make_pair [C++]
- std::move [C++]
- std::swap [C++]
ms.openlocfilehash: 723b077500b9b741445efcd8574fb26cd53e5fc7
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246311"
---
# <a name="ltutilitygt-functions"></a>&lt;utility&gt;-Funktionen

## <a name="asconst"></a> as_const

```cpp
template <class T> constexpr add_const_t<T>& as_const(T& t) noexcept;
template <class T> void as_const(const T&&) = delete;
```

### <a name="return-value"></a>Rückgabewert

Gibt *T*.

## <a name="declval"></a> declval

```cpp
template <class T> add_rvalue_reference_t<T> declval() noexcept;  // as unevaluated operand
```

## <a name="exchange"></a> Exchange

**(C++14)** weist einem Objekt einen neuen Wert zu und gibt den alten Wert zurück.

```cpp
template <class T, class Other = T>
    T exchange(T& val, Other&& new_val)
```

### <a name="parameters"></a>Parameter

*val*\
Das Objekt, das den Wert von „new_val“ erhält.

*"new_val"* \
Das Objekt, dessen Wert nach „val“ kopiert oder verschoben wird.

### <a name="remarks"></a>Hinweise

Bei komplexen Typen vermeidet `exchange` das Kopieren des alten Werts, wenn ein Bewegungskonstruktor verfügbar ist, vermeidet das Kopieren des neuen Werts, wenn er ein temporäres Objekt ist oder verschoben wird, und nimmt alle Typen als neuen Wert an, wobei beliebige verfügbare konvertierende Zuweisungsoperatoren genutzt werden. Die Exchange-Funktion unterscheidet sich von [Std](../standard-library/algorithm-functions.md#swap) darin, dass das linke Argument nicht verschoben oder, des rechten Arguments kopiert.

### <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung von `exchange`. In der Praxis eignet sich `exchange` am besten für große Objekte, die aufwendig zu kopieren sind:

```cpp
#include <utility>
#include <iostream>

using namespace std;

struct C
{
   int i;
   //...
};

int main()
{
   // Use brace initialization
   C c1{ 1 };
   C c2{ 2 };
   C result = exchange(c1, c2);
   cout << "The old value of c1 is: " << result.i << endl;
   cout << "The new value of c1 after exchange is: " << c1.i << endl;

   return 0;
}
```

```Output
The old value of c1 is: 1
The new value of c1 after exchange is: 2
```

## <a name="forward"></a> Vorwärts

Wandelt bedingt sein Argument in einen rvalue-Verweis um, wenn das Argument ein rvalue-Wert oder ein rvalue-Verweis ist. Dadurch wird die rvalue-Funktion eines Arguments auf die Weiterleitungsfunktion zur Unterstützung einer perfekten Weiterleitung zurückgesetzt.

```cpp
template <class Type>    // accepts lvalues
    constexpr Type&& forward(typename remove_reference<Type>::type& Arg) noexcept

template <class Type>    // accepts everything else
    constexpr Type&& forward(typename remove_reference<Type>::type&& Arg) noexcept
```

### <a name="parameters"></a>Parameter

*Typ*\
Der Typ des übergebenen Werts *Arg*, die möglicherweise nicht den Typ des *Arg*. In der Regel bestimmt durch ein Vorlagenargument der Weiterleitungsfunktion.

*arg*\
Das umzuwandelnde Argument.

### <a name="return-value"></a>Rückgabewert

Gibt einen Rvalue-Verweis auf *Arg* der Wert im übergebenen *Arg* war ursprünglich ein Rvalue-Wert oder ein Verweis auf ein Rvalue-Wert zurückgegeben; andernfalls *Arg* ohne dessen Typ zu ändern.

### <a name="remarks"></a>Hinweise

Sie müssen ein explizites Vorlagenargument angeben, um `forward` aufzurufen.

`forward` Das Argument nicht weitergeleitet werden. Stattdessen ermöglicht `forward` dem Compiler durch bedingte Umwandlung des Arguments in einen rvalue-Verweis, wenn es ursprünglich ein rvalue-Wert oder ein rvalue-Verweis war, eine Überladungsauflösung mit Kenntnis des ursprünglichen Typs des weitergeleiteten Arguments auszuführen. Der sichtbare Typ eines Arguments einer Weiterleitungsfunktion kann seinen ursprünglichen Typ abweichen, z. B., wenn ein Rvalue-Wert wird als Argument an eine Funktion verwendet und an einen Parameternamen gebunden ist eine Namens wird er einen Lvalue ist, für einen beliebigen Wert tatsächlich als Rvalue-Wert vorhanden ist – `forward` wird die Rvalue-Funktion des Arguments wiederhergestellt.

Wiederherstellen der Rvalue-Funktion des ursprünglichen Werts eines Arguments, auf die überladungsauflösung, wird als bezeichnet *eine perfekte Weiterleitung*. Mit der perfekten Weiterleitung wird eine Vorlagenfunktion aktiviert, um ein Argument eines Referenztyps zu akzeptieren und die rvalue-Funktion wiederherzustellen, falls es für eine korrekte Überladungsauflösung erforderlich ist. Mithilfe der perfekten Weiterleitung können Sie die Verschiebesemantik für rvalues beibehalten und brauchen keine Überladungen für Funktionen bereitzustellen, die sich nur durch den Referenztyp ihrer Argumente unterscheiden.

## <a name="from_chars"></a> from_chars

```cpp
from_chars_result from_chars(const char* first, const char* last, see below& value, int base = 10);

from_chars_result from_chars(const char* first, const char* last, float& value, chars_format fmt = chars_format::general); 

from_chars_result from_chars(const char* first, const char* last, double& value, chars_format fmt = chars_format::general); 

from_chars_result from_chars(const char* first, const char* last, long double& value, chars_format fmt = chars_format::general);
```

## <a name="get"></a> Erhalten

Ruft ein Element aus einem `pair` -Objekt über den Index oder den Typ ab.

```cpp
// get reference to element at Index in pair Pr
template <size_t Index, class T1, class T2>
    constexpr tuple_element_t<Index, pair<T1, T2>>&
    get(pair<T1, T2>& Pr) noexcept;

// get reference to element T1 in pair Pr
template <class T1, class T2>
    constexpr T1& get(pair<T1, T2>& Pr) noexcept;

// get reference to element T2 in pair Pr
template <class T2, class T1>
    constexpr T2& get(pair<T1, T2>& Pr) noexcept;

// get const reference to element at Index in pair Pr
template <size_t Index, class T1, class T2>
    constexpr const tuple_element_t<Index, pair<T1, T2>>&
    get(const pair<T1, T2>& Pr) noexcept;

// get const reference to element T1 in pair Pr
template <class T1, class T2>
    constexpr const T1& get(const pair<T1, T2>& Pr) noexcept;

// get const reference to element T2 in pair Pr
template <class T2, class T1>
    constexpr const T2& get(const pair<T1, T2>& Pr) noexcept;

// get rvalue reference to element at Index in pair Pr
template <size_t Index, class T1, class T2>
    constexpr tuple_element_t<Index, pair<T1, T2>>&&
    get(pair<T1, T2>&& Pr) noexcept;

// get rvalue reference to element T1 in pair Pr
template <class T1, class T2>
    constexpr T1&& get(pair<T1, T2>&& Pr) noexcept;

// get rvalue reference to element T2 in pair Pr
template <class T2, class T1>
    constexpr T2&& get(pair<T1, T2>&& Pr) noexcept;
```

### <a name="parameters"></a>Parameter

*Index*\
Der 0-basierte Index des ausgewählten Elements.

*T1*\
Der Typ des ersten Paarelements.

*T2*\
Der Typ des zweiten Paarelements.

*Pull Request*\
Das Paar, für das die Auswahl durchgeführt werden soll.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktionen geben jeweils einen Verweis auf ein Element des `pair` -Arguments zurück.

Für die indizierten Überladungen Wenn der Wert des *Index* ist 0, die die Funktionen geben `pr.first` und, wenn der Wert des *Index* ist 1, die die Funktionen geben `pr.second`. Der Typ `RI` ist der Typ des zurückgegebenen Elements.

Für die Überladungen, die keine Indexparameter haben, wird das zurückzugebende Element durch das Typargument abgeleitet. Aufrufen von `get<T>(Tuple)` erzeugt einen Compilerfehler aus, wenn *Pr* enthält mehr oder weniger als ein Element vom Typ "t".

### <a name="example"></a>Beispiel

```cpp
#include <utility>
#include <iostream>
using namespace std;
int main()
{

    typedef pair<int, double> MyPair;

    MyPair c0(9, 3.14);

    // get elements by index
    cout << " " << get<0>(c0);
    cout << " " << get<1>(c0) << endl;

    // get elements by type (C++14)
    MyPair c1(1, 0.27);
    cout << " " << get<int>(c1);
    cout << " " << get<double>(c1) << endl;
}
```

```Output
9 3.14
1 0.27
```

## <a name="index_sequence"></a> index_sequence

```cpp
template<size_t... I>
    using index_sequence = integer_sequence<size_t, I...>;
```

## <a name="index_sequence_for"></a> index_sequence_for

```cpp
template<class... T>
    using index_sequence_for = make_index_sequence<sizeof...(T)>;
```

## <a name="make_index_sequence"></a> make_index_sequence

```cpp
template<size_t N>
    using make_index_sequence = make_integer_sequence<size_t, N>;
```

## <a name="make_integer_sequence"></a> make_integer_sequence

```cpp
template<class T, T N>
    using make_integer_sequence = integer_sequence<T, see below >;
```

## <a name="make_pair"></a> make_pair

Eine Vorlagenfunktion, die Sie verwenden können, um Objekte vom Typ `pair` zu erstellen, wobei die Komponententypen automatisch auf Grundlage der Datentypen ausgewählt werden, die als Parameter übergeben werden.

```cpp
template <class T, class U>
    pair<T, U> make_pair(T& Val1, U& Val2);

template <class T, class U>
    pair<T, U> make_pair(T& Val1, U&& Val2);

template <class T, class U>
    pair<T, U> make_pair(T&& Val1, U& Val2);

template <class T, class U>
    pair<T, U> make_pair(T&& Val1, U&& Val2);
```

### <a name="parameters"></a>Parameter

*Wert1*\
Ein Wert, der das erste Element aus `pair` initialisiert.

*Wert2*\
Ein Wert, der das zweite Element aus `pair` initialisiert.

### <a name="return-value"></a>Rückgabewert

Das Pair-Objekt, das erstellt wird: `pair` < `T`,`U`> (`Val1`, `Val2`).

### <a name="remarks"></a>Hinweise

`make_pair` konvertiert ein Objekt vom Typ [reference_wrapper-Klasse](../standard-library/reference-wrapper-class.md) in Verweistypen und verfallende Arrays und Funktionen in Zeiger.

im zurückgegebenen `pair`-Objekt wird `T` wie folgt bestimmt:

- Wenn der Eingabetyp `T` `reference_wrapper<X>` ist, lautet der zurückgegebene Typ `T` `X&`.

- Andernfalls ist der zurückgegebene Typ `T` `decay<T>::type`. Wenn [decay-Klasse](../standard-library/decay-class.md) wird nicht unterstützt, der zurückgegebene Typ `T` ist identisch mit dem Eingabetyp `T`.

Der zurückgegebene Typ `U` wird auf ähnliche Weise anhand des Eingabetyps `U` bestimmt.

Ein Vorteil von `make_pair` besteht darin, dass die Typen von Objekten, die gespeichert werden, werden automatisch vom Compiler bestimmt, und müssen nicht explizit angegeben werden. Verwenden Sie explizite Vorlagenargumente wie z. B. keine `make_pair<int, int>(1, 2)` bei Verwendung von `make_pair` da sie ausführliche und fügt der komplexen Rvalue-Verweis-Probleme, die möglicherweise Kompilierungsfehler verursachen. Die korrekte Syntax für dieses Beispiel wäre `make_pair(1, 2)`.

Die `make_pair`-Hilfsfunktion ermöglicht außerdem, zwei Werte an eine Funktion zu übergeben, die ein Paar als Eingabeparameter erfordert.

### <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung der Hilfsfunktion `make_pair` beim Deklarieren und Initialisieren eines Paares finden Sie unter [pair Structure (pair-Struktur)](../standard-library/pair-structure.md).

## <a name="move"></a> Verschieben

Wandelt unbedingt das Argument in einen rvalue-Verweis um und signalisiert dadurch, dass es verschoben werden kann, wenn das Verschieben für den zugehörigen Typ aktiviert ist.

```cpp
template <class Type>
    constexpr typename remove_reference<Type>::type&& move(Type&& Arg) noexcept;
```

### <a name="parameters"></a>Parameter

*Typ*\
Ein Typ, abgeleitet aus dem Typ des Arguments übergeben *Arg*zusammen mit den verweisreduzierungsregeln.

*arg*\
Das umzuwandelnde Argument. Auch wenn der Typ des *Arg* scheinbar als Rvalue-Verweis, angegeben werden `move` auch Lvalue-Argumente akzeptiert, da Lvalue-Verweise an Rvalue-Verweise gebunden werden können.

### <a name="return-value"></a>Rückgabewert

`Arg` als rvalue-Verweis, unabhängig davon, ob sein Typ ein Verweistyp ist.

### <a name="remarks"></a>Hinweise

Das Vorlagenargument *Typ* ist nicht vorgesehen, explizit angegeben werden, sondern vom Typ des der übergebene Wert abgeleitet werden *Arg*. Der Typ des *Typ* entsprechend den verweisreduzierungsregeln angepasst wird.

`move` Das Argument nicht verschoben werden. Durch unbedingtes Umwandeln des zugehörigen Arguments, einen l-Wert sein kann – einen Rvalue-Verweis ermöglicht es den Compiler zu verschieben, anstatt Sie zu kopieren, der Wert übergeben *Arg* Wenn der Typ der verschieben aktiviert ist. Wenn der Typ Move-fähigen nicht ist, wird er stattdessen kopiert.

Wenn der Wert übergeben *Arg* ein Lvalue ist – d. h. er besitzt einen Namen oder die Adresse kann akzeptiert werden – er ungültig, wenn die Verschiebung erfolgt. Finden Sie mit der nicht in der übergebene Wert *Arg* mit seinem Namen oder die Adresse, nachdem er verschoben wurde.

## <a name="moveif"></a> move_if_noexcept

```cpp
template <class T> constexpr conditional_t< !is_nothrow_move_constructible_v<T> && is_copy_constructible_v<T>, const T&, T&&> move_if_noexcept(T& x) noexcept;
```

## <a name="swap"></a> Swap

Tauscht die Elemente von zwei Arten oder [pair-Struktur](../standard-library/pair-structure.md) Objekte.

```cpp
template <class T>
    void swap(T& left, T& right) noexcept(see below );
template <class T, size_t N>
    void swap(T (&left)[N], T (&right)[N]) noexcept(is_nothrow_swappable_v<T>);
template <class T, class U>
    void swap(pair<T, U>& left, pair<T, U>& right);
```

### <a name="parameters"></a>Parameter

*Links*\
Ein Objekt vom Typ oder Typ `pair`.

*Richting*\
Ein Objekt vom Typ oder Typ `pair`.

### <a name="remarks"></a>Hinweise

Ein Vorteil von `swap` besteht darin, dass die Typen von Objekten, die gespeichert werden, werden automatisch vom Compiler bestimmt, und müssen nicht explizit angegeben werden. Verwenden Sie explizite Vorlagenargumente wie z. B. keine `swap<int, int>(1, 2)` bei Verwendung von `swap` da sie ausführliche und fügt der komplexen Rvalue-Verweis-Probleme, die möglicherweise Kompilierungsfehler verursachen.

## <a name="to_chars"></a> to_chars

```cpp
to_chars_result to_chars(char* first, char* last, see below value, int base = 10);
to_chars_result to_chars(char* first, char* last, float value); 
to_chars_result to_chars(char* first, char* last, double value); 
to_chars_result to_chars(char* first, char* last, long double value);
to_chars_result to_chars(char* first, char* last, float value, chars_format fmt); 
to_chars_result to_chars(char* first, char* last, double value, chars_format fmt); 
to_chars_result to_chars(char* first, char* last, long double value, chars_format fmt);
to_chars_result to_chars(char* first, char* last, float value, chars_format fmt, int precision); 
to_chars_result to_chars(char* first, char* last, double value, chars_format fmt, int precision); 
to_chars_result to_chars(char* first, char* last, long double value, chars_format fmt, int precision);
```

### <a name="remarks"></a>Hinweise

Wert in eine Zeichenfolge konvertiert, indem Sie den Bereich ausfüllen `[first, last)`, wobei `[first, last)` ist erforderlich, um ein gültiger Bereich sein.
