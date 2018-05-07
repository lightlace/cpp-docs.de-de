---
title: Compilerfehler C3240 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3240
dev_langs:
- C++
helpviewer_keywords:
- C3240
ms.assetid: 1a8dc213-b80c-47ae-ada0-e9554b635d1e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f092843b42cc64f694315da349eb7fb66ca5dbf4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3240"></a>Compilerfehler C3240
'Funktion': muss eine Funktion abstrakten Member nicht überladen von "Type" sein  
  
 Ein Basistyp enthielt eine Funktion, die definiert wurde. Funktion muss virtuell sein.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3240 generiert.  
  
```  
// C3240.cpp  
// compile with: /c  
__interface I {  
   void f();  
};  
  
struct A1 : I {   
   void f() {}  
};  
  
struct A2 : I {   
   void f() = 0;  
};  
  
template <class T>   
struct A3 : T {  
   void T::f() {}  
};  
  
template <class T>   
struct A4 : T {  
   void T::f() {}  
};  
  
A3<A1> x;   // C3240  
A3<I> x2;  
A4<A2> x3;  
```