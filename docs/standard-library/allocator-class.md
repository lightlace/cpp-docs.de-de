---
title: allocator-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- memory/std::allocator
- memory/std::allocator::const_pointer
- memory/std::allocator::const_reference
- memory/std::allocator::difference_type
- memory/std::allocator::pointer
- memory/std::allocator::reference
- memory/std::allocator::size_type
- memory/std::allocator::value_type
- memory/std::allocator::address
- memory/std::allocator::allocate
- memory/std::allocator::construct
- memory/std::allocator::deallocate
- memory/std::allocator::destroy
- memory/std::allocator::max_size
- memory/std::allocator::rebind
dev_langs:
- C++
helpviewer_keywords:
- std::allocator [C++]
- std::allocator [C++], const_pointer
- std::allocator [C++], const_reference
- std::allocator [C++], difference_type
- std::allocator [C++], pointer
- std::allocator [C++], reference
- std::allocator [C++], size_type
- std::allocator [C++], value_type
- std::allocator [C++], address
- std::allocator [C++], allocate
- std::allocator [C++], construct
- std::allocator [C++], deallocate
- std::allocator [C++], destroy
- std::allocator [C++], max_size
- std::allocator [C++], rebind
ms.assetid: 3fd58076-56cc-43bb-ad58-b4b7c9c6b410
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6f510e137f9b1c986e15f58cd2d2ca729d072404
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="allocator-class"></a>allocator-Klasse

Die Vorlagenklasse beschreibt ein Objekt, das die Speicherbelegung und -freigabe für Objektarrays des Typs **Type** verwaltet. Ein Objekt der **allocator**-Klasse ist das Standardzuweisungsobjekt, das in den Konstruktoren für verschiedene Containervorlagenklassen in der C++-Standardbibliothek angegeben ist.

## <a name="syntax"></a>Syntax

```cpp
template <class Type>
class allocator
```

### <a name="parameters"></a>Parameter

*Typ* den Typ des Objekts, die für den Speicher wird reserviert oder freigegeben.

## <a name="remarks"></a>Hinweise

Alle C++-Standardbibliothekcontainer verfügen über einen Vorlagenparameter, der auf **allocator** zurückgesetzt wird. Durch das Erstellen eines Containers mit einer benutzerdefinierten Zuweisung erhalten Sie die Kontrolle über die Zuweisung und können Element des Containers freisetzen.

Beispielsweise kann ein Zuweisungsobjekt Speicher in einem privaten Heap oder im freigegebenen Arbeitsspeicher zuweisen oder für kleine oder große Objektgrößen optimieren. Es könnte auch über die von ihm bereitgestellten Typdefinitionen angeben, dass über spezielle Zugriffsmethodenobjekte auf Elemente zugegriffen wird, die den freigegebenen Arbeitsspeicher verwalten, oder dass eine automatische Garbage Collection ausgeführt wird. Daher sollte eine Klasse, die den Speicher mithilfe eines Zuweisungsobjekts zuweist, diese Typen für das Deklarieren von Zeiger- und Verweisobjekten verwenden, wie dies bei den Containern in der C++-Standardbibliothek der Fall ist.

**(nur C_++98/03)** Wenn Sie eine Ableitung aus einer Zuweisungsklasse vornehmen, müssen Sie eine [rebind](#rebind)-Struktur bereitstellen, deren `_Other`-Typedef Ihre neue abgeleitete Klasse verweist.

Daher definiert eine Zuweisung die folgenden Typen:

- [pointer](#pointer) verhält sich wie ein Zeiger auf **Type**.

- [const_pointer](#const_pointer) verhält sich wie ein const-Zeiger auf **Type**.

- [reference](#reference) verhält sich wie ein Verweis auf **Type**.

- [const_reference](#const_reference) verhält sich wie ein const-Verweist auf **Type**.

Diese **Type**s geben das Format an, das Zeiger und Verweise für zugewiesene Elemente verwenden müssen. ([allocator::pointer](#pointer) entspricht nicht unbedingt **Type**\* für alle Zuweisungsobjekte, obwohl es über diese offensichtliche Definition für die **allocator**-Klasse verfügt.)

**C++11 und höher:** Verwenden Sie zum Aktivieren von „move“-Vorgängen in Ihrer Zuweisung die minimale Zuweisungsschnittstelle, und implementieren Sie den Kopierkonstruktor „== and !=“, Operatoren, „allocate“ und „deallocate“. Weitere Informationen und ein Beispiel finden Sie unter [Allocators](../standard-library/allocators.md)

## <a name="members"></a>Member

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[allocator](#allocator)|Zum Erstellen von `allocator`-Objekten verwendete Konstruktoren.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[const_pointer](#const_pointer)|Ein Typ, der einen konstanten Zeiger auf den Typ des Objekts bereitstellt, das von der Zuweisung verwaltet wird.|
|[const_reference](#const_reference)|Ein Typ, der einen konstanten Verweis auf den Typ des Objekts bereitstellt, das von der Zuweisung verwaltet wird.|
|[difference_type](#difference_type)|Ein ganzzahliger Typ mit Vorzeichen, der die Differenz zwischen Werten von Zeigern und dem Typ des Objekts, das von der Zuweisung verwaltet wird, darstellen kann.|
|[Zeiger](#pointer)|Ein Typ, der einen Zeiger auf den Typ des Objekts bereitstellt, das von der Zuweisung verwaltet wird.|
|[Verweis](#reference)|Ein Typ, der einen Verweis auf den Typ des Objekts bereitstellt, das von der Zuweisung verwaltet wird.|
|[size_type](#size_type)|Ein ganzzahliger Typ ohne Vorzeichen, der die Länge einer beliebigen Sequenz darstellen kann, die ein Objekt der Vorlagenklasse `allocator` zuordnen kann.|
|[value_type](#value_type)|Ein Typ, der von der Zuweisung verwaltet wird.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[address](#address)|Sucht die Adresse eines Objekts, dessen Wert angegeben wird.|
|[allocate](#allocate)|Ordnet einen Speicherblock zu, der groß genug ist, um mindestens eine angegebene Anzahl von Elementen zu speichern.|
|[construct](#construct)|Erstellt eine bestimmte Art von Objekt an einer bestimmten Adresse, die mit einem angegebenen Wert initialisiert wird.|
|[deallocate](#deallocate)|Gibt eine angegebene Anzahl von Objekten im Speicher frei, beginnend an einer angegebenen Position.|
|[destroy](#destroy)|Ruft einen Objektdestruktor auf, ohne die Zuordnung des Speicherplatzes aufzuheben, an dem Objekt gespeichert wurde.|
|[max_size](#max_size)|Gibt die Anzahl der Elemente vom Typ `Type` zurück, die von einem Objekt der Klasse `allocator` zugeordnet werden konnten, bevor der freie Speicherplatz verbraucht ist.|
|[rebind](#rebind)|Eine Struktur, die eine Zuweisung für Objekt eines Typs zum Zuweisen von Speicher für Objekte des anderen Typs ermöglicht.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator=](#op_eq)|Weist ein `allocator` zu einem anderen `allocator`-Objekt zu.|

## <a name="requirements"></a>Anforderungen

**Header:** \<memory>

**Namespace:** std

## <a name="address"></a> allocator::address

Sucht die Adresse eines Objekts, dessen Wert angegeben wird.

```cpp
pointer address(reference val) const;
const_pointer address(const_reference val) const;
```

### <a name="parameters"></a>Parameter

`val` Der Konstante oder nonconst Wert des Objekts, dessen Adresse gesucht wird.

### <a name="return-value"></a>Rückgabewert

Ein konstanter oder nicht konstanter Zeiger auf ein Objekt mit konstantem bzw. nicht konstantem Wert.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt die Adresse von `val` zurück, in der Form, die Zeiger für zugewiesen Elemente benutzen.

### <a name="example"></a>Beispiel

```cpp
// allocator_address.cpp
// compile with: /EHsc
#include <memory>
#include <algorithm>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   vector <int> v1;
   vector <int>::iterator v1Iter;
   vector <int>:: allocator_type v1Alloc;

   int i;
   for ( i = 1 ; i <= 7 ; i++ )
   {
      v1.push_back( 2 * i );
   }

   cout << "The original vector v1 is:\n ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )
      cout << *v1Iter << " ";
   cout << ")." << endl;

   allocator<int>::const_pointer v1Ptr;
   const int k = 8;
   v1Ptr = v1Alloc.address( *find(v1.begin( ), v1.end( ), k) );
   // v1Ptr = v1Alloc.address( k );
   cout << "The integer addressed by v1Ptr has a value of: "
        << "*v1Ptr = " << *v1Ptr << "." << endl;
}
```

```Output
The original vector v1 is:
 ( 2 4 6 8 10 12 14 ).
The integer addressed by v1Ptr has a value of: *v1Ptr = 8.
```

## <a name="allocate"></a> allocator::allocate

Ordnet einen Speicherblock zu, der groß genug ist, um mindestens eine angegebene Anzahl von Elementen zu speichern.

```cpp
pointer allocate(size_type count, const void* _Hint);
```

### <a name="parameters"></a>Parameter

`count` Die Anzahl der Elemente, die für die ist ausreichend Speicherplatz zugeordnet werden soll.

*_Hint* ein konstanter Zeiger, die das Zuordnungsobjekt unterstützen möglicherweise erfüllen die Anforderung für die Speicherung von Suchen der Adresse eines Objekts, das vor der Anforderung zugeordnet.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das zugewiesene Objekt oder NULL, wenn kein Arbeitsspeicher zugewiesen wurde.

### <a name="remarks"></a>Hinweise

Die Memberfunktion weist Speicherplatz zu für ein Array von count-Elementen des Typs **Type**, indem er den Operator new(`count`) aufruft. Er gibt einen Zeiger auf das zugewiesene Objekt zurück. Das hint-Argument hilft einigen Allocators dabei, die Positionierung von Verweisen zu verbessern; eine gültige Auswahl ist die Adresse eines Objekts, das schon mal vom gleichen Zuweisungsobjekt zugewiesen, aber noch nicht freigegeben wurde. Wenn Sie kein hint-Argument angeben möchten, können Sie stattdessen ein NULL-Zeigerargument verwenden.

### <a name="example"></a>Beispiel

```cpp
// allocator_allocate.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   allocator<int> v1Alloc;
   allocator<int>::pointer v1aPtr;
   v1aPtr = v1Alloc.allocate ( 10 );

   int i;
   for ( i = 0 ; i < 10 ; i++ )
   {
      v1aPtr[ i ] = i;
   }

   for ( i = 0 ; i < 10 ; i++ )
   {
      cout << v1aPtr[ i ] << " ";
   }
   cout << endl;
   v1Alloc.deallocate( v1aPtr, 10 );
}
```

```Output
0 1 2 3 4 5 6 7 8 9
```

## <a name="allocator"></a> allocator::allocator

Zum Erstellen von Zuweisungsobjekten verwendete Konstruktoren.

```cpp
allocator();
allocator(const allocator<Type>& right);
template <class Other>
allocator(const allocator<Other>& right);
```

### <a name="parameters"></a>Parameter

`right` Das Zuweisungsobjekt kopiert werden soll.

### <a name="remarks"></a>Hinweise

Der Konstruktor führt keine Aktion aus. Im Allgemeinen sollte jedoch ein von einem anderen Zuweisungsobjekt erstelltes Zuweisungsobjekt mit diesem übereinstimmen und den Austausch von Zuweisungsobjekten und die Freigabe zwischen den beiden Zuweisungsobjekten erlauben.

### <a name="example"></a>Beispiel

```cpp
// allocator_allocator.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

class Int {
public:
   Int( int i )
   {
      cout << "Constructing " << ( void* )this  << endl;
      x = i;
      bIsConstructed = true;
   };
   ~Int( )
   {
      cout << "Destructing " << ( void* )this << endl;
      bIsConstructed = false;
   };
   Int &operator++( )
   {
      x++;
      return *this;
   };
   int x;
private:
   bool bIsConstructed;
};

int main( )
{
   allocator<double> Alloc;
   vector <Int>:: allocator_type v1Alloc;

   allocator<double> cAlloc(Alloc);
   allocator<Int> cv1Alloc(v1Alloc);

   if ( cv1Alloc == v1Alloc )
      cout << "The allocator objects cv1Alloc & v1Alloc are equal."
           << endl;
   else
      cout << "The allocator objects cv1Alloc & v1Alloc are not equal."
           << endl;

   if ( cAlloc == Alloc )
      cout << "The allocator objects cAlloc & Alloc are equal."
           << endl;
   else
      cout << "The allocator objects cAlloc & Alloc are not equal."
           << endl;
}
```

```Output
The allocator objects cv1Alloc & v1Alloc are equal.
The allocator objects cAlloc & Alloc are equal.
```

## <a name="const_pointer"></a> allocator::const_pointer

Ein Typ, der einen konstanten Zeiger auf den Typ des Objekts bereitstellt, das von der Zuweisung verwaltet wird.

```cpp
typedef const value_type *const_pointer;
```

### <a name="remarks"></a>Hinweise

Der Zeigertyp beschreibt ein Objekt **ptr**, das durch den Ausdruck **\*ptr** jedes beliebige konstante Objekt angeben kann, das von einem Objekt des Vorlagenklassenallocators zugewiesen werden kann.

### <a name="example"></a>Beispiel

```cpp
// allocator_const_ptr.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   vector <int> v1;
   vector <int>::iterator v1Iter;
   vector <int>:: allocator_type v1Alloc;

   int i;
   for ( i = 1 ; i <= 7 ; i++ )
   {
      v1.push_back( i * 2 );
   }

   cout << "The original vector v1 is:\n ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )
      cout << *v1Iter << " ";
   cout << ")." << endl;

   allocator<int>::const_pointer v1Ptr;
   const int k = 10;
   v1Ptr = v1Alloc.address( k );

   cout << "The integer's address found has a value of: "
        << *v1Ptr << "." << endl;
}
```

```Output
The original vector v1 is:
 ( 2 4 6 8 10 12 14 ).
The integer's address found has a value of: 10.
```

## <a name="const_reference"></a> allocator::const_reference

Ein Typ, der einen konstanten Verweis auf den Typ des Objekts bereitstellt, das von der Zuweisung verwaltet wird.

```cpp
typedef const value_type& const_reference;
```

### <a name="remarks"></a>Hinweise

Der Verweistyp beschreibt ein Objekt, das jedes beliebige konstante Objekt angeben kann, das von einem Objekt des Vorlagenklassenallocators zugewiesen werden kann.

### <a name="example"></a>Beispiel

```cpp
// allocator_const_ref.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   vector <double> v;
   vector <double> ::iterator vIter, vfIter;
   vector <double> :: allocator_type vAlloc;

   int j;
   for ( j = 1 ; j <= 7 ; j++ )
   {
      v.push_back( 100.0 * j );
   }

   cout << "The original vector v is:\n ( " ;
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;

   vfIter = v.begin( );
   allocator<double>::const_reference vcref =*vfIter;
   cout << "The value of the element referred to by vref is: "
        << vcref << ",\n the first element in the vector." << endl;

   // const references can have their elements modified,
   // so the following would generate an error:
   // vcref = 150;
   // but the value of the first element could be modified through
   // its nonconst iterator and the const reference would remain valid
 *vfIter = 175;
   cout << "The value of the element referred to by vcref,"
        <<"\n after nofication through its nonconst iterator, is: "
        << vcref << "." << endl;
}
```

```Output
The original vector v is:
 ( 100 200 300 400 500 600 700 ).
The value of the element referred to by vref is: 100,
 the first element in the vector.
The value of the element referred to by vcref,
 after nofication through its nonconst iterator, is: 175.
```

## <a name="construct"></a> allocator::construct

Erstellt eine bestimmte Art von Objekt an einer bestimmten Adresse, die mit einem angegebenen Wert initialisiert wird.

```cpp
void construct(pointer ptr, const Type& val);
void construct(pointer ptr, Type&& val);
template <class _Other>
void construct(pointer ptr, _Other&&...   val);
```

### <a name="parameters"></a>Parameter

`ptr` Ein Zeiger auf den Speicherort, an dem das Objekt erstellt werden.

`val` Der Wert, mit denen der zu erstellte Objekt initialisiert werden.

### <a name="remarks"></a>Hinweise

Die erste Memberfunktion ist äquivalent zu **new** ((`void`\*)`ptr`) **Type** (`val`).

### <a name="example"></a>Beispiel

```cpp
// allocator_construct.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <algorithm>
#include <vector>

using namespace std;

int main( )
{
   vector <int> v1;
   vector <int>::iterator v1Iter;
   vector <int>:: allocator_type v1Alloc;

   int i;
   for ( i = 1 ; i <= 7 ; i++ )
   {
      v1.push_back( 3 * i );
   }

   cout << "The original vector v1 is:\n ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )
      cout << *v1Iter << " ";
   cout << ")." << endl;

   allocator<int>::pointer v1PtrA;
   int kA = 6, kB = 7;
   v1PtrA = v1Alloc.address( *find( v1.begin( ), v1.end( ), kA ) );
   v1Alloc.destroy ( v1PtrA );
   v1Alloc.construct ( v1PtrA , kB );

   cout << "The modified vector v1 is:\n ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )
      cout << *v1Iter << " ";
   cout << ")." << endl;
}
```

```Output
The original vector v1 is:
 ( 3 6 9 12 15 18 21 ).
The modified vector v1 is:
 ( 3 7 9 12 15 18 21 ).
```

## <a name="deallocate"></a> allocator::deallocate

Gibt eine angegebene Anzahl von Objekten im Speicher frei, beginnend an einer angegebenen Position.

```cpp
void deallocate(pointer ptr, size_type count);
```

### <a name="parameters"></a>Parameter

`ptr` Ein Zeiger auf das erste Objekt aus dem Speicher freigegeben werden muss.

`count` Die Anzahl der Objekte aus dem Speicher freigegeben werden muss.

### <a name="remarks"></a>Hinweise

Die Memberfunktion Speicherplatz für das Array von Anzahl von Objekten des Typs frei **Typ** beginnend `ptr`, durch den Aufruf `operator delete(ptr)`. Der Zeiger `ptr` muss für ein Zuweisungsobjekt, das gleich **\*this** ist,von einem Aufruf an [allocate](#allocate) zurückgegeben worden sein, damit er ein Arrayobjekt der gleichen Größe und des gleichen Typs zuweisen kann. `deallocate` löst nie eine Ausnahme aus.

### <a name="example"></a>Beispiel

Ein Beispiel für den Gebrauch dieser Memberfunktion finden Sie unter [allocator::allocate](#allocate).

## <a name="destroy"></a> allocator::destroy

Ruft einen Objektdestruktor auf, ohne die Zuordnung des Speicherplatzes aufzuheben, an dem Objekt gespeichert wurde.

```cpp
void destroy(pointer ptr);
```

### <a name="parameters"></a>Parameter

`ptr` Ein Zeiger, der die Adresse des Objekts gelöscht werden, festlegen.

### <a name="remarks"></a>Hinweise

Die Memberfunktion zerstört das Objekt vom angegebenen `ptr`, durch Aufrufen des Destruktors `ptr->` **Typ**::**~ Typ**.

### <a name="example"></a>Beispiel

```cpp
// allocator_destroy.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <algorithm>
#include <vector>

using namespace std;

int main( )
{
   vector <int> v1;
   vector <int>::iterator v1Iter;
   vector <int>:: allocator_type v1Alloc;

   int i;
   for ( i = 1 ; i <= 7 ; i++ )
   {
      v1.push_back( 2 * i );
   }

   cout << "The original vector v1 is:\n ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )
      cout << *v1Iter << " ";
   cout << ")." << endl;

   allocator<int>::pointer v1PtrA;
   int kA = 12, kB = -99;
   v1PtrA = v1Alloc.address( *find(v1.begin( ), v1.end( ), kA) );
   v1Alloc.destroy ( v1PtrA );
   v1Alloc.construct ( v1PtrA , kB );

   cout << "The modified vector v1 is:\n ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )
      cout << *v1Iter << " ";
   cout << ")." << endl;
}
```

```Output
The original vector v1 is:
 ( 2 4 6 8 10 12 14 ).
The modified vector v1 is:
 ( 2 4 6 8 10 -99 14 ).
```

## <a name="difference_type"></a> allocator::difference_type

Ein ganzzahliger Typ mit Vorzeichen, der die Differenz zwischen Werten von Zeigern und dem Typ des Objekts, das von der Zuweisung verwaltet wird, darstellen kann.

```cpp
typedef ptrdiff_t difference_type;
```

### <a name="remarks"></a>Hinweise

Der Ganzzahltyp mit Vorzeichen beschreibt ein Objekt, das den unterschied zwischen den Adressen von zwei beliebigen Elementen in einer Sequenz darstellen kann, die von einem Objekt eines Vorlagenklassenallocators zugewiesen werden kann.

### <a name="example"></a>Beispiel

```cpp
// allocator_diff_type.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   vector <int> v1;
   vector <int>::iterator v1Iter;
   vector <int>:: allocator_type v1Alloc;

   int i;
   for ( i = 0 ; i <= 7 ; i++ )
   {
      v1.push_back( i * 2 );
   }

   cout << "The original vector v1 is:\n ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )
      cout << *v1Iter << " ";
   cout << ")." << endl;

   allocator<int>::const_pointer v1PtrA, v1PtrB;
   const int kA = 4, kB =12;
   v1PtrA = v1Alloc.address( kA );
   v1PtrB = v1Alloc.address( kB );
   allocator<int>::difference_type v1diff = *v1PtrB - *v1PtrA;

   cout << "Pointer v1PtrA addresses " << *v1PtrA << "." << endl;
   cout << "Pointer v1PtrB addresses " << *v1PtrB <<  "." << endl;
   cout << "The difference between the integer's addresses is: "
        << v1diff << "." << endl;
}
```

```Output
The original vector v1 is:
 ( 0 2 4 6 8 10 12 14 ).
Pointer v1PtrA addresses 4.
Pointer v1PtrB addresses 12.
The difference between the integer's addresses is: 8.
```

## <a name="max_size"></a> allocator::max_size

Gibt die Anzahl der Elemente vom Typ **Type** zurück, die von einem Objekt der Klassenzuweisung zugeordnet werden konnten, bevor der freie Speicherplatz verbraucht ist.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl von Elementen, die zugewiesen werden konnten.

### <a name="example"></a>Beispiel

```cpp
// allocator_max_size.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   vector <int> v1;
   vector <int>::iterator v1Iter;
   vector <int>:: allocator_type v1Alloc;

   int i;
   for ( i = 1 ; i <= 7 ; i++ )
   {
      v1.push_back( i );
   }

   cout << "The original vector v1 is:\n ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )
      cout << *v1Iter << " ";
   cout << ")." << endl;

   vector <double> v2;
   vector <double> ::iterator v2Iter;
   vector <double> :: allocator_type v2Alloc;
   allocator<int>::size_type v1size;
   v1size = v1Alloc.max_size( );

   cout << "The number of integers that can be allocated before\n"
        << " the free memory in the vector v1 is used up is: "
        << v1size << "." << endl;

   int ii;
   for ( ii = 1 ; ii <= 7 ; ii++ )
   {
      v2.push_back( ii * 10.0 );
   }

   cout << "The original vector v2 is:\n ( " ;
   for ( v2Iter = v2.begin( ) ; v2Iter != v2.end( ) ; v2Iter++ )
      cout << *v2Iter << " ";
   cout << ")." << endl;
   allocator<double>::size_type v2size;
   v2size = v2Alloc.max_size( );

   cout << "The number of doubles that can be allocated before\n"
        << " the free memory in the vector v2 is used up is: "
        << v2size << "." << endl;
}
```

## <a name="op_eq"></a> allocator::operator=

Weist einem Zuweisungsobjekt ein anderes Zuweisungsobjekt zu.

```cpp
template <class Other>
allocator<Type>& operator=(const allocator<Other>& right);
```

### <a name="parameters"></a>Parameter

`right` Ein Zuweisungsobjekt, einem anderen Objekt zugewiesen werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Zuweisungsobjekt

### <a name="remarks"></a>Hinweise

Der Vorlagenzuweisungsoperator führt keine Aktion aus. Im Allgemeinen sollte jedoch ein einem anderen Zuweisungsobjekt zugewiesenes Zuweisungsobjekt mit diesem übereinstimmen und den Austausch von Zuweisungsobjekten und die Freigabe zwischen den beiden Zuweisungsobjekten erlauben.

### <a name="example"></a>Beispiel

```cpp
// allocator_op_assign.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

class Int {
public:
   Int(int i)
   {
      cout << "Constructing " << ( void* )this  << endl;
      x = i;
      bIsConstructed = true;
   };
   ~Int( ) {
      cout << "Destructing " << ( void* )this << endl;
      bIsConstructed = false;
   };
   Int &operator++( )
   {
      x++;
      return *this;
   };
   int x;
private:
   bool bIsConstructed;
};

int main( )
{
   allocator<Int> Alloc;
   allocator<Int> cAlloc ;
   cAlloc = Alloc;
}
```

## <a name="pointer"></a> allocator::pointer

Ein Typ, der einen Zeiger auf den Typ des Objekts bereitstellt, das von der Zuweisung verwaltet wird.

```cpp
typedef value_type *pointer;
```

### <a name="remarks"></a>Hinweise

Der Zeigertyp beschreibt ein Objekt **ptr**, das durch den Ausdruck **\*ptr** jedes beliebige Objekt angeben kann, das von einem Objekt des Vorlagenklassenallocators zugewiesen werden kann.

### <a name="example"></a>Beispiel

```cpp
// allocator_ptr.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   vector <int> v1;
   vector <int>::iterator v1Iter;
   vector <int>:: allocator_type v1Alloc;

   int i;
   for ( i = 1 ; i <= 7 ; i++ )
   {
      v1.push_back( 3 * i );
   }

   cout << "The original vector v1 is:\n ( " ;
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )
      cout << *v1Iter << " ";
   cout << ")." << endl;

   allocator<int>::const_pointer v1Ptr;
   const int k = 12;
   v1Ptr = v1Alloc.address( k );

   cout << "The integer addressed by v1Ptr has a value of: "
        << "*v1Ptr = " << *v1Ptr << "." << endl;
}
```

```Output
The original vector v1 is:
 ( 3 6 9 12 15 18 21 ).
The integer addressed by v1Ptr has a value of: *v1Ptr = 12.
```

## <a name="rebind"></a> allocator::rebind

Eine Struktur, die eine Zuweisung für Objekt eines Typs zum Zuweisen von Speicher für Objekte des anderen Typs ermöglicht.
```cpp
struct rebind {    typedef allocator<_Other> other ;    };
```
### <a name="parameters"></a>Parameter

*andere* der Typ des Elements für das belegen von Arbeitsspeicher.

### <a name="remarks"></a>Hinweise

Diese Struktur ist nützlich beim Zuweisen von Arbeitsspeicher für einen Typ, der sich vom Elementtyp des zu implementierenden Containers unterscheidet.

Die Membervorlagenklasse definiert den Typ „other“. Ihr einziger Zweck ist es, den Typnamen **allocator**\<_ **_Other**> bereitzustellen, wenn der Typname **allocator**\<**Type**> ist.

Hat man z.B. ein Zuweisungsobjekt **al** des Typs **A**, können Sie ein Objekt des Typ **_Other** mit folgendem Ausdruck zuweisen:

```cpp
A::rebind<Other>::other(al).allocate(1, (Other *)0)
```

Oder Sie können dessen Zeigertyp benennen, indem Sie Folgendes eingeben:

```cpp
A::rebind<Other>::other::pointer
```

### <a name="example"></a>Beispiel

```cpp
// allocator_rebind.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <algorithm>
#include <vector>

using namespace std;

typedef vector<int>::allocator_type IntAlloc;
int main( )
{
   IntAlloc v1Iter;
   vector<int> v1;

   IntAlloc::rebind<char>::other::pointer pszC =
      IntAlloc::rebind<char>::other(v1.get_allocator()).allocate(1, (void *)0);

   int * pInt = v1Iter.allocate(10);
}
```

## <a name="reference"></a> allocator::reference

Ein Typ, der einen Verweis auf den Typ des Objekts bereitstellt, das von der Zuweisung verwaltet wird.

```cpp
typedef value_type& reference;
```

### <a name="remarks"></a>Hinweise

Der Verweistyp beschreibt ein Objekt, das jedes beliebige Objekt angeben kann, das von einem Objekt des Vorlagenklassenallocators zugewiesen werden kann.

### <a name="example"></a>Beispiel

```cpp
// allocator_reference.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   vector <double> v;
   vector <double> ::iterator vIter, vfIter;
   vector <double> :: allocator_type vAlloc;

   int j;
   for ( j = 1 ; j <= 7 ; j++ )
   {
      v.push_back( 100.0 * j );
   }

   cout << "The original vector v is:\n ( " ;
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;

   vfIter = v.begin( );
   allocator<double>::reference vref =*vfIter;
   cout << "The value of the element referred to by vref is: "
        << vref << ",\n the first element in the vector." << endl;

   // nonconst references can have their elements modified
   vref = 150;
   cout << "The element referred to by vref after being modified is: "
        << vref << "." << endl;
}
```

```Output
The original vector v is:
 ( 100 200 300 400 500 600 700 ).
The value of the element referred to by vref is: 100,
 the first element in the vector.
The element referred to by vref after being modified is: 150.
```

## <a name="size_type"></a> allocator::size_type

Ein ganzzahliger Typ ohne Vorzeichen, der die Länge einer beliebigen Sequenz darstellen kann, die ein Objekt der Vorlagenklassenzuweisung zuweisen kann.

```cpp
typedef size_t size_type;
```

### <a name="example"></a>Beispiel

```cpp
// allocator_size_type.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   vector <double> v;
   vector <double> ::iterator vIter;
   vector <double> :: allocator_type vAlloc;

   int j;
   for ( j = 1 ; j <= 7 ; j++ )
   {
      v.push_back( 100.0 * j );
   }

   cout << "The original vector v is:\n ( " ;
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;

   allocator<double>::size_type vsize;
   vsize = vAlloc.max_size( );

   cout << "The number of doubles that can be allocated before\n"
        << " the free memory in the vector v is used up is: "
        << vsize << "." << endl;
}
```

## <a name="value_type"></a> allocator::value_type

Ein Typ, der von der Zuweisung verwaltet wird.

```cpp
typedef Type value_type;
```

### <a name="remarks"></a>Hinweise

Der Typ stellt ein Synonym für den Vorlagenparameter **Type** dar.

### <a name="example"></a>Beispiel

```cpp
// allocator_value_type.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>
using namespace std;

int main( )
{
   vector <double> v;
   vector <double> ::iterator vIter, vfIter;
   vector <double> :: allocator_type vAlloc;

   int j;
   for ( j = 1 ; j <= 7 ; j++ )
   {
      v.push_back( 100.0 * j );
   }

   cout << "The original vector v is:\n ( " ;
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;

   vfIter = v.begin( );
   allocator<double>::value_type vecVal = 150.0;
 *vfIter = vecVal;
   cout << "The value of the element addressed by vfIter is: "
        << *vfIter << ",\n the first element in the vector." << endl;

   cout << "The modified vector v is:\n ( " ;
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;
}
```

```Output
The original vector v is:
 ( 100 200 300 400 500 600 700 ).
The value of the element addressed by vfIter is: 150,
 the first element in the vector.
The modified vector v is:
 ( 150 200 300 400 500 600 700 ).
```

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
