---
title: "Compilerfehler C2767"
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
  - "C2767"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2767"
ms.assetid: e8f84178-a160-4d71-a236-07e4fcc11e96
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2767
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Dimensionen der verwalteten oder WinRT\-Arrays stimmen nicht überein: Erwartet wurde\(n\) N Argument\(e\), bereitgestellt wurde\(n\) M Argument\(e\).  
  
 Die Deklaration eines verwalteten oder WinRT\-Arrays wurde nicht ordnungsgemäß formatiert.  Weitere Informationen finden Sie unter [Array](../../windows/arrays-cpp-component-extensions.md).  
  
 Im folgenden Beispiel wird C2767 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2767.cpp  
// compile with: /clr  
int main() {  
   array<int> ^p1 = new array<int>(2,3); // C2767  
   array<int> ^p2 = new array<int>(2);   // OK  
}  
```