---
title: "result_of-Klasse"
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
  - "functional/std::tr1::result_of"
  - "std::tr1::result_of"
  - "result_of"
  - "std.tr1.result_of"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "result_of-Klasse [TR1]"
ms.assetid: 14ec0040-07f1-45a5-80b5-d0c9f9b00c8f
caps.latest.revision: 20
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# result_of-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Rückgabetyp eines umschlossenen aufrufbaren Objekts.  
  
## Syntax  
  
```  
template<class Ty>  
    struct result_of {  
    typedef T0 type;  
    };  
```  
  
#### Parameter  
 `Ty`  
 Eine Beschreibung eines Funktionsaufrufs \(siehe Abschnitt Hinweise\).  
  
## Hinweise  
 Die Vorlagenklasse definiert seinen Member `type` als Synonym für den Rückgabetyp eines Funktionsaufrufs, der durch das Vorlagenargument `Ty` beschrieben wird.  Das Vorlagenargument muss im Format `Fty(T1, T2, ..., TN)` sein, wobei `Fty` ein aufrufbarer Typ ist.  Die Vorlage bestimmt den Rückgabetyp anhand des ersten der folgenden Regeln, die gilt:  
  
-   wenn `Fty` ein Zeiger ist, zu arbeiten Typ, `R(*)(U1, U2, ..., UN)`, ist der Rückgabetyp `R`;  
  
-   `Fty` wenn ein Verweis auf Funktionstyp `R(&)(U1, U2, ..., UN)` ist, ist der Rückgabetyp `R`;  
  
-   wenn `Fty` ein Zeiger auf Memberfunktionstyp `R(U1::*)(U2, ..., UN)` ist, ist der Rückgabetyp `R`;  
  
-   wenn `Fty` ein Zeiger auf Datenmembertyp `R U1::*` ist, ist der Rückgabetyp `R`;  
  
-   wenn `Fty` eine Klasse mit einer Member\-typedef `result_type` ist, ist der Rückgabetyp `Fty::result_type`;  
  
-   wenn `N` 0 ist, \(das heißt, `Ty` die Form `Fty()`\), das der Rückgabetyp ist `void`;  
  
-   wenn `Fty` eine Klasse mit einer Membervorlage ist, die `result` genannt wird, ist der Rückgabetyp `Fty::result<T1, T2, ..., TN>::type`;  
  
-   in allen anderen Fällen ist dies ein Fehler.  
  
## Beispiel  
  
```  
// std_tr1__functional__result_of.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
double square(double x)   
    {   
    return (x * x);   
    }   
  
template<class Fun,   
    class Arg>   
    void test_result(const Fun& fun, Arg arg)   
    {   
    typename std::result_of<Fun(Arg)>::type val = fun(arg);   
    std::cout << "val == " << val << std::endl;   
    }   
  
int main()   
    {   
    test_result(&square, 3.0);   
  
    return (0);   
    }  
  
```  
  
  **val \=\= 9**   
## Anforderungen  
 **Header:** \<functional\>  
  
 **Namespace:** std