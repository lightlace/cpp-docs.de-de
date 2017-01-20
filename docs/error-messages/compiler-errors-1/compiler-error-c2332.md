---
title: "Compilerfehler C2332"
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
  - "C2332"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2332"
ms.assetid: fb05cd68-e271-4bea-9fb7-ef4edb0a26ac
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2332
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'typedef': Fehlender Tagname  
  
 Der Compiler hat eine unvollständige Typdefinition gefunden.  
  
 Im folgenden Beispiel wird C2332 generiert:  
  
```  
// C2332.cpp  
// compile with: /c  
struct S {  
   int i;  
};  
  
typedef struct * pS;   // C2332  
typedef struct S* pS;   // OK  
  
int get_S_i(pS p) {  
   return p->i;  
}  
```