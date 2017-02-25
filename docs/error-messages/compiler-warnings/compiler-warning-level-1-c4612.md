---
title: "Compilerwarnung (Stufe 1) C4612 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4612"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4612"
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 1) C4612
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fehler im Namen der Includedatei  
  
 Diese Warnung tritt bei **\#pragma include\_alias** auf, wenn ein Dateiname falsch ist oder fehlt.  
  
 Die Argumente für die **\#pragma include\_alias**\-Anweisung können die Anführung wie in \(**"***dateiname***"**\) oder spitze Klammern wie in \(**\<***dateiname***\>**\) verwenden, aber beide müssen die gleiche Form aufweisen.  
  
## Beispiel  
  
```  
// C4612.cpp // compile with: /W1 /LD #pragma include_alias("StandardIO", <stdio.h>) // C4612  
```