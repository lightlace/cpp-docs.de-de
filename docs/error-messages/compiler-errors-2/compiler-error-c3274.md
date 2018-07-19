---
title: Compilerfehler C3274 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3274
dev_langs:
- C++
helpviewer_keywords:
- C3274
ms.assetid: 1f03f18e-b569-48eb-9249-11c70122a305
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 072e490d73c574367c9c97d86d9c82d547a76e1c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33250963"
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