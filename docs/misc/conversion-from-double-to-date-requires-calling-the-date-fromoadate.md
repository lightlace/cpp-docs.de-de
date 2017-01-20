---
title: "F&#252;r die Konvertierung von &#39;Double&#39; in &#39;Date&#39; muss &#39;Date.FromOADate&#39; aufgerufen werden"
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
  - "vbc30533"
  - "bc30533"
helpviewer_keywords: 
  - "BC30533"
ms.assetid: afcfd115-4614-4b0b-ad09-76af8dba2ed5
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# F&#252;r die Konvertierung von &#39;Double&#39; in &#39;Date&#39; muss &#39;Date.FromOADate&#39; aufgerufen werden
Sie haben versucht, einen `Date`\-Wert in einen `Double`\-Wert zu konvertieren, was nicht ohne Verwendung der Methode <xref:System.DateTime.FromOADate*?displayProperty=fullName> erfolgen kann.  
  
 **Fehler\-ID:** BC30533  
  
### So beheben Sie diesen Fehler  
  
-   Verwenden Sie die <xref:System.DateTime.FromOADate*>\-Methode, um den Wert zu konvertieren.  
  
## Siehe auch  
 [Type Conversions in Visual Basic](../Topic/Type%20Conversions%20in%20Visual%20Basic.md)