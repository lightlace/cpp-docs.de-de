---
title: "Compilerfehler C3734"
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
  - "C3734"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3734"
ms.assetid: 4e2afdcc-7da9-45a1-9c96-85f25e2986e8
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3734
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': Eine verwaltete oder WinRT\-Klasse kann kein „coclass“\-Attribut sein.  
  
 Das [coclass](../../windows/coclass.md)\-Attribut kann nicht zusammen mit verwalteten oder WinRT\-Klassen verwendet werden.  
  
 Im folgenden Beispiel wird C3734 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3734.cpp  
// compile with: /clr /c  
[module(name="x")];  
  
[coclass]  
ref class CMyClass {   // C3734 remove the ref keyword to resolve  
};  
```  
  
 Im folgenden Beispiel wird C3734 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3734_b.cpp  
// compile with: /clr:oldSyntax /c  
[module(name="x")];  
  
[coclass]  
__gc class CMyClass {   // C3734 remove the __gc keyword to resolve  
};  
```