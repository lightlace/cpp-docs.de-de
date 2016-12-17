---
title: "Compilerfehler C2793"
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
  - "C2793"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2793"
ms.assetid: ce35f4e8-c357-40ca-95c4-15ff001ad69d
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
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