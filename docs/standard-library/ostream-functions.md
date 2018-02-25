---
title: '&lt;ostream&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ostream/std::swap
- ostream/std::endl
- ostream/std::ends
- ostream/std::flush
ms.assetid: d6e56cc0-c8df-4dbe-be10-98e14c35ed3a
caps.latest.revision: 
manager: ghogen
helpviewer_keywords:
- std::swap [C++]
- std::endl [C++]
- std::ends [C++]
- std::flush [C++]
ms.openlocfilehash: 4693e33563048807cdef1c81cb4d47d4fb455137
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ltostreamgt-functions"></a>&lt;ostream&gt;-Funktionen

Hierbei handelt es sich um die globalen Vorlagenfunktionen, die in definierten &lt;Ostream&gt;. Member-Funktionen finden Sie unter der [Basic_ostream-Klasse](basic-ostream-class.md) Dokumentation.

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

*Elem*  
Der Elementtyp.

*Ostr*  
Ein Objekt des Typs **Basic_ostream**.

*Tr*  
Zeichenmerkmale.

### <a name="return-value"></a>Rückgabewert

Ein Objekt des Typs **Basic_ostream**.

### <a name="remarks"></a>Hinweise

Ruft die Manipulator *Ostr*.[ Put](../standard-library/basic-ostream-class.md#put)(*Ostr*.[ Widen](../standard-library/basic-ios-class.md#widen)("\n")), und ruft dann *Ostr*.[ Flush](../standard-library/basic-ostream-class.md#flush). Es gibt *Ostr*.

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

*Elem*  
Der Elementtyp.

*Ostr*  
Ein Objekt des Typs **Basic_ostream**.

*Tr*  
Zeichenmerkmale.

### <a name="return-value"></a>Rückgabewert

Ein Objekt des Typs **Basic_ostream**.

### <a name="remarks"></a>Hinweise

Ruft die Manipulator *Ostr*.[ Put](../standard-library/basic-ostream-class.md#put)(*Elem*('\0')). Es gibt *Ostr*.

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

*Elem*  
Der Elementtyp.

*Ostr*  
Ein Objekt des Typs **Basic_ostream**.

*Tr*  
Zeichenmerkmale.

### <a name="return-value"></a>Rückgabewert

Ein Objekt des Typs **Basic_ostream**.

### <a name="remarks"></a>Hinweise

Ruft die Manipulator *Ostr*.[ Flush](../standard-library/basic-ostream-class.md#flush). Es gibt *Ostr*.

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

Tauscht die Werte von zwei **Basic_ostream** Objekte.

```cpp
template <class Elem, class Tr>
void swap(
   basic_ostream<Elem, Tr>& left,
   basic_ostream<Elem, Tr>& right);
```

### <a name="parameters"></a>Parameter

*Elem*  
Der Elementtyp.

*Tr*  
Zeichenmerkmale.

*left*  
Ein Lvalue-Verweis auf eine **Basic_ostream** Objekt.

*right*  
Ein Lvalue-Verweis auf eine **Basic_ostream** Objekt.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion **Swap** führt `left.swap(right)`.

## <a name="see-also"></a>Siehe auch

[\<ostream>](../standard-library/ostream.md)  
