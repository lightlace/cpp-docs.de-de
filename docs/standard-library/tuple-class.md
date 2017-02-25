---
title: "tuple-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tr1::tuple"
  - "std.tr1.tuple"
  - "tuple"
  - "tr1.tuple"
  - "std::tr1::tuple"
  - "tuple/std::tr1::tuple"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tuple-Klasse"
  - "tuple-Klasse [TR1]"
ms.assetid: c38749be-ae4d-41f3-98ea-6aa3250de9a3
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# tuple-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Umschließt eine Sequenz von Elementen mit fester Länge ein.  
  
## Syntax  
  
```  
template<class T1, class T2, ..., class TN>  
class tuple {  
public:  
    tuple();  
    explicit tuple(P1, P2, ..., PN);              // 0 < N  
    tuple(const tuple&);  
    template <class U1, class U2, ..., class UN>  
        tuple(const tuple<U1, U2, ..., UN>&);  
    template <class U1, class U2>  
        tuple(const pair<U1, U2>&);               // N == 2  
    void swap(tuple& right);  
    tuple& operator=(const tuple&);  
    template <class U1, class U2, ..., class UN>  
        tuple& operator=(const tuple<U1, U2, ..., UN>&);  
    template <class U1, class U2>  
        tuple& operator=(const pair<U1, U2>&);    // N == 2  
    };  
```  
  
#### Parameter  
 `TN`  
 Der Typ des N\-ten Tupelelements.  
  
## Hinweise  
 Die Vorlagenklasse beschreibt ein Objekt, das N\-Objekte der Typen `T1`, `T2` speichert,..., `TN` bzw. wo wo `0 <= N <= Nmax`.  Der Umfang der Tupelinstanz `tuple<T1, T2, ..., TN>` entspricht der Anzahl `N` seiner Vorlagenargumenten.  Der Index des Vorlagenarguments `Ti` und des entsprechenden gespeicherten Werts dieses Typs lautet `i - 1`.  Somit während die Typen von 1 bis n in dieser Dokumentation, Zahlen\- der entsprechende Indexwertbereich von 0 bis n. \- 1.  
  
## Beispiel  
  
```  
// tuple.cpp  
// compile with: /EHsc  
  
#include <vector>  
#include <iomanip>  
#include <iostream>  
#include <tuple>  
#include <string>  
  
using namespace std;  
  
typedef tuple <int, double, string> ids;  
  
void print_ids(const ids& i)  
{  
   cout << "( "  
        << get<0>(i) << ", "   
        << get<1>(i) << ", "   
        << get<2>(i) << " )." << endl;  
}  
  
int main( )  
{  
   // Using the constructor to declare and initialize a tuple  
   ids p1(10, 1.1e-2, "one");  
  
   // Compare using the helper function to declare and initialize a tuple  
   ids p2;  
   p2 = make_tuple(10, 2.22e-1, "two");  
  
   // Making a copy of a tuple  
   ids p3(p1);  
  
   cout.precision(3);  
   cout << "The tuple p1 is: ( ";  
   print_ids(p1);  
   cout << "The tuple p2 is: ( ";  
   print_ids(p2);  
   cout << "The tuple p3 is: ( ";  
   print_ids(p3);  
  
   vector<ids> v;  
  
   v.push_back(p1);  
   v.push_back(p2);  
   v.push_back(make_tuple(3, 3.3e-2, "three"));  
  
   cout << "The tuples in the vector are" << endl;  
   for(vector<ids>::const_iterator i = v.begin(); i != v.end(); ++i)  
   {  
      print_ids(*i);  
   }  
}  
```  
  
  **Das Tupel p1 ist: \(10, 0,011, ein\).**  
**Das Tupel p2 ist: \(10, 0,222, zwei\).**  
**Das Tupel p3 ist: \(10, 0,011, ein\).**  
**Die Tupel im Vektor sind**  
**\(10, 0,011, ein\).**  
**\(10, 0,222, zwei\).**  
**\(3, 0,033, drei\).**   
## Anforderungen  
 Tupel **Header:** \<\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<tuple\>](../standard-library/tuple.md)   
 [make\_tuple\-Funktion](../Topic/make_tuple%20Function.md)