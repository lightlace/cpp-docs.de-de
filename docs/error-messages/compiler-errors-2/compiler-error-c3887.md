---
title: "Compilerfehler C3887"
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
  - "C3887"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3887"
ms.assetid: a7e82426-ef99-437b-9562-2822004e18fe
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3887
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': der Initialisierer für einen literalen Datenmember muss ein konstanter Ausdruck sein  
  
 Ein literaler [Datenmember](../../windows/literal-cpp-component-extensions.md) kann nur mit einem konstanten Ausdruck initialisiert werden.  
  
 Im folgenden Beispiel wird C3887 generiert:  
  
```  
// C3887.cpp  
// compile with: /clr  
ref struct Y1 {  
   static int i = 9;  
   literal  
   int staticConst = i;   // C3887  
};  
```  
  
 Mögliche Lösung:  
  
```  
// C3887b.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   literal  
   int staticConst = 9;  
};  
```