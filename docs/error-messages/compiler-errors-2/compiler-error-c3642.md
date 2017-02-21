---
title: "Compilerfehler C3642 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3642"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3642"
ms.assetid: 429790c2-9614-4d85-b31c-687c8d8f83ff
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Compilerfehler C3642
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'return\_type\/args': Mit der \_\_clrcall\-Aufrufkonvention aus systemeigenem Code kann keine Funktion aufgerufen werden  
  
 Eine Funktion, die mit der [\_\_clrcall](../../cpp/clrcall.md)\-Aufrufkonvention markiert ist, kann nicht von systemeigenem \(nicht verwaltetem\) Code aufgerufen werden.  
  
 *return\_type\/args* ist entweder der Name der Funktion oder der Typ der Funktion `__clrcall`, die aufgerufen werden soll.  Ein Typ wird verwendet, wenn der Aufruf über einen Funktionszeiger erfolgt.  
  
 Um eine verwaltete Funktion aus einem systemeigenen Kontext aufzurufen, können Sie eine Wrapperfunktion hinzufügen, die die `__clrcall`\-Funktion aufruft.  Als Alternative können Sie den CLR\-Marshallingmechanismus verwenden. Weitere Informationen finden Sie unter [Gewusst wie: Marshallen von Funktionszeigern mit PInvoke](../../dotnet/how-to-marshal-function-pointers-using-pinvoke.md).  
  
 Im folgenden Beispiel wird C3642 generiert:  
  
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