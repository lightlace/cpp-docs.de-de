---
title: "Compilerwarnung (Stufe 1) C4163 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4163"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4163"
ms.assetid: b08413fd-03fc-4f41-9167-a98976ac12f2
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4163
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'bezeichner': nicht als intrinsische Funktion verfügbar  
  
 Die angegebene Funktion kann nicht als [intrinsische](../../preprocessor/intrinsic.md) Funktion verwendet werden. Der Compiler ignoriert den ungültigen Funktionsnamen.  
  
 Im folgenden Beispiel wird C4163 generiert.  
  
```  
// C4163.cpp // compile with: /W1 /LD #include <math.h> #pragma intrinsic(mysin)   // C4163 // try the following line instead // #pragma intrinsic(sin)  
```