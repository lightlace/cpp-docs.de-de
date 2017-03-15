---
title: "Compilerwarnung (Stufe 1) C4167 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4167"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4167"
ms.assetid: 74a420bd-9371-4167-b1ee-74dd8680f97b
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 1) C4167
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Funktion: Nur als systeminterne Funktion verfügbar  
  
 Die **\#pragma\-Funktion** versucht zu erzwingen, dass der Compiler einen konventionellen Aufruf für eine Funktion verwendet, die in systeminterner Form verwendet werden muss. Das Pragma wird ignoriert.  
  
 Um diese Warnung zu vermeiden, entfernen Sie die **\#pragma\-Funhtion**.  
  
## Beispiel  
  
```  
// C4167.cpp // compile with: /W1 #include <malloc.h> #pragma function(_alloca )   // C4167: _alloca() is intrinsic only int main(){}  
```