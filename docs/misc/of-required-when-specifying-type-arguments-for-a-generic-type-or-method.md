---
title: "Zur Angabe von Typargumenten f&#252;r generische Typen oder Methoden ist &quot;Of&quot; erforderlich."
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "bc32093"
  - "vbc32093"
helpviewer_keywords: 
  - "BC32093"
ms.assetid: 9a1baf12-a4a4-442d-9baa-852ad30a956b
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "shoag"
manager: "wpickett"
---
# Zur Angabe von Typargumenten f&#252;r generische Typen oder Methoden ist &quot;Of&quot; erforderlich.
Eine Anweisung versucht, ohne Verwendung einer [Of](../Topic/Of%20Clause%20\(Visual%20Basic\).md)\-Klausel einen Typ aus einem generischen Typ zu erstellen bzw. eine generische Methode aufzurufen.  
  
 Die [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)]\-Syntax für generische Typen erfordert, dass Typparameter und \-argumente durch das `Of`\-Schlüsselwort eingeführt werden. Zusätzlich müssen Typparameterliste und Typargumentliste in Klammern eingeschlossen sein.  
  
 **Fehler\-ID:** BC32093  
  
### So beheben Sie diesen Fehler  
  
-   Fügen Sie das `Of`\-Schlüsselwort am Anfang der Typargumentliste hinzu, und schließen Sie die gesamte Liste in Klammern ein.  
  
## Siehe auch  
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Gewusst wie: Verwenden einer generischen Klasse](../Topic/How%20to:%20Use%20a%20Generic%20Class%20\(Visual%20Basic\).md)