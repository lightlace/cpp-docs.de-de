---
title: "Compilerfehler C2710 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2710"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2710"
ms.assetid: a2a6bb5b-86ad-4a6c-acd0-e2bef8464e0e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2710
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Konstrukt': \_\_declspec\(Modifizierer\) kann nur auf eine Funktion angewendet werden, die einen Zeiger zurückgibt  
  
 Eine Funktion, deren Rückgabewert ein Zeiger ist, stellt das einzige Konstrukt dar, auf das `modifier` angewendet werden kann.  
  
 Im folgenden Beispiel wird C2710 generiert:  
  
```  
// C2710.cpp  
__declspec(restrict) void f();   // C2710  
// try the following line instead  
__declspec(restrict) int * g();  
```