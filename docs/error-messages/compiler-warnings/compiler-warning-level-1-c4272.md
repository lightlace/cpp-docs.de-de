---
title: "Compilerwarnung (Stufe 1) C4272 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4272"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4272"
ms.assetid: 0d6c1de4-2eef-42c4-b861-c221f8b495ef
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerwarnung (Stufe 1) C4272
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion' : Ist als \_\_declspec\(dllimport\) markiert. Beim Importieren einer Funktion muss eine systemeigene Aufrufkonvention angegeben werden.  
  
 Der Export einer mit der [\_\_clrcall](../../cpp/clrcall.md)\-Aufrufkonvention markierten Funktion stellt einen Fehler dar, und der Compiler gibt diese Warnung aus, sobald Sie versuchen, eine Funktion zu importieren, die als `__clrcall` markiert ist.  
  
 Im folgenden Beispiel wird C4272 generiert:  
  
```  
// C4272.cpp  
// compile with: /c /W1 /clr  
__declspec(dllimport) void __clrcall Test();   // C4272  
__declspec(dllimport) void Test2();   // OK  
```