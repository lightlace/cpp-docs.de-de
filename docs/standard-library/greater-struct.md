---
title: "greater-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "greater"
  - "xfunctional/std::greater"
  - "std.greater"
  - "std::greater"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "greater-Struktur"
  - "greater-Funktion"
ms.assetid: ebc348e1-edcd-466b-b21a-db95bd8f9079
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# greater-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein binäres Prädikat, mit dem der größer\-als\-Vorgang \(`operator>`\) auf den Argumenten ausgeführt wird.  
  
## Syntax  
  
```  
template<class Type = void>  
   struct greater : public binary_function <Type, Type, bool>   
   {  
      bool operator()(  
         const Type& Left,   
         const Type& Right  
      ) const;  
   };  
  
// specialized transparent functor for operator>  
template<>  
   struct greater<void>  
   {  
      template<class Type1, class Type2>  
      auto operator()(Type1&& Left, Type2&& Right) const  
      -> decltype(std::forward<Type1>(Left)  
         > std::forward<Type2>(Right));  
   };  
  
```  
  
#### Parameter  
 `Type`, `Type1`, `Type2`  
 Jeder Typ, der ein `operator>`\-Element unterstützt, das Operanden angegebener oder abgeleiteter Typen akzeptiert.  
  
 `Left`  
 Der linke Operand des größer\-als\-Vorgangs.  Die nicht spezialisierte Vorlage besitzt ein lvalue\-Verweisargument vom Typ `Type`.  Die spezialisierte Vorlage vervollkommnet die Weiterleitung von lvalue und rvalue\-Verweisargumenten des abgeleiteten Typs `Type1`.  
  
 `Right`  
 Der rechte Operand des größer\-als\-Vorgangs.  Die nicht spezialisierte Vorlage besitzt ein lvalue\-Verweisargument vom Typ `Type`.  Die spezialisierte Vorlage vervollkommnet die Weiterleitung von lvalue und rvalue\-Verweisargumenten des abgeleiteten Typs `Type2`.  
  
## Rückgabewert  
 Das Ergebnis von `Left` `>` `Right`.  Die spezialisierte Vorlage vervollkommnet die Weiterleitung des Ergebnisses mit dem von `operator>` zurückgegebenen Typs.  
  
## Hinweise  
 Das binäre `greater`\<`Type`\>\-Prädikat stellt eine strenge schwache Sortierung eines Satzes von Elementwerten vom Typ `Type` in Äquivalenzklassen bereit, wenn und nur wenn dieser Typ den mathematischen Standardanforderungen für eine solche Sortierung entspricht.  Die Spezialisierungen für einen Zeigertyp ergeben eine gesamte Sortierung von Elementen, insofern, dass alle Elemente unterschiedlicher Werte zueinander in Beziehung stehend sortiert werden.  
  
## Beispiel  
  
```  
// functional_greater.cpp  
// compile with: /EHsc  
#include <vector>  
#include <algorithm>  
#include <functional>  
#include <cstdlib>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector <int> v1;  
   vector <int>::iterator Iter1;  
  
   int i;  
   for ( i = 0 ; i < 8 ; i++ )  
   {  
      v1.push_back( rand( ) );  
   }  
  
   cout << "Original vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   // To sort in ascending order,  
   // use default binary predicate less<int>( )  
   sort( v1.begin( ), v1.end( ) );  
   cout << "Sorted vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   // To sort in descending order,   
   // specify binary predicate greater<int>( )  
   sort( v1.begin( ), v1.end( ), greater<int>( ) );  
   cout << "Resorted vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
}  
```  
  
## Ausgabe  
  
```  
Original vector v1 = ( 41 18467 6334 26500 19169 15724 11478 29358 )  
Sorted vector v1 = ( 41 6334 11478 15724 18467 19169 26500 29358 )  
Resorted vector v1 = ( 29358 26500 19169 18467 15724 11478 6334 41 )  
```  
  
## Anforderungen  
 **Header:** \<functional\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Standard Template Library](../misc/standard-template-library.md)