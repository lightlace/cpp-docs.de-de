---
title: "Compilerfehler CS0744"
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
  - "CS0744"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0744"
ms.assetid: 7ce430d6-737a-4103-9116-d9a4a69f8af3
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0744
Kontextbezogenes Schlüsselwort "equals" erwartet.  
  
 Das Muster für eine `join`\-Klausel ist `join`...`in`...`on`...`equals`, wie im folgenden Beispiel gezeigt:  
  
```  
var query = from x in array1 join y in array2 on x equals y select x;  
```  
  
### So beheben Sie diesen Fehler  
  
1.  Fügen Sie der `join`\-Klausel das `equals`Schlüsselwort hinzu.  
  
## Beispiel  
 Mit dem folgenden Code wird CS0744 generiert:  
  
```  
// cs0744.cs using System; using System.Linq; public class C { public static int Main() { int[] array1 = { 1, 2, 3 ,4, 5, 6,}; int[] array2 = { 5, 6, 7, 8, 9 }; var c = from x in array1 join y in array2 on x y // CS0744 select x; return 1; } }  
```  
  
## Siehe auch  
 [LINQ\-Abfrageausdrücke](../Topic/LINQ%20Query%20Expressions%20\(C%23%20Programming%20Guide\).md)   
 [join\-Klausel](../Topic/join%20clause%20\(C%23%20Reference\).md)