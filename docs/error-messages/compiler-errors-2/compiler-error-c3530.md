---
title: "Compilerfehler C3530 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3530"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3530"
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Compilerfehler C3530
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Auto" kann nicht mit einem anderen Typspezifizierer kombiniert werden  
  
 Ein Typspezifizierer wird mit dem `auto`\-Schlüsselwort verwendet.  
  
### So beheben Sie diesen Fehler  
  
1.  Verwenden Sie keinen Typspezifizierer in einer Variablendeklaration, die das `auto`\-Schlüsselwort verwendet.  
  
## Beispiel  
 Im folgenden Beispiel wird C3530 erzeugt, da die Variable `x` sowohl mit dem `auto`\-Schlüsselwort als auch mit dem `int`\-Typ deklariert und das Beispiel mit **\/Zc:auto** kompiliert wird.  
  
```  
// C3530.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto int x;   // C3530  
   return 0;  
}  
```  
  
## Siehe auch  
 [Auto\-Schlüsselwort](../../cpp/auto-keyword.md)