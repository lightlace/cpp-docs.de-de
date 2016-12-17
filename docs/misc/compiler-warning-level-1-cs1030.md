---
title: "Compilerwarnung (Stufe 1) CS1030"
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
  - "CS1030"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1030"
ms.assetid: 7c565abc-1366-4641-9383-ab8ba026ab96
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerwarnung (Stufe 1) CS1030
\#warning: "Text"  
  
 Zeigt den Text einer mit der [\#warning](../Topic/%23warning%20\(C%23%20Reference\).md)\-Direktive angegebenen Warnung an.  
  
 Das folgende Beispiel zeigt, wie eine benutzerdefinierte Warnung erstellt wird:  
  
```  
// CS1030.cs class Sample { static void Main() { #warning Let's give a warning here   // CS1030 } }  
```