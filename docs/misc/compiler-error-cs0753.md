---
title: "Compilerfehler CS0753"
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
  - "CS0753"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0753"
ms.assetid: 287dd9da-da74-4290-9fa1-21ef1a8150fe
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0753
Nur Methoden, Klassen, Strukturen oder Schnittstellen können partiell sein.  
  
 Der [partial](../Topic/partial%20\(Type\)%20\(C%23%20Reference\).md)\-Modifizierer kann nur mit Klassen, Strukturen, Schnittstellen und Methoden verwendet werden.  
  
### So beheben Sie diesen Fehler  
  
1.  Entfernen Sie den `partial`\-Modifizierer aus dem Variablen\- bzw. Sprachkonstrukt.  
  
## Beispiel  
 Durch den folgenden Code wird der Fehler CS0753 ausgelöst:  
  
```  
// cs0753.cs using System; public partial class C { partial int num; // CS0753 public static int Main() { return 1; } }  
```  
  
## Siehe auch  
 [Partielle Klassen und Methoden](../Topic/Partial%20Classes%20and%20Methods%20\(C%23%20Programming%20Guide\).md)