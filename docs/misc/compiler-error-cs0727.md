---
title: "Compilerfehler CS0727"
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
  - "CS0727"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0727"
ms.assetid: 54bfb87e-d759-4310-a8ab-02dccd06337c
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0727
Ungültiger Formatbezeichner  
  
 Dieser Fehler tritt im Debugger auf. Wenn Sie einen Variablennamen in einem der Debugfenster eingeben, können Sie diesem ein Komma und dann einen Formatbezeichner anfügen. Beispiele sind: „myInt, h“ und „myString,nq“. Dieser Fehler tritt auf, wenn der Compiler die von Ihnen vorgenommene Eingabe überhaupt nicht analysieren kann. Um diesen Fehler zu beheben, geben Sie den Variablennamen erneut ein, und geben Sie optional hinter diesem ein Komma und einen [gültigen Formatbezeichner](../Topic/Format%20Specifiers%20in%20C%23.md) ein.