---
title: "Compilerfehler C3895"
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
  - "C3895"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3895"
ms.assetid: 771b9fe5-d6d4-4297-bf57-e2f857722155
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3895
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': Typdatenmember können nicht 'volatile' sein  
  
 Bestimmte Arten von Datenmembern, z. B. [literal](../../windows/literal-cpp-component-extensions.md) oder [initonly](../../dotnet/initonly-cpp-cli.md), können nicht [volatile](../../cpp/volatile-cpp.md) sein.  
  
 Im folgenden Beispiel wird C3895 generiert:  
  
```  
// C3895.cpp  
// compile with: /clr  
ref struct Y1 {  
   initonly  
   volatile int data_var2;   // C3895  
};  
```