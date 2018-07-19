---
title: '&lt;ostream&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ostream/std::swap
- ostream/std::endl
- ostream/std::ends
- ostream/std::flush
ms.assetid: d6e56cc0-c8df-4dbe-be10-98e14c35ed3a
helpviewer_keywords:
- std::swap [C++]
- std::endl [C++]
- std::ends [C++]
- std::flush [C++]
ms.openlocfilehash: d30ad23956c978ee47ef447463a0d5422a94d4b9
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962321"
---
# <a name="ltostreamgt-functions"></a>&lt;ostream&gt;-Funktionen

Hierbei handelt es sich um die globale Vorlagenfunktionen, die in definierten &lt;Ostream&gt;. Member-Funktionen, finden Sie unter den [Basic_ostream-Klasse](basic-ostream-class.md) Dokumentation.

||||
|-|-|-|
|[endl](#endl)|[ends](#ends)|[flush](#flush)|
|[swap](#swap)|

## <a name="endl"></a>endl

Beendet eine Zeile und leert den Puffer.

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& endl(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>Parameter

*Elem* Typ des Elements.

*Ostr* ein Objekt des Typs **Basic_ostream**.

*TR* "traits"-Zeichen.

### <a name="return-value"></a>Rückgabewert

Ein Objekt des Typs **Basic_ostream**.

### <a name="remarks"></a>Hinweise

Der Manipulator ruft *Ostr*.[ Put](../standard-library/basic-ostream-class.md#put)(*Ostr*.[ Widen](../standard-library/basic-ios-class.md#widen)('\n')), und ruft dann *Ostr*.[ leeren](../standard-library/basic-ostream-class.md#flush). Es gibt *Ostr*.

### <a name="example"></a>Beispiel

```cpp
// ostream_endl.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "testing" << endl;
}
```

```Output
testing
```

## <a name="ends"></a>Ends

Beendet eine Zeichenfolge.

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& ends(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>Parameter

*Elem* Typ des Elements.

*Ostr* ein Objekt des Typs `basic_ostream`.

*TR* "traits"-Zeichen.

### <a name="return-value"></a>Rückgabewert

Ein Objekt vom Typ `basic_ostream`.

### <a name="remarks"></a>Hinweise

Der Manipulator ruft *Ostr*.[ Put](../standard-library/basic-ostream-class.md#put)(*Elem*('\0')). Es gibt *Ostr*.

### <a name="example"></a>Beispiel

```cpp
// ostream_ends.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "a";
   cout << "b" << ends;
   cout << "c" << endl;
}
```

```Output
ab c
```

## <a name="flush"></a>flush

Leert den Puffer.

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& flush(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>Parameter

*Elem* Typ des Elements.

*Ostr* ein Objekt des Typs `basic_ostream`.

*TR* "traits"-Zeichen.

### <a name="return-value"></a>Rückgabewert

Ein Objekt vom Typ `basic_ostream`.

### <a name="remarks"></a>Hinweise

Der Manipulator ruft *Ostr*.[ leeren](../standard-library/basic-ostream-class.md#flush). Es gibt *Ostr*.

### <a name="example"></a>Beispiel

```cpp
// ostream_flush.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "testing" << flush;
}
```

```Output
testing
```

## <a name="swap"></a>swap

Tauscht die Werte zweier `basic_ostream`-Objekte aus.

```cpp
template <class Elem, class Tr>
void swap(
   basic_ostream<Elem, Tr>& left,
   basic_ostream<Elem, Tr>& right);
```

### <a name="parameters"></a>Parameter

*Elem* Typ des Elements.

*TR* "traits"-Zeichen.

*linken* ein Lvalue-Verweis auf eine `basic_ostream` Objekt.

*richtige* ein Lvalue-Verweis auf eine `basic_ostream` Objekt.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion `swap` führt `left.swap(right)` aus.

## <a name="see-also"></a>Siehe auch

[\<ostream>](../standard-library/ostream.md)
