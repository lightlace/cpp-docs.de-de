---
title: "binder1st-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xfunctional/std::binder1st"
  - "std::binder1st"
  - "binder1st"
  - "std.binder1st"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "binder1st-Klasse"
ms.assetid: 6b8ee343-c82f-48f8-867d-06f9d1d324c0
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# binder1st-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Vorlagenklasse, mit der ein Konstruktor bereitgestellt wird, der ein binäres Funktionsobjekt in ein unäres Funktionsobjekt konvertiert, indem das erste Argument der binären Funktion an einen angegebenen Wert gebunden wird.  
  
## Syntax  
  
```  
template<class Operation>  
class binder1st  
   : public unary_function <  
      typename Operation::second_argument_type,  
      typename Operation::result_type>   
  {  
   public:  
   typedef typename Operation::argument_type argument_type;  
   typedef typename Operation::result_type result_type;  
   binder1st(  
      const Operation & _Func,  
      const typename Operation::first_argument_type& _Left  
   );  
   result_type operator()(  
      const argument_type& _Right  
   ) const;  
   result_type operator()(  
      const argument_type& _Right  
   ) const;  
   protected:  
   Operation op;  
   typename Operation::first_argument_type value;  
   };  
```  
  
#### Parameter  
 `_Func`  
 Das einem Funktionsobjekt unären zu konvertierende binäre Funktionsobjekt.  
  
 `_Left`  
 Der Wert, auf das das erste Argument des binären Funktionsobjekts gebunden werden soll.  
  
 `_Right`  
 Der Wert des Arguments, das das benutzerdefinierte binären Objekt z festen Wert des zweiten Arguments vergleicht.  
  
## Rückgabewert  
 Das unäre Funktionsobjekt, das aus dem Binden des ersten Arguments des binären Funktionsobjekts dem Wert `_Left.` entsteht  
  
## Hinweise  
 Die Vorlagenklasse speichert eine Kopie eines binären Funktionsobjekts `_Func` in **op** und eine Kopie von `_Left` in **Wert**.  Es definiert die Memberfunktion `operator()` als Rückgabe von **op**\(**Wert**, `_Right`\).  
  
 Wenn `_Func` ein Objekt des Typs **Vorgang** aufweist und `c` eine Konstante ist, wird [bind1st](../Topic/bind1st%20Function.md) \( `_Func`, `c` \) in `binder1st``binder1st`\<**Vorgang**\>\-Klassenkonstruktor \( `_Func`, `c` \) und bequemeres entsprechend.  
  
## Beispiel  
  
```  
// functional_binder1st.cpp  
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
        binder1st<less<int> >(less<int>(), 10));  
    cout << "The number of elements in v1 greater than 10 is: "  
         << result1 << "." << endl;  
  
    // Compare use of binder2nd fixing 2nd argument:  
    // count the number of integers < 10 in the vector  
    vector<int>::iterator::difference_type result2;  
    result2 = count_if(v1.begin(), v1.end(),  
        binder2nd<less<int> >(less<int>(), 10));  
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