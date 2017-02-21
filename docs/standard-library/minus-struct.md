---
title: "minus-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "minus"
  - "std.minus"
  - "std::minus"
  - "xfunctional/std::minus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "minus-Struktur"
  - "minus-Klasse"
ms.assetid: 7bce784e-2be6-413a-b516-004e9ecb2a39
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# minus-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein vordefiniertes Funktionsobjekt, mit dem der Subtraktionsvorgang \(binäres `operator-`\) auf den Argumenten ausführt wird.  
  
## Syntax  
  
```  
template<class Type = void>  
   struct minus : public binary_function <Type, Type, Type>   
   {  
      Type operator()(  
         const Type& Left,   
         const Type& Right  
      ) const;  
   };  
  
// specialized transparent functor for operator-  
template<>  
   struct minus<void>  
   {  
      template<class Type1, class Type2>  
      auto operator()(Type1&& Left, Type2&& Right) const  
         -> decltype(std::forward<Type1>(Left)  
            - std::forward<Type2>(Right));  
   };  
  
```  
  
#### Parameter  
 `Type`, `Type1`, `Type2`  
 Ein Typ, der ein binäres `operator-`\-Element unterstützt, das Operanden angegebener oder abgeleiteter Typen akzeptiert.  
  
 `Left`  
 Der linke Operand des Vorgangs.  Die nicht spezialisierte Vorlage besitzt ein lvalue\-Verweisargument vom Typ `Type`.  Die spezialisierte Vorlage vervollkommnet die Weiterleitung von lvalue und rvalue\-Verweisargumenten des abgeleiteten Typs `Type1`.  
  
 `Right`  
 Der rechte Operand des Vorgangs.  Die nicht spezialisierte Vorlage besitzt ein lvalue\-Verweisargument vom Typ `Type`.  Die spezialisierte Vorlage vervollkommnet die Weiterleitung von lvalue und rvalue\-Verweisargumenten des abgeleiteten Typs `Type2`.  
  
## Rückgabewert  
 Das Ergebnis von `Left` `-` `Right`.  Die spezialisierte Vorlage vervollkommnet die Weiterleitung des Ergebnisses mit dem von `operator-` zurückgegebenen Typs.  
  
## Beispiel  
  
```  
// functional_minus.cpp  
// compile with: /EHsc  
#include <vector>  
#include <functional>  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
   vector <int> v1, v2, v3 ( 6 );  
   vector <int>::iterator Iter1, Iter2, Iter3;  
  
   int i;  
   for ( i = 0 ; i <= 5 ; i++ )  
   {  
      v1.push_back( 4 * i + 1);  
   }  
  
   int j;  
   for ( j = 0 ; j <= 5 ; j++ )  
   {  
      v2.push_back( 3 * j - 1);  
   }  
  
   cout << "The vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   cout << "The vector v2 = ( " ;  
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )  
      cout << *Iter2 << " ";  
   cout << ")" << endl;  
  
   // Finding the element-wise diference of the elements of v1 & v2  
   transform ( v1.begin( ),  v1.end( ), v2.begin( ), v3.begin ( ),   
      minus<int>( ) );  
  
   cout << "The element-wise differences between v1 and v2 are: ( " ;  
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )  
      cout << *Iter3 << " ";  
   cout << ")" << endl;  
}  
```  
  
  **Der Vektor v1 \= \(1 5 9 13 17 21\)**  
**Der Vektor v2 \= \(\-1 2 5 8 11 14\)**  
**Die elementweisen Unterschiede zwischen v1 und v2 sind: \(2 3 4 5 6 7\)**   
## Anforderungen  
 **Header:** \<functional\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)