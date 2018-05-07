---
title: Compiler-Fehler C3175 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3175
dev_langs:
- C++
helpviewer_keywords:
- C3175
ms.assetid: 3f19d513-a05a-4b6c-806f-276fe5c36b90
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 199895ecba509b291d3853f0adabb2b68eee1e49
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3175"></a>Compiler-Fehler C3175 generiert
"Funktion1": Rufen Sie eine Methode eines verwalteten Typs kann nicht von nicht verwalteten Funktion "Funktion2"  
  
 Nicht verwaltete Funktionen können keine Memberfunktionen von verwalteten Klassen aufrufen.  
  
 Im folgende Beispiel wird C3175 generiert:  
  
```  
// C3175_2.cpp  
// compile with: /clr  
  
ref struct A {  
   static void func() {  
   }  
};  
  
#pragma unmanaged   // remove this line to resolve  
  
void func2() {  
   A::func();   // C3175  
}  
  
#pragma managed  
  
int main() {  
   A ^a = gcnew A;  
   func2();  
}  
```  
