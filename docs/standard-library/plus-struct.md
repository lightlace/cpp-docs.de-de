---
title: "plus-Struktur"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "xfunctional/std::plus"
  - "std.plus"
  - "plus"
  - "std::plus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "plus-Klasse"
  - "plus-Struktur"
ms.assetid: 4594abd5-b2f2-4fac-9b6b-fc9a2723f8cf
caps.latest.revision: 20
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# plus-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein vordefiniertes Funktionsobjekt, mit dem der Additionsvorgang \(binäres `operator+`\) auf den Argumenten ausführt wird.  
  
## Syntax  
  
```  
template<class Type = void>  
   struct plus : public binary_function <Type, Type, Type>   
   {  
      Type operator()(  
         const Type& Left,   
         const Type& Right  
      ) const;  
   };  
  
// specialized transparent functor for operator+  
template<> struct plus<void>  
   {  
   template<class Type1, class Type2>  
      auto operator()(Type1&& Left, Type2&& Right) const  
      -> decltype(std::forward<Type1>(Left)  
         + std::forward<Type2>(Right));  
   };  
  
```  
  
#### Parameter  
 `Type`, `Type1`, `Type2`  
 Ein Typ, der ein binäres `operator+`\-Element unterstützt, das Operanden angegebener oder abgeleiteter Typen akzeptiert.  
  
 `Left`  
 Der linke Operand des Additionsvorgangs.  Die nicht spezialisierte Vorlage besitzt ein lvalue\-Verweisargument vom Typ `Type`.  Die spezialisierte Vorlage vervollkommnet die Weiterleitung von lvalue und rvalue\-Verweisargumenten des abgeleiteten Typs `Type1`.  
  
 `Right`  
 Der rechte Operand des Additionsvorgangs.  Die nicht spezialisierte Vorlage besitzt ein lvalue\-Verweisargument vom Typ `Type`.  Die spezialisierte Vorlage vervollkommnet die Weiterleitung von lvalue und rvalue\-Verweisargumenten des abgeleiteten Typs `Type2`.  
  
## Rückgabewert  
 Das Ergebnis von `Left` `+` `Right`.  Die spezialisierte Vorlage vervollkommnet die Weiterleitung des Ergebnisses mit dem vom binären `operator+`\-Element zurückgegebenen Typs.  
  
## Beispiel  
  
```  
// functional_plus.cpp  
// compile with: /EHsc  
#include <vector>  
#include <functional>  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
   vector <double> v1, v2, v3 ( 6 );  
   vector <double>::iterator Iter1, Iter2, Iter3;  
  
   int i;  
   for ( i = 0 ; i <= 5 ; i++ )  
      v1.push_back( 4 * i );  
  
   int j;  
   for ( j = 0 ; j <= 5 ; j++ )  
      v2.push_back( -2.0 * j - 4 );  
  
   cout << "The vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   cout << "The vector v2 = ( " ;  
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )  
      cout << *Iter2 << " ";  
   cout << ")" << endl;  
  
   // Finding the element-wise sums of the elements of v1 & v2  
   transform (v1.begin( ), v1.end( ), v2.begin( ), v3.begin ( ), plus<double>( ) );  
  
   cout << "The element-wise sums are: ( " ;  
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )  
      cout << *Iter3 << " ";  
   cout << ")" << endl;  
}  
```  
  
  **Der Vektor v1 \= \(0 4 8 12 16 20\)**  
**Der Vektor v2 \= \(\-4 \-6 \-8 \-10 \-12 \-14\)**  
**Die elementweisen Summen sind: \(\-4 \-2 0 2 4 6\)**   
## Anforderungen  
 **Header:** \<functional\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)