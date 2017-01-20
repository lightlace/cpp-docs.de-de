---
title: "Compilerwarnung (Stufe 4) C4400"
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
  - "C4400"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4400"
ms.assetid: f135fe98-4f92-4e07-9d71-2621b36ee755
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4400
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Typ": const\/volatile\-Qualifizierer werden für diesen Typ nicht unterstützt  
  
 Der [const](../../cpp/const-cpp.md)\-Qualifizierer und der [volatile](../../cpp/volatile-cpp.md)\-Qualifizierer können nicht mit Variablentypen der Common Language Runtime verwendet werden.  
  
## Beispiel  
 Im folgenden Beispiel wird C4400 generiert.  
  
```  
// C4400.cpp  
// compile with: /clr /W4  
// C4401 expected  
using namespace System;  
#pragma warning (disable : 4101)  
int main() {  
   const String^ str;   // C4400  
   volatile String^ str2;   // C4400  
}  
```