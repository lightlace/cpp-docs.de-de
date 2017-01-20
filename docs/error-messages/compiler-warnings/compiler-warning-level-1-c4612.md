---
title: "Compilerwarnung (Stufe 1) C4612"
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
  - "C4612"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4612"
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
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