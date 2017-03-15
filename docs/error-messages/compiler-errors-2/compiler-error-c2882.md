---
title: "Compilerfehler C2882 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2882"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2882"
ms.assetid: 617018ee-5a0d-4b8d-9612-77e8ae52679b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2882
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Name': Unzulässige Verwendung eines Namespacebezeichners in einem Ausdruck  
  
 Sie haben versucht, den Namen eines Namespaces in einem Ausdruck zu verwenden.  
  
 Im folgenden Beispiel wird C2882 generiert:  
  
```  
// C2882.cpp  
// compile with: /c  
namespace A {  
   int k;  
}  
  
int i = A;   // C2882, can't assign A to i  
```