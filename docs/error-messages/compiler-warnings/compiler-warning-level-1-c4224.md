---
title: "Compilerwarnung (Stufe 1) C4224 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4224"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4224"
ms.assetid: 1531cae0-5040-49fd-b149-005bb5085391
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4224
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht dem Standard entsprechende Erweiterung: Formaler Parameter 'Bezeichner' wurde zuvor als Typ definiert  
  
 Der Bezeichner wurde zuvor bereits als `typedef` verwendet.  Bei Einhaltung der ANSI\-Kompatibilität \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) wird hierdurch eine Warnung ausgegeben.  
  
## Beispiel  
  
```  
// C4224.cpp  
// compile with: /Za /W1 /LD  
typedef int I;  
void func ( int I );  // C4224  
```