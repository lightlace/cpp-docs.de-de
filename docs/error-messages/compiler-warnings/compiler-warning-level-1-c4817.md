---
title: "Compilerwarnung (Stufe 1) C4817 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4817"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4817"
ms.assetid: a68f5486-6940-4934-9f93-bfd4d71f92a9
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerwarnung (Stufe 1) C4817
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„member“: Unzulässige Verwendung des Punkts \(.\) zum Zugreifen auf diesen Member. Compiler wurde durch „\-\>“ ersetzt.  
  
 Es wurde der falsche Memberzugriffsoperator verwendet.  
  
## Beispiel  
 Im folgenden Beispiel wird C4817 generiert.  
  
```  
// C4817.cpp // compile with: /clr /W1 using namespace System; int main() { array<Int32> ^ a = gcnew array<Int32>(100); Console::WriteLine( a.Length );   // C4817 Console::WriteLine( a->Length );   // OK }  
```  
  
## Beispiel  
 C4817 kann auch durch **\/clr:oldSyntax** generiert werden: Im folgenden Beispiel wird C4817 generiert.  
  
```  
// C4817_b.cpp // compile with: /clr:oldSyntax /W1 using namespace System; int main() { Int32 a[] = new Int32[11]; Console::WriteLine( a.Length ); // Console::WriteLine( a->Length ); }  
```