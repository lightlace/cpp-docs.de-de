---
title: "Compilerwarnung (Stufe 1) C4627 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4627"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4627"
ms.assetid: 8840f3e6-b496-423a-8635-eb55d5f854a2
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# Compilerwarnung (Stufe 1) C4627
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"\<Bezeichner\>": Wird bei der Suche nach Verwendung des vorkompilierten Headers übersprungen.  
  
 Bei der Suche nach dem Ort, an dem ein vorkompilierter Header verwendet wird, hat der Compiler eine `#include`\-Anweisung für die Includedatei *\<Bezeichner\>* gefunden. Der Compiler ignoriert die `#include`\-Anweisung, gibt aber die Warnung **C4627** aus, wenn der vorkompilierte Header nicht bereits die Includedatei *\<Bezeichner\>* enthält.  
  
## Siehe auch  
 [Erstellen vorkompilierter Headerdateien](../../build/reference/creating-precompiled-header-files.md)