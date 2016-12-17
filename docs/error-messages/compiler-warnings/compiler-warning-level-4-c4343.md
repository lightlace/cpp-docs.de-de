---
title: "Compilerwarnung (Stufe 4) C4343"
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
  - "C4343"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4343"
ms.assetid: a721b710-e04f-4d15-b678-e4a2c8fd0181
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4343
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„\#pragma optimize\("g",off\)“ überschreibt Option „\/Og“.  
  
 Diese Warnung, die nur im Compiler der Itanium\-Prozessorfamilie \(IPF\) gültig ist, meldet, dass ein „pragma [optimize](../../preprocessor/optimize.md)“ eine [\/Og](../../build/reference/og-global-optimizations.md)\-Compileroption außer Kraft gesetzt hat.  
  
 Im folgenden Beispiel wird C4343 generiert.  
  
```  
// C4343.cpp // compile with: /Og /W4 /LD // processor: IPF #pragma optimize ("g", off)   // C4343  
```