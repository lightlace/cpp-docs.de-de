---
title: "Compilerfehler C2714 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2714"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2714"
ms.assetid: 401a5a42-660c-4bad-9d63-1a2d092bc489
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C2714
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\_\_alignof\(void\) ist nicht zulässig  
  
 Einem Operator wurde ein ungültiger Wert übergeben.  
  
 Weitere Informationen finden Sie unter [\_\_alignof\-Operator](../../cpp/alignof-operator.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C2714 generiert.  
  
```  
// C2714.cpp  
int main() {  
   return __alignof(void);   // C2714  
   return __alignof(char);   // OK  
}  
```