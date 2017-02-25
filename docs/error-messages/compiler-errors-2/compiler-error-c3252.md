---
title: "Compiler Error C3252 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3252"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3252"
ms.assetid: aa9ad096-e9ac-41c7-8ad9-b966751c7c75
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compiler Error C3252
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Methode" : Der Zugriff auf eine virtuelle Methode kann in einem verwaltetem oder WinRT\-Typ nicht reduziert werden.  
  
 Eine Klasse, die eine virtuelle Methode von einer Basisklasse oder eine Methode implementiert, kann den Zugriff auf diese Methode nicht reduzieren.  
  
 Beachten Sie, dass alle Methoden in einer Schnittstelle öffentlich sind.  
  
 Im folgenden Beispiel wird C3252 generiert und gezeigt, wie Sie diesen Fehler beheben.  
  
```  
// C3252.cpp  
// compile with: /clr /c  
ref class A {  
public:  
   virtual void f1() {}  
};  
  
ref class B : public A {  
// To fix, uncomment the following line:   
// public:      
   virtual void f1() override sealed {}   // C3252, make this method public  
};  
```