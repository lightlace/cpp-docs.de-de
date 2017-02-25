---
title: "Compilerfehler C2382 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2382"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2382"
ms.assetid: 4d4436f9-d0d6-4bd0-b8ec-767b89adfb2f
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2382
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„function“: Neudefinition; unterschiedliche Ausnahmespezifikationen  
  
 Unter [\/Za](../../build/reference/za-ze-disable-language-extensions.md) zeigt dieser Fehler an, dass eine Funktionsüberladung nur auf für die [Ausnahmespezifikation](../../cpp/exception-specifications-throw-cpp.md) versucht wurde.  
  
 Im folgenden Beispiel wird C2382 generiert:  
  
```  
// C2382.cpp // compile with: /Za /c void f1(void) throw(int) {} void f1(void) throw(char) {}   // C2382 void f2(void) throw(char) {}   // OK  
```