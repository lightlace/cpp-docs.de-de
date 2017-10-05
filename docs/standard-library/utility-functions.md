---
title: '&lt;utility&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- utility/std::exchange
- utility/std::forward
- utility/std::make_pair
- utility/std::move
- utility/std::swap
ms.assetid: b1df38cd-3a59-4098-9c81-83342eb719a4
caps.latest.revision: 7
manager: ghogen
helpviewer_keywords:
- std::exchange [C++]
- std::forward [C++]
- std::make_pair [C++]
- std::move [C++]
- std::swap [C++]
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: d2b444c2de41651ac74047717ed54a7059866f86
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="ltutilitygt-functions"></a>&lt;utility&gt;-Funktionen
||||  
|-|-|-|  
|[exchange](#exchange)|[forward](#forward)|[get-Funktion &lt;utility&gt;](#get)|  
|[make_pair](#make_pair)|[move](#move)|[swap](#swap)|  
  
##  <a name="exchange"></a> exchange  
 **(C++14)** weist einem Objekt einen neuen Wert zu und gibt den alten Wert zurück.  
  
```cpp  
template <class T, class Other = T>
T exchange(T& val, Other&& new_val)
```  
  
### <a name="parameters"></a>Parameter  
 `val`  
 Das Objekt, das den Wert von „new_val“ erhält.  
  
 `new_val`  
 Das Objekt, dessen Wert nach „val“ kopiert oder verschoben wird.  
  
### <a name="remarks"></a>Hinweise  
 Bei komplexen Typen vermeidet `exchange` das Kopieren des alten Werts, wenn ein Bewegungskonstruktor verfügbar ist, vermeidet das Kopieren des neuen Werts, wenn er ein temporäres Objekt ist oder verschoben wird, und nimmt alle Typen als neuen Wert an, wobei beliebige verfügbare konvertierende Zuweisungsoperatoren genutzt werden. Die exchange-Funktion unterscheidet sich von [std::swap](../standard-library/algorithm-functions.md#swap) insofern, als das linke Argument nicht zum rechten Argument verschoben oder kopiert wird.  
  
### <a name="example"></a>Beispiel  
  Das folgende Beispiel veranschaulicht die Verwendung von `exchange`. In der Praxis eignet sich `exchange` am besten für große Objekte, die aufwendig zu kopieren sind:  
  
```  
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
/* Output:  
The old value of c1 is: 1  
The new value of c1 after exchange is: 2  
*/  
```  
  
##  <a name="forward"></a> forward  
 Wandelt bedingt sein Argument in einen rvalue-Verweis um, wenn das Argument ein rvalue-Wert oder ein rvalue-Verweis ist. Dadurch wird die rvalue-Funktion eines Arguments auf die Weiterleitungsfunktion zur Unterstützung einer perfekten Weiterleitung zurückgesetzt.  
  
```
template <class Type>    // accepts lvalues
constexpr Type&& forward(typename remove_reference<Type>::type& Arg) noexcept

template <class Type>    // accepts everything else
constexpr Type&& forward(typename remove_reference<Type>::type&& Arg) noexcept
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`Type`|Der Typ des Werts, der an `Arg` übergeben wurde. Dieser kann sich vom Typ `Arg` unterscheiden. In der Regel bestimmt durch ein Vorlagenargument der Weiterleitungsfunktion.|  
|`Arg`|Das umzuwandelnde Argument.|  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen rvalue-Verweis auf `Arg` zurück, wenn der Wert, der an `Arg` übergeben wurde, ursprünglich ein rvalue-Wert oder ein Verweis auf einen rvalue-Wert war; gibt andernfalls `Arg` zurück, ohne den Typ zu ändern.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen ein explizites Vorlagenargument angeben, um `forward` aufzurufen.  
  
 `forward` leitet das Argument nicht weiter. Stattdessen ermöglicht `forward` dem Compiler durch bedingte Umwandlung des Arguments in einen rvalue-Verweis, wenn es ursprünglich ein rvalue-Wert oder ein rvalue-Verweis war, eine Überladungsauflösung mit Kenntnis des ursprünglichen Typs des weitergeleiteten Arguments auszuführen. Der sichtbare Typ eines Arguments einer Weiterleitungsfunktion kann vom ursprünglichen Typ abweichen, z.B. wenn ein rvalue-Wert als Argument einer Funktion verwendet wird und an einen Parameternamen gebunden ist. Mithilfe eines Namens wird er in einen lvalue-Wert umgewandelt, unabhängig davon, ob der Wert tatsächlich als rvalue-Wert vorhanden ist. Mit `forward` wird die rvalue-Funktion des Arguments wiederhergestellt.  
  
 Das Wiederherstellen der rvalue-Funktion des ursprünglichen Werts eines Arguments zum Ausführen einer Überladungsauflösung wird als *perfekte Weiterleitung* bezeichnet. Mit der perfekten Weiterleitung wird eine Vorlagenfunktion aktiviert, um ein Argument eines Referenztyps zu akzeptieren und die rvalue-Funktion wiederherzustellen, falls es für eine korrekte Überladungsauflösung erforderlich ist. Mithilfe der perfekten Weiterleitung können Sie die Verschiebesemantik für rvalues beibehalten und brauchen keine Überladungen für Funktionen bereitzustellen, die sich nur durch den Referenztyp ihrer Argumente unterscheiden.  
  
##  <a name="get"></a> get  
 Ruft ein Element aus einem `pair` -Objekt über den Index oder den Typ ab.  
  
```
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
 `Index`  
 Der 0-basierte Index des angegebenen Elements.  
  
 `T1`  
 Der Typ des ersten Paarelements.  
  
 `T2`  
 Der Typ des zweiten Paarelements.  
  
 `pr`  
 Das Paar, für das die Auswahl durchgeführt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die Vorlagenfunktionen geben jeweils einen Verweis auf ein Element des `pair` -Arguments zurück.  
  
 Wenn für die indizierten Überladungen der Wert von `Index` „0“ lautet, geben die Funktionen `pr.first` zurück, und wenn der Wert von `Index` „1“ lautet, geben die Funktionen `pr.second`zurück. Der Typ `RI` ist der Typ des zurückgegebenen Elements.  
  
 Für die Überladung, die keine Indexparameter aufweisen, wird das zurückzugebende Element durch das Typargument abgeleitet. Das Aufrufen von `get<T>(Tuple)` führt zu einem Compilerfehler, wenn `pr` mehr oder weniger als ein Element vom Typ „T“ enthält.  
  
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
  
##  <a name="make_pair"></a> make_pair  
 Eine Vorlagenfunktion, die Sie verwenden können, um Objekte vom Typ `pair` zu erstellen, wobei die Komponententypen automatisch auf Grundlage der Datentypen ausgewählt werden, die als Parameter übergeben werden.  
  
```
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
 `Val1`  
 Ein Wert, der das erste Element aus `pair` initialisiert.  
  
 `Val2`  
 Ein Wert, der das zweite Element aus `pair` initialisiert.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Objektpaar, das erstellt wird: `pair`< `T`, `U`>( `Val1`, `Val2`).  
  
### <a name="remarks"></a>Hinweise  
 `make_pair` konvertiert ein Objekt vom Typ [reference_wrapper-Klasse](../standard-library/reference-wrapper-class.md) in Verweistypen und verfallende Arrays und Funktionen in Zeiger.  
  
 im zurückgegebenen `pair`-Objekt wird `T` wie folgt bestimmt:  
  
-   Wenn der Eingabetyp `T` `reference_wrapper<X>` ist, lautet der zurückgegebene Typ `T` `X&`.  
  
-   Andernfalls ist der zurückgegebene Typ `T` `decay<T>::type`. Wenn die [decay-Klasse](../standard-library/decay-class.md) nicht unterstützt wird, ist der zurückgegebene Typ `T` mit dem Eingabetyp `T` identisch.  
  
 Der zurückgegebene Typ `U` wird auf ähnliche Weise anhand des Eingabetyps `U` bestimmt.  
  
 Ein Vorteil von `make_pair` ist, dass die Typen von Objekten, die gespeichert werden, automatisch vom Compiler bestimmt werden und nicht explizit angegeben werden müssen. Verwenden Sie keine expliziten Vorlagenargumente wie `make_pair<int, int>(1, 2)`, wenn Sie `make_pair` verwenden, da dies unnötig detailliert ist und zu komplexen rvalue-Verweisproblemen führt, die möglicherweise Kompilierungsfehler verursachen. Die korrekte Syntax für dieses Beispiel wäre `make_pair(1, 2)`.  
  
 Die `make_pair`-Hilfsfunktion ermöglicht außerdem, zwei Werte an eine Funktion zu übergeben, die ein Paar als Eingabeparameter erfordert.  
  
### <a name="example"></a>Beispiel  
  Ein Beispiel für die Verwendung der Hilfsfunktion `make_pair` beim Deklarieren und Initialisieren eines Paares finden Sie unter [pair Structure (pair-Struktur)](../standard-library/pair-structure.md).  
  
##  <a name="move"></a> move  
 Wandelt unbedingt das Argument in einen rvalue-Verweis um und signalisiert dadurch, dass es verschoben werden kann, wenn das Verschieben für den zugehörigen Typ aktiviert ist.  
  
```
template <class Type>
constexpr typename remove_reference<Type>::type&& move(Type&& Arg) noexcept;
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`Type`|Ein Typ, der von dem Typ des Arguments abgeleitet wurde, das in `Arg` zusammen mit den Verweisreduzierungsregeln übergeben wurde.|  
|`Arg`|Das umzuwandelnde Argument. Obwohl der Typ `Arg` scheinbar als rvalue-Verweis angegeben ist, akzeptiert `move` auch lvalue-Argumente, da lavalue-Verweise an rvalue-Verweise gebunden werden können.|  
  
### <a name="return-value"></a>Rückgabewert  
 `Arg` als rvalue-Verweis, unabhängig davon, ob sein Typ ein Verweistyp ist.  
  
### <a name="remarks"></a>Hinweise  
 Das Vorlagenargument `Type` soll nicht explizit angegeben, sondern anhand des Werts abgeleitet werden, der an `Arg` übergeben wird. Der Typ von `Type` wird den Verweisreduzierungsregeln entsprechend angepasst.  
  
 Mit `move` wird das zugehörige Argument nicht verschoben. Durch unbedingtes Umwandeln des zugehörigen Arguments, bei dem es sich um ein lvalue-Objekt handeln kann, in einen rvalue-Verweis wird der Compiler stattdessen in die Lage versetzt, den in `Arg` übergebenen Wert zu verschieben, statt zu kopieren, wenn das Verschieben für den entsprechende Typ aktiviert ist. Wenn das Verschieben für den Typ nicht aktiviert ist, wird er stattdessen kopiert.  
  
 Wenn der in `Arg` übergebene Wert ein lvalue ist – d. h., er besitzt einen Namen oder seine Adresse kann akzeptiert werden – wird er ungültig, wenn die Verschiebung erfolgt. Verweisen Sie nicht auf den in `Arg` übergebenen Wert mit seinem Namen oder seiner Adresse, nachdem er verschoben wurde.  
  
##  <a name="swap"></a> swap  
 Tauscht die Elemente zweier Objekte einer [pair-Struktur](../standard-library/pair-structure.md).  
  
```
template <class T, class U>  
void swap(pair<T, U>& left, pair<T, U>& right);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`left`|Ein Objekt vom Typ `pair`.|  
|`right`|Ein Objekt vom Typ `pair`.|  
  
### <a name="remarks"></a>Hinweise  
 Ein Vorteil von `swap` ist, dass die Typen von Objekten, die gespeichert werden, automatisch vom Compiler bestimmt werden und nicht explizit angegeben werden müssen. Verwenden Sie keine expliziten Vorlagenargumente wie `swap<int, int>(1, 2)`, wenn Sie `swap` verwenden, da dies unnötig detailliert ist und zu komplexen rvalue-Verweisproblemen führt, die möglicherweise Kompilierungsfehler verursachen.  
  
## <a name="see-also"></a>Siehe auch  
 [\<utility>](../standard-library/utility.md)




