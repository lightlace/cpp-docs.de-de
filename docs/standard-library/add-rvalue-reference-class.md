---
title: "add_rvalue_reference-Klasse"
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
  - "type_traits/std::add_rvalue_reference"
  - "std::add_rvalue_reference"
  - "add_rvalue_reference"
  - "std.add_rvalue_reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "add_rvalue_reference-Klasse"
ms.assetid: 76b0cb7c-1031-45d0-b409-f03ab0297580
caps.latest.revision: 11
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# add_rvalue_reference-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt einen Rvalue\-Verweistyp des Vorlagenparameters, wenn sie ein Objekt oder eine Funktion ist. Andernfalls entspricht die Semantik von Verweisen reduzieren, der Typ der Vorlagenparameter.  
  
## Syntax  
  
```cpp  
template<class T>  
    struct add_rvalue_reference;  
  
template<class T>  
    using add_rvalue_reference_t = typename add_rvalue_reference<T>::type;  
```  
  
#### Parameter  
 T  
 Der zu ändernde Typ.  
  
## Hinweise  
 Die `add_rvalue_reference` \-Klasse verfügt über einen Member mit dem Namen `type`, dies ist ein Alias für den Typ des einen Rvalue\-Verweis mit dem Vorlagenparameter `T`. Die Semantik von Verweisen reduzieren bedeutet, dass für nicht\-Objekt und nicht\-Funktion `T`, `T&&` ist eine `T`. Zum Beispiel, wenn `T` ist ein Lvalue\-Verweistyp  `add_rvalue_reference<T>::type` Lvalue\-Verweistyp, nicht auf einen Rvalue\-Verweis ist.  
  
 Der Einfachheit halber \< Type\_traits \> definiert eine Vorlage für die Hilfsfunktion `add_rvalue_reference_t`, die Aliase der `type` Mitglied `add_rvalue_reference`.  
  
## Beispiel  
 Dieses Codebeispiel Static\_assert verwendet, um anzuzeigen, wie Rvalue\-Verweis\-Typen erstellt werden `add_rvalue_reference` und `add_rvalue_reference_t`, und wie das Ergebnis des `add_rvalue_reference` auf einen Lvalue\-Verweis ist ein Rvalue\-Verweis, jedoch in den Referenztyp Lvalue reduziert.  
  
```cpp  
// ex_add_rvalue_reference.cpp  
// Build by using: cl /EHsc /W4 ex_add_rvalue_reference.cpp  
#include <type_traits>   
#include <iostream>   
#include <string>  
  
using namespace std;  
int main()  
{  
    static_assert(is_same<add_rvalue_reference<string>::type, string&&>::value,   
        "Expected add_rvalue_reference_t<string> to be string&&");  
    static_assert(is_same<add_rvalue_reference_t<string*>, string*&&>::value,   
        "Expected add_rvalue_reference_t<string*> to be string*&&");  
    static_assert(is_same<add_rvalue_reference<string&>::type, string&>::value,   
        "Expected add_rvalue_reference_t<string&> to be string&");  
    static_assert(is_same<add_rvalue_reference_t<string&&>, string&&>::value,   
        "Expected add_rvalue_reference_t<string&&> to be string&&");  
    cout << "All static_assert tests of add_rvalue_reference passed." << endl;  
    return 0;  
}  
  
/*Output:  
All static_assert tests of add_rvalue_reference passed.  
*/  
```  
  
## Anforderungen  
 Header: \<type\_traits\> Namespace: std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [add\_lvalue\_reference\-Klasse](../standard-library/add-lvalue-reference-class.md)   
 [is\_rvalue\_reference\-Klasse](../standard-library/is-rvalue-reference-class.md)