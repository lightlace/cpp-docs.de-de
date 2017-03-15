---
title: "Compilerfehler C3274 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3274"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3274"
ms.assetid: 1f03f18e-b569-48eb-9249-11c70122a305
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerfehler C3274
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\_\_finally\/finally' ohne entsprechendes 'try'  
  
 Es wurde eine [\_\_finally](../../cpp/try-finally-statement.md)\- oder [finally](../../dotnet/finally.md)\-Anweisung gefunden, der kein `try` entspricht. Um dies zu beheben, löschen Sie entweder die `__finally`\-Anweisung, oder fügen Sie eine `try`\-Anweisung für die `__finally` hinzu.  
  
 Im folgenden Beispiel wird C3274 generiert:  
  
```  
// C3274.cpp // compile with: /clr // C3274 expected using namespace System; int main() { try { try { throw gcnew ApplicationException(); } catch(...) { Console::Error->WriteLine(L"Caught an exception"); } finally { Console::WriteLine(L"In finally"); } } finally { Console::WriteLine(L"In finally"); } // Uncomment the following 3 lines to resolve. // try { //   throw gcnew ApplicationException(); // } finally { Console::WriteLine(L"In finally"); } Console::WriteLine(L"**FAIL**"); }  
```