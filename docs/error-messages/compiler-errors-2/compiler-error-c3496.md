---
title: "Compilerfehler C3496 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3496"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3496"
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C3496
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"this" wird immer nach Wert erfasst: "&" wird ignoriert.  
  
 Der `this`\-Zeiger kann nicht als Verweis erfasst werden.  
  
### So beheben Sie diesen Fehler  
  
-   Erfassen Sie den `this`\-Zeiger nach Wert.  
  
## Beispiel  
 Im folgenden Beispiel wird C3496 generiert, weil ein Verweis auf den `this`\-Zeiger in der Erfassungsliste eines Lambdaausdrucks auftritt:  
  
```  
// C3496.cpp // compile with: /c class C { void f() { [&this] {}(); // C3496 } };  
```  
  
## Siehe auch  
 [Lambda\-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)