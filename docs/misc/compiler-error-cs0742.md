---
title: "Compilerfehler CS0742"
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CS0742"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0742"
ms.assetid: 078ee7af-17e4-4572-8fee-d97e09c9002b
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0742
Auf einen Abfragetext muss eine Select\-Klausel oder Group\-Klausel folgen.  
  
 Ein Abfrageausdruck muss entweder mit einer `select`\-Klausel oder einer `group`\-Klausel \(ohne eine Fortsetzung\) enden.  
  
### So beheben Sie diesen Fehler  
  
1.  Fügen Sie der Abfrage eine [select\-Klausel](../Topic/select%20clause%20\(C%23%20Reference\).md) oder eine [group\-Klausel](../Topic/group%20clause%20\(C%23%20Reference\).md) hinzu.  
  
## Beispiel  
 Durch den folgenden Code wird der Fehler CS0742 ausgelöst:  
  
```  
// cs0742.cs using System.Linq; public class Test { public static int Main() { int[] array = { 1, 2, 3 }; var query = from num in array; // CS0742 return 1; } }  
```  
  
 Wenn in der `group`\-Klausel das [into](../Topic/into%20\(C%23%20Reference\).md)\-Schlüsselwort zum Speichern der Ergebnisse der Gruppierung in einem temporären Bezeichner verwendet wird, darf sie nicht die letzte Klausel in einer Abfrage sein. Dann ist eine `select`\-Klausel oder eine zweite `group`\-Klausel erforderlich.  
  
## Siehe auch  
 [LINQ\-Abfrageausdrücke](../Topic/LINQ%20Query%20Expressions%20\(C%23%20Programming%20Guide\).md)