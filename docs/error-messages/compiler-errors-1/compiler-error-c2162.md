---
title: "Compilerfehler C2162"
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
  - "C2162"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2162"
ms.assetid: 34923628-d35e-48ab-9072-b95e3b5f6b45
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2162
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Formaler Makroparameter erwartet  
  
 Bei dem auf einen Zeichenfolgenoperator \(\#\) folgenden Token handelte es sich nicht um den Namen eines formalen Parameters.  
  
## Beispiel  
 Im folgenden Beispiel wird C2162 generiert:  
  
```  
// C2162.cpp  
// compile with: /c  
#include <stdio.h>  
  
#define print(a) printf_s(b)   // OK  
#define print(a) printf_s(#b)    // C2162  
```