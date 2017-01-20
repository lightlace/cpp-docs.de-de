---
title: "Compilerwarnung (Stufe 4) C4131"
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
  - "C4131"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4131"
ms.assetid: 7903b3e1-454f-4be2-aa9b-230992f96a2d
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4131
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"function": Verwendet Deklarator für altes Format  
  
 Die angegebene Funktionsdeklaration weist keine Prototypform auf.  
  
 Funktionsdeklarationen im alten Format sollten in die Prototypform konvertiert werden.  
  
 Im folgenden Beispiel wird eine Funktionsdeklaration im alten Stil veranschaulicht:  
  
```  
// C4131.c // compile with: /W4 /c void addrec( name, id ) // C4131 expected char *name; int id; { }  
```  
  
 Im folgenden Beispiel wird eine Prototypform veranschaulicht:  
  
```  
void addrec( char *name, int id ) { }  
```