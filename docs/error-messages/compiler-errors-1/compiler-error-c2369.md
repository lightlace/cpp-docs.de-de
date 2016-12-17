---
title: "Compilerfehler C2369"
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
  - "C2369"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2369"
ms.assetid: 2a3933f6-2313-40ff-800f-921b296fdbbf
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2369
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Array': Neudefinition. Unterschiedliche Feldindizes  
  
 Das Array wurde bereits mit einem anderen Feldindex deklariert.  
  
 Im folgenden Beispiel wird C2369 generiert:  
  
```  
// C2369.cpp // compile with: /c int a[10]; int a[20];   // C2369 int b[20];   // OK  
```