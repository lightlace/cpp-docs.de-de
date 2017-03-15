---
title: "Compilerwarnung (Stufe 1) C4076 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4076"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4076"
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
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