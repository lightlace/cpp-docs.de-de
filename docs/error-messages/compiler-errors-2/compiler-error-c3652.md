---
title: "Compilerfehler C3652 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3652"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3652"
ms.assetid: 15d68737-177e-41f1-80e0-7c3e2afdf0fc
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C3652
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Überschreibung': Eine Funktion, die explizite Überschreibungen durchführt, muss virtuell sein  
  
 Eine Funktion, die eine explizite Überschreibung vornimmt, muss als "virtuell" deklariert werden.  Weitere Informationen finden Sie unter [Explizite Überschreibungen](../../windows/explicit-overrides-cpp-component-extensions.md).  
  
 Im folgenden Beispiel wird C3652 generiert:  
  
```  
// C3652.cpp  
// compile with: /clr /c  
public interface class I {  
   void f();  
};  
  
public ref struct R : I {  
   void f() = I::f {}   // C3652  
   // try the following line instead  
   // virtual void f() = I::f {}  
};  
```