---
title: "Compilerfehler C2793 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2793"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2793"
ms.assetid: ce35f4e8-c357-40ca-95c4-15ff001ad69d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2793
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Token': Auf '::' folgen unerwartete Token; Bezeichner oder Schlüsselwort 'operator' erwartet  
  
 Die einzigen Token, die auf `__super::` folgen können, sind ein Bezeichner oder das Schlüsselwort `operator`.  
  
 Im folgenden Beispiel wird C2793 generiert:  
  
```  
// C2793.cpp  
struct B {  
   void mf();  
};  
  
struct D : B {  
   void mf() {  
      __super::(); // C2793  
   }  
};  
```