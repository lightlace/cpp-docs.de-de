---
title: "Compilerwarnung (Stufe 1) C4052"
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
  - "C4052"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4052"
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4052
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unterschiedliche Funktionsdeklarationen; eine enthält variable Argumente  
  
 Eine Deklaration der Funktion enthält keine variablen Argumente. Wird ignoriert.  
  
 Im folgenden Beispiel wird C4052 generiert:  
  
```  
// C4052.c // compile with: /W4 /c int f(); int f(int i, ...);   // C4052  
```