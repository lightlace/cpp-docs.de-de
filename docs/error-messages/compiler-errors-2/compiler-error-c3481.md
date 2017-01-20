---
title: "Compilerfehler C3481"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C3481"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3481"
ms.assetid: 5d09375a-5ed3-4b61-86ed-45e91fd734c7
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
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