---
title: "Compilerwarnung (Stufe 1) C4077"
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
  - "C4077"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4077"
ms.assetid: c2d28805-b33f-41ad-afba-33b3f788c649
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4077
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unbekannte check\_stack\-Option  
  
 Die alte Form des **check\_stack**\-Pragmas wird mit einem unbekannten Argument verwendet. Das Argument muss `+`, `-`, `(on)`, `(off)` oder leer sein.  
  
 Der Compiler ignoriert das Pragma und die Stapelüberprüfung bleibt unverändert.  
  
## Beispiel  
  
```  
// C4077.cpp // compile with: /W1 /LD #pragma check_stack yes // C4077 #pragma check_stack +    // Correct old form #pragma check_stack (on) // Correct new form  
```