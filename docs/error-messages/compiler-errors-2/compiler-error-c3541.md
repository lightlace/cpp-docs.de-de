---
title: "Compilerfehler C3541 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3541"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3541"
ms.assetid: 252cfd4c-5fd2-415e-a17d-6b0c254350db
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C3541
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Typ": typeid kann nicht für einen Typ übernommen werden, der "Auto" enthält  
  
 Der [typeid](../../windows/typeid-cpp-component-extensions.md)\-Operator kann nicht auf den angegebenen Typ angewendet werden, da dieser den `auto`\-Spezifizierer enthält.  
  
## Beispiel  
 Das folgende Beispiel ergibt C3541.  
  
```  
// C3541.cpp  
// Compile with /Zc:auto  
#include <typeinfo>  
int main() {  
    auto x = 123;  
    typeid(x);    // OK  
    typeid(auto); // C3541  
    return 0;  
}  
```  
  
## Siehe auch  
 [Auto\-Schlüsselwort](../../cpp/auto-keyword.md)   
 [\/Zc:auto \(Variablentyp ableiten\)](../../build/reference/zc-auto-deduce-variable-type.md)   
 [typeid](../../windows/typeid-cpp-component-extensions.md)