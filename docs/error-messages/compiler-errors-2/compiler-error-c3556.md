---
title: "Compilerfehler C3556 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3556"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3556"
ms.assetid: 9b002dcc-494e-414f-9587-20c2a0a39333
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C3556
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Ausdruck": Falsches Argument für "Deklarationstyp".  
  
 Der Compiler kann den Typ des Ausdrucks, der das Argument für den `decltype(``expression``)`\-Typspezifizierer ist, nicht ableiten. Im folgenden Codebeispiel kann der Compiler den Typ des `myFunction`\-Arguments nicht ableiten, weil `myFunction` überladen ist.  
  
```  
void myFunction(); void myFunction(int); decltype(myFunction); // C3556  
```