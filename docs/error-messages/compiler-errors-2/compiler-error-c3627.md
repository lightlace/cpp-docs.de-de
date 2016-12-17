---
title: "Compilerfehler C3627"
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
  - "C3627"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3627"
ms.assetid: 905ad0a0-8c49-4187-b66e-b375f5a1fae5
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3627
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nur ein Werttyp kann geschachtelt werden  
  
 Nur Werteklassen können gepackt werden.  
  
 Im folgenden Beispiel wird C3627 generiert:  
  
```  
// C3627.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__value class vA {  
};  
  
__gc class A {  
};  
  
int main()  
{  
   A* a;  
   __box(a);   // C3627  
  
   // box a value type  
   vA va;  
   __box(va);  
}  
```