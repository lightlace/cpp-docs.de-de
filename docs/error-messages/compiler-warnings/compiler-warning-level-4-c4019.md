---
title: "Compilerwarnung (Stufe 4) C4019 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4019"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4019"
ms.assetid: 4ecfe85d-673f-4334-8154-36fe7f0b3444
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 4) C4019
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Leere Anweisung im globalen Gültigkeitsbereich  
  
 Einem Semikolon im globalen Gültigkeitsbereich geht keine Anweisung voraus.  
  
 Diese Warnung kann behoben werden, indem Sie das überzählige Semikolon entfernen.  
  
## Beispiel  
  
```  
// C4019.c // compile with: /Za /W4 #define declint( varname ) int varname; declint( a );   // C4019, int a;; declint( b )   // OK, int b; int main() { }  
```