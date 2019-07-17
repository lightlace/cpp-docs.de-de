---
title: '&lt;new&gt;-Funktionen'
ms.date: 11/04/2016
f1_keywords:
- new/std::get_new_handler
- new/std::nothrow
- new/std::set_new_handler
ms.assetid: e250f06a-b025-4509-ae7a-5356d56aad7d
ms.openlocfilehash: c912e5be07ea0ebdd3148d30c80c39a5f8cfa1a5
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68243669"
---
# <a name="ltnewgt-functions"></a>&lt;new&gt;-Funktionen

## <a name="get_new_handler"></a> get_new_handler

```cpp
new_handler get_new_handler() noexcept;
```

### <a name="remarks"></a>Hinweise

Gibt die aktuelle `new_handler`.

## <a name="launder"></a> Profis

```cpp
template <class T>
    constexpr T* launder(T* ptr) noexcept;
```

### <a name="parameters"></a>Parameter

*PTR*\
Die Adresse eines Bytes in den Arbeitsspeicher, der ein Objekt, dessen Typ enthält ähnelt *T*.

### <a name="return-value"></a>Rückgabewert

Ein Wert vom Typ *T\**  , die auf X verweist.

### <a name="remarks"></a>Hinweise

Auch bezeichnet als Barriere Optimierung Zeiger.

Als ein konstanter Ausdruck verwendet, wenn der Wert des Arguments in einem konstanten Ausdruck verwendet werden kann. Ein Byte des Speichers ist erreichbar über ein Zeigerwert, der auf ein Objekt verweist, wenn in den Speicher, der durch ein anderes Objekt ein Objekt mit einem ähnlichen Zeiger belegt wird.

### <a name="example"></a>Beispiel

```cpp
struct X { const int n; };

X *p = new X{3};
const int a = p->n;
new (p) X{5}; // p does not point to new object because X::n is const
const int b = p->n; // undefined behavior
const int c = std::launder(p)->n; // OK
```

## <a name="nothrow"></a> nothrow

Stellt ein Objekt als Argument für die **Nothrow** Versionen von **neue** und **löschen**.

```cpp
extern const std::nothrow_t nothrow;
```

### <a name="remarks"></a>Hinweise

Das Objekt wird als Funktionsargument verwendet, um auf den Parametertyp [std::nothrow_t](../standard-library/nothrow-t-structure.md) abzustimmen.

### <a name="example"></a>Beispiel

Beispiele zur Verwendung von `std::nothrow_t` als Funktionsparameter finden Sie unter [operator new](../standard-library/new-operators.md#op_new) und [operator new&#91;&#93;](../standard-library/new-operators.md#op_new_arr).

## <a name="set_new_handler"></a> set_new_handler

Installiert eine Benutzerfunktion, die aufgerufen werden soll **new-Operator** nicht in der Lage, um Speicher zu belegen.

```cpp
new_handler set_new_handler(new_handler Pnew) throw();
```

### <a name="parameters"></a>Parameter

*PDAs*\
Die `new_handler` installiert werden.

### <a name="return-value"></a>Rückgabewert

0 (null) beim ersten Aufruf und der vorherige `new_handler` bei nachfolgenden Aufrufen.

### <a name="remarks"></a>Hinweise

Die Funktion speichert *PDAs* in einer statischen [neuen Handler](../standard-library/new-typedefs.md#new_handler) Zeiger, die er verwaltet, gibt anschließend den Wert, der zuvor im Zeiger gespeichert. Der neue Handler wird verwendet, indem [new-Operator](../standard-library/new-operators.md#op_new)( **"size_t"** ).

### <a name="example"></a>Beispiel

```cpp
// new_set_new_handler.cpp
// compile with: /EHsc
#include<new>
#include<iostream>

using namespace std;
void __cdecl newhandler( )
{
   cout << "The new_handler is called:" << endl;
   throw bad_alloc( );
   return;
}

int main( )
{
   set_new_handler (newhandler);
   try
   {
      while ( 1 )
      {
         new int[5000000];
         cout << "Allocating 5000000 ints." << endl;
      }
   }
   catch ( exception e )
   {
      cout << e.what( ) << endl;
   }
}
```

```Output
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
The new_handler is called:
bad allocation
```
