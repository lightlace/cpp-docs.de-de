---
title: "Compilerfehler C2462 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2462"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2462"
ms.assetid: a8601bf8-f5ce-41de-9117-e2632bd4996b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2462
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner' : Ein Typ kann nicht in einem 'new\-Ausdruck' definiert werden  
  
 Ein Typ kann nicht im Operandenfeld des Operators `new` definiert werden.  Schreiben Sie die Typdefinition in eine separate Anweisung.  
  
 Im folgenden Beispiel wird C2462 generiert:  
  
```  
// C2462.cpp  
int main() {  
   new struct S { int i; };   // C2462  
}  
```