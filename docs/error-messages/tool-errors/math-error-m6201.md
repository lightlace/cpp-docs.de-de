---
title: "Mathematischer Fehler M6201 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "M6201"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6201"
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Mathematischer Fehler M6201
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion' : \_DOMAIN error  
  
 Ein Argument der angegebenen Funktion befindet sich außerhalb des für Eingabewerte dieser Funktion zulässigen Bereichs.  
  
## Beispiel  
  
```  
result = sqrt(-1.0)   // C statement  
result = SQRT(-1.0)   !  FORTRAN statement  
```  
  
 Dieser Fehler führt zum Aufruf der `_matherr`\-Funktion mit dem Namen der Funktion, ihrer Argumente und des Fehlertyps.  Die `_matherr`\-Funktion kann neu geschrieben werden, um die Behandlung bestimmter Laufzeitfehler der Gleitkommaarithmetik anzupassen.