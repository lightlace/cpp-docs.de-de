---
title: Compilerfehler C2108 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2108
dev_langs:
- C++
helpviewer_keywords:
- C2108
ms.assetid: c84f0b47-5e2c-47d2-8edb-427a40e17c36
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 936c7f53ba112d2fc7bf03d76acac27bd8b4c372
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2108"></a>Compilerfehler C2108
Index ist kein Ganzzahltyp  
  
 Das Arrayindexfeld entspricht keinem ganzzahligen Ausdruck.  
  
## <a name="example"></a>Beispiel  
 C2108 kann auftreten, wenn Sie falsch verwenden, die `this` Zeiger, der einen Werttyp an Standardindexer des Typs zuzugreifen. Weitere Informationen finden Sie unter [Semantik dieses Zeigers](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer).  
  
 Im folgenden Beispiel wird C2108 generiert.  
  
```  
// C2108.cpp  
// compile with: /clr  
using namespace System;  
  
value struct B {  
   property Double default[Double] {  
      Double get(Double data) {  
         return data*data;  
      }  
   }  
   void Test() {  
      Console::WriteLine("{0}", this[3.3]);   // C2108  
      Console::WriteLine("{0}", this->default[3.3]);   // OK  
   }  
};  
  
int main() {  
   B ^ myb = gcnew B();  
   myb->Test();  
}  
```
