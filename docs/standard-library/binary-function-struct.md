---
title: "binary_function-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.binary_function"
  - "functional/std::binary_function"
  - "std::binary_function"
  - "binary_function"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "binary_function-Klasse"
ms.assetid: 79b6d53d-644c-4add-b0ba-3a5f40f69c60
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# binary_function-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine niedrige leere Struktur, die definiert Typen werden geerbt, die von abgeleiteten Klassen, das ein binäres Funktionsobjekt bereitstellt.  
  
## Syntax  
  
```  
  
   template<class Arg1, class Arg2, class Result>  
struct binary_function {  
   typedef Arg1 first_argument_type;  
   typedef Arg2 second_argument_type;  
   typedef Result result_type;  
};  
```  
  
## Hinweise  
 Die Vorlagenstruktur dient als Basisklasse für die Klassen, die eine Memberfunktion des Formulars definieren:  
  
 **result\_type operator\(\)**\( **const**,**first\_argument\_type &**  
  
 **const second\_argument\_type &** \) **const**  
  
 Alle diese Funktionen binäre können ihrem ersten Argumenttyp als **first\_argument\_type**, um den Typ des zweiten Arguments als **second\_argument\_type** und den Rückgabetyp verweisen als ***result\_type***.  
  
## Beispiel  
  
```  
// functional_binary_function.cpp  
// compile with: /EHsc  
#include <vector>  
#include <functional>  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
  
template <class Type> class average:   
binary_function<Type, Type, Type>   
{  
public:  
   result_type operator( ) ( first_argument_type a,   
                 second_argument_type b )  
   {  
      return (result_type) ( ( a + b ) / 2 );  
   }  
};  
  
int main( )  
{  
   vector <double> v1, v2, v3 ( 6 );  
   vector <double>::iterator Iter1, Iter2, Iter3;  
  
   for ( int i = 1 ; i <= 6 ; i++ )  
      v1.push_back( 11.0 / i );  
  
   for ( int j = 0 ; j <= 5 ; j++ )  
      v2.push_back( -2.0 * j );  
  
   cout << "The vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   cout << "The vector v2 = ( " ;  
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )  
      cout << *Iter2 << " ";  
   cout << ")" << endl;  
  
   // Finding the element-wise averages of the elements of v1 & v2  
   transform ( v1.begin( ),  v1.end( ), v2.begin( ), v3.begin ( ),   
      average<double>( ) );  
  
   cout << "The element-wise averages are: ( " ;  
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )  
      cout << *Iter3 << " ";  
   cout << ")" << endl;  
}  
```  
  
  **Der Vektor v1 \= \(11 5.5 3.66667 2.75 2.2 1.83333\)**  
**Der Vektor v2 \= \(\-0 \-2 \-4 \-6 \-8 \-10\)**  
**Die elementweisen Durchschnitte sind: \(5,5 1,75 \-0,166667 \-1,625 \-2,9 \-4,08333\)**   
## Anforderungen  
 **Header:** \<functional\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [binary\_function\-Strukturbeispiel](../misc/binary-function-structure-sample.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)