---
title: "Compilerfehler C2739 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2739"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2739"
ms.assetid: 5b63e435-7631-43d7-805e-f2adefb7e517
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerfehler C2739
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Nummer" : Explizit verwaltet oder WinRT\-Arraydimensionen müssen zwischen 1 und 32 liegen  
  
 Eine Arraydimension lag nicht zwischen 1 und 32.  
  
 Im folgenden Beispiel wird C2739 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2739.cpp  
// compile with: /clr  
int main() {  
   array<int, -1>^a;   // C2739  
   // try the following line instead  
   // array<int, 2>^a;  
}  
```