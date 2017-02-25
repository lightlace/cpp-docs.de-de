---
title: "Compilerfehler C2814 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2814"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2814"
ms.assetid: 7d165136-a08b-4497-a76d-60a21bb19404
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# Compilerfehler C2814
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„Member“: Ein systemeigener Typ kann innerhalb eines verwalteten oder WinRT\-Typs „Typ“ nicht geschachtelt werden.  
  
## Beispiel  
 Ein systemeigener Typ kann nicht in einem CLR\- oder WinRT\-Typ geschachtelt werden.  Im folgenden Beispiel wird C2814 generiert und gezeigt, wie Sie diesen Fehler beheben.  
  
```  
// C2814.cpp  
// compile with: /clr /c  
ref class A {  
   class B {};   // C2814  
   ref class C {};   // OK  
};  
```  
  
## Beispiel  
 Bei Verwendung von Managed Extensions for C\+\+ müssen Sie „managed\-ness“ eines eingebetteten Typs explizit mit einem der folgenden Schlüsselwörter angeben: [\_\_gc](../../misc/gc.md), [\_\_nogc](../../misc/nogc.md) oder [\_\_value](../../misc/value.md).  
  
 Im folgenden Beispiel wird C2814 generiert und gezeigt, wie Sie diesen Fehler beheben.  
  
```  
// C2814_b.cpp  
// compile with: /clr:oldSyntax /c  
__gc class A {  
   class B {};   // C2814  
   __gc class C {};   // OK  
};  
```