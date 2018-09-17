---
title: '&lt;utility&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
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
ms.openlocfilehash: 12e8b2c4dfb0d7d36974fb2e5979d82b69c89316
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718322"
---
# <a name="ltutilitygt-functions"></a>&lt;utility&gt;-Funktionen

||||
|-|-|-|
|[exchange](#exchange)|[forward](#forward)|[get-Funktion &lt;utility&gt;](#get)|
|[make_pair](#make_pair)|[move](#move)|[swap](#swap)|

## <a name="exchange"></a> exchange

**(C++14)** weist einem Objekt einen neuen Wert zu und gibt den alten Wert zurück.

```cpp
template <class T, class Other = T>
T exchange(T& val, Other&& new_val)
```

### <a name="parameters"></a>Parameter

*val*<br/>
Das Objekt, das den Wert von „new_val“ erhält.

*"new_val"*<br/>
Das Objekt, dessen Wert nach „val“ kopiert oder verschoben wird.

### <a name="remarks"></a>Hinweise

Bei komplexen Typen vermeidet `exchange` das Kopieren des alten Werts, wenn ein Bewegungskonstruktor verfügbar ist, vermeidet das Kopieren des neuen Werts, wenn er ein temporäres Objekt ist oder verschoben wird, und nimmt alle Typen als neuen Wert an, wobei beliebige verfügbare konvertierende Zuweisungsoperatoren genutzt werden. Die exchange-Funktion unterscheidet sich von [std::swap](../standard-library/algorithm-functions.md#swap) insofern, als das linke Argument nicht zum rechten Argument verschoben oder kopiert wird.

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

## <a name="forward"></a> forward

Wandelt bedingt sein Argument in einen rvalue-Verweis um, wenn das Argument ein rvalue-Wert oder ein rvalue-Verweis ist. Dadurch wird die rvalue-Funktion eines Arguments auf die Weiterleitungsfunktion zur Unterstützung einer perfekten Weiterleitung zurückgesetzt.

```cpp
template <class Type>    // accepts lvalues
constexpr Type&& forward(typename remove_reference<Type>::type& Arg) noexcept

template <class Type>    // accepts everything else
constexpr Type&& forward(typename remove_reference<Type>::type&& Arg) noexcept
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*Type*|Der Typ des übergebenen Werts *Arg*, die möglicherweise nicht den Typ des *Arg*. In der Regel bestimmt durch ein Vorlagenargument der Weiterleitungsfunktion.|
|*arg*|Das umzuwandelnde Argument.|

### <a name="return-value"></a>Rückgabewert

Gibt einen Rvalue-Verweis auf *Arg* der Wert im übergebenen *Arg* war ursprünglich ein Rvalue-Wert oder ein Verweis auf ein Rvalue-Wert zurückgegeben; andernfalls *Arg* ohne dessen Typ zu ändern.

### <a name="remarks"></a>Hinweise

Sie müssen ein explizites Vorlagenargument angeben, um `forward` aufzurufen.

`forward` leitet das Argument nicht weiter. Stattdessen ermöglicht `forward` dem Compiler durch bedingte Umwandlung des Arguments in einen rvalue-Verweis, wenn es ursprünglich ein rvalue-Wert oder ein rvalue-Verweis war, eine Überladungsauflösung mit Kenntnis des ursprünglichen Typs des weitergeleiteten Arguments auszuführen. Der sichtbare Typ eines Arguments einer Weiterleitungsfunktion kann vom ursprünglichen Typ abweichen, z.B. wenn ein rvalue-Wert als Argument einer Funktion verwendet wird und an einen Parameternamen gebunden ist. Mithilfe eines Namens wird er in einen lvalue-Wert umgewandelt, unabhängig davon, ob der Wert tatsächlich als rvalue-Wert vorhanden ist. Mit `forward` wird die rvalue-Funktion des Arguments wiederhergestellt.

Das Wiederherstellen der rvalue-Funktion des ursprünglichen Werts eines Arguments zum Ausführen einer Überladungsauflösung wird als *perfekte Weiterleitung* bezeichnet. Mit der perfekten Weiterleitung wird eine Vorlagenfunktion aktiviert, um ein Argument eines Referenztyps zu akzeptieren und die rvalue-Funktion wiederherzustellen, falls es für eine korrekte Überladungsauflösung erforderlich ist. Mithilfe der perfekten Weiterleitung können Sie die Verschiebesemantik für rvalues beibehalten und brauchen keine Überladungen für Funktionen bereitzustellen, die sich nur durch den Referenztyp ihrer Argumente unterscheiden.

## <a name="get"></a> get

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

*Index*<br/>
Der 0-basierte Index des angegebenen Elements.

*T1*<br/>
Der Typ des ersten Paarelements.

*T2*<br/>
Der Typ des zweiten Paarelements.

*Pull Request*<br/>
Das Paar, für das die Auswahl durchgeführt werden soll.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktionen geben jeweils einen Verweis auf ein Element des `pair` -Arguments zurück.

Für die indizierten Überladungen Wenn der Wert des *Index* ist 0, die die Funktionen geben `pr.first` und, wenn der Wert des *Index* ist 1, die die Funktionen geben `pr.second`. Der Typ `RI` ist der Typ des zurückgegebenen Elements.

Für die Überladung, die keine Indexparameter aufweisen, wird das zurückzugebende Element durch das Typargument abgeleitet. Aufrufen von `get<T>(Tuple)` erzeugt einen Compilerfehler aus, wenn *Pr* enthält mehr oder weniger als ein Element vom Typ "t".

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

    /*
    Output:
    9 3.14
    1 0.27
    */

}
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

*Wert1*<br/>
Ein Wert, der das erste Element aus `pair` initialisiert.

*Wert2*<br/>
Ein Wert, der das zweite Element aus `pair` initialisiert.

### <a name="return-value"></a>Rückgabewert

Das Objektpaar, das erstellt wird: `pair`< `T`, `U`>( `Val1`, `Val2`).

### <a name="remarks"></a>Hinweise

`make_pair` konvertiert ein Objekt vom Typ [reference_wrapper-Klasse](../standard-library/reference-wrapper-class.md) in Verweistypen und verfallende Arrays und Funktionen in Zeiger.

im zurückgegebenen `pair`-Objekt wird `T` wie folgt bestimmt:

- Wenn der Eingabetyp `T` `reference_wrapper<X>` ist, lautet der zurückgegebene Typ `T` `X&`.

- Andernfalls ist der zurückgegebene Typ `T` `decay<T>::type`. Wenn die [decay-Klasse](../standard-library/decay-class.md) nicht unterstützt wird, ist der zurückgegebene Typ `T` mit dem Eingabetyp `T` identisch.

Der zurückgegebene Typ `U` wird auf ähnliche Weise anhand des Eingabetyps `U` bestimmt.

Ein Vorteil von `make_pair` ist, dass die Typen von Objekten, die gespeichert werden, automatisch vom Compiler bestimmt werden und nicht explizit angegeben werden müssen. Verwenden Sie keine expliziten Vorlagenargumente wie `make_pair<int, int>(1, 2)`, wenn Sie `make_pair` verwenden, da dies unnötig detailliert ist und zu komplexen rvalue-Verweisproblemen führt, die möglicherweise Kompilierungsfehler verursachen. Die korrekte Syntax für dieses Beispiel wäre `make_pair(1, 2)`.

Die `make_pair`-Hilfsfunktion ermöglicht außerdem, zwei Werte an eine Funktion zu übergeben, die ein Paar als Eingabeparameter erfordert.

### <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung der Hilfsfunktion `make_pair` beim Deklarieren und Initialisieren eines Paares finden Sie unter [pair Structure (pair-Struktur)](../standard-library/pair-structure.md).

## <a name="move"></a> move

Wandelt unbedingt das Argument in einen rvalue-Verweis um und signalisiert dadurch, dass es verschoben werden kann, wenn das Verschieben für den zugehörigen Typ aktiviert ist.

```cpp
template <class Type>
constexpr typename remove_reference<Type>::type&& move(Type&& Arg) noexcept;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*Type*|Ein Typ, abgeleitet aus dem Typ des Arguments übergeben *Arg*zusammen mit den verweisreduzierungsregeln.|
|*arg*|Das umzuwandelnde Argument. Auch wenn der Typ des *Arg* scheinbar als Rvalue-Verweis, angegeben werden `move` auch Lvalue-Argumente akzeptiert, da Lvalue-Verweise an Rvalue-Verweise gebunden werden können.|

### <a name="return-value"></a>Rückgabewert

`Arg` als rvalue-Verweis, unabhängig davon, ob sein Typ ein Verweistyp ist.

### <a name="remarks"></a>Hinweise

Das Vorlagenargument *Typ* dient nicht explizit angegeben werden, sondern vom Typ des der übergebene Wert abgeleitet werden *Arg*. Der Typ des *Typ* entsprechend den verweisreduzierungsregeln angepasst wird.

Mit `move` wird das zugehörige Argument nicht verschoben. Durch unbedingtes Umwandeln des zugehörigen Arguments, einen l-Wert sein kann – einen Rvalue-Verweis ermöglicht es den Compiler zu verschieben, anstatt Sie zu kopieren, der Wert übergeben *Arg* Wenn der Typ der verschieben aktiviert ist. Wenn das Verschieben für den Typ nicht aktiviert ist, wird er stattdessen kopiert.

Wenn der Wert übergeben *Arg* ein Lvalue ist – d. h. er besitzt einen Namen oder die Adresse kann akzeptiert werden – er ungültig, wenn die Verschiebung erfolgt. Verweisen Sie nicht auf den übergebenen Wert *Arg* mit seinem Namen oder die Adresse, nachdem er verschoben wurde.

## <a name="swap"></a>  swap

Tauscht die Elemente zweier Objekte einer [pair-Struktur](../standard-library/pair-structure.md).

```cpp
template <class T, class U>
void swap(pair<T, U>& left, pair<T, U>& right);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*left*|Ein Objekt vom Typ `pair`.|
|*right*|Ein Objekt vom Typ `pair`.|

### <a name="remarks"></a>Hinweise

Ein Vorteil von `swap` ist, dass die Typen von Objekten, die gespeichert werden, automatisch vom Compiler bestimmt werden und nicht explizit angegeben werden müssen. Verwenden Sie keine expliziten Vorlagenargumente wie `swap<int, int>(1, 2)`, wenn Sie `swap` verwenden, da dies unnötig detailliert ist und zu komplexen rvalue-Verweisproblemen führt, die möglicherweise Kompilierungsfehler verursachen.

## <a name="see-also"></a>Siehe auch

[\<utility>](../standard-library/utility.md)<br/>
