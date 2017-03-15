---
title: '&lt;ostream&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6e56cc0-c8df-4dbe-be10-98e14c35ed3a
caps.latest.revision: 15
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 44708461657101b1ddad7db76f1c3c8d4df07f3a
ms.lasthandoff: 02/24/2017

---
# <a name="ltostreamgt-functions"></a>&lt;ostream&gt;-Funktionen
||||  
|-|-|-|  
|[swap](#swap)|[endl](#endl)|[ends](#ends)|  
|[flush](#flush)|  
  
##  <a name="a-nameendla--endl"></a><a name="endl"></a> endl  
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
 Der Manipulator ruft `Ostr`**.**[put](../standard-library/basic-ostream-class.md#basic_ostream__put)( `Ostr`**.** auf. [widen](../standard-library/basic-ios-class.md#basic_ios__widen)( **'\n'**)) und dann `Ostr`**.** [flush](../standard-library/basic-ostream-class.md#basic_ostream__flush). Er gibt `Ostr` zurück.  
  
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
  
##  <a name="a-nameendsa--ends"></a><a name="ends"></a> ends  
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
 Der Manipulator ruft `Ostr`**.**[put](../standard-library/basic-ostream-class.md#basic_ostream__put)( `Elem`( **'\0'**)) auf. Er gibt `Ostr.` zurück.  
  
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
  
##  <a name="a-nameflusha--flush"></a><a name="flush"></a> flush  
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
 Der Manipulator ruft `Ostr`**.**[flush](../standard-library/basic-ostream-class.md#basic_ostream__flush) auf. Er gibt `Ostr` zurück.  
  
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
  
##  <a name="a-nameswapa--swap"></a><a name="swap"></a> swap  
 Tauscht die Werte zweier `basic_ostream`-Objekte aus.  
  
```  
template <class Elem, class Tr>  
void swap(
    basic_ostream<Elem, Tr>& left,  
    basic_ostream<Elem, Tr>& right);
```  
  
### <a name="parameters"></a>Parameter  
 ` left`  
 Ein lvalue-Verweis auf ein `basic_ostream`-Objekt.  
  
 ` right`  
 Ein lvalue-Verweis auf ein `basic_ostream`-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Vorlagenfunktion `swap` führt ` left.swap(`` right``)` aus.  
  
## <a name="see-also"></a>Siehe auch  
 [\<ostream>](../standard-library/ostream.md)


