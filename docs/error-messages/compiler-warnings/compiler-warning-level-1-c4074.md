---
title: "Compilerwarnung (Stufe 1) C4074"
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
  - "C4074"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4074"
ms.assetid: cd510e66-c338-4a86-a4d7-bfa1df9b16c3
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4074
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Initialisierungen stehen im für den Compiler reservierten Initialisierungsbereich  
  
 Der durch [\#pragma init\_seg](../../preprocessor/init-seg.md) festgelegte Compilerinitialisierungsbereich wurde von Microsoft reserviert.  Code in diesem Bereich kann vor der Initialisierung der C\-Laufzeitbibliothek ausgeführt werden.  
  
 Im folgenden Beispiel wird C4074 generiert:  
  
```  
// C4074.cpp  
// compile with: /W1  
#pragma init_seg( compiler )   // C4074  
  
// try this line to resolve the warning  
// #pragma init_seg(user)  
  
int main() {  
}  
```