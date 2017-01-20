---
title: "Compilerfehler CS2005"
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
  - "CS2005"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS2005"
ms.assetid: 03535d2a-ae30-4272-ab45-e277df5ee8e1
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS2005
Fehlende Dateispezifikation für die Option "Option".  
  
 Eine [Compileroption](../Topic/C%23%20Compiler%20Options.md) wurde nur teilweise angegeben.  
  
 Bei Verwendung von [\/recurse](../Topic/-recurse%20\(C%23%20Compiler%20Options\).md) müssen Sie beispielsweise die zu durchsuchende Datei angeben: **\/recurse:***Dateiname***cs**.  
  
## Beispiel  
 Im folgenden Beispiel wird CS2005 generiert.  
  
```  
// CS2005.cs // compile with: /recurse: // CS2005 expected class x { public static void Main() {} }  
```