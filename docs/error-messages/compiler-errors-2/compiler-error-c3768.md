---
title: Compilerfehler C3768 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3768
dev_langs:
- C++
helpviewer_keywords:
- C3768
ms.assetid: 091f0d53-1dff-43fd-813d-5c43c85b6ab0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3634ecf3eb1417095cce144706838113b5ad2a0e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3768"></a>Compilerfehler C3768
die Adresse einer virtuellen Vararg-Funktion in reinen verwalteten Code nicht akzeptiert werden.  
  
 Die **/CLR: pure** -Compileroption in Visual Studio 2015 als veraltet markiert ist.  
  
 Beim Kompilieren mit `/clr:pure`, können Sie nicht die Adresse einer virtuellen erhalten `vararg` Funktion.  
  
## <a name="example"></a>Beispiel  

 Im folgende Beispiel wird C3768 generiert:  
  
```  
// C3768.cpp  
// compile with: /clr:pure  
struct A  
{  
   virtual void f(...);  
};  
  
int main()  
{  
   &(A::f);   // C3768  
}  
```