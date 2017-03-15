---
title: "false (C++)"
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
  - "false_cpp"
  - "false"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "false-Schlüsselwort [C++]"
ms.assetid: cc13aec5-1f02-4d38-8dbf-5473ea2b354f
caps.latest.revision: 11
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# false (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Schlüsselwort ist eines der zwei Werte für eine Variable des Typs [bool](../cpp/bool-cpp.md) oder ein bedingter Ausdruck \(ein bedingter Ausdruck ist jetzt ein boolescher Ausdruck mit dem Wert **true**\).  Wenn z. B. `i` eine Variable vom Typ `bool` ist, weist die `i = false;`\-Anweisung der **\-Variablen den Wert `i`false** zu.  
  
## Beispiel  
  
```  
// bool_false.cpp  
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