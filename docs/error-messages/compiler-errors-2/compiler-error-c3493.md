---
title: "Compilerfehler C3493 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3493"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3493"
ms.assetid: 734b4257-12a3-436f-8488-c8c55ec81634
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C3493
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"var" kann nicht implizit erfasst werden, da kein Standarderfassungsmodus angegeben wurde  
  
 Die leere Lambdaausdruckerfassung, `[]`, gibt an, dass der Lambdaausdruck weder explizit noch implizit Variablen erfasst.  
  
### So beheben Sie diesen Fehler  
  
-   Geben Sie einen Standarderfassungsmodus an, oder  
  
-   erfassen Sie explizit mindestens eine Variable.  
  
## Beispiel  
 Im folgenden Beispiel wird C3493 generiert, da eine externe Variable geändert, aber die leere Erfassungsklausel angegeben wird:  
  
```  
// C3493a.cpp int main() { int m = 55; [](int n) { m = n; }(99); // C3493 }  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C3493 aufgelöst, indem die Erfassung nach Verweis als Standarderfassungsmodus angegeben wird.  
  
```  
// C3493b.cpp int main() { int m = 55; [&](int n) { m = n; }(99); }  
```  
  
## Siehe auch  
 [Lambda\-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)