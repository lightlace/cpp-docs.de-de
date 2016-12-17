---
title: "Das Erben von &#39;System.&lt;Klassenname&gt;&#39; ist ung&#252;ltig."
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
  - "vbc30015"
  - "bc30015"
helpviewer_keywords: 
  - "BC30015"
ms.assetid: b4c005df-a510-47c7-b5cc-27f4514d32b6
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Das Erben von &#39;System.&lt;Klassenname&gt;&#39; ist ung&#252;ltig.
Eine Klasse kann nicht von `System.Array`, `System.Delegate`, `System.Enum` oder `System.ValueType` erben.  
  
 **Fehler\-ID:** BC30015  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie die `Inherits`\-Anweisung, oder ändern Sie sie, um von einer gültigen Basisklasse zu erben.  
  
## Siehe auch  
 [Inheritance Basics](../Topic/Inheritance%20Basics%20\(Visual%20Basic\).md)   
 [Object Variable Declaration](../Topic/Object%20Variable%20Declaration%20\(Visual%20Basic\).md)