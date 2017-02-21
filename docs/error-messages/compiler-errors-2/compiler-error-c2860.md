---
title: "Compilerfehler C2860 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2860"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2860"
ms.assetid: ccc83553-90ed-4e94-b5e9-38b58ae38e31
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2860
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"void" kann kein Argumenttyp sein, mit Ausnahme von "\(void\)"  
  
 Der Typ `void` kann nicht als Argumenttyp mit anderen Argumenten verwendet werden.  
  
 Im folgenden Beispiel wird C2860 generiert:  
  
```  
// C2860.cpp  
// compile with: /c  
void profunc1(void, int i);   // C2860  
void func10(void);   // OK  
```