---
title: "Compilerwarnung (Stufe 1) C4114"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4114"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4114"
ms.assetid: 3983e1c6-e8bb-46dc-8894-e1827db48797
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4114
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der gleiche Typqualifizierer wurde mehrmals verwendet  
  
 Ein Typqualifizierer \(**const**, `volatile`, **signed** oder `unsigned`\) wird in einer Typdeklaration oder \-definition mehrfach verwendet.  Bei Verwendung der Microsoft\-Erweiterungen \(\/Ze\) wird eine Warnung, bei Einhaltung der ANSI\-Kompatibilität \(\/Za\) eine Fehlermeldung ausgegeben.  
  
 Im folgenden Beispiel wird C4114 generiert:  
  
```  
// C4114.cpp  
// compile with: /W1 /c  
volatile volatile int i;   // C4114  
```  
  
 Im folgenden Beispiel wird C4114 generiert:  
  
```  
// C4114_b.cpp  
// compile with: /W1 /c  
static const int const * ii;   // C4114  
static const int * const iii;   // OK  
```