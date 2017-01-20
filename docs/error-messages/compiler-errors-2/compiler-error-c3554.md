---
title: "Compilerfehler C3554"
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
  - "C3554"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3554"
ms.assetid: aede18d5-fefc-4da9-9b69-adfe90bfa742
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3554
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"decltype" kann nicht mit einem anderen Typspezifizierer kombiniert werden.  
  
 Sie können das `decltype()`\-Schlüsselwort nicht mit einem Typspezifizierer qualifizieren. Das folgende Codefragment verursacht beispielsweise den Fehler C3554 .  
  
```  
int x; unsigned decltype(x); // C3554  
```