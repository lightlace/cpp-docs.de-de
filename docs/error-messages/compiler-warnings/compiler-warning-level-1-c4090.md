---
title: "Compilerwarnung (Stufe 1) C4090 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4090"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4090"
ms.assetid: baad469d-23d4-45aa-ad9c-305b32d61e9a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4090
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Operation': Unterschiedliche 'Modifizierer'\-Qualifizierer  
  
 Eine in einer Operation verwendete Variable wurde mit einem speziellen Modifizierer definiert, der eine Änderung der Variablen verhindert, ohne dass sie vom Compiler erkannt wird.  Der Ausdruck wird unverändert kompiliert.  
  
 Diese Warnung kann verursacht werden, wenn ein Zeiger auf **const** oder `volatile` einem Zeiger zugewiesen ist, der nicht als Zeiger auf **const** oder `volatile` deklariert wurde.  
  
 Diese Warnung wird für C\-Programme ausgegeben.  In einem C\+\+\-Programm gibt der Compiler den Fehler [C2440](../../error-messages/compiler-errors-1/compiler-error-c2440.md) aus.  
  
 Im folgenden Beispiel wird C4090 generiert:  
  
```  
// C4090.c  
// compile with: /W1  
int *volatile *p;  
int *const *q;  
int **r;  
  
int main() {  
   p = q;   // C4090  
   p = r;  
   q = p;   // C4090  
   q = r;  
   r = p;   // C4090  
   r = q;   // C4090  
}  
```