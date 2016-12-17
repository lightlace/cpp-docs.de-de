---
title: "Die Option /win32manifest wird ignoriert"
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc2034"
  - "bc2034"
helpviewer_keywords: 
  - "BC2034"
ms.assetid: 8009553a-f6ba-4d2b-8ddd-8a9357bc928e
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "shoag"
manager: "wpickett"
---
# Die Option /win32manifest wird ignoriert
Die Option \/win32manifest wird ignoriert Sie kann nur angegeben werden, wenn das Ziel eine Assembly ist.  
  
 Dem Visual Basic\-Compiler wurde die `/win32manifest`\-Compileroption übergeben, als die `/target`\-Option auf `module` festgelegt ist.  
  
 **Fehler\-ID:** BC2034  
  
### So beheben Sie diesen Fehler  
  
1.  Entfernen Sie die `/win32manifest`\-Compileroption, oder legen Sie die `/target`\-Option auf `exe`, `winexe` oder `library` fest.  
  
## Siehe auch  
 [\/target](../Topic/-target%20\(Visual%20Basic\).md)   
 [\/win32manifest](../Topic/-win32manifest%20\(Visual%20Basic\).md)   
 [Visual Basic Command\-Line Compiler](../Topic/Visual%20Basic%20Command-Line%20Compiler.md)