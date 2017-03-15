---
title: "Compilerfehler C3481 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3481"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3481"
ms.assetid: 5d09375a-5ed3-4b61-86ed-45e91fd734c7
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C3481
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': Es wurde keine Lambdaerfassungsvariable gefunden.  
  
 Der Compiler konnte die Definition einer Variablen, die Sie an die Erfassungsliste eines Lambda\-Ausdrucks übergeben haben, nicht finden.  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie die Variable aus der Erfassungsliste des Lambda\-Ausdrucks.  
  
## Beispiel  
 Im folgenden Beispiel wird C3481 generiert, weil die `n`\-Variable nicht definiert ist:  
  
```  
// C3481.cpp int main() { [n] {}(); // C3481 }  
```  
  
## Siehe auch  
 [Lambda\-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)