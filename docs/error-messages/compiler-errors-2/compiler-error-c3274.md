---
title: Compilerfehler C3274 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3274
dev_langs:
- C++
helpviewer_keywords:
- C3274
ms.assetid: 1f03f18e-b569-48eb-9249-11c70122a305
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6fc2149b3aac1e3575500ed4ac6c3c1b283f1db4
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3274"></a>Compilerfehler C3274
'__finally/finally' ohne entsprechendes 'try'  
  
 Es wurde eine [__finally](../../cpp/try-finally-statement.md) - oder [finally](../../dotnet/finally.md) -Anweisung gefunden, der kein `try`entspricht. Um dies zu beheben, löschen Sie entweder die `__finally` -Anweisung, oder fügen Sie eine `try` -Anweisung für die `__finally`hinzu.  
  
 Im folgenden Beispiel wird C3274 generiert:  
  
```  
// C3274.cpp  
// compile with: /clr  
// C3274 expected  
using namespace System;  
int main() {  
   try {  
      try {  
         throw gcnew ApplicationException();  
      }  
      catch(...) {  
         Console::Error->WriteLine(L"Caught an exception");  
      }  
      finally {  
         Console::WriteLine(L"In finally");  
      }  
   } finally {  
      Console::WriteLine(L"In finally");  
   }  
  
   // Uncomment the following 3 lines to resolve.  
   // try {  
   //   throw gcnew ApplicationException();  
   // }  
  
   finally {  
      Console::WriteLine(L"In finally");  
   }  
   Console::WriteLine(L"**FAIL**");  
}  
```
