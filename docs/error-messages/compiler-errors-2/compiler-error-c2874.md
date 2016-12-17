---
title: "Compilerfehler C2874"
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
  - "C2874"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2874"
ms.assetid: b54fa9d8-8df5-40d9-9b3b-aa3e9dd6a3be
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2874
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

using\-Deklaration verursacht eine mehrfache Deklaration von 'Symbol'  
  
 Die Deklaration bewirkt, dass dasselbe Element zweimal definiert wird.  
  
 Im folgenden Beispiel wird C2874 generiert:  
  
```  
// C2874.cpp  
namespace Z {  
   int i;  
}  
  
int main() {  
   int i;  
   using Z::i;   // C2874, i already declared  
}  
```