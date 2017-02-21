---
title: "Compilerfehler C2010 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2010"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2010"
ms.assetid: 5795ed1d-e206-410b-b7b4-528d125c67b4
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2010
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Zeichen': unerwartetes Zeichen in Makroparameterliste  
  
 Das Zeichen wird in der Liste formaler Parameter einer Makrodefinition falsch verwendet.  Entfernen Sie das Zeichen, um den Fehler zu beheben.  
  
 Im folgenden Beispiel wird C2010 generiert:  
  
```  
// C2010.cpp  
// compile with: /c  
#define mymacro(a|) (2*a)   // C2010  
#define mymacro(a) (2*a)   // OK  
```