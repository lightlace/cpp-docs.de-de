---
title: "Compilerfehler CS1103"
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
  - "CS1103"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1103"
ms.assetid: 513a26ea-9d66-4dc3-b3e6-d709c3089b1a
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1103
Der erste Parameter einer Erweiterungsmethode darf nicht den Typ "Typ" haben.  
  
 Der erste Parameter einer Erweiterungsmethode darf kein Zeigertyp sein.  
  
## Beispiel  
 Im folgenden Beispiel wird CS1103 generiert:  
  
```  
// cs1103.cs public static class Extensions { public unsafe static char* Test(this char* charP) { return charP; } // CS1103 }   
```  
  
## Siehe auch  
 [Erweiterungsmethoden](../Topic/Extension%20Methods%20\(C%23%20Programming%20Guide\).md)   
 [Unsicher](../Topic/unsafe%20\(C%23%20Reference\).md)