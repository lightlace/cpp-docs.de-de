---
title: "Compilerfehler C2881"
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
  - "C2881"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2881"
ms.assetid: b49c63c2-b064-4d4b-a75e-ddd2af947522
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2881
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Namespace1': Wird bereits als Alias für 'Namespace2' verwendet  
  
 Für zwei Namespaces kann nicht derselbe Name als Alias verwendet werden.  
  
 Im folgenden Beispiel wird C2881 generiert:  
  
```  
// C2881.cpp  
// compile with: /c  
namespace A {  
   int k;  
}  
  
namespace B {  
   int i;  
}  
  
namespace C = A;  
namespace C = B;   // C2881 C is already an alias for A  
```