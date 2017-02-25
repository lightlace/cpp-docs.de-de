---
title: "Compilerfehler C3140 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3140"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3140"
ms.assetid: 122f8943-fac3-4db8-a3a8-2c5d19233de6
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C3140
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Es können nicht mehrere "module"\-Attribute in der gleichen Kompilationseinheit vorhanden sein  
  
 Das [module](../../windows/module-cpp.md)\-Attribut kann nur einmal pro Projekt definiert werden.  
  
 Im folgenden Beispiel wird C3140 generiert:  
  
```  
// C3140.cpp  
// compile with: /c  
[emitidl];  
[module(name = "MyLibrary")];  
[module(name = "MyLibrary2")];   // C3140  
```