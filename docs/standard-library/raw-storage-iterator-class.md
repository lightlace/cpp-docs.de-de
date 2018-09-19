---
title: raw_storage_iterator-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- memory/std::raw_storage_iterator
- memory/std::raw_storage_iterator::element_type
- memory/std::raw_storage_iterator::iter_type
dev_langs:
- C++
helpviewer_keywords:
- std::raw_storage_iterator [C++]
- std::raw_storage_iterator [C++], element_type
- std::raw_storage_iterator [C++], iter_type
ms.assetid: 6f033f15-f48e-452a-a326-647ea2cf346f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 848612f59c2d5cc24289b6d8c56b0c9eeaebc961
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712789"
---
# <a name="rawstorageiterator-class"></a>raw_storage_iterator-Klasse

Eine Adapterklasse, die bereitgestellt wird, um Algorithmen das Speichern ihrer Ergebnisse in nicht initialisiertem Speicher zu ermöglichen.

## <a name="syntax"></a>Syntax

```cpp
template <class OutputIterator, class Type>
class raw_storage_iterator
```

### <a name="parameters"></a>Parameter

*OutputIterator*<br/>
Gibt den Ausgabeiterator für das Objekt an, das gespeichert wird.

*Type*<br/>
Der Typ des Objekts, dem Speicher zugeordnet wird.

## <a name="remarks"></a>Hinweise

Die Klasse beschreibt einen Ausgabeiterator, die Objekte des Typs erstellt `Type` in der Sequenz generiert. Ein Objekt der Klasse `raw_storage_iterator` \< **ForwardIterator**, **Typ**> auf Speicher zugreift, über ein forward-Iterator-Objekt der Klasse `ForwardIterator`, dass Sie, wenn angeben Sie Erstellen Sie das Objekt. Für ein Objekt der Klasse `ForwardIterator`, den Ausdruck  **& \*erste** müssen festlegen, nicht erstellten Speicher für das nächste Objekt (des Typs `Type`) in der generierten Sequenz.

Diese Adapterklasse wird verwendet, wenn es erforderlich ist, Speicherbelegung und Objekterstellung zu trennen. `raw_storage_iterator` kann verwendet werden, um Objekte in nicht initialisierten Speicher zu kopieren, beispielsweise Arbeitsspeicher, der über die `malloc`-Funktion zugeordnet wurde.

## <a name="members"></a>Member

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[raw_storage_iterator](#raw_storage_iterator)|Erstellt einen unformatierten Speicheriterator mit einem angegebenen zugrunde liegenden Ausgabeiterator.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[element_type](#element_type)|Stellt einen Typ bereit, der ein Element beschreibt, das in einem unformatierten Speicheriterator gespeichert werden soll.|
|[iter_type](#iter_type)|Stellt einen Typ bereit, der einen Iterator beschreibt, der einem unformatierten Speicheriterator zugrunde liegt.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator*](#op_star)|Ein Dereferenzierungsoperator, der zum Implementieren des ausgabeiteratorausdrucks \* `ii`  =  `x`.|
|[operator=](#op_eq)|Ein Zuweisungsoperator, der zum Implementieren der unformatierten speicheriteratorausdrucks \* `i`  =  `x` für das im Speicher gespeichert.|
|[operator++](#op_add_add)|Inkrementoperatoren in Präfix- und Postfix-Notation für unformatierte Speicheriteratoren.|

## <a name="requirements"></a>Anforderungen

**Header:** \<memory>

**Namespace:** std

## <a name="element_type"></a> raw_storage_iterator::element_type

Stellt einen Typ bereit, der ein Element beschreibt, das in einem unformatierten Speicheriterator gespeichert werden soll.

```cpp
typedef Type element_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für den Raw_storage_iterator-Klassenvorlagenparameter `Type`.

## <a name="iter_type"></a> raw_storage_iterator::iter_type

Stellt einen Typ bereit, der einen Iterator beschreibt, der einem unformatierten Speicheriterator zugrunde liegt.

```cpp
typedef ForwardIterator iter_type;
```

### <a name="remarks"></a>Hinweise

Der Type stellt ein Synonym für den Vorlagenparameter `ForwardIterator` dar.

## <a name="op_star"></a>  raw_storage_iterator:: Operator\*

Der Dereferenzierungsoperator, der zum Implementieren des unformatierten Speicheriteratorausdrucks \* *ii* = *x* verwendet wird.

```cpp
raw_storage_iterator<ForwardIterator, Type>& operator*();
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf den unformatierten Speicheriterator.

### <a name="remarks"></a>Hinweise

Die Anforderungen für eine `ForwardIterator` der unformatierte speicheriterator nur den Ausdruck erfordern \* *Ii* = *t* gültig sein und, die er sagt nichts über die **Operator** oder `operator=` selbst. Die memberoperatoren in dieser Implementierung gibt  **\*dies**, sodass [Operator =](#op_eq)(**ConstType**&) können den tatsächlichen Speicher in einem Ausdruck ausführen wie z. B. \* *Ptr* = `val`.

### <a name="example"></a>Beispiel

```cpp
// raw_storage_iterator_op_deref.cpp
// compile with: /EHsc
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

class Int
{
public:
   Int(int i)
   {
      cout << "Constructing " << i << endl;
      x = i;
      bIsConstructed = true;
   };

   Int &operator=(int i)
   {
      if (!bIsConstructed)
         cout << "Not constructed.\n";
      cout << "Copying " << i << endl;
      x = i;
      return *this;
   };

   int x;

private:
   bool bIsConstructed;
};

int main( void)
{
   Int *pInt = ( Int* ) malloc( sizeof( Int ) );
   memset( pInt, 0, sizeof( Int ) ); // Set bIsConstructed to false;
*pInt = 5;
   raw_storage_iterator< Int*, Int > it( pInt );
*it = 5;
}
/* Output:
Not constructed.
Copying 5
Constructing 5
*/
```

## <a name="op_eq"></a> raw_storage_iterator::operator=

Ein Zuweisungsoperator, der dazu verwendet wird, den für einen unformatierten Speicheriterator verwendeten Ausdruck \* *i* = *x* zu implementieren, damit er im Arbeitsspeicher gespeichert werden kann.

```cpp
raw_storage_iterator<ForwardIterator, Type>& operator=(
    const Type& val);
```

### <a name="parameters"></a>Parameter

*val*<br/>
Der Wert des Objekts vom Typ `Type` in den Speicher eingefügt werden soll.

### <a name="return-value"></a>Rückgabewert

Der Operator fügt `val` in den Speicher ein, und gibt dann einen Verweis auf den unformatierten Speicheriterator zurück.

### <a name="remarks"></a>Hinweise

Die Anforderungen für eine `ForwardIterator` Zustand, der der unformatierten speicheriterator erfüllt werden muss, benötigen Sie nur den Ausdruck \* *Ii* = *t* gültig sein, und er sagt nichts über die **Operator** oder `operator=` selbst. Diese Memberoperatoren geben beide **\*this** zurück.

Der Zuweisungsoperator erstellt zuerst das nächste Objekt in der Ausgabesequenz, mithilfe des gespeicherten Iteratorwerts, indem die Platzierung des neuer Ausdrucks **new** (( `void` \*) &\* **first**) **Typ**( `val`) bewertet wird.

### <a name="example"></a>Beispiel

```cpp
// raw_storage_iterator_op_assign.cpp
// compile with: /EHsc
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

class Int
{
public:
   Int( int i )
   {
      cout << "Constructing " << i << endl;
      x = i;
      bIsConstructed = true;
   };
   Int &operator=( int i )
   {
      if ( !bIsConstructed )
         cout << "Not constructed.\n";
      cout << "Copying " << i << endl; x = i;
      return *this;
   };
   int x;
private:
   bool bIsConstructed;
};

int main( void )
{
   Int *pInt = ( Int* )malloc( sizeof( Int ) );
   memset( pInt, 0, sizeof( Int ) ); // Set bIsConstructed to false;

*pInt = 5;

   raw_storage_iterator<Int*, Int> it( pInt );
*it = 5;
}
/* Output:
Not constructed.
Copying 5
Constructing 5
*/
```

## <a name="op_add_add"></a> raw_storage_iterator::operator++

Inkrementoperatoren in Präfix- und Postfix-Notation für unformatierte Speicheriteratoren.

```cpp
raw_storage_iterator<ForwardIterator, Type>& operator++();

raw_storage_iterator<ForwardIterator, Type> operator++(int);
```

### <a name="return-value"></a>Rückgabewert

Ein unformatierten Speicheriterator oder ein Verweis auf einen unformatierten Speicheriterator.

### <a name="remarks"></a>Hinweise

Der erste Operator versucht schließlich zum Extrahieren und speichern ein Objekt des Typs `CharType` aus dem zugeordneten Eingabestream. Der zweite Operator erstellt eine Kopie des Objekts, inkrementiert das Objekt und gibt dann die Kopie zurück.

Der erste Preincrement-Operator erhöht das gespeicherte Ausgabeiteratorobjekt schrittweise, und gibt anschließend **\*this** zurück.

Der zweite Postinkrement-Operator erstellt eine Kopie von **\*this**, erhöht das gespeicherte Ausgabeiteratorobjekt und gibt dann die Kopie zurück.

Der Konstruktor speichert `first` wie die Ausgabe-Iterator-Objekt.

### <a name="example"></a>Beispiel

```cpp
// raw_storage_iterator_op_incr.cpp
// compile with: /EHsc
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

int main( void )
{
   int *pInt = new int[5];
   std::raw_storage_iterator<int*,int> it( pInt );
   for ( int i = 0; i < 5; i++, it++ ) {
      *it = 2 * i;
   };

   for ( int i = 0; i < 5; i++ ) cout << "array " << i << " = " << pInt[i] << endl;;

   delete[] pInt;
}
/* Output:
array 0 = 0
array 1 = 2
array 2 = 4
array 3 = 6
array 4 = 8
*/
```

## <a name="raw_storage_iterator"></a> raw_storage_iterator::raw_storage_iterator

Erstellt einen unformatierten Speicheriterator mit einem angegebenen zugrunde liegenden Ausgabeiterator.

```cpp
explicit raw_storage_iterator(ForwardIterator first);
```

### <a name="parameters"></a>Parameter

*Erste*<br/>
Der Forward-Iterator, mit dem das `raw_storage_iterator`-Objekt erstellt wird.

### <a name="example"></a>Beispiel

```cpp
// raw_storage_iterator_ctor.cpp
// compile with: /EHsc /W3
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

class Int
{
public:
   Int(int i)
   {
      cout << "Constructing " << i << endl;
      x = i;
      bIsConstructed = true;
   };
   Int &operator=( int i )
   {
      if (!bIsConstructed)
         cout << "Error! I'm not constructed!\n";
      cout << "Copying " << i << endl;  x = i; return *this;
   };
   int x;
   bool bIsConstructed;
};

int main( void )
{
   std::list<int> l;
   l.push_back( 1 );
   l.push_back( 2 );
   l.push_back( 3 );
   l.push_back( 4 );

   Int *pInt = (Int*)malloc(sizeof(Int)*l.size( ));
   memset (pInt, 0, sizeof(Int)*l.size( ));
   // Hack: make sure bIsConstructed is false

   std::copy( l.begin( ), l.end( ), pInt );  // C4996
   for (unsigned int i = 0; i < l.size( ); i++)
      cout << "array " << i << " = " << pInt[i].x << endl;;

   memset (pInt, 0, sizeof(Int)*l.size( ));
   // hack: make sure bIsConstructed is false

   std::copy( l.begin( ), l.end( ),
      std::raw_storage_iterator<Int*,Int>(pInt));  // C4996
   for (unsigned int i = 0; i < l.size( ); i++ )
      cout << "array " << i << " = " << pInt[i].x << endl;

   free(pInt);
}
/* Output:
Error! I'm not constructed!
Copying 1
Error! I'm not constructed!
Copying 2
Error! I'm not constructed!
Copying 3
Error! I'm not constructed!
Copying 4
array 0 = 1
array 1 = 2
array 2 = 3
array 3 = 4
Constructing 1
Constructing 2
Constructing 3
Constructing 4
array 0 = 1
array 1 = 2
array 2 = 3
array 3 = 4
*/
```

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
