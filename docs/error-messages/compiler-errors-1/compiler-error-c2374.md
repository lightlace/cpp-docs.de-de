---
title: "Compilerfehler C2374"
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
  - "C2374"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2374"
ms.assetid: 73b51965-e91c-4e21-9732-f71c1449d22e
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2374
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"identifier": Neudefinition; Mehrfachinitialisierung  
  
 Der Bezeichner wird mehrfach initialisiert.  
  
 Im folgenden Beispiel wird C2374 generiert:  
  
```  
// C2374.cpp // compile with: /c int i = 0; int i = 1;   // C2374 int j = 1;   // OK  
```