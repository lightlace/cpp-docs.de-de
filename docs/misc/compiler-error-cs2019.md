---
title: "Compilerfehler CS2019"
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
  - "CS2019"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS2019"
ms.assetid: eafd2531-8b3a-499c-9e12-a605a011396f
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS2019
Ungültiger Zieltyp für \/target: Sie müssen "exe", "winexe", "library", oder "module" angeben.  
  
 Die [\/target](../Topic/-target%20\(C%23%20Compiler%20Options\).md)\-Compileroption wurde verwendet, aber es wurde ein ungültiger Parameter übergeben. Kompilieren Sie das Programm mithilfe der Form der **\/target**\-Option neu, die für die Ausgabedatei geeignet ist, um diesen Fehler zu beheben.  
  
 Im folgenden Beispiel wird CS2017 generiert:  
  
```  
// CS2019.cs // compile with: /target:libra // CS2019 expected class MyClass { }  
```