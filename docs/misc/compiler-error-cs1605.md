---
title: "Compilerfehler CS1605"
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
  - "CS1605"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1605"
ms.assetid: a202d3a9-9777-4902-a7b9-1628640f9433
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1605
'var' kann nicht als ref\- oder out\-Argument übergeben werden, da das Element schreibgeschützt ist.  
  
 Bei einer Variablen, die als [ref](../Topic/ref%20\(C%23%20Reference\).md)\- oder [out](../Topic/out%20\(C%23%20Reference\).md)\-Parameter übergeben wird, wird erwartet, dass sie in der aufgerufenen Methode bearbeitet wird. Daher ist es nicht möglich, einen schreibgeschützten Parameter als `ref` oder `out` zu übergeben.