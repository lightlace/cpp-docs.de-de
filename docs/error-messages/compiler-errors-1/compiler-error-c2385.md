---
title: "Compilerfehler C2385"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2385"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2385"
ms.assetid: 6d3dd1f2-e56d-49d7-865c-6a9acdb17417
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2385
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mehrdeutiger Zugriff von 'Member'  
  
 Der Member kann von mehr als einem Objekt ableiten \(es wird von mehr als einem Objekt geerbt\).  Um diesen Fehler zu beheben,  
  
-   Lösen Sie die Mehrdeutigkeit von Member durch eine Typumwandlung auf.  
  
-   Benennen Sie die mehrdeutigen Member in den Basisklassen um.  
  
## Beispiel  
 Im folgenden Beispiel wird C2385 generiert.  
  
```  
// C2385.cpp  
// C2385 expected  
#include <stdio.h>  
  
struct A   
{  
    void x(int i)   
    {  
        printf_s("\nIn A::x");  
    }  
};  
  
struct B   
{  
    void x(char c)   
    {  
        printf_s("\nIn B::x");  
    }  
};  
  
// Delete the following line to resolve.  
struct C : A, B {}  
  
// Uncomment the following 4 lines to resolve.  
// struct C : A, B   
// {  
//     using B::x;  
//     using A::x;  
// };  
  
int main()   
{  
    C aC;  
    aC.x(100);  
    aC.x('c');  
}  
  
struct C : A, B   
{  
    using B::x;  
    using A::x;  
};  
```