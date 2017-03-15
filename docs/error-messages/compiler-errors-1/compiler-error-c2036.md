---
title: "Compilerfehler C2036 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2036"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2036"
ms.assetid: 895821a9-65d1-44b5-bde1-dae827f3e486
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C2036
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Unbekannte Größe  
  
 Eine für `identifier` ausgeführte Operation erfordert die Größe des Datenobjekts, die nicht ermittelt werden kann.  
  
## Beispiel  
 Im folgenden Beispiel wird C2036 generiert.  
  
```  
// C2036.c  
// a C program  
struct A* pA;  
struct B { int i; } *pB;  
int main() {  
   pA++;   // C2036, size of A not known  
   ((char*)pA)++;   // OK  
  
   pB++;   // OK  
}  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C2036 generiert.  
  
```  
// C2036_2.cpp  
// a C++ program  
struct A* pA;  
int main() {  
   pA++;   // C2036, size of A not known  
   ((char*&)pA)++;   // OK, if sizeof(A) == sizeof(char)  
}  
```