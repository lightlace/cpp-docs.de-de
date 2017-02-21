---
title: "Compilerfehler C2886 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2886"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2886"
ms.assetid: c01588a1-484c-4dc9-a3f1-f900c6e44543
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2886
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class::identifier' : Symbol kann nicht in der using\-Deklaration eines Members verwendet werden  
  
 Eine `using`\-Deklaration verwendet ein Symbol, z. B. den Namen für einen Namespace.  `using`\-Deklarationen werden zum Deklarieren von Basisklassenmembern verwendet.  
  
 Im folgenden Beispiel wird C2886 generiert:  
  
```  
// C2886.cpp  
// compile with: /c  
namespace Z {  
    int i;  
}  
  
class B {  
protected:  
    int i;  
};  
  
class D : public B {  
    // Error: Z is a namespace  
    using Z::i;   // C2886  
  
    // OK: B is a base class  
    using B::i;  
};  
```