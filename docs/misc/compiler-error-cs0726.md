---
title: "Compilerfehler CS0726"
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
  - "CS0726"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0726"
ms.assetid: 9ea5f004-cf25-4e6e-b9e5-6b53e4a7e1ab
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0726
"format specifier" ist kein gültiger Formatbezeichner  
  
 Dieser Fehler tritt im Debugger auf. Wenn Sie einen Variablennamen in einem der Debugfenster eingeben, können Sie diesem ein Komma und dann einen Formatbezeichner anfügen. Beispiele: `myInt, h` und `myString,nq`. Dieser Fehler tritt auf, wenn der Compiler den [Formatbezeichner in C\#](../Topic/Format%20Specifiers%20in%20C%23.md) nicht erkennt.