---
title: "Compilerfehler C3554 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3554"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3554"
ms.assetid: aede18d5-fefc-4da9-9b69-adfe90bfa742
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# Compilerfehler C3554
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"decltype" kann nicht mit einem anderen Typspezifizierer kombiniert werden.  
  
 Sie können das `decltype()`\-Schlüsselwort nicht mit einem Typspezifizierer qualifizieren. Das folgende Codefragment verursacht beispielsweise den Fehler C3554 .  
  
```  
int x; unsigned decltype(x); // C3554  
```