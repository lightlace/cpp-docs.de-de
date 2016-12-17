---
title: "Compilerwarnung (Stufe 4) C4429"
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
  - "C4429"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4429"
ms.assetid: a3e4cf1f-a869-4e47-834a-850c21eb5297
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4429
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unvollständiger oder falsch formatierter universaler Zeichenname  
  
 Der Compiler hat eine Zeichenfolge gefunden, die möglicherweise ein falsch formatierter universaler Zeichenname ist.  Ein universaler Zeichenname ist `\u` gefolgt von vier hexadezimalen Stellen oder `\U` gefolgt von acht hexadezimalen Stellen.  
  
 Im folgenden Beispiel wird C4429 generiert:  
  
```  
// C4429.cpp  
// compile with: /W4 /WX  
int \ug0e4 = 0;   // C4429  
// Try the following line instead:  
// int \u00e4 = 0;   // OK, a well-formed universal character name.  
```