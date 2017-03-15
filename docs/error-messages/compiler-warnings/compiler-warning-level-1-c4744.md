---
title: "Compilerwarnung (Stufe 1) C4744 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4744"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4744"
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerwarnung (Stufe 1) C4744
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' hat einen unterschiedlichen Typ in 'Datei1' und 'Datei2': 'Typ1' und 'Typ2'  
  
 Eine externe Variable, die in zwei Dateien referenziert oder definiert wurde, hat in diesen Dateien verschiedene Typen.  Zur Behebung des Problems gleichen Sie die Typdefinitionen an oder ändern den Variablennamen in einer der Dateien.  
  
 C4744 wird nur ausgegeben, wenn Dateien mit \/GL kompiliert werden.  Weitere Informationen finden Sie unter [\/GL \(Optimierung des ganzen Programms\)](../../build/reference/gl-whole-program-optimization.md).  
  
> [!NOTE]
>  C4744 tritt normalerweise in C\-Dateien \(nicht C\+\+\) auf, da in C\+\+ ein Variablenname mit Typinformationen ergänzt wird.  Wenn das folgende Beispiel als C\+\+ kompiliert wird, wird der Linkerfehler LNK2019 ausgegeben.  
  
## Beispiel  
 Dieses Beispiel enthält die erste Definition.  
  
```  
// C4744.c  
// compile with: /c /GL  
int global;  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C4744 generiert.  
  
```  
// C4744b.c  
// compile with: C4744.c /GL /W1  
// C4744 expected  
#include <stdio.h>  
  
extern unsigned global;  
  
main()   
{  
    printf_s("%d\n", global);  
}  
```