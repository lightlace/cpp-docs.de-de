---
title: "Compilerfehler C2748"
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
  - "C2748"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2748"
ms.assetid: b63ac78b-a200-499c-afea-15af1a1e819e
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2748
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

verwaltet oder WinRT\-Arrayerstellung muss eine Arraygröße oder einen Arrayinitialisierung besitzen  
  
 Eine verwaltete oder ein WinRT\-Array wurde nicht ordnungsgemäß formatiert.  Weitere Informationen finden Sie unter [Array](../../windows/arrays-cpp-component-extensions.md).  
  
 Im folgenden Beispiel wird C2748 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2748.cpp  
// compile with: /clr  
int main() {  
   array<int> ^p1 = new array<int>();   // C2748  
   // try the following line instead  
   array<int> ^p2 = new array<int>(2);  
}  
```