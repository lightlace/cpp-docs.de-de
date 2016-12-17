---
title: "Compilerwarnung (Stufe 1) C4353"
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
  - "C4353"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4353"
ms.assetid: 6e79f186-ed82-4c95-9923-0ad5bb9c4db1
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4353
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verwendung einer Nicht\-Standarderweiterung: Konstante 0 \(null\) als Funktionsausdruck.Verwenden Sie stattdessen die systeminterne Funktion '\_\_noop'  
  
 Die Konstante Null \(0\) kann nicht als Funktionsausdruck verwendet werden.  Weitere Informationen finden Sie unter [\_\_noop](../../intrinsics/noop.md).  
  
 Im folgenden Beispiel wird C4353 generiert:  
  
```  
// C4353.cpp  
// compile with: /W1  
void MyPrintf(void){};  
#define X 0  
#if X  
   #define DBPRINT MyPrint  
#else  
   #define DBPRINT 0   // C4353 expected  
#endif  
int main(){  
DBPRINT();  
}  
```