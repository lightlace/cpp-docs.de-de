---
title: "Die Option &#39;/moduleassemblyname&#39; kann nur beim Erstellen eines Ziels vom Typ &#39;Modul&#39; angegeben werden."
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "bc2030"
  - "vbc2030"
helpviewer_keywords: 
  - "BC2030"
ms.assetid: 2ebc577b-3464-40cc-8788-9fc9d3b4f928
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "shoag"
manager: "wpickett"
---
# Die Option &#39;/moduleassemblyname&#39; kann nur beim Erstellen eines Ziels vom Typ &#39;Modul&#39; angegeben werden.
Dem Visual Basic\-Compiler wurde die `/moduleassemblyname`\-Compileroption übergeben, als die `/target`\-Option auf einen anderen Wert als `module` festgelegt wurde.  
  
 **Fehler\-ID:** BC2030  
  
### So beheben Sie diesen Fehler  
  
1.  Entfernen Sie die `/moduleassemblyname`\-Compileroption, oder legen Sie die `/target`\-Option auf `module` fest.  
  
## Siehe auch  
 [\/target](../Topic/-target%20\(Visual%20Basic\).md)   
 [\/moduleassemblyname](../Topic/-moduleassemblyname.md)   
 [Visual Basic Command\-Line Compiler](../Topic/Visual%20Basic%20Command-Line%20Compiler.md)