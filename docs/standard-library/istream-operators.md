---
title: '&lt;istream&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7174da41-f301-4a34-b631-0ab918b188d2
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 4c2a2f8c2c2b55e3c14db9e44a4b05041c0ecfc9
ms.lasthandoff: 02/24/2017

---
# <a name="ltistreamgt-operators"></a>&lt;iStream&gt;-Operatoren
 
##  <a name="a-nameoperatorgtgta--operatorgtgt"></a><a name="operator_gt__gt_"></a> Operator&gt;&gt;  
 Extrahiert von Zeichenfolgen und Zeichen aus dem Stream.  
  
```  
template <class Elem, class Tr>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,   
    Elem* str);

template <class Elem, class Tr>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,   
    Elem& Ch);

template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,   
    signed char* str);

template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,   
    signed char& Ch);

template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,   
    unsigned char* str);

template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,   
    unsigned char& Ch);

template <class Elem, class Tr, class Type>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,  
    Type& val);
```  
  
### <a name="parameters"></a>Parameter  
 `Ch`  
 Ein Zeichen.  
  
 `Istr`  
 Ein Stream.  
  
 ` str`  
 Eine Zeichenfolge.  
  
 ` val`  
 Ein Typ.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Stream  
  
### <a name="remarks"></a>Hinweise  
 Die `basic_istream`-Klasse definiert außerdem mehrere Extraktionsoperatoren. Weitere Informationen finden Sie unter [basic_istream::operator>>](../standard-library/basic-istream-class.md#basic_istream__operator_gt__gt_).  
  
 Die Vorlagenfunktion:  
  
```cpp  
template <class Elem, class Tr>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem* str);
```  
  
 extrahiert bis zu *N*-1-Elemente und speichert sie in das Array, beginnend mit _*Str*. If `Istr`. [Breite](../standard-library/ios-base-class.md#ios_base__width) ist größer als&0; (null), *N* ist `Istr`. **Breite**, andernfalls ist die Größe des größten Arrays von **Elem** deklariert werden kann. Die Funktion speichert immer den Wert **Elem()** nach beliebigen extrahierten Elementen, die gespeichert werden. Die Extraktion hält früh am Ende der Datei, an einem Zeichen mit dem Wert **Elem**(0) (das nicht extrahiert wurde), oder an einem beliebigen Element (das nicht extrahiert wurde), welches von [ws](../standard-library/istream-functions.md#ws) verworfen werden würde. Wenn die Funktion keine Elemente extrahiert, ruft es `Istr`. [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **failbit**) auf. In jedem Fall ruft es `Istr`. **Breite**(0) und gibt `Istr`.  
  
 **Sicherheitshinweis** Die null-terminierte Zeichenfolge, die aus dem Eingabestream extrahiert wird, darf nicht die Größe des Zielpuffers ` str` überschreiten. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
 Die Vorlagenfunktion:  
  
```cpp  
template <class Elem, class Tr>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem& Ch);
```  
  
 extrahiert ein Element, wenn möglich, und speichert es in `Ch`. Andernfalls ruft sie **ist**. [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **failbit**) auf. In jedem Fall gibt sie `Istr` zurück.  
  
 Die Vorlagenfunktion:  
  
```cpp  
template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char* str);
```  
  
 gibt `Istr` >> ( `char`**\***) ` str` zurück.  
  
 Die Vorlagenfunktion:  
  
```cpp  
template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char& Ch);
```  
  
 gibt `Istr` >> ( **char&**) `Ch` zurück.  
  
 Die Vorlagenfunktion:  
  
```cpp  
template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char* str);
```  
  
 gibt `Istr` >> ( **char \***) ` str` zurück.  
  
 Die Vorlagenfunktion:  
  
```cpp  
template <class Tr>  
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char& Ch);
```  
  
 gibt `Istr` >> ( **char&**) `Ch` zurück.  
  
 Die Vorlagenfunktion:  
  
```cpp  
template <class Elem, class Tr, class Type>  
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,  
    Type& val);
```  
  
 gibt `Istr` `>>` ` val` (und konvertiert ein `rvalue reference` auf `Istr` zu einer `lvalue` im Prozess).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// istream_op_extract.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )   
{  
   ws( cin );  
   char c[10];  
  
   cin.width( 9 );  
   cin >> c;  
   cout << c << endl;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [\<istream>](../standard-library/istream.md)


