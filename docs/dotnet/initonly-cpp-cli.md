---
title: "initonly (C++/CLI)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "initonly_cpp"
  - "initonly"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "initonly-Attribut [C++]"
ms.assetid: f745d7fa-dc08-46f1-9b97-0977be58a008
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "mblome"
manager: "ghogen"
---
# initonly (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**initonly** ist ein Schlüsselwort, das kontextbezogenes dieser Variablenzuweisung kann nur als Teil der Deklaration oder in einem statischen Konstruktor in derselben Klasse auftreten angibt.  
  
 Im folgenden Beispiel wird die Verwendung von `initionly` veranschaulicht.  
  
```  
// mcpp_initonly.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   initonly  
   static int staticConst1;  
  
   initonly  
   static int staticConst2 = 0;  
  
   static Y1() {  
      staticConst1 = 0;  
   }  
};  
```  
  
## Siehe auch  
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)