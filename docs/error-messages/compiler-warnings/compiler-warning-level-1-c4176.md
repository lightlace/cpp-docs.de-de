---
title: "Compilerwarnung (Stufe 1) C4176 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4176"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4176"
ms.assetid: cfffb934-219a-4a63-9df6-ba54405bf766
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 1) C4176
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Subcomponent": Unbekannte Unterkomponente bei \#pragma component browser.  
  
 \#pragma **component** enthält eine ungültige Unterkomponente. Um Verweise auf einen bestimmten Namen auszuschließen, müssen Sie die Option **references** vor dem Namen verwenden.  
  
## Beispiel  
  
```  
// C4176.cpp // compile with: /W1 /LD #pragma component(browser, off, i)  // C4176 #pragma component(browser, off, references, i) // ok  
```