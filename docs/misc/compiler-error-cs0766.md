---
title: "Compilerfehler CS0766"
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
  - "CS0766"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0766"
ms.assetid: 4574e30b-3e76-42cd-90e8-31c72126a08c
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0766
Partielle Methoden müssen einen void\-Rückgabetyp haben.  
  
 Eine partielle Methode kann keinen Wert zurückgeben. Der Rückgabetyp muss "void" sein.  
  
### So beheben Sie diesen Fehler  
  
1.  Weisen Sie der partiellen Methode einen void\-Rückgabetyp zu, oder konvertieren Sie die Methode in eine reguläre \(nicht partielle\) Methode.  
  
## Beispiel  
 Im folgenden Beispiel wird CS0766 generiert:  
  
```  
// cs0766.cs using System; public partial class C { partial int Part(); // CS0766 // Typically the implementing declaration // is contained in a separate file. partial int Part() //CS0766 { } public static int Main() { return 1; } }  
```  
  
## Siehe auch  
 [Partielle Klassen und Methoden](../Topic/Partial%20Classes%20and%20Methods%20\(C%23%20Programming%20Guide\).md)