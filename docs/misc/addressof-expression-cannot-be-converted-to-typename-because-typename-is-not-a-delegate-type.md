---
title: "Der Ausdruck „AddressOf“ kann nicht in &#39;&lt;Typname&gt;&#39; umgewandelt werden, da &#39;&lt;Typname&gt;&#39; kein Delegattyp ist."
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
  - "vbc30581"
  - "bc30581"
helpviewer_keywords: 
  - "BC30581"
ms.assetid: 5db7589a-5456-4b3a-9d6b-93d9157f0484
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Der Ausdruck „AddressOf“ kann nicht in &#39;&lt;Typname&gt;&#39; umgewandelt werden, da &#39;&lt;Typname&gt;&#39; kein Delegattyp ist.
Eine Anweisung versucht, einen `AddressOf`\-Ausdruck in einen Typ zu konvertieren, der kein Delegattyp ist.  
  
 Der `AddressOf`\-Operator erstellt eine Delegatinstanz einer Prozedur, die auf eine bestimmte Prozedur verweist.`AddressOf` kann als Operand eines Delegatkonstruktors oder in einem Kontext verwendet werden, in dem der Typ des Delegaten vom Compiler bestimmt werden kann.  
  
 **Fehler\-ID:** BC30581  
  
### So beheben Sie diesen Fehler  
  
-   Ändern Sie den Zieltyp in einen Delegattyp.  
  
## Siehe auch  
 [AddressOf Operator](../Topic/AddressOf%20Operator%20\(Visual%20Basic\).md)   
 [NICHT IM BUILD: Delegaten und der AddressOf\-Operator](assetId:///7b2ed932-8598-4355-b2f7-5cedb23ee86f)