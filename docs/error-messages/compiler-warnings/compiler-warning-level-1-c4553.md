---
title: "Compilerwarnung (Stufe 1) C4553 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4553"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4553"
ms.assetid: d8aacbe0-3cb5-4367-a6e5-fd7e28f0ff9d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 1) C4553
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Operator': Operator hat keine Auswirkungen; ist 'Operator' beabsichtigt?  
  
 Wenn eine Ausdrucksanweisung einen Operator ohne Nebeneffekte am Anfang des Ausdrucks hat, liegt wahrscheinlich ein Fehler vor.  
  
 Im folgenden Beispiel wird C4553 generiert:  
  
```  
// C4553.cpp  
// compile with: /W1  
int func()  
{  
   return 0;  
}  
  
int main()  
{  
   int i;  
   i == func();   // C4553  
   // try the following line instead  
   // i = func();  
}  
```