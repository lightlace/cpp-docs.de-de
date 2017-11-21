---
title: '&lt;ostream&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ostream/std::swap
- ostream/std::endl
- ostream/std::ends
- ostream/std::flush
ms.assetid: d6e56cc0-c8df-4dbe-be10-98e14c35ed3a
caps.latest.revision: "15"
manager: ghogen
helpviewer_keywords:
- std::swap [C++]
- std::endl [C++]
- std::ends [C++]
- std::flush [C++]
ms.openlocfilehash: 252a178f1ce71c30bdd830811cbce59b22acc791
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ltostreamgt-functions"></a>&lt;ostream&gt;-Funktionen
||||  
|-|-|-|  
|[swap](#swap)|[endl](#endl)|[ends](#ends)|  
|[flush](#flush)|  
  
##  <a name="endl"></a> endl  
 Beendet eine Zeile und leert den Puffer.  
  
```  
template class<Elem, Tr> basic_ostream<Elem, Tr>& endl(basic_ostream<Elem, Tr>& Ostr);
```  
  
### <a name="parameters"></a>Parameter  
 `Elem`  
 Der Elementtyp.  
  
 `Ostr`  
 Ein Objekt vom Typ `basic_ostream`.  
  
 `Tr`  
 Zeichenmerkmale.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Objekt vom Typ `basic_ostream`.  
  
### <a name="remarks"></a>Hinweise  
 Der Manipulator ruft `Ostr`**.**[put](../standard-library/basic-ostream-class.md#put)( `Ostr`**.** auf. [widen](../standard-library/basic-ios-class.md#widen)( **'\n'**)) und dann `Ostr`**.** [flush](../standard-library/basic-ostream-class.md#flush). Er gibt `Ostr` zurück.  
  
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
  
##  <a name="ends"></a> ends  
 Beendet eine Zeichenfolge.  
  
```  
template class<Elem, Tr> basic_ostream<Elem, Tr>& ends(basic_ostream<Elem, Tr>& Ostr);
```  
  
### <a name="parameters"></a>Parameter  
 `Elem`  
 Der Elementtyp.  
  
 `Ostr`  
 Ein Objekt vom Typ `basic_ostream`.  
  
 `Tr`  
 Zeichenmerkmale.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Objekt vom Typ `basic_ostream`.  
  
### <a name="remarks"></a>Hinweise  
 Der Manipulator ruft `Ostr`**.**[put](../standard-library/basic-ostream-class.md#put)( `Elem`( **'\0'**)) auf. Er gibt `Ostr.` zurück.  
  
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
  
##  <a name="flush"></a> flush  
 Leert den Puffer.  
  
```  
template class<Elem, Tr> basic_ostream<Elem, Tr>& flush(basic_ostream<Elem, Tr>& Ostr);
```  
  
### <a name="parameters"></a>Parameter  
 `Elem`  
 Der Elementtyp.  
  
 `Ostr`  
 Ein Objekt vom Typ `basic_ostream`.  
  
 `Tr`  
 Zeichenmerkmale.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Objekt vom Typ `basic_ostream`.  
  
### <a name="remarks"></a>Hinweise  
 Der Manipulator ruft `Ostr`**.**[flush](../standard-library/basic-ostream-class.md#flush) auf. Er gibt `Ostr` zurück.  
  
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
  
##  <a name="swap"></a> swap  
 Tauscht die Werte zweier `basic_ostream`-Objekte aus.  
  
```  
template <class Elem, class Tr>  
void swap(
    basic_ostream<Elem, Tr>& left,  
    basic_ostream<Elem, Tr>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `left`  
 Ein lvalue-Verweis auf ein `basic_ostream`-Objekt.  
  
 `right`  
 Ein lvalue-Verweis auf ein `basic_ostream`-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Vorlagenfunktion `swap` führt `left.swap(right)` aus.  
  
## <a name="see-also"></a>Siehe auch  
 [\<ostream>](../standard-library/ostream.md)

