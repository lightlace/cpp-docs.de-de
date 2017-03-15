---
title: "Compilerfehler C2425 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2425"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2425"
ms.assetid: 0ce59404-9aff-4e01-aa8d-27d23e92eb30
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2425
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'token': nicht konstanter Ausdruck in 'Kontext'  
  
 Das Token ist Teil eines nicht konstanten Ausdrucks in diesem Kontext.  
  
 Um dieses Problem zu beheben, ersetzen Sie das Token mit einer Berechnung oder einem konstanten Buchstabensymbol.  
  
 Im folgenden Beispiel wird C2425 generiert:  
  
```  
// C2425.cpp  
// processor: x86  
int main() {  
   int i = 3;  
   __asm {  
      mov eax, [ebp - i]   // C2425  
      mov eax, [ebp - 3]   // OK  
   }  
}  
```