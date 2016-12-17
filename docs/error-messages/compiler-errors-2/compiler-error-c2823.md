---
title: "Compilerfehler C2823"
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
  - "C2823"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2823"
ms.assetid: 982b1b35-1a7c-456e-b711-f80cfe2d571e
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2823
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine typedef\-Vorlage ist ungültig  
  
 Vorlagen sind in [typedef](assetId:///cc96cf26-ba93-4179-951e-695d1f5fdcf1)\-Definitionen nicht zulässig.  
  
 Im folgenden Beispiel wird C2823 generiert:  
  
```  
// C2823.cpp  
template<class T>  
typedef struct x {  
   T i;   // C2823 can't use T, specify data type and delete template  
   int i;   // OK  
} x1;  
```