---
title: "#ExternalSource-Direktiven sind nicht schachtelbar."
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
  - "bc30580"
  - "vbc30580"
helpviewer_keywords: 
  - "BC30580"
ms.assetid: 56c6ef4b-28b1-4a62-8afa-d83a7742b507
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "shoag"
manager: "wpickett"
---
# #ExternalSource-Direktiven sind nicht schachtelbar.
Sie haben versucht, eine `#ExternalSource`\-Anweisung \(Direktive\) in einem anderen `#ExternalSource`\-Block anzuordnen. Die `#ExternalSource`\-Anweisung verweist auf äußeren Code, sodass der Compiler genau melden kann, wenn Ausnahmen innerhalb dieses Codes auftreten.  
  
 `#ExternalSource`\-Blöcke können nicht in anderen `#ExternalSource`\-Blöcken geschachtelt werden.  
  
 **Fehler\-ID:** BC30580  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie die innere `#ExternalSource`\-Anweisung aus dem einschließenden `#ExternalSource`\-Block.  
  
## Siehe auch  
 [\#ExternalSource Directive](../Topic/%23ExternalSource%20Directive.md)   
 [NOTINBUILD: Bedingte Kompilierung \(Visual Basic\)](assetId:///ad1e35e0-935e-4a35-a2ae-738bcf2a9240)