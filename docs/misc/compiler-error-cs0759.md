---
title: "Compilerfehler CS0759"
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CS0759"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0759"
ms.assetid: 96f0e178-adbf-4327-8934-ac282c428184
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0759
Für die implementierende Deklaration der partiellen Methode "Methode" wurde keine definierende Deklaration gefunden.  
  
 Eine partielle Methode muss über eine definierende Deklaration verfügen, durch die die Signatur \(Name, Rückgabetyp und Parameter\) der Methode definiert wird. Der Implementierungs\- oder Methodentext ist optional.  
  
### So beheben Sie diesen Fehler  
  
1.  Geben Sie eine definierende Deklaration für die partielle Methode im anderen Teil einer partiellen Klasse oder Struktur an.  
  
## Beispiel  
 Im folgenden Beispiel wird CS0759 generiert:  
  
```  
// cs0759.cs using System; public partial class C { partial void Part() // CS0759 { } public static int Main() { return 1; } }  
```  
  
## Siehe auch  
 [Partielle Klassen und Methoden](../Topic/Partial%20Classes%20and%20Methods%20\(C%23%20Programming%20Guide\).md)