---
title: "Compilerwarnung (Stufe 1) C4606"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4606"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4606"
ms.assetid: c1b45fb6-672b-42eb-9e1c-c67b3e4150d3
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4606
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#Pragmawarnung : 'warning\_number' wurde ignoriert. Warnungen der Codeanalyse sind keine Warnstufen zugeordnet  
  
 Bei Warnungen der Codeanalyse werden nur `error`, `once` und `default` für das [warning](../../preprocessor/warning.md)\-Pragma unterstützt.  
  
## Beispiel  
 Im folgenden Beispiel wird C4606 generiert.  
  
```  
// C4606.cpp  
// compile with: /c /W1  
#pragma warning(1: 6001)   // C4606  
#pragma warning(once: 6001)   // OK  
```