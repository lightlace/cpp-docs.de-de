---
title: "Compilerwarnung (Stufe 1) C4602 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4602"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4602"
ms.assetid: c1f0300f-e2a2-4c9e-a7c3-4c7318d10509
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerwarnung (Stufe 1) C4602
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma pop\_macro: 'Makroname' Kein vorangehendes '\#pragma push\_macro' für diesen Bezeichner definiert.  
  
 Wenn Sie [pop\_macro](../../preprocessor/pop-macro.md) für ein bestimmtes Makro verwenden, müssen Sie zunächst den entsprechenden Makronamen an [push\_macro](../../preprocessor/push-macro.md) übergeben. Im folgenden Beispiel wird C4602 generiert:  
  
```  
// C4602.cpp // compile with: /W1 int main() { #pragma pop_macro("x")   // C4602 x is not on the stack }  
```