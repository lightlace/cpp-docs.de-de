---
title: "binder2nd-Klasse"
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
  - "std.binder2nd"
  - "binder2nd"
  - "xfunctional/std::binder2nd"
  - "std::binder2nd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "binder2nd-Klasse"
ms.assetid: b2a9c1d1-dfc4-4ca9-a10e-ae84e195a62d
caps.latest.revision: 22
caps.handback.revision: "16"
ms.author: "corob"
manager: "ghogen"
---
# binder2nd-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Vorlagenklasse, mit der ein Konstruktor bereitgestellt wird, der ein binäres Funktionsobjekt in ein unäres Funktionsobjekt konvertiert, indem das zweite Argument der binären Funktion an einen angegebenen Wert gebunden wird.  
  
## Syntax  
  
```  
template<class Operation>  
   class binder2nd  
      : public unary_function <  
         typename Operation::first_argument_type,  
         typename Operation::result_type>   
   {  
   public:  
   typedef typename Operation::argument_type argument_type;  
   typedef typename Operation::result_type result_type;  
   binder2nd(  
      const Operation& _Func,  
      const typename Operation::second_argument_type& _Right  
   );  
   result_type operator()(  
      const argument_type& _Left  
   ) const;  
   result_type operator()(  
      argument_type& _Left  
   ) const;  
   protected:  
   Operation op;  
   typename Operation::second_argument_type value;  
   };  
```  
  
#### Parameter  
 `_Func`  
 Das einem Funktionsobjekt unären zu konvertierende binäre Funktionsobjekt.  
  
 `_Right`  
 Der Wert, auf das das zweite Argument des binären Funktionsobjekts gebunden werden soll.  
  
 `_Left`  
 Der Wert des Arguments, das das benutzerdefinierte binären Objekt z festen Wert des zweiten Arguments vergleicht.  
  
## Rückgabewert  
 Das unäre Funktionsobjekt, das aus dem Binden des zweiten Arguments des binären Funktionsobjekts dem Wert `_Right.` entsteht  
  
## Hinweise  
 Die Vorlagenklasse speichert eine Kopie eines \_Func des binären Funktionsobjekts in **op** und eine Kopie von `_Right` in **Wert**.  Es definiert die Memberfunktion `operator()` als Rückgabe von `_Left`\( **op**, **Wert**\).  
  
 Wenn `_Func` ein Objekt des Typs **Vorgang** ist und c eine Konstante ist, wird [bind2nd](../Topic/bind2nd%20Function.md) \( `_Func`, `c` \) in `binder2nd``binder2nd`\<**Vorgang**\>\-Klassenkonstruktor \( `_Func`, `c` \) und bequemeres entsprechend.  
  
## Beispiel  
  
```  
// functional_binder2nd.cpp  
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
    for (i = 0; i <= 5; i++)  
    {  
        v1.push_back(5 * i);  
    }  
  
    cout << "The vector v1 = ( ";  
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)  
        cout << *Iter << " ";  
    cout << ")" << endl;  
  
    // Count the number of integers > 10 in the vector  
    vector<int>::iterator::difference_type result1;  
    result1 = count_if(v1.begin(), v1.end(),  
        binder2nd<greater<int> >(greater<int>(), 10));  
    cout << "The number of elements in v1 greater than 10 is: "  
         << result1 << "." << endl;  
  
    // Compare using binder1st fixing 1st argument:  
    // count the number of integers < 10 in the vector  
    vector<int>::iterator::difference_type result2;  
    result2 = count_if(v1.begin(), v1.end(),  
        binder1st<greater<int> >(greater<int>(), 10));  
    cout << "The number of elements in v1 less than 10 is: "  
         << result2 << "." << endl;  
}  
```  
  
  **Der Vektor v1 \= \(0 5 10 15 20 25\)**  
**Die Anzahl der Elemente in v1, das größer 10 ist, ist: 3.**  
**Die Anzahl der Elemente in v1 kleiner als 10 ist: 2.**   
## Anforderungen  
 **Header:** \<functional\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)