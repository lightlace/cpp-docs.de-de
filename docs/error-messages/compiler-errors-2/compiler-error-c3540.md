---
title: "Compilerfehler C3540 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3540"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3540"
ms.assetid: 3c0c959c-e3b7-40eb-b922-ccac44bd9d85
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C3540
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Typ": sizeof kann nicht für einen Typ übernommen werden, der "Auto" enthält  
  
 Der [sizeof](../../cpp/sizeof-operator.md)\-Operator kann nicht auf den angegebenen Typ angewendet werden, da dieser den `auto`\-Spezifizierer enthält.  
  
## Beispiel  
 Im folgenden Beispiel wird C3540 ergeben.  
  
```  
// C3540.cpp  
// Compile with /Zc:auto  
int main() {  
    auto x = 123;  
    sizeof(x);    // OK  
    sizeof(auto); // C3540  
    return 0;  
}  
```  
  
## Siehe auch  
 [Auto\-Schlüsselwort](../../cpp/auto-keyword.md)   
 [\/Zc:auto \(Variablentyp ableiten\)](../../build/reference/zc-auto-deduce-variable-type.md)   
 [sizeof\-Operator](../../cpp/sizeof-operator.md)