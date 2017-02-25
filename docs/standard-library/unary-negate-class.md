---
title: "unary_negate-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "unary_negate"
  - "std::unary_negate"
  - "std.unary_negate"
  - "xfunctional/std::unary_negate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unary_negate-Klasse"
ms.assetid: e3b86eec-3205-49b9-ab83-f55225af4e0c
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# unary_negate-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Klasse, mit der eine Memberfunktion bereitgestellt wird, die den Rückgabewert einer angegebenen unären Funktion negiert.  
  
## Syntax  
  
```  
  
   template<class Predicate>  
class unary_negate  
   : public unary_function<  
      typename Predicate::argument_type,  
      bool>   
{  
public:  
explicit unary_negate(  
   const Predicate& _Func  
);  
bool operator()(  
   const typename Predicate::argument_type& _Left ) const;  
};  
```  
  
#### Parameter  
 `_Func`  
 Der unäre negiert werden Funktion.  
  
 `_Left`  
 Der Operand der unären negiert werden Funktion.  
  
## Rückgabewert  
 Die der Negation unären Funktion.  
  
## Hinweise  
 Die Vorlagenklasse speichert eine Kopie eines \_Func des unären Funktionsobjekts *.*  Sie definiert die Memberfunktion `operator()` als Rückgabe von **\!**\_*Func\(\_Left\).*  
  
 Der Konstruktor des `unary_negate` wird selten direkt verwendet.  Die Hilfsfunktion [not1](../Topic/not1%20Function.md) bietet eine einfachere Möglichkeit, das **unary\_negator** Adapterprädikat zu deklarieren und zu verwenden.  
  
## Beispiel  
  
```  
// functional_unary_negate.cpp  
// compile with: /EHsc  
#include <vector>  
#include <functional>  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
  
int main()  
{  
    vector<int> v1;  
    vector<int>::iterator Iter;  
  
    int i;  
    for (i = 0; i <= 7; i++)  
    {  
        v1.push_back(5 * i);  
    }  
  
    cout << "The vector v1 = ( ";  
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)  
        cout << *Iter << " ";  
    cout << ")" << endl;  
  
    vector<int>::iterator::difference_type result1;  
    // Count the elements greater than 10  
    result1 = count_if(v1.begin(), v1.end(), bind2nd(greater<int>(), 10));  
    cout << "The number of elements in v1 greater than 10 is: "  
         << result1 << "." << endl;  
  
    vector<int>::iterator::difference_type result2;  
    // Use the negator to count the elements less than or equal to 10  
    result2 = count_if(v1.begin(), v1.end(),  
        unary_negate<binder2nd <greater<int> > >(bind2nd(greater<int>(),10)));  
  
    // The following helper function not1 also works for the above line  
    // not1(bind2nd(greater<int>(), 10)));  
  
    cout << "The number of elements in v1 not greater than 10 is: "  
         << result2 << "." << endl;  
}  
```  
  
  **Der Vektor v1 \= \(0 5 10 15 20 25 30 35\)**  
**Die Anzahl der Elemente in v1, das größer 10 ist, ist: 5.**  
**Die Anzahl der Elemente in v1, das als 10 nicht größer ist, ist: 3.**   
## Anforderungen  
 **Header:** \<functional\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)