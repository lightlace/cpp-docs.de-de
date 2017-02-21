---
title: "negate-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "negate"
  - "std.negate"
  - "std::negate"
  - "xfunctional/std::negate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "negate-Struktur"
  - "negate-Klasse"
ms.assetid: 8a372686-786e-4262-b37c-ca13dc11e62f
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# negate-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein vordefiniertes Funktionsobjekt, mit dem der arithmetische Negationsvorgang \(unäres `operator-`\-Element\) auf dem Argument ausgeführt wird.  
  
## Syntax  
  
```  
template<class Type = void>  
   struct negate : public unary_function<Type, Type>   
   {  
      Type operator()(  
         const Type& Left  
      ) const;  
   };  
  
// specialized transparent functor for unary operator-  
template<>  
   struct negate<void>  
   {  
      template<class Type>  
      auto operator()(Type&& Left) const  
         -> decltype(-std::forward<Type>(Left));  
   };  
  
```  
  
#### Parameter  
 `Type`  
 Jeder Typ, der ein `operator-`\-Element unterstützt, das einen Operanden des angegebenen oder abgeleiteten Typs akzeptiert.  
  
 `Left`  
 Der zu negierende Operand.  Die spezialisierte Vorlage vervollkommnet die Weiterleitung von lvalue und rvalue\-Verweisargumenten des abgeleiteten Typs `Type`.  
  
## Rückgabewert  
 Das Ergebnis von `-``Left.`. Mit der spezialisierten Vorlage wird eine perfekte Weiterleitung des Ergebnisses ausgeführt, das den Typ aufweist, der vom unären `operator-` zurückgegeben wird.  
  
## Beispiel  
  
```  
// functional_negate.cpp  
// compile with: /EHsc  
#include <vector>  
#include <functional>  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
   vector <int> v1, v2 ( 8 );  
   vector <int>::iterator Iter1, Iter2;  
  
   int i;  
   for ( i = -2 ; i <= 5 ; i++ )  
   {  
      v1.push_back( 5 * i );  
   }  
  
   cout << "The vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   // Finding the element-wise negatives of the vector v1  
   transform ( v1.begin( ),  v1.end( ), v2.begin( ), negate<int>( ) );  
  
   cout << "The negated elements of the vector = ( " ;  
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )  
      cout << *Iter2 << " ";  
   cout << ")" << endl;  
}  
```  
  
  **Der Vektor v1 \= \(\-10 \-5 0 5 10 15 20 25\)**  
**Die negierten Elemente des Vektors \(\= 10 5 0 \-5 \-10 \-15 \-20 \-25\)**   
## Anforderungen  
 **Header:** \<functional\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)