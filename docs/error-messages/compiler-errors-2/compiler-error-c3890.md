---
title: "Compilerfehler C3890 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3890"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3890"
ms.assetid: 2f22c2fd-c14e-45e1-b936-b739ffc0b135
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C3890
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': Sie können die Adresse eines literal\-Datenmembers nicht übernehmen  
  
 Ein literal\-Datenmember ist auf dem Heap der Garbage Collection vorhanden.  Ein Objekt auf dem Heap der Garbage Collection kann verschoben werden, daher ist eine Übernahme der Adresse nicht sinnvoll.  
  
 Im folgenden Beispiel wird C3890 generiert:  
  
```  
// C3890.cpp  
// compile with: /clr  
ref struct Y1 {  
   literal int staticConst = 9;  
};  
  
int main() {  
   int p = &Y1::staticConst;   // C3890  
   int p2 = Y1::staticConst;   // OK  
}  
```