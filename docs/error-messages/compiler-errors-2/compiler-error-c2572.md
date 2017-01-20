---
title: "Compilerfehler C2572"
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
  - "C2572"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2572"
ms.assetid: f1a42d69-727d-4ce5-88c8-d5f55dea66ac
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2572
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class::member': Neudefinition des Standardparameters: Parameter param  
  
 Standardparameter können nicht neu definiert werden.  Wenn für den Parameter ein anderer Wert erforderlich ist, sollte der Standardparameter nicht definiert werden.  
  
 Im folgenden Beispiel wird C2572 generiert:  
  
```  
// C2572.cpp  
// compile with: /c  
void f(int i = 1);   // function declaration  
  
// function definition  
void f(int i = 1) {}   // C2572  
  
// try the following line instead  
// void f(int i) {}  
```