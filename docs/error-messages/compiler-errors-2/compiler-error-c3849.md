---
title: Compilerfehler C3849 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3849
dev_langs:
- C++
helpviewer_keywords:
- C3849
ms.assetid: 5347140e-1a81-4841-98c0-b63d98264b64
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7fbe46ee4f83dc5477eeb67e0debf14fe4f9fad5
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3849"></a>Compilerfehler C3849
Funktionstypen Aufruf ein Ausdruck vom Typ "Type" würden const "und/oder" volatile-Qualifizierer für alle Zahl verfügbaren operatorüberladungen verlieren.  
  
 Eine Variable mit einem angegebenen Const-Volatile-Typ kann Member nur mit dieselbe oder eine höhere Const-Volatile-Qualifikationen definierten Funktionen aufrufen.  
  
 Um diesen Fehler zu beheben, geben Sie eine entsprechenden Member-Funktion. Eine Konvertierung kann nicht auf ein Const oder volatile qualifiziertes Objekt ausgeführt werden, wenn die Konvertierung zu einer Qualifikation führt. Der Qualifizierer darf jedoch nicht Qualifizierer in einer Konvertierung.  
  
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
