---
title: "Compilerfehler C2586"
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
  - "C2586"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2586"
ms.assetid: dae703c7-5c38-4db6-8411-4d1b22713eb5
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2586
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fehlerhafte benutzerdefinierte Konvertierungssyntax: unzulässige Dereferenzierung  
  
 Die Dereferenzierung eines Konvertierungsoperators ist nicht zulässig.  
  
 Im folgenden Beispiel wird C2586 generiert:  
  
```  
// c2586.cpp  
// compile with: /c  
struct C {  
   * operator int();   // C2586  
   operator char();   // OK  
};  
```