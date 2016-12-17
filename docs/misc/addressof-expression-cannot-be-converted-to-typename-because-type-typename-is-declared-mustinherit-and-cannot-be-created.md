---
title: "Der &#39;AddressOf&#39;-Ausdruck kann nicht in &#39;&lt;Typname&gt;&#39; konvertiert werden, da der Typ &#39;&lt;Typname&gt;&#39; als &#39;MustInherit&#39; deklariert wurde und nicht erstellt werden kann."
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
  - "vbc30939"
  - "bc30939"
helpviewer_keywords: 
  - "BC30939"
ms.assetid: e8edef15-0df5-46d7-aba6-89e26a2aa506
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "shoag"
manager: "wpickett"
---
# Der &#39;AddressOf&#39;-Ausdruck kann nicht in &#39;&lt;Typname&gt;&#39; konvertiert werden, da der Typ &#39;&lt;Typname&gt;&#39; als &#39;MustInherit&#39; deklariert wurde und nicht erstellt werden kann.
Eine Anweisung versucht, einen `AddressOf`\-Ausdruck in einen Typ zu konvertieren, der nur eine Basisklasse sein und nicht zum Erstellen einer Instanz verwendet werden kann.  
  
 Der `AddressOf`\-Operator erstellt eine Delegatinstanz einer Prozedur, die auf eine bestimmte Prozedur verweist.  
  
 **Fehler\-ID:** BC30939  
  
### So beheben Sie diesen Fehler  
  
-   Weisen Sie den `AddressOf`\-Ausdruck einem bestimmten Delegattyp zu.  
  
## Siehe auch  
 [AddressOf Operator](../Topic/AddressOf%20Operator%20\(Visual%20Basic\).md)   
 [NICHT IM BUILD: Delegaten und der AddressOf\-Operator](assetId:///7b2ed932-8598-4355-b2f7-5cedb23ee86f)   
 [Delegates](../Topic/Delegates%20\(Visual%20Basic\).md)