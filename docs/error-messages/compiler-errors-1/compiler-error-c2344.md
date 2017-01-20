---
title: "Compilerfehler C2344"
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
  - "C2344"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2344"
ms.assetid: a84c7b37-c84e-4345-8691-c23abb2dc193
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2344
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

align\(\#\): Die Ausrichtung muss eine Potenz von 2 sein.  
  
 Bei Verwendung des [align](../../cpp/align-cpp.md)\-Schlüsselworts muss der übergebene Wert eine Potenz von zwei sein.  
  
 Im folgenden Code wird beispielsweise C2344 erzeugt, weil 3 keine Potenz von 2 ist:  
  
```  
// C2344.cpp // compile with: /c __declspec(align(3)) int a;   // C2344 __declspec(align(4)) int b;   // OK  
```