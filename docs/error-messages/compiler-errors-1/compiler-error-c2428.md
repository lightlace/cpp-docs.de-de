---
title: "Compilerfehler C2428 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2428"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2428"
ms.assetid: 74aa5714-e930-4f9e-9061-68ccce7f0d38
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2428
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Operation': Nicht erlaubt bei einem Operanden des Typs 'bool'  
  
 Dekrementoperatoren können nicht auf Objekte vom Typ `bool` angewendet werden.  
  
 Im folgenden Beispiel wird C2428 generiert:  
  
```  
// C2428.cpp  
void g(bool fFlag) {  
   --fFlag;   // C2428  
   fFlag--;   // C2428  
}  
```