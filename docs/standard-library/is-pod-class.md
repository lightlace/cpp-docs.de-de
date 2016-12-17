---
title: "is_pod-Klasse"
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
  - "std.tr1.is_pod"
  - "is_pod"
  - "std::tr1::is_pod"
  - "std.is_pod"
  - "std::is_pod"
  - "type_traits/std::is_pod"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_pod-Klasse [TR1]"
  - "is_pod"
ms.assetid: d73ebdee-746b-4082-9fa4-2db71432eb0e
caps.latest.revision: 20
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# is_pod-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob der Typ POD ist.  
  
## Syntax  
  
```  
template<class Ty>  
    struct is_pod;  
```  
  
#### Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## Hinweise  
 `is_pod<Ty>::value` ist `true`, wenn der Typ `Ty` Plain Old Data \(POD\) ist.  Andernfalls ist der Wert `false`.  
  
 Arithmetische Typen, Enumerationstypen, Zeigertypen und Zeiger auf Membertypen sind POD.  
  
 Eine cv\-qualifizierte Version eines POD\-Typs ist selbst ein POD\-Typ.  
  
 Ein Array von POD ist selbst POD.  
  
 Eine Struktur oder Union, all deren nicht statische Datenmember POD sind, ist selbst POD, wenn sie Folgendes aufweist:  
  
-   Keine benutzerdeklarierten Konstruktoren  
  
-   Keine privaten oder geschützten nicht statischen Datenmember  
  
-   Keine Basisklassen  
  
-   Keine virtuellen Funktionen  
  
-   Keine nicht statischen Datenmember des Verweistyps  
  
-   Keinen benutzerdefinierten Kopierzuweisungsoperator  
  
-   Keinen benutzerdefinierten Destruktor  
  
 Aus diesem Grund können Sie rekursiv POD\-Strukturen und \-Arrays erstellen, die POD\-Strukturen und \-Arrays enthalten.  
  
## Beispiel  
  
```  
// std_tr1__type_traits__is_pod.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
struct throws   
    {   
    throws() throw(int)   
        {   
        }   
  
    throws(const throws&) throw(int)   
        {   
        }   
  
    throws& operator=(const throws&) throw(int)   
        {   
        }   
  
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_pod<trivial> == " << std::boolalpha   
        << std::is_pod<trivial>::value << std::endl;   
    std::cout << "is_pod<int> == " << std::boolalpha   
        << std::is_pod<int>::value << std::endl;   
    std::cout << "is_pod<throws> == " << std::boolalpha   
        << std::is_pod<throws>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_pod\<trivial\> \=\= true**  
**is\_pod\<int\> \=\= true**  
**is\_pod\<throws\> \=\= false**   
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)