---
title: "Compilerwarnung (Stufe 1) C4185"
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
  - "C4185"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4185"
ms.assetid: 37e7063a-35b1-4e05-ae31-e811dced02b9
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4185
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Das unbekannte \#import\-Attribut "Attribut" wird ignoriert  
  
 Das Attribut ist kein gültiges `#import`\-Attribut. Es wird ignoriert.  
  
## Beispiel  
  
```  
// C4185.cpp // compile with: /W1 /c #import "stdole2.tlb" no_such_attribute   // C4185  
```