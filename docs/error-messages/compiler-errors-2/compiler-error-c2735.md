---
title: "Compilerfehler C2735"
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
  - "C2735"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2735"
ms.assetid: 6ce45600-7148-4bc0-8699-af0ef137571e
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2735
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Schlüsselwort 'Schlüsselwort' ist in Typangabe eines formalen Parameters nicht erlaubt  
  
 Das Schlüsselwort ist in diesem Kontext ungültig.  
  
 Im folgenden Beispiel wird C2735 generiert:  
  
```  
// C2735.cpp  
void f(inline int){}   // C2735  
```