---
title: "Compilerfehler CS1038"
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
  - "CS1038"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1038"
ms.assetid: 05c53ae9-2819-4771-aee8-3f2ff6bcf0b0
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1038
\#endregion\-Direktive erwartet.  
  
 Eine [\#region](../Topic/%23region%20\(C%23%20Reference\).md)\-Direktive hatte keine passende [\#endregion](../Topic/%23endregion%20\(C%23%20Reference\).md)\-Direktive.  
  
 Im folgenden Beispiel wird CS1038 generiert:  
  
```  
// CS1038.cs #region testing public class clx { public static void Main() { } } // CS1038 // uncomment the next line to resolve // #endregion  
```