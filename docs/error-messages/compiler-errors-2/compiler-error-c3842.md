---
title: "Compilerfehler C3842 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3842"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3842"
ms.assetid: 41a1a44a-c618-40a2-8d26-7da27d14095d
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerfehler C3842
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Qualifizierer 'function': 'const' und 'volatile' in Memberfunktionen von WinRT oder verwalteten Typen werden nicht unterstützt.  
  
 [const](../../cpp/const-cpp.md) und [flüchtige](../../cpp/volatile-cpp.md) werden in Memberfunktionen der Windows\-Runtime oder von verwalteten Typen nicht unterstützt.  
  
 Im folgenden Beispiel wird C3842 generiert:  
  
```  
// C3842a.cpp  
// compile with: /clr /c  
public ref struct A {  
   void f() const {}   // C3842  
   void f() volatile {}   // C3842  
  
   void f() {}  
};  
  
```