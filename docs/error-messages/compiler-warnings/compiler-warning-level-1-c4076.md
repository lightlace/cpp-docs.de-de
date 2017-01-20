---
title: "Compilerwarnung (Stufe 1) C4076"
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
  - "C4076"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4076"
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4076
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Typmodifizierer": Kann nicht mit Typ "Typname" verwendet werden  
  
 Ein Typmodifizierer kann unabhängig davon, ob er **signed** oder `unsigned` ist, nicht mit einem Typ verwendet werden, der nicht ganzzahlig ist.***Typmodifizierer*** wird ignoriert.  
  
## Beispiel  
 Im folgenden Beispiel wird C4076 generiert:  
  
```  
// C4076.cpp // compile with: /W1 /LD unsigned double x;   // C4076  
```