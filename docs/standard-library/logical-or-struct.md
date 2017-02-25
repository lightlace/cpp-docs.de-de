---
title: "logical_or-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.logical_or"
  - "std::logical_or"
  - "logical_or"
  - "xfunctional/std::logical_or"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "logical_or-Klasse"
  - "logical_or-Struktur"
ms.assetid: ec8143f8-5755-4e7b-8025-507fb6bf6911
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# logical_or-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein vordefiniertes Funktionsobjekt, mit dem der logische Disjunktionsvorgang \(`operator||`\) auf die Argumente ausgeführt werden kann.  
  
## Syntax  
  
```  
template<class Type = void>  
   struct logical_or : public binary_function<Type, Type, bool>   
   {  
      bool operator()(  
         const Type& Left,   
         const Type& Right  
      ) const;  
   };  
  
// specialized transparent functor for operator||  
template<>  
   struct logical_or<void>  
   {  
      template<class Type1, class Type2>  
      auto operator()(Type1&& Left, Type2&& Right) const  
         -> decltype(std::forward<Type1>(Left)  
            || std::forward<Type2>(Right));  
   };  
  
```  
  
#### Parameter  
 `Type`, `Type1`, `Type2`  
 Jeder Typ, der ein `operator||`\-Element unterstützt, das Operanden angegebener oder abgeleiteter Typen akzeptiert.  
  
 `Left`  
 Der linke Operand des logischen Disjunktionsvorgangs.  Die nicht spezialisierte Vorlage besitzt ein lvalue\-Verweisargument vom Typ `Type`.  Die spezialisierte Vorlage vervollkommnet die Weiterleitung von lvalue und rvalue\-Verweisargumenten des abgeleiteten Typs `Type1`.  
  
 `Right`  
 Der rechte Operand des logischen Disjunktionsvorgangs.  Die nicht spezialisierte Vorlage besitzt ein lvalue\-Verweisargument vom Typ `Type`.  Die spezialisierte Vorlage vervollkommnet die Weiterleitung von lvalue und rvalue\-Verweisargumenten des abgeleiteten Typs `Type2`.  
  
## Rückgabewert  
 Das Ergebnis von `Left` `||` `Right`.  Die spezialisierte Vorlage vervollkommnet die Weiterleitung des Ergebnisses mit dem von `operator||` zurückgegebenen Typs.  
  
## Hinweise  
 Bei benutzerdefinierten Typen gibt es keine verkürzte Operandenauswertung.  Beide Argumente werden von `operator||` ausgewertet.  
  
## Beispiel  
  
```  
// functional_logical_or.cpp  
// compile with: /EHsc  
#include <deque>  
#include <algorithm>  
#include <functional>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   deque <bool> d1, d2, d3( 7 );  
   deque <bool>::iterator iter1, iter2, iter3;  
  
   int i;  
   for ( i = 0 ; i < 7 ; i++ )  
   {  
      d1.push_back((bool)((rand() % 2) != 0));  
   }  
  
   int j;  
   for ( j = 0 ; j < 7 ; j++ )  
   {  
      d2.push_back((bool)((rand() % 2) != 0));  
   }  
  
   cout << boolalpha;    // boolalpha I/O flag on  
  
   cout << "Original deque:\n d1 = ( " ;  
   for ( iter1 = d1.begin( ) ; iter1 != d1.end( ) ; iter1++ )  
      cout << *iter1 << " ";  
   cout << ")" << endl;  
  
   cout << "Original deque:\n d2 = ( " ;  
   for ( iter2 = d2.begin( ) ; iter2 != d2.end( ) ; iter2++ )  
      cout << *iter2 << " ";  
   cout << ")" << endl;  
  
   // To find element-wise disjunction of the truth values  
   // of d1 & d2, use the logical_or function object  
   transform( d1.begin( ), d1.end( ), d2.begin( ),  
      d3.begin( ), logical_or<bool>( ) );  
   cout << "The deque which is the disjuction of d1 & d2 is:\n d3 = ( " ;  
   for ( iter3 = d3.begin( ) ; iter3 != d3.end( ) ; iter3++ )  
      cout << *iter3 << " ";  
   cout << ")" << endl;  
}  
```  
  
  **Ursprüngliche Doppelschlange:**  
 **d1 \= \(true true false false true false false\)**  
**Ursprüngliche Doppelschlange:**  
 **d2 \= \(false false false true true true true\)**  
**Die Doppelschlange, die die Disjunktion von d1 & d2 ist:**  
 **d3 \= \(true und false true true true true\)**   
## Anforderungen  
 **Header:** \<functional\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)