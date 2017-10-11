---
title: Compilerfehler C3854 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3854
dev_langs:
- C++
helpviewer_keywords:
- C3854
ms.assetid: 32a9ead0-c6c7-485a-8802-c7b1fe921d3a
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 34285e8de195b2b7c516cf665f3b2cbf37039e6d
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3854"></a>Compilerfehler C3854
Ausdruck links von '=' wird als Funktion ausgewertet. Kann nicht an eine Funktion zuweisen (eine Funktion ist kein l-Wert)  
  
 Ein Verweis kann nicht erneut initialisiert werden. Dereferenziert einen Verweis auf eine Funktion ergibt eine Funktion, die ein Rvalue ist, den Sie zuweisen können. Aus diesem Grund nicht über einen Verweis auf eine Funktion zugewiesen.  
  
 Im folgende Beispiel wird C3854 generiert:  
  
```  
// C3854.cpp  
int afunc(int i)  
{  
   return i;  
}  
  
typedef int (& rFunc_t)(int);  
typedef int (* pFunc_t)(int);  
  
int main()  
{  
   rFunc_t rf = afunc;   // OK binding a reference to function  
   pFunc_t pf = &afunc;   // OK initializing a pointer to function  
  
   *pf = &afunc;   // C3854  
   // try the following line instead  
   // pf = &afunc;  
   *rf = &afunc;   // C3854  
}  
```
