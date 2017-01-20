---
title: "Compilerfehler C3697"
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
  - "C3697"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3697"
ms.assetid: 2d3f63c4-b7f8-421d-a7a5-2bf17fd054f9
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3697
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Qualifizierer': Dieser Qualifizierer kann nicht für '^' verwendet werden  
  
 Das Trackinghandle \(^\) wurde auf einen Qualifizierer angewendet, für den es nicht vorgesehen ist.  
  
 Im folgenden Beispiel wird C3697 generiert:  
  
```  
// C3697.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   String ^__restrict s;   // C3697  
   String ^ s2;   // OK  
}  
```