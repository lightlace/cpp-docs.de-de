---
title: "Die Schnittstelle &quot;&lt;Schnittstellenname1&gt;&quot; kann nicht geerbt werden, da die Schnittstelle &quot;&lt;Schnittstellenname2&gt;&quot;, von der geerbt wird, m&#246;glicherweise mit der Schnittstelle &quot;&lt;Schnittstellenname3&gt;&quot; identisch ist, von der die Schnittstelle &quot;&lt;Schnittstellenname4&gt;&quot; bei manchen Typargumenten erbt."
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
  - "vbc32122"
  - "bc32122"
helpviewer_keywords: 
  - "BC32122"
ms.assetid: 64a66ec7-0f5f-4804-a92b-9a6279fdfd6d
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "shoag"
manager: "wpickett"
---
# Die Schnittstelle &quot;&lt;Schnittstellenname1&gt;&quot; kann nicht geerbt werden, da die Schnittstelle &quot;&lt;Schnittstellenname2&gt;&quot;, von der geerbt wird, m&#246;glicherweise mit der Schnittstelle &quot;&lt;Schnittstellenname3&gt;&quot; identisch ist, von der die Schnittstelle &quot;&lt;Schnittstellenname4&gt;&quot; bei manchen Typargumenten erbt.
Eine generische Schnittstelle erbt von mindestens zwei generischen Schnittstellen, und zwei der Vererbungen können einen Konflikt mit bestimmten Werten von Typargumenten verursachen.  
  
 Dieser Fehler kann durch die folgenden Anweisungen generiert werden.  
  
```  
Public Interface interfaceA(Of u) End Interface Public Interface interfaceX(Of v) Inherits interfaceA(Of v) End Interface Public Interface interfaceY(Of w) Inherits interfaceA(Of w) End Interface Public Interface derivedInterface(Of t1, t2) Inherits interfaceX(Of t1), interfaceY(Of t2) End Interface  
```  
  
 Wenn die Erstellung oder Implementierung von `derivedInterface` durch Angeben desselben Typs für `t1` und `t2` erfolgt, muss sie zwei Versionen von `interfaceA` mit identischen Typargumenten erben. Dies führt zu einer Mehrdeutigkeit in Bezug auf die Version, auf die zugegriffen werden soll.  
  
 **Fehler\-ID:** BC32122  
  
### So beheben Sie diesen Fehler  
  
-   Ändern Sie eines der für die abgeleitete Schnittstelle angegebenen Typargumente, sodass kein Konflikt auftritt.  
  
     \- oder \-  
  
-   Entfernen Sie eine der Schnittstellen, die den potenziellen Vererbungs\- oder Implementierungskonflikt auslösen, aus der `Inherits`\-Anweisung.  
  
## Siehe auch  
 [NICHT IM BUILD: Übersicht über Schnittstellen](assetId:///f96bb470-c1b8-4c73-89bc-6f536b798da1)   
 [Interface Statement](../Topic/Interface%20Statement%20\(Visual%20Basic\).md)   
 [Inheritance Basics](../Topic/Inheritance%20Basics%20\(Visual%20Basic\).md)   
 [Inherits Statement](../Topic/Inherits%20Statement.md)   
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)