---
title: "&quot;System.Nullable&quot; erf&#252;llt die Structure-Einschr&#228;nkung f&#252;r den &lt;Typparametername&gt;-Typparameter nicht."
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
  - "bc32115"
  - "vbc32115"
helpviewer_keywords: 
  - "BC32115"
ms.assetid: 98053645-fa76-4826-a7c1-f1bdf3511863
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# &quot;System.Nullable&quot; erf&#252;llt die Structure-Einschr&#228;nkung f&#252;r den &lt;Typparametername&gt;-Typparameter nicht.
Ein generischer Typ wird aufgerufen, indem ein Typargument vom Typ <xref:System.Nullable`1> an einen Typparameter mit einer `Structure`\-Einschränkung übergeben wird.  
  
 Die Common Language Runtime \(CLR\) lässt die <xref:System.Nullable`1>\-Struktur als Typargument für diese Struktur nicht zu. Obwohl es sich um eine Struktur handelt, die ansonsten die Anforderungen einer `Structure`\-Einschränkung erfüllt, könnte die rekursive Verwendung zu umständlichen Konstruktionen wie `Nullable(Of Nullable(Of Nullable))` führen.  
  
 **Fehler\-ID:** BC32115  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie die `Structure`\-Einschränkung aus dem Typparameter, oder ändern Sie das Typargument in einen anderen Werttyp als <xref:System.Nullable`1>.  
  
## Siehe auch  
 <xref:System.Nullable`1>   
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Structure \(Visual Basic\)](assetId:///263ce115-ac36-4c05-8cb7-0e0eead5c6d0)