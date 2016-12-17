---
title: "Compilerfehler C2714"
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
  - "C2714"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2714"
ms.assetid: 401a5a42-660c-4bad-9d63-1a2d092bc489
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
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