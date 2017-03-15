---
title: "Compilerwarnung (Stufe 1) C4033 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4033"
ms.assetid: 189a9ec3-ff6d-49dd-b9b2-530b28bbb7c9
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 1) C4033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Funktion" muss einen Wert zurückgeben  
  
 Die Funktion gibt keinen Wert zurück. Es wird ein nicht definierter Wert zurückgegeben.  
  
 Funktionen, in denen `return` ohne einen Rückgabewert verwendet wird, müssen mit dem Typ `void` deklariert werden.  
  
 Dieser Fehler gilt für die C\-Sprachcode.  
  
 Im folgenden Beispiel wird C4033 generiert:  
  
```  
// C4033.c // compile with: /W1 /LD int test_1(int x)   // C4033 expected { if (x) { return;   // C4033 } }  
```