---
title: "Alias definition is recursive."
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vs.message.0x800A00DA"
  - "vs.message.VS_E_RECURSIVEALIAS"
ms.assetid: e48a2908-9b94-4c6a-9807-beeeba71531c
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "douge"
---
# Alias definition is recursive.
Im Allgemeinen tritt dieser Fehler auf, wenn ein Alias definiert wurde, der indirekt oder direkt auf sich selbst verweist.  
  
### So beheben Sie diesen Fehler  
  
1.  Ändern Sie die Aliasdefinition, und versuchen Sie es erneut.  
  
     – oder –  
  
2.  Überprüfen Sie die aktuelle Liste der Aliase und ihrer Definitionen, indem Sie im Befehlsfenster `>alias` eingeben, und versuchen Sie es erneut.  
  
## Siehe auch  
 [Befehl "Alias"](../Topic/Alias%20Command.md)   
 [Visual Studio\-Befehlsaliase](../Topic/Visual%20Studio%20Command%20Aliases.md)