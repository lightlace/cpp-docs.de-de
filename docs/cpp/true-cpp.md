---
title: "true (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "true_cpp"
  - "true"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "true-Schlüsselwort [C++]"
ms.assetid: 96be2a70-51c3-4250-9752-874d25a5a11e
caps.latest.revision: 12
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# true (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
  
        bool-identifier = true ;  
bool-expression logical-operator true ;  
```  
  
## Hinweise  
 Dieses Schlüsselwort ist einer der zwei Werte für eine Variable des Typs [bool](../cpp/bool-cpp.md) oder ein bedingter Ausdruck \(ein bedingter Ausdruck ist jetzt ein boolescher Ausdruck mit dem Wert "true"\).  Wenn `i` vom Typ `bool` ist, erhält `i = true;` von der Anweisung  **den Wert `i`true** zugewiesen.  
  
## Beispiel  
  
```  
// bool_true.cpp  
#include <stdio.h>  
int main()  
{  
    bool bb = true;  
    printf_s("%d\n", bb);  
    bb = false;  
    printf_s("%d\n", bb);  
}  
```  
  
  **1**  
**0**   
## Siehe auch  
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)