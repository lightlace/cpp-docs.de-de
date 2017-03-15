---
title: "Compilerfehler C2675 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2675"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2675"
ms.assetid: 4b92a12b-bff8-4dd5-a109-620065fc146c
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Compilerfehler C2675
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unärer Operator 'Operator': 'Typ' definiert diesen Operator oder eine Konvertierung in einen für den vordefinierten Operator geeigneten Typ nicht  
  
 C2675 kann auch auftreten, wenn ein unärer Operator verwendet wird und der Typ diesen Operator oder eine Konvertierung in einen für den vordefinierten Operator geeigneten Typ nicht definiert.  Um den Operator zu verwenden, müssen Sie ihn für den angegebenen Typ überladen oder eine Konvertierung in einen Typ definieren, für den der Operator definiert ist.  
  
## Beispiel  
 Im folgenden Beispiel wird C2675 generiert.  
  
```  
// C2675.cpp  
struct C {   
   C(){}  
} c;  
  
struct D {   
   D(){}  
   void operator-(){}  
} d;  
  
int main() {  
   -c;   // C2675  
   -d;   // OK  
}  
```