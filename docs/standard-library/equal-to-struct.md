---
title: "equal_to-Struktur"
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
  - "std::equal_to"
  - "equal_to"
  - "xfunctional/std::equal_to"
  - "std.equal_to"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "equal_to-Funktion"
  - "equal_to-Struktur"
ms.assetid: 8e4f2b50-b2db-48e3-b4cc-6cc03362c2a6
caps.latest.revision: 17
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# equal_to-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein binäres Prädikat, mit dem der Gleichheitsvorgang \(`operator==`\) auf den Argumenten ausgeführt wird.  
  
## Syntax  
  
```  
template<class Type = void>  
   struct equal_to : public binary_function<Type, Type, bool>   
   {  
      bool operator()(  
         const Type& Left,   
         const Type& Right  
      ) const;  
   };  
  
// specialized transparent functor for operator==  
template<>  
   struct equal_to<void>  
   {  
      template<class Type1, class Type2>  
      auto operator()(Type1&& Left, Type2&& Right) const  
         -> decltype(std::forward<Type1>(Left)  
            == std::forward<Type2>(Right));  
   };  
  
```  
  
#### Parameter  
 `Type`, `Type1`, `Type2`  
 Jeder Typ, der ein `operator==`\-Element unterstützt, das Operanden angegebener oder abgeleiteter Typen akzeptiert.  
  
 `Left`  
 Der linke Operand des Gleichheitsvorgangs.  Die nicht spezialisierte Vorlage besitzt ein lvalue\-Verweisargument vom Typ `Type`.  Die spezialisierte Vorlage vervollkommnet die Weiterleitung von lvalue und rvalue\-Verweisargumenten des abgeleiteten Typs `Type1`.  
  
 `Right`  
 Der rechte Operand des Gleichheitsvorgangs.  Die nicht spezialisierte Vorlage besitzt ein lvalue\-Verweisargument vom Typ `Type`.  Die spezialisierte Vorlage vervollkommnet die Weiterleitung von lvalue und rvalue\-Verweisargumenten des abgeleiteten Typs `Type2`.  
  
## Rückgabewert  
 Das Ergebnis von `Left` `==` `Right`.  Die spezialisierte Vorlage vervollkommnet die Weiterleitung des Ergebnisses mit dem von `operator==` zurückgegebenen Typs.  
  
## Hinweise  
 Die Objekte vom Typ `Type` müssen auf Gleichheit vergleichbar sein.  Das erfordert, dass das mit dem `operator==`\-Element, das im Satz von Objekten definiert wird, die Eigenschaften einer mathematischen Äquivalenzrelation erfüllt werden.  Alle integrierten numerischen Typen und Zeigertypen erfüllen diese Anforderung.  
  
## Beispiel  
  
```  
// functional_equal_to.cpp  
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
   for ( i = 0 ; i <= 5 ; i+=2 )  
   {  
      v1.push_back( 2.0 *i );  
      v1.push_back( 2.0 * i + 1.0 );  
   }  
  
   int j;  
   for ( j = 0 ; j <= 5 ; j+=2 )  
   {  
      v2.push_back( - 2.0 * j );  
      v2.push_back( 2.0 * j + 1.0 );  
   }  
  
   cout << "The vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   cout << "The vector v2 = ( " ;  
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )  
      cout << *Iter2 << " ";  
   cout << ")" << endl;  
  
   // Testing for the element-wise equality between v1 & v2  
   transform ( v1.begin( ),  v1.end( ), v2.begin( ), v3.begin ( ),   
      equal_to<double>( ) );  
  
   cout << "The result of the element-wise equal_to comparison\n"  
      << "between v1 & v2 is: ( " ;  
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )  
      cout << *Iter3 << " ";  
   cout << ")" << endl;  
}  
```  
  
  **Der Vektor v1 \= \(0 1 4 5 8 9\)**  
**Der Vektor v2 \= \(\-0 1 \-4 5 \-8 9\)**  
**Das Ergebnis des elementweisen equal\_to\-Vergleichs.**  
**zwischen v1 & v2 ist: \(1 1 0 1 0 1\)**