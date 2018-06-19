---
title: Compilerfehler C3642 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3642
dev_langs:
- C++
helpviewer_keywords:
- C3642
ms.assetid: 429790c2-9614-4d85-b31c-687c8d8f83ff
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c9e841bcc4fbcb62d6a2d1e6f51f47a73bd2e06a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33264516"
---
# <a name="compiler-error-c3642"></a>Compilerfehler C3642
' Return_type/Args': eine Funktion kann nicht aufgerufen werden, mit der __clrcall-Aufrufkonvention von systemeigenem Code  
  
 Eine Funktion, die mit der [__clrcall](../../cpp/clrcall.md) Aufrufkonvention kann nicht von systemeigenem (nicht verwalteten) Code aufgerufen werden.  
  
 *Return_type-Args* ist entweder der Name der Funktion oder der Typ, der die `__clrcall` Funktion, die Sie aufrufen möchten.  Ein Typ wird verwendet, wenn Sie über einen Funktionszeiger aufrufen.  
  
 Um eine verwaltete Funktion aus einem systemeigenen Kontext aufzurufen, können Sie hinzufügen, eine ""-Wrapperfunktion, die aufgerufen wird, wird die `__clrcall` Funktion. Oder Sie können den CLR-marshalling-Mechanismus verwenden; finden Sie unter [wie: Marshallen Funktion Zeigern mithilfe von PInvoke](../../dotnet/how-to-marshal-function-pointers-using-pinvoke.md) für Weitere Informationen.  
  
 Im folgende Beispiel wird C3642 generiert:  
  
```  
// C3642.cpp  
// compile with: /clr  
using namespace System;  
struct S {  
   void Test(String ^ s) {   // CLR type in signature, implicitly __clrcall  
      Console::WriteLine(s);  
   }  
   void Test2(char * s) {  
      Test(gcnew String(s));  
   }  
};  
  
#pragma unmanaged  
int main() {  
   S s;  
   s.Test("abc");   // C3642  
   s.Test2("abc");   // OK  
}  
```