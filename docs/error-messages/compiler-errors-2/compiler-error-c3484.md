---
title: "Compilerfehler C3484 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3484"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3484"
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C3484
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vor dem Rückgabetyp wird '\-\>' erwartet.  
  
 Sie müssen vor dem Rückgabetyp eines Lambdaausdrucks `->` bereitstellen.  
  
### So beheben Sie diesen Fehler  
  
-   Stellen Sie `->` vor dem Rückgabetyp bereit.  
  
## Beispiel  
 Im folgenden Beispiel wird der Fehler C3484 generiert:  
  
```  
// C3484a.cpp int main() { return []() . int { return 42; }(); // C3484 }  
```  
  
## Beispiel  
 Im folgende Beispiel wird C3484 durch Bereitstellen von `->` vor dem Rückgabetyp des Lambdaausdrucks behoben:  
  
```  
// C3484b.cpp int main() { return []() -> int { return 42; }(); }  
```  
  
## Siehe auch  
 [Lambda\-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)