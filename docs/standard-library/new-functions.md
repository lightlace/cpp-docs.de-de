---
title: '&lt;new&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- new/std::nothrow
- new/std::set_new_handler
ms.assetid: e250f06a-b025-4509-ae7a-5356d56aad7d
ms.openlocfilehash: 6192805f0f427f86267a646b11d9f1d3365a1d57
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716039"
---
# <a name="ltnewgt-functions"></a>&lt;new&gt;-Funktionen

|||
|-|-|
|[nothrow](#nothrow)|[set_new_handler](#set_new_handler)|

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

*PDAs*<br/>
Die `new_handler` installiert werden.

### <a name="return-value"></a>Rückgabewert

0 (null) beim ersten Aufruf und der vorherige `new_handler` bei nachfolgenden Aufrufen.

### <a name="remarks"></a>Hinweise

Die Funktion speichert *PDAs* in einer statischen [neuen Handler](../standard-library/new-typedefs.md#new_handler) Zeiger, die er verwaltet, gibt anschließend den Wert, der zuvor im Zeiger gespeichert. Der neue Handler wird verwendet, indem [new-Operator](../standard-library/new-operators.md#op_new)(**"size_t"**).

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

## <a name="see-also"></a>Siehe auch

[\<new>](../standard-library/new.md)<br/>
