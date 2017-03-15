---
title: "Compilerwarnung (Stufe 1) C4551 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4551"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4551"
ms.assetid: 458b59bd-e2d7-425f-9ba6-268ff200424f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 1) C4551
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dem Funktionsaufruf fehlt die Argumentliste  
  
 Ein Funktionsaufruf muss öffnende und schließende runde Klammern hinter dem Funktionsnamen enthalten, auch wenn die Funktion keine Parameter annimmt.  
  
 Im folgenden Beispiel wird C4551 generiert:  
  
```  
// C4551.cpp  
// compile with: /W1  
void function1() {  
}  
  
int main() {  
   function1;   // C4551  
   function1();   // OK  
}  
```