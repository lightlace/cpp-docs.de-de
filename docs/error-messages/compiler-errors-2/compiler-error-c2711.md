---
title: "Compilerfehler C2711 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2711"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2711"
ms.assetid: 9df9f808-7419-4e63-abdd-e6538ff0871f
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C2711
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion' : Diese Funktion kann nicht als verwaltet kompiliert werden. Verwenden Sie ggf. \#Pragma und nicht verwaltet  
  
 Einige Anweisungen verhindern, dass der Compiler MSIL für die einschließende Funktion generiert.  
  
 Im folgenden Beispiel wird C2711 generiert:  
  
```  
// C2711.cpp  
// compile with: /clr  
// processor: x86  
using namespace System;  
value struct V {  
   static const t = 10;  
};  
  
void bar() {  
   V::t;  
   __asm int 3   // C2711 inline asm can't be compiled managed  
}  
```