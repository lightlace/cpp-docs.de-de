---
title: "Compilerfehler C2824"
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
  - "C2824"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2824"
ms.assetid: 5bd865f7-e0af-404e-80fe-e2b798b44a59
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2824
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Rückgabetyp für Operator "new" muss "void \*" sein  
  
 Bei nicht basierten Zeigern muss von Überladungen des Operators `new` `void *` zurückgegeben werden.  
  
 Im folgenden Beispiel wird C2824 generiert:  
  
```  
// C2824.cpp  
// compile with: /c  
class   A {  
   A* operator new(size_t i, char *m);   // C2824  
   // try the following line instead  
   // void* operator new(size_t i, char *m);  
};  
```