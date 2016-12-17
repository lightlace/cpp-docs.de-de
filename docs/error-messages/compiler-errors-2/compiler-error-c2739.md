---
title: "Compilerfehler C2739"
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
  - "C2739"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2739"
ms.assetid: 5b63e435-7631-43d7-805e-f2adefb7e517
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
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