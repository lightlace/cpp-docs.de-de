---
title: "Compilerfehler C3849"
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
  - "C3849"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3849"
ms.assetid: 5347140e-1a81-4841-98c0-b63d98264b64
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3849
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

function\-style\-Aufruf an einen Ausdruck des Typs 'Typ' verliert möglicherweise die const\- und\/oder volatile\-Qualifizierer für alle 'Anzahl' verfügbaren Operatorüberladungen  
  
 Eine Variable mit einem festgelegten **const\-volatile**\-Typ kann nur Memberfunktionen aufrufen, die mit denselben oder höher wertigen **const\-volatile**\-Qualifizierungen definiert wurden.  
  
 Um diesen Fehler zu beheben, stellen Sie eine entsprechende Memberfunktion bereit.  Sie können keine Konvertierung für ein mit `const` oder `volatile` gekennzeichnetes Objekt ausführen, wenn die Konvertierung zu einer geringer wertigen Qualifizierung führt.  Die Anzahl der Qualifizierer darf sich durch eine Konvertierung erhöhen, jedoch nicht verringern.  
  
 In den folgenden Beispielen wird C3849 generiert:  
  
```  
// C3849.cpp  
void glbFunc3(int i, char c)  
{  
   i;  
}  
typedef void (* pFunc3)(int, char);  
  
void glbFunc2(int i)  
{  
   i;  
}  
  
typedef void (* pFunc2)(int);  
  
void glbFunc1()  
{  
}  
typedef void (* pFunc1)();  
  
struct S4  
{  
   operator ()(int i)  
   {  
      i;  
   }  
  
   operator pFunc1() const  
   {  
      return &glbFunc1;  
   }  
  
   operator pFunc2() volatile  
   {  
      return &glbFunc2;  
   }  
  
   operator pFunc3()  
   {  
      return &glbFunc3;  
   }  
  
   // operator pFunc1() const volatile  
   // {  
   //    return &glbFunc1;  
   // }  
};  
  
int main()  
{  
   // Cannot call any of the 4 overloads of "operator ()(.....)" and   
   // "operator pFunc()" because none is declared as "const volatile"  
   const volatile S4 s4;  // can only call cv member functions of S4  
   s4();   // C3849 to resolve, uncomment member function  
}  
```