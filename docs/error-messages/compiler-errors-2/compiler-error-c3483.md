---
title: "Compilerfehler C3483 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3483"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3483"
ms.assetid: 18b3a2c5-dfc9-4661-9653-08a5798474cf
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C3483
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Variable" ist bereits Teil der Lambdaerfassungsliste.  
  
 Sie haben dieselbe Variable mehrmals an die Erfassungsliste eines Lambdaausdrucks übergeben.  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie alle zusätzlichen Instanzen der Variablen aus der Erfassungsliste.  
  
## Beispiel  
 Im folgenden Beispiel wird C3483 generiert, da die Variable `n` mehrmals in der Erfassungsliste des Lambdaausdrucks vorkommt:  
  
```  
// C3483.cpp int main() { int m = 6, n = 5; [m,n,n] { return n + m; }(); // C3483 }  
```  
  
## Siehe auch  
 [Lambda\-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)