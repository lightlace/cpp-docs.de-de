---
title: "Compilerfehler C3648 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3648"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3648"
ms.assetid: 5d042989-41cb-4cd0-aa50-976b70146aaf
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C3648
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese explizite Überschreibungssyntax erfordert \/clr:oldSyntax  
  
 Bei der Kompilierung für die neueste verwaltete Syntax hat der Compiler eine explizite Überschreibungssyntax für die vorherigen Versionen gefunden.  
  
 Weitere Informationen finden Sie unter [Explizite Überschreibungen](../../windows/explicit-overrides-cpp-component-extensions.md).  Weitere Informationen über die ältere Syntax finden Sie unter [Expliziten Überschreibungen](../../cpp/explicit-overrides-cpp.md).  
  
 Im folgenden Beispiel wird C3648 generiert:  
  
```  
// C3648.cpp  
// compile with: /clr  
public interface struct I {  
   void f();  
};  
  
public ref struct R : I {  
   virtual void I::f() {}   // C3648  
   // try the following line instead  
   // virtual void f() = I::f{}  
};  
```