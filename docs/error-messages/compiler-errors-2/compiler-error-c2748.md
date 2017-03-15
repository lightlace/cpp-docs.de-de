---
title: "Compilerfehler C2748 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2748"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2748"
ms.assetid: b63ac78b-a200-499c-afea-15af1a1e819e
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
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