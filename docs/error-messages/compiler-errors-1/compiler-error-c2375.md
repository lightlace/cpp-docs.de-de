---
title: "Compilerfehler C2375 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2375"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2375"
ms.assetid: 193c5e8b-1b20-4928-8a02-8c1cddaf2a26
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2375
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Funktion": Neudefinition; unterschiedliche Bindung  
  
 Die Funktion wurde bereits mit einem anderen Bindungsspezifizierer deklariert.  
  
 Im folgenden Beispiel wird C2375 generiert:  
  
```  
// C2375.cpp // compile with: /Za /c extern void func( void ); static void func( void );   // C2375 static void func2( void );   // OK  
```