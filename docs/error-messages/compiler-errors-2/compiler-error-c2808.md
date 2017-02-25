---
title: "Compilerfehler C2808 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2808"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2808"
ms.assetid: 3d745102-d3b3-4735-a7d2-ad42d5bf3cfa
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2808
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der unäre 'Operator Operator' hat zu viele formale Parameter  
  
 Der unäre Operator verfügt über eine Parameterliste, die nicht void ist.  
  
 Im folgenden Beispiel wird C2808 generiert:  
  
```  
// C2808.cpp  
// compile with: /c  
class X {  
public:  
   X operator! ( X );   // C2808 nonvoid parameter list  
   X operator! ( void );   // OK  
};  
  
```