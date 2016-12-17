---
title: "binary_negate-Klasse"
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
  - "xfunctional/std::binary_negate"
  - "std::binary_negate"
  - "binary_negate"
  - "std.binary_negate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "binary_negate-Klasse"
ms.assetid: 7b86f02c-af7e-4c7f-9df1-08addae4dd65
caps.latest.revision: 20
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# binary_negate-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Klasse, mit der eine Memberfunktion bereitgestellt wird, die den Rückgabewert einer angegebenen binären Funktion negiert.  
  
## Syntax  
  
```  
  
   template<class Operation>  
class binary_negate  
   : public binary_function <  
      typename Operation::first_argument_type,  
      typename Operation::second_argument_type,   
      bool>   
{  
public:  
explicit binary_negate(  
   const Operation& _Func  
);  
bool operator()(  
   const typename Operation::first_argument_type& _Left,  
   const typename Operation::second_argument_type& _Right  
) const;  
};  
```  
  
#### Parameter  
 `_Func`  
 Die binäre negiert werden Funktion.  
  
 `_Left`  
 Der linke Operand binärer negiert werden Funktion.  
  
 `_Right`  
 Der rechte Operand binärer negiert werden Funktion.  
  
## Rückgabewert  
 Die Negation binärer Funktion.  
  
## Hinweise  
 Die Vorlagenklasse speichert eine Kopie eines \_Func des binären Funktionsobjekts.  Sie definiert die Memberfunktion `operator()` als Rückgabe von **\!**\_*Func\(\_Left, \_Right\).*  
  
 Der Konstruktor des `binary_negate` wird selten direkt verwendet.  Die Hilfsfunktion [not2](../Topic/not2%20Function.md) wird normalerweise bevorzugt, um das **binary\_negator** Adapterprädikat zu deklarieren und zu verwenden.  
  
## Beispiel  
  
```  
// functional_binary_negate.cpp  
// compile with: /EHsc  
#define _CRT_RAND_S  
#include <stdlib.h>  
  
#include <vector>  
#include <algorithm>  
#include <functional>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector <unsigned int> v1;  
   vector <unsigned int>::iterator Iter1;  
  
   unsigned int i;  
   v1.push_back( 6262 );  
   v1.push_back( 6262 );  
   unsigned int randVal = 0;  
   for ( i = 0 ; i < 5 ; i++ )  
   {  
      rand_s(&randVal);  
      v1.push_back( randVal );  
   }  
  
   cout << "Original vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   // To sort in ascending order,  
   // use default binary predicate less<unsigned int>( )  
   sort( v1.begin( ), v1.end( ) );  
   cout << "Sorted vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   // To sort in descending order,  
   // use the binary_negate function  
   sort( v1.begin( ), v1.end( ),  
   binary_negate<less<unsigned int> >(less<unsigned int>( ) ) );  
  
   // The helper function not2 could also have been used  
   // in the above line and is usually preferred for convenience  
   // sort( v1.begin( ), v1.end( ), not2(less<unsigned int>( ) ) );  
  
   cout << "Resorted vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
}  
```  
  
  **Erster Vektor v1 \= \(6262 6262 2233879413 2621500314 580942933 3715465425 3739828298\)**  
**Sortierter Vektor v1 \= \(6262 6262 580942933 2233879413 2621500314 3715465425 3739828298\)**  
**Neu sortierter Vektor v1 \= \(3739828298 3715465425 2621500314 2233879413 580942933 6262 6262\)**   
## Anforderungen  
 **Header:** \<functional\>  
  
 std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)