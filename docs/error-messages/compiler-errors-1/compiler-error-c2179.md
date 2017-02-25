---
title: "Compilerfehler C2179 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2179"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2179"
ms.assetid: f929bfc6-3964-4e54-87d6-7529b9b6c0b9
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2179
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ': Ein Attributargument kann keine Typparameter verwenden  
  
 Ein generischer Typparameter wird zur Laufzeit aufgelöst.  Ein Attributparameter muss jedoch zur Kompilierzeit aufgelöst werden.  Deshalb können Sie keinen generischen Typparameter als Argument für ein Attribut verwenden.  
  
## Beispiel  
 Im folgenden Beispiel wird C2179 generiert.  
  
```  
// C2179.cpp  
// compile with: /clr  
using namespace System;  
  
public ref struct Attr : Attribute {  
   Attr(Type ^ a) {  
      x = a;  
   }  
  
   Type ^ x;  
};  
  
ref struct G {};  
  
generic<typename T>   
public ref class Z {   
public:  
   Type ^ d;  
   [Attr(T::typeid)]   // C2179  
   // try the following line instead  
   // [Attr(G::typeid)]  
   T t;  
};  
```