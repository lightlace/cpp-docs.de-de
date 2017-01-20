---
title: "Nicht freigegebene Member in einer Struktur k&#246;nnen nicht als &#39;New&#39; deklariert werden."
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
  - "vbc30795"
  - "BC30795"
helpviewer_keywords: 
  - "BC30795"
ms.assetid: 8e4e1ad8-3bac-475f-82e8-e4f134692204
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Nicht freigegebene Member in einer Struktur k&#246;nnen nicht als &#39;New&#39; deklariert werden.
Eine nicht freigegebene Variable in einer Struktur wird mit einer `New`\-Klausel deklariert.  
  
 Sie können eine freigegebene Verweisvariable in einer Struktur initialisieren, und Sie können eine Verweisvariable ohne Initialisierung verwenden. Die folgenden Codezeilen zeigen dies.  
  
 `Shared structVar1 As New System.ApplicationException`  
  
 `Dim structVar2 As System.ApplicationException`  
  
 Sie können eine nicht freigegebene Verweisvariable jedoch nicht in einer Struktur initialisieren. Die folgende Codezeile ist ungültig.  
  
 `Dim structVar3 As New System.ApplicationException ' INVALID IN A STRUCTURE`  
  
 **Fehler\-ID:** BC30795  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie den `Shared`\-Modifizierer oder das Schlüsselwort `New` aus der Deklaration der Verweisvariablen.  
  
## Siehe auch  
 [Structure Statement](../Topic/Structure%20Statement.md)   
 [Shared](../Topic/Shared%20\(Visual%20Basic\).md)   
 [New Operator](../Topic/New%20Operator%20\(Visual%20Basic\).md)