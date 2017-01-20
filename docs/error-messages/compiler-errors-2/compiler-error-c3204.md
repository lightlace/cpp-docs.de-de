---
title: "Compilerfehler C3204"
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
  - "C3204"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3204"
ms.assetid: 06e578da-0262-48c8-b2ae-be1cd6d28884
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3204
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"\_alloca" kann nicht innerhalb eines catch\-Blocks aufgerufen werden  
  
 Dieser Fehler tritt auf, wenn Sie einen Aufruf von [\_alloca](../../c-runtime-library/reference/alloca.md) innerhalb eines catch\-Blocks verwenden.  
  
## Beispiel  
 Im folgenden Beispiel wird C3204 generiert:  
  
```  
// C3204.cpp // compile with: /EHsc #include <malloc.h> void ShowError(void) { try { } catch(...) { _alloca(1);   // C3204 } }  
```