---
title: "Compilerfehler C3886"
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
  - "C3886"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3886"
ms.assetid: 485f6c12-cc1b-4146-9034-409a0a5e615e
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3886
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': ein literaler Datenmember muss initialisiert werden  
  
 Eine [literale](../../windows/literal-cpp-component-extensions.md) Variable muss initialisiert werden, wenn sie deklariert ist.  
  
 Im folgenden Beispiel wird C3886 generiert:  
  
```  
// C3886.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   literal int staticConst;   // C3886  
   literal int staticConst2 = 0;   // OK  
};  
```