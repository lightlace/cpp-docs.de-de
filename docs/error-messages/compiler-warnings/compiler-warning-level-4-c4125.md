---
title: "Compilerwarnung (Stufe 4) C4125 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4125"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4125"
ms.assetid: a081d1f4-0789-4915-91df-7ff0b28ca245
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 4) C4125
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dezimale Ziffer beendet oktale Escapesequenz  
  
 Der Compiler wertet die oktale Zahl ohne die Dezimalziffer aus und geht davon aus, dass die Dezimalziffer ein Zeichen ist.  
  
## Beispiel  
  
```  
// C4125a.cpp // compile with: /W4 char array1[] = "\709"; // C4125 int main() { }  
```  
  
 Wenn die Ziffer 9 als Zeichen vorgesehen ist, korrigieren Sie das Beispiel wie folgt:  
  
```  
// C4125b.cpp // compile with: /W4 char array[] = "\0709";  // C4125 String containing "89" int main() { }  
```