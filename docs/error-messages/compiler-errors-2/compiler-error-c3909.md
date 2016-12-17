---
title: "Compilerfehler C3909"
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
  - "C3909"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3909"
ms.assetid: 0a443132-e53f-42dc-a58b-f086da3e7bfd
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3909
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine WinRT\- oder verwaltete Ereignisdeklaration muss in einem WinRT\- oder verwalteten Typ auftreten  
  
 Ein Windows\-Runtime\-Ereignis oder verwaltetes Ereignis wurde in einem systemeigenen Typ deklariert.  Deklarieren Sie zum Beheben dieses Fehlers Ereignisse in Windows\-Runtime\-Typen oder verwalteten Typen.  
  
 Weitere Informationen finden Sie unter [event](../../windows/event-cpp-component-extensions.md).  
  
 Im folgenden Beispiel wird C3909 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3909.cpp  
// compile with: /clr /c  
delegate void H();  
class X {  
   event H^ E;   // C3909 - use ref class X instead  
};  
  
ref class Y {  
   static event H^ E {  
      void add(H^) {}  
      void remove( H^ h ) {}  
      void raise( ) {}  
   }  
};  
```