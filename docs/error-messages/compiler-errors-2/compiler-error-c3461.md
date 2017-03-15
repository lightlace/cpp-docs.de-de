---
title: "Compilerfehler C3461 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3461"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3461"
ms.assetid: bd66833a-545d-445a-bdfe-dee771a450a4
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C3461
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ': Nur ein verwalteter Typ kann weitergeleitet werden.  
  
 Die Typweiterleitung ist nur bei CLR\-Typen möglich.  Weitere Informationen finden Sie unter [Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md).  
  
 Weitere Informationen finden Sie unter [Type Forwarding \(C\+\+\/CLI\)](../../windows/type-forwarding-cpp-cli.md).  
  
## Beispiel  
 Im folgenden Beispiel wird eine Komponente erstellt:  
  
```  
// C3461.cpp // compile with: /clr /LD public ref class R {};  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C3461 generiert:  
  
```  
// C3461b.cpp // compile with: /clr /c #using "C3461.dll" class N {}; [assembly:TypeForwardedTo(N::typeid)];   // C3461 [assembly:TypeForwardedTo(R::typeid)];   // OK  
```