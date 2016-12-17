---
title: "&quot;&lt;Prozedurname1&gt;&quot; kann &quot;&lt;Prozedurname2&gt;&quot; nicht &#252;berschreiben, da sie sich durch Parameter unterscheiden, die als ParamArray deklariert sind."
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
  - "bc30906"
  - "vbc30906"
helpviewer_keywords: 
  - "BC30906"
ms.assetid: 12939030-732e-4c6d-8fe9-707b7532174b
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "shoag"
manager: "wpickett"
---
# &quot;&lt;Prozedurname1&gt;&quot; kann &quot;&lt;Prozedurname2&gt;&quot; nicht &#252;berschreiben, da sie sich durch Parameter unterscheiden, die als ParamArray deklariert sind.
Eine Prozedur in einer abgeleiteten Klasse überschreibt eine Prozedur gleichen Namens in der Basisklasse, aber die Parameterlisten unterscheiden sich.  
  
 Um eine Prozedur in einer geerbten Klasse zu überschreiben, müssen Parameterliste, Zugriffsebene und Rückgabetyp \(sofern vorhanden\) der überschreibenden Prozedur übereinstimmen. Insbesondere müssen alle [Optional](../Topic/Optional%20\(Visual%20Basic\).md)\- oder [ParamArray](../Topic/ParamArray%20\(Visual%20Basic\).md)\-Deklarationen übereinstimmen.  
  
 **Fehler\-ID:** BC30906  
  
### So beheben Sie diesen Fehler  
  
-   Wenn Sie die Prozedur überschreiben möchten, sorgen Sie dafür, dass die Parameterliste exakt der Parameterliste in der Basisklassenprozedur entspricht. Wenn der letzte Parameter in der Basisklassenprozedur mit `ParamArray` deklariert ist, muss er auch in der überschreibenden Prozedur mit `ParamArray` deklariert sein.  
  
-   Wenn sich die Parameterliste von der Basisklassenversion unterscheiden soll, können Sie sie nicht überschreiben. Ziehen Sie stattdessen eine Überladung in Betracht. Weitere Informationen finden Sie unter [Procedure Overloading](../Topic/Procedure%20Overloading%20\(Visual%20Basic\).md).  
  
## Siehe auch  
 [Overrides](../Topic/Overrides%20\(Visual%20Basic\).md)   
 [NICHT IM BUILD: Überschreiben von Eigenschaften und Methoden](assetId:///2167e8f5-1225-4b13-9ebd-02591ba90213)