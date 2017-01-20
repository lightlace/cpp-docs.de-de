---
title: "Bei der Initialisierung eines Arrays aus Arrays k&#246;nnen nur die Grenzen f&#252;r das Array der h&#246;chsten Ebene festgelegt werden."
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
  - "bc32014"
  - "vbc32014"
helpviewer_keywords: 
  - "BC32014"
ms.assetid: d8d7155d-82d1-4a25-b9bb-1883e1586383
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Bei der Initialisierung eines Arrays aus Arrays k&#246;nnen nur die Grenzen f&#252;r das Array der h&#246;chsten Ebene festgelegt werden.
Eine Arrayinitialisierung für ein verzweigtes Array \(Array aus Arrays\) legt die anfängliche Länge für eine der niedrigeren Ebenen fest. Sie können in der Anweisung für die Arraydeklaration aber nur die Länge des Arrays der obersten Ebene festlegen.  
  
 **Fehler\-ID:** BC32014  
  
### So beheben Sie diesen Fehler  
  
1.  Entfernen Sie die Längenangabe aus allen Arrays mit Ausnahme des Arrays der obersten Ebene.  
  
2.  Legen Sie die anfängliche Länge von Arrays niedrigerer Ebenen in nachfolgenden Zuweisungsanweisungen mit dem `New`\-Schlüsselwort fest.  
  
## Siehe auch  
 [NOTINBUILD: Arrayvariable](assetId:///c2da78bd-6928-46ba-805f-44f819dfaf93)   
 [NOTINBUILD: Verzweigte Arrays in Visual Basic](assetId:///05c12439-ee8f-4fef-ba75-b35402b67ab9)   
 [New Operator](../Topic/New%20Operator%20\(Visual%20Basic\).md)