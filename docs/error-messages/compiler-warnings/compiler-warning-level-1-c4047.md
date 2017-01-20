---
title: "Compilerwarnung (Stufe 1) C4047"
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
  - "C4047"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4047"
ms.assetid: b75ad6fb-5c93-4434-a85f-c4083051a5de
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4047
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Operator': 'Bezeichner1' unterscheidet sich in Ebenen der Dereferenzierung von 'Bezeichner2'  
  
 Ein Zeiger kann auf eine Variable \(eine Dereferenzierungsebene\), auf einen anderen Zeiger, der auf eine Variable zeigt \(zwei Dereferenzierungsebenen\), zeigen usw.  
  
## Beispiel  
 Im folgenden Beispiel wird C4047 generiert:  
  
```  
// C4047.c  
// compile with: /W1  
  
int main() {  
   char **p = 0;   // two levels of indirection  
   char *q = 0;   // one level of indirection  
  
   char *p2 = 0;   // one level of indirection  
   char *q2 = 0;   // one level of indirection  
  
   p = q;   // C4047  
   p2 = q2;  
}  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C4047 generiert:  
  
```  
// C4047b.c  
// compile with: /W1  
#include <stdio.h>  
  
int main() {  
   int i;  
   FILE *myFile = NULL;  
   errno_t  err = 0;  
   char file_name[256];  
   char *cs = 0;  
  
   err = fopen_s(&myFile, "C4047.txt", "r");  
   if ((err != 0) || (myFile)) {  
      printf_s("fopen_s failed!\n");  
      exit(-1);  
    }  
   i = fgets(file_name, 256, myFile);   // C4047  
   cs = fgets(file_name, 256, myFile);   // OK  
}  
```