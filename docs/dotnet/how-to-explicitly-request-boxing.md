---
title: "Gewusst wie: Explizites Anfordern von Boxing"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Boxing, explizit anfordern"
ms.assetid: 1359e6e5-162d-4f5d-9b6a-1690d93df3ee
caps.latest.revision: 11
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Explizites Anfordern von Boxing
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können Boxing explizit anfordern, indem Sie eine Variable für eine Variable des Typs `Object` zuweisen.  
  
## Beispiel  
  
```  
// vcmcppv2_explicit_boxing3.cpp  
// compile with: /clr  
using namespace System;  
  
void f(int i) {  
   Console::WriteLine("f(int i)");  
}  
  
void f(Object ^o) {  
   Console::WriteLine("f(Object^ o)");  
}  
  
int main() {  
   int i = 5;  
   Object ^ O = i;   // forces i to be boxed  
   f(i);  
   f(O);  
   f( (Object^)i );  // boxes i  
}  
```  
  
  **f \(int i\)**  
**f \(Object^ O\)**  
**f \(Object^ O\)**   
## Siehe auch  
 [Boxing](../windows/boxing-cpp-component-extensions.md)