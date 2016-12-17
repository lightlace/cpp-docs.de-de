---
title: "Compilerwarnung (Stufe 1) C4602"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C4602"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4602"
ms.assetid: c1f0300f-e2a2-4c9e-a7c3-4c7318d10509
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4602
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma pop\_macro: 'Makroname' Kein vorangehendes '\#pragma push\_macro' für diesen Bezeichner definiert.  
  
 Wenn Sie [pop\_macro](../../preprocessor/pop-macro.md) für ein bestimmtes Makro verwenden, müssen Sie zunächst den entsprechenden Makronamen an [push\_macro](../../preprocessor/push-macro.md) übergeben. Im folgenden Beispiel wird C4602 generiert:  
  
```  
// C4602.cpp // compile with: /W1 int main() { #pragma pop_macro("x")   // C4602 x is not on the stack }  
```