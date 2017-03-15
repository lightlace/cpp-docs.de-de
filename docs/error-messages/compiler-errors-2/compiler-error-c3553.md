---
title: "Compilerfehler C3553 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3553"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3553"
ms.assetid: 7f84bf37-6419-4ad3-ab30-64266100b930
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# Compilerfehler C3553
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"decltype" erwartet einen Ausdruck und keinen Typ.  
  
 Das `decltype()`\-Schlüsselwort benötigt einen Ausdruck als Argument, nicht den Namen eines Typs. Im folgenden Codefragment wird beispielsweise durch die letzte Anweisung der Fehler C3553 verursacht.  
  
 `int x = 0;`  
  
 `decltype(x+1);`  
  
 `decltype(int); // C3553`