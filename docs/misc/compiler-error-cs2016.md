---
title: "Compilerfehler CS2016"
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
  - "CS2016"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS2016"
ms.assetid: 69f77502-f726-4856-ac87-e556eeb67349
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS2016
Die Codepage "Codepage" ist ungültig oder nicht installiert.  
  
 An die Compileroption [\/codepage](../Topic/-codepage%20\(C%23%20Compiler%20Options\).md) wurde ein ungültiger Wert übergeben.  
  
 Im folgenden Beispiel wird CS2016 generiert:  
  
```  
// CS2016.cs // compile with: /codepage:x // CS2016 expected class MyClass { public static void Main() { } }  
```