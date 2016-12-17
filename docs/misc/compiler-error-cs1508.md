---
title: "Compilerfehler CS1508"
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
  - "CS1508"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1508"
ms.assetid: 979bc615-58ce-49f8-ba73-e6cf57c56418
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1508
Der Ressourcenbezeichner "Bezeichner" wurde in dieser Assembly bereits verwendet.  
  
 In einer Kompilierung wurde derselbe Bezeichner \(***Bezeichner***\) an mindestens zwei [\/resource](../Topic/-resource%20\(C%23%20Compiler%20Options\).md)\- oder [\/linkresource](../Topic/-linkresource%20\(C%23%20Compiler%20Options\).md)\-Compileroptionen übergeben.  
  
 Folgende Optionen würden beispielsweise CS1508 generieren:  
  
```  
/resource:anyfile.bmp,DuplicatIdent /linkresource:a.bmp,DuplicatIdent  
```